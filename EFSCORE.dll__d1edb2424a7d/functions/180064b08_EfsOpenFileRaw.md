# EfsOpenFileRaw

- ea: `0x180064b08`
- end: `0x1800650b6`
- name: `EfsOpenFileRaw`
- size: `1454`
- prototype: `__int64 __fastcall(unsigned __int16 *, PCWSTR DosPathName, int, unsigned int, struct IMPORT_CONTEXT **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010900`

## callees

- `0x1800102f0`
- `0x180010bf0`
- `0x18004de90`
- `0x18004f104`
- `0x180063698`
- `0x180063d54`
- `0x180063e78`
- `0x1800640d4`
- `0x180064364`
- `0x180064b08`
- `0x180067390`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064bac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064bac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064c1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064e2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064c1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064e2d`
- `ntdll!RtlFreeHeap` at `0x180064c3d`
- `ntdll!RtlFreeHeap` at `0x180064c5c`
- `ntdll!RtlFreeHeap` at `0x180064e15`
- `ntdll!RtlFreeHeap` at `0x180064f30`
- `ntdll!RtlFreeHeap` at `0x180064c3d`
- `ntdll!RtlFreeHeap` at `0x180064c5c`
- `ntdll!RtlFreeHeap` at `0x180064e15`
- `ntdll!RtlFreeHeap` at `0x180064f30`
- `ntdll!NtCreateFile` at `0x180064df9`
- `ntdll!NtCreateFile` at `0x180064e6b`
- `ntdll!NtCreateFile` at `0x180064df9`
- `ntdll!NtCreateFile` at `0x180064e6b`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180064b9e`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180064b9e`
- `ntdll!RtlInitUnicodeString` at `0x180064b7e`
- `ntdll!RtlInitUnicodeString` at `0x180064b8a`
- `ntdll!RtlInitUnicodeString` at `0x180064b7e`
- `ntdll!RtlInitUnicodeString` at `0x180064b8a`
- `ntdll!RtlNtStatusToDosError` at `0x180064e9d`
- `ntdll!RtlNtStatusToDosError` at `0x180064ed1`
- `ntdll!RtlNtStatusToDosError` at `0x180064e9d`
- `ntdll!RtlNtStatusToDosError` at `0x180064ed1`

## pseudocode

```c
__int64 __fastcall EfsOpenFileRaw(
        unsigned __int16 *a1,
        PCWSTR DosPathName,
        int a3,
        unsigned int a4,
        struct IMPORT_CONTEXT **a5)
{
  struct IMPORT_CONTEXT *v7; // r12
  struct EXPORT_CONTEXT *v8; // r15
  char v9; // si
  DWORD LastError; // eax
  ULONG NetFileName; // ebx
  int v13; // eax
  HANDLE v14; // rcx
  ULONG CreateDisposition; // ebx
  int v17; // r13d
  int v18; // ecx
  ACCESS_MASK v19; // r14d
  ULONG CreateOptions; // edi
  ULONG FileAttributes; // esi
  unsigned int v22; // eax
  int v23; // r13d
  NTSTATUS v24; // eax
  NTSTATUS v25; // ebx
  ULONG v26; // eax
  int v27; // eax
  ULONG v28; // eax
  unsigned int v29; // edi
  struct IMPORT_CONTEXT *v30; // rax
  struct EXPORT_CONTEXT *v31; // rax
  unsigned int v32; // r8d
  HANDLE hObject; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v34; // [rsp+70h] [rbp-98h]
  int v35; // [rsp+74h] [rbp-94h] BYREF
  int DestinationString; // [rsp+78h] [rbp-90h]
  struct _UNICODE_STRING DestinationString_8; // [rsp+80h] [rbp-88h] BYREF
  struct _UNICODE_STRING v38; // [rsp+90h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES v41; // [rsp+E0h] [rbp-28h] BYREF

