# CProfMgr::OnLogoff(_SN_ONLOGOFF_PARAMS *)

- ea: `0x180002da0`
- end: `0x18000302c`
- name: `?OnLogoff@CProfMgr@@UEAAJPEAU_SN_ONLOGOFF_PARAMS@@@Z`
- size: `652`
- prototype: `__int64 __fastcall(CProfMgr *__hidden this, struct _SN_ONLOGOFF_PARAMS *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180002da0`
- `0x180003f30`
- `0x180004620`
- `0x180019b38`
- `0x180030eb8`
- `0x180031120`
- `0x180031a54`
- `0x1800335f8`
- `0x1800339f0`
- `0x1800462fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002eb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000301d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002eb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000301d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002e2f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002e2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002e13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002e13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003002`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003002`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ff4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ff4`
- `RPCRT4!RpcImpersonateClient` at `0x180002df1`
- `RPCRT4!RpcImpersonateClient` at `0x180002df1`
- `RPCRT4!RpcRevertToSelf` at `0x180002e52`
- `RPCRT4!RpcRevertToSelf` at `0x180002e52`

## string_xrefs

- `0x180002e0a`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180002e8e`: `CRpcUtils::GetClientToken`
- `0x180002e87`: `OpenThreadToken failed: 0x%x in %s`
- `0x180002ed6`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x180002f0e`: `GetUserSidFromUserToken() failed: 0x%x in %s`
- `0x180002f42`: `CRdshUvhdConfigurationProvider::CreateInstance() failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CProfMgr::OnLogoff(CProfMgr *this, struct _SN_ONLOGOFF_PARAMS *a2)
{
  __int64 v2; // rdx
  RPC_STATUS v3; // eax
  signed int v4; // edi
  __int64 v5; // rcx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v8; // eax
  bool v9; // sf
  void *v10; // rax
  void *v11; // rbx
  int UserSidFromUserToken; // eax
  int v13; // eax
  struct RdVhd::Uvhd::IUvhdConfigurationProvider *v14; // rsi
  const unsigned __int16 *v15; // rax
  int v16; // eax
  ULONGLONG v17; // rax
  __int64 v18; // rdx
  char v19; // r10
  int v20; // r11d
  void *v21; // rsi
  HANDLE ProcessHeap; // rax
  const int *v24; // [rsp+30h] [rbp-48h] BYREF
  int v25; // [rsp+38h] [rbp-40h]
  __int64 v26; // [rsp+3Ch] [rbp-3Ch]
  int v27; // [rsp+44h] [rbp-34h]
  LPVOID lpMem; // [rsp+48h] [rbp-30h]
  int v29; // [rsp+50h] [rbp-28h]
  void *TokenHandle; // [rsp+88h] [rbp+10h] BYREF
  RdVhd::Uvhd::IUvhdConfigurationProvider *v31; // [rsp+90h] [rbp+18h] BYREF

  v2 = *((unsigned int *)a2 + 2);
  v24 = &CBaseStringT<unsigned short>::`vftable';
  v26 = 128;
  lpMem = 0;
  v27 = 0;
  v29 = 0x8000000;
  v25 = 0;
  v31 = 0;
  CUVHDProfileTelemetryLogging::LogSessionUsage(1, v2);
  TokenHandle = 0;
  v3 = RpcImpersonateClient(0);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      v4 = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    v8 = RpcRevertToSelf();
    v9 = v8 < 0;
    if ( v8 > 0 )
    {
      v8 = (unsigned __int16)v8 | 0x80070000;
      v9 = v8 < 0;
    }
    if ( v9 )
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v8);
      v4 = -2147024891;
    }
    else
    {
      if ( v4 >= 0 )
      {
        v10 = TokenHandle;
        goto LABEL_18;
      }
      _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", (unsigned int)v4, "CRpcUtils::GetClientToken");
    }
  }
  else
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", (unsigned int)v4, "CRpcUtils::GetClientToken");
  }
  v10 = TokenHandle;
  if ( TokenHandle )
  {
    v11 = 0;
    CloseHandle(TokenHandle);
    goto LABEL_19;
  }
