# UserService::CDPInitializePhase2Internal(void)

- ea: `0x18001c94c`
- end: `0x18001cc09`
- name: `?CDPInitializePhase2Internal@UserService@@AEAAJXZ`
- size: `701`
- prototype: `__int64 __fastcall(UserService *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002584c`

## callees

- `0x180003678`
- `0x180006494`
- `0x1800097d0`
- `0x18001c94c`
- `0x18001cc10`
- `0x180024f14`
- `0x1800251dc`
- `0x180043988`
- `0x180057438`
- `0x180057e18`
- `0x180058f2c`
- `0x180059f70`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001cbf8`
- `msvcp_win!_Mtx_unlock` at `0x18001cbf8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c9ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c9ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ca11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ca77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ca11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ca77`
- `cdp!CDPInitializeUserServicePhase2` at `0x18001cb40`
- `cdp!CDPInitializeUserServicePhase2` at `0x18001cb40`
- `cdp!CDPSetAccountProviderInternal` at `0x18001ca56`
- `cdp!CDPSetAccountProviderInternal` at `0x18001ca56`
- `cdp!CDPCreateAccountProviderInternal` at `0x18001c9f0`
- `cdp!CDPCreateAccountProviderInternal` at `0x18001c9f0`
- `cdp!CDPInitializeUserService` at `0x18001cb00`
- `cdp!CDPInitializeUserService` at `0x18001cb00`

## string_xrefs

- `0x18001c9fc`: `..\userservice.cpp`
- `0x18001ca62`: `..\userservice.cpp`
- `0x18001cb23`: `{"hr":"0x%08x","file":"%s","line":%d,"text":"CDPInitializeUserService failed"}`
- `0x18001cb63`: `{"hr":"0x%08x","file":"%s","line":%d,"text":"CDPInitializeUserServicePhase2 failed"}`
- `0x18001c9cf`: `{"hr":"0x%08x","file":"%s","line":%d,"text":"CDPComResourcePolicyBroker init failed"}`
- `0x18001ca1d`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu","text":"CDPCreateAccountProviderInternal failed"}`
- `0x18001ca83`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu","text":"CDPSetAccountProviderInternal failed"}`
- `0x18001cab8`: `{"hr":"0x%08x","file":"%s","line":%d,"text":"CreateCdpResourceHandlers failed"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserService::CDPInitializePhase2Internal(UserService *this)
{
  struct _Mtx_internal_imp_t *v2; // rsi
  __int64 v3; // rcx
  __int64 v4; // r9
  int v5; // ebx
  DWORD v6; // ecx
  const char *v7; // rdx
  UserService *v8; // rcx
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v11; // r9
  int v12; // eax
  __int64 v13; // r9
  UserService *v14; // rcx
  const char *v15; // rdx
  int v16; // eax
  __int64 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  std::_Ref_count_base *v20; // rcx
  const char *v22; // [rsp+30h] [rbp-18h] BYREF
  std::_Ref_count_base *v23; // [rsp+38h] [rbp-10h] BYREF
  int v24; // [rsp+70h] [rbp+28h] BYREF
  __int64 CurrentThreadId; // [rsp+78h] [rbp+30h] BYREF
  __int64 v26; // [rsp+80h] [rbp+38h] BYREF
  char *v27; // [rsp+88h] [rbp+40h]

  v2 = (UserService *)((char *)this + 128);
  v27 = (char *)this + 128;
  std::_Mutex_base::lock((UserService *)((char *)this + 128));
  if ( (_BYTE)byte_1800A3698 )
    goto LABEL_31;
  if ( *((_BYTE *)this + 232) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 224);
    LODWORD(CurrentThreadId) = CoCreateInstance(
                                 &GUID_eb887a2b_2dab_437e_9b80_a726333391f0,
                                 0,
                                 0x17u,
                                 &GUID_aa5555f2_8825_4d5d_a35e_df73844c0806,
                                 (LPVOID *)this + 28);
    if ( (int)CurrentThreadId < 0 )
    {
      v24 = 477;
      Log<long &,char const (&)[19],int>(
        v3,
        "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"CDPComResourcePolicyBroker init failed\"}",
        (unsigned int *)&CurrentThreadId,
        v4,
        &v24);
    }
  }
  v26 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v5 = CDPCreateAccountProviderInternal(&v26);
  if ( v5 >= 0 )
  {
    v5 = CDPSetAccountProviderInternal(v26);
    if ( v5 < 0 )
    {
      v22 = "..\\userservice.cpp";
      LODWORD(v23) = 482;
      v24 = v5;
      CurrentThreadId = GetCurrentThreadId();
      v7 = "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"CDPSetAccountProviderInternal failed\"}";
      goto LABEL_7;
    }
    if ( *((_BYTE *)this + 232) )
    {
      LODWORD(CurrentThreadId) = UserService::CreateCdpResourceHandlers(this);
      if ( (int)CurrentThreadId < 0 )
      {
        v24 = 490;
        Log<long &,char const (&)[19],int>(
          (__int64)v8,
          "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"CreateCdpResourceHandlers failed\"}",
          (unsigned int *)&CurrentThreadId,
          v9,
          &v24);
      }
    }
    LODWORD(CurrentThreadId) = UserService::RegisterCloudDataConflictResolver(v8);
    if ( (int)CurrentThreadId < 0 )
    {
      v24 = 494;
      Log<long &,char const (&)[19],int>(
        v10,
        "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"RegisterCloudDataConflictResolver failed\"}",
        (unsigned int *)&CurrentThreadId,
        v11,
        &v24);
    }
    LOBYTE(v10) = *((_BYTE *)this + 232) != 0 ? -1 : 2;
    v12 = CDPInitializeUserService(v10);
    LOBYTE(v14) = (_BYTE)byte_1800A3698;
    if ( (_BYTE)byte_1800A3698 )
      goto LABEL_30;
    LODWORD(CurrentThreadId) = v12;
    if ( v12 >= 0 )
    {
      UserService::WaitForShellReady(v14);
      if ( (_BYTE)byte_1800A3698 || (v16 = CDPInitializeUserServicePhase2(), (LOBYTE(v14) = (_BYTE)byte_1800A3698) != 0) )
      {
LABEL_30:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
LABEL_31:
        v5 = 0;
        goto LABEL_32;
      }
      LODWORD(CurrentThreadId) = v16;
      if ( v16 >= 0 )
      {
LABEL_23:
        if ( *((_BYTE *)this + 232) )
        {
          v17 = (__int64 *)std::make_shared<WindowsCdpSettingsListener,>(&v22);
          v18 = *v17;
          v19 = v17[1];
          *v17 = 0;
          v17[1] = 0;
          *((_QWORD *)this + 26) = v18;
          v20 = (std::_Ref_count_base *)*((_QWORD *)this + 27);
          *((_QWORD *)this + 27) = v19;
          if ( v20 )
            std::_Ref_count_base::_Decref(v20);
          if ( v23 )
            std::_Ref_count_base::_Decref(v23);
          WindowsCdpSettingsListener::Subscribe(*((WindowsCdpSettingsListener **)this + 26));
        }
        UserService::DelaySetupUserInfoForAdvertisement(this, &v24);
        goto LABEL_30;
      }
      v24 = 522;
      v15 = "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"CDPInitializeUserServicePhase2 failed\"}";
    }
    else
    {
      v24 = 503;
      v15 = "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"CDPInitializeUserService failed\"}";
    }
    Log<long &,char const (&)[19],int>((__int64)v14, v15, (unsigned int *)&CurrentThreadId, v13, &v24);
    goto LABEL_23;
  }
  v22 = "..\\userservice.cpp";
  LODWORD(v23) = 481;
  v24 = v5;
  v6 = GetCurrentThreadId();
  CurrentThreadId = v6;
  v7 = "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"CDPCreateAccountProviderInternal failed\"}";
LABEL_7:
  Log<long &,char const * &,int &,unsigned __int64>(
    v6,
    (_DWORD)v7,
    (unsigned int)&v24,
    (unsigned int)&v22,
    (__int64)&v23,
    (__int64)&CurrentThreadId);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
LABEL_32:
  _Mtx_unlock(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001c94c  push    rbp
0x18001c94e  push    rbx
0x18001c94f  push    rsi
0x18001c950  push    rdi
0x18001c951  mov     rbp, rsp
0x18001c954  sub     rsp, 48h
0x18001c958  mov     rdi, rcx
0x18001c95b  lea     rsi, [rcx+80h]
0x18001c962  mov     [rbp+arg_18], rsi
0x18001c966  mov     rcx, rsi; this
0x18001c969  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001c96e  nop
0x18001c96f  mov     al, cs:byte_1800A3698
0x18001c975  nop
0x18001c976  test    al, al
0x18001c978  jnz     loc_18001CBF3
0x18001c97e  cmp     [rdi+0E8h], al
0x18001c984  jz      short loc_18001C9DB
0x18001c986  lea     rbx, [rdi+0E0h]
0x18001c98d  mov     rcx, rbx
0x18001c990  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c995  mov     [rsp+48h+ppv], rbx; ppv
0x18001c99a  lea     r9, _GUID_aa5555f2_8825_4d5d_a35e_df73844c0806; riid
0x18001c9a1  xor     edx, edx; pUnkOuter
0x18001c9a3  lea     r8d, [rdx+17h]; dwClsContext
0x18001c9a7  lea     rcx, _GUID_eb887a2b_2dab_437e_9b80_a726333391f0; rclsid
0x18001c9ae  call    cs:__imp_CoCreateInstance
0x18001c9b4  mov     dword ptr [rbp+arg_8], eax
0x18001c9b7  test    eax, eax
0x18001c9b9  jns     short loc_18001C9DB
0x18001c9bb  mov     [rbp+arg_0], 1DDh
0x18001c9c2  lea     rax, [rbp+arg_0]
0x18001c9c6  mov     [rsp+48h+ppv], rax
0x18001c9cb  lea     r8, [rbp+arg_8]
0x18001c9cf  lea     rdx, aHr0x08xFileSLi_12; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18001c9d6  call    ??$Log@AEAJAEAY0BD@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BD@$$CBD$$QEAH@Z; Log<long &,char const (&)[19],int>(CDPLogLevel,char const *,long &,char const (&)[19],int &&)
0x18001c9db  mov     [rbp+arg_10], 0
0x18001c9e3  lea     rcx, [rbp+arg_10]
0x18001c9e7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c9ec  lea     rcx, [rbp+arg_10]
0x18001c9f0  call    cs:__imp_CDPCreateAccountProviderInternal
0x18001c9f6  mov     ebx, eax
0x18001c9f8  test    eax, eax
0x18001c9fa  jns     short loc_18001CA52
0x18001c9fc  lea     rax, aUserserviceCpp; "..\\userservice.cpp"
0x18001ca03  mov     [rbp+var_18], rax
0x18001ca07  mov     dword ptr [rbp+var_10], 1E1h
0x18001ca0e  mov     [rbp+arg_0], ebx
0x18001ca11  call    cs:__imp_GetCurrentThreadId
0x18001ca17  mov     ecx, eax
0x18001ca19  mov     [rbp+arg_8], rcx
0x18001ca1d  lea     rdx, aHr0x08xFileSLi_5; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18001ca24  lea     rax, [rbp+arg_8]
0x18001ca28  mov     [rsp+48h+var_20], rax
0x18001ca2d  lea     rax, [rbp+var_10]
0x18001ca31  lea     r8, [rbp+arg_0]
0x18001ca35  lea     r9, [rbp+var_18]
0x18001ca39  mov     [rsp+48h+ppv], rax
0x18001ca3e  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18001ca43  nop
0x18001ca44  lea     rcx, [rbp+arg_10]
0x18001ca48  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ca4d  jmp     loc_18001CBF5
0x18001ca52  mov     rcx, [rbp+arg_10]
0x18001ca56  call    cs:__imp_CDPSetAccountProviderInternal
0x18001ca5c  mov     ebx, eax
0x18001ca5e  test    eax, eax
0x18001ca60  jns     short loc_18001CA8C
0x18001ca62  lea     rax, aUserserviceCpp; "..\\userservice.cpp"
0x18001ca69  mov     [rbp+var_18], rax
0x18001ca6d  mov     dword ptr [rbp+var_10], 1E2h
0x18001ca74  mov     [rbp+arg_0], ebx
0x18001ca77  call    cs:__imp_GetCurrentThreadId
0x18001ca7d  mov     eax, eax
0x18001ca7f  mov     [rbp+arg_8], rax
0x18001ca83  lea     rdx, aHr0x08xFileSLi; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18001ca8a  jmp     short loc_18001CA24
0x18001ca8c  cmp     byte ptr [rdi+0E8h], 0
0x18001ca93  jz      short loc_18001CAC4
0x18001ca95  mov     rcx, rdi; this
0x18001ca98  call    ?CreateCdpResourceHandlers@UserService@@AEAAJXZ; UserService::CreateCdpResourceHandlers(void)
0x18001ca9d  mov     dword ptr [rbp+arg_8], eax
0x18001caa0  test    eax, eax
0x18001caa2  jns     short loc_18001CAC4
0x18001caa4  mov     [rbp+arg_0], 1EAh
0x18001caab  lea     rax, [rbp+arg_0]
0x18001caaf  mov     [rsp+48h+ppv], rax
0x18001cab4  lea     r8, [rbp+arg_8]
0x18001cab8  lea     rdx, aHr0x08xFileSLi_4; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18001cabf  call    ??$Log@AEAJAEAY0BD@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BD@$$CBD$$QEAH@Z; Log<long &,char const (&)[19],int>(CDPLogLevel,char const *,long &,char const (&)[19],int &&)
0x18001cac4  call    ?RegisterCloudDataConflictResolver@UserService@@AEAAJXZ; UserService::RegisterCloudDataConflictResolver(void)
0x18001cac9  mov     dword ptr [rbp+arg_8], eax
0x18001cacc  test    eax, eax
0x18001cace  jns     short loc_18001CAF0
0x18001cad0  mov     [rbp+arg_0], 1EEh
0x18001cad7  lea     rax, [rbp+arg_0]
0x18001cadb  mov     [rsp+48h+ppv], rax
0x18001cae0  lea     r8, [rbp+arg_8]
0x18001cae4  lea     rdx, aHr0x08xFileSLi_8; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18001caeb  call    ??$Log@AEAJAEAY0BD@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BD@$$CBD$$QEAH@Z; Log<long &,char const (&)[19],int>(CDPLogLevel,char const *,long &,char const (&)[19],int &&)
0x18001caf0  mov     al, [rdi+0E8h]
0x18001caf6  neg     al
0x18001caf8  sbb     cl, cl
0x18001cafa  and     cl, 0FDh
0x18001cafd  add     cl, 2
0x18001cb00  call    cs:__imp_CDPInitializeUserService
0x18001cb06  mov     cl, cs:byte_1800A3698; this
0x18001cb0c  nop
0x18001cb0d  test    cl, cl
0x18001cb0f  jnz     loc_18001CBEA
0x18001cb15  mov     dword ptr [rbp+arg_8], eax
0x18001cb18  test    eax, eax
0x18001cb1a  jns     short loc_18001CB2C
0x18001cb1c  mov     [rbp+arg_0], 1F7h
0x18001cb23  lea     rdx, aHr0x08xFileSLi_2; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18001cb2a  jmp     short loc_18001CB6A
0x18001cb2c  call    ?WaitForShellReady@UserService@@AEAAXXZ; UserService::WaitForShellReady(void)
0x18001cb31  mov     al, cs:byte_1800A3698
0x18001cb37  nop
0x18001cb38  test    al, al
0x18001cb3a  jnz     loc_18001CBEA
0x18001cb40  call    cs:__imp_CDPInitializeUserServicePhase2
0x18001cb46  mov     cl, cs:byte_1800A3698
0x18001cb4c  nop
0x18001cb4d  test    cl, cl
0x18001cb4f  jnz     loc_18001CBEA
0x18001cb55  mov     dword ptr [rbp+arg_8], eax
0x18001cb58  test    eax, eax
0x18001cb5a  jns     short loc_18001CB7C
0x18001cb5c  mov     [rbp+arg_0], 20Ah
0x18001cb63  lea     rdx, aHr0x08xFileSLi_9; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18001cb6a  lea     rax, [rbp+arg_0]
0x18001cb6e  mov     [rsp+48h+ppv], rax
0x18001cb73  lea     r8, [rbp+arg_8]
0x18001cb77  call    ??$Log@AEAJAEAY0BD@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BD@$$CBD$$QEAH@Z; Log<long &,char const (&)[19],int>(CDPLogLevel,char const *,long &,char const (&)[19],int &&)
0x18001cb7c  cmp     byte ptr [rdi+0E8h], 0
0x18001cb83  jz      short loc_18001CBDD
0x18001cb85  lea     rcx, [rbp+var_18]
0x18001cb89  call    ??$make_shared@VWindowsCdpSettingsListener@@$$V@std@@YA?AV?$shared_ptr@VWindowsCdpSettingsListener@@@0@XZ; std::make_shared<WindowsCdpSettingsListener,>(void)
0x18001cb8e  mov     rcx, [rax]
0x18001cb91  mov     rdx, [rax+8]
0x18001cb95  mov     qword ptr [rax], 0
0x18001cb9c  mov     qword ptr [rax+8], 0
0x18001cba4  mov     [rdi+0D0h], rcx
0x18001cbab  mov     rcx, [rdi+0D8h]; this
0x18001cbb2  mov     [rdi+0D8h], rdx
0x18001cbb9  test    rcx, rcx
0x18001cbbc  jz      short loc_18001CBC3
0x18001cbbe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001cbc3  mov     rcx, [rbp+var_10]; this
0x18001cbc7  test    rcx, rcx
0x18001cbca  jz      short loc_18001CBD1
0x18001cbcc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001cbd1  mov     rcx, [rdi+0D0h]; this
0x18001cbd8  call    ?Subscribe@WindowsCdpSettingsListener@@QEAAXXZ; WindowsCdpSettingsListener::Subscribe(void)
0x18001cbdd  lea     rdx, [rbp+arg_0]
0x18001cbe1  mov     rcx, rdi
0x18001cbe4  call    ?DelaySetupUserInfoForAdvertisement@UserService@@AEAA?AUfire_and_forget@winrt@@XZ; UserService::DelaySetupUserInfoForAdvertisement(void)
0x18001cbe9  nop
0x18001cbea  lea     rcx, [rbp+arg_10]
0x18001cbee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001cbf3  xor     ebx, ebx
0x18001cbf5  mov     rcx, rsi; _Mtx_t
0x18001cbf8  call    cs:__imp__Mtx_unlock
0x18001cbfe  mov     eax, ebx
0x18001cc00  add     rsp, 48h
0x18001cc04  pop     rdi
0x18001cc05  pop     rsi
0x18001cc06  pop     rbx
0x18001cc07  pop     rbp
0x18001cc08  retn
```
