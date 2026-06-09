# EnsureStoreLicenseForPackageActivation2

- ea: `0x18000fdd0`
- end: `0x1800103e0`
- name: `EnsureStoreLicenseForPackageActivation2`
- size: `1552`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800011d4`
- `0x180001960`
- `0x180006cb4`
- `0x180006f7c`
- `0x1800070d4`
- `0x18000762c`
- `0x180007858`
- `0x18000bdc0`
- `0x18000bde0`
- `0x18000be00`
- `0x18000be7c`
- `0x18000e9c4`
- `0x18000ee24`
- `0x18000efb4`
- `0x18000fdd0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001031b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001034f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001031b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001034f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000ff6f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000ff6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ff55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ff55`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000ff7a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000ff7a`
- `RPCRT4!NdrClientCall3` at `0x180010021`
- `RPCRT4!NdrClientCall3` at `0x1800100de`
- `RPCRT4!NdrClientCall3` at `0x180010145`
- `RPCRT4!NdrClientCall3` at `0x180010021`
- `RPCRT4!NdrClientCall3` at `0x1800100de`
- `RPCRT4!NdrClientCall3` at `0x180010145`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fe16`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180010273`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fe16`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180010273`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x18000fe45`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x18000fe45`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserTokenFromSid` at `0x18000ff20`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserTokenFromSid` at `0x18000ff20`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EnsureStoreLicenseForPackageActivation2(__int64 a1, unsigned int a2, void *a3, void *a4)
{
  unsigned int v6; // r14d
  unsigned int v8; // edi
  __int64 result; // rax
  ULONGLONG TickCount64; // r13
  struct _GUID *v11; // rsi
  struct _GUID *v12; // rax
  HANDLE v13; // rbx
  HANDLE CurrentThread; // rax
  __int64 RpcHandle; // rbx
  unsigned int v16; // r15d
  int Pointer; // eax
  signed int v18; // ebx
  unsigned int v19; // edx
  const char *v20; // r8
  int v21; // r9d
  __int64 v22; // rbx
  int v23; // eax
  int v24; // eax
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  signed int LastError; // eax
  int v29; // edx
  unsigned int v30; // r8d
  signed int v31; // eax
  int v32; // edx
  unsigned int v33; // r8d
  signed int v34; // eax
  int v35; // edx
  unsigned int v36; // r8d
  signed int v37; // eax
  int v38; // edx
  unsigned int v39; // r8d
  signed int v40; // eax
  int v41; // edx
  unsigned int v42; // r8d
  signed int v43; // eax
  int v44; // edx
  unsigned int v45; // r8d
  signed int v46; // eax
  int v47; // edx
  unsigned int v48; // r8d
  signed int v49; // eax
  int v50; // edx
  unsigned int v51; // r8d
  wil *v52; // rcx
  __int64 v53; // [rsp+0h] [rbp-228h] BYREF
  __int64 v54; // [rsp+28h] [rbp-200h]
  __int64 v55; // [rsp+38h] [rbp-1F0h]
  unsigned int v56; // [rsp+50h] [rbp-1D8h] BYREF
  void **v57; // [rsp+58h] [rbp-1D0h] BYREF
  __int64 v58; // [rsp+60h] [rbp-1C8h]
  unsigned int v59; // [rsp+68h] [rbp-1C0h] BYREF
  struct _GUID *v60; // [rsp+70h] [rbp-1B8h] BYREF
  __int64 v61; // [rsp+78h] [rbp-1B0h]
  void **v62; // [rsp+80h] [rbp-1A8h] BYREF
  __int64 v63; // [rsp+88h] [rbp-1A0h]
  int v64; // [rsp+90h] [rbp-198h] BYREF
  ULONGLONG v65; // [rsp+98h] [rbp-190h] BYREF
  void **v66; // [rsp+A0h] [rbp-188h] BYREF
  HANDLE Token; // [rsp+A8h] [rbp-180h] BYREF
  void **v68; // [rsp+B0h] [rbp-178h] BYREF
  struct _GUID *v69; // [rsp+B8h] [rbp-170h]
  void **v70; // [rsp+C0h] [rbp-168h] BYREF
  void *TokenHandle; // [rsp+C8h] [rbp-160h] BYREF
  bool v72; // [rsp+D0h] [rbp-158h]
  unsigned __int16 v73[128]; // [rsp+E0h] [rbp-148h] BYREF

  v6 = a2;
  v59 = a2;
  v8 = 0;
  if ( !a1 )
    return 3221225485LL;
  TickCount64 = GetTickCount64();
  v65 = TickCount64;
  v64 = 256;
  result = PsmGetPackageFullNameFromKey(a1, v73, &v64);
  if ( (int)result >= 0 )
  {
    if ( BypassServiceResponse(v73) )
      return 0;
    if ( StoreAppsAreDisabled() )
      return 3221226340LL;
    if ( !InvokeLicenseManagerRequired(v73, a3, 0) )
      return 0;
    try
    {
      v56 = 0;
      v60 = 0;
      GetAppSessionGuidsFromJob(a4, &v56, &v60);
      v68 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
      v11 = v60;
      v12 = 0;
      if ( v60 )
        v12 = v60;
      v69 = v12;
      GetSidString((__int64)&v62, a3);
      v57 = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
      v58 = 0;
      v66 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      Token = 0;
      if ( (int)UMgrQueryUserTokenFromSid(v63, &Token) >= 0 )
      {
        v13 = Token;
        v70 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
        TokenHandle = 0;
        v72 = 0;
        CurrentThread = GetCurrentThread();
        OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle);
        v72 = SetThreadToken(0, v13);
        RpcHandle = GetRpcHandle((__int64)&v60);
        if ( v58 )
        {
          if ( !((unsigned __int8 (__fastcall *)(void ***))*v57)(&v57) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v29, v30);
            __debugbreak();
          }
          v58 = 0;
        }
        v58 = *(_QWORD *)(RpcHandle + 8);
        *(_QWORD *)(RpcHandle + 8) = 0;
        v60 = (struct _GUID *)&Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
        if ( !v61 || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(&v60) )
        {
          v16 = v56;
          LODWORD(v55) = v56;
          LODWORD(v54) = v6;
          Pointer = (unsigned int)NdrClientCall3(
                                    (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                    2u,
                                    0,
                                    v58,
                                    a1,
                                    v54,
                                    v63,
                                    v55,
                                    v11).Pointer;
          v18 = Pointer;
          if ( Pointer >= 1 )
            v18 = Pointer | 0x80010000;
          OverrideImpersonationScope::~OverrideImpersonationScope((OverrideImpersonationScope *)&v70);
          goto LABEL_28;
        }
        v31 = GetLastError();
        if ( v31 > 0 )
          v31 = (unsigned __int16)v31 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v31, v32, v33);
LABEL_61:
        v34 = GetLastError();
        if ( v34 > 0 )
          v34 = (unsigned __int16)v34 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v34, v35, v36);
        __debugbreak();
      }
      v22 = GetRpcHandle((__int64)&v60);
      if ( v58 )
      {
        if ( !((unsigned __int8 (__fastcall *)(void ***))*v57)(&v57) )
          goto LABEL_61;
        v58 = 0;
      }
      v58 = *(_QWORD *)(v22 + 8);
      *(_QWORD *)(v22 + 8) = 0;
      v60 = (struct _GUID *)&Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
      if ( v61 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(&v60) )
      {
        v37 = GetLastError();
        if ( v37 > 0 )
          v37 = (unsigned __int16)v37 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v37, v38, v39);
        __debugbreak();
      }
      v16 = v56;
      LODWORD(v55) = v56;
      LODWORD(v54) = v6;
      v23 = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, v58, a1, v54, v63, v55, v11).Pointer;
      if ( v23 >= 1 )
        v23 |= 0x80010000;
      v18 = v23;