  hObject = 0;
  v35 = 0;
  v7 = 0;
  memset(&v41, 0, sizeof(v41));
  v8 = 0;
  v9 = a4;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString_8 = 0;
  v38 = 0;
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString_8, 0);
  RtlInitUnicodeString(&v38, 0);
  if ( !RtlDosPathNameToNtPathName_U(DosPathName, &DestinationString_8, 0, 0) )
  {
    LastError = GetLastError();
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 11, 216);
    NetFileName = 3;
    goto LABEL_3;
  }
  if ( a3 )
  {
    NetFileName = EfspGetNetFileName(a1, &v38);
    if ( NetFileName )
      goto LABEL_3;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &v38;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
  }
  v41.RootDirectory = 0;
  v41.ObjectName = &DestinationString_8;
  CreateDisposition = 1;
  v41.Length = 48;
  v41.Attributes = 64;
  v34 = 1;
  v17 = v9 & 2;
  DestinationString = v9 & 1;
  *(_OWORD *)&v41.SecurityDescriptor = 0;
  if ( (v9 & 1) != 0 )
  {
    v18 = 18;
    if ( (v9 & 2) != 0 )
    {
      CreateDisposition = 3;
      v19 = 1048963;
      v34 = 3;
      CreateOptions = 32801;
      FileAttributes = 148;
    }
    else
    {
      CreateDisposition = 5;
      v34 = 5;
      FileAttributes = (v9 & 4 | 0x108u) >> 1;
      v19 = 1048960;
      CreateOptions = 2129952;
    }
  }
  else
  {
    FileAttributes = 128;
    v18 = 17;
    if ( v17 )
    {
      CreateOptions = 33;
      v19 = 1048705;
    }
    else
    {
      CreateOptions = 2097184;
      v19 = 1048704;
    }
  }
  v22 = EfspEnablePrivilege(v18);
  if ( v22 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v22, 11, 57);
    v19 |= DestinationString + 1;
  }
  else
  {
    CreateOptions |= 0x4000u;
    if ( !v17 )
      v19 |= 0x10000u;
  }
  if ( a3 )
  {
    v23 = NtCreateFile(
            &hObject,
            v19,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            FileAttributes,
            0,
            CreateDisposition,
            CreateOptions,
            0,
            0);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v38.Buffer);
    v38.Buffer = 0;
    if ( v23 < 0 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v23, 11, 118);
      NetFileName = RtlNtStatusToDosError(v23);
      goto LABEL_43;
    }
    CloseHandle(hObject);
    hObject = 0;
  }
  v24 = NtCreateFile(&hObject, v19, &v41, &IoStatusBlock, 0, FileAttributes, 0, CreateDisposition, CreateOptions, 0, 0);
  v25 = v24;
  if ( v24 < 0 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v24, 11, 137);
    NetFileName = RtlNtStatusToDosError(v25);
    goto LABEL_43;
  }
  v26 = EfsEnsureLocalHandle(hObject);
  NetFileName = v26;
  if ( v26 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v26, 11, 149);
    v8 = 0;
    goto LABEL_3;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString_8.Buffer);
  DestinationString_8.Buffer = 0;
  v27 = OefsAcquireExclusiveOperation(hObject, 0, 0, 2, &v35, 0, 0);
  NetFileName = v27;
  if ( v27 < 0 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v27, 11, 172);
    v28 = NetFileName;
    NetFileName = (unsigned __int16)NetFileName;
    if ( (v28 & 0x1FFF0000) != 0x70000 )
      NetFileName = 1359;
LABEL_43:
    v8 = 0;
    if ( !NetFileName )
    {
LABEL_6:
      v14 = hObject;
      goto LABEL_7;
    }
