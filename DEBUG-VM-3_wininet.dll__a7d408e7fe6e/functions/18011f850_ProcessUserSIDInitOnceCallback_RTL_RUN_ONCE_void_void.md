# _ProcessUserSIDInitOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18011f850`
- end: `0x18011fb99`
- name: `?_ProcessUserSIDInitOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `841`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009cf0`
- `0x1800548ec`
- `0x1800701d0`
- `0x1800a8848`
- `0x1800b5a90`
- `0x18010a6bc`
- `0x18010d394`
- `0x180119bf4`
- `0x18011f850`
- `0x18011fba0`
- `0x18013b3a4`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801dd598`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011faf2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011faf2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18011f900`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18011f900`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011f8ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011f8ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011fb0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011fb5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011fb6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011fb0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011fb5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011fb6d`
- `ntdll!RtlQueryPackageClaims` at `0x18011faa9`
- `ntdll!RtlQueryPackageClaims` at `0x18011faa9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18011fb4e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18011fb4e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18011f9f5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18011fa48`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18011f9f5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18011fa48`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18011fb28`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18011fb28`

## pseudocode

```c
_BOOL8 __fastcall _ProcessUserSIDInitOnceCallback(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  signed int TokenUserSID; // ebx
  HANDLE CurrentProcess; // rax
  unsigned int v6; // r8d
  int v7; // eax
  unsigned int v8; // r8d
  int v9; // edi
  int v10; // eax
  int LastError; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  DWORD v16; // eax
  BOOL v17; // edi
  HANDLE v18; // rbx
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+44h] [rbp-BCh]
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v23; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE hToken; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h]
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  _BYTE pSourceSid[80]; // [rsp+70h] [rbp-90h] BYREF
  _SID v29; // [rsp+C0h] [rbp-40h] BYREF

  v21 = 0;
  v25 = 0;
  hToken = 0;
  TokenHandle = 0;
  memset_0(pSourceSid, 0, 0x44u);
  memset_0(&v29, 0, 0x44u);
  v22 = 0;
  v23 = 0;
  v20 = 4096;
  v27 = 0;
  if ( Context )
    *Context = 0;
  TokenUserSID = AutoTokenImpersonate::Impersonate((AutoTokenImpersonate *)&hToken, 0);
  if ( TokenUserSID < 0 )
  {
    v21 = 63;
    goto LABEL_41;
  }
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    TokenUserSID = WxGetTokenUserSID(TokenHandle, pSourceSid, v6);
    if ( TokenUserSID < 0 )
    {
      v21 = 67;
      goto LABEL_41;
    }
    TokenUserSID = WxIsTokenAppContainer(TokenHandle, &v22);
    if ( TokenUserSID < 0 )
    {
      v21 = 69;
      goto LABEL_41;
    }
    v9 = v22;
    if ( v22 )
    {
      TokenUserSID = WxGetTokenAppContainerSID(TokenHandle, &v29, v8);
      if ( TokenUserSID < 0 )
      {
        v21 = 72;
        goto LABEL_41;
      }
    }
    TokenUserSID = WxGetTokenSessionId(TokenHandle, &v23);
    if ( TokenUserSID < 0 )
    {
      v21 = 75;
      goto LABEL_41;
    }
    TokenUserSID = WxGetTokenIntegrityLevel(TokenHandle, &v20);
    if ( TokenUserSID < 0 )
    {
      v21 = 77;
      goto LABEL_41;
    }
    if ( CopySid(0x44u, &g_rgbProcessUserSID, pSourceSid) )
    {
      TokenUserSID = 0;
      if ( !v9 || (g_fIsProcessAppContainer = 1, CopySid(0x44u, &g_rgbAppContainerSID, &v29)) )
      {
        if ( (unsigned int)Feature_WinInetCacheAppBrokerForUWPMediumIL__private_IsEnabledDeviceUsageNoInline() )
        {
          v12 = RtlQueryPackageClaims(TokenHandle, 0, 0, 0, 0, 0, &v27, 0);
          if ( v12 < 0 )
          {
            if ( v12 != -1073741275 )
            {
              TokenUserSID = HRESULT_FROM_NTSTATUS(v12);
              if ( TokenUserSID < 0 )
              {
                v21 = 107;
                goto LABEL_41;
              }
            }
          }
          else
          {
            if ( (BYTE3(xmmword_180266B60) & 0x20) != 0 )
              WPP_SF_L(v14, v13, v15, (unsigned int)v27);
            g_fAppIsPackaged = v27 != 0;
          }
        }
        g_dwProcessSessionId = v23;
        g_dwProcessIntegrityLevel = v20;
        goto LABEL_41;
      }
      LastError = WxGetLastError();
      TokenUserSID = LastError;
      if ( LastError > 0 )
        TokenUserSID = (unsigned __int16)LastError | 0x80070000;
      v21 = 85;
      if ( TokenUserSID >= 0 )
        TokenUserSID = -2147418113;
    }
    else
    {
      v10 = WxGetLastError();
      TokenUserSID = v10;
      if ( v10 > 0 )
        TokenUserSID = (unsigned __int16)v10 | 0x80070000;
      v21 = 79;
      if ( TokenUserSID >= 0 )
        TokenUserSID = -2147418113;
    }
  }
  else
  {
    v7 = WxGetLastError();
    TokenUserSID = v7;
    if ( v7 > 0 )
      TokenUserSID = (unsigned __int16)v7 | 0x80070000;
    v21 = 65;
    if ( TokenUserSID >= 0 )
      TokenUserSID = -2147418113;
  }
