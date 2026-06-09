# PrecacheStoreLicenseForPackageResume2

- ea: `0x180010cc0`
- end: `0x1800111f1`
- name: `PrecacheStoreLicenseForPackageResume2`
- size: `1329`
- prototype: `__int64 __fastcall(__int64, signed int, void *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800011d4`
- `0x180001960`
- `0x180006cb4`
- `0x180006f7c`
- `0x18000762c`
- `0x180007858`
- `0x18000bdc0`
- `0x18000bde0`
- `0x18000be00`
- `0x18000be7c`
- `0x18000e9c4`
- `0x18000ee24`
- `0x18000efb4`
- `0x180010cc0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001112b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001117a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001112b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001117a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010e01`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010e01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010de5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010de5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010e0c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010e0c`
- `RPCRT4!NdrClientCall3` at `0x180010eae`
- `RPCRT4!NdrClientCall3` at `0x180010f69`
- `RPCRT4!NdrClientCall3` at `0x180010fc3`
- `RPCRT4!NdrClientCall3` at `0x180010eae`
- `RPCRT4!NdrClientCall3` at `0x180010f69`
- `RPCRT4!NdrClientCall3` at `0x180010fc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180010cf2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800110a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180010cf2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800110a4`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x180010d29`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x180010d29`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserTokenFromSid` at `0x180010dba`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserTokenFromSid` at `0x180010dba`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PrecacheStoreLicenseForPackageResume2(__int64 a1, signed int a2, void *a3)
{
  signed int v4; // r14d
  ULONGLONG TickCount64; // r12
  unsigned int v7; // edi
  __int64 result; // rax
  HANDLE v9; // rbx
  HANDLE CurrentThread; // rax
  __int64 v11; // rbx
  int v12; // eax
  signed int v13; // ebx
  unsigned int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  __int64 RpcHandle; // rbx
  int Pointer; // eax
  int v19; // eax
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  signed int v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  signed int v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  signed int LastError; // eax
  int v30; // edx
  unsigned int v31; // r8d
  signed int v32; // eax
  int v33; // edx
  unsigned int v34; // r8d
  signed int v35; // eax
  int v36; // edx
  unsigned int v37; // r8d
  signed int v38; // eax
  int v39; // edx
  unsigned int v40; // r8d
  wil *v41; // rcx
  __int64 v42; // [rsp+0h] [rbp-208h] BYREF
  __int64 v43; // [rsp+28h] [rbp-1E0h]
  unsigned __int16 *v44; // [rsp+40h] [rbp-1C8h] BYREF
  __int64 v45; // [rsp+48h] [rbp-1C0h]
  signed int v46; // [rsp+50h] [rbp-1B8h] BYREF
  signed int v47; // [rsp+58h] [rbp-1B0h] BYREF
  int v48; // [rsp+60h] [rbp-1A8h] BYREF
  ULONGLONG v49; // [rsp+68h] [rbp-1A0h] BYREF
  void **v50; // [rsp+70h] [rbp-198h] BYREF
  HANDLE Token; // [rsp+78h] [rbp-190h] BYREF
  void **v52; // [rsp+80h] [rbp-188h] BYREF
  __int64 v53; // [rsp+88h] [rbp-180h]
  void **v54; // [rsp+90h] [rbp-178h] BYREF
  __int64 v55; // [rsp+98h] [rbp-170h]
  void **v56; // [rsp+A0h] [rbp-168h] BYREF
  void *TokenHandle; // [rsp+A8h] [rbp-160h] BYREF
  bool v58; // [rsp+B0h] [rbp-158h]
  unsigned __int16 v59[128]; // [rsp+C0h] [rbp-148h] BYREF

  v4 = a2;
  v47 = a2;
  TickCount64 = GetTickCount64();
  v49 = TickCount64;
  v7 = 0;
  if ( !a1 )
    return 3221225485LL;
  v48 = 256;
  result = PsmGetPackageFullNameFromKey(a1, v59, &v48);
  if ( (int)result >= 0 )
  {
    if ( BypassServiceResponse(v59) )
      return 0;
    if ( StoreAppsAreDisabled() )
      return 3221226340LL;
    if ( !InvokeLicenseManagerRequired(v59, a3, 0) )
      return 0;
    try
    {
      GetSidString((__int64)&v52, a3);
      v44 = (unsigned __int16 *)&Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
      v45 = 0;
      v50 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      Token = 0;
      if ( (int)UMgrQueryUserTokenFromSid(v53, &Token) < 0 )
      {
        RpcHandle = GetRpcHandle((__int64)&v54);
        v45 = *(_QWORD *)(RpcHandle + 8);
        *(_QWORD *)(RpcHandle + 8) = 0;
        v54 = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
        if ( v55 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(&v54) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v30, v31);
          __debugbreak();
        }
        LODWORD(v43) = v4;
        Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, v45, a1, v43, v53).Pointer;
        if ( Pointer >= 1 )
          Pointer |= 0x80010000;
        v13 = Pointer;
      }
      else
      {
        v9 = Token;
        v56 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
        TokenHandle = 0;
        v58 = 0;
        CurrentThread = GetCurrentThread();
        OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle);
        v58 = SetThreadToken(0, v9);
        v11 = GetRpcHandle((__int64)&v54);
        v45 = *(_QWORD *)(v11 + 8);
        *(_QWORD *)(v11 + 8) = 0;
        v54 = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
        if ( v55 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(&v54) )
        {
          v23 = GetLastError();
          if ( v23 > 0 )
            v23 = (unsigned __int16)v23 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
          v26 = GetLastError();
          if ( v26 > 0 )
            v26 = (unsigned __int16)v26 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
          __debugbreak();
        }
        LODWORD(v43) = v4;
        v12 = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, v45, a1, v43, v53).Pointer;
        v13 = v12;
        if ( v12 >= 1 )
          v13 = v12 | 0x80010000;
        OverrideImpersonationScope::~OverrideImpersonationScope((OverrideImpersonationScope *)&v56);
      }
      if ( v13 < 0 )
      {
        if ( (v13 & 0x1FFF0000) == 0x3F0000 || (v13 & 0x1FFF0000) == 0x7E10000 )
          goto LABEL_52;
        LODWORD(v43) = v4;
        v19 = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, v45, a1, v43, v53).Pointer;
        if ( v19 >= 1 )
          v19 |= 0x80010000;
        v13 = v19;
        if ( v19 < 0 )
LABEL_52:
          wil::details::in1diag3::_Throw_Hr((wil::details::in1diag3 *)0x348, v14, (const char *)(unsigned int)v13, v16);
      }
      v50 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( Token )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v50) )
        {
          v32 = GetLastError();
          if ( v32 > 0 )
            v32 = (unsigned __int16)v32 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v32, v33, v34);
          goto LABEL_56;
        }
        Token = 0;
      }
      v44 = (unsigned __int16 *)&Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
      if ( !v45 )
      {
LABEL_32:
        v52 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
        if ( !v53 || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v52) )
          goto LABEL_65;
LABEL_59:
        v38 = GetLastError();
        if ( v38 > 0 )
          v38 = (unsigned __int16)v38 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v38, v39, v40);
        JUMPOUT(0x1800111EFLL);
      }
      if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(&v44) )
      {
        v45 = 0;
        goto LABEL_32;
      }
LABEL_56:
      v35 = GetLastError();
      if ( v35 > 0 )
        v35 = (unsigned __int16)v35 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v35, v36, v37);
      goto LABEL_59;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException((wil::details::in1diag3 *)0x34C, (unsigned int)&v42, v15);
      v46 = wil::ResultFromCaughtException(v41);
      v7 = 0;
      v13 = v46;
      TickCount64 = v49;
      v4 = v47;
    }
LABEL_65:
    if ( (unsigned int)dword_18001A010 > 5
      && (qword_18001A020 & 0x400000000000LL) != 0
      && (qword_18001A028 & 0x400000000000LL) == qword_18001A028 )
    {
      v47 = v13;
      v49 = GetTickCount64() - TickCount64;
      v46 = v4;
      v44 = v59;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v20,
        (unsigned int)&unk_180016BF1,
        v21,
        v22,
        (__int64)&v44,
        (__int64)&v46,
        (__int64)&v49,
        (__int64)&v47);
    }
    if ( v13 < 0 )
      return v13 | 0x20000000u;
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180010cc0  push    rbx
0x180010cc2  push    rsi
0x180010cc3  push    rdi
0x180010cc4  push    r12
0x180010cc6  push    r13
0x180010cc8  push    r14
0x180010cca  push    r15
0x180010ccc  sub     rsp, 1D0h
0x180010cd3  mov     rax, cs:__security_cookie
0x180010cda  xor     rax, rsp
0x180010cdd  mov     [rsp+208h+var_48], rax
0x180010ce5  mov     rbx, r8
0x180010ce8  mov     r14d, edx
0x180010ceb  mov     r15, rcx
0x180010cee  mov     [rsp+208h+var_1B0], edx
0x180010cf2  call    cs:__imp_GetTickCount64
0x180010cf8  mov     r12, rax
0x180010cfb  mov     [rsp+208h+var_1A0], rax
0x180010d00  xor     edi, edi
0x180010d02  test    r15, r15
0x180010d05  jnz     short loc_180010D11
0x180010d07  mov     eax, 0C000000Dh
0x180010d0c  jmp     loc_180011108
0x180010d11  mov     [rsp+208h+var_1A8], 100h
0x180010d19  lea     r8, [rsp+208h+var_1A8]
0x180010d1e  lea     rdx, [rsp+208h+var_148]
0x180010d26  mov     rcx, r15
0x180010d29  call    cs:__imp_PsmGetPackageFullNameFromKey
0x180010d2f  test    eax, eax
0x180010d31  js      loc_180011108
0x180010d37  lea     rcx, [rsp+208h+var_148]; unsigned __int16 *
0x180010d3f  call    ?BypassServiceResponse@@YA_NPEBG@Z; BypassServiceResponse(ushort const *)
0x180010d44  test    al, al
0x180010d46  jnz     loc_180011106
0x180010d4c  call    ?StoreAppsAreDisabled@@YA_NXZ; StoreAppsAreDisabled(void)
0x180010d51  test    al, al
0x180010d53  jz      short loc_180010D5F
0x180010d55  mov     eax, 0C0000364h
0x180010d5a  jmp     loc_180011108
0x180010d5f  xor     r8d, r8d; bool
0x180010d62  mov     rdx, rbx; pSid
0x180010d65  lea     rcx, [rsp+208h+var_148]; unsigned __int16 *
0x180010d6d  call    ?InvokeLicenseManagerRequired@@YA_NPEBGPEAX_N@Z; InvokeLicenseManagerRequired(ushort const *,void *,bool)
0x180010d72  test    al, al
0x180010d74  jz      loc_180011106
0x180010d7a  mov     rdx, rbx
0x180010d7d  lea     rcx, [rsp+208h+var_188]
0x180010d85  call    ?GetSidString@@YA?AV?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@PEAX@Z; GetSidString(void *)
0x180010d8a  nop
0x180010d8b  lea     r13, ??_7?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable'
0x180010d92  mov     [rsp+208h+var_1C8], r13
0x180010d97  mov     [rsp+208h+var_1C0], rdi
0x180010d9c  lea     rsi, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180010da3  mov     [rsp+208h+var_198], rsi
0x180010da8  mov     [rsp+208h+Token], rdi
0x180010dad  lea     rdx, [rsp+208h+Token]
0x180010db2  mov     rcx, [rsp+208h+var_180]
0x180010dba  call    cs:__imp_UMgrQueryUserTokenFromSid
0x180010dc0  test    eax, eax
0x180010dc2  js      loc_180010ED3
0x180010dc8  mov     rbx, [rsp+208h+Token]
0x180010dcd  mov     [rsp+208h+var_168], rsi
0x180010dd5  mov     [rsp+208h+TokenHandle], rdi
0x180010ddd  mov     [rsp+208h+var_158], dil
0x180010de5  call    cs:__imp_GetCurrentThread
0x180010deb  lea     r9, [rsp+208h+TokenHandle]; TokenHandle
0x180010df3  mov     esi, 1
0x180010df8  mov     r8d, esi; OpenAsSelf
0x180010dfb  lea     edx, [rsi+3]; DesiredAccess
0x180010dfe  mov     rcx, rax; ThreadHandle
0x180010e01  call    cs:__imp_OpenThreadToken
0x180010e07  mov     rdx, rbx; Token
0x180010e0a  xor     ecx, ecx; Thread
0x180010e0c  call    cs:__imp_SetThreadToken
0x180010e12  test    eax, eax
0x180010e14  setnz   [rsp+208h+var_158]
0x180010e1c  lea     rcx, [rsp+208h+var_178]
0x180010e24  call    ?GetRpcHandle@@YA?AV?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@XZ; GetRpcHandle(void)
0x180010e29  mov     rbx, rax
0x180010e2c  cmp     [rsp+208h+var_1C0], rdi
0x180010e31  jz      short loc_180010E52
0x180010e33  mov     rcx, [rsp+208h+var_1C8]
0x180010e38  mov     rax, [rcx]
0x180010e3b  lea     rcx, [rsp+208h+var_1C8]
0x180010e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e45  test    al, al
0x180010e47  jz      loc_18001112B
0x180010e4d  mov     [rsp+208h+var_1C0], rdi
0x180010e52  mov     rax, [rbx+8]
0x180010e56  mov     [rsp+208h+var_1C0], rax
0x180010e5b  mov     [rbx+8], rdi
0x180010e5f  mov     [rsp+208h+var_178], r13
0x180010e67  cmp     [rsp+208h+var_170], rdi
0x180010e6f  jz      short loc_180010E86
0x180010e71  lea     rcx, [rsp+208h+var_178]
0x180010e79  call    ?InternalClose@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(void)
0x180010e7e  test    al, al
0x180010e80  jz      loc_180011146
0x180010e86  mov     rax, [rsp+208h+var_180]
0x180010e8e  mov     [rsp+208h+var_1D8], rax
0x180010e93  mov     dword ptr [rsp+208h+var_1E0], r14d
0x180010e98  mov     [rsp+208h+var_1E8], r15
0x180010e9d  mov     r9, [rsp+208h+var_1C0]
0x180010ea2  xor     r8d, r8d; pReturnValue
0x180010ea5  mov     edx, esi; nProcNum
0x180010ea7  lea     rcx, pProxyInfo; pProxyInfo
0x180010eae  call    cs:__imp_NdrClientCall3
0x180010eb4  mov     rbx, rax
0x180010eb7  cmp     ebx, esi
0x180010eb9  jl      short loc_180010EC1
0x180010ebb  or      ebx, 80010000h
0x180010ec1  lea     rcx, [rsp+208h+var_168]; this
0x180010ec9  call    ??1OverrideImpersonationScope@@QEAA@XZ; OverrideImpersonationScope::~OverrideImpersonationScope(void)
0x180010ece  jmp     loc_180010F7A
0x180010ed3  lea     rcx, [rsp+208h+var_178]
0x180010edb  call    ?GetRpcHandle@@YA?AV?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@XZ; GetRpcHandle(void)
0x180010ee0  mov     rbx, rax
0x180010ee3  cmp     [rsp+208h+var_1C0], rdi
0x180010ee8  jz      short loc_180010F09
0x180010eea  mov     rcx, [rsp+208h+var_1C8]
0x180010eef  mov     rax, [rcx]
0x180010ef2  lea     rcx, [rsp+208h+var_1C8]
0x180010ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010efc  test    al, al
0x180010efe  jz      loc_180011160
0x180010f04  mov     [rsp+208h+var_1C0], rdi
0x180010f09  mov     rax, [rbx+8]
0x180010f0d  mov     [rsp+208h+var_1C0], rax
0x180010f12  mov     [rbx+8], rdi
0x180010f16  mov     [rsp+208h+var_178], r13
0x180010f1e  cmp     [rsp+208h+var_170], rdi
0x180010f26  jz      short loc_180010F3D
0x180010f28  lea     rcx, [rsp+208h+var_178]
0x180010f30  call    ?InternalClose@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(void)
0x180010f35  test    al, al
0x180010f37  jz      loc_18001117A
0x180010f3d  mov     rax, [rsp+208h+var_180]
0x180010f45  mov     [rsp+208h+var_1D8], rax
0x180010f4a  mov     dword ptr [rsp+208h+var_1E0], r14d
0x180010f4f  mov     [rsp+208h+var_1E8], r15
0x180010f54  mov     r9, [rsp+208h+var_1C0]
0x180010f59  xor     r8d, r8d; pReturnValue
0x180010f5c  lea     esi, [r8+1]
0x180010f60  mov     edx, esi; nProcNum
0x180010f62  lea     rcx, pProxyInfo; pProxyInfo
0x180010f69  call    cs:__imp_NdrClientCall3
0x180010f6f  cmp     eax, esi
0x180010f71  jl      short loc_180010F78
0x180010f73  or      eax, 80010000h
0x180010f78  mov     ebx, eax
0x180010f7a  test    ebx, ebx
0x180010f7c  jns     short loc_180010FDC
0x180010f7e  mov     eax, ebx
0x180010f80  and     eax, 1FFF0000h
0x180010f85  cmp     eax, 3F0000h
0x180010f8a  jz      loc_180011194
0x180010f90  cmp     eax, 7E10000h
0x180010f95  jz      loc_180011194
0x180010f9b  mov     rax, [rsp+208h+var_180]
0x180010fa3  mov     [rsp+208h+var_1D8], rax
0x180010fa8  mov     dword ptr [rsp+208h+var_1E0], r14d
0x180010fad  mov     [rsp+208h+var_1E8], r15
0x180010fb2  mov     r9, [rsp+208h+var_1C0]
0x180010fb7  xor     r8d, r8d; pReturnValue
0x180010fba  mov     edx, esi; nProcNum
0x180010fbc  lea     rcx, pProxyInfo; pProxyInfo
0x180010fc3  call    cs:__imp_NdrClientCall3
0x180010fc9  cmp     eax, esi
0x180010fcb  jl      short loc_180010FD2
0x180010fcd  or      eax, 80010000h
0x180010fd2  mov     ebx, eax
0x180010fd4  test    eax, eax
0x180010fd6  js      loc_180011194
0x180010fdc  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180010fe3  mov     [rsp+208h+var_198], rax
0x180010fe8  cmp     [rsp+208h+Token], rdi
0x180010fed  jz      short loc_180011006
0x180010fef  lea     rcx, [rsp+208h+var_198]
0x180010ff4  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x180010ff9  test    al, al
0x180010ffb  jz      loc_1800111A2
0x180011001  mov     [rsp+208h+Token], rdi
0x180011006  mov     [rsp+208h+var_1C8], r13
0x18001100b  cmp     [rsp+208h+var_1C0], rdi
0x180011010  jz      short loc_180011029
0x180011012  lea     rcx, [rsp+208h+var_1C8]
0x180011017  call    ?InternalClose@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(void)
0x18001101c  test    al, al
0x18001101e  jz      loc_1800111BC
0x180011024  mov     [rsp+208h+var_1C0], rdi
0x180011029  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x180011030  mov     [rsp+208h+var_188], rax
0x180011038  cmp     [rsp+208h+var_180], rdi
0x180011040  jz      short loc_180011057
0x180011042  lea     rcx, [rsp+208h+var_188]
0x18001104a  call    ?InternalClose@?$HandleT@ULocalAllocMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(void)
0x18001104f  test    al, al
0x180011051  jz      loc_1800111D6
0x180011057  jmp     short loc_180011069
0x180011059  xor     edi, edi
0x18001105b  mov     ebx, [rsp+208h+var_1B8]
0x18001105f  mov     r12, [rsp+208h+var_1A0]
0x180011064  mov     r14d, [rsp+208h+var_1B0]
0x180011069  mov     eax, cs:dword_18001A010
0x18001106f  cmp     eax, 5
0x180011072  jbe     loc_1800110F8
0x180011078  mov     rcx, cs:qword_18001A028
0x18001107f  mov     rax, cs:qword_18001A020
0x180011086  mov     rdx, 400000000000h
0x180011090  test    rdx, rax
0x180011093  jz      short loc_1800110F8
0x180011095  mov     rax, rcx
0x180011098  and     rax, rdx
0x18001109b  cmp     rax, rcx
0x18001109e  jnz     short loc_1800110F8
0x1800110a0  mov     [rsp+208h+var_1B0], ebx
0x1800110a4  call    cs:__imp_GetTickCount64
0x1800110aa  sub     rax, r12
0x1800110ad  mov     [rsp+208h+var_1A0], rax
0x1800110b2  mov     [rsp+208h+var_1B8], r14d
0x1800110b7  lea     rax, [rsp+208h+var_148]
0x1800110bf  mov     [rsp+208h+var_1C8], rax
0x1800110c4  lea     rax, [rsp+208h+var_1B0]
0x1800110c9  mov     [rsp+208h+var_1D0], rax
0x1800110ce  lea     rax, [rsp+208h+var_1A0]
0x1800110d3  mov     [rsp+208h+var_1D8], rax
0x1800110d8  lea     rax, [rsp+208h+var_1B8]
0x1800110dd  mov     [rsp+208h+var_1E0], rax
0x1800110e2  lea     rax, [rsp+208h+var_1C8]
0x1800110e7  mov     [rsp+208h+var_1E8], rax
0x1800110ec  lea     rdx, unk_180016BF1
0x1800110f3  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800110f8  test    ebx, ebx
0x1800110fa  jns     short loc_180011102
0x1800110fc  bts     ebx, 1Dh
0x180011100  mov     edi, ebx
0x180011102  mov     eax, edi
0x180011104  jmp     short loc_180011108
0x180011106  xor     eax, eax
0x180011108  mov     rcx, [rsp+208h+var_48]
0x180011110  xor     rcx, rsp; StackCookie
0x180011113  call    __security_check_cookie
0x180011118  add     rsp, 1D0h
0x18001111f  pop     r15
0x180011121  pop     r14
0x180011123  pop     r13
0x180011125  pop     r12
0x180011127  pop     rdi
0x180011128  pop     rsi
0x180011129  pop     rbx
0x18001112a  retn
0x18001112b  call    cs:__imp_GetLastError
0x180011131  nop
0x180011132  test    eax, eax
0x180011134  jle     short loc_18001113E
0x180011136  movzx   eax, ax
0x180011139  or      eax, 80070000h
0x18001113e  mov     ecx, eax; this
0x180011140  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180011145  int     3; Trap to Debugger
0x180011146  call    cs:__imp_GetLastError
0x18001114c  test    eax, eax
0x18001114e  jle     short loc_180011158
0x180011150  movzx   eax, ax
0x180011153  or      eax, 80070000h
0x180011158  mov     ecx, eax; this
0x18001115a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001115f  nop
0x180011160  call    cs:__imp_GetLastError
0x180011166  test    eax, eax
0x180011168  jle     short loc_180011172
0x18001116a  movzx   eax, ax
0x18001116d  or      eax, 80070000h
0x180011172  mov     ecx, eax; this
0x180011174  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180011179  int     3; Trap to Debugger
0x18001117a  call    cs:__imp_GetLastError
0x180011180  test    eax, eax
0x180011182  jle     short loc_18001118C
0x180011184  movzx   eax, ax
0x180011187  or      eax, 80070000h
0x18001118c  mov     ecx, eax; this
0x18001118e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180011193  int     3; Trap to Debugger
0x180011194  mov     r8d, ebx; char *
0x180011197  mov     ecx, 348h; this
0x18001119c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(uint,char const *,long)
0x1800111a2  call    cs:__imp_GetLastError
0x1800111a8  test    eax, eax
0x1800111aa  jle     short loc_1800111B4
0x1800111ac  movzx   eax, ax
0x1800111af  or      eax, 80070000h
0x1800111b4  mov     ecx, eax; this
0x1800111b6  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800111bb  nop
0x1800111bc  call    cs:__imp_GetLastError
0x1800111c2  test    eax, eax
0x1800111c4  jle     short loc_1800111CE
0x1800111c6  movzx   eax, ax
0x1800111c9  or      eax, 80070000h
  ... truncated ...
```