LABEL_3:
    if ( !hObject )
      goto LABEL_9;
    v13 = OefsReleaseExclusiveOperation(hObject, 0, 0);
    if ( v13 < 0 )
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v13, 11, 253);
    goto LABEL_6;
  }
  if ( !v35 )
  {
    NetFileName = 32;
    goto LABEL_3;
  }
  v29 = CreateOptions & 0xFFFFFFFE;
  if ( DestinationString )
  {
    v30 = (struct IMPORT_CONTEXT *)wil::details::heap_allocator::allocate(0x20u);
    v7 = v30;
    if ( v30 )
    {
      NetFileName = EfspPrepareImportContext(hObject, a4, FileAttributes & 0xFFFFFFEF, v34, v29, v19, v30);
      if ( !NetFileName )
      {
        hObject = 0;
        *a5 = v7;
        v7 = 0;
        goto LABEL_9;
      }
      goto LABEL_3;
    }
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, 32, 11, 198);
    goto LABEL_50;
  }
  v31 = (struct EXPORT_CONTEXT *)wil::details::heap_allocator::allocate(0x30u);
  v8 = v31;
  if ( !v31 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, 48, 11, 227);
LABEL_50:
    NetFileName = 8;
    goto LABEL_3;
  }
  NetFileName = EfspPrepareExportContext(hObject, a4, v32, v29, v19, v31);
  if ( NetFileName )
    goto LABEL_3;
  v14 = 0;
  hObject = 0;
  *a5 = v8;
  v8 = 0;
LABEL_7:
  if ( v14 )
    CloseHandle(v14);
LABEL_9:
  if ( DestinationString_8.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString_8.Buffer);
  if ( v38.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v38.Buffer);
  if ( v7 )
    EfsFreeHeap(v7);
  if ( v8 )
    EfsFreeHeap(v8);
  return NetFileName;
}

