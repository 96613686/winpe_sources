# CLinkResolver::Resolve(HWND__ *,ushort const *,ushort const *)

- ea: `0x180603944`
- end: `0x180603d34`
- name: `?Resolve@CLinkResolver@@QEAAHPEAUHWND__@@PEBG1@Z`
- size: `1008`
- prototype: `__int64 __fastcall(LPARAM this, HWND hWndParent, LPCWSTR pszPath, LPCWSTR)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x18007e9b8`

## callees

- `0x180024490`
- `0x1800a3080`
- `0x1801ae9bc`
- `0x18021dbd0`
- `0x1802713ac`
- `0x1802a3c10`
- `0x18030bf4c`
- `0x1803a4cb0`
- `0x180517614`
- `0x180601884`
- `0x18060194c`
- `0x180603944`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1806039fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1806039fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180603a08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180603a08`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18060399a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18060399a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x180603987`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x180603987`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180603994`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180603994`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180603a8b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180603af6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180603b23`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180603b79`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180603ba2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180603a8b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180603af6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180603b23`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180603b79`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180603ba2`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThreadWithHandle` at `0x1806039e6`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThreadWithHandle` at `0x1806039e6`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x180603b54`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x180603bd6`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x180603b54`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x180603bd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLinkResolver::Resolve(LPARAM this, HWND hWndParent, LPCWSTR pszPath, LPCWSTR a4)
{
  WCHAR *v8; // rbx
  DWORD TimeOut; // eax
  unsigned int v10; // ebx
  HINSTANCE v11; // rax
  int v12; // ecx
  int v13; // eax
  LPWSTR FileNameW; // rbx
  HINSTANCE v15; // rax
  __int64 v16; // r8
  HINSTANCE v17; // rax
  __int64 v18; // r8
  LPWSTR v19; // rbx
  HINSTANCE v20; // rax
  int v21; // eax
  LPWSTR v22; // rbx
  HINSTANCE v23; // rax
  __int64 v24; // rbx
  HINSTANCE v25; // rax
  __int64 v26; // rdx
  _OWORD *v27; // rax
  _OWORD *v28; // rsi
  __int64 v29; // rcx
  int pHandle; // [rsp+20h] [rbp-50h]
  __int64 v32; // [rsp+40h] [rbp-30h] BYREF
  HANDLE hHandle; // [rsp+48h] [rbp-28h] BYREF
  LPARAM v34; // [rsp+50h] [rbp-20h] BYREF
  LPARAM v35; // [rsp+58h] [rbp-18h]
  LPCWSTR v36; // [rsp+60h] [rbp-10h]

  v8 = (WCHAR *)(this + 2036);
  StringCchCopyW((unsigned __int16 *)(this + 2036), 0x104u, pszPath);
  if ( !PathIsRootW(v8) )
    PathRemoveFileSpecW(v8);
  *(_DWORD *)(this + 824) = GetTickCount();
  v32 = 0;
  if ( (*(_DWORD *)(this + 2032) & 0x101) == 1 )
  {
    hHandle = 0;
    _InterlockedIncrement((volatile signed __int32 *)(this + 16));
    if ( !SHCreateThreadWithHandle(
            lambda_469cb8603dcf52f8cda9d5d6a8068e20_::_lambda_invoker_cdecl_,
            (void *)this,
            0x218u,
            0,
            &hHandle) )
    {
      v10 = 2;
      CBaseTreeWalkerCB::Release((CBaseTreeWalkerCB *)(this + 8));
      goto LABEL_38;
    }
    TimeOut = CLinkResolver::_GetTimeOut((CLinkResolver *)this);
    WaitForSingleObject(hHandle, TimeOut);
    CloseHandle(hHandle);
    *(_BYTE *)(this + 828) = 0;
    v10 = 1;
  }
  else
  {
    v11 = Shell32Instance::get((Shell32Instance *)&v32);
    v10 = SHFusionDialogBoxParam(v11, (LPCWSTR)0x3EC, hWndParent, (DLGPROC)CLinkResolver::_DlgProc, this);
    if ( v10 != 1 )
      goto LABEL_38;
  }
  v12 = *(_DWORD *)(this + 840);
  if ( v12 >= 40 )
  {
    if ( !(unsigned int)PathIsUnderWinsxs((LPCWCH)(this + 888)) )
      goto LABEL_38;
    if ( (*(_BYTE *)(this + 2032) & 1) != 0 )
      goto LABEL_35;
    v34 = (LPARAM)pszPath;
    v35 = this + 888;
    v36 = a4;
    v25 = Shell32Instance::get((Shell32Instance *)&v32);
    v26 = 1009;
LABEL_37:
    v10 = SHFusionDialogBoxParam(v25, (LPCWSTR)v26, hWndParent, (DLGPROC)DeadLinkProc, (LPARAM)&v34);
    goto LABEL_38;
  }
  v13 = *(_DWORD *)(this + 2032);
  if ( (v13 & 1) != 0 )
  {
LABEL_35:
    v10 = 2;
    goto LABEL_38;
  }
  if ( (*(_BYTE *)(this + 48) & 1) != 0 )
  {
    if ( a4 )
      FileNameW = PathFindFileNameW(a4);
    else
      FileNameW = (LPWSTR)&c_szNULL;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
    {
      v15 = Shell32Instance::get((Shell32Instance *)&v32);
      v16 = 4215;
LABEL_22:
      MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const____1(
        v15,
        hWndParent,
        (LPCWSTR)v16,
        pHandle,
        (__int64)FileNameW);
      goto LABEL_35;
    }
    v17 = Shell32Instance::get((Shell32Instance *)&v32);
    v18 = 4215;
    goto LABEL_24;
  }
  if ( a4 || (v13 & 0x200) != 0 )
  {
    v34 = (LPARAM)pszPath;
    v35 = this + 888;
    v36 = a4;
    if ( *(_DWORD *)(this + 1436) )
      v24 = 1006;
    else
      v24 = (v12 <= 10) + 1008LL;
    v25 = Shell32Instance::get((Shell32Instance *)&v32);
    v26 = v24;
    goto LABEL_37;
  }
  if ( v12 <= 10 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
    {
      FileNameW = PathFindFileNameW(pszPath);
      v15 = Shell32Instance::get((Shell32Instance *)&v32);
      v16 = 4211;
      goto LABEL_22;
    }
    FileNameW = PathFindFileNameW(pszPath);
    v17 = Shell32Instance::get((Shell32Instance *)&v32);
    v18 = 4211;
LABEL_24:
    ShellMessageBoxW(v17, hWndParent, (LPCWSTR)v18, (LPCWSTR)0x1070, 0x30u, FileNameW);
    goto LABEL_35;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
  {
    v19 = PathFindFileNameW(pszPath);
    v20 = Shell32Instance::get((Shell32Instance *)&v32);
    v21 = MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const___unsigned_short___(
            v20,
            hWndParent,
            pHandle,
            (__int64)v19,
            this + 888);
  }
  else
  {
    v22 = PathFindFileNameW(pszPath);
    v23 = Shell32Instance::get((Shell32Instance *)&v32);
    v21 = ShellMessageBoxW(v23, hWndParent, (LPCWSTR)0x1074, (LPCWSTR)0x1070, 0x34u, v22, this + 888);
  }
  v10 = (v21 != 6) + 1;
LABEL_38:
  v27 = (_OWORD *)(this + 232);
  v28 = (_OWORD *)(this + 844);
  v29 = 4;
  do
  {
    *v27 = *v28;
    v27[1] = v28[1];
    v27[2] = v28[2];
    v27[3] = v28[3];
    v27[4] = v28[4];
    v27[5] = v28[5];
    v27[6] = v28[6];
    v27[7] = v28[7];
    v27 += 8;
    v28 += 8;
    --v29;
  }
  while ( v29 );
  *v27 = *v28;
  v27[1] = v28[1];
  v27[2] = v28[2];
  v27[3] = v28[3];
  v27[4] = v28[4];
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v32);
  return v10;
}

```

