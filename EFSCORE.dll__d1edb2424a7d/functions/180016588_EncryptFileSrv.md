# EncryptFileSrv

- ea: `0x180016588`
- end: `0x180016db5`
- name: `EncryptFileSrv`
- size: `2093`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800106e0`
- `0x180016080`
- `0x180042a3c`

## callees

- `0x180004f86`
- `0x180005045`
- `0x18000ddb8`
- `0x180010bf0`
- `0x180016588`
- `0x180017510`
- `0x180018fcc`
- `0x18001bf1c`
- `0x18001c22c`
- `0x18001d1ac`
- `0x180024dcc`
- `0x180025084`
- `0x18004d314`
- `0x18004d998`
- `0x18004e030`
- `0x18004e4c4`
- `0x180063698`
- `0x1800688fc`
- `0x1800704f4`
- `0x1800d87ac`
- `0x1800dca3c`
- `0x1800dddf0`
- `0x1800ddeb0`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001689d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800168ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001689d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800168ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016b04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016b14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016b04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016b14`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180016d32`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180016d32`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180016d0b`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180016d0b`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180016bda`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180016bda`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180016863`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180016863`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016a59`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016a59`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001698b`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001698b`

## pseudocode

```c
__int64 __fastcall EncryptFileSrv(struct _EFS_USER_INFO *a1, const void **a2, const void **a3, void *a4)
{
  __int64 v7; // rbx
  LPVOID *v8; // r14
  unsigned __int64 v9; // rbx
  LPVOID *p_lpMem; // rsi
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  _DWORD *v15; // rax
  DWORD v16; // ebx
  int v17; // r8d
  unsigned __int64 v18; // rbx
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  _DWORD *v23; // rax
  DWORD FileAttributesW; // r12d
  DWORD LastError; // eax
  DWORD v26; // eax
  int v27; // edi
  __int64 v28; // rcx
  DWORD v29; // r15d
  DWORD v30; // r8d
  unsigned int v31; // eax
  __int64 v32; // rcx
  DWORD v33; // eax
  int v34; // eax
  HANDLE FileW; // rax
  void *v36; // r15
  int v37; // eax
  DWORD v38; // ecx
  DWORD v39; // r8d
  DWORD v41; // eax
  DWORD v42; // r12d
  int v43; // r8d
  DWORD v44; // eax
  int v45; // eax
  DWORD v46; // ecx
  __int64 v47; // rcx
  DWORD v48; // eax
  _BYTE v49[32]; // [rsp+0h] [rbp-40h] BYREF
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-20h]
  int v51; // [rsp+40h] [rbp+0h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp+8h] BYREF
  struct _EFS_FILE_KEY *v53; // [rsp+50h] [rbp+10h] BYREF
  struct _EFS_USER_INFO *v54; // [rsp+58h] [rbp+18h]
  struct _FILETIME LastWriteTime; // [rsp+60h] [rbp+20h] BYREF
  __int64 v56; // [rsp+68h] [rbp+28h] BYREF
  int v57; // [rsp+70h] [rbp+30h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+38h]
  __int128 v59; // [rsp+80h] [rbp+40h]
  __int128 v60; // [rsp+90h] [rbp+50h]
  __int128 v61; // [rsp+A0h] [rbp+60h]
  __int64 *v62; // [rsp+B0h] [rbp+70h]
  unsigned __int8 v63[4]; // [rsp+B8h] [rbp+78h] BYREF
  int v64; // [rsp+BCh] [rbp+7Ch]
  const void **v65; // [rsp+D0h] [rbp+90h]
  int v66; // [rsp+E0h] [rbp+A0h] BYREF
  __int64 v67; // [rsp+E8h] [rbp+A8h]
  char v68; // [rsp+F0h] [rbp+B0h]
  struct _UNICODE_STRING NtPathName; // [rsp+F8h] [rbp+B8h] BYREF
  __int128 v70; // [rsp+108h] [rbp+C8h] BYREF
  __int64 v71; // [rsp+118h] [rbp+D8h]
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+120h] [rbp+E0h] BYREF

  v65 = a2;
  v54 = a1;
  v71 = 0;
  v56 = 0;
  lpMem = 0;
  v53 = 0;
  v70 = 0;
  memset_0(&v57, 0, 0x60u);
  v7 = *(unsigned __int16 *)a2;
  v8 = 0;
  LastWriteTime = 0;
  v66 = 0;
  v9 = v7 + 2;
  v67 = 0;
  p_lpMem = 0;
  v68 = 0;
  LOBYTE(v51) = 0;
  NtPathName = 0;
  v57 = -1;
  memset(&FileInformation, 0, sizeof(FileInformation));
  hObject = (HANDLE)-1LL;
  v62 = 0;
  v63[0] = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v64 = -1;
  if ( v9 > g_ulMaxStackAllocSize || v9 + g_ulAdditionalProbeSize + 8 < v9 || !(unsigned int)VerifyStackAvailable() )
    goto LABEL_108;
  v11 = v9 + 23;
  if ( v9 + 23 <= v9 + 8 )
    v11 = 0xFFFFFFFFFFFFFF0LL;
  v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
  v13 = alloca(v12);
  v14 = alloca(v12);
  p_lpMem = (LPVOID *)&v51;
  if ( v49 == (_BYTE *)-64LL || (v51 = 1801679955, (p_lpMem = &lpMem) == 0) )
  {
LABEL_108:
    if ( v9 + 8 >= v9 )
    {
      v15 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_lpMem = (LPVOID *)v15;
      if ( v15 )
      {
        *v15 = 1885431112;
        p_lpMem = (LPVOID *)(v15 + 2);
      }
    }
  }
  if ( p_lpMem )
  {
    *((_WORD *)p_lpMem + ((unsigned __int64)*(unsigned __int16 *)a2 >> 1)) = 0;
    memcpy_0(p_lpMem, a2[1], *(unsigned __int16 *)a2);
    if ( a3 )
    {
      v18 = *(unsigned __int16 *)a3 + 2LL;
      if ( v18 > g_ulMaxStackAllocSize
        || v18 + g_ulAdditionalProbeSize + 8 < v18
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_109;
      }
      v19 = v18 + 23;
      if ( v18 + 23 <= v18 + 8 )
        v19 = 0xFFFFFFFFFFFFFF0LL;
      v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
      v21 = alloca(v20);
      v22 = alloca(v20);
      v8 = (LPVOID *)&v51;
      if ( v49 == (_BYTE *)-64LL || (v51 = 1801679955, (v8 = &lpMem) == 0) )
      {
LABEL_109:
        if ( v18 + 8 >= v18 )
        {
          v23 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          v8 = (LPVOID *)v23;
          if ( v23 )
          {
            *v23 = 1885431112;
            v8 = (LPVOID *)(v23 + 2);
          }
        }
      }
      if ( !v8 )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, *(unsigned __int16 *)a3 + 2, 4, 195);
        dwCreationDisposition[0] = 196;
        goto LABEL_13;
      }
      *((_WORD *)v8 + ((unsigned __int64)*(unsigned __int16 *)a3 >> 1)) = 0;
      memcpy_0(v8, a3[1], *(unsigned __int16 *)a3);
    }
    FileAttributesW = GetFileAttributesW((LPCWSTR)p_lpMem);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 4, 208);
      v26 = GetLastError();
      v16 = v26;
      dwCreationDisposition[0] = 209;
LABEL_31:
      v17 = v26;
      goto LABEL_14;
    }
    v27 = FileAttributesW & 0x10;
    if ( v8 )
    {
      v31 = EfsParseDescriptorType((const unsigned __int16 *)v8);
      if ( !(unsigned __int8)EfsConstructDescriptorEFS(v54, v8, v31, p_lpMem, &v53, &lpMem) )
      {
        v16 = GetLastError();
        if ( !v16 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v32);
        v29 = 255;
        goto LABEL_37;
      }
    }
    else if ( !(unsigned __int8)EfsConstructEFS(v54, &v53, &lpMem) )
    {
      v16 = GetLastError();
      if ( !v16 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v28);
      v29 = 240;
LABEL_37:
      v30 = v16;
LABEL_38:
      v26 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v30, 4, v29);
      dwCreationDisposition[0] = v29;
      goto LABEL_31;
    }
    if ( !RtlDosPathNameToNtPathName_U((PCWSTR)p_lpMem, &NtPathName, 0, 0) )
    {
      v33 = GetLastError();
      v29 = 269;
LABEL_45:
      v16 = v33;
      v30 = v33;
      goto LABEL_38;
    }
    if ( (FileAttributesW & 0x10) == 0 && OefsCheckGlobalSupport() && a4 )
    {
      v16 = 0;
      v34 = OefsEncryptFileSrv(
              v54,
              &NtPathName,
              (const unsigned __int16 *)p_lpMem,
              a4,
              (struct _EFS_DATA_STREAM_HEADER *)lpMem,
              v53,
              v63);
      if ( v34 >= 0 )
        goto LABEL_64;
      if ( v34 != -2147024846 )
      {
        v16 = (unsigned __int16)v34;
        if ( (v34 & 0x1FFF0000) != 0x70000 )
          v16 = 6000;
        dwCreationDisposition[0] = 303;
        v17 = v16;
        goto LABEL_14;
      }
    }
    FileW = CreateFileW(
              (LPCWSTR)p_lpMem,
              0x183u,
              v27 != 0 ? 7 : 0,
              0,
              3u,
              (FileAttributesW & 0x10) != 0 ? 0x2000000 : 0x200000,
              0);
    v36 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v33 = GetLastError();
      v29 = 340;
      goto LABEL_45;
    }
    if ( a4 )
    {
      v37 = OefsExclusiveOperationContext::Acquire(&v66, FileW, 0, &v51);
      v16 = v37;
      if ( v37 < 0 )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v37, 4, 104);
        v38 = v16;
        v16 = (unsigned __int16)v16;
        if ( (v38 & 0x1FFF0000) != 0x70000 )
          v16 = 1359;
        dwCreationDisposition[0] = 361;
        goto LABEL_61;
      }
      if ( !(_BYTE)v51 )
      {
        v16 = 32;
        dwCreationDisposition[0] = 366;
LABEL_61:
        v39 = v16;
LABEL_62:
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v39, 4, dwCreationDisposition[0]);
LABEL_63:
        CloseHandle(v36);
        goto LABEL_64;
      }
      if ( !GetFileInformationByHandle(v36, &FileInformation) )
      {
        v41 = GetLastError();
        v42 = 373;
LABEL_84:
        v16 = v41;
        v43 = v41;
LABEL_85:
        v44 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v43, 4, v42);
        dwCreationDisposition[0] = v42;
        v39 = v44;
        goto LABEL_62;
      }
      if ( (FileInformation.dwFileAttributes & 0x10) != v27 )
      {
        v16 = 87;
        v42 = 387;
        v43 = 87;
        goto LABEL_85;
      }
      if ( (FileInformation.dwFileAttributes & 0x4000) != 0 )
      {
        if ( (FileInformation.dwFileAttributes & 0x10) != 0
          || (v45 = EfsCheckFileAccess(v54, 0, v36), v16 = v45, v45 >= 0) )
        {
          v16 = 0;
          goto LABEL_79;
        }
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v45, 4, 152);
        v46 = v16;
        v16 = (unsigned __int16)v16;
        if ( (v46 & 0x1FFF0000) != 0x70000 )
          v16 = 1359;
        dwCreationDisposition[0] = 409;
        goto LABEL_61;
      }
    }
    if ( (FileAttributesW & 0x400) != 0 )
    {
      v16 = EfspCheckReparseTag(v36);
      if ( v16 )
        goto LABEL_63;
    }
    v16 = EfspGetFileInformation(v36, &v56);
    if ( v16 )
      goto LABEL_63;
    if ( GetFileTime(v36, 0, 0, &LastWriteTime) )
    {
      if ( SetFileTime(v36, 0, 0, &LastWriteTime) )
      {
        *(_QWORD *)&v60 = v65;
        *((_QWORD *)&v60 + 1) = lpMem;
        v57 = FileAttributesW;
        hObject = v36;
        *(_QWORD *)&v59 = a4;
        *((_QWORD *)&v59 + 1) = p_lpMem;
        v47 = *((_QWORD *)v53 + 1);
        *((_QWORD *)&v61 + 1) = &v70;
        *(_QWORD *)&v61 = v47;
        v62 = &v56;
        v63[0] = 0;
        v64 = 0;
        if ( (FileAttributesW & 0x10) != 0 )
          v48 = EfspEncryptDirectory(&v57);
        else
          v48 = EfspEncryptFile(&v57);
        v16 = v48;
        goto LABEL_64;
      }
      v41 = GetLastError();
      v42 = 465;
    }
    else
    {
      v41 = GetLastError();
      v42 = 458;
    }
    goto LABEL_84;
  }
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, *(unsigned __int16 *)a2 + 2, 4, 179);
  dwCreationDisposition[0] = 180;
LABEL_13:
  v16 = 8;
  v17 = 8;
LABEL_14:
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v17, 4, dwCreationDisposition[0]);
LABEL_64:
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( !v63[0] && a4 )
    MarkFileForDelete(a4);
  if ( lpMem )
    EfsFreeHeap(lpMem);
  if ( v53 )
    EfsStreamFileKeyDestroy(v53);
  if ( p_lpMem && *((_DWORD *)p_lpMem - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v8 && *((_DWORD *)v8 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_79:
  OefsExclusiveOperationContext::~OefsExclusiveOperationContext((OefsExclusiveOperationContext *)&v66);
  return v16;
}

```

