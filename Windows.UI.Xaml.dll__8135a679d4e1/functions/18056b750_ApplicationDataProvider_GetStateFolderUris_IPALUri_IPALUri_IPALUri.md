# ApplicationDataProvider::GetStateFolderUris(IPALUri * *,IPALUri * *,IPALUri * *)

- ea: `0x18056b750`
- end: `0x18056bb1e`
- name: `?GetStateFolderUris@ApplicationDataProvider@@CAJPEAPEAUIPALUri@@00@Z`
- size: `974`
- prototype: `HRESULT __fastcall(IPALUri **ppLocalFolder, IPALUri **ppRoamingFolder, IPALUri **ppTempFolder)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18056b6f8`

## callees

- `0x180004bc0`
- `0x18056b750`
- `0x180687a78`
- `0x18076e110`
- `0x18076f0a4`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18056b9f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18056ba30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18056ba60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18056ba86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18056b9f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18056ba30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18056ba60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18056ba86`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x18056b7f2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x18056b879`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x18056b992`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x18056b7f2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x18056b879`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x18056b992`
- `api-ms-win-appmodel-state-l1-2-0!OpenState` at `0x18056b7b5`
- `api-ms-win-appmodel-state-l1-2-0!OpenState` at `0x18056b7b5`
- `api-ms-win-appmodel-state-l1-2-0!GetStateFolder` at `0x18056b7df`
- `api-ms-win-appmodel-state-l1-2-0!GetStateFolder` at `0x18056b866`
- `api-ms-win-appmodel-state-l1-2-0!GetStateFolder` at `0x18056b97f`
- `api-ms-win-appmodel-state-l1-2-0!GetStateFolder` at `0x18056b7df`
- `api-ms-win-appmodel-state-l1-2-0!GetStateFolder` at `0x18056b866`
- `api-ms-win-appmodel-state-l1-2-0!GetStateFolder` at `0x18056b97f`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18056b933`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18056b933`

## pseudocode

```c
__int64 __fastcall ApplicationDataProvider::GetStateFolderUris(
        IPALUri **ppLocalFolder,
        IPALUri **ppRoamingFolder,
        IPALUri **ppTempFolder)
{
  __int64 v6; // rdi
  HRESULT v7; // ecx
  wchar_t *v8; // rdx
  HRESULT v10; // eax
  HRESULT v11; // ebx
  wchar_t *v12; // rdx
  wchar_t *v15; // rdx
  signed int LastError; // eax
  signed int v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  unsigned int cSpecialFolderPath; // [rsp+30h] [rbp-D0h] BYREF
  IPALUri *pLocalFolder; // [rsp+38h] [rbp-C8h] BYREF
  IPALUri *pRoamingFolder; // [rsp+40h] [rbp-C0h] BYREF
  IPALUri *pTempFolder; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t specialFolderPath[264]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(specialFolderPath, 0, 0x208u);
  cSpecialFolderPath = 260;
  pLocalFolder = 0;
  pRoamingFolder = 0;
  pTempFolder = 0;
  v6 = OpenState();
  if ( !v6 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError == 15700 || LastError == 5 )
    {
      v11 = 0;
      goto $Cleanup_4179;
    }
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 < 0 )
    {
      OnFailure_2990_(v11);
      goto $Cleanup_4179;
    }
  }
  if ( !(unsigned int)GetStateFolder(v6, 1, specialFolderPath, &cSpecialFolderPath) )
  {
    v19 = GetLastError();
    v11 = v19;
    if ( v19 > 0 )
      v11 = (unsigned __int16)v19 | 0x80070000;
    if ( v11 < 0 )
      goto LABEL_47;
  }
  if ( PathAddBackslashW(specialFolderPath) )
  {
    v8 = specialFolderPath;
    while ( *v8++ )
      ;
    v10 = gps.m_pTarget->UriCreate(
            &gps.m_pTarget->IPALURIServices,
            (unsigned int)(v8 - specialFolderPath) - 1,
            specialFolderPath,
            &pLocalFolder);
    v11 = v10;
    if ( v10 < 0 )
      goto LABEL_12;
    cSpecialFolderPath = 260;
    if ( !(unsigned int)GetStateFolder(v6, 2, specialFolderPath, &cSpecialFolderPath) )
    {
      v20 = GetLastError();
      v11 = v20;
      if ( v20 > 0 )
        v11 = (unsigned __int16)v20 | 0x80070000;
      if ( v11 < 0 )
        goto LABEL_47;
    }
    if ( PathAddBackslashW(specialFolderPath) )
    {
      v12 = specialFolderPath;
      while ( *v12++ )
        ;
      v10 = gps.m_pTarget->UriCreate(
              &gps.m_pTarget->IPALURIServices,
              (unsigned int)(v12 - specialFolderPath) - 1,
              specialFolderPath,
              &pRoamingFolder);
      v11 = v10;
      if ( v10 < 0 )
      {
LABEL_12:
        OnFailure_2990_(v10);
        goto $Cleanup_4179;
      }
      cSpecialFolderPath = 260;
      if ( !(unsigned int)GetStateFolder(v6, 3, specialFolderPath, &cSpecialFolderPath) )
      {
        v18 = GetLastError();
        v11 = v18;
        if ( v18 > 0 )
          v11 = (unsigned __int16)v18 | 0x80070000;
        if ( v11 < 0 )
        {
LABEL_47:
          OnFailure_2990_(v11);
          goto $Cleanup_4179;
        }
      }
      if ( PathAddBackslashW(specialFolderPath) )
      {
        v15 = specialFolderPath;
        while ( *v15++ )
          ;
        v10 = gps.m_pTarget->UriCreate(
                &gps.m_pTarget->IPALURIServices,
                (unsigned int)(v15 - specialFolderPath) - 1,
                specialFolderPath,
                &pTempFolder);
        v11 = v10;
        if ( v10 >= 0 )
        {
          *ppLocalFolder = pLocalFolder;
          *ppRoamingFolder = pRoamingFolder;
          *ppTempFolder = pTempFolder;
          pLocalFolder = 0;
          pRoamingFolder = 0;
          goto LABEL_19;
        }
        goto LABEL_12;
      }
    }
  }
  v11 = -2147467259;
  OnFailure_977_(v7);
