# DecryptFileSrv

- ea: `0x180013c68`
- end: `0x180014414`
- name: `DecryptFileSrv`
- size: `1964`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800106b0`

## callees

- `0x180001a7c`
- `0x180001b48`
- `0x180001ba8`
- `0x180004f86`
- `0x180005045`
- `0x180013c68`
- `0x180017510`
- `0x1800184c8`
- `0x18001b4d8`
- `0x18001b61c`
- `0x18001d1ac`
- `0x18004d314`
- `0x18004d998`
- `0x18004e030`
- `0x18004e17c`
- `0x180063698`
- `0x180066828`
- `0x1800d87ac`
- `0x1800dddf0`
- `0x1800ddeb0`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001438c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001438c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013fb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013fc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013fb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013fc7`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180014382`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180014382`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180014359`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180014359`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18001422b`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18001422b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013e60`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800141b4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013e60`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800141b4`
- `ntdll!RtlFreeHeap` at `0x180013f72`
- `ntdll!RtlFreeHeap` at `0x180014282`
- `ntdll!RtlFreeHeap` at `0x180013f72`
- `ntdll!RtlFreeHeap` at `0x180014282`
- `ntdll!NtCreateFile` at `0x18001414a`
- `ntdll!NtCreateFile` at `0x18001414a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001400b`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001400b`
- `ntdll!RtlInitUnicodeString` at `0x180013d1a`
- `ntdll!RtlInitUnicodeString` at `0x180013d1a`
- `ntdll!RtlNtStatusToDosError` at `0x1800141a0`
- `ntdll!RtlNtStatusToDosError` at `0x1800141a0`
- `ntdll!RtlDllShutdownInProgress` at `0x180013ef5`
- `ntdll!RtlDllShutdownInProgress` at `0x180013ef5`

## pseudocode

```c
__int64 __fastcall DecryptFileSrv(struct _EFS_USER_INFO *a1, const void **a2, void *a3, unsigned int a4)
{
  __int64 v7; // rsi
  DWORD v8; // ebx
  unsigned __int64 v9; // rsi
  HANDLE *p_hObject; // rdi
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  _DWORD *v15; // rax
  int v16; // r8d
  DWORD FileAttributesW; // eax
  char v18; // r15
  DWORD LastError; // eax
  DWORD v20; // eax
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // r8
  DWORD v26; // r8d
  int v27; // esi
  int v28; // r14d
  int v29; // eax
  ULONG CreateOptions; // esi
  ULONG ShareAccess; // r13d
  NTSTATUS v32; // eax
  NTSTATUS v33; // r14d
  ULONG v34; // ebx
  DWORD v35; // eax
  DWORD v36; // eax
  int v37; // esi
  int v38; // eax
  DWORD v39; // ecx
  char dwFileAttributes; // bl
  DWORD v41; // eax
  __int64 v42; // [rsp+0h] [rbp-60h] BYREF
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-40h]
  int v44; // [rsp+60h] [rbp+0h] BYREF
  unsigned int v45; // [rsp+64h] [rbp+4h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp+8h] BYREF
  struct _EFS_USER_INFO *v47; // [rsp+70h] [rbp+10h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp+18h] BYREF
  __int64 v49; // [rsp+88h] [rbp+28h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+90h] [rbp+30h] BYREF
  __int64 v51; // [rsp+98h] [rbp+38h] BYREF
  DWORD v52; // [rsp+A0h] [rbp+40h] BYREF
  HANDLE v53; // [rsp+A8h] [rbp+48h]
  __int128 v54; // [rsp+B0h] [rbp+50h]
  __int128 v55; // [rsp+C0h] [rbp+60h]
  __int128 v56; // [rsp+D0h] [rbp+70h]
  __int64 *v57; // [rsp+E0h] [rbp+80h]
  unsigned __int8 v58[4]; // [rsp+E8h] [rbp+88h] BYREF
  int v59; // [rsp+ECh] [rbp+8Ch]
  int v60; // [rsp+100h] [rbp+A0h] BYREF
  __int64 v61; // [rsp+108h] [rbp+A8h]
  char v62; // [rsp+110h] [rbp+B0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+118h] [rbp+B8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+150h] [rbp+F0h] BYREF
  __int128 v65; // [rsp+160h] [rbp+100h] BYREF
  __int64 v66; // [rsp+170h] [rbp+110h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+178h] [rbp+118h] BYREF

  v49 = (__int64)a2;
  v47 = a1;
  v45 = a4;
  hObject = 0;
  v51 = 0;
  v66 = 0;
  v65 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  DestinationString = 0;
  memset_0(&v52, 0, 0x60u);
  LastWriteTime = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  LOBYTE(v44) = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v7 = *(unsigned __int16 *)a2;
  v8 = 8;
  v52 = -1;
  v9 = v7 + 2;
  v54 = 0;
  v55 = 0;
  p_hObject = 0;
  v56 = 0;
  v57 = 0;
  v58[0] = 0;
  v59 = -1;
  v53 = 0;
  if ( v9 > g_ulMaxStackAllocSize || v9 + g_ulAdditionalProbeSize + 8 < v9 || !(unsigned int)VerifyStackAvailable() )
    goto LABEL_85;
  v11 = v9 + 23;
  if ( v9 + 23 <= v9 + 8 )
    v11 = 0xFFFFFFFFFFFFFF0LL;
  v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
  v13 = alloca(v12);
  v14 = alloca(v12);
  p_hObject = (HANDLE *)&v44;
  if ( &v42 == (__int64 *)-96LL || (v44 = 1801679955, (p_hObject = &hObject) == 0) )
  {
LABEL_85:
    if ( v9 + 8 >= v9 )
    {
      v15 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_hObject = (HANDLE *)v15;
      if ( v15 )
      {
        *v15 = 1885431112;
        p_hObject = (HANDLE *)(v15 + 2);
      }
    }
  }
  if ( !p_hObject )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, *(unsigned __int16 *)a2 + 2, 4, 84);
    LODWORD(AllocationSize) = 597;