## disassembly

```asm
0x180016588  push    rbp
0x18001658a  push    rbx
0x18001658b  push    rsi
0x18001658c  push    rdi
0x18001658d  push    r12
0x18001658f  push    r13
0x180016591  push    r14
0x180016593  push    r15
0x180016595  sub     rsp, 168h
0x18001659c  lea     rbp, [rsp+40h]
0x1800165a1  mov     rax, cs:__security_cookie
0x1800165a8  xor     rax, rbp
0x1800165ab  mov     [rbp+160h+var_48], rax
0x1800165b2  xor     eax, eax
0x1800165b4  mov     [rbp+160h+var_D0], rdx
0x1800165bb  mov     rdi, r8
0x1800165be  mov     [rbp+160h+var_148], rcx
0x1800165c2  mov     r15, rdx
0x1800165c5  mov     [rbp+160h+var_88], rax
0x1800165cc  xorps   xmm0, xmm0
0x1800165cf  mov     [rbp+160h+var_138], rax
0x1800165d3  lea     r8d, [rax+60h]; Size
0x1800165d7  mov     [rbp+160h+lpMem], rax
0x1800165db  xor     edx, edx; Val
0x1800165dd  mov     [rbp+160h+var_150], rax
0x1800165e1  lea     rcx, [rbp+160h+var_130]; void *
0x1800165e5  mov     r13, r9
0x1800165e8  movups  [rbp+160h+var_98], xmm0
0x1800165ef  call    memset_0
0x1800165f4  movzx   ebx, word ptr [r15]
0x1800165f8  xor     r14d, r14d
0x1800165fb  xorps   xmm0, xmm0
0x1800165fe  mov     qword ptr [rbp+160h+LastWriteTime.dwLowDateTime], 0
0x180016606  xor     eax, eax
0x180016608  mov     [rbp+160h+var_C0], r14d
0x18001660f  mov     [rbp+160h+FileInformation.nFileIndexLow], eax
0x180016615  add     rbx, 2
0x180016619  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001661d  mov     [rbp+160h+var_B8], r14
0x180016624  xor     esi, esi
0x180016626  mov     [rbp+160h+var_B0], r14b
0x18001662d  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180016634  lea     r12d, [r14+8]
0x180016638  xorps   xmm1, xmm1
0x18001663b  mov     byte ptr [rbp+160h+var_160], r14b
0x18001663f  movups  xmmword ptr [rbp+160h+NtPathName.Length], xmm0
0x180016646  mov     [rbp+160h+var_130], 0FFFFFFFFh
0x18001664d  movups  xmmword ptr [rbp+160h+FileInformation.dwFileAttributes], xmm0
0x180016654  mov     [rbp+160h+hObject], rax
0x180016658  movups  xmmword ptr [rbp+160h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18001665f  mov     [rbp+160h+var_F0], r14
0x180016663  movups  xmmword ptr [rbp+160h+FileInformation.nFileSizeHigh], xmm0
0x18001666a  mov     [rbp+160h+var_E8], r14b
0x18001666e  movdqa  [rbp+160h+var_120], xmm0
0x180016673  movdqa  [rbp+160h+var_110], xmm1
0x180016678  movdqa  [rbp+160h+var_100], xmm0
0x18001667d  mov     [rbp+160h+var_E4], eax
0x180016680  ja      short loc_1800166D8
0x180016682  mov     rcx, cs:g_ulAdditionalProbeSize
0x180016689  add     rcx, r12
0x18001668c  add     rcx, rbx
0x18001668f  cmp     rcx, rbx
0x180016692  jb      short loc_1800166D8
0x180016694  call    VerifyStackAvailable
0x180016699  test    eax, eax
0x18001669b  jz      short loc_1800166D8
0x18001669d  lea     rax, [rbx+8]
0x1800166a1  lea     rcx, [rax+0Fh]
0x1800166a5  cmp     rcx, rax
0x1800166a8  ja      short loc_1800166B4
0x1800166aa  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800166b4  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800166b8  mov     rax, rcx
0x1800166bb  call    _alloca_probe
0x1800166c0  sub     rsp, rcx
0x1800166c3  lea     rsi, [rsp+1A0h+var_160]
0x1800166c8  test    rsi, rsi
0x1800166cb  jz      short loc_1800166D8
0x1800166cd  mov     dword ptr [rsi], 6B637453h
0x1800166d3  add     rsi, r12
0x1800166d6  jnz     short loc_1800166FE
0x1800166d8  lea     rcx, [rbx+8]
0x1800166dc  cmp     rcx, rbx
0x1800166df  jb      short loc_1800166FE
0x1800166e1  mov     rax, cs:g_pfnAllocate
0x1800166e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166ed  mov     rsi, rax
0x1800166f0  test    rax, rax
0x1800166f3  jz      short loc_1800166FE
0x1800166f5  mov     dword ptr [rax], 70616548h
0x1800166fb  add     rsi, r12
0x1800166fe  test    rsi, rsi
0x180016701  jnz     short loc_180016755
0x180016703  movzx   r8d, word ptr [r15]
0x180016707  lea     edi, [rsi+4]
0x18001670a  mov     rcx, cs:g_hPublisher
0x180016711  lea     rdx, EFS_ERROR_MEMORY
0x180016718  add     r8d, 2
0x18001671c  mov     [rsp+1A0h+dwCreationDisposition], 0B3h
0x180016724  mov     r9d, edi
0x180016727  call    fnEfsLogTrace1
0x18001672c  mov     [rsp+1A0h+dwCreationDisposition], 0B4h
0x180016734  mov     ebx, r12d
0x180016737  mov     r8d, r12d
0x18001673a  mov     r9d, edi
0x18001673d  mov     rcx, cs:g_hPublisher
0x180016744  lea     rdx, EFS_TRACE_ERROR
0x18001674b  call    fnEfsLogTrace1
0x180016750  jmp     loc_180016B0A
0x180016755  movzx   ecx, word ptr [r15]
0x180016759  xor     eax, eax
0x18001675b  shr     rcx, 1
0x18001675e  mov     [rsi+rcx*2], ax
0x180016762  mov     rcx, rsi; void *
0x180016765  movzx   r8d, word ptr [r15]; Size
0x180016769  mov     rdx, [r15+8]; Src
0x18001676d  call    memcpy_0
0x180016772  test    rdi, rdi
0x180016775  jz      loc_180016860
0x18001677b  movzx   ebx, word ptr [rdi]
0x18001677e  add     rbx, 2
0x180016782  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180016789  ja      short loc_1800167E2
0x18001678b  mov     rcx, cs:g_ulAdditionalProbeSize
0x180016792  add     rcx, r12
0x180016795  add     rcx, rbx
0x180016798  cmp     rcx, rbx
0x18001679b  jb      short loc_1800167E2
0x18001679d  call    VerifyStackAvailable
0x1800167a2  test    eax, eax
0x1800167a4  jz      short loc_1800167E2
0x1800167a6  lea     rax, [rbx+8]
0x1800167aa  lea     rcx, [rax+0Fh]
0x1800167ae  cmp     rcx, rax
0x1800167b1  ja      short loc_1800167BD
0x1800167b3  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800167bd  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800167c1  mov     rax, rcx
0x1800167c4  call    _alloca_probe
0x1800167c9  sub     rsp, rcx
0x1800167cc  lea     r14, [rsp+1A0h+var_160]
0x1800167d1  test    r14, r14
0x1800167d4  jz      short loc_1800167E2
0x1800167d6  mov     dword ptr [r14], 6B637453h
0x1800167dd  add     r14, r12
0x1800167e0  jnz     short loc_180016808
0x1800167e2  lea     rcx, [rbx+8]
0x1800167e6  cmp     rcx, rbx
0x1800167e9  jb      short loc_180016808
0x1800167eb  mov     rax, cs:g_pfnAllocate
0x1800167f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167f7  mov     r14, rax
0x1800167fa  test    rax, rax
0x1800167fd  jz      short loc_180016808
0x1800167ff  mov     dword ptr [rax], 70616548h
0x180016805  add     r14, r12
0x180016808  movzx   eax, word ptr [rdi]
0x18001680b  test    r14, r14
0x18001680e  jnz     short loc_180016843
0x180016810  mov     rcx, cs:g_hPublisher
0x180016817  lea     edi, [r14+4]
0x18001681b  mov     r9d, edi
0x18001681e  mov     [rsp+1A0h+dwCreationDisposition], 0C3h
0x180016826  lea     r8d, [rax+2]
0x18001682a  lea     rdx, EFS_ERROR_MEMORY
0x180016831  call    fnEfsLogTrace1
0x180016836  mov     [rsp+1A0h+dwCreationDisposition], 0C4h
0x18001683e  jmp     loc_180016734
0x180016843  mov     rcx, rax
0x180016846  xor     eax, eax
0x180016848  shr     rcx, 1
0x18001684b  mov     [r14+rcx*2], ax
0x180016850  mov     rcx, r14; void *
0x180016853  movzx   r8d, word ptr [rdi]; Size
0x180016857  mov     rdx, [rdi+8]; Src
0x18001685b  call    memcpy_0
0x180016860  mov     rcx, rsi; lpFileName
0x180016863  call    cs:__imp_GetFileAttributesW
0x180016869  mov     r12d, eax
0x18001686c  cmp     eax, 0FFFFFFFFh
0x18001686f  jnz     short loc_1800168B5
0x180016871  call    cs:__imp_GetLastError
0x180016877  mov     rcx, cs:g_hPublisher
0x18001687e  lea     rdx, EFS_API_ERROR
0x180016885  mov     edi, 4
0x18001688a  mov     [rsp+1A0h+dwCreationDisposition], 0D0h
0x180016892  mov     r9d, edi
0x180016895  mov     r8d, eax
0x180016898  call    fnEfsLogTrace1
0x18001689d  call    cs:__imp_GetLastError
0x1800168a3  mov     ebx, eax
0x1800168a5  mov     [rsp+1A0h+dwCreationDisposition], 0D1h
0x1800168ad  mov     r8d, eax
0x1800168b0  jmp     loc_18001673A
0x1800168b5  mov     edi, r12d
0x1800168b8  and     edi, 10h
0x1800168bb  mov     eax, edi
0x1800168bd  neg     eax
0x1800168bf  sbb     r15d, r15d
0x1800168c2  and     r15d, 1E00000h
0x1800168c9  add     r15d, 200000h
0x1800168d0  test    r14, r14
0x1800168d3  jnz     short loc_180016932
0x1800168d5  mov     rcx, [rbp+160h+var_148]
0x1800168d9  lea     r8, [rbp+160h+lpMem]
0x1800168dd  lea     rdx, [rbp+160h+var_150]
0x1800168e1  call    EfsConstructEFS
0x1800168e6  test    al, al
0x1800168e8  jnz     loc_18001697B
0x1800168ee  call    cs:__imp_GetLastError
0x1800168f4  mov     ebx, eax
0x1800168f6  test    eax, eax
0x1800168f8  jnz     short loc_1800168FF
0x1800168fa  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "rc != ERROR_SUCCESS")
0x1800168ff  mov     r15d, 0F0h
0x180016905  mov     r8d, ebx
0x180016908  mov     rcx, cs:g_hPublisher
0x18001690f  lea     rdx, EFS_API_ERROR
0x180016916  mov     edi, 4
0x18001691b  mov     [rsp+1A0h+dwCreationDisposition], r15d
0x180016920  mov     r9d, edi
0x180016923  call    fnEfsLogTrace1
0x180016928  mov     [rsp+1A0h+dwCreationDisposition], r15d
0x18001692d  jmp     loc_1800168AD
0x180016932  mov     rcx, r14; unsigned __int16 *
0x180016935  call    ?EfsParseDescriptorType@@YAKPEBG@Z; EfsParseDescriptorType(ushort const *)
0x18001693a  lea     rcx, [rbp+160h+lpMem]
0x18001693e  mov     r9, rsi
0x180016941  mov     qword ptr [rsp+1A0h+dwFlagsAndAttributes], rcx
0x180016946  mov     r8d, eax
0x180016949  lea     rcx, [rbp+160h+var_150]
0x18001694d  mov     rdx, r14
0x180016950  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rcx
0x180016955  mov     rcx, [rbp+160h+var_148]
0x180016959  call    EfsConstructDescriptorEFS
0x18001695e  test    al, al
0x180016960  jnz     short loc_18001697B
0x180016962  call    cs:__imp_GetLastError
0x180016968  mov     ebx, eax
0x18001696a  test    eax, eax
0x18001696c  jnz     short loc_180016973
0x18001696e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "rc != ERROR_SUCCESS")
0x180016973  mov     r15d, 0FFh
0x180016979  jmp     short loc_180016905
0x18001697b  xor     r9d, r9d; DirectoryInfo
0x18001697e  lea     rdx, [rbp+160h+NtPathName]; NtPathName
0x180016985  xor     r8d, r8d; NtFileNamePart
0x180016988  mov     rcx, rsi; DosPathName
0x18001698b  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180016991  test    al, al
0x180016993  jnz     short loc_1800169AB
0x180016995  call    cs:__imp_GetLastError
0x18001699b  mov     r15d, 10Dh
0x1800169a1  mov     ebx, eax
0x1800169a3  mov     r8d, eax
0x1800169a6  jmp     loc_180016908
0x1800169ab  test    edi, edi
0x1800169ad  jnz     short loc_180016A2D
0x1800169af  call    ?OefsCheckGlobalSupport@@YA_NXZ; OefsCheckGlobalSupport(void)
0x1800169b4  test    al, al
0x1800169b6  jz      short loc_180016A2D
0x1800169b8  test    r13, r13
0x1800169bb  jz      short loc_180016A2D
0x1800169bd  mov     rcx, [rbp+160h+var_148]; struct _EFS_USER_INFO *
0x1800169c1  lea     rax, [rbp+160h+var_E8]
0x1800169c5  mov     [rsp+1A0h+hTemplateFile], rax; unsigned __int8 *
0x1800169ca  lea     rdx, [rbp+160h+NtPathName]; struct _UNICODE_STRING *
0x1800169d1  mov     rax, [rbp+160h+var_150]
0x1800169d5  mov     r9, r13; void *
0x1800169d8  mov     qword ptr [rsp+1A0h+dwFlagsAndAttributes], rax; struct _EFS_FILE_KEY *
0x1800169dd  mov     r8, rsi; unsigned __int16 *
0x1800169e0  mov     rax, [rbp+160h+lpMem]
0x1800169e4  xor     ebx, ebx
0x1800169e6  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rax; struct _EFS_DATA_STREAM_HEADER *
0x1800169eb  call    ?OefsEncryptFileSrv@@YAJPEAU_EFS_USER_INFO@@PEAU_UNICODE_STRING@@PEBGPEAXPEAU_EFS_DATA_STREAM_HEADER@@PEAU_EFS_FILE_KEY@@PEAE@Z; OefsEncryptFileSrv(_EFS_USER_INFO *,_UNICODE_STRING *,ushort const *,void *,_EFS_DATA_STREAM_HEADER *,_EFS_FILE_KEY *,uchar *)
0x1800169f0  test    eax, eax
0x1800169f2  jns     loc_180016B0A
0x1800169f8  cmp     eax, 80070032h
0x1800169fd  jz      short loc_180016A2D
0x1800169ff  mov     ecx, eax
0x180016a01  movzx   ebx, ax
0x180016a04  and     ecx, 1FFF0000h
0x180016a0a  cmp     ecx, 70000h
0x180016a10  jz      short loc_180016A17
0x180016a12  mov     ebx, 1770h
0x180016a17  mov     [rsp+1A0h+dwCreationDisposition], 12Fh
0x180016a1f  mov     r9d, 4
0x180016a25  mov     r8d, ebx
0x180016a28  jmp     loc_18001673D
0x180016a2d  mov     eax, edi
0x180016a2f  mov     [rsp+1A0h+hTemplateFile], 0; hTemplateFile
0x180016a38  neg     eax
0x180016a3a  mov     [rsp+1A0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x180016a3f  mov     edx, 183h; dwDesiredAccess
0x180016a44  mov     [rsp+1A0h+dwCreationDisposition], 3; dwCreationDisposition
0x180016a4c  sbb     r8d, r8d
0x180016a4f  mov     rcx, rsi; lpFileName
0x180016a52  and     r8d, 7; dwShareMode
0x180016a56  xor     r9d, r9d; lpSecurityAttributes
0x180016a59  call    cs:__imp_CreateFileW
  ... truncated ...
```
