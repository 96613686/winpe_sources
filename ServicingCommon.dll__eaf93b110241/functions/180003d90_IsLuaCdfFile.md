# IsLuaCdfFile

- ea: `0x180003d90`
- end: `0x18000404f`
- name: `IsLuaCdfFile`
- size: `703`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180003d90`
- `0x180004060`
- `0x1800043d0`
- `0x18000a8d0`
- `0x18000be10`
- `0x18000c5c0`
- `0x18000ea30`
- `0x1800293a0`
- `0x180098b08`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180003f69`
- `KERNEL32!CloseHandle` at `0x180003f69`
- `ntdll!RtlFreeUnicodeString` at `0x180003f04`
- `ntdll!RtlFreeUnicodeString` at `0x18000403e`
- `ntdll!RtlFreeUnicodeString` at `0x180003f04`
- `ntdll!RtlFreeUnicodeString` at `0x18000403e`
- `ntdll!NtOpenFile` at `0x180003e7e`
- `ntdll!NtOpenFile` at `0x180003e7e`
- `ntdll!RtlInitUnicodeString` at `0x180003fa9`
- `ntdll!RtlInitUnicodeString` at `0x180003fa9`
- `ntdll!RtlFreeHeap` at `0x180003ea8`
- `ntdll!RtlFreeHeap` at `0x180003ea8`

## pseudocode

```c
__int64 __fastcall IsLuaCdfFile(const WCHAR *a1, _DWORD *a2)
{
  int v3; // ebx
  const WCHAR *v4; // rsi
  NTSTATUS v5; // edi
  void *v6; // rcx
  ULONG_PTR Information; // rdx
  int FileTable; // eax
  unsigned int v10; // r8d
  void *v11; // r9
  int v12; // ecx
  PCWSTR SourceString; // [rsp+38h] [rbp-D0h] BYREF
  struct _UNICODE_STRING SourceString_8; // [rsp+40h] [rbp-C8h] BYREF
  struct _UNICODE_STRING P_8; // [rsp+50h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-78h] BYREF
  void **v18; // [rsp+A8h] [rbp-60h] BYREF
  void *FileHandle; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v20; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v21; // [rsp+C8h] [rbp-40h]
  __int128 v22; // [rsp+D8h] [rbp-30h]
  struct _UNICODE_STRING DestinationString; // [rsp+E8h] [rbp-20h] BYREF

  *a2 = 0;
  SourceString = 0;
  FileHandle = 0;
  v18 = &CCodeIntegrityLookupContext::`vftable';
  P_8 = 0;
  SourceString_8 = 0;
  DestinationString = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v3 = LuaCdfCreateFileNameForFile(a1, &SourceString, &P_8, &SourceString_8);
  if ( v3 >= 0 )
  {
    v4 = SourceString;
    if ( SourceString )
    {
      ObjectAttributes.ObjectName = &SourceString_8;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      ObjectAttributes.RootDirectory = 0;
      IoStatusBlock = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v5 = NtOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 1u, 0);
      if ( v5 >= 0 )
      {
        v20 = (unsigned __int64)FileHandle;
        v22 = 0;
        BYTE8(v22) = 0;
        v21 = 0;
        v5 = RtlFileMapMapView(&v20);
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, SourceString_8.Buffer);
      SourceString_8.Buffer = 0;
      if ( v5 >= 0 )
      {
        IoStatusBlock = 0;
        v3 = CdfInitializeContext(&v18, &IoStatusBlock);
        if ( v3 < 0 )
          goto LABEL_7;
        RtlInitUnicodeString(&DestinationString, v4);
        Information = IoStatusBlock.Information;
        LODWORD(SourceString) = 0;
        if ( IoStatusBlock.Information )
          goto LABEL_27;
        FileTable = LuaCdfpFetchFileTable((struct _LUACDF_CONTEXT *)&IoStatusBlock);
        if ( FileTable < 0 )
          goto LABEL_19;
        Information = IoStatusBlock.Information;
        if ( IoStatusBlock.Information )
        {
LABEL_27:
          FileTable = CdfSearchStringTable(IoStatusBlock.Pointer, Information, &DestinationString, &SourceString);
          if ( FileTable < 0 )
            goto LABEL_19;
          if ( (_DWORD)SourceString != -1 )
          {
LABEL_22:
            if ( FileTable >= 0 )
            {
              v3 = FileTable;
              *a2 = 1;
LABEL_21:
              LuaCdfFreeContext(&IoStatusBlock);
              goto LABEL_7;
            }
LABEL_19:
            v3 = 0;
            if ( FileTable != -1073741772 )
              v3 = FileTable;
            goto LABEL_21;
          }
          v12 = -1073741772;
        }
        else
        {
          v12 = -1073741595;
        }
        FileTable = RtlXmlReportErrorFunction(v12, Information, v10, v11);
        goto LABEL_22;
      }
      v3 = 0;
      if ( v5 != -1073741772 )
        v3 = v5;
    }
    else
    {
      v3 = 0;
    }
  }