LABEL_41:
  v16 = WX_WIN32_FROM_HR((unsigned int)TokenUserSID);
  SetLastError(v16);
  v17 = TokenUserSID >= 0;
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  v18 = hToken;
  if ( !(_DWORD)v25 )
    goto LABEL_52;
  if ( hToken )
    ImpersonateLoggedOnUser(hToken);
  else
    RevertToSelf();
  if ( v18 )
  {
    CloseHandle(v18);
    v18 = 0;
LABEL_52:
    if ( v18 )
      CloseHandle(v18);
  }
  return v17;
}

```

## disassembly

```asm
0x18011f850  mov     [rsp-8+arg_0], rbx
0x18011f855  mov     [rsp-8+arg_8], rsi
0x18011f85a  push    rbp
0x18011f85b  push    rdi
0x18011f85c  push    r14
0x18011f85e  lea     rbp, [rsp-20h]
0x18011f863  sub     rsp, 120h
0x18011f86a  mov     rax, cs:__security_cookie
0x18011f871  xor     rax, rsp
0x18011f874  mov     [rbp+30h+var_20], rax
0x18011f878  xor     esi, esi
0x18011f87a  lea     rcx, [rsp+130h+pSourceSid]; void *
0x18011f87f  mov     rbx, r8
0x18011f882  mov     [rsp+130h+var_EC], esi
0x18011f886  xor     edx, edx; Val
0x18011f888  mov     [rsp+130h+var_D8], rsi
0x18011f88d  mov     [rsp+130h+hToken], rsi
0x18011f892  lea     r14d, [rsi+44h]
0x18011f896  mov     [rsp+130h+TokenHandle], rsi
0x18011f89b  mov     r8d, r14d; Size
0x18011f89e  call    memset_0
0x18011f8a3  mov     r8d, r14d; Size
0x18011f8a6  lea     rcx, [rbp+30h+var_70]; void *
0x18011f8aa  xor     edx, edx; Val
0x18011f8ac  call    memset_0
0x18011f8b1  mov     [rsp+130h+var_E8], esi
0x18011f8b5  mov     [rsp+130h+var_E4], esi
0x18011f8b9  mov     [rsp+130h+var_F0], 1000h
0x18011f8c1  mov     [rsp+130h+var_C8], rsi
0x18011f8c6  test    rbx, rbx
0x18011f8c9  jz      short loc_18011F8CE
0x18011f8cb  mov     [rbx], rsi
0x18011f8ce  xor     edx, edx; void *
0x18011f8d0  lea     rcx, [rsp+130h+hToken]; this
0x18011f8d5  call    ?Impersonate@AutoTokenImpersonate@@QEAAJPEAX@Z; AutoTokenImpersonate::Impersonate(void *)
0x18011f8da  mov     ebx, eax
0x18011f8dc  test    eax, eax
0x18011f8de  jns     short loc_18011F8ED
0x18011f8e0  mov     [rsp+130h+var_EC], 3Fh ; '?'
0x18011f8e8  jmp     loc_18011FAE9
0x18011f8ed  call    cs:__imp_GetCurrentProcess
0x18011f8f3  lea     r8, [rsp+130h+TokenHandle]; TokenHandle
0x18011f8f8  mov     edx, 20008h; DesiredAccess
0x18011f8fd  mov     rcx, rax; ProcessHandle
0x18011f900  call    cs:__imp_OpenProcessToken
0x18011f906  test    eax, eax
0x18011f908  jnz     short loc_18011F935
0x18011f90a  call    WxGetLastError
0x18011f90f  mov     ebx, eax
0x18011f911  test    eax, eax
0x18011f913  jle     short loc_18011F91E
0x18011f915  movzx   ebx, ax
0x18011f918  or      ebx, 80070000h
0x18011f91e  test    ebx, ebx
0x18011f920  mov     [rsp+130h+var_EC], 41h ; 'A'
0x18011f928  mov     eax, 8000FFFFh
0x18011f92d  cmovns  ebx, eax
0x18011f930  jmp     loc_18011FAE9
0x18011f935  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x18011f93a  lea     rdx, [rsp+130h+pSourceSid]; pDestinationSid
0x18011f93f  call    ?WxGetTokenUserSID@@YAJPEAXPEAU_SID@@K@Z; WxGetTokenUserSID(void *,_SID *,ulong)
0x18011f944  mov     ebx, eax
0x18011f946  test    eax, eax
0x18011f948  jns     short loc_18011F957
0x18011f94a  mov     [rsp+130h+var_EC], 43h ; 'C'
0x18011f952  jmp     loc_18011FAE9
0x18011f957  mov     rcx, [rsp+130h+TokenHandle]; void *
0x18011f95c  lea     rdx, [rsp+130h+var_E8]; int *
0x18011f961  call    ?WxIsTokenAppContainer@@YAJPEAXPEAH@Z; WxIsTokenAppContainer(void *,int *)
0x18011f966  mov     ebx, eax
0x18011f968  test    eax, eax
0x18011f96a  jns     short loc_18011F979
0x18011f96c  mov     [rsp+130h+var_EC], 45h ; 'E'
0x18011f974  jmp     loc_18011FAE9
0x18011f979  mov     edi, [rsp+130h+var_E8]
0x18011f97d  test    edi, edi
0x18011f97f  jz      short loc_18011F9A2
0x18011f981  mov     rcx, [rsp+130h+TokenHandle]; void *
0x18011f986  lea     rdx, [rbp+30h+var_70]; struct _SID *
0x18011f98a  call    ?WxGetTokenAppContainerSID@@YAJPEAXPEAU_SID@@K@Z; WxGetTokenAppContainerSID(void *,_SID *,ulong)
0x18011f98f  mov     ebx, eax
0x18011f991  test    eax, eax
0x18011f993  jns     short loc_18011F9A2
0x18011f995  mov     [rsp+130h+var_EC], 48h ; 'H'
0x18011f99d  jmp     loc_18011FAE9
0x18011f9a2  mov     rcx, [rsp+130h+TokenHandle]; void *
0x18011f9a7  lea     rdx, [rsp+130h+var_E4]; unsigned int *
0x18011f9ac  call    ?WxGetTokenSessionId@@YAJPEAXPEAK@Z; WxGetTokenSessionId(void *,ulong *)
0x18011f9b1  mov     ebx, eax
0x18011f9b3  test    eax, eax
0x18011f9b5  jns     short loc_18011F9C4
0x18011f9b7  mov     [rsp+130h+var_EC], 4Bh ; 'K'
0x18011f9bf  jmp     loc_18011FAE9
0x18011f9c4  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x18011f9c9  lea     rdx, [rsp+130h+var_F0]; unsigned int *
0x18011f9ce  call    ?WxGetTokenIntegrityLevel@@YAJPEAXPEAK@Z; WxGetTokenIntegrityLevel(void *,ulong *)
0x18011f9d3  mov     ebx, eax
0x18011f9d5  test    eax, eax
0x18011f9d7  jns     short loc_18011F9E6
0x18011f9d9  mov     [rsp+130h+var_EC], 4Dh ; 'M'
0x18011f9e1  jmp     loc_18011FAE9
0x18011f9e6  lea     r8, [rsp+130h+pSourceSid]; pSourceSid
0x18011f9eb  mov     ecx, r14d; nDestinationSidLength
0x18011f9ee  lea     rdx, ?g_rgbProcessUserSID@@3PAEA; pDestinationSid
0x18011f9f5  call    cs:__imp_CopySid
0x18011f9fb  test    eax, eax
0x18011f9fd  jnz     short loc_18011FA2A
0x18011f9ff  call    WxGetLastError
0x18011fa04  mov     ebx, eax
0x18011fa06  test    eax, eax
0x18011fa08  jle     short loc_18011FA13
0x18011fa0a  movzx   ebx, ax
0x18011fa0d  or      ebx, 80070000h
0x18011fa13  test    ebx, ebx
0x18011fa15  mov     [rsp+130h+var_EC], 4Fh ; 'O'
0x18011fa1d  mov     eax, 8000FFFFh
0x18011fa22  cmovns  ebx, eax
0x18011fa25  jmp     loc_18011FAE9
0x18011fa2a  mov     ebx, esi
0x18011fa2c  test    edi, edi
0x18011fa2e  jz      short loc_18011FA7A
0x18011fa30  lea     r8, [rbp+30h+var_70]; pSourceSid
0x18011fa34  mov     cs:?g_fIsProcessAppContainer@@3HA, 1; int g_fIsProcessAppContainer
0x18011fa3e  lea     rdx, ?g_rgbAppContainerSID@@3PAEA; pDestinationSid
0x18011fa45  mov     ecx, r14d; nDestinationSidLength
0x18011fa48  call    cs:__imp_CopySid
0x18011fa4e  test    eax, eax
0x18011fa50  jnz     short loc_18011FA7A
0x18011fa52  call    WxGetLastError
0x18011fa57  mov     ebx, eax
0x18011fa59  test    eax, eax
0x18011fa5b  jle     short loc_18011FA66
0x18011fa5d  movzx   ebx, ax
0x18011fa60  or      ebx, 80070000h
0x18011fa66  test    ebx, ebx
0x18011fa68  mov     [rsp+130h+var_EC], 55h ; 'U'
0x18011fa70  mov     eax, 8000FFFFh
0x18011fa75  cmovns  ebx, eax
0x18011fa78  jmp     short loc_18011FAE9
0x18011fa7a  call    Feature_WinInetCacheAppBrokerForUWPMediumIL__private_IsEnabledDeviceUsageNoInline
0x18011fa7f  test    eax, eax
0x18011fa81  jz      short loc_18011FAD5
0x18011fa83  mov     rcx, [rsp+130h+TokenHandle]
0x18011fa88  lea     rax, [rsp+130h+var_C8]
0x18011fa8d  mov     [rsp+130h+var_F8], rsi
0x18011fa92  xor     r9d, r9d
0x18011fa95  mov     [rsp+130h+var_100], rax
0x18011fa9a  xor     r8d, r8d
0x18011fa9d  mov     [rsp+130h+var_108], rsi
0x18011faa2  xor     edx, edx
0x18011faa4  mov     [rsp+130h+var_110], rsi
0x18011faa9  call    cs:__imp_RtlQueryPackageClaims
0x18011faaf  test    eax, eax
0x18011fab1  js      short loc_18011FB30
0x18011fab3  test    byte ptr cs:xmmword_180266B60+3, 20h
0x18011faba  jz      short loc_18011FAC6
0x18011fabc  mov     r9d, dword ptr [rsp+130h+var_C8]
0x18011fac1  call    WPP_SF_L
0x18011fac6  cmp     dword ptr [rsp+130h+var_C8], esi
0x18011faca  mov     eax, esi
0x18011facc  setnz   al
0x18011facf  mov     cs:?g_fAppIsPackaged@@3HA, eax; int g_fAppIsPackaged
0x18011fad5  mov     eax, [rsp+130h+var_E4]
0x18011fad9  mov     cs:?g_dwProcessSessionId@@3KA, eax; ulong g_dwProcessSessionId
0x18011fadf  mov     eax, [rsp+130h+var_F0]
0x18011fae3  mov     cs:?g_dwProcessIntegrityLevel@@3KA, eax; ulong g_dwProcessIntegrityLevel
0x18011fae9  mov     ecx, ebx
0x18011faeb  call    WX_WIN32_FROM_HR
0x18011faf0  mov     ecx, eax; dwErrCode
0x18011faf2  call    cs:__imp_SetLastError
0x18011faf8  mov     rcx, [rsp+130h+TokenHandle]; hObject
0x18011fafd  test    ebx, ebx
0x18011faff  mov     edi, esi
0x18011fb01  setns   dil
0x18011fb05  test    rcx, rcx
0x18011fb08  jz      short loc_18011FB15
0x18011fb0a  call    cs:__imp_CloseHandle
0x18011fb10  mov     [rsp+130h+TokenHandle], rsi
0x18011fb15  mov     rbx, [rsp+130h+hToken]
0x18011fb1a  cmp     dword ptr [rsp+130h+var_D8], esi
0x18011fb1e  jz      short loc_18011FB65
0x18011fb20  test    rbx, rbx
0x18011fb23  jz      short loc_18011FB4E
0x18011fb25  mov     rcx, rbx; hToken
0x18011fb28  call    cs:__imp_ImpersonateLoggedOnUser
0x18011fb2e  jmp     short loc_18011FB54
0x18011fb30  cmp     eax, 0C0000225h
0x18011fb35  jz      short loc_18011FAD5
0x18011fb37  mov     ecx, eax; int
0x18011fb39  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x18011fb3e  mov     ebx, eax
0x18011fb40  test    eax, eax
0x18011fb42  jns     short loc_18011FAD5
0x18011fb44  mov     [rsp+130h+var_EC], 6Bh ; 'k'
0x18011fb4c  jmp     short loc_18011FAE9
0x18011fb4e  call    cs:__imp_RevertToSelf
0x18011fb54  test    rbx, rbx
0x18011fb57  jz      short loc_18011FB73
0x18011fb59  mov     rcx, rbx; hObject
0x18011fb5c  call    cs:__imp_CloseHandle
0x18011fb62  mov     rbx, rsi
0x18011fb65  test    rbx, rbx
0x18011fb68  jz      short loc_18011FB73
0x18011fb6a  mov     rcx, rbx; hObject
0x18011fb6d  call    cs:__imp_CloseHandle
0x18011fb73  mov     eax, edi
0x18011fb75  mov     rcx, [rbp+30h+var_20]
0x18011fb79  xor     rcx, rsp; StackCookie
0x18011fb7c  call    __security_check_cookie
0x18011fb81  lea     r11, [rsp+130h+var_10]
0x18011fb89  mov     rbx, [r11+20h]
0x18011fb8d  mov     rsi, [r11+28h]
0x18011fb91  mov     rsp, r11
0x18011fb94  pop     r14
0x18011fb96  pop     rdi
0x18011fb97  pop     rbp
0x18011fb98  retn
```
