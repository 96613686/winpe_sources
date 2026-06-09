# IsLuaCdfFile

- ea: `0x18000b1c0`
- end: `0x18000b47f`
- name: `IsLuaCdfFile`
- size: `703`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002f80`
- `0x1800037f0`
- `0x180003bb8`
- `0x18000b1c0`
- `0x18000b490`
- `0x18000ba20`
- `0x18000bf20`
- `0x180018de4`
- `0x18002d2b0`
- `0x180096c5c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000b399`
- `KERNEL32!CloseHandle` at `0x18000b399`
- `ntdll!RtlFreeUnicodeString` at `0x18000b334`
- `ntdll!RtlFreeUnicodeString` at `0x18000b46e`
- `ntdll!RtlFreeUnicodeString` at `0x18000b334`
- `ntdll!RtlFreeUnicodeString` at `0x18000b46e`
- `ntdll!RtlInitUnicodeString` at `0x18000b3d9`
- `ntdll!RtlInitUnicodeString` at `0x18000b3d9`
- `ntdll!RtlFreeHeap` at `0x18000b2d8`
- `ntdll!RtlFreeHeap` at `0x18000b2d8`
- `ntdll!NtOpenFile` at `0x18000b2ae`
- `ntdll!NtOpenFile` at `0x18000b2ae`

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
0x18000b1c0  mov     r11, rsp
0x18000b1c3  push    rbp
0x18000b1c4  push    rbx
0x18000b1c5  push    r15
0x18000b1c7  lea     rbp, [r11-28h]
0x18000b1cb  sub     rsp, 110h
0x18000b1d2  mov     rax, cs:__security_cookie
0x18000b1d9  xor     rax, rsp
0x18000b1dc  mov     [rbp+20h+var_30], rax
0x18000b1e0  xorps   xmm0, xmm0
0x18000b1e3  mov     [r11-20h], r12
0x18000b1e7  xor     r15d, r15d
0x18000b1ea  mov     [r11-28h], r14
0x18000b1ee  mov     r14, rdx
0x18000b1f1  mov     [rdx], r15d
0x18000b1f4  xorps   xmm1, xmm1
0x18000b1f7  mov     [rsp+120h+SourceString], r15
0x18000b1fc  lea     r12, ??_7CCodeIntegrityLookupContext@@6B@; const CCodeIntegrityLookupContext::`vftable'
0x18000b203  mov     [rbp+20h+FileHandle], r15
0x18000b207  lea     rdx, [rsp+120h+SourceString]
0x18000b20c  mov     [rbp+20h+var_80], r12
0x18000b210  lea     r9, [rsp+120h+SourceString+8]
0x18000b215  lea     r8, [rsp+120h+P+8]
0x18000b21a  movups  xmmword ptr [rsp+120h+P+8], xmm0
0x18000b21f  movups  xmmword ptr [rsp+120h+SourceString+8], xmm1
0x18000b224  movups  xmmword ptr [rbp+20h+DestinationString.Length], xmm0
0x18000b228  movups  [rbp+20h+var_70], xmm0
0x18000b22c  movups  [rbp+20h+var_60], xmm0
0x18000b230  movups  [rbp+20h+var_50], xmm0
0x18000b234  call    LuaCdfCreateFileNameForFile
0x18000b239  mov     ebx, eax
0x18000b23b  test    eax, eax
0x18000b23d  js      loc_18000B320
0x18000b243  mov     [rsp+120h+arg_10], rsi
0x18000b24b  mov     rsi, [rsp+120h+SourceString]
0x18000b250  test    rsi, rsi
0x18000b253  jz      loc_18000B428
0x18000b259  xorps   xmm0, xmm0
0x18000b25c  mov     [rsp+120h+OpenOptions], r15d; OpenOptions
0x18000b261  lea     rax, [rsp+120h+SourceString+8]
0x18000b266  mov     [rsp+120h+arg_18], rdi
0x18000b26e  lea     r9, [rbp+20h+IoStatusBlock]; IoStatusBlock
0x18000b272  mov     [rsp+120h+ObjectAttributes.ObjectName], rax
0x18000b277  lea     r8, [rsp+120h+ObjectAttributes]; ObjectAttributes
0x18000b27c  mov     qword ptr [rsp+120h+ObjectAttributes.Length], 30h ; '0'
0x18000b285  mov     edx, 120089h; DesiredAccess
0x18000b28a  mov     qword ptr [rsp+120h+ObjectAttributes.Attributes], 40h ; '@'
0x18000b293  lea     rcx, [rbp+20h+FileHandle]; FileHandle
0x18000b297  mov     [rsp+120h+ObjectAttributes.RootDirectory], r15
0x18000b29c  movups  xmmword ptr [rbp+20h+IoStatusBlock], xmm0
0x18000b2a0  mov     [rsp+120h+ShareAccess], 1; ShareAccess
0x18000b2a8  movdqu  xmmword ptr [rsp+120h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b2ae  call    cs:__imp_NtOpenFile
0x18000b2b5  nop     dword ptr [rax+rax+00h]
0x18000b2ba  mov     edi, eax
0x18000b2bc  test    eax, eax
0x18000b2be  jns     loc_18000B3A7
0x18000b2c4  mov     rcx, gs:60h
0x18000b2cd  xor     edx, edx; Flags
0x18000b2cf  mov     r8, [rsp+120h+P]; P
0x18000b2d4  mov     rcx, [rcx+30h]; HeapHandle
0x18000b2d8  call    cs:__imp_RtlFreeHeap
0x18000b2df  nop     dword ptr [rax+rax+00h]
0x18000b2e4  mov     [rsp+120h+P], r15
0x18000b2e9  test    edi, edi
0x18000b2eb  js      loc_18000B384
0x18000b2f1  xorps   xmm0, xmm0
0x18000b2f4  lea     rdx, [rbp+20h+IoStatusBlock]
0x18000b2f8  lea     rcx, [rbp+20h+var_80]
0x18000b2fc  movdqu  xmmword ptr [rbp+20h+IoStatusBlock], xmm0
0x18000b301  call    CdfInitializeContext
0x18000b306  mov     ebx, eax
0x18000b308  test    eax, eax
0x18000b30a  jns     loc_18000B3D2
0x18000b310  mov     rdi, [rsp+120h+arg_18]
0x18000b318  mov     rsi, [rsp+120h+arg_10]
0x18000b320  mov     r14, [rsp+120h+var_20]
0x18000b328  cmp     [rsp+120h+var_D0], r15
0x18000b32d  jz      short loc_18000B340
0x18000b32f  lea     rcx, [rsp+120h+P+8]; UnicodeString
0x18000b334  call    cs:__imp_RtlFreeUnicodeString
0x18000b33b  nop     dword ptr [rax+rax+00h]
0x18000b340  cmp     [rsp+120h+P], r15
0x18000b345  jnz     loc_18000B469
0x18000b34b  mov     rcx, [rbp+20h+FileHandle]; hObject
0x18000b34f  mov     [rbp+20h+var_80], r12
0x18000b353  mov     r12, [rsp+108h]
0x18000b35b  test    rcx, rcx
0x18000b35e  jnz     short loc_18000B395
0x18000b360  lea     rcx, [rbp+20h+var_70]
0x18000b364  call    RtlFileMapFree
0x18000b369  mov     eax, ebx
0x18000b36b  mov     rcx, [rbp+20h+var_30]
0x18000b36f  xor     rcx, rsp; StackCookie
0x18000b372  call    __security_check_cookie
0x18000b377  add     rsp, 110h
0x18000b37e  pop     r15
0x18000b380  pop     rbx
0x18000b381  pop     rbp
0x18000b382  retn
0x18000b384  cmp     edi, 0C0000034h
0x18000b38a  mov     ebx, r15d
0x18000b38d  cmovnz  ebx, edi
0x18000b390  jmp     loc_18000B310
0x18000b395  mov     [rbp+20h+FileHandle], r15
0x18000b399  call    cs:__imp_CloseHandle
0x18000b3a0  nop     dword ptr [rax+rax+00h]
0x18000b3a5  jmp     short loc_18000B360
0x18000b3a7  mov     rax, [rbp+20h+FileHandle]
0x18000b3ab  lea     rcx, [rbp+20h+var_70]
0x18000b3af  xorps   xmm0, xmm0
0x18000b3b2  movups  [rbp+20h+var_70], xmm0
0x18000b3b6  mov     qword ptr [rbp+20h+var_70], rax
0x18000b3ba  movups  [rbp+20h+var_50], xmm0
0x18000b3be  mov     byte ptr [rbp+20h+var_50+8], r15b
0x18000b3c2  movups  [rbp+20h+var_60], xmm0
0x18000b3c6  call    RtlFileMapMapView
0x18000b3cb  mov     edi, eax
0x18000b3cd  jmp     loc_18000B2C4
0x18000b3d2  mov     rdx, rsi; SourceString
0x18000b3d5  lea     rcx, [rbp+20h+DestinationString]; DestinationString
0x18000b3d9  call    cs:__imp_RtlInitUnicodeString
0x18000b3e0  nop     dword ptr [rax+rax+00h]
0x18000b3e5  mov     rdx, [rbp+20h+IoStatusBlock.Information]
0x18000b3e9  mov     dword ptr [rsp+120h+SourceString], r15d
0x18000b3ee  test    rdx, rdx
0x18000b3f1  jnz     short loc_18000B440
0x18000b3f3  lea     rcx, [rbp+20h+IoStatusBlock]; struct _LUACDF_CONTEXT *
0x18000b3f7  call    ?LuaCdfpFetchFileTable@@YAJPEAU_LUACDF_CONTEXT@@@Z; LuaCdfpFetchFileTable(_LUACDF_CONTEXT *)
0x18000b3fc  test    eax, eax
0x18000b3fe  jns     short loc_18000B430
0x18000b400  cmp     eax, 0C0000034h
0x18000b405  mov     ebx, r15d
0x18000b408  cmovnz  ebx, eax
0x18000b40b  lea     rcx, [rbp+20h+IoStatusBlock]
0x18000b40f  call    LuaCdfFreeContext
0x18000b414  jmp     loc_18000B310
0x18000b419  test    eax, eax
0x18000b41b  js      short loc_18000B400
0x18000b41d  mov     ebx, eax
0x18000b41f  mov     dword ptr [r14], 1
0x18000b426  jmp     short loc_18000B40B
0x18000b428  mov     ebx, r15d
0x18000b42b  jmp     loc_18000B318
0x18000b430  mov     rdx, [rbp+20h+IoStatusBlock.Information]
0x18000b434  test    rdx, rdx
0x18000b437  jnz     short loc_18000B440
0x18000b439  mov     ecx, 0C00000E5h
0x18000b43e  jmp     short loc_18000B462
0x18000b440  mov     rcx, qword ptr [rbp+20h+IoStatusBlock]
0x18000b444  lea     r9, [rsp+120h+SourceString]
0x18000b449  lea     r8, [rbp+20h+DestinationString]
0x18000b44d  call    CdfSearchStringTable
0x18000b452  test    eax, eax
0x18000b454  js      short loc_18000B400
0x18000b456  cmp     dword ptr [rsp+120h+SourceString], 0FFFFFFFFh
0x18000b45b  jnz     short loc_18000B419
0x18000b45d  mov     ecx, 0C0000034h; int
0x18000b462  call    ?RtlXmlReportErrorFunction@@YAJJKKPEAX@Z; RtlXmlReportErrorFunction(long,ulong,ulong,void *)
0x18000b467  jmp     short loc_18000B419
0x18000b469  lea     rcx, [rsp+120h+SourceString+8]; UnicodeString
0x18000b46e  call    cs:__imp_RtlFreeUnicodeString
0x18000b475  nop     dword ptr [rax+rax+00h]
0x18000b47a  jmp     loc_18000B34B
```
