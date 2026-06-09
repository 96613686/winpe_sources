# FltpGetNameSupportVolumeInfo

- ea: `0x180022bac`
- end: `0x180022e04`
- name: `FltpGetNameSupportVolumeInfo`
- size: `600`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x18000afe0`

## callees

- `0x180009f20`
- `0x180022a84`
- `0x180022bac`
- `0x180024800`
- `0x180024c40`
- `0x18004dcc0`
- `0x18005c5a0`
- `0x180065a70`
- `0x180067b00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180022d52`
- `ntoskrnl!ExAllocatePool2` at `0x180022d52`
- `ntoskrnl!ObfDereferenceObject` at `0x180022dc3`
- `ntoskrnl!ObfDereferenceObject` at `0x180022dc3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180022d87`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180022d87`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180022ccd`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180022ccd`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180022cf3`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180022cf3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180022c00`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180022c00`
- `ntoskrnl!IoGetBaseFileSystemDeviceObject` at `0x180022c4e`
- `ntoskrnl!IoGetBaseFileSystemDeviceObject` at `0x180022c4e`

## pseudocode

```c
__int64 __fastcall FltpGetNameSupportVolumeInfo(PFILE_OBJECT FileObject, PVOID *a2)
{
  _QWORD *v4; // rax
  unsigned int BaseDeviceObjectName; // edi
  PDEVICE_OBJECT BaseFileSystemDeviceObject; // r14
  unsigned int i; // esi
  __int64 v8; // rdi
  unsigned __int16 Length; // si
  __int64 Pool2; // rax
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+20h] [rbp-E0h] BYREF
  UNICODE_STRING String1[18]; // [rsp+30h] [rbp-D0h] BYREF

  DiskDeviceObject = 0;
  memset(String1, 0, sizeof(String1));
  v4 = ExAllocateFromPagedLookasideList(&stru_180040140);
  if ( v4 )
  {
    *(_OWORD *)v4 = 0;
    v4[2] = 0;
    BaseDeviceObjectName = 0;
    *a2 = v4;
  }
  else
  {
    BaseDeviceObjectName = -1073741670;
  }
  if ( (int)FltpDbgStatus(BaseDeviceObjectName, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 2514, 0) >= 0 )
  {
    BaseFileSystemDeviceObject = IoGetBaseFileSystemDeviceObject(FileObject);
    if ( BaseFileSystemDeviceObject->DeviceType == 20 )
      *(_DWORD *)*a2 |= 1u;
    *((_DWORD *)*a2 + 1) = 0;
    FltpInitNameControl(String1);
    BaseDeviceObjectName = FltpGetBaseDeviceObjectName(BaseFileSystemDeviceObject, String1);
    if ( (int)FltpDbgStatus(BaseDeviceObjectName, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 2545, 0) >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v8 = 4LL * i;
        if ( LODWORD(FsTypes[v8]) == -1 )
          break;
        if ( RtlEqualUnicodeString(String1, (PCUNICODE_STRING)&qword_18003E060[v8], 1u) )
        {
          *((_DWORD *)*a2 + 1) = FsTypes[v8];
          break;
        }
      }
      BaseDeviceObjectName = IoGetDiskDeviceObject(BaseFileSystemDeviceObject, &DiskDeviceObject);
      if ( (int)FltpDbgStatus(BaseDeviceObjectName, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 2567, 0) >= 0 )
      {
        BaseDeviceObjectName = FltpGetObjectName(DiskDeviceObject);
        if ( (int)FltpDbgStatus(BaseDeviceObjectName, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 2574, 0) >= 0 )
        {
          Length = String1[0].Length;
          Pool2 = ExAllocatePool2(256, String1[0].Length, 1937067334);
          if ( Pool2 )
          {
            *((_QWORD *)*a2 + 2) = Pool2;
            *((_WORD *)*a2 + 5) = Length;
            RtlCopyUnicodeString((PUNICODE_STRING)((char *)*a2 + 8), String1);
          }
          else
          {
            BaseDeviceObjectName = -1073741670;
          }
        }
      }
    }
    if ( (int)FltpDbgStatus(BaseDeviceObjectName, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 2597, 0) < 0 )
    {
      FltpFreeNameSupportVolumeInfo(*a2);
      *a2 = 0;
    }
    if ( DiskDeviceObject )
      ObfDereferenceObject(DiskDeviceObject);
    FltpCleanupNameControl(String1);
  }
  return BaseDeviceObjectName;
}