LABEL_28:
      if ( v18 < 0 )
      {
        if ( (v18 & 0x1FFF0000) == 0x3F0000 || (v18 & 0x1FFF0000) == 0x7E10000 )
          goto LABEL_67;
        LODWORD(v55) = v16;
        LODWORD(v54) = v6;
        v24 = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, v58, a1, v54, v63, v55, v11).Pointer;
        if ( v24 >= 1 )
          v24 |= 0x80010000;
        v18 = v24;
        if ( v24 < 0 )
LABEL_67:
          wil::details::in1diag3::_Throw_Hr((wil::details::in1diag3 *)0x3A5, v19, (const char *)(unsigned int)v18, v21);
      }
      v66 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( Token )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v66) )
        {
          v40 = GetLastError();
          if ( v40 > 0 )
            v40 = (unsigned __int16)v40 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v40, v41, v42);
          goto LABEL_71;
        }
        Token = 0;
      }
      v57 = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
      if ( !v58 )
      {
LABEL_40:
        v62 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
        if ( !v63 )
        {
LABEL_43:
          v68 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
          if ( !v69
            || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v68) )
          {
            goto LABEL_83;
          }
LABEL_77:
          v49 = GetLastError();
          if ( v49 > 0 )
            v49 = (unsigned __int16)v49 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v49, v50, v51);
          JUMPOUT(0x1800103DELL);
        }
        if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v62) )
        {
          v63 = 0;
          goto LABEL_43;
        }