$Cleanup_4179:
  if ( pLocalFolder )
  {
    pLocalFolder->Release(pLocalFolder);
    pLocalFolder = 0;
  }
  if ( pRoamingFolder )
  {
    pRoamingFolder->Release(pRoamingFolder);
    pRoamingFolder = 0;
  }
  if ( pTempFolder )
  {
    pTempFolder->Release(pTempFolder);
LABEL_19:
    pTempFolder = 0;
  }
  if ( v6 )
    CloseState(v6);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18056b750  mov     [rsp-8+arg_18], rbx
0x18056b755  push    rbp
0x18056b756  push    rsi
0x18056b757  push    rdi
0x18056b758  push    r12
0x18056b75a  push    r13
0x18056b75c  push    r14
0x18056b75e  push    r15
0x18056b760  lea     rbp, [rsp-170h]
0x18056b768  sub     rsp, 270h
0x18056b76f  mov     rax, cs:__security_cookie
0x18056b776  xor     rax, rsp
0x18056b779  mov     [rbp+1A0h+var_40], rax
0x18056b780  mov     r15, ppTempFolder
0x18056b783  mov     r14, ppRoamingFolder
0x18056b786  mov     rsi, ppLocalFolder
0x18056b789  xor     edx, edx; Val
0x18056b78b  mov     r8d, 208h; Size
0x18056b791  lea     ppLocalFolder, [rsp+2A0h+specialFolderPath]; void *
0x18056b796  call    memset_0
0x18056b79b  xor     r12d, r12d
0x18056b79e  mov     [rsp+2A0h+cSpecialFolderPath], 104h
0x18056b7a6  mov     [rsp+2A0h+pLocalFolder], r12
0x18056b7ab  mov     [rsp+2A0h+pRoamingFolder], r12
0x18056b7b0  mov     [rsp+2A0h+pTempFolder], r12
0x18056b7b5  call    cs:__imp_OpenState
0x18056b7bb  mov     rdi, rax
0x18056b7be  mov     r13d, 80070000h
0x18056b7c4  test    rax, rax
0x18056b7c7  jz      loc_18056B9F8
0x18056b7cd  lea     r9, [rsp+2A0h+cSpecialFolderPath]
0x18056b7d2  mov     edx, 1
0x18056b7d7  lea     ppTempFolder, [rsp+2A0h+specialFolderPath]
0x18056b7dc  mov     ppLocalFolder, rdi
0x18056b7df  call    cs:__imp_GetStateFolder
0x18056b7e5  test    eax, eax
0x18056b7e7  jz      loc_18056BA60
0x18056b7ed  lea     ppLocalFolder, [rsp+2A0h+specialFolderPath]; pszPath
0x18056b7f2  call    cs:__imp_PathAddBackslashW
0x18056b7f8  test    rax, rax
0x18056b7fb  jz      loc_18056BABF
0x18056b801  mov     ppLocalFolder, cs:?gps@@3V?$EncodedPtr@UIPlatformServices@@@@A.m_pTarget; EncodedPtr<IPlatformServices> gps ...
0x18056b808  lea     ppRoamingFolder, [rsp+2A0h+specialFolderPath]
0x18056b80d  add     ppLocalFolder, 10h
0x18056b811  mov     rax, [ppLocalFolder]
0x18056b814  mov     r10, [rax]
0x18056b817  movzx   eax, word ptr [ppRoamingFolder]
0x18056b81a  add     ppRoamingFolder, 2
0x18056b81e  test    ax, ax
0x18056b821  jnz     short loc_18056B817
0x18056b823  lea     rax, [rsp+2A0h+specialFolderPath]
0x18056b828  sub     ppRoamingFolder, rax
0x18056b82b  lea     r9, [rsp+2A0h+pLocalFolder]
0x18056b830  sar     ppRoamingFolder, 1
0x18056b833  lea     ppTempFolder, [rsp+2A0h+specialFolderPath]
0x18056b838  dec     edx
0x18056b83a  mov     rax, r10
0x18056b83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18056b842  mov     ebx, eax
0x18056b844  test    eax, eax
0x18056b846  js      loc_18056BA54
0x18056b84c  lea     r9, [rsp+2A0h+cSpecialFolderPath]
0x18056b851  mov     [rsp+2A0h+cSpecialFolderPath], 104h
0x18056b859  lea     ppTempFolder, [rsp+2A0h+specialFolderPath]
0x18056b85e  mov     edx, 2
0x18056b863  mov     ppLocalFolder, rdi
0x18056b866  call    cs:__imp_GetStateFolder
0x18056b86c  test    eax, eax
0x18056b86e  jz      loc_18056BA86
0x18056b874  lea     ppLocalFolder, [rsp+2A0h+specialFolderPath]; pszPath
0x18056b879  call    cs:__imp_PathAddBackslashW
0x18056b87f  test    rax, rax
0x18056b882  jz      loc_18056BACE
0x18056b888  mov     ppLocalFolder, cs:?gps@@3V?$EncodedPtr@UIPlatformServices@@@@A.m_pTarget; EncodedPtr<IPlatformServices> gps ...
0x18056b88f  lea     ppRoamingFolder, [rsp+2A0h+specialFolderPath]
0x18056b894  add     ppLocalFolder, 10h
0x18056b898  mov     rax, [ppLocalFolder]
0x18056b89b  mov     r10, [rax]
0x18056b89e  movzx   eax, word ptr [ppRoamingFolder]
0x18056b8a1  add     ppRoamingFolder, 2
0x18056b8a5  test    ax, ax
0x18056b8a8  jnz     short loc_18056B89E
0x18056b8aa  lea     rax, [rsp+2A0h+specialFolderPath]
0x18056b8af  sub     ppRoamingFolder, rax
0x18056b8b2  lea     r9, [rsp+2A0h+pRoamingFolder]
0x18056b8b7  sar     ppRoamingFolder, 1
0x18056b8ba  lea     ppTempFolder, [rsp+2A0h+specialFolderPath]
0x18056b8bf  dec     edx
0x18056b8c1  mov     rax, r10
0x18056b8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18056b8c9  mov     ebx, eax
0x18056b8cb  test    eax, eax
0x18056b8cd  jns     loc_18056B965
0x18056b8d3  mov     ecx, eax; failedFrameHR
0x18056b8d5  call    OnFailure_2990_
0x18056b8da  mov     ppLocalFolder, [rsp+2A0h+pLocalFolder]
0x18056b8df  test    ppLocalFolder, ppLocalFolder
0x18056b8e2  jz      short loc_18056B8F5
0x18056b8e4  mov     rax, [ppLocalFolder]
0x18056b8e7  mov     rax, [rax+10h]
0x18056b8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18056b8f0  mov     [rsp+2A0h+pLocalFolder], r12
0x18056b8f5  mov     ppLocalFolder, [rsp+2A0h+pRoamingFolder]
0x18056b8fa  test    ppLocalFolder, ppLocalFolder
0x18056b8fd  jz      short loc_18056B910
0x18056b8ff  mov     rax, [ppLocalFolder]
0x18056b902  mov     rax, [rax+10h]
0x18056b906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18056b90b  mov     [rsp+2A0h+pRoamingFolder], r12
0x18056b910  mov     ppLocalFolder, [rsp+2A0h+pTempFolder]
0x18056b915  test    ppLocalFolder, ppLocalFolder
0x18056b918  jz      short loc_18056B92B
0x18056b91a  mov     rax, [ppLocalFolder]
0x18056b91d  mov     rax, [rax+10h]
0x18056b921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18056b926  mov     [rsp+2A0h+pTempFolder], r12
0x18056b92b  test    rdi, rdi
0x18056b92e  jz      short loc_18056B939
0x18056b930  mov     ppLocalFolder, rdi
0x18056b933  call    cs:__imp_CloseState
0x18056b939  mov     eax, ebx
0x18056b93b  mov     ppLocalFolder, [rbp+1A0h+var_40]
0x18056b942  xor     ppLocalFolder, rsp; StackCookie
0x18056b945  call    __security_check_cookie
0x18056b94a  mov     rbx, [rsp+2A0h+arg_18]
0x18056b952  add     rsp, 270h
0x18056b959  pop     r15
0x18056b95b  pop     r14
0x18056b95d  pop     r13
0x18056b95f  pop     r12
0x18056b961  pop     rdi
0x18056b962  pop     rsi
0x18056b963  pop     rbp
0x18056b964  retn
0x18056b965  lea     r9, [rsp+2A0h+cSpecialFolderPath]
0x18056b96a  mov     [rsp+2A0h+cSpecialFolderPath], 104h
0x18056b972  lea     ppTempFolder, [rsp+2A0h+specialFolderPath]
0x18056b977  mov     edx, 3
0x18056b97c  mov     ppLocalFolder, rdi
0x18056b97f  call    cs:__imp_GetStateFolder
0x18056b985  test    eax, eax
0x18056b987  jz      loc_18056BA30
0x18056b98d  lea     ppLocalFolder, [rsp+2A0h+specialFolderPath]; pszPath
0x18056b992  call    cs:__imp_PathAddBackslashW
0x18056b998  test    rax, rax
0x18056b99b  jz      loc_18056BAE8
0x18056b9a1  mov     ppLocalFolder, cs:?gps@@3V?$EncodedPtr@UIPlatformServices@@@@A.m_pTarget; EncodedPtr<IPlatformServices> gps ...
0x18056b9a8  lea     ppRoamingFolder, [rsp+2A0h+specialFolderPath]
0x18056b9ad  add     ppLocalFolder, 10h
0x18056b9b1  mov     rax, [ppLocalFolder]
0x18056b9b4  mov     r10, [rax]
0x18056b9b7  movzx   eax, word ptr [ppRoamingFolder]
0x18056b9ba  add     ppRoamingFolder, 2
0x18056b9be  test    ax, ax
0x18056b9c1  jnz     short loc_18056B9B7
0x18056b9c3  lea     rax, [rsp+2A0h+specialFolderPath]
0x18056b9c8  sub     ppRoamingFolder, rax
0x18056b9cb  lea     r9, [rsp+2A0h+pTempFolder]
0x18056b9d0  sar     ppRoamingFolder, 1
0x18056b9d3  lea     ppTempFolder, [rsp+2A0h+specialFolderPath]
0x18056b9d8  dec     edx
0x18056b9da  mov     rax, r10
0x18056b9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18056b9e2  mov     ebx, eax
0x18056b9e4  test    eax, eax
0x18056b9e6  jns     loc_18056BAF7
0x18056b9ec  mov     ecx, eax; failedFrameHR
0x18056b9ee  call    OnFailure_2990_
0x18056b9f3  jmp     $Cleanup_4179
0x18056b9f8  call    cs:__imp_GetLastError
0x18056b9fe  mov     ebx, eax
0x18056ba00  cmp     eax, 3D54h
0x18056ba05  jz      loc_18056BAB7
0x18056ba0b  cmp     eax, 5
0x18056ba0e  jz      loc_18056BAB7
0x18056ba14  test    eax, eax
0x18056ba16  jg      loc_18056BAAC
0x18056ba1c  test    ebx, ebx
0x18056ba1e  jns     loc_18056B7CD
0x18056ba24  mov     ecx, ebx; failedFrameHR
0x18056ba26  call    OnFailure_2990_
0x18056ba2b  jmp     $Cleanup_4179
0x18056ba30  call    cs:__imp_GetLastError
0x18056ba36  mov     ebx, eax
0x18056ba38  test    eax, eax
0x18056ba3a  jg      loc_18056BADD
0x18056ba40  test    ebx, ebx
0x18056ba42  jns     loc_18056B98D
0x18056ba48  mov     ecx, ebx; failedFrameHR
0x18056ba4a  call    OnFailure_2990_
0x18056ba4f  jmp     $Cleanup_4179
0x18056ba54  mov     ecx, eax; failedFrameHR
0x18056ba56  call    OnFailure_2990_
0x18056ba5b  jmp     $Cleanup_4179
0x18056ba60  call    cs:__imp_GetLastError
0x18056ba66  mov     ebx, eax
0x18056ba68  test    eax, eax
0x18056ba6a  jle     short loc_18056BA72
0x18056ba6c  movzx   ebx, ax
0x18056ba6f  or      ebx, r13d
0x18056ba72  test    ebx, ebx
0x18056ba74  jns     loc_18056B7ED
0x18056ba7a  mov     ecx, ebx; failedFrameHR
0x18056ba7c  call    OnFailure_2990_
0x18056ba81  jmp     $Cleanup_4179
0x18056ba86  call    cs:__imp_GetLastError
0x18056ba8c  mov     ebx, eax
0x18056ba8e  test    eax, eax
0x18056ba90  jle     short loc_18056BA98
0x18056ba92  movzx   ebx, ax
0x18056ba95  or      ebx, r13d
0x18056ba98  test    ebx, ebx
0x18056ba9a  jns     loc_18056B874
0x18056baa0  mov     ecx, ebx; failedFrameHR
0x18056baa2  call    OnFailure_2990_
0x18056baa7  jmp     $Cleanup_4179
0x18056baac  movzx   ebx, ax
0x18056baaf  or      ebx, r13d
0x18056bab2  jmp     loc_18056BA1C
0x18056bab7  mov     ebx, r12d
0x18056baba  jmp     $Cleanup_4179
0x18056babf  mov     ebx, 80004005h
0x18056bac4  call    OnFailure_977_
0x18056bac9  jmp     $Cleanup_4179
0x18056bace  mov     ebx, 80004005h
0x18056bad3  call    OnFailure_977_
0x18056bad8  jmp     $Cleanup_4179
0x18056badd  movzx   ebx, ax
0x18056bae0  or      ebx, r13d
0x18056bae3  jmp     loc_18056BA40
0x18056bae8  mov     ebx, 80004005h
0x18056baed  call    OnFailure_977_
0x18056baf2  jmp     $Cleanup_4179
0x18056baf7  mov     rax, [rsp+2A0h+pLocalFolder]
0x18056bafc  mov     [rsi], rax
0x18056baff  mov     rax, [rsp+2A0h+pRoamingFolder]
0x18056bb04  mov     [r14], rax
0x18056bb07  mov     rax, [rsp+2A0h+pTempFolder]
0x18056bb0c  mov     [r15], rax
0x18056bb0f  mov     [rsp+2A0h+pLocalFolder], r12
0x18056bb14  mov     [rsp+2A0h+pRoamingFolder], r12
0x18056bb19  jmp     loc_18056B926
```
