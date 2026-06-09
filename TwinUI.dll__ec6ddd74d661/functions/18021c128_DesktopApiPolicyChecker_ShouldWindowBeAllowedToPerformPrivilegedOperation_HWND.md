# DesktopApiPolicyChecker::ShouldWindowBeAllowedToPerformPrivilegedOperation(HWND__ *)

- ea: `0x18021c128`
- end: `0x18021c3e3`
- name: `?ShouldWindowBeAllowedToPerformPrivilegedOperation@DesktopApiPolicyChecker@@YAJPEAUHWND__@@@Z`
- size: `699`
- prototype: `__int64 __fastcall(HWND hWnd, HWND)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18021c3f0`
- `0x18021cb30`

## callees

- `0x18000e498`
- `0x18002df5c`
- `0x1800378dc`
- `0x180055268`
- `0x1800a0f20`
- `0x1800ab0e0`
- `0x1800b0a94`
- `0x1800f1a00`
- `0x180215d9c`
- `0x180216904`
- `0x18021c128`
- `0x1803862f8`
- `0x180386478`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18021c2f3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18021c2f3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18021c314`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18021c314`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x18021c330`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x18021c330`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18021c144`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18021c362`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18021c144`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18021c362`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18021c2e0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18021c2e0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18021c2c9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18021c2c9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x18021c397`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x18021c397`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18021c18f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18021c18f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DesktopApiPolicyChecker::ShouldWindowBeAllowedToPerformPrivilegedOperation(HWND hWnd, HWND a2)
{
  const char *v3; // r9
  int LastError; // ebx
  __int64 v6; // rdx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int Policy; // eax
  unsigned __int16 **v10; // r8
  int *v11; // r8
  struct IUnknown *v12; // rbx
  int IsAppBeingDebugged; // eax
  int *v14; // r8
  int v15; // edi
  const unsigned __int16 *v16; // rdx
  int ShouldAppBeAllowedToPerformPrivilegedOperationBasedOnForeground; // eax
  HWND ForegroundWindow; // rbx
  HWND Ancestor; // rsi
  DWORD v20; // r14d
  HANDLE v21; // rax
  const char *v22; // r9
  struct IUnknown *v23; // [rsp+20h] [rbp-30h] BYREF
  __int64 v24; // [rsp+28h] [rbp-28h] BYREF
  HANDLE v25; // [rsp+30h] [rbp-20h] BYREF
  __int64 *v26; // [rsp+38h] [rbp-18h] BYREF
  __int64 v27; // [rsp+40h] [rbp-10h] BYREF
  char v28; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  DWORD dwProcessId; // [rsp+88h] [rbp+38h] BYREF
  WINBOOL pbDebuggerPresent; // [rsp+90h] [rbp+40h] BYREF
  DWORD v32; // [rsp+98h] [rbp+48h] BYREF

  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(hWnd, &dwProcessId) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x13,
             (unsigned int)"Internal\\Shell\\Inc\\DesktopApiPolicyChecker.h",
             v3);
  v24 = 0;
  v26 = &v24;
  v27 = 0;
  v28 = 1;
  LastError = UMgrOpenProcessTokenForQuery(dwProcessId, &v27);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v26);
  if ( LastError < 0 )
  {
    v7 = (unsigned int)LastError;
    v8 = 24;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"Internal\\Shell\\Inc\\DesktopApiPolicyChecker.h",
      (const char *)v7,
      (int)v23);
