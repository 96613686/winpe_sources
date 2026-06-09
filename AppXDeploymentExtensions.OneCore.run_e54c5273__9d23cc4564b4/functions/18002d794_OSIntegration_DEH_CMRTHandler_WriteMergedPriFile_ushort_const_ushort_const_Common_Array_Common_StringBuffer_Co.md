# OSIntegration::DEH::CMRTHandler::_WriteMergedPriFile(ushort const *,ushort const *,Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> *)

- ea: `0x18002d794`
- end: `0x18002def4`
- name: `?_WriteMergedPriFile@CMRTHandler@DEH@OSIntegration@@AEAAJPEBG0PEAV?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@Common@@@Z`
- size: `1888`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *, _QWORD *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d1e4`

## callees

- `0x18001b84c`
- `0x18001c348`
- `0x18001c3c8`
- `0x18001c3fc`
- `0x18002d794`
- `0x18004b92c`
- `0x18008a584`
- `0x180094b44`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800bbf40`
- `0x1800cd2f8`
- `0x1800f0260`
- `0x1800f0700`
- `0x1800f0a7c`
- `0x180128894`
- `0x18013bcf8`
- `0x18013e28c`
- `0x18013e4a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002daf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002daf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d895`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002de7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d895`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002de7c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18002d8cd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18002d8cd`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18002da47`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18002da47`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002db83`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002db83`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18002daeb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18002daeb`
- `ext-ms-win-resources-deployment-l1-1-0!MergeRelatedPriFiles` at `0x18002d916`
- `ext-ms-win-resources-deployment-l1-1-0!MergeRelatedPriFiles` at `0x18002dd0e`
- `ext-ms-win-resources-deployment-l1-1-0!MergeRelatedPriFiles` at `0x18002d916`
- `ext-ms-win-resources-deployment-l1-1-0!MergeRelatedPriFiles` at `0x18002dd0e`

## string_xrefs

- `0x18002dc0c`: `Linked user-specific merged PRI file`
- `0x18002dbbe`: `Trying to copy shared PRI to user specific PRI`
- `0x18002da89`: `Unable to link shared merged PRI file to user-specific path`
- `0x18002dab5`: `Unable to link shared merged PRI file to user-specific path`
- `0x18002db26`: `Trying to move shared PRI to user specific PRI`
- `0x18002d9fc`: `Created shared merged PRI file`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSIntegration::DEH::CMRTHandler::_WriteMergedPriFile(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        _QWORD *a4)
{
  void *v8; // r14
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // rax
  int v12; // eax
  signed int v13; // ebx
  char *v14; // rdx
  char v15; // r13
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  int v22; // ecx
  signed int LastError; // eax
  __int64 v24; // rdx
  int v25; // ecx
  __int64 v26; // rdx
  signed int v27; // eax
  int v28; // ecx
  __int64 v29; // rdx
  signed int v30; // eax
  int v31; // ecx
  int v32; // ecx
  void *v33; // r12
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r8
  int v39; // eax
  unsigned int v40; // edi
  char *v41; // rdx
  unsigned __int64 v43; // rdx
  int v44; // [rsp+20h] [rbp-99h]
  int v45; // [rsp+20h] [rbp-99h]
  int v46; // [rsp+20h] [rbp-99h]
  HANDLE hObject; // [rsp+58h] [rbp-61h] BYREF
  void *v48; // [rsp+60h] [rbp-59h]
  const wchar_t *v49; // [rsp+68h] [rbp-51h] BYREF
  const WCHAR *v50; // [rsp+70h] [rbp-49h] BYREF
  int v51[2]; // [rsp+78h] [rbp-41h] BYREF
  _QWORD v52[3]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE FileInformation[36]; // [rsp+98h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v52[0] = L"MRT Deh";
  v52[1] = InvokeMRTMergeStart;
  v52[2] = InvokeMRTMergeStop;
  InvokeMRTMergeStart(L"MRT Deh");
  v8 = operator new[](saturated_mul(a4[2], 8u));
  v48 = v8;
  v9 = 0;
  v10 = a4[2];
  if ( v10 )
  {
    do
    {
      if ( v9 < v10 )
        v11 = *(_QWORD *)(8 * v9 + *a4);
      else
        v11 = 0;
      *((_QWORD *)v8 + v9++) = *(_QWORD *)(v11 + 8);
      v10 = a4[2];
    }
    while ( v9 < v10 );
  }
  hObject = 0;
  v12 = Common::AutoNoImpersonateDuringScope::DropImpersonation(&hObject);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F2,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
      (const char *)(unsigned int)v12,
      v44);
    Common::AutoNoImpersonateDuringScope::RestoreImpersonation((Common::AutoNoImpersonateDuringScope *)&hObject);
    v14 = (char *)hObject - 1;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    operator delete(v48, (unsigned __int64)v14);
    InvokeMRTMergeStop(L"MRT Deh");
    return (unsigned int)v13;
  }
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileAttributesExW(a2, GetFileExInfoStandard, FileInformation)
    || (v13 = 0, v15 = 0, !*(_QWORD *)&FileInformation[28]) )
  {
    v16 = MergeRelatedPriFiles(*((unsigned int *)a4 + 4), v8, 0, 0);
    v13 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x306,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
        (const char *)(unsigned int)v16,
        (int)a2);
      if ( (byte_1802E21C5 & 1) != 0 )
        McTemplateU0zqqdzz_EventWriteTransfer(
          (unsigned int)L"Unknown File",
          (unsigned int)&MrtDEHMergeFailure,
          (unsigned int)L"Merge failure for shared merged PRI file",
          0,
          0,
          v13,
          *(_QWORD *)(a1 + 80),
          (__int64)L"Unknown File");
      details::appxLog<unsigned short const *,int,int,long,unsigned short *,unsigned short const *>(
        (unsigned int)v13,
        v19,
        v20,
        L"Merge failure for shared merged PRI file");
      goto LABEL_50;
    }
    v15 = 1;
    if ( (byte_1802E21C5 & 2) != 0 )
      McTemplateU0zzz_EventWriteTransfer(
        v18,
        (unsigned int)MrtDEHCreatingPriFile,
        *(_QWORD *)(a1 + 80),
        (_DWORD)a2,
        (__int64)L"Created shared merged PRI file");
    v44 = (int)a2;
    details::appxLog<unsigned short *,unsigned short const *,unsigned short const *>(
      v18,
      v17,
      MrtDEHCreatingPriFile,
      *(_QWORD *)(a1 + 80));
  }
  if ( CreateHardLinkW(a3, a2, 0) )
  {
    if ( (byte_1802E21C5 & 2) != 0 )
      McTemplateU0zzz_EventWriteTransfer(
        v22,
        (unsigned int)&MrtDEHLinkingPriFile,
        *(_QWORD *)(a1 + 80),
        (_DWORD)a3,
        (__int64)L"Linked user-specific merged PRI file");
    v49 = L"Linked user-specific merged PRI file";
    v50 = a3;
    *(_QWORD *)v51 = *(_QWORD *)(a1 + 80);
    SetAppXErrorFromLogMessage(0, &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID, &MrtDEHLinkingPriFile, 3u, v51, &v50, &v49);
  }
  else
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    v25 = (int)retaddr;
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x323,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
        (const char *)(unsigned int)v13,
        v44);
    if ( (byte_1802E21C5 & 4) != 0 )
      McTemplateU0zzdz_EventWriteTransfer(
        v25,
        (unsigned int)&MrtDEHGenericWarning,
        *(_QWORD *)(a1 + 80),
        (_DWORD)a3,
        v13,
        (__int64)L"Unable to link shared merged PRI file to user-specific path");
    v45 = (int)a3;
    details::appxLog<_SID const *,unsigned short const *,unsigned short const *,long>(
      (unsigned int)v13,
      v24,
      &MrtDEHGenericWarning,
      *(_QWORD *)(a1 + 80));
    if ( v15 )
    {
      if ( MoveFileW(a2, a3) )
      {
        v13 = 0;
      }
      else
      {
        v27 = GetLastError();
        v13 = v27;
        if ( v27 > 0 )
          v13 = (unsigned __int16)v27 | 0x80070000;
      }
      v28 = (int)retaddr;
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x330,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
          (const char *)(unsigned int)v13,
          (int)a3);
      if ( (byte_1802E21C5 & 4) != 0 )
        McTemplateU0zzdz_EventWriteTransfer(
          v28,
          (unsigned int)MrtDEHMovingSharedPriFile,
          *(_QWORD *)(a1 + 80),
          (_DWORD)a3,
          v13,
          (__int64)L"Trying to move shared PRI to user specific PRI");
      v45 = (int)a3;
      details::appxLog<_SID const *,unsigned short const *,unsigned short const *,long>(
        (unsigned int)v13,
        v26,
        MrtDEHMovingSharedPriFile,
        *(_QWORD *)(a1 + 80));
    }
    if ( v13 >= 0 )
      goto LABEL_61;
    if ( CopyFileW(a2, a3, 0) )
    {
      v13 = 0;
    }
    else
    {
      v30 = GetLastError();
      v13 = v30;
      if ( v30 > 0 )
        v13 = (unsigned __int16)v30 | 0x80070000;
    }
    v31 = (int)retaddr;
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x33E,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
        (const char *)(unsigned int)v13,
        v45);
    if ( (byte_1802E21C5 & 4) != 0 )
      McTemplateU0zzdz_EventWriteTransfer(
        v31,
        (unsigned int)MrtDEHCopyingSharedPriFile,
        *(_QWORD *)(a1 + 80),
        (_DWORD)a3,
        v13,
        (__int64)L"Trying to copy shared PRI to user specific PRI");
    v45 = (int)a3;
    details::appxLog<_SID const *,unsigned short const *,unsigned short const *,long>(
      (unsigned int)v13,
      v29,
      MrtDEHCopyingSharedPriFile,
      *(_QWORD *)(a1 + 80));
  }
  if ( v13 >= 0 )
  {
LABEL_61:
    v33 = v48;
    goto LABEL_62;
  }
LABEL_50:
  v32 = (int)retaddr;
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35A,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
      (const char *)(unsigned int)v13,
      v45);
  if ( (byte_1802E21C5 & 4) != 0 )
    McTemplateU0zzdz_EventWriteTransfer(
      v32,
      (unsigned int)MrtDEHMergingToUserSpecificPriFile,
      *(_QWORD *)(a1 + 80),
      (_DWORD)a2,
      v13,
      (__int64)L"Trying to merge to user-specific merged PRI file");
  details::appxLog<_SID const *,unsigned short const *,unsigned short const *,long>(
    (unsigned int)v13,
    v21,
    MrtDEHMergingToUserSpecificPriFile,
    *(_QWORD *)(a1 + 80));
  v46 = (int)a3;
  v33 = v48;
  v34 = MergeRelatedPriFiles(*((unsigned int *)a4 + 4), v48, 0, 0);
  v13 = v34;
  if ( v34 >= 0 )
  {
    if ( (byte_1802E21C5 & 2) != 0 )
      McTemplateU0zzz_EventWriteTransfer(
        v36,
        (unsigned int)MrtDEHCreatingPriFile,
        *(_QWORD *)(a1 + 80),
        (_DWORD)a2,
        (__int64)L"Merged to user-specific merged PRI file");
    v45 = (int)a2;
    details::appxLog<unsigned short *,unsigned short const *,unsigned short const *>(
      v36,
      v35,
      MrtDEHCreatingPriFile,
      *(_QWORD *)(a1 + 80));
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x369,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
      (const char *)(unsigned int)v34,
      v46);
    if ( (byte_1802E21C5 & 1) != 0 )
      McTemplateU0zqqdzz_EventWriteTransfer(
        (unsigned int)L"Unknown File",
        (unsigned int)&MrtDEHMergeFailure,
        (unsigned int)L"Merge failure for user-specific merged PRI file",
        0,
        0,
        v13,
        *(_QWORD *)(a1 + 80),
        (__int64)L"Unknown File");
    details::appxLog<unsigned short const *,int,int,long,unsigned short *,unsigned short const *>(
      (unsigned int)v13,
      v37,
      v38,
      L"Merge failure for user-specific merged PRI file");
  }
LABEL_62:
  v39 = Common::AutoNoImpersonateDuringScope::RestoreImpersonation((Common::AutoNoImpersonateDuringScope *)&hObject);
  v40 = v39;
  if ( v39 >= 0 )
  {
    if ( v13 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x379,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
        (const char *)(unsigned int)v13,
        v45);
    Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&hObject);
    operator delete(v33, v43);
    MrtAutoLog::~MrtAutoLog((MrtAutoLog *)v52);
    return (unsigned int)v13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x377,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
    (const char *)(unsigned int)v39,
    v45);
  Common::AutoNoImpersonateDuringScope::RestoreImpersonation((Common::AutoNoImpersonateDuringScope *)&hObject);
  v41 = (char *)hObject - 1;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  operator delete(v33, (unsigned __int64)v41);
  InvokeMRTMergeStop(L"MRT Deh");
  return v40;
}

```