LABEL_74:
        v46 = GetLastError();
        if ( v46 > 0 )
          v46 = (unsigned __int16)v46 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v46, v47, v48);
        goto LABEL_77;
      }
      if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(&v57) )
      {
        v58 = 0;
        goto LABEL_40;
      }
LABEL_71:
      v43 = GetLastError();
      if ( v43 > 0 )
        v43 = (unsigned __int16)v43 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v43, v44, v45);
      goto LABEL_74;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException((wil::details::in1diag3 *)0x3A9, (unsigned int)&v53, v20);
      v56 = wil::ResultFromCaughtException(v52);
      v8 = 0;
      v18 = v56;
      TickCount64 = v65;
      v6 = v59;
    }
LABEL_83:
    if ( (unsigned int)dword_18001A010 > 5
      && (qword_18001A020 & 0x400000000000LL) != 0
      && (qword_18001A028 & 0x400000000000LL) == qword_18001A028 )
    {
      v59 = v18;
      v65 = GetTickCount64() - TickCount64;
      v56 = v6;
      v60 = (struct _GUID *)v73;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v25,
        (unsigned int)&unk_180016B8A,
        v26,
        v27,
        (__int64)&v60,
        (__int64)&v56,
        (__int64)&v65,
        (__int64)&v59);
    }
    if ( v18 < 0 )
      return v18 | 0x20000000u;
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18000fdd0  push    rbx
0x18000fdd2  push    rsi
0x18000fdd3  push    rdi
0x18000fdd4  push    r12
0x18000fdd6  push    r13
0x18000fdd8  push    r14
0x18000fdda  push    r15
0x18000fddc  sub     rsp, 1F0h
0x18000fde3  mov     rax, cs:__security_cookie
0x18000fdea  xor     rax, rsp
0x18000fded  mov     [rsp+228h+var_48], rax
0x18000fdf5  mov     rsi, r9
0x18000fdf8  mov     rbx, r8
0x18000fdfb  mov     r14d, edx
0x18000fdfe  mov     r12, rcx
0x18000fe01  mov     [rsp+228h+var_1C0], edx
0x18000fe05  xor     edi, edi
0x18000fe07  test    rcx, rcx
0x18000fe0a  jnz     short loc_18000FE16
0x18000fe0c  mov     eax, 0C000000Dh
0x18000fe11  jmp     loc_1800102DD
0x18000fe16  call    cs:__imp_GetTickCount64
0x18000fe1c  mov     r13, rax
0x18000fe1f  mov     [rsp+228h+var_190], rax
0x18000fe27  mov     [rsp+228h+var_198], 100h
0x18000fe32  lea     r8, [rsp+228h+var_198]
0x18000fe3a  lea     rdx, [rsp+228h+var_148]
0x18000fe42  mov     rcx, r12
0x18000fe45  call    cs:__imp_PsmGetPackageFullNameFromKey
0x18000fe4b  test    eax, eax
0x18000fe4d  js      loc_1800102DD
0x18000fe53  lea     rcx, [rsp+228h+var_148]; unsigned __int16 *
0x18000fe5b  call    ?BypassServiceResponse@@YA_NPEBG@Z; BypassServiceResponse(ushort const *)
0x18000fe60  test    al, al
0x18000fe62  jnz     loc_1800102DB
0x18000fe68  call    ?StoreAppsAreDisabled@@YA_NXZ; StoreAppsAreDisabled(void)
0x18000fe6d  test    al, al
0x18000fe6f  jz      short loc_18000FE7B
0x18000fe71  mov     eax, 0C0000364h
0x18000fe76  jmp     loc_1800102DD
0x18000fe7b  xor     r8d, r8d; bool
0x18000fe7e  mov     rdx, rbx; pSid
0x18000fe81  lea     rcx, [rsp+228h+var_148]; unsigned __int16 *
0x18000fe89  call    ?InvokeLicenseManagerRequired@@YA_NPEBGPEAX_N@Z; InvokeLicenseManagerRequired(ushort const *,void *,bool)
0x18000fe8e  test    al, al
0x18000fe90  jz      loc_1800102DB
0x18000fe96  mov     [rsp+228h+var_1D8], edi
0x18000fe9a  mov     [rsp+228h+var_1B8], rdi
0x18000fe9f  lea     r8, [rsp+228h+var_1B8]; struct _GUID **
0x18000fea4  lea     rdx, [rsp+228h+var_1D8]; unsigned int *
0x18000fea9  mov     rcx, rsi; JobHandle
0x18000feac  call    ?GetAppSessionGuidsFromJob@@YAJPEAXPEAKPEAPEAU_GUID@@@Z; GetAppSessionGuidsFromJob(void *,ulong *,_GUID * *)
0x18000feb1  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x18000feb8  mov     [rsp+228h+var_178], rax
0x18000fec0  mov     rsi, [rsp+228h+var_1B8]
0x18000fec5  mov     rax, rdi
0x18000fec8  test    rsi, rsi
0x18000fecb  cmovnz  rax, rsi
0x18000fecf  mov     [rsp+228h+var_170], rax
0x18000fed7  mov     rdx, rbx
0x18000feda  lea     rcx, [rsp+228h+var_1A8]
0x18000fee2  call    ?GetSidString@@YA?AV?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@PEAX@Z; GetSidString(void *)
0x18000fee7  nop
0x18000fee8  lea     r15, ??_7?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable'
0x18000feef  mov     [rsp+228h+var_1D0], r15
0x18000fef4  mov     [rsp+228h+var_1C8], rdi
0x18000fef9  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18000ff00  mov     [rsp+228h+var_188], rax
0x18000ff08  mov     [rsp+228h+Token], rdi
0x18000ff10  lea     rdx, [rsp+228h+Token]
0x18000ff18  mov     rcx, [rsp+228h+var_1A0]
0x18000ff20  call    cs:__imp_UMgrQueryUserTokenFromSid
0x18000ff26  test    eax, eax
0x18000ff28  js      loc_180010047
0x18000ff2e  mov     rbx, [rsp+228h+Token]
0x18000ff36  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18000ff3d  mov     [rsp+228h+var_168], rax
0x18000ff45  mov     [rsp+228h+TokenHandle], rdi
0x18000ff4d  mov     [rsp+228h+var_158], dil
0x18000ff55  call    cs:__imp_GetCurrentThread
0x18000ff5b  lea     r9, [rsp+228h+TokenHandle]; TokenHandle
0x18000ff63  mov     edx, 4; DesiredAccess
0x18000ff68  lea     r8d, [rdx-3]; OpenAsSelf
0x18000ff6c  mov     rcx, rax; ThreadHandle
0x18000ff6f  call    cs:__imp_OpenThreadToken
0x18000ff75  mov     rdx, rbx; Token
0x18000ff78  xor     ecx, ecx; Thread
0x18000ff7a  call    cs:__imp_SetThreadToken
0x18000ff80  test    eax, eax
0x18000ff82  setnz   [rsp+228h+var_158]
0x18000ff8a  lea     rcx, [rsp+228h+var_1B8]
0x18000ff8f  call    ?GetRpcHandle@@YA?AV?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@XZ; GetRpcHandle(void)
0x18000ff94  mov     rbx, rax
0x18000ff97  cmp     [rsp+228h+var_1C8], rdi
0x18000ff9c  jz      short loc_18000FFBD
0x18000ff9e  mov     rcx, [rsp+228h+var_1D0]
0x18000ffa3  mov     rax, [rcx]
0x18000ffa6  lea     rcx, [rsp+228h+var_1D0]
0x18000ffab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffb0  test    al, al
0x18000ffb2  jz      loc_180010300
0x18000ffb8  mov     [rsp+228h+var_1C8], rdi
0x18000ffbd  mov     rax, [rbx+8]
0x18000ffc1  mov     [rsp+228h+var_1C8], rax
0x18000ffc6  mov     [rbx+8], rdi
0x18000ffca  mov     [rsp+228h+var_1B8], r15
0x18000ffcf  cmp     [rsp+228h+var_1B0], rdi
0x18000ffd4  jz      short loc_18000FFE8
0x18000ffd6  lea     rcx, [rsp+228h+var_1B8]
0x18000ffdb  call    ?InternalClose@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(void)
0x18000ffe0  test    al, al
0x18000ffe2  jz      loc_18001031B
0x18000ffe8  mov     [rsp+228h+var_1E8], rsi
0x18000ffed  mov     r15d, [rsp+228h+var_1D8]
0x18000fff2  mov     dword ptr [rsp+228h+var_1F0], r15d
0x18000fff7  mov     rax, [rsp+228h+var_1A0]
0x18000ffff  mov     [rsp+228h+var_1F8], rax
0x180010004  mov     dword ptr [rsp+228h+var_200], r14d
0x180010009  mov     [rsp+228h+var_208], r12
0x18001000e  mov     r9, [rsp+228h+var_1C8]
0x180010013  xor     r8d, r8d; pReturnValue
0x180010016  lea     edx, [r8+2]; nProcNum
0x18001001a  lea     rcx, pProxyInfo; pProxyInfo
0x180010021  call    cs:__imp_NdrClientCall3
0x180010027  mov     rbx, rax
0x18001002a  cmp     ebx, 1
0x18001002d  jl      short loc_180010035
0x18001002f  or      ebx, 80010000h
0x180010035  lea     rcx, [rsp+228h+var_168]; this
0x18001003d  call    ??1OverrideImpersonationScope@@QEAA@XZ; OverrideImpersonationScope::~OverrideImpersonationScope(void)
0x180010042  jmp     loc_1800100F0
0x180010047  lea     rcx, [rsp+228h+var_1B8]
0x18001004c  call    ?GetRpcHandle@@YA?AV?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@XZ; GetRpcHandle(void)
0x180010051  mov     rbx, rax
0x180010054  cmp     [rsp+228h+var_1C8], rdi
0x180010059  jz      short loc_18001007A
0x18001005b  mov     rcx, [rsp+228h+var_1D0]
0x180010060  mov     rax, [rcx]
0x180010063  lea     rcx, [rsp+228h+var_1D0]
0x180010068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001006d  test    al, al
0x18001006f  jz      loc_180010335
0x180010075  mov     [rsp+228h+var_1C8], rdi
0x18001007a  mov     rax, [rbx+8]
0x18001007e  mov     [rsp+228h+var_1C8], rax
0x180010083  mov     [rbx+8], rdi
0x180010087  mov     [rsp+228h+var_1B8], r15
0x18001008c  cmp     [rsp+228h+var_1B0], rdi
0x180010091  jz      short loc_1800100A5
0x180010093  lea     rcx, [rsp+228h+var_1B8]
0x180010098  call    ?InternalClose@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(void)
0x18001009d  test    al, al
0x18001009f  jz      loc_18001034F
0x1800100a5  mov     [rsp+228h+var_1E8], rsi
0x1800100aa  mov     r15d, [rsp+228h+var_1D8]
0x1800100af  mov     dword ptr [rsp+228h+var_1F0], r15d
0x1800100b4  mov     rax, [rsp+228h+var_1A0]
0x1800100bc  mov     [rsp+228h+var_1F8], rax
0x1800100c1  mov     dword ptr [rsp+228h+var_200], r14d
0x1800100c6  mov     [rsp+228h+var_208], r12
0x1800100cb  mov     r9, [rsp+228h+var_1C8]
0x1800100d0  xor     r8d, r8d; pReturnValue
0x1800100d3  lea     edx, [r8+2]; nProcNum
0x1800100d7  lea     rcx, pProxyInfo; pProxyInfo
0x1800100de  call    cs:__imp_NdrClientCall3
0x1800100e4  cmp     eax, 1
0x1800100e7  jl      short loc_1800100EE
0x1800100e9  or      eax, 80010000h
0x1800100ee  mov     ebx, eax
0x1800100f0  test    ebx, ebx
0x1800100f2  jns     short loc_18001015F
0x1800100f4  mov     eax, ebx
0x1800100f6  and     eax, 1FFF0000h
0x1800100fb  cmp     eax, 3F0000h
0x180010100  jz      loc_180010369
0x180010106  cmp     eax, 7E10000h
0x18001010b  jz      loc_180010369
0x180010111  mov     [rsp+228h+var_1E8], rsi
0x180010116  mov     dword ptr [rsp+228h+var_1F0], r15d
0x18001011b  mov     rax, [rsp+228h+var_1A0]
0x180010123  mov     [rsp+228h+var_1F8], rax
0x180010128  mov     dword ptr [rsp+228h+var_200], r14d
0x18001012d  mov     [rsp+228h+var_208], r12
0x180010132  mov     r9, [rsp+228h+var_1C8]
0x180010137  xor     r8d, r8d; pReturnValue
0x18001013a  lea     edx, [r8+2]; nProcNum
0x18001013e  lea     rcx, pProxyInfo; pProxyInfo
0x180010145  call    cs:__imp_NdrClientCall3
0x18001014b  cmp     eax, 1
0x18001014e  jl      short loc_180010155
0x180010150  or      eax, 80010000h
0x180010155  mov     ebx, eax
0x180010157  test    eax, eax
0x180010159  js      loc_180010369
0x18001015f  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180010166  mov     [rsp+228h+var_188], rax
0x18001016e  cmp     [rsp+228h+Token], rdi
0x180010176  jz      short loc_180010195
0x180010178  lea     rcx, [rsp+228h+var_188]
0x180010180  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x180010185  test    al, al
0x180010187  jz      loc_180010377
0x18001018d  mov     [rsp+228h+Token], rdi
0x180010195  lea     rax, ??_7?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable'
0x18001019c  mov     [rsp+228h+var_1D0], rax
0x1800101a1  cmp     [rsp+228h+var_1C8], rdi
0x1800101a6  jz      short loc_1800101BF
0x1800101a8  lea     rcx, [rsp+228h+var_1D0]
0x1800101ad  call    ?InternalClose@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(void)
0x1800101b2  test    al, al
0x1800101b4  jz      loc_180010391
0x1800101ba  mov     [rsp+228h+var_1C8], rdi
0x1800101bf  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x1800101c6  mov     [rsp+228h+var_1A8], rax
0x1800101ce  cmp     [rsp+228h+var_1A0], rdi
0x1800101d6  jz      short loc_1800101F5
0x1800101d8  lea     rcx, [rsp+228h+var_1A8]
0x1800101e0  call    ?InternalClose@?$HandleT@ULocalAllocMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(void)
0x1800101e5  test    al, al
0x1800101e7  jz      loc_1800103AB
0x1800101ed  mov     [rsp+228h+var_1A0], rdi
0x1800101f5  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x1800101fc  mov     [rsp+228h+var_178], rax
0x180010204  cmp     [rsp+228h+var_170], rdi
0x18001020c  jz      short loc_180010223
0x18001020e  lea     rcx, [rsp+228h+var_178]
0x180010216  call    ?InternalClose@?$HandleT@ULocalAllocMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(void)
0x18001021b  test    al, al
0x18001021d  jz      loc_1800103C5
0x180010223  jmp     short loc_180010238
0x180010225  xor     edi, edi
0x180010227  mov     ebx, [rsp+228h+var_1D8]
0x18001022b  mov     r13, [rsp+228h+var_190]
0x180010233  mov     r14d, [rsp+228h+var_1C0]
0x180010238  mov     eax, cs:dword_18001A010
0x18001023e  cmp     eax, 5
0x180010241  jbe     loc_1800102CD
0x180010247  mov     rcx, cs:qword_18001A028
0x18001024e  mov     rax, cs:qword_18001A020
0x180010255  mov     rdx, 400000000000h
0x18001025f  test    rdx, rax
0x180010262  jz      short loc_1800102CD
0x180010264  mov     rax, rcx
0x180010267  and     rax, rdx
0x18001026a  cmp     rax, rcx
0x18001026d  jnz     short loc_1800102CD
0x18001026f  mov     [rsp+228h+var_1C0], ebx
0x180010273  call    cs:__imp_GetTickCount64
0x180010279  sub     rax, r13
0x18001027c  mov     [rsp+228h+var_190], rax
0x180010284  mov     [rsp+228h+var_1D8], r14d
0x180010289  lea     rax, [rsp+228h+var_148]
0x180010291  mov     [rsp+228h+var_1B8], rax
0x180010296  lea     rax, [rsp+228h+var_1C0]
0x18001029b  mov     [rsp+228h+var_1F0], rax
0x1800102a0  lea     rax, [rsp+228h+var_190]
0x1800102a8  mov     [rsp+228h+var_1F8], rax
0x1800102ad  lea     rax, [rsp+228h+var_1D8]
0x1800102b2  mov     [rsp+228h+var_200], rax
0x1800102b7  lea     rax, [rsp+228h+var_1B8]
0x1800102bc  mov     [rsp+228h+var_208], rax
0x1800102c1  lea     rdx, unk_180016B8A
0x1800102c8  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800102cd  test    ebx, ebx
0x1800102cf  jns     short loc_1800102D7
0x1800102d1  bts     ebx, 1Dh
0x1800102d5  mov     edi, ebx
0x1800102d7  mov     eax, edi
0x1800102d9  jmp     short loc_1800102DD
0x1800102db  xor     eax, eax
0x1800102dd  mov     rcx, [rsp+228h+var_48]
0x1800102e5  xor     rcx, rsp; StackCookie
0x1800102e8  call    __security_check_cookie
0x1800102ed  add     rsp, 1F0h
0x1800102f4  pop     r15
0x1800102f6  pop     r14
0x1800102f8  pop     r13
0x1800102fa  pop     r12
0x1800102fc  pop     rdi
0x1800102fd  pop     rsi
0x1800102fe  pop     rbx
0x1800102ff  retn
0x180010300  call    cs:__imp_GetLastError
0x180010306  nop
0x180010307  test    eax, eax
0x180010309  jle     short loc_180010313
0x18001030b  movzx   eax, ax
0x18001030e  or      eax, 80070000h
0x180010313  mov     ecx, eax; this
0x180010315  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001031a  int     3; Trap to Debugger
0x18001031b  call    cs:__imp_GetLastError
0x180010321  test    eax, eax
0x180010323  jle     short loc_18001032D
0x180010325  movzx   eax, ax
0x180010328  or      eax, 80070000h
0x18001032d  mov     ecx, eax; this
0x18001032f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180010334  nop
0x180010335  call    cs:__imp_GetLastError
  ... truncated ...
```