LABEL_29:
    Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v24);
    return (unsigned int)LastError;
  }
  pbDebuggerPresent = 0;
  Policy = AppModelPolicy_GetPolicy(v24, v6, &pbDebuggerPresent);
  LastError = Policy;
  if ( Policy < 0 )
  {
    v7 = (unsigned int)Policy;
    v8 = 27;
    goto LABEL_7;
  }
  v23 = 0;
  if ( pbDebuggerPresent != 196608 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v23,
      0);
    if ( (int)UserAwareCallerIdentity::GetAppIdFromProcessId(dwProcessId, (unsigned int)&v23, v10) >= 0 )
    {
      pbDebuggerPresent = 0;
      v12 = v23;
      IsAppBeingDebugged = CallerIdentity::ApiPolicyChecker::IsAppBeingDebugged(
                             (CallerIdentity::ApiPolicyChecker *)v23,
                             (const unsigned __int16 *)&pbDebuggerPresent,
                             v11);
      v15 = IsAppBeingDebugged;
      if ( IsAppBeingDebugged < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21,
          (unsigned int)"Internal\\Shell\\Inc\\DesktopApiPolicyChecker.h",
          (const char *)(unsigned int)IsAppBeingDebugged,
          (int)v23);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
        LastError = v15;
        goto LABEL_29;
      }
      if ( pbDebuggerPresent )
        goto LABEL_30;
      pbDebuggerPresent = 0;
      if ( (int)CallerIdentity::ApiPolicyChecker::IsApplicationForeground(
                  (CallerIdentity::ApiPolicyChecker *)v12,
                  (const unsigned __int16 *)&pbDebuggerPresent,
                  v14) < 0
        || pbDebuggerPresent )
      {
        ShouldAppBeAllowedToPerformPrivilegedOperationBasedOnForeground = CallerIdentity::ApiPolicyChecker::ShouldAppBeAllowedToPerformPrivilegedOperationBasedOnForeground(
                                                                            v12,
                                                                            v16);
        LastError = ShouldAppBeAllowedToPerformPrivilegedOperationBasedOnForeground;
        if ( ShouldAppBeAllowedToPerformPrivilegedOperationBasedOnForeground < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2B,
            (unsigned int)"Internal\\Shell\\Inc\\DesktopApiPolicyChecker.h",
            (const char *)(unsigned int)ShouldAppBeAllowedToPerformPrivilegedOperationBasedOnForeground,
            (int)v23);
LABEL_17:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
          goto LABEL_29;
        }
        goto LABEL_30;
      }
LABEL_28:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
      LastError = -2147019873;
      goto LABEL_29;
    }
  }
  ForegroundWindow = GetForegroundWindow();
  Ancestor = GetAncestor(hWnd, 2u);
  v20 = dwProcessId;
  pbDebuggerPresent = IsDebuggerPresent();
  if ( !pbDebuggerPresent )
  {
    v21 = OpenProcess(0x1000u, 0, v20);
    v25 = v21;
    if ( v21 && !CheckRemoteDebuggerPresent(v21, &pbDebuggerPresent) )
      pbDebuggerPresent = 0;
    CAutoHandle<void *>::~CAutoHandle<void *>(&v25);
    if ( !pbDebuggerPresent && Ancestor != ForegroundWindow )
    {
      v32 = pbDebuggerPresent;
      if ( !GetWindowThreadProcessId(ForegroundWindow, &v32) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x43,
                      (unsigned int)"Internal\\Shell\\Inc\\DesktopApiPolicyChecker.h",
                      v22);
        goto LABEL_17;
      }
      if ( dwProcessId != v32 || !IsWindowVisible(hWnd) )
        goto LABEL_28;
    }
  }
LABEL_30:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
  Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v24);
  return 0;
}