LABEL_18:
  v11 = v10;
LABEL_19:
  if ( v4 >= 0 )
  {
    UserSidFromUserToken = CProfMgr::GetUserSidFromUserToken(v5, v11, &v24);
    v4 = UserSidFromUserToken;
    if ( UserSidFromUserToken >= 0 )
    {
      v13 = CRdshUvhdConfigurationProvider::CreateInstance(&v31);
      v14 = v31;
      v4 = v13;
      if ( v13 >= 0 )
      {
        v15 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v24);
        v16 = RdVhd::Uvhd::CUvhdProfileManager::DisconnectUserProfileVhd(v15, v11, v14);
        v4 = v16;
        if ( v16 < 0 )
        {
          CUVHDProfileTelemetryLogging::LogFailedDisconnectUserProfileVhd(v16);
          v17 = CBaseStringT<unsigned short>::PContents(&v24);
          CrimsonHelper::RaiseEvent<unsigned short const *,long,long>(
            (CrimsonHelper *)&CrimsonHelper::s_instance,
            v18,
            v17,
            v20,
            v19);
          _DbgPrintMessage(
            8,
            "CUvhdProfileManager::DisconnectUserProfileVhd failed: 0x%x in %s",
            (unsigned int)v4,
            "CProfMgr::OnLogoff");
        }
      }
      else
      {
        _DbgPrintMessage(
          8,
          "CRdshUvhdConfigurationProvider::CreateInstance() failed: 0x%x in %s",
          (unsigned int)v13,
          "CProfMgr::OnLogoff");
      }
      if ( v14 )
        RdVhd::Uvhd::IUvhdConfigurationProvider::`scalar deleting destructor'(v14, 1);
    }
    else
    {
      _DbgPrintMessage(8, "GetUserSidFromUserToken() failed: 0x%x in %s", UserSidFromUserToken, "CProfMgr::OnLogoff");
    }
    v21 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v21);
    }
  }
  else
  {
    _DbgPrintMessage(8, "CRpcUtils::GetClientToken failed: 0x%x in %s", v4, "CProfMgr::OnLogoff");
  }
  if ( v11 )
    CloseHandle(v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002da0  mov     r11, rsp
0x180002da3  push    rbx
0x180002da4  push    rdi
0x180002da5  sub     rsp, 68h
0x180002da9  mov     edx, [rdx+8]
0x180002dac  lea     rax, ??_7?$CBaseStringT@G@@6B@; const CBaseStringT<ushort>::`vftable'
0x180002db3  mov     [r11-48h], rax
0x180002db7  mov     ecx, 1
0x180002dbc  mov     qword ptr [r11-3Ch], 80h
0x180002dc4  mov     [r11+8], rbp
0x180002dc8  xor     ebp, ebp
0x180002dca  mov     [r11-30h], rbp
0x180002dce  mov     [rsp+78h+var_34], ebp
0x180002dd2  mov     [rsp+78h+var_28], 8000000h
0x180002dda  mov     [rsp+78h+var_40], ebp
0x180002dde  mov     [r11+18h], rbp
0x180002de2  call    ?LogSessionUsage@CUVHDProfileTelemetryLogging@@SAXW4_RD_TELEMETRY_SESSION_EVENT_CODE@@K@Z; CUVHDProfileTelemetryLogging::LogSessionUsage(_RD_TELEMETRY_SESSION_EVENT_CODE,ulong)
0x180002de7  xor     ecx, ecx; BindingHandle
0x180002de9  mov     [rsp+78h+TokenHandle], rbp
0x180002df1  call    cs:__imp_RpcImpersonateClient
0x180002df7  mov     edi, eax
0x180002df9  test    eax, eax
0x180002dfb  jle     short loc_180002E06
0x180002dfd  movzx   edi, ax
0x180002e00  or      edi, 80070000h
0x180002e06  test    edi, edi
0x180002e08  jns     short loc_180002E13
0x180002e0a  lea     rdx, aRpcimpersonate_0; "RpcImpersonateClient failed: 0x%x in %s"
0x180002e11  jmp     short loc_180002E8E
0x180002e13  call    cs:__imp_GetCurrentThread
0x180002e19  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x180002e21  mov     edx, 0Eh; DesiredAccess
0x180002e26  mov     rcx, rax; ThreadHandle
0x180002e29  mov     r8d, 1; OpenAsSelf
0x180002e2f  call    cs:__imp_OpenThreadToken
0x180002e35  test    eax, eax
0x180002e37  jnz     short loc_180002E50
0x180002e39  call    cs:__imp_GetLastError
0x180002e3f  mov     edi, eax
0x180002e41  test    eax, eax
0x180002e43  jle     short loc_180002E52
0x180002e45  movzx   edi, ax
0x180002e48  or      edi, 80070000h
0x180002e4e  jmp     short loc_180002E52
0x180002e50  mov     edi, ebp
0x180002e52  call    cs:__imp_RpcRevertToSelf
0x180002e58  test    eax, eax
0x180002e5a  jle     short loc_180002E66
0x180002e5c  movzx   eax, ax
0x180002e5f  or      eax, 80070000h
0x180002e64  test    eax, eax
0x180002e66  jns     short loc_180002E83
0x180002e68  mov     r8d, eax
0x180002e6b  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x180002e72  mov     ecx, 8; int
0x180002e77  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002e7c  mov     edi, 80070005h
0x180002e81  jmp     short loc_180002EA2
0x180002e83  test    edi, edi
0x180002e85  jns     short loc_180002EBD
0x180002e87  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x180002e8e  lea     r9, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken"
0x180002e95  mov     r8d, edi
0x180002e98  mov     ecx, 8; int
0x180002e9d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002ea2  mov     rax, [rsp+78h+TokenHandle]
0x180002eaa  test    rax, rax
0x180002ead  jz      short loc_180002EC5
0x180002eaf  mov     rcx, rax; hObject
0x180002eb2  mov     rbx, rbp
0x180002eb5  call    cs:__imp_CloseHandle
0x180002ebb  jmp     short loc_180002EC8
0x180002ebd  mov     rax, [rsp+78h+TokenHandle]
0x180002ec5  mov     rbx, rax
0x180002ec8  test    edi, edi
0x180002eca  jns     short loc_180002EEC
0x180002ecc  lea     r9, aCprofmgrOnlogo_0; "CProfMgr::OnLogoff"
0x180002ed3  mov     r8d, edi
0x180002ed6  lea     rdx, aCrpcutilsGetcl_4; "CRpcUtils::GetClientToken failed: 0x%x "...
0x180002edd  mov     ecx, 8; int
0x180002ee2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002ee7  jmp     loc_18000300D
0x180002eec  lea     r8, [rsp+78h+var_48]
0x180002ef1  mov     [rsp+78h+var_18], rsi
0x180002ef6  mov     rdx, rbx
0x180002ef9  call    ?GetUserSidFromUserToken@CProfMgr@@AEAAJPEAXAEAV?$CBaseStringT@G@@@Z; CProfMgr::GetUserSidFromUserToken(void *,CBaseStringT<ushort> &)
0x180002efe  mov     edi, eax
0x180002f00  test    eax, eax
0x180002f02  jns     short loc_180002F24
0x180002f04  lea     r9, aCprofmgrOnlogo_0; "CProfMgr::OnLogoff"
0x180002f0b  mov     r8d, eax
0x180002f0e  lea     rdx, aGetusersidfrom; "GetUserSidFromUserToken() failed: 0x%x "...
0x180002f15  mov     ecx, 8; int
0x180002f1a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002f1f  jmp     loc_180002FEA
0x180002f24  lea     rcx, [rsp+78h+arg_10]; struct CRdshUvhdConfigurationProvider **
0x180002f2c  call    ?CreateInstance@CRdshUvhdConfigurationProvider@@SAJPEAPEAV1@@Z; CRdshUvhdConfigurationProvider::CreateInstance(CRdshUvhdConfigurationProvider * *)
0x180002f31  mov     rsi, [rsp+78h+arg_10]
0x180002f39  mov     edi, eax
0x180002f3b  test    eax, eax
0x180002f3d  jns     short loc_180002F4B
0x180002f3f  mov     r8d, eax
0x180002f42  lea     rdx, aCrdshuvhdconfi_2; "CRdshUvhdConfigurationProvider::CreateI"...
0x180002f49  jmp     short loc_180002FC7
0x180002f4b  lea     rcx, [rsp+78h+var_48]
0x180002f50  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180002f55  mov     r8, rsi; struct RdVhd::Uvhd::IUvhdConfigurationProvider *
0x180002f58  mov     rdx, rbx; void *
0x180002f5b  mov     rcx, rax; unsigned __int16 *
0x180002f5e  call    ?DisconnectUserProfileVhd@CUvhdProfileManager@Uvhd@RdVhd@@SAJPEBGPEAXPEAVIUvhdConfigurationProvider@23@@Z; RdVhd::Uvhd::CUvhdProfileManager::DisconnectUserProfileVhd(ushort const *,void *,RdVhd::Uvhd::IUvhdConfigurationProvider *)
0x180002f63  mov     edi, eax
0x180002f65  test    eax, eax
0x180002f67  jns     short loc_180002FD8
0x180002f69  mov     ecx, eax; int
0x180002f6b  call    ?LogFailedDisconnectUserProfileVhd@CUVHDProfileTelemetryLogging@@SAXJ@Z; CUVHDProfileTelemetryLogging::LogFailedDisconnectUserProfileVhd(long)
0x180002f70  mov     r10d, edi
0x180002f73  movzx   r11d, di
0x180002f77  sar     r10d, 10h
0x180002f7b  mov     ecx, edi
0x180002f7d  and     r10d, 7FFh
0x180002f84  and     ecx, 78000000h
0x180002f8a  cmp     ecx, 50000000h
0x180002f90  cmovnz  r10d, ebp
0x180002f94  test    r10d, r10d
0x180002f97  jnz     short loc_180002F9C
0x180002f99  mov     r11d, edi
0x180002f9c  lea     rcx, [rsp+78h+var_48]
0x180002fa1  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180002fa6  mov     r9d, r11d
0x180002fa9  mov     [rsp+78h+var_58], r10d
0x180002fae  mov     r8, rax
0x180002fb1  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180002fb8  call    ??$RaiseEvent@PEBGJJ@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEBGJJ@Z; CrimsonHelper::RaiseEvent<ushort const *,long,long>(_EVENT_DESCRIPTOR const &,ushort const *,long,long)
0x180002fbd  mov     r8d, edi
0x180002fc0  lea     rdx, aCuvhdprofilema; "CUvhdProfileManager::DisconnectUserProf"...
0x180002fc7  lea     r9, aCprofmgrOnlogo_0; "CProfMgr::OnLogoff"
0x180002fce  mov     ecx, 8; int
0x180002fd3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002fd8  test    rsi, rsi
0x180002fdb  jz      short loc_180002FEA
0x180002fdd  mov     edx, 1; unsigned int
0x180002fe2  mov     rcx, rsi; this
0x180002fe5  call    ??_GIUvhdConfigurationProvider@Uvhd@RdVhd@@UEAAPEAXI@Z; RdVhd::Uvhd::IUvhdConfigurationProvider::`scalar deleting destructor'(uint)
0x180002fea  mov     rsi, [rsp+78h+lpMem]
0x180002fef  test    rsi, rsi
0x180002ff2  jz      short loc_180003008
0x180002ff4  call    cs:__imp_GetProcessHeap
0x180002ffa  mov     r8, rsi; lpMem
0x180002ffd  xor     edx, edx; dwFlags
0x180002fff  mov     rcx, rax; hHeap
0x180003002  call    cs:__imp_HeapFree
0x180003008  mov     rsi, [rsp+78h+var_18]
0x18000300d  mov     rbp, [rsp+78h+arg_0]
0x180003015  test    rbx, rbx
0x180003018  jz      short loc_180003023
0x18000301a  mov     rcx, rbx; hObject
0x18000301d  call    cs:__imp_CloseHandle
0x180003023  mov     eax, edi
0x180003025  add     rsp, 68h
0x180003029  pop     rdi
0x18000302a  pop     rbx
0x18000302b  retn
```