## disassembly

```asm
0x18002d794  push    rbp
0x18002d796  push    rbx
0x18002d797  push    rsi
0x18002d798  push    rdi
0x18002d799  push    r12
0x18002d79b  push    r13
0x18002d79d  push    r14
0x18002d79f  push    r15
0x18002d7a1  lea     rbp, [rsp-1Fh]
0x18002d7a6  sub     rsp, 0D8h
0x18002d7ad  mov     rax, cs:__security_cookie
0x18002d7b4  xor     rax, rsp
0x18002d7b7  mov     [rbp+57h+var_50], rax
0x18002d7bb  mov     rdi, r9
0x18002d7be  mov     r12, r8
0x18002d7c1  mov     r15, rdx
0x18002d7c4  mov     rsi, rcx
0x18002d7c7  lea     r13, aMrtDeh; "MRT Deh"
0x18002d7ce  mov     [rbp+57h+var_90], r13
0x18002d7d2  lea     rax, ?InvokeMRTMergeStart@@YAXPEBG@Z; InvokeMRTMergeStart(ushort const *)
0x18002d7d9  mov     [rbp+57h+var_88], rax
0x18002d7dd  lea     rax, ?InvokeMRTMergeStop@@YAXPEBG@Z; InvokeMRTMergeStop(ushort const *)
0x18002d7e4  mov     [rbp+57h+var_80], rax
0x18002d7e8  mov     rcx, r13; unsigned __int16 *
0x18002d7eb  call    ?InvokeMRTMergeStart@@YAXPEBG@Z; InvokeMRTMergeStart(ushort const *)
0x18002d7f0  nop
0x18002d7f1  mov     eax, 8
0x18002d7f6  mul     qword ptr [rdi+10h]
0x18002d7fa  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18002d801  cmovb   rax, rbx
0x18002d805  mov     rcx, rax; unsigned __int64
0x18002d808  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d80d  mov     r14, rax
0x18002d810  mov     [rbp+57h+var_B0], rax
0x18002d814  xor     edx, edx
0x18002d816  mov     r8, [rdi+10h]
0x18002d81a  test    r8, r8
0x18002d81d  jz      short loc_18002D84B
0x18002d81f  lea     rcx, ds:0[rdx*8]
0x18002d827  cmp     rdx, r8
0x18002d82a  jb      short loc_18002D830
0x18002d82c  xor     eax, eax
0x18002d82e  jmp     short loc_18002D837
0x18002d830  mov     rax, [rdi]
0x18002d833  mov     rax, [rcx+rax]
0x18002d837  mov     rax, [rax+8]
0x18002d83b  mov     [r14+rcx], rax
0x18002d83f  inc     rdx
0x18002d842  mov     r8, [rdi+10h]
0x18002d846  cmp     rdx, r8
0x18002d849  jb      short loc_18002D81F
0x18002d84b  mov     [rbp+57h+var_C0], ebx
0x18002d84e  mov     [rbp+57h+hObject], 0
0x18002d856  lea     rcx, [rbp+57h+hObject]; TokenHandle
0x18002d85a  call    ?DropImpersonation@AutoNoImpersonateDuringScope@Common@@QEAAJXZ; Common::AutoNoImpersonateDuringScope::DropImpersonation(void)
0x18002d85f  mov     ebx, eax
0x18002d861  test    eax, eax
0x18002d863  jns     short loc_18002D8B4
0x18002d865  mov     rcx, [rbp+5Fh]; this
0x18002d869  mov     r9d, eax; char *
0x18002d86c  lea     r8, aOnecoreAdminAp_34; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18002d873  mov     edx, 2F2h; void *
0x18002d878  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d87d  nop
0x18002d87e  lea     rcx, [rbp+57h+hObject]; this
0x18002d882  call    ?RestoreImpersonation@AutoNoImpersonateDuringScope@Common@@QEAAJXZ; Common::AutoNoImpersonateDuringScope::RestoreImpersonation(void)
0x18002d887  mov     rcx, [rbp+57h+hObject]; hObject
0x18002d88b  lea     rdx, [rcx-1]
0x18002d88f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002d893  ja      short loc_18002D89C
0x18002d895  call    cs:__imp_CloseHandle
0x18002d89b  nop
0x18002d89c  mov     rcx, [rbp+57h+var_B0]; void *
0x18002d8a0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d8a5  nop
0x18002d8a6  mov     rcx, r13; unsigned __int16 *
0x18002d8a9  call    ?InvokeMRTMergeStop@@YAXPEBG@Z; InvokeMRTMergeStop(ushort const *)
0x18002d8ae  nop
0x18002d8af  jmp     loc_18002DED2
0x18002d8b4  xorps   xmm0, xmm0
0x18002d8b7  xor     eax, eax
0x18002d8b9  movups  [rbp+57h+FileInformation], xmm0
0x18002d8bd  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18002d8c1  mov     dword ptr [rbp+57h+var_68+10h], eax
0x18002d8c4  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x18002d8c8  xor     edx, edx; fInfoLevelId
0x18002d8ca  mov     rcx, r15; lpFileName
0x18002d8cd  call    cs:__imp_GetFileAttributesExW
0x18002d8d3  lea     r13, aUnknownFile; "Unknown File"
0x18002d8da  test    eax, eax
0x18002d8dc  jz      short loc_18002D8FC
0x18002d8de  xor     ebx, ebx
0x18002d8e0  xor     r13b, r13b
0x18002d8e3  cmp     dword ptr [rbp+57h+var_68+0Ch], ebx
0x18002d8e6  jnz     loc_18002DA3E
0x18002d8ec  cmp     dword ptr [rbp+57h+var_68+10h], ebx
0x18002d8ef  jnz     loc_18002DA3E
0x18002d8f5  lea     r13, aUnknownFile; "Unknown File"
0x18002d8fc  lea     rax, [rbp+57h+var_C0]
0x18002d900  mov     [rsp+110h+var_E8], rax
0x18002d905  mov     qword ptr [rsp+110h+var_F0], r15; int
0x18002d90a  xor     r9d, r9d
0x18002d90d  xor     r8d, r8d
0x18002d910  mov     rdx, r14
0x18002d913  mov     ecx, [rdi+10h]
0x18002d916  call    cs:__imp_MergeRelatedPriFiles
0x18002d91c  mov     ebx, eax
0x18002d91e  test    eax, eax
0x18002d920  jns     loc_18002D9F9
0x18002d926  mov     rcx, [rbp+5Fh]; this
0x18002d92a  mov     r9d, eax; char *
0x18002d92d  lea     r14, aOnecoreAdminAp_34; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18002d934  mov     r8, r14; unsigned int
0x18002d937  mov     edx, 306h; void *
0x18002d93c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d941  test    cs:byte_1802E21C5, 1
0x18002d948  jz      short loc_18002D9A7
0x18002d94a  movsxd  rax, [rbp+57h+var_C0]
0x18002d94e  test    eax, eax
0x18002d950  js      short loc_18002D974
0x18002d952  cmp     eax, [rdi+10h]
0x18002d955  jge     short loc_18002D974
0x18002d957  mov     rcx, rax
0x18002d95a  cmp     rax, [rdi+10h]
0x18002d95e  jb      short loc_18002D964
0x18002d960  xor     eax, eax
0x18002d962  jmp     short loc_18002D96E
0x18002d964  lfence
0x18002d967  mov     rax, [rdi]
0x18002d96a  mov     rax, [rax+rcx*8]
0x18002d96e  mov     rcx, [rax+8]
0x18002d972  jmp     short loc_18002D977
0x18002d974  mov     rcx, r13
0x18002d977  mov     [rsp+110h+var_D8], rcx
0x18002d97c  mov     rax, [rsi+50h]
0x18002d980  mov     [rsp+110h+var_E0], rax
0x18002d985  mov     dword ptr [rsp+110h+var_E8], ebx
0x18002d989  mov     [rsp+110h+var_F0], 0
0x18002d991  xor     r9d, r9d
0x18002d994  lea     r8, aMergeFailureFo_0; "Merge failure for shared merged PRI fil"...
0x18002d99b  lea     rdx, MrtDEHMergeFailure
0x18002d9a2  call    McTemplateU0zqqdzz_EventWriteTransfer
0x18002d9a7  movsxd  rax, [rbp+57h+var_C0]
0x18002d9ab  test    eax, eax
0x18002d9ad  js      short loc_18002D9D1
0x18002d9af  cmp     eax, [rdi+10h]
0x18002d9b2  jge     short loc_18002D9D1
0x18002d9b4  mov     rcx, rax
0x18002d9b7  cmp     rax, [rdi+10h]
0x18002d9bb  jb      short loc_18002D9C1
0x18002d9bd  xor     eax, eax
0x18002d9bf  jmp     short loc_18002D9CB
0x18002d9c1  lfence
0x18002d9c4  mov     rax, [rdi]
0x18002d9c7  mov     rax, [rax+rcx*8]
0x18002d9cb  mov     rcx, [rax+8]
0x18002d9cf  jmp     short loc_18002D9D4
0x18002d9d1  mov     rcx, r13
0x18002d9d4  mov     [rsp+110h+var_D0], rcx
0x18002d9d9  mov     rax, [rsi+50h]
0x18002d9dd  mov     [rsp+110h+var_D8], rax
0x18002d9e2  mov     dword ptr [rsp+110h+var_E0], ebx
0x18002d9e6  lea     r9, aMergeFailureFo_0; "Merge failure for shared merged PRI fil"...
0x18002d9ed  mov     ecx, ebx
0x18002d9ef  call    ??$appxLog@PEBGHHJPEAGPEBG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGHHJPEAG2@Z; details::appxLog<ushort const *,int,int,long,ushort *,ushort const *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,int,int,long,ushort *,ushort const *)
0x18002d9f4  jmp     loc_18002DC82
0x18002d9f9  mov     r13b, 1
0x18002d9fc  lea     r14, aCreatedSharedM; "Created shared merged PRI file"
0x18002da03  test    cs:byte_1802E21C5, 2
0x18002da0a  jz      short loc_18002DA24
0x18002da0c  mov     qword ptr [rsp+110h+var_F0], r14
0x18002da11  mov     r9, r15
0x18002da14  mov     r8, [rsi+50h]
0x18002da18  lea     rdx, MrtDEHCreatingPriFile
0x18002da1f  call    McTemplateU0zzz_EventWriteTransfer
0x18002da24  mov     [rsp+110h+var_E8], r14
0x18002da29  mov     qword ptr [rsp+110h+var_F0], r15; int
0x18002da2e  mov     r9, [rsi+50h]
0x18002da32  lea     r8, MrtDEHCreatingPriFile
0x18002da39  call    ??$appxLog@PEAGPEBGPEBG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEAGPEBG3@Z; details::appxLog<ushort *,ushort const *,ushort const *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort *,ushort const *,ushort const *)
0x18002da3e  xor     r8d, r8d; lpSecurityAttributes
0x18002da41  mov     rdx, r15; lpExistingFileName
0x18002da44  mov     rcx, r12; lpFileName
0x18002da47  call    cs:__imp_CreateHardLinkW
0x18002da4d  lea     r14, aOnecoreAdminAp_34; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18002da54  test    eax, eax
0x18002da56  jnz     loc_18002DC0C
0x18002da5c  call    cs:__imp_GetLastError
0x18002da62  mov     ebx, eax
0x18002da64  test    eax, eax
0x18002da66  jle     short loc_18002DA71
0x18002da68  movzx   ebx, ax
0x18002da6b  or      ebx, 80070000h
0x18002da71  mov     rcx, [rbp+5Fh]; this
0x18002da75  test    ebx, ebx
0x18002da77  jns     short loc_18002DA89
0x18002da79  mov     r9d, ebx; char *
0x18002da7c  mov     r8, r14; unsigned int
0x18002da7f  mov     edx, 323h; void *
0x18002da84  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002da89  lea     rax, aUnableToLinkSh; "Unable to link shared merged PRI file t"...
0x18002da90  test    cs:byte_1802E21C5, 4
0x18002da97  jz      short loc_18002DABC
0x18002da99  mov     [rsp+110h+var_E8], rax
0x18002da9e  mov     [rsp+110h+var_F0], ebx
0x18002daa2  mov     r9, r12
0x18002daa5  mov     r8, [rsi+50h]
0x18002daa9  lea     rdx, MrtDEHGenericWarning
0x18002dab0  call    McTemplateU0zzdz_EventWriteTransfer
0x18002dab5  lea     rax, aUnableToLinkSh; "Unable to link shared merged PRI file t"...
0x18002dabc  mov     [rsp+110h+var_E0], rax
0x18002dac1  mov     dword ptr [rsp+110h+var_E8], ebx
0x18002dac5  mov     qword ptr [rsp+110h+var_F0], r12; int
0x18002daca  mov     r9, [rsi+50h]
0x18002dace  lea     r8, MrtDEHGenericWarning
0x18002dad5  mov     ecx, ebx
0x18002dad7  call    ??$appxLog@PEBU_SID@@PEBGPEBGJ@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBU_SID@@PEBG3J@Z; details::appxLog<_SID const *,ushort const *,ushort const *,long>(long,_GUID const &,_EVENT_DESCRIPTOR const &,_SID const *,ushort const *,ushort const *,long)
0x18002dadc  test    r13b, r13b
0x18002dadf  jz      loc_18002DB72
0x18002dae5  mov     rdx, r12; lpNewFileName
0x18002dae8  mov     rcx, r15; lpExistingFileName
0x18002daeb  call    cs:__imp_MoveFileW
0x18002daf1  test    eax, eax
0x18002daf3  jz      short loc_18002DAF9
0x18002daf5  xor     ebx, ebx
0x18002daf7  jmp     short loc_18002DB0E
0x18002daf9  call    cs:__imp_GetLastError
0x18002daff  mov     ebx, eax
0x18002db01  test    eax, eax
0x18002db03  jle     short loc_18002DB0E
0x18002db05  movzx   ebx, ax
0x18002db08  or      ebx, 80070000h
0x18002db0e  mov     rcx, [rbp+5Fh]; this
0x18002db12  test    ebx, ebx
0x18002db14  jns     short loc_18002DB26
0x18002db16  mov     r9d, ebx; char *
0x18002db19  mov     r8, r14; unsigned int
0x18002db1c  mov     edx, 330h; void *
0x18002db21  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002db26  lea     r13, aTryingToMoveSh; "Trying to move shared PRI to user speci"...
0x18002db2d  test    cs:byte_1802E21C5, 4
0x18002db34  jz      short loc_18002DB52
0x18002db36  mov     [rsp+110h+var_E8], r13
0x18002db3b  mov     [rsp+110h+var_F0], ebx
0x18002db3f  mov     r9, r12
0x18002db42  mov     r8, [rsi+50h]
0x18002db46  lea     rdx, MrtDEHMovingSharedPriFile
0x18002db4d  call    McTemplateU0zzdz_EventWriteTransfer
0x18002db52  mov     [rsp+110h+var_E0], r13
0x18002db57  mov     dword ptr [rsp+110h+var_E8], ebx
0x18002db5b  mov     qword ptr [rsp+110h+var_F0], r12; int
0x18002db60  mov     r9, [rsi+50h]
0x18002db64  lea     r8, MrtDEHMovingSharedPriFile
0x18002db6b  mov     ecx, ebx
0x18002db6d  call    ??$appxLog@PEBU_SID@@PEBGPEBGJ@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBU_SID@@PEBG3J@Z; details::appxLog<_SID const *,ushort const *,ushort const *,long>(long,_GUID const &,_EVENT_DESCRIPTOR const &,_SID const *,ushort const *,ushort const *,long)
0x18002db72  test    ebx, ebx
0x18002db74  jns     loc_18002DE3D
0x18002db7a  xor     r8d, r8d; bFailIfExists
0x18002db7d  mov     rdx, r12; lpNewFileName
0x18002db80  mov     rcx, r15; lpExistingFileName
0x18002db83  call    cs:__imp_CopyFileW
0x18002db89  test    eax, eax
0x18002db8b  jz      short loc_18002DB91
0x18002db8d  xor     ebx, ebx
0x18002db8f  jmp     short loc_18002DBA6
0x18002db91  call    cs:__imp_GetLastError
0x18002db97  mov     ebx, eax
0x18002db99  test    eax, eax
0x18002db9b  jle     short loc_18002DBA6
0x18002db9d  movzx   ebx, ax
0x18002dba0  or      ebx, 80070000h
0x18002dba6  mov     rcx, [rbp+5Fh]; this
0x18002dbaa  test    ebx, ebx
0x18002dbac  jns     short loc_18002DBBE
0x18002dbae  mov     r9d, ebx; char *
0x18002dbb1  mov     r8, r14; unsigned int
0x18002dbb4  mov     edx, 33Eh; void *
0x18002dbb9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002dbbe  lea     r13, aTryingToCopySh; "Trying to copy shared PRI to user speci"...
0x18002dbc5  test    cs:byte_1802E21C5, 4
0x18002dbcc  jz      short loc_18002DBEA
0x18002dbce  mov     [rsp+110h+var_E8], r13
0x18002dbd3  mov     [rsp+110h+var_F0], ebx
0x18002dbd7  mov     r9, r12
0x18002dbda  mov     r8, [rsi+50h]
0x18002dbde  lea     rdx, MrtDEHCopyingSharedPriFile
0x18002dbe5  call    McTemplateU0zzdz_EventWriteTransfer
0x18002dbea  mov     [rsp+110h+var_E0], r13
0x18002dbef  mov     dword ptr [rsp+110h+var_E8], ebx
0x18002dbf3  mov     qword ptr [rsp+110h+var_F0], r12
0x18002dbf8  mov     r9, [rsi+50h]
0x18002dbfc  lea     r8, MrtDEHCopyingSharedPriFile
0x18002dc03  mov     ecx, ebx
0x18002dc05  call    ??$appxLog@PEBU_SID@@PEBGPEBGJ@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBU_SID@@PEBG3J@Z; details::appxLog<_SID const *,ushort const *,ushort const *,long>(long,_GUID const &,_EVENT_DESCRIPTOR const &,_SID const *,ushort const *,ushort const *,long)
0x18002dc0a  jmp     short loc_18002DC7A
0x18002dc0c  lea     r13, aLinkedUserSpec; "Linked user-specific merged PRI file"
0x18002dc13  test    cs:byte_1802E21C5, 2
0x18002dc1a  jz      short loc_18002DC34
0x18002dc1c  mov     qword ptr [rsp+110h+var_F0], r13
0x18002dc21  mov     r9, r12
  ... truncated ...
```