```

## disassembly

```asm
0x18021c128  push    rbp
0x18021c12a  push    rbx
0x18021c12b  push    rsi
0x18021c12c  push    rdi
0x18021c12d  push    r14
0x18021c12f  mov     rbp, rsp
0x18021c132  sub     rsp, 50h
0x18021c136  mov     rdi, rcx
0x18021c139  mov     [rbp+dwProcessId], 0
0x18021c140  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x18021c144  call    cs:__imp_GetWindowThreadProcessId
0x18021c14b  nop     dword ptr [rax+rax+00h]
0x18021c150  test    eax, eax
0x18021c152  jnz     short loc_18021C16C
0x18021c154  mov     rcx, [rbp+28h]; this
0x18021c158  lea     r8, aInternalShellI; "Internal\\Shell\\Inc\\DesktopApiPolicyC"...
0x18021c15f  lea     edx, [rax+13h]; void *
0x18021c162  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18021c167  jmp     loc_18021C3D7
0x18021c16c  mov     [rbp+var_28], 0
0x18021c174  lea     rax, [rbp+var_28]
0x18021c178  mov     [rbp+var_18], rax
0x18021c17c  mov     [rbp+var_10], 0
0x18021c184  mov     [rbp+var_8], 1
0x18021c188  lea     rdx, [rbp+var_10]
0x18021c18c  mov     ecx, [rbp+dwProcessId]
0x18021c18f  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x18021c196  nop     dword ptr [rax+rax+00h]
0x18021c19b  mov     ebx, eax
0x18021c19d  lea     rcx, [rbp+var_18]
0x18021c1a1  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18021c1a6  test    ebx, ebx
0x18021c1a8  jns     short loc_18021C1B4
0x18021c1aa  mov     r9d, ebx
0x18021c1ad  mov     edx, 18h
0x18021c1b2  jmp     short loc_18021C1D6
0x18021c1b4  mov     [rbp+pbDebuggerPresent], 0
0x18021c1bb  lea     r8, [rbp+pbDebuggerPresent]
0x18021c1bf  mov     rcx, [rbp+var_28]
0x18021c1c3  call    ?AppModelPolicy_GetPolicy@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@@Z; AppModelPolicy_GetPolicy(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *)
0x18021c1c8  mov     ebx, eax
0x18021c1ca  test    eax, eax
0x18021c1cc  jns     short loc_18021C1EB
0x18021c1ce  mov     r9d, eax; char *
0x18021c1d1  mov     edx, 1Bh; void *
0x18021c1d6  lea     r8, aInternalShellI; "Internal\\Shell\\Inc\\DesktopApiPolicyC"...
0x18021c1dd  mov     rcx, [rbp+28h]; this
0x18021c1e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021c1e6  jmp     loc_18021C3B5
0x18021c1eb  mov     [rbp+var_30], 0
0x18021c1f3  cmp     [rbp+pbDebuggerPresent], 30000h
0x18021c1fa  jz      loc_18021C2C9
0x18021c200  xor     edx, edx
0x18021c202  lea     rcx, [rbp+var_30]
0x18021c206  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18021c20b  lea     rdx, [rbp+var_30]; unsigned int
0x18021c20f  mov     ecx, [rbp+dwProcessId]; dwProcessId
0x18021c212  call    ?GetAppIdFromProcessId@UserAwareCallerIdentity@@YAJKPEAPEAG@Z; UserAwareCallerIdentity::GetAppIdFromProcessId(ulong,ushort * *)
0x18021c217  test    eax, eax
0x18021c219  js      loc_18021C2C9
0x18021c21f  mov     [rbp+pbDebuggerPresent], 0
0x18021c226  lea     rdx, [rbp+pbDebuggerPresent]; unsigned __int16 *
0x18021c22a  mov     rbx, [rbp+var_30]
0x18021c22e  mov     rcx, rbx; this
0x18021c231  call    ?IsAppBeingDebugged@ApiPolicyChecker@CallerIdentity@@YAJPEBGPEAH@Z; CallerIdentity::ApiPolicyChecker::IsAppBeingDebugged(ushort const *,int *)
0x18021c236  mov     edi, eax
0x18021c238  test    eax, eax
0x18021c23a  jns     short loc_18021C265
0x18021c23c  mov     rcx, [rbp+28h]; this
0x18021c240  mov     r9d, eax; char *
0x18021c243  lea     r8, aInternalShellI; "Internal\\Shell\\Inc\\DesktopApiPolicyC"...
0x18021c24a  mov     edx, 21h ; '!'; void *
0x18021c24f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021c254  nop
0x18021c255  lea     rcx, [rbp+var_30]
0x18021c259  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18021c25e  mov     ebx, edi
0x18021c260  jmp     loc_18021C3B5
0x18021c265  cmp     [rbp+pbDebuggerPresent], 0
0x18021c269  jnz     loc_18021C3C2
0x18021c26f  mov     [rbp+pbDebuggerPresent], 0
0x18021c276  lea     rdx, [rbp+pbDebuggerPresent]; unsigned __int16 *
0x18021c27a  mov     rcx, rbx; this
0x18021c27d  call    ?IsApplicationForeground@ApiPolicyChecker@CallerIdentity@@YAJPEBGPEAH@Z; CallerIdentity::ApiPolicyChecker::IsApplicationForeground(ushort const *,int *)
0x18021c282  test    eax, eax
0x18021c284  js      short loc_18021C290
0x18021c286  cmp     [rbp+pbDebuggerPresent], 0
0x18021c28a  jz      loc_18021C3A7
0x18021c290  mov     rcx, rbx; this
0x18021c293  call    ?ShouldAppBeAllowedToPerformPrivilegedOperationBasedOnForeground@ApiPolicyChecker@CallerIdentity@@YAJPEBG@Z; CallerIdentity::ApiPolicyChecker::ShouldAppBeAllowedToPerformPrivilegedOperationBasedOnForeground(ushort const *)
0x18021c298  mov     ebx, eax
0x18021c29a  test    eax, eax
0x18021c29c  jns     loc_18021C3C2
0x18021c2a2  mov     rcx, [rbp+28h]; this
0x18021c2a6  mov     r9d, eax; char *
0x18021c2a9  lea     r8, aInternalShellI; "Internal\\Shell\\Inc\\DesktopApiPolicyC"...
0x18021c2b0  mov     edx, 2Bh ; '+'; void *
0x18021c2b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021c2ba  nop
0x18021c2bb  lea     rcx, [rbp+var_30]
0x18021c2bf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18021c2c4  jmp     loc_18021C3B5
0x18021c2c9  call    cs:__imp_GetForegroundWindow
0x18021c2d0  nop     dword ptr [rax+rax+00h]
0x18021c2d5  mov     rbx, rax
0x18021c2d8  mov     edx, 2; gaFlags
0x18021c2dd  mov     rcx, rdi; hwnd
0x18021c2e0  call    cs:__imp_GetAncestor
0x18021c2e7  nop     dword ptr [rax+rax+00h]
0x18021c2ec  mov     rsi, rax
0x18021c2ef  mov     r14d, [rbp+dwProcessId]
0x18021c2f3  call    cs:__imp_IsDebuggerPresent
0x18021c2fa  nop     dword ptr [rax+rax+00h]
0x18021c2ff  mov     [rbp+pbDebuggerPresent], eax
0x18021c302  test    eax, eax
0x18021c304  jnz     loc_18021C3C2
0x18021c30a  mov     r8d, r14d; dwProcessId
0x18021c30d  xor     edx, edx; bInheritHandle
0x18021c30f  mov     ecx, 1000h; dwDesiredAccess
0x18021c314  call    cs:__imp_OpenProcess
0x18021c31b  nop     dword ptr [rax+rax+00h]
0x18021c320  mov     [rbp+var_20], rax
0x18021c324  test    rax, rax
0x18021c327  jz      short loc_18021C343
0x18021c329  lea     rdx, [rbp+pbDebuggerPresent]; pbDebuggerPresent
0x18021c32d  mov     rcx, rax; hProcess
0x18021c330  call    cs:__imp_CheckRemoteDebuggerPresent
0x18021c337  nop     dword ptr [rax+rax+00h]
0x18021c33c  test    eax, eax
0x18021c33e  jnz     short loc_18021C343
0x18021c340  mov     [rbp+pbDebuggerPresent], eax
0x18021c343  lea     rcx, [rbp+var_20]
0x18021c347  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x18021c34c  mov     eax, [rbp+pbDebuggerPresent]
0x18021c34f  test    eax, eax
0x18021c351  jnz     short loc_18021C3C2
0x18021c353  cmp     rsi, rbx
0x18021c356  jz      short loc_18021C3C2
0x18021c358  mov     [rbp+arg_18], eax
0x18021c35b  lea     rdx, [rbp+arg_18]; lpdwProcessId
0x18021c35f  mov     rcx, rbx; hWnd
0x18021c362  call    cs:__imp_GetWindowThreadProcessId
0x18021c369  nop     dword ptr [rax+rax+00h]
0x18021c36e  test    eax, eax
0x18021c370  jnz     short loc_18021C38C
0x18021c372  mov     rcx, [rbp+28h]; this
0x18021c376  lea     r8, aInternalShellI; "Internal\\Shell\\Inc\\DesktopApiPolicyC"...
0x18021c37d  lea     edx, [rax+43h]; void *
0x18021c380  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18021c385  mov     ebx, eax
0x18021c387  jmp     loc_18021C2BB
0x18021c38c  mov     eax, [rbp+arg_18]
0x18021c38f  cmp     [rbp+dwProcessId], eax
0x18021c392  jnz     short loc_18021C3A7
0x18021c394  mov     rcx, rdi; hWnd
0x18021c397  call    cs:__imp_IsWindowVisible
0x18021c39e  nop     dword ptr [rax+rax+00h]
0x18021c3a3  test    eax, eax
0x18021c3a5  jnz     short loc_18021C3C2
0x18021c3a7  lea     rcx, [rbp+var_30]
0x18021c3ab  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18021c3b0  mov     ebx, 8007139Fh
0x18021c3b5  lea     rcx, [rbp+var_28]
0x18021c3b9  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18021c3be  mov     eax, ebx
0x18021c3c0  jmp     short loc_18021C3D7
0x18021c3c2  lea     rcx, [rbp+var_30]
0x18021c3c6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18021c3cb  nop
0x18021c3cc  lea     rcx, [rbp+var_28]
0x18021c3d0  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18021c3d5  xor     eax, eax
0x18021c3d7  add     rsp, 50h
0x18021c3db  pop     r14
0x18021c3dd  pop     rdi
0x18021c3de  pop     rsi
0x18021c3df  pop     rbx
0x18021c3e0  pop     rbp
0x18021c3e1  retn
```