```

## disassembly

```asm
0x180022bac  mov     [rsp-8+arg_10], rbx
0x180022bb1  mov     [rsp-8+arg_18], rsi
0x180022bb6  push    rbp
0x180022bb7  push    rdi
0x180022bb8  push    r12
0x180022bba  push    r13
0x180022bbc  push    r14
0x180022bbe  lea     rbp, [rsp-60h]
0x180022bc3  sub     rsp, 160h
0x180022bca  mov     rax, cs:__security_cookie
0x180022bd1  xor     rax, rsp
0x180022bd4  mov     [rbp+80h+var_30], rax
0x180022bd8  mov     rbx, rdx
0x180022bdb  mov     [rsp+180h+DiskDeviceObject], 0
0x180022be4  mov     rsi, rcx
0x180022be7  xor     edx, edx; Val
0x180022be9  lea     rcx, [rsp+180h+String1]; void *
0x180022bee  mov     r8d, 120h; Size
0x180022bf4  call    memset
0x180022bf9  lea     rcx, stru_180040140; Lookaside
0x180022c00  call    cs:__imp_ExAllocateFromPagedLookasideList
0x180022c07  nop     dword ptr [rax+rax+00h]
0x180022c0c  test    rax, rax
0x180022c0f  jnz     short loc_180022C18
0x180022c11  mov     edi, 0C000009Ah
0x180022c16  jmp     short loc_180022C29
0x180022c18  xor     ecx, ecx
0x180022c1a  xorps   xmm0, xmm0
0x180022c1d  movups  xmmword ptr [rax], xmm0
0x180022c20  mov     [rax+10h], rcx
0x180022c24  xor     edi, edi
0x180022c26  mov     [rbx], rax
0x180022c29  lea     r13, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x180022c30  mov     r8d, 9D2h
0x180022c36  mov     rdx, r13
0x180022c39  xor     r9d, r9d
0x180022c3c  mov     ecx, edi
0x180022c3e  call    FltpDbgStatus
0x180022c43  test    eax, eax
0x180022c45  js      loc_180022DD9
0x180022c4b  mov     rcx, rsi; FileObject
0x180022c4e  call    cs:__imp_IoGetBaseFileSystemDeviceObject
0x180022c55  nop     dword ptr [rax+rax+00h]
0x180022c5a  mov     r14, rax
0x180022c5d  cmp     dword ptr [rax+48h], 14h
0x180022c61  jnz     short loc_180022C69
0x180022c63  mov     rcx, [rbx]
0x180022c66  or      dword ptr [rcx], 1
0x180022c69  mov     rcx, [rbx]
0x180022c6c  mov     dword ptr [rcx+4], 0
0x180022c73  lea     rcx, [rsp+180h+String1]
0x180022c78  call    FltpInitNameControl
0x180022c7d  lea     rdx, [rsp+180h+String1]
0x180022c82  mov     rcx, r14
0x180022c85  call    FltpGetBaseDeviceObjectName
0x180022c8a  mov     r8d, 9F1h
0x180022c90  xor     r9d, r9d
0x180022c93  mov     rdx, r13
0x180022c96  mov     ecx, eax
0x180022c98  mov     edi, eax
0x180022c9a  call    FltpDbgStatus
0x180022c9f  test    eax, eax
0x180022ca1  js      loc_180022D93
0x180022ca7  xor     esi, esi
0x180022ca9  lea     r12, FsTypes
0x180022cb0  mov     edi, esi
0x180022cb2  shl     rdi, 5
0x180022cb6  cmp     dword ptr [rdi+r12], 0FFFFFFFFh
0x180022cbb  jz      short loc_180022CEB
0x180022cbd  lea     rdx, [r12+10h]
0x180022cc2  mov     r8b, 1; CaseInSensitive
0x180022cc5  add     rdx, rdi; String2
0x180022cc8  lea     rcx, [rsp+180h+String1]; String1
0x180022ccd  call    cs:__imp_RtlEqualUnicodeString
0x180022cd4  nop     dword ptr [rax+rax+00h]
0x180022cd9  test    al, al
0x180022cdb  jnz     short loc_180022CE1
0x180022cdd  inc     esi
0x180022cdf  jmp     short loc_180022CB0
0x180022ce1  mov     rcx, [rbx]
0x180022ce4  mov     eax, [rdi+r12]
0x180022ce8  mov     [rcx+4], eax
0x180022ceb  lea     rdx, [rsp+180h+DiskDeviceObject]; DiskDeviceObject
0x180022cf0  mov     rcx, r14; FileSystemDeviceObject
0x180022cf3  call    cs:__imp_IoGetDiskDeviceObject
0x180022cfa  nop     dword ptr [rax+rax+00h]
0x180022cff  mov     r8d, 0A07h
0x180022d05  xor     r9d, r9d
0x180022d08  mov     ecx, eax
0x180022d0a  mov     rdx, r13
0x180022d0d  mov     edi, eax
0x180022d0f  call    FltpDbgStatus
0x180022d14  test    eax, eax
0x180022d16  js      short loc_180022D93
0x180022d18  mov     rcx, [rsp+180h+DiskDeviceObject]; Object
0x180022d1d  lea     rdx, [rsp+180h+String1]
0x180022d22  call    FltpGetObjectName
0x180022d27  mov     r8d, 0A0Eh
0x180022d2d  xor     r9d, r9d
0x180022d30  mov     rdx, r13
0x180022d33  mov     ecx, eax
0x180022d35  mov     edi, eax
0x180022d37  call    FltpDbgStatus
0x180022d3c  test    eax, eax
0x180022d3e  js      short loc_180022D93
0x180022d40  movzx   esi, [rsp+180h+String1.Length]
0x180022d45  mov     ecx, 100h
0x180022d4a  mov     edx, esi
0x180022d4c  mov     r8d, 73754D46h
0x180022d52  call    cs:__imp_ExAllocatePool2
0x180022d59  nop     dword ptr [rax+rax+00h]
0x180022d5e  mov     rcx, rax
0x180022d61  test    rax, rax
0x180022d64  jnz     short loc_180022D6D
0x180022d66  mov     edi, 0C000009Ah
0x180022d6b  jmp     short loc_180022D93
0x180022d6d  mov     rax, [rbx]
0x180022d70  lea     rdx, [rsp+180h+String1]; SourceString
0x180022d75  mov     [rax+10h], rcx
0x180022d79  mov     rax, [rbx]
0x180022d7c  mov     [rax+0Ah], si
0x180022d80  mov     rcx, [rbx]
0x180022d83  add     rcx, 8; DestinationString
0x180022d87  call    cs:__imp_RtlCopyUnicodeString
0x180022d8e  nop     dword ptr [rax+rax+00h]
0x180022d93  mov     r8d, 0A25h
0x180022d99  xor     r9d, r9d
0x180022d9c  mov     rdx, r13
0x180022d9f  mov     ecx, edi
0x180022da1  call    FltpDbgStatus
0x180022da6  test    eax, eax
0x180022da8  jns     short loc_180022DB9
0x180022daa  mov     rcx, [rbx]; Entry
0x180022dad  call    FltpFreeNameSupportVolumeInfo
0x180022db2  mov     qword ptr [rbx], 0
0x180022db9  mov     rcx, [rsp+180h+DiskDeviceObject]; Object
0x180022dbe  test    rcx, rcx
0x180022dc1  jz      short loc_180022DCF
0x180022dc3  call    cs:__imp_ObfDereferenceObject
0x180022dca  nop     dword ptr [rax+rax+00h]
0x180022dcf  lea     rcx, [rsp+180h+String1]
0x180022dd4  call    FltpCleanupNameControl
0x180022dd9  mov     eax, edi
0x180022ddb  mov     rcx, [rbp+80h+var_30]
0x180022ddf  xor     rcx, rsp; StackCookie
0x180022de2  call    __security_check_cookie
0x180022de7  lea     r11, [rsp+180h+var_20]
0x180022def  mov     rbx, [r11+40h]
0x180022df3  mov     rsi, [r11+48h]
0x180022df7  mov     rsp, r11
0x180022dfa  pop     r14
0x180022dfc  pop     r13
0x180022dfe  pop     r12
0x180022e00  pop     rdi
0x180022e01  pop     rbp
0x180022e02  retn
```