LABEL_13:
    v16 = v8;
LABEL_17:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v16, 4, (char)AllocationSize);
    goto LABEL_18;
  }
  *((_WORD *)p_hObject + ((unsigned __int64)*(unsigned __int16 *)a2 >> 1)) = 0;
  memcpy_0(p_hObject, a2[1], *(unsigned __int16 *)a2);
  FileAttributesW = GetFileAttributesW((LPCWSTR)p_hObject);
  v18 = FileAttributesW;
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 4, 95);
    v20 = GetLastError();
    v8 = v20;
    LODWORD(AllocationSize) = 608;
LABEL_16:
    v16 = v20;
    goto LABEL_17;
  }
  if ( !RtlDosPathNameToNtPathName_U((PCWSTR)p_hObject, &DestinationString, 0, 0) )
  {
    v8 = GetLastError();
    v26 = v8;
    v27 = 620;
LABEL_39:
    v20 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v26, 4, v27);
    LODWORD(AllocationSize) = v27;
    goto LABEL_16;
  }
  v8 = 0;
  v28 = v18 & 0x10;
  if ( (v18 & 0x10) == 0 && OefsCheckGlobalSupport() && a3 )
  {
    v29 = OefsDecryptFileSrv(v47, &DestinationString, (const unsigned __int16 *)p_hObject, a3, a4, v58);
    if ( v29 >= 0 )
      goto LABEL_18;
    if ( v29 != -2147024846 )
    {
      v8 = (unsigned __int16)v29;
      if ( (v29 & 0x1FFF0000) != 0x70000 )
        v8 = 6001;
      LODWORD(AllocationSize) = 649;
      v16 = v8;
      goto LABEL_17;
    }
  }
  LODWORD(v47) = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  CreateOptions = v28 != 0 ? 33 : 2097248;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ShareAccess = v28 != 0 ? 7 : 0;
  while ( 1 )
  {
    v32 = NtCreateFile(
            &hObject,
            0x100183u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0,
            ShareAccess,
            1u,
            CreateOptions,
            0,
            0);
    v33 = v32;
    if ( v32 >= 0 )
      break;
    if ( (_DWORD)v47 || v32 != -1073741638 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v32, 4, 214);
      v34 = RtlNtStatusToDosError(v33);
      if ( v33 != -1073741790 || (v35 = GetFileAttributesW((LPCWSTR)p_hObject), v18 = v35, v35 != -1) )
      {
        if ( (v18 & 1) != 0 )
        {
          v8 = 6009;
LABEL_61:
          v27 = 757;
          v26 = v8;
          goto LABEL_39;
        }
        if ( v33 == -1073741757 && (v45 & 1) != 0 )
        {
          v8 = 32;
          goto LABEL_61;
        }
      }
      v8 = EfspMapError(v34, 6001);
      goto LABEL_61;
    }
    LODWORD(v47) = 1;
    CreateOptions = CreateOptions & 0xFFDFFFBE | 1;
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(hObject, &FileInformation) )
  {
    v36 = GetLastError();
    v37 = 766;
LABEL_64:
    v16 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v36, 4, v37);
    LODWORD(AllocationSize) = v37;
    goto LABEL_17;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  DestinationString.Buffer = 0;
  if ( a3 )
  {
    v38 = OefsExclusiveOperationContext::Acquire(&v60, hObject, 1, &v44);
    v8 = v38;
    if ( v38 < 0 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v38, 4, 24);
      v39 = v8;
      v8 = (unsigned __int16)v8;
      if ( (v39 & 0x1FFF0000) != 0x70000 )
        v8 = 1359;
      LODWORD(AllocationSize) = 793;
      goto LABEL_13;
    }
    if ( !(_BYTE)v44 )
    {
      v16 = 32;
      LODWORD(AllocationSize) = 798;
      v8 = 32;
      goto LABEL_17;
    }
  }
  v8 = EfspGetFileInformation(hObject, &v51);
  if ( !v8 )
  {
    if ( !GetFileTime(hObject, 0, 0, &LastWriteTime) )
    {
      v36 = GetLastError();
      v8 = v36;
      v37 = 824;
      goto LABEL_64;
    }
    if ( !SetFileTime(hObject, 0, 0, &LastWriteTime) )
    {
      v36 = GetLastError();
      v8 = v36;
      v37 = 831;
      goto LABEL_64;
    }
    dwFileAttributes = FileInformation.dwFileAttributes;
    v53 = hObject;
    *((_QWORD *)&v56 + 1) = &v65;
    v57 = &v51;
    *(_QWORD *)&v55 = v49;
    *(_QWORD *)&v54 = a3;
    hObject = 0;
    *((_QWORD *)&v54 + 1) = p_hObject;
    v52 = FileInformation.dwFileAttributes;
    v59 = 1;
    v58[0] = 0;
    if ( (v45 & 2) == 0 )
      EfspAuditProtectionRemoved(p_hObject);
    if ( (dwFileAttributes & 0x10) != 0 )
      v41 = EfspDecryptDirectory(&v52);
    else
      v41 = EfspDecryptFile(&v52);
    v8 = v41;
  }