LABEL_7:
  if ( P_8.Buffer )
    RtlFreeUnicodeString(&P_8);
  if ( SourceString_8.Buffer )
    RtlFreeUnicodeString(&SourceString_8);
  v6 = FileHandle;
  v18 = &CCodeIntegrityLookupContext::`vftable';
  if ( FileHandle )
  {
    FileHandle = 0;
    CloseHandle(v6);
  }
  RtlFileMapFree(&v20);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003d90  mov     r11, rsp
0x180003d93  push    rbp
0x180003d94  push    rbx
0x180003d95  push    r15
0x180003d97  lea     rbp, [r11-28h]
0x180003d9b  sub     rsp, 110h
0x180003da2  mov     rax, cs:__security_cookie
0x180003da9  xor     rax, rsp
0x180003dac  mov     [rbp+20h+var_30], rax
0x180003db0  xorps   xmm0, xmm0
0x180003db3  mov     [r11-20h], r12
0x180003db7  xor     r15d, r15d
0x180003dba  mov     [r11-28h], r14
0x180003dbe  mov     r14, rdx
0x180003dc1  mov     [rdx], r15d
0x180003dc4  xorps   xmm1, xmm1
0x180003dc7  mov     [rsp+120h+SourceString], r15
0x180003dcc  lea     r12, ??_7CCodeIntegrityLookupContext@@6B@; const CCodeIntegrityLookupContext::`vftable'
0x180003dd3  mov     [rbp+20h+FileHandle], r15
0x180003dd7  lea     rdx, [rsp+120h+SourceString]
0x180003ddc  mov     [rbp+20h+var_80], r12
0x180003de0  lea     r9, [rsp+120h+SourceString+8]
0x180003de5  lea     r8, [rsp+120h+P+8]
0x180003dea  movups  xmmword ptr [rsp+120h+P+8], xmm0
0x180003def  movups  xmmword ptr [rsp+120h+SourceString+8], xmm1
0x180003df4  movups  xmmword ptr [rbp+20h+DestinationString.Length], xmm0
0x180003df8  movups  [rbp+20h+var_70], xmm0
0x180003dfc  movups  [rbp+20h+var_60], xmm0
0x180003e00  movups  [rbp+20h+var_50], xmm0
0x180003e04  call    LuaCdfCreateFileNameForFile
0x180003e09  mov     ebx, eax
0x180003e0b  test    eax, eax
0x180003e0d  js      loc_180003EF0
0x180003e13  mov     [rsp+120h+arg_10], rsi
0x180003e1b  mov     rsi, [rsp+120h+SourceString]
0x180003e20  test    rsi, rsi
0x180003e23  jz      loc_180003FF8
0x180003e29  xorps   xmm0, xmm0
0x180003e2c  mov     [rsp+120h+OpenOptions], r15d; OpenOptions
0x180003e31  lea     rax, [rsp+120h+SourceString+8]
0x180003e36  mov     [rsp+120h+arg_18], rdi
0x180003e3e  lea     r9, [rbp+20h+IoStatusBlock]; IoStatusBlock
0x180003e42  mov     [rsp+120h+ObjectAttributes.ObjectName], rax
0x180003e47  lea     r8, [rsp+120h+ObjectAttributes]; ObjectAttributes
0x180003e4c  mov     qword ptr [rsp+120h+ObjectAttributes.Length], 30h ; '0'
0x180003e55  mov     edx, 120089h; DesiredAccess
0x180003e5a  mov     qword ptr [rsp+120h+ObjectAttributes.Attributes], 40h ; '@'
0x180003e63  lea     rcx, [rbp+20h+FileHandle]; FileHandle
0x180003e67  mov     [rsp+120h+ObjectAttributes.RootDirectory], r15
0x180003e6c  movups  xmmword ptr [rbp+20h+IoStatusBlock], xmm0
0x180003e70  mov     [rsp+120h+ShareAccess], 1; ShareAccess
0x180003e78  movdqu  xmmword ptr [rsp+120h+ObjectAttributes.SecurityDescriptor], xmm0
0x180003e7e  call    cs:__imp_NtOpenFile
0x180003e85  nop     dword ptr [rax+rax+00h]
0x180003e8a  mov     edi, eax
0x180003e8c  test    eax, eax
0x180003e8e  jns     loc_180003F77
0x180003e94  mov     rcx, gs:60h
0x180003e9d  xor     edx, edx; Flags
0x180003e9f  mov     r8, [rsp+120h+P]; P
0x180003ea4  mov     rcx, [rcx+30h]; HeapHandle
0x180003ea8  call    cs:__imp_RtlFreeHeap
0x180003eaf  nop     dword ptr [rax+rax+00h]
0x180003eb4  mov     [rsp+120h+P], r15
0x180003eb9  test    edi, edi
0x180003ebb  js      loc_180003F54
0x180003ec1  xorps   xmm0, xmm0
0x180003ec4  lea     rdx, [rbp+20h+IoStatusBlock]
0x180003ec8  lea     rcx, [rbp+20h+var_80]
0x180003ecc  movdqu  xmmword ptr [rbp+20h+IoStatusBlock], xmm0
0x180003ed1  call    CdfInitializeContext
0x180003ed6  mov     ebx, eax
0x180003ed8  test    eax, eax
0x180003eda  jns     loc_180003FA2
0x180003ee0  mov     rdi, [rsp+120h+arg_18]
0x180003ee8  mov     rsi, [rsp+120h+arg_10]
0x180003ef0  mov     r14, [rsp+120h+var_20]
0x180003ef8  cmp     [rsp+120h+var_D0], r15
0x180003efd  jz      short loc_180003F10
0x180003eff  lea     rcx, [rsp+120h+P+8]; UnicodeString
0x180003f04  call    cs:__imp_RtlFreeUnicodeString
0x180003f0b  nop     dword ptr [rax+rax+00h]
0x180003f10  cmp     [rsp+120h+P], r15
0x180003f15  jnz     loc_180004039
0x180003f1b  mov     rcx, [rbp+20h+FileHandle]; hObject
0x180003f1f  mov     [rbp+20h+var_80], r12
0x180003f23  mov     r12, [rsp+108h]
0x180003f2b  test    rcx, rcx
0x180003f2e  jnz     short loc_180003F65
0x180003f30  lea     rcx, [rbp+20h+var_70]
0x180003f34  call    RtlFileMapFree
0x180003f39  mov     eax, ebx
0x180003f3b  mov     rcx, [rbp+20h+var_30]
0x180003f3f  xor     rcx, rsp; StackCookie
0x180003f42  call    __security_check_cookie
0x180003f47  add     rsp, 110h
0x180003f4e  pop     r15
0x180003f50  pop     rbx
0x180003f51  pop     rbp
0x180003f52  retn
0x180003f54  cmp     edi, 0C0000034h
0x180003f5a  mov     ebx, r15d
0x180003f5d  cmovnz  ebx, edi
0x180003f60  jmp     loc_180003EE0
0x180003f65  mov     [rbp+20h+FileHandle], r15
0x180003f69  call    cs:__imp_CloseHandle
0x180003f70  nop     dword ptr [rax+rax+00h]
0x180003f75  jmp     short loc_180003F30
0x180003f77  mov     rax, [rbp+20h+FileHandle]
0x180003f7b  lea     rcx, [rbp+20h+var_70]
0x180003f7f  xorps   xmm0, xmm0
0x180003f82  movups  [rbp+20h+var_70], xmm0
0x180003f86  mov     qword ptr [rbp+20h+var_70], rax
0x180003f8a  movups  [rbp+20h+var_50], xmm0
0x180003f8e  mov     byte ptr [rbp+20h+var_50+8], r15b
0x180003f92  movups  [rbp+20h+var_60], xmm0
0x180003f96  call    RtlFileMapMapView
0x180003f9b  mov     edi, eax
0x180003f9d  jmp     loc_180003E94
0x180003fa2  mov     rdx, rsi; SourceString
0x180003fa5  lea     rcx, [rbp+20h+DestinationString]; DestinationString
0x180003fa9  call    cs:__imp_RtlInitUnicodeString
0x180003fb0  nop     dword ptr [rax+rax+00h]
0x180003fb5  mov     rdx, [rbp+20h+IoStatusBlock.Information]
0x180003fb9  mov     dword ptr [rsp+120h+SourceString], r15d
0x180003fbe  test    rdx, rdx
0x180003fc1  jnz     short loc_180004010
0x180003fc3  lea     rcx, [rbp+20h+IoStatusBlock]; struct _LUACDF_CONTEXT *
0x180003fc7  call    ?LuaCdfpFetchFileTable@@YAJPEAU_LUACDF_CONTEXT@@@Z; LuaCdfpFetchFileTable(_LUACDF_CONTEXT *)
0x180003fcc  test    eax, eax
0x180003fce  jns     short loc_180004000
0x180003fd0  cmp     eax, 0C0000034h
0x180003fd5  mov     ebx, r15d
0x180003fd8  cmovnz  ebx, eax
0x180003fdb  lea     rcx, [rbp+20h+IoStatusBlock]
0x180003fdf  call    LuaCdfFreeContext
0x180003fe4  jmp     loc_180003EE0
0x180003fe9  test    eax, eax
0x180003feb  js      short loc_180003FD0
0x180003fed  mov     ebx, eax
0x180003fef  mov     dword ptr [r14], 1
0x180003ff6  jmp     short loc_180003FDB
0x180003ff8  mov     ebx, r15d
0x180003ffb  jmp     loc_180003EE8
0x180004000  mov     rdx, [rbp+20h+IoStatusBlock.Information]
0x180004004  test    rdx, rdx
0x180004007  jnz     short loc_180004010
0x180004009  mov     ecx, 0C00000E5h
0x18000400e  jmp     short loc_180004032
0x180004010  mov     rcx, qword ptr [rbp+20h+IoStatusBlock]
0x180004014  lea     r9, [rsp+120h+SourceString]
0x180004019  lea     r8, [rbp+20h+DestinationString]
0x18000401d  call    CdfSearchStringTable
0x180004022  test    eax, eax
0x180004024  js      short loc_180003FD0
0x180004026  cmp     dword ptr [rsp+120h+SourceString], 0FFFFFFFFh
0x18000402b  jnz     short loc_180003FE9
0x18000402d  mov     ecx, 0C0000034h; int
0x180004032  call    ?RtlXmlReportErrorFunction@@YAJJKKPEAX@Z; RtlXmlReportErrorFunction(long,ulong,ulong,void *)
0x180004037  jmp     short loc_180003FE9
0x180004039  lea     rcx, [rsp+120h+SourceString+8]; UnicodeString
0x18000403e  call    cs:__imp_RtlFreeUnicodeString
0x180004045  nop     dword ptr [rax+rax+00h]
0x18000404a  jmp     loc_180003F1B
```