## disassembly

```asm
0x180603944  push    rbp
0x180603946  push    rbx
0x180603947  push    rsi
0x180603948  push    rdi
0x180603949  push    r12
0x18060394b  push    r14
0x18060394d  push    r15
0x18060394f  mov     rbp, rsp
0x180603952  sub     rsp, 70h
0x180603956  mov     rax, cs:__security_cookie
0x18060395d  xor     rax, rsp
0x180603960  mov     [rbp+var_8], rax
0x180603964  mov     rdi, r9
0x180603967  mov     r15, r8
0x18060396a  mov     r14, rdx
0x18060396d  mov     rsi, rcx
0x180603970  lea     rbx, [rcx+7F4h]
0x180603977  mov     edx, 104h; unsigned __int64
0x18060397c  mov     rcx, rbx; unsigned __int16 *
0x18060397f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180603984  mov     rcx, rbx; pszPath
0x180603987  call    cs:__imp_PathIsRootW
0x18060398d  test    eax, eax
0x18060398f  jnz     short loc_18060399A
0x180603991  mov     rcx, rbx; pszPath
0x180603994  call    cs:__imp_PathRemoveFileSpecW
0x18060399a  call    cs:__imp_GetTickCount
0x1806039a0  mov     [rsi+338h], eax
0x1806039a6  mov     [rbp+var_30], 0
0x1806039ae  mov     eax, [rsi+7F0h]
0x1806039b4  and     eax, 101h
0x1806039b9  cmp     eax, 1
0x1806039bc  jnz     short loc_180603A2F
0x1806039be  mov     [rbp+hHandle], 0
0x1806039c6  lock inc dword ptr [rsi+10h]
0x1806039ca  lea     rax, [rbp+hHandle]
0x1806039ce  mov     [rsp+70h+pHandle], rax; pHandle
0x1806039d3  xor     r9d, r9d; pfnCallback
0x1806039d6  mov     r8d, 218h; flags
0x1806039dc  mov     rdx, rsi; pData
0x1806039df  lea     rcx, _lambda_469cb8603dcf52f8cda9d5d6a8068e20____lambda_invoker_cdecl_; pfnThreadProc
0x1806039e6  call    cs:__imp_SHCreateThreadWithHandle
0x1806039ec  test    eax, eax
0x1806039ee  jz      short loc_180603A1C
0x1806039f0  mov     rcx, rsi; this
0x1806039f3  call    ?_GetTimeOut@CLinkResolver@@AEAAKXZ; CLinkResolver::_GetTimeOut(void)
0x1806039f8  mov     edx, eax; dwMilliseconds
0x1806039fa  mov     rcx, [rbp+hHandle]; hHandle
0x1806039fe  call    cs:__imp_WaitForSingleObject
0x180603a04  mov     rcx, [rbp+hHandle]; hObject
0x180603a08  call    cs:__imp_CloseHandle
0x180603a0e  mov     byte ptr [rsi+33Ch], 0
0x180603a15  mov     ebx, 1
0x180603a1a  jmp     short loc_180603A60
0x180603a1c  mov     ebx, 2
0x180603a21  lea     rcx, [rsi+8]; this
0x180603a25  call    ?Release@CBaseTreeWalkerCB@@UEAAKXZ; CBaseTreeWalkerCB::Release(void)
0x180603a2a  jmp     loc_180603C88
0x180603a2f  lea     rcx, [rbp+var_30]; this
0x180603a33  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x180603a38  mov     rcx, rax; hInstance
0x180603a3b  mov     [rsp+70h+pHandle], rsi; int
0x180603a40  lea     r9, ?_DlgProc@CLinkResolver@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180603a47  mov     r8, r14; hWndParent
0x180603a4a  mov     edx, 3ECh; lpTemplateName
0x180603a4f  call    SHFusionDialogBoxParam
0x180603a54  mov     rbx, rax
0x180603a57  cmp     eax, 1
0x180603a5a  jnz     loc_180603C88
0x180603a60  mov     ecx, [rsi+348h]
0x180603a66  cmp     ecx, 28h ; '('
0x180603a69  jge     loc_180603C2E
0x180603a6f  mov     eax, [rsi+7F0h]
0x180603a75  test    al, 1
0x180603a77  jnz     loc_180603C4A
0x180603a7d  test    byte ptr [rsi+30h], 1
0x180603a81  jz      short loc_180603ACB
0x180603a83  test    rdi, rdi
0x180603a86  jz      short loc_180603A96
0x180603a88  mov     rcx, rdi; pszPath
0x180603a8b  call    cs:__imp_PathFindFileNameW
0x180603a91  mov     rbx, rax
0x180603a94  jmp     short loc_180603A9D
0x180603a96  lea     rbx, c_szNULL
0x180603a9d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x180603aa4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x180603aa9  lea     rcx, [rbp+var_30]; this
0x180603aad  test    al, al
0x180603aaf  jz      short loc_180603ABE
0x180603ab1  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x180603ab6  mov     r8d, 1077h
0x180603abc  jmp     short loc_180603B0E
0x180603abe  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x180603ac3  mov     r8d, 1077h
0x180603ac9  jmp     short loc_180603B3B
0x180603acb  test    rdi, rdi
0x180603ace  jnz     loc_180603BEE
0x180603ad4  bt      eax, 9
0x180603ad8  jb      loc_180603BEE
0x180603ade  cmp     ecx, 0Ah
0x180603ae1  jg      short loc_180603B5F
0x180603ae3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x180603aea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x180603aef  mov     rcx, r15; pszPath
0x180603af2  test    al, al
0x180603af4  jz      short loc_180603B23
0x180603af6  call    cs:__imp_PathFindFileNameW
0x180603afc  mov     rbx, rax
0x180603aff  lea     rcx, [rbp+var_30]; this
0x180603b03  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x180603b08  mov     r8d, 1073h; lpcText
0x180603b0e  mov     rcx, rax; hAppInst
0x180603b11  mov     rdx, r14; hWnd
0x180603b14  mov     [rsp+70h+var_48], rbx; __int64
0x180603b19  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short_const____1
0x180603b1e  jmp     loc_180603C4A
0x180603b23  call    cs:__imp_PathFindFileNameW
0x180603b29  mov     rbx, rax
0x180603b2c  lea     rcx, [rbp+var_30]; this
0x180603b30  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x180603b35  mov     r8d, 1073h; lpcText
0x180603b3b  mov     [rsp+70h+var_48], rbx
0x180603b40  mov     rcx, rax; hAppInst
0x180603b43  mov     rdx, r14; hWnd
0x180603b46  mov     r9d, 1070h; lpcTitle
0x180603b4c  mov     dword ptr [rsp+70h+pHandle], 30h ; '0'; fuStyle
0x180603b54  call    cs:__imp_ShellMessageBoxW
0x180603b5a  jmp     loc_180603C4A
0x180603b5f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x180603b66  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x180603b6b  lea     rdi, [rsi+378h]
0x180603b72  mov     rcx, r15; pszPath
0x180603b75  test    al, al
0x180603b77  jz      short loc_180603BA2
0x180603b79  call    cs:__imp_PathFindFileNameW
0x180603b7f  mov     rbx, rax
0x180603b82  lea     rcx, [rbp+var_30]; this
0x180603b86  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x180603b8b  mov     [rsp+70h+var_40], rdi; __int64
0x180603b90  mov     [rsp+70h+var_48], rbx; __int64
0x180603b95  mov     rdx, r14; hWnd
0x180603b98  mov     rcx, rax; hAppInst
0x180603b9b  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short_const___unsigned_short___
0x180603ba0  jmp     short loc_180603BDC
0x180603ba2  call    cs:__imp_PathFindFileNameW
0x180603ba8  mov     rbx, rax
0x180603bab  lea     rcx, [rbp+var_30]; this
0x180603baf  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x180603bb4  mov     [rsp+70h+var_40], rdi
0x180603bb9  mov     [rsp+70h+var_48], rbx
0x180603bbe  mov     dword ptr [rsp+70h+pHandle], 34h ; '4'; fuStyle
0x180603bc6  mov     r9d, 1070h; lpcTitle
0x180603bcc  lea     r8d, [r9+4]; lpcText
0x180603bd0  mov     rdx, r14; hWnd
0x180603bd3  mov     rcx, rax; hAppInst
0x180603bd6  call    cs:__imp_ShellMessageBoxW
0x180603bdc  mov     ecx, eax
0x180603bde  xor     eax, eax
0x180603be0  cmp     ecx, 6
0x180603be3  setnz   al
0x180603be6  lea     ebx, [rax+1]
0x180603be9  jmp     loc_180603C88
0x180603bee  mov     [rbp+var_20], r15
0x180603bf2  lea     rax, [rsi+378h]
0x180603bf9  mov     [rbp+var_18], rax
0x180603bfd  mov     [rbp+var_10], rdi
0x180603c01  cmp     dword ptr [rsi+59Ch], 0
0x180603c08  jz      short loc_180603C11
0x180603c0a  mov     ebx, 3EEh
0x180603c0f  jmp     short loc_180603C20
0x180603c11  xor     ebx, ebx
0x180603c13  cmp     ecx, 0Ah
0x180603c16  setle   bl
0x180603c19  add     rbx, 3F0h
0x180603c20  lea     rcx, [rbp+var_30]; this
0x180603c24  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x180603c29  mov     rdx, rbx
0x180603c2c  jmp     short loc_180603C6B
0x180603c2e  lea     r12, [rsi+378h]
0x180603c35  mov     rcx, r12; lpString1
0x180603c38  call    PathIsUnderWinsxs
0x180603c3d  test    eax, eax
0x180603c3f  jz      short loc_180603C88
0x180603c41  test    byte ptr [rsi+7F0h], 1
0x180603c48  jz      short loc_180603C51
0x180603c4a  mov     ebx, 2
0x180603c4f  jmp     short loc_180603C88
0x180603c51  mov     [rbp+var_20], r15
0x180603c55  mov     [rbp+var_18], r12
0x180603c59  mov     [rbp+var_10], rdi
0x180603c5d  lea     rcx, [rbp+var_30]; this
0x180603c61  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x180603c66  mov     edx, 3F1h; lpTemplateName
0x180603c6b  mov     rcx, rax; hInstance
0x180603c6e  lea     rax, [rbp+var_20]
0x180603c72  mov     [rsp+70h+pHandle], rax; LPARAM
0x180603c77  lea     r9, ?DeadLinkProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180603c7e  mov     r8, r14; hWndParent
0x180603c81  call    SHFusionDialogBoxParam
0x180603c86  mov     ebx, eax
0x180603c88  lea     rax, [rsi+0E8h]
0x180603c8f  add     rsi, 34Ch
0x180603c96  mov     ecx, 4
0x180603c9b  lea     edx, [rcx+7Ch]
0x180603c9e  movups  xmm0, xmmword ptr [rsi]
0x180603ca1  movups  xmmword ptr [rax], xmm0
0x180603ca4  movups  xmm1, xmmword ptr [rsi+10h]
0x180603ca8  movups  xmmword ptr [rax+10h], xmm1
0x180603cac  movups  xmm0, xmmword ptr [rsi+20h]
0x180603cb0  movups  xmmword ptr [rax+20h], xmm0
0x180603cb4  movups  xmm1, xmmword ptr [rsi+30h]
0x180603cb8  movups  xmmword ptr [rax+30h], xmm1
0x180603cbc  movups  xmm0, xmmword ptr [rsi+40h]
0x180603cc0  movups  xmmword ptr [rax+40h], xmm0
0x180603cc4  movups  xmm1, xmmword ptr [rsi+50h]
0x180603cc8  movups  xmmword ptr [rax+50h], xmm1
0x180603ccc  movups  xmm0, xmmword ptr [rsi+60h]
0x180603cd0  movups  xmmword ptr [rax+60h], xmm0
0x180603cd4  movups  xmm1, xmmword ptr [rsi+70h]
0x180603cd8  movups  xmmword ptr [rax+70h], xmm1
0x180603cdc  add     rax, rdx
0x180603cdf  add     rsi, rdx
0x180603ce2  sub     rcx, 1
0x180603ce6  jnz     short loc_180603C9E
0x180603ce8  movups  xmm0, xmmword ptr [rsi]
0x180603ceb  movups  xmmword ptr [rax], xmm0
0x180603cee  movups  xmm1, xmmword ptr [rsi+10h]
0x180603cf2  movups  xmmword ptr [rax+10h], xmm1
0x180603cf6  movups  xmm0, xmmword ptr [rsi+20h]
0x180603cfa  movups  xmmword ptr [rax+20h], xmm0
0x180603cfe  movups  xmm1, xmmword ptr [rsi+30h]
0x180603d02  movups  xmmword ptr [rax+30h], xmm1
0x180603d06  movups  xmm0, xmmword ptr [rsi+40h]
0x180603d0a  movups  xmmword ptr [rax+40h], xmm0
0x180603d0e  lea     rcx, [rbp+var_30]
0x180603d12  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180603d17  mov     eax, ebx
0x180603d19  mov     rcx, [rbp+var_8]
0x180603d1d  xor     rcx, rsp; StackCookie
0x180603d20  call    __security_check_cookie
0x180603d25  add     rsp, 70h
0x180603d29  pop     r15
0x180603d2b  pop     r14
0x180603d2d  pop     r12
0x180603d2f  pop     rdi
0x180603d30  pop     rsi
0x180603d31  pop     rbx
0x180603d32  pop     rbp
0x180603d33  retn
```