LABEL_18:
  if ( (unsigned int)dword_180114250 > 4 )
  {
    v45 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180114250,
      (__int64)byte_180101F79,
      v21,
      v22,
      (__int64)&v45);
  }
  if ( !RtlDllShutdownInProgress()
    && (unsigned int)dword_180114218 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_180114218, 0x400000000000LL) )
  {
    v49 = 0x1000000;
    v45 = v8;
    v47 = (struct _EFS_USER_INFO *)1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v23,
      (int)&byte_180101F37,
      v24,
      (__int64)&v47,
      (__int64)&v45,
      (__int64)&v49);
  }
  if ( DestinationString.Buffer )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
    DestinationString.Buffer = 0;
  }
  if ( !v58[0] && a3 )
    MarkFileForDelete(a3);
  if ( p_hObject && *((_DWORD *)p_hObject - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( hObject )
    CloseHandle(hObject);
  if ( v53 )
    CloseHandle(v53);
  OefsExclusiveOperationContext::~OefsExclusiveOperationContext((OefsExclusiveOperationContext *)&v60);
  return v8;
}

```

## disassembly

```asm
0x180013c68  push    rbp
0x180013c6a  push    rbx
0x180013c6b  push    rsi
0x180013c6c  push    rdi
0x180013c6d  push    r12
0x180013c6f  push    r13
0x180013c71  push    r14
0x180013c73  push    r15
0x180013c75  sub     rsp, 1C8h
0x180013c7c  lea     rbp, [rsp+60h]
0x180013c81  mov     rax, cs:__security_cookie
0x180013c88  xor     rax, rbp
0x180013c8b  mov     [rbp+1A0h+var_50], rax
0x180013c92  xorps   xmm0, xmm0
0x180013c95  mov     [rbp+1A0h+var_178], rdx
0x180013c99  xor     r15d, r15d
0x180013c9c  mov     [rbp+1A0h+var_190], rcx
0x180013ca0  mov     r12, r8
0x180013ca3  mov     [rbp+1A0h+var_19C], r9d
0x180013ca7  mov     r14, rdx
0x180013caa  mov     [rbp+1A0h+hObject], r15
0x180013cae  xor     eax, eax
0x180013cb0  mov     [rbp+1A0h+var_168], r15
0x180013cb4  xorps   xmm1, xmm1
0x180013cb7  mov     [rbp+1A0h+var_90], rax
0x180013cbe  lea     r8d, [r15+60h]; Size
0x180013cc2  xor     edx, edx; Val
0x180013cc4  lea     rcx, [rbp+1A0h+var_160]; void *
0x180013cc8  mov     r13d, r9d
0x180013ccb  movups  [rbp+1A0h+var_A0], xmm0
0x180013cd2  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.Length], xmm0
0x180013cd9  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.ObjectName], xmm0
0x180013ce0  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180013ce7  movups  xmmword ptr [rbp+1A0h+IoStatusBlock], xmm0
0x180013cee  movups  xmmword ptr [rbp+1A0h+DestinationString.Length], xmm1
0x180013cf2  call    memset_0
0x180013cf7  xor     edx, edx; SourceString
0x180013cf9  mov     qword ptr [rbp+1A0h+LastWriteTime.dwLowDateTime], r15
0x180013cfd  lea     rcx, [rbp+1A0h+DestinationString]; DestinationString
0x180013d01  mov     [rbp+1A0h+var_100], r15d
0x180013d08  mov     [rbp+1A0h+var_F8], r15
0x180013d0f  mov     [rbp+1A0h+var_F0], r15b
0x180013d16  mov     byte ptr [rbp+1A0h+var_1A0], r15b
0x180013d1a  call    cs:__imp_RtlInitUnicodeString
0x180013d20  movzx   esi, word ptr [r14]
0x180013d24  lea     ebx, [r15+8]
0x180013d28  xorps   xmm0, xmm0
0x180013d2b  mov     [rbp+1A0h+var_160], 0FFFFFFFFh
0x180013d32  add     rsi, 2
0x180013d36  movdqa  [rbp+1A0h+var_150], xmm0
0x180013d3b  cmp     rsi, cs:g_ulMaxStackAllocSize
0x180013d42  xorps   xmm1, xmm1
0x180013d45  movdqa  [rbp+1A0h+var_140], xmm1
0x180013d4a  mov     edi, r15d
0x180013d4d  movdqa  [rbp+1A0h+var_130], xmm0
0x180013d52  mov     [rbp+1A0h+var_120], r15
0x180013d59  mov     [rbp+1A0h+var_118], r15b
0x180013d60  mov     [rbp+1A0h+var_114], 0FFFFFFFFh
0x180013d6a  mov     [rbp+1A0h+var_158], r15
0x180013d6e  ja      short loc_180013DC6
0x180013d70  mov     rcx, cs:g_ulAdditionalProbeSize
0x180013d77  add     rcx, rbx
0x180013d7a  add     rcx, rsi
0x180013d7d  cmp     rcx, rsi
0x180013d80  jb      short loc_180013DC6
0x180013d82  call    VerifyStackAvailable
0x180013d87  test    eax, eax
0x180013d89  jz      short loc_180013DC6
0x180013d8b  lea     rax, [rsi+8]
0x180013d8f  lea     rcx, [rax+0Fh]
0x180013d93  cmp     rcx, rax
0x180013d96  ja      short loc_180013DA2
0x180013d98  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180013da2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180013da6  mov     rax, rcx
0x180013da9  call    _alloca_probe
0x180013dae  sub     rsp, rcx
0x180013db1  lea     rdi, [rsp+200h+var_1A0]
0x180013db6  test    rdi, rdi
0x180013db9  jz      short loc_180013DC6
0x180013dbb  mov     dword ptr [rdi], 6B637453h
0x180013dc1  add     rdi, rbx
0x180013dc4  jnz     short loc_180013DEC
0x180013dc6  lea     rcx, [rsi+8]
0x180013dca  cmp     rcx, rsi
0x180013dcd  jb      short loc_180013DEC
0x180013dcf  mov     rax, cs:g_pfnAllocate
0x180013dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ddb  mov     rdi, rax
0x180013dde  test    rax, rax
0x180013de1  jz      short loc_180013DEC
0x180013de3  mov     dword ptr [rax], 70616548h
0x180013de9  add     rdi, rbx
0x180013dec  test    rdi, rdi
0x180013def  jnz     short loc_180013E41
0x180013df1  movzx   r8d, word ptr [r14]
0x180013df5  lea     r9d, [rdi+4]
0x180013df9  mov     rcx, cs:g_hPublisher
0x180013e00  lea     rdx, EFS_ERROR_MEMORY
0x180013e07  add     r8d, 2
0x180013e0b  mov     dword ptr [rsp+200h+AllocationSize], 254h
0x180013e13  call    fnEfsLogTrace1
0x180013e18  mov     dword ptr [rsp+200h+AllocationSize], 255h
0x180013e20  mov     r8d, ebx
0x180013e23  mov     rcx, cs:g_hPublisher
0x180013e2a  lea     rdx, EFS_TRACE_ERROR
0x180013e31  mov     r9d, 4
0x180013e37  call    fnEfsLogTrace1
0x180013e3c  jmp     loc_180013ECB
0x180013e41  movzx   ecx, word ptr [r14]
0x180013e45  shr     rcx, 1
0x180013e48  mov     [rdi+rcx*2], r15w
0x180013e4d  mov     rcx, rdi; void *
0x180013e50  movzx   r8d, word ptr [r14]; Size
0x180013e54  mov     rdx, [r14+8]; Src
0x180013e58  call    memcpy_0
0x180013e5d  mov     rcx, rdi; lpFileName
0x180013e60  call    cs:__imp_GetFileAttributesW
0x180013e66  mov     r15d, eax
0x180013e69  cmp     eax, 0FFFFFFFFh
0x180013e6c  jnz     loc_180013FFE
0x180013e72  call    cs:__imp_GetLastError
0x180013e78  mov     rcx, cs:g_hPublisher
0x180013e7f  lea     rdx, EFS_API_ERROR
0x180013e86  mov     r8d, eax
0x180013e89  mov     dword ptr [rsp+200h+AllocationSize], 25Fh
0x180013e91  mov     r9d, 4
0x180013e97  call    fnEfsLogTrace1
0x180013e9c  call    cs:__imp_GetLastError
0x180013ea2  mov     ebx, eax
0x180013ea4  mov     dword ptr [rsp+200h+AllocationSize], 260h
0x180013eac  mov     r8d, eax
0x180013eaf  mov     rcx, cs:g_hPublisher
0x180013eb6  lea     rdx, EFS_TRACE_ERROR
0x180013ebd  mov     r9d, 4
0x180013ec3  call    fnEfsLogTrace1
0x180013ec8  xor     r15d, r15d
0x180013ecb  mov     eax, cs:dword_180114250
0x180013ed1  cmp     eax, 4
0x180013ed4  jbe     short loc_180013EF5
0x180013ed6  lea     rax, [rbp+1A0h+var_19C]
0x180013eda  mov     [rbp+1A0h+var_19C], ebx
0x180013edd  lea     rdx, byte_180101F79
0x180013ee4  mov     [rsp+200h+AllocationSize], rax
0x180013ee9  lea     rcx, dword_180114250
0x180013ef0  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180013ef5  call    cs:__imp_RtlDllShutdownInProgress
0x180013efb  test    al, al
0x180013efd  jnz     short loc_180013F59
0x180013eff  mov     eax, cs:dword_180114218
0x180013f05  cmp     eax, 5
0x180013f08  jbe     short loc_180013F59
0x180013f0a  mov     rdx, 400000000000h
0x180013f14  lea     rcx, dword_180114218
0x180013f1b  call    _tlgKeywordOn
0x180013f20  test    al, al
0x180013f22  jz      short loc_180013F59
0x180013f24  lea     rax, [rbp+1A0h+var_178]
0x180013f28  mov     [rbp+1A0h+var_178], 1000000h
0x180013f30  mov     qword ptr [rsp+200h+FileAttributes], rax
0x180013f35  lea     r9, [rbp+1A0h+var_190]
0x180013f39  lea     rax, [rbp+1A0h+var_19C]
0x180013f3d  mov     [rbp+1A0h+var_19C], ebx
0x180013f40  lea     rdx, byte_180101F37
0x180013f47  mov     [rsp+200h+AllocationSize], rax
0x180013f4c  mov     [rbp+1A0h+var_190], 1
0x180013f54  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180013f59  cmp     [rbp+1A0h+DestinationString.Buffer], r15
0x180013f5d  jz      short loc_180013F7C
0x180013f5f  mov     rcx, gs:60h
0x180013f68  xor     edx, edx; Flags
0x180013f6a  mov     r8, [rbp+1A0h+DestinationString.Buffer]; P
0x180013f6e  mov     rcx, [rcx+30h]; HeapHandle
0x180013f72  call    cs:__imp_RtlFreeHeap
0x180013f78  mov     [rbp+1A0h+DestinationString.Buffer], r15
0x180013f7c  cmp     [rbp+1A0h+var_118], r15b
0x180013f83  jnz     short loc_180013F92
0x180013f85  test    r12, r12
0x180013f88  jz      short loc_180013F92
0x180013f8a  mov     rcx, r12
0x180013f8d  call    MarkFileForDelete
0x180013f92  test    rdi, rdi
0x180013f95  jz      short loc_180013FAF
0x180013f97  lea     rcx, [rdi-8]
0x180013f9b  cmp     dword ptr [rcx], 70616548h
0x180013fa1  jnz     short loc_180013FAF
0x180013fa3  mov     rax, cs:g_pfnFree
0x180013faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013faf  mov     rcx, [rbp+1A0h+hObject]; hObject
0x180013fb3  test    rcx, rcx
0x180013fb6  jz      short loc_180013FBE
0x180013fb8  call    cs:__imp_CloseHandle
0x180013fbe  mov     rcx, [rbp+1A0h+var_158]; hObject
0x180013fc2  test    rcx, rcx
0x180013fc5  jz      short loc_180013FCD
0x180013fc7  call    cs:__imp_CloseHandle
0x180013fcd  lea     rcx, [rbp+1A0h+var_100]; this
0x180013fd4  call    ??1OefsExclusiveOperationContext@@QEAA@XZ; OefsExclusiveOperationContext::~OefsExclusiveOperationContext(void)
0x180013fd9  mov     eax, ebx
0x180013fdb  mov     rcx, [rbp+1A0h+var_50]
0x180013fe2  xor     rcx, rbp; StackCookie
0x180013fe5  call    __security_check_cookie
0x180013fea  lea     rsp, [rbp+168h]
0x180013ff1  pop     r15
0x180013ff3  pop     r14
0x180013ff5  pop     r13
0x180013ff7  pop     r12
0x180013ff9  pop     rdi
0x180013ffa  pop     rsi
0x180013ffb  pop     rbx
0x180013ffc  pop     rbp
0x180013ffd  retn
0x180013ffe  xor     r9d, r9d; DirectoryInfo
0x180014001  lea     rdx, [rbp+1A0h+DestinationString]; NtPathName
0x180014005  xor     r8d, r8d; NtFileNamePart
0x180014008  mov     rcx, rdi; DosPathName
0x18001400b  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180014011  test    al, al
0x180014013  jnz     short loc_18001404B
0x180014015  call    cs:__imp_GetLastError
0x18001401b  mov     ebx, eax
0x18001401d  mov     r8d, eax
0x180014020  mov     esi, 26Ch
0x180014025  mov     rcx, cs:g_hPublisher
0x18001402c  lea     rdx, EFS_API_ERROR
0x180014033  mov     r9d, 4
0x180014039  mov     dword ptr [rsp+200h+AllocationSize], esi
0x18001403d  call    fnEfsLogTrace1
0x180014042  mov     dword ptr [rsp+200h+AllocationSize], esi
0x180014046  jmp     loc_180013EAC
0x18001404b  xor     ebx, ebx
0x18001404d  mov     r14d, r15d
0x180014050  and     r14d, 10h
0x180014054  jnz     short loc_1800140BF
0x180014056  call    ?OefsCheckGlobalSupport@@YA_NXZ; OefsCheckGlobalSupport(void)
0x18001405b  test    al, al
0x18001405d  jz      short loc_1800140BF
0x18001405f  test    r12, r12
0x180014062  jz      short loc_1800140BF
0x180014064  mov     rcx, [rbp+1A0h+var_190]; struct _EFS_USER_INFO *
0x180014068  lea     rax, [rbp+1A0h+var_118]
0x18001406f  mov     qword ptr [rsp+200h+FileAttributes], rax; unsigned __int8 *
0x180014074  lea     rdx, [rbp+1A0h+DestinationString]; struct _UNICODE_STRING *
0x180014078  mov     r9, r12; void *
0x18001407b  mov     dword ptr [rsp+200h+AllocationSize], r13d; unsigned int
0x180014080  mov     r8, rdi; unsigned __int16 *
0x180014083  call    ?OefsDecryptFileSrv@@YAJPEAU_EFS_USER_INFO@@PEAU_UNICODE_STRING@@PEBGPEAXKPEAE@Z; OefsDecryptFileSrv(_EFS_USER_INFO *,_UNICODE_STRING *,ushort const *,void *,ulong,uchar *)
0x180014088  test    eax, eax
0x18001408a  jns     loc_180013EC8
0x180014090  cmp     eax, 80070032h
0x180014095  jz      short loc_1800140BF
0x180014097  mov     ecx, eax
0x180014099  movzx   ebx, ax
0x18001409c  and     ecx, 1FFF0000h
0x1800140a2  cmp     ecx, 70000h
0x1800140a8  jz      short loc_1800140AF
0x1800140aa  mov     ebx, 1771h
0x1800140af  mov     dword ptr [rsp+200h+AllocationSize], 289h
0x1800140b7  mov     r8d, ebx
0x1800140ba  jmp     loc_180013EAF
0x1800140bf  lea     rax, [rbp+1A0h+DestinationString]
0x1800140c3  mov     dword ptr [rbp+1A0h+var_190], ebx
0x1800140c6  mov     [rbp+1A0h+ObjectAttributes.ObjectName], rax
0x1800140cd  xorps   xmm0, xmm0
0x1800140d0  mov     eax, r14d
0x1800140d3  mov     [rbp+1A0h+ObjectAttributes.Length], 30h ; '0'
0x1800140dd  neg     eax
0x1800140df  mov     [rbp+1A0h+ObjectAttributes.RootDirectory], rbx
0x1800140e6  mov     [rbp+1A0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800140f0  sbb     esi, esi
0x1800140f2  and     esi, 0FFDFFFC1h
0x1800140f8  add     esi, 200060h
0x1800140fe  neg     r14d
0x180014101  movdqu  xmmword ptr [rbp+1A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180014109  sbb     r13d, r13d
0x18001410c  and     r13d, 7
0x180014110  mov     [rsp+200h+EaLength], ebx; EaLength
0x180014114  lea     r9, [rbp+1A0h+IoStatusBlock]; IoStatusBlock
0x18001411b  mov     [rsp+200h+EaBuffer], rbx; EaBuffer
0x180014120  lea     r8, [rbp+1A0h+ObjectAttributes]; ObjectAttributes
0x180014127  mov     [rsp+200h+CreateOptions], esi; CreateOptions
0x18001412b  lea     rcx, [rbp+1A0h+hObject]; FileHandle
0x18001412f  mov     [rsp+200h+CreateDisposition], 1; CreateDisposition
0x180014137  mov     edx, 100183h; DesiredAccess
0x18001413c  mov     [rsp+200h+ShareAccess], r13d; ShareAccess
0x180014141  mov     [rsp+200h+FileAttributes], ebx; FileAttributes
0x180014145  mov     [rsp+200h+AllocationSize], rbx; AllocationSize
0x18001414a  call    cs:__imp_NtCreateFile
0x180014150  mov     r14d, eax
0x180014153  test    eax, eax
0x180014155  jns     loc_180014200
0x18001415b  cmp     dword ptr [rbp+1A0h+var_190], ebx
0x18001415e  jnz     short loc_180014179
0x180014160  cmp     eax, 0C00000BAh
0x180014165  jnz     short loc_180014179
0x180014167  and     esi, 0FFDFFFBFh
0x18001416d  mov     dword ptr [rbp+1A0h+var_190], 1
0x180014174  or      esi, 1
0x180014177  jmp     short loc_180014110
0x180014179  mov     rcx, cs:g_hPublisher
  ... truncated ...
```