```

## disassembly

```asm
0x180064b08  mov     rax, rsp
0x180064b0b  mov     [rax+8], rbx
0x180064b0f  mov     [rax+20h], r9d
0x180064b13  mov     [rax+18h], r8d
0x180064b17  push    rbp
0x180064b18  push    rsi
0x180064b19  push    rdi
0x180064b1a  push    r12
0x180064b1c  push    r13
0x180064b1e  push    r14
0x180064b20  push    r15
0x180064b22  lea     rbp, [rax-48h]
0x180064b26  sub     rsp, 110h
0x180064b2d  xorps   xmm0, xmm0
0x180064b30  xorps   xmm1, xmm1
0x180064b33  xor     r13d, r13d
0x180064b36  mov     rbx, rdx
0x180064b39  mov     rdi, rcx
0x180064b3c  mov     [rsp+140h+hObject], r13
0x180064b41  xor     edx, edx; SourceString
0x180064b43  mov     [rsp+140h+var_D4], r13d
0x180064b48  lea     rcx, [rsp+140h+DestinationString.Buffer]; DestinationString
0x180064b4d  mov     r12d, r13d
0x180064b50  movups  xmmword ptr [rbp+40h+var_68.Length], xmm0
0x180064b54  mov     r15d, r13d
0x180064b57  mov     esi, r9d
0x180064b5a  movups  xmmword ptr [rbp+40h+var_68.ObjectName], xmm0
0x180064b5e  mov     r14d, r8d
0x180064b61  movups  xmmword ptr [rbp+40h+var_68.SecurityDescriptor], xmm0
0x180064b65  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm1
0x180064b69  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm1
0x180064b6d  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm1
0x180064b71  movups  xmmword ptr [rsp+140h+DestinationString.Buffer], xmm0
0x180064b76  movups  xmmword ptr [rbp+40h+var_B8.Length], xmm1
0x180064b7a  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x180064b7e  call    cs:__imp_RtlInitUnicodeString
0x180064b84  xor     edx, edx; SourceString
0x180064b86  lea     rcx, [rbp+40h+var_B8]; DestinationString
0x180064b8a  call    cs:__imp_RtlInitUnicodeString
0x180064b90  xor     r9d, r9d; DirectoryInfo
0x180064b93  lea     rdx, [rsp+140h+DestinationString.Buffer]; NtPathName
0x180064b98  xor     r8d, r8d; NtFileNamePart
0x180064b9b  mov     rcx, rbx; DosPathName
0x180064b9e  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180064ba4  test    al, al
0x180064ba6  jnz     loc_180064C99
0x180064bac  call    cs:__imp_GetLastError
0x180064bb2  mov     rcx, cs:g_hPublisher
0x180064bb9  lea     r9d, [r13+0Bh]
0x180064bbd  mov     r8d, eax
0x180064bc0  mov     dword ptr [rsp+140h+AllocationSize], 0D8h
0x180064bc8  lea     rdx, EFS_API_ERROR
0x180064bcf  call    fnEfsLogTrace1
0x180064bd4  lea     ebx, [r13+3]
0x180064bd8  mov     rcx, [rsp+140h+hObject]; void *
0x180064bdd  test    rcx, rcx
0x180064be0  jz      short loc_180064C24
0x180064be2  xor     r8d, r8d; __int64
0x180064be5  xor     edx, edx; unsigned int
0x180064be7  call    ?OefsReleaseExclusiveOperation@@YAJPEAXK_J@Z; OefsReleaseExclusiveOperation(void *,ulong,__int64)
0x180064bec  test    eax, eax
0x180064bee  jns     short loc_180064C14
0x180064bf0  mov     rcx, cs:g_hPublisher
0x180064bf7  lea     rdx, EFS_API_ERROR
0x180064bfe  mov     r9d, 0Bh
0x180064c04  mov     dword ptr [rsp+140h+AllocationSize], 1FDh
0x180064c0c  mov     r8d, eax
0x180064c0f  call    fnEfsLogTrace1
0x180064c14  mov     rcx, [rsp+140h+hObject]; hObject
0x180064c19  test    rcx, rcx
0x180064c1c  jz      short loc_180064C24
0x180064c1e  call    cs:__imp_CloseHandle
0x180064c24  cmp     [rbp+40h+P], r13
0x180064c28  jz      short loc_180064C43
0x180064c2a  mov     rcx, gs:60h
0x180064c33  xor     edx, edx; Flags
0x180064c35  mov     r8, [rbp+40h+P]; P
0x180064c39  mov     rcx, [rcx+30h]; HeapHandle
0x180064c3d  call    cs:__imp_RtlFreeHeap
0x180064c43  cmp     [rbp+40h+var_B8.Buffer], r13
0x180064c47  jz      short loc_180064C62
0x180064c49  mov     rcx, gs:60h
0x180064c52  xor     edx, edx; Flags
0x180064c54  mov     r8, [rbp+40h+var_B8.Buffer]; P
0x180064c58  mov     rcx, [rcx+30h]; HeapHandle
0x180064c5c  call    cs:__imp_RtlFreeHeap
0x180064c62  test    r12, r12
0x180064c65  jz      short loc_180064C6F
0x180064c67  mov     rcx, r12; lpMem
0x180064c6a  call    EfsFreeHeap
0x180064c6f  test    r15, r15
0x180064c72  jz      short loc_180064C7C
0x180064c74  mov     rcx, r15; lpMem
0x180064c77  call    EfsFreeHeap
0x180064c7c  mov     eax, ebx
0x180064c7e  mov     rbx, [rsp+140h+arg_0]
0x180064c86  add     rsp, 110h
0x180064c8d  pop     r15
0x180064c8f  pop     r14
0x180064c91  pop     r13
0x180064c93  pop     r12
0x180064c95  pop     rdi
0x180064c96  pop     rsi
0x180064c97  pop     rbp
0x180064c98  retn
0x180064c99  test    r14d, r14d
0x180064c9c  jz      short loc_180064CD6
0x180064c9e  lea     rdx, [rbp+40h+var_B8]; struct _UNICODE_STRING *
0x180064ca2  mov     rcx, rdi; unsigned __int16 *
0x180064ca5  call    ?EfspGetNetFileName@@YAKPEBGPEAU_UNICODE_STRING@@@Z; EfspGetNetFileName(ushort const *,_UNICODE_STRING *)
0x180064caa  mov     ebx, eax
0x180064cac  test    eax, eax
0x180064cae  jnz     loc_180064BD8
0x180064cb4  lea     rax, [rbp+40h+var_B8]
0x180064cb8  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x180064cbf  xorps   xmm0, xmm0
0x180064cc2  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x180064cc6  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x180064ccb  mov     [rbp+40h+ObjectAttributes.RootDirectory], r13
0x180064ccf  mov     [rbp+40h+ObjectAttributes.Attributes], 40h ; '@'
0x180064cd6  lea     rax, [rsp+140h+DestinationString.Buffer]
0x180064cdb  mov     [rbp+40h+var_68.RootDirectory], r13
0x180064cdf  mov     [rbp+40h+var_68.ObjectName], rax
0x180064ce3  mov     ebx, 1
0x180064ce8  mov     eax, esi
0x180064cea  mov     [rbp+40h+var_68.Length], 30h ; '0'
0x180064cf1  and     eax, ebx
0x180064cf3  mov     [rbp+40h+var_68.Attributes], 40h ; '@'
0x180064cfa  mov     r13d, esi
0x180064cfd  mov     [rsp+140h+var_D8], ebx
0x180064d01  and     r13d, 2
0x180064d05  mov     dword ptr [rsp+140h+DestinationString.Length], eax
0x180064d09  xorps   xmm0, xmm0
0x180064d0c  movdqu  xmmword ptr [rbp+40h+var_68.SecurityDescriptor], xmm0
0x180064d11  test    eax, eax
0x180064d13  jz      short loc_180064D57
0x180064d15  lea     ecx, [rbx+11h]
0x180064d18  test    r13d, r13d
0x180064d1b  jz      short loc_180064D36
0x180064d1d  lea     ebx, [rcx-0Fh]
0x180064d20  mov     r14d, 100183h
0x180064d26  mov     [rsp+140h+var_D8], ebx
0x180064d2a  mov     edi, 8021h
0x180064d2f  mov     esi, 94h
0x180064d34  jmp     short loc_180064D7A
0x180064d36  and     esi, 4
0x180064d39  mov     ebx, 5
0x180064d3e  or      esi, 108h
0x180064d44  mov     [rsp+140h+var_D8], ebx
0x180064d48  shr     esi, 1
0x180064d4a  mov     r14d, 100180h
0x180064d50  mov     edi, 208020h
0x180064d55  jmp     short loc_180064D7A
0x180064d57  mov     esi, 80h
0x180064d5c  lea     ecx, [rsi-6Fh]; int
0x180064d5f  test    r13d, r13d
0x180064d62  jz      short loc_180064D6F
0x180064d64  lea     edi, [rsi-5Fh]
0x180064d67  mov     r14d, 100081h
0x180064d6d  jmp     short loc_180064D7A
0x180064d6f  mov     edi, 200020h
0x180064d74  mov     r14d, 100080h
0x180064d7a  call    ?EfspEnablePrivilege@@YAKJ@Z; EfspEnablePrivilege(long)
0x180064d7f  test    eax, eax
0x180064d81  jz      short loc_180064DB2
0x180064d83  mov     rcx, cs:g_hPublisher
0x180064d8a  lea     rdx, EFS_API_ERROR
0x180064d91  mov     r9d, 0Bh
0x180064d97  mov     dword ptr [rsp+140h+AllocationSize], 139h
0x180064d9f  mov     r8d, eax
0x180064da2  call    fnEfsLogTrace1
0x180064da7  mov     eax, dword ptr [rsp+140h+DestinationString.Length]
0x180064dab  inc     eax
0x180064dad  or      r14d, eax
0x180064db0  jmp     short loc_180064DC0
0x180064db2  bts     edi, 0Eh
0x180064db6  test    r13d, r13d
0x180064db9  jnz     short loc_180064DC0
0x180064dbb  bts     r14d, 10h
0x180064dc0  xor     r13d, r13d
0x180064dc3  cmp     [rbp+40h+arg_10], r13d
0x180064dc7  jz      short loc_180064E3B
0x180064dc9  mov     [rsp+50h], r13d; EaLength
0x180064dce  lea     r9, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x180064dd2  mov     [rsp+140h+EaBuffer], r13; EaBuffer
0x180064dd7  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x180064ddb  mov     [rsp+140h+CreateOptions], edi; CreateOptions
0x180064ddf  lea     rcx, [rsp+140h+hObject]; FileHandle
0x180064de4  mov     [rsp+140h+CreateDisposition], ebx; CreateDisposition
0x180064de8  mov     edx, r14d; DesiredAccess
0x180064deb  mov     [rsp+140h+ShareAccess], r13d; ShareAccess
0x180064df0  mov     [rsp+140h+FileAttributes], esi; FileAttributes
0x180064df4  mov     [rsp+140h+AllocationSize], r13; AllocationSize
0x180064df9  call    cs:__imp_NtCreateFile
0x180064dff  mov     rcx, gs:60h
0x180064e08  xor     edx, edx; Flags
0x180064e0a  mov     r8, [rbp+40h+var_B8.Buffer]; P
0x180064e0e  mov     r13d, eax
0x180064e11  mov     rcx, [rcx+30h]; HeapHandle
0x180064e15  call    cs:__imp_RtlFreeHeap
0x180064e1b  mov     [rbp+40h+var_B8.Buffer], r12
0x180064e1f  test    r13d, r13d
0x180064e22  js      loc_180064EAA
0x180064e28  mov     rcx, [rsp+140h+hObject]; hObject
0x180064e2d  call    cs:__imp_CloseHandle
0x180064e33  xor     r13d, r13d
0x180064e36  mov     [rsp+140h+hObject], r13
0x180064e3b  mov     [rsp+50h], r13d; EaLength
0x180064e40  lea     r9, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x180064e44  mov     [rsp+140h+EaBuffer], r13; EaBuffer
0x180064e49  lea     r8, [rbp+40h+var_68]; ObjectAttributes
0x180064e4d  mov     [rsp+140h+CreateOptions], edi; CreateOptions
0x180064e51  lea     rcx, [rsp+140h+hObject]; FileHandle
0x180064e56  mov     [rsp+140h+CreateDisposition], ebx; CreateDisposition
0x180064e5a  mov     edx, r14d; DesiredAccess
0x180064e5d  mov     [rsp+140h+ShareAccess], r13d; ShareAccess
0x180064e62  mov     [rsp+140h+FileAttributes], esi; FileAttributes
0x180064e66  mov     [rsp+140h+AllocationSize], r13; AllocationSize
0x180064e6b  call    cs:__imp_NtCreateFile
0x180064e71  mov     ebx, eax
0x180064e73  test    eax, eax
0x180064e75  jns     short loc_180064EE1
0x180064e77  mov     rcx, cs:g_hPublisher
0x180064e7e  lea     rdx, EFS_API_ERROR
0x180064e85  mov     r9d, 0Bh
0x180064e8b  mov     dword ptr [rsp+140h+AllocationSize], 189h
0x180064e93  mov     r8d, eax
0x180064e96  call    fnEfsLogTrace1
0x180064e9b  mov     ecx, ebx; Status
0x180064e9d  call    cs:__imp_RtlNtStatusToDosError
0x180064ea3  mov     ebx, eax
0x180064ea5  jmp     loc_180064FA3
0x180064eaa  mov     rcx, cs:g_hPublisher
0x180064eb1  lea     rdx, EFS_API_ERROR
0x180064eb8  mov     r9d, 0Bh
0x180064ebe  mov     dword ptr [rsp+140h+AllocationSize], 176h
0x180064ec6  mov     r8d, r13d
0x180064ec9  call    fnEfsLogTrace1
0x180064ece  mov     ecx, r13d; Status
0x180064ed1  call    cs:__imp_RtlNtStatusToDosError
0x180064ed7  mov     ebx, eax
0x180064ed9  xor     r13d, r13d
0x180064edc  jmp     loc_180064FA3
0x180064ee1  mov     rcx, [rsp+140h+hObject]
0x180064ee6  call    EfsEnsureLocalHandle
0x180064eeb  mov     ebx, eax
0x180064eed  test    eax, eax
0x180064eef  jz      short loc_180064F1D
0x180064ef1  mov     rcx, cs:g_hPublisher
0x180064ef8  lea     rdx, EFS_API_ERROR
0x180064eff  mov     r9d, 0Bh
0x180064f05  mov     dword ptr [rsp+140h+AllocationSize], 195h
0x180064f0d  mov     r8d, eax
0x180064f10  call    fnEfsLogTrace1
0x180064f15  mov     r15, r13
0x180064f18  jmp     loc_180064BD8
0x180064f1d  mov     rcx, gs:60h
0x180064f26  xor     edx, edx; Flags
0x180064f28  mov     r8, [rbp+40h+P]; P
0x180064f2c  mov     rcx, [rcx+30h]; HeapHandle
0x180064f30  call    cs:__imp_RtlFreeHeap
0x180064f36  mov     rcx, [rsp+140h+hObject]
0x180064f3b  lea     rax, [rsp+140h+var_D4]
0x180064f40  mov     qword ptr [rsp+140h+ShareAccess], r13
0x180064f45  mov     r9d, 2
0x180064f4b  mov     qword ptr [rsp+140h+FileAttributes], r13
0x180064f50  xor     r8d, r8d
0x180064f53  xor     edx, edx
0x180064f55  mov     [rsp+140h+AllocationSize], rax
0x180064f5a  mov     [rbp+40h+P], r13
0x180064f5e  call    ?OefsAcquireExclusiveOperation@@YAJPEAXK_JW4_OEFS_EXCLUSIVE_OPERATION@@PEAHPEAKPEA_J@Z; OefsAcquireExclusiveOperation(void *,ulong,__int64,_OEFS_EXCLUSIVE_OPERATION,int *,ulong *,__int64 *)
0x180064f63  mov     ebx, eax
0x180064f65  test    eax, eax
0x180064f67  jns     short loc_180064FB3
0x180064f69  mov     rcx, cs:g_hPublisher
0x180064f70  lea     rdx, EFS_API_ERROR
0x180064f77  mov     r9d, 0Bh
0x180064f7d  mov     dword ptr [rsp+140h+AllocationSize], 1ACh
0x180064f85  mov     r8d, eax
0x180064f88  call    fnEfsLogTrace1
0x180064f8d  mov     eax, ebx
0x180064f8f  movzx   ebx, bx
0x180064f92  and     eax, 1FFF0000h
0x180064f97  cmp     eax, 70000h
0x180064f9c  jz      short loc_180064FA3
0x180064f9e  mov     ebx, 54Fh
0x180064fa3  mov     r15, r13
0x180064fa6  test    ebx, ebx
0x180064fa8  jz      loc_180064C14
0x180064fae  jmp     loc_180064BD8
0x180064fb3  cmp     [rsp+140h+var_D4], r13d
0x180064fb8  jnz     short loc_180064FC4
0x180064fba  mov     ebx, 20h ; ' '
0x180064fbf  jmp     loc_180064BD8
0x180064fc4  and     edi, 0FFFFFFFEh
0x180064fc7  cmp     dword ptr [rsp+140h+DestinationString.Length], r13d
0x180064fcc  jz      loc_180065058
0x180064fd2  mov     ebx, 20h ; ' '
0x180064fd7  mov     ecx, ebx; unsigned __int64
0x180064fd9  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
  ... truncated ...
```
