# EnsureStoreLicenseForOptionalPackageUsage

- ea: `0x18000f7d0`
- end: `0x18000fd8a`
- name: `EnsureStoreLicenseForOptionalPackageUsage`
- size: `1466`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, HANDLE JobHandle)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180006cb4`
- `0x180006f7c`
- `0x1800070d4`
- `0x18000762c`
- `0x180007858`
- `0x18000bdc0`
- `0x18000bde0`
- `0x18000be00`
- `0x18000e9c4`
- `0x18000ee24`
- `0x18000efb4`
- `0x18000f7d0`
- `0x180011c5c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd6f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f935`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f935`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f91b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f91b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000f940`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000f940`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f814`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fc18`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f814`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fc18`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserTokenFromSid` at `0x18000f8e6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserTokenFromSid` at `0x18000f8e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EnsureStoreLicenseForOptionalPackageUsage(
        unsigned __int16 *a1,
        unsigned int a2,
        void *a3,
        struct _GUID *a4,
        HANDLE JobHandle)
{
  struct _GUID *v5; // r14
  unsigned int v7; // r15d
  const unsigned __int16 *v8; // rsi
  unsigned int v9; // edi
  ULONGLONG TickCount64; // r12
  __int128 v12; // xmm6
  struct _GUID *v13; // rax
  HANDLE v14; // rbx
  HANDLE CurrentThread; // rax
  __int64 RpcHandle; // rbx
  signed int v17; // ebx
  unsigned int v18; // edx
  const char *v19; // r8
  int v20; // r9d
  __int64 v21; // rbx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  signed int LastError; // eax
  int v26; // edx
  unsigned int v27; // r8d
  signed int v28; // eax
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
  wil *v49; // rcx
  __int64 v50; // [rsp+0h] [rbp-118h] BYREF
  unsigned int v51; // [rsp+50h] [rbp-C8h] BYREF
  void **v52; // [rsp+58h] [rbp-C0h] BYREF
  __int64 v53; // [rsp+60h] [rbp-B8h]
  struct _GUID *v54[2]; // [rsp+70h] [rbp-A8h] BYREF
  void **v55; // [rsp+80h] [rbp-98h] BYREF
  __int64 v56; // [rsp+88h] [rbp-90h]
  ULONGLONG v57; // [rsp+90h] [rbp-88h] BYREF
  void **v58; // [rsp+98h] [rbp-80h] BYREF
  HANDLE Token; // [rsp+A0h] [rbp-78h] BYREF
  void **v60; // [rsp+A8h] [rbp-70h] BYREF
  struct _GUID *v61; // [rsp+B0h] [rbp-68h]
  void **v62; // [rsp+B8h] [rbp-60h] BYREF
  void *TokenHandle; // [rsp+C0h] [rbp-58h] BYREF
  bool v64; // [rsp+C8h] [rbp-50h]
  unsigned __int16 *v65; // [rsp+120h] [rbp+8h] BYREF
  unsigned int v66; // [rsp+128h] [rbp+10h]
  struct _GUID *v67; // [rsp+138h] [rbp+20h]

  v67 = a4;
  v66 = a2;
  v65 = a1;
  v5 = a4;
  v7 = a2;
  v8 = a1;
  v9 = 0;
  if ( !a1 || !a4 )
    return 3221225485LL;
  TickCount64 = GetTickCount64();
  v57 = TickCount64;
  if ( BypassServiceResponse(v8) )
    return 0;
  if ( StoreAppsAreDisabled() )
    return 3221226340LL;
  try
  {
    v51 = 0;
    v54[0] = 0;
    GetAppSessionGuidsFromJob(JobHandle, &v51, v54);
    v12 = 0;
    if ( v51 )
      v12 = (__int128)*v54[0];
    v60 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
    v13 = 0;
    if ( v54[0] )
      v13 = v54[0];
    v61 = v13;
    GetSidString((__int64)&v55, a3);
    v52 = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
    v53 = 0;
    v58 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Token = 0;
    if ( (int)UMgrQueryUserTokenFromSid(v56, &Token) >= 0 )
    {
      v14 = Token;
      v62 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      TokenHandle = 0;
      v64 = 0;
      CurrentThread = GetCurrentThread();
      OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle);
      v64 = SetThreadToken(0, v14);
      RpcHandle = GetRpcHandle((__int64)v54);
      if ( v53 )
      {
        if ( !((unsigned __int8 (__fastcall *)(void ***))*v52)(&v52) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v26, v27);
          __debugbreak();
        }
        v53 = 0;
      }
      v53 = *(_QWORD *)(RpcHandle + 8);
      *(_QWORD *)(RpcHandle + 8) = 0;
      v54[0] = (struct _GUID *)&Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
      if ( !v54[1] || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(v54) )
      {
        *(_OWORD *)v54 = v12;
        v17 = EnsureLicenseForOptionalPackageUsage(v53, (_DWORD)v8, v7, v56, (__int64)v5, (__int64)v54);
        if ( v17 >= 1 )
          v17 |= 0x80010000;
        OverrideImpersonationScope::~OverrideImpersonationScope((OverrideImpersonationScope *)&v62);
        goto LABEL_27;
      }
      v28 = GetLastError();
      if ( v28 > 0 )
        v28 = (unsigned __int16)v28 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v28, v29, v30);
LABEL_59:
      v31 = GetLastError();
      if ( v31 > 0 )
        v31 = (unsigned __int16)v31 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v31, v32, v33);
      __debugbreak();
    }
    v21 = GetRpcHandle((__int64)v54);
    if ( v53 )
    {
      if ( !((unsigned __int8 (__fastcall *)(void ***))*v52)(&v52) )
        goto LABEL_59;
      v53 = 0;
    }
    v53 = *(_QWORD *)(v21 + 8);
    *(_QWORD *)(v21 + 8) = 0;
    v54[0] = (struct _GUID *)&Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
    if ( v54[1] && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(v54) )
    {
      v34 = GetLastError();
      if ( v34 > 0 )
        v34 = (unsigned __int16)v34 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v34, v35, v36);
      __debugbreak();
    }
    *(_OWORD *)v54 = v12;
    v17 = EnsureLicenseForOptionalPackageUsage(v53, (_DWORD)v8, v7, v56, (__int64)v5, (__int64)v54);
    if ( v17 >= 1 )
      v17 |= 0x80010000;
LABEL_27:
    if ( v17 < 0 )
    {
      if ( (v17 & 0x1FFF0000) == 0x3F0000 || (v17 & 0x1FFF0000) == 0x7E10000 )
        goto LABEL_65;
      *(_OWORD *)v54 = v12;
      v17 = EnsureLicenseForOptionalPackageUsage(v53, (_DWORD)v8, v7, v56, (__int64)v5, (__int64)v54);
      if ( v17 >= 1 )
        v17 |= 0x80010000;
      if ( v17 < 0 )
LABEL_65:
        wil::details::in1diag3::_Throw_Hr((wil::details::in1diag3 *)0x3EF, v18, (const char *)(unsigned int)v17, v20);
    }
    v58 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    if ( Token )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v58) )
      {
        v37 = GetLastError();
        if ( v37 > 0 )
          v37 = (unsigned __int16)v37 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v37, v38, v39);
        goto LABEL_69;
      }
      Token = 0;
    }
    v52 = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
    if ( !v53 )
    {
LABEL_39:
      v55 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
      if ( !v56 )
      {
LABEL_42:
        v60 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
        if ( !v61 || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v60) )
          goto LABEL_81;
LABEL_75:
        v46 = GetLastError();
        if ( v46 > 0 )
          v46 = (unsigned __int16)v46 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v46, v47, v48);
        JUMPOUT(0x18000FD88LL);
      }
      if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v55) )
      {
        v56 = 0;
        goto LABEL_42;
      }
LABEL_72:
      v43 = GetLastError();
      if ( v43 > 0 )
        v43 = (unsigned __int16)v43 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v43, v44, v45);
      goto LABEL_75;
    }
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(&v52) )
    {
      v53 = 0;
      goto LABEL_39;
    }
LABEL_69:
    v40 = GetLastError();
    if ( v40 > 0 )
      v40 = (unsigned __int16)v40 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v40, v41, v42);
    goto LABEL_72;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException((wil::details::in1diag3 *)0x3F3, (unsigned int)&v50, v19);
    v51 = wil::ResultFromCaughtException(v49);
    v9 = 0;
    v5 = v67;
    v7 = v66;
    v8 = v65;
    v17 = v51;
    TickCount64 = v57;
  }
LABEL_81:
  if ( (unsigned int)dword_18001A010 > 5
    && (qword_18001A020 & 0x400000000000LL) != 0
    && (qword_18001A028 & 0x400000000000LL) == qword_18001A028 )
  {
    LODWORD(v65) = v17;
    v57 = GetTickCount64() - TickCount64;
    v54[0] = v5;
    v51 = v7;
    v52 = (void **)v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v22,
      (unsigned int)&unk_180016B07,
      v23,
      v24,
      (__int64)&v52,
      (__int64)&v51,
      (__int64)v54,
      (__int64)&v57,
      (__int64)&v65);
  }
  if ( v17 < 0 )
    return v17 | 0x20000000u;
  return v9;
}

```

## disassembly

```asm
0x18000f7d0  mov     rax, rsp
0x18000f7d3  mov     [rax+20h], r9
0x18000f7d7  mov     [rax+10h], edx
0x18000f7da  mov     [rax+8], rcx
0x18000f7de  push    rbx
0x18000f7df  push    rsi
0x18000f7e0  push    rdi
0x18000f7e1  push    r12
0x18000f7e3  push    r13
0x18000f7e5  push    r14
0x18000f7e7  push    r15
0x18000f7e9  sub     rsp, 0E0h
0x18000f7f0  movaps  xmmword ptr [rax-48h], xmm6
0x18000f7f4  mov     r14, r9
0x18000f7f7  mov     rbx, r8
0x18000f7fa  mov     r15d, edx
0x18000f7fd  mov     rsi, rcx
0x18000f800  xor     edi, edi
0x18000f802  test    rcx, rcx
0x18000f805  jz      loc_18000FC8A
0x18000f80b  test    r9, r9
0x18000f80e  jz      loc_18000FC8A
0x18000f814  call    cs:__imp_GetTickCount64
0x18000f81a  mov     r12, rax
0x18000f81d  mov     [rsp+118h+var_88], rax
0x18000f825  mov     rcx, rsi; unsigned __int16 *
0x18000f828  call    ?BypassServiceResponse@@YA_NPEBG@Z; BypassServiceResponse(ushort const *)
0x18000f82d  test    al, al
0x18000f82f  jz      short loc_18000F838
0x18000f831  xor     eax, eax
0x18000f833  jmp     loc_18000FC8F
0x18000f838  call    ?StoreAppsAreDisabled@@YA_NXZ; StoreAppsAreDisabled(void)
0x18000f83d  test    al, al
0x18000f83f  jz      short loc_18000F84B
0x18000f841  mov     eax, 0C0000364h
0x18000f846  jmp     loc_18000FC8F
0x18000f84b  mov     [rsp+118h+var_C8], edi
0x18000f84f  mov     [rsp+118h+var_A8], rdi
0x18000f854  lea     r8, [rsp+118h+var_A8]; struct _GUID **
0x18000f859  lea     rdx, [rsp+118h+var_C8]; unsigned int *
0x18000f85e  mov     rcx, [rsp+118h+JobHandle]; JobHandle
0x18000f866  call    ?GetAppSessionGuidsFromJob@@YAJPEAXPEAKPEAPEAU_GUID@@@Z; GetAppSessionGuidsFromJob(void *,ulong *,_GUID * *)
0x18000f86b  xorps   xmm6, xmm6
0x18000f86e  mov     rcx, [rsp+118h+var_A8]
0x18000f873  cmp     [rsp+118h+var_C8], edi
0x18000f877  jbe     short loc_18000F87C
0x18000f879  movups  xmm6, xmmword ptr [rcx]
0x18000f87c  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x18000f883  mov     [rsp+118h+var_70], rax
0x18000f88b  mov     rax, rdi
0x18000f88e  test    rcx, rcx
0x18000f891  cmovnz  rax, rcx
0x18000f895  mov     [rsp+118h+var_68], rax
0x18000f89d  mov     rdx, rbx
0x18000f8a0  lea     rcx, [rsp+118h+var_98]
0x18000f8a8  call    ?GetSidString@@YA?AV?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@PEAX@Z; GetSidString(void *)
0x18000f8ad  nop
0x18000f8ae  lea     r13, ??_7?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable'
0x18000f8b5  mov     [rsp+118h+var_C0], r13
0x18000f8ba  mov     [rsp+118h+var_B8], rdi
0x18000f8bf  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18000f8c6  mov     [rsp+118h+var_80], rax
0x18000f8ce  mov     [rsp+118h+Token], rdi
0x18000f8d6  lea     rdx, [rsp+118h+Token]
0x18000f8de  mov     rcx, [rsp+118h+var_90]
0x18000f8e6  call    cs:__imp_UMgrQueryUserTokenFromSid
0x18000f8ec  test    eax, eax
0x18000f8ee  js      loc_18000F9FA
0x18000f8f4  mov     rbx, [rsp+118h+Token]
0x18000f8fc  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18000f903  mov     [rsp+118h+var_60], rax
0x18000f90b  mov     [rsp+118h+TokenHandle], rdi
0x18000f913  mov     [rsp+118h+var_50], dil
0x18000f91b  call    cs:__imp_GetCurrentThread
0x18000f921  lea     r9, [rsp+118h+TokenHandle]; TokenHandle
0x18000f929  mov     edx, 4; DesiredAccess
0x18000f92e  lea     r8d, [rdx-3]; OpenAsSelf
0x18000f932  mov     rcx, rax; ThreadHandle
0x18000f935  call    cs:__imp_OpenThreadToken
0x18000f93b  mov     rdx, rbx; Token
0x18000f93e  xor     ecx, ecx; Thread
0x18000f940  call    cs:__imp_SetThreadToken
0x18000f946  test    eax, eax
0x18000f948  setnz   [rsp+118h+var_50]
0x18000f950  lea     rcx, [rsp+118h+var_A8]
0x18000f955  call    ?GetRpcHandle@@YA?AV?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@XZ; GetRpcHandle(void)
0x18000f95a  mov     rbx, rax
0x18000f95d  cmp     [rsp+118h+var_B8], rdi
0x18000f962  jz      short loc_18000F983
0x18000f964  mov     rcx, [rsp+118h+var_C0]
0x18000f969  mov     rax, [rcx]
0x18000f96c  lea     rcx, [rsp+118h+var_C0]
0x18000f971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f976  test    al, al
0x18000f978  jz      loc_18000FCAA
0x18000f97e  mov     [rsp+118h+var_B8], rdi
0x18000f983  mov     rax, [rbx+8]
0x18000f987  mov     [rsp+118h+var_B8], rax
0x18000f98c  mov     [rbx+8], rdi
0x18000f990  mov     [rsp+118h+var_A8], r13
0x18000f995  cmp     [rsp+118h+var_A8+8], rdi
0x18000f99a  jz      short loc_18000F9AE
0x18000f99c  lea     rcx, [rsp+118h+var_A8]
0x18000f9a1  call    ?InternalClose@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(void)
0x18000f9a6  test    al, al
0x18000f9a8  jz      loc_18000FCC5
0x18000f9ae  movdqa  xmmword ptr [rsp+118h+var_A8], xmm6
0x18000f9b4  lea     rax, [rsp+118h+var_A8]
0x18000f9b9  mov     [rsp+118h+var_F0], rax
0x18000f9be  mov     [rsp+118h+var_F8], r14
0x18000f9c3  mov     r9, [rsp+118h+var_90]
0x18000f9cb  mov     r8d, r15d
0x18000f9ce  mov     rdx, rsi
0x18000f9d1  mov     rcx, [rsp+118h+var_B8]
0x18000f9d6  call    EnsureLicenseForOptionalPackageUsage
0x18000f9db  mov     ebx, eax
0x18000f9dd  cmp     eax, 1
0x18000f9e0  jl      short loc_18000F9E8
0x18000f9e2  or      ebx, 80010000h
0x18000f9e8  lea     rcx, [rsp+118h+var_60]; this
0x18000f9f0  call    ??1OverrideImpersonationScope@@QEAA@XZ; OverrideImpersonationScope::~OverrideImpersonationScope(void)
0x18000f9f5  jmp     loc_18000FA92
0x18000f9fa  lea     rcx, [rsp+118h+var_A8]
0x18000f9ff  call    ?GetRpcHandle@@YA?AV?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@XZ; GetRpcHandle(void)
0x18000fa04  mov     rbx, rax
0x18000fa07  cmp     [rsp+118h+var_B8], rdi
0x18000fa0c  jz      short loc_18000FA2D
0x18000fa0e  mov     rcx, [rsp+118h+var_C0]
0x18000fa13  mov     rax, [rcx]
0x18000fa16  lea     rcx, [rsp+118h+var_C0]
0x18000fa1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa20  test    al, al
0x18000fa22  jz      loc_18000FCDF
0x18000fa28  mov     [rsp+118h+var_B8], rdi
0x18000fa2d  mov     rax, [rbx+8]
0x18000fa31  mov     [rsp+118h+var_B8], rax
0x18000fa36  mov     [rbx+8], rdi
0x18000fa3a  mov     [rsp+118h+var_A8], r13
0x18000fa3f  cmp     [rsp+118h+var_A8+8], rdi
0x18000fa44  jz      short loc_18000FA58
0x18000fa46  lea     rcx, [rsp+118h+var_A8]
0x18000fa4b  call    ?InternalClose@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(void)
0x18000fa50  test    al, al
0x18000fa52  jz      loc_18000FCF9
0x18000fa58  movdqa  xmmword ptr [rsp+118h+var_A8], xmm6
0x18000fa5e  lea     rax, [rsp+118h+var_A8]
0x18000fa63  mov     [rsp+118h+var_F0], rax
0x18000fa68  mov     [rsp+118h+var_F8], r14
0x18000fa6d  mov     r9, [rsp+118h+var_90]
0x18000fa75  mov     r8d, r15d
0x18000fa78  mov     rdx, rsi
0x18000fa7b  mov     rcx, [rsp+118h+var_B8]
0x18000fa80  call    EnsureLicenseForOptionalPackageUsage
0x18000fa85  mov     ebx, eax
0x18000fa87  cmp     eax, 1
0x18000fa8a  jl      short loc_18000FA92
0x18000fa8c  or      ebx, 80010000h
0x18000fa92  test    ebx, ebx
0x18000fa94  jns     short loc_18000FAF5
0x18000fa96  mov     eax, ebx
0x18000fa98  and     eax, 1FFF0000h
0x18000fa9d  cmp     eax, 3F0000h
0x18000faa2  jz      loc_18000FD13
0x18000faa8  cmp     eax, 7E10000h
0x18000faad  jz      loc_18000FD13
0x18000fab3  movdqa  xmmword ptr [rsp+118h+var_A8], xmm6
0x18000fab9  lea     rax, [rsp+118h+var_A8]
0x18000fabe  mov     [rsp+118h+var_F0], rax
0x18000fac3  mov     [rsp+118h+var_F8], r14
0x18000fac8  mov     r9, [rsp+118h+var_90]
0x18000fad0  mov     r8d, r15d
0x18000fad3  mov     rdx, rsi
0x18000fad6  mov     rcx, [rsp+118h+var_B8]
0x18000fadb  call    EnsureLicenseForOptionalPackageUsage
0x18000fae0  mov     ebx, eax
0x18000fae2  cmp     eax, 1
0x18000fae5  jl      short loc_18000FAED
0x18000fae7  or      ebx, 80010000h
0x18000faed  test    ebx, ebx
0x18000faef  js      loc_18000FD13
0x18000faf5  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18000fafc  mov     [rsp+118h+var_80], rax
0x18000fb04  cmp     [rsp+118h+Token], rdi
0x18000fb0c  jz      short loc_18000FB2B
0x18000fb0e  lea     rcx, [rsp+118h+var_80]
0x18000fb16  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x18000fb1b  test    al, al
0x18000fb1d  jz      loc_18000FD21
0x18000fb23  mov     [rsp+118h+Token], rdi
0x18000fb2b  mov     [rsp+118h+var_C0], r13
0x18000fb30  cmp     [rsp+118h+var_B8], rdi
0x18000fb35  jz      short loc_18000FB4E
0x18000fb37  lea     rcx, [rsp+118h+var_C0]
0x18000fb3c  call    ?InternalClose@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(void)
0x18000fb41  test    al, al
0x18000fb43  jz      loc_18000FD3B
0x18000fb49  mov     [rsp+118h+var_B8], rdi
0x18000fb4e  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x18000fb55  mov     [rsp+118h+var_98], rax
0x18000fb5d  cmp     [rsp+118h+var_90], rdi
0x18000fb65  jz      short loc_18000FB84
0x18000fb67  lea     rcx, [rsp+118h+var_98]
0x18000fb6f  call    ?InternalClose@?$HandleT@ULocalAllocMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(void)
0x18000fb74  test    al, al
0x18000fb76  jz      loc_18000FD55
0x18000fb7c  mov     [rsp+118h+var_90], rdi
0x18000fb84  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x18000fb8b  mov     [rsp+118h+var_70], rax
0x18000fb93  cmp     [rsp+118h+var_68], rdi
0x18000fb9b  jz      short loc_18000FBB2
0x18000fb9d  lea     rcx, [rsp+118h+var_70]
0x18000fba5  call    ?InternalClose@?$HandleT@ULocalAllocMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(void)
0x18000fbaa  test    al, al
0x18000fbac  jz      loc_18000FD6F
0x18000fbb2  jmp     short loc_18000FBDA
0x18000fbb4  xor     edi, edi
0x18000fbb6  mov     r14, [rsp+118h+arg_18]
0x18000fbbe  mov     r15d, [rsp+118h+arg_8]
0x18000fbc6  mov     rsi, [rsp+118h+arg_0]
0x18000fbce  mov     ebx, [rsp+118h+var_C8]
0x18000fbd2  mov     r12, [rsp+118h+var_88]
0x18000fbda  mov     eax, cs:dword_18001A010
0x18000fbe0  cmp     eax, 5
0x18000fbe3  jbe     loc_18000FC7C
0x18000fbe9  mov     rcx, cs:qword_18001A028
0x18000fbf0  mov     rax, cs:qword_18001A020
0x18000fbf7  mov     rdx, 400000000000h
0x18000fc01  test    rdx, rax
0x18000fc04  jz      short loc_18000FC7C
0x18000fc06  mov     rax, rcx
0x18000fc09  and     rax, rdx
0x18000fc0c  cmp     rax, rcx
0x18000fc0f  jnz     short loc_18000FC7C
0x18000fc11  mov     dword ptr [rsp+118h+arg_0], ebx
0x18000fc18  call    cs:__imp_GetTickCount64
0x18000fc1e  sub     rax, r12
0x18000fc21  mov     [rsp+118h+var_88], rax
0x18000fc29  mov     [rsp+118h+var_A8], r14
0x18000fc2e  mov     [rsp+118h+var_C8], r15d
0x18000fc33  mov     [rsp+118h+var_C0], rsi
0x18000fc38  lea     rax, [rsp+118h+arg_0]
0x18000fc40  mov     [rsp+118h+var_D8], rax
0x18000fc45  lea     rax, [rsp+118h+var_88]
0x18000fc4d  mov     [rsp+118h+var_E0], rax
0x18000fc52  lea     rax, [rsp+118h+var_A8]
0x18000fc57  mov     [rsp+118h+var_E8], rax
0x18000fc5c  lea     rax, [rsp+118h+var_C8]
0x18000fc61  mov     [rsp+118h+var_F0], rax
0x18000fc66  lea     rax, [rsp+118h+var_C0]
0x18000fc6b  mov     [rsp+118h+var_F8], rax
0x18000fc70  lea     rdx, unk_180016B07
0x18000fc77  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000fc7c  test    ebx, ebx
0x18000fc7e  jns     short loc_18000FC86
0x18000fc80  bts     ebx, 1Dh
0x18000fc84  mov     edi, ebx
0x18000fc86  mov     eax, edi
0x18000fc88  jmp     short loc_18000FC8F
0x18000fc8a  mov     eax, 0C000000Dh
0x18000fc8f  movaps  xmm6, [rsp+118h+var_48]
0x18000fc97  add     rsp, 0E0h
0x18000fc9e  pop     r15
0x18000fca0  pop     r14
0x18000fca2  pop     r13
0x18000fca4  pop     r12
0x18000fca6  pop     rdi
0x18000fca7  pop     rsi
0x18000fca8  pop     rbx
0x18000fca9  retn
0x18000fcaa  call    cs:__imp_GetLastError
0x18000fcb0  nop
0x18000fcb1  test    eax, eax
0x18000fcb3  jle     short loc_18000FCBD
0x18000fcb5  movzx   eax, ax
0x18000fcb8  or      eax, 80070000h
0x18000fcbd  mov     ecx, eax; this
0x18000fcbf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000fcc4  int     3; Trap to Debugger
0x18000fcc5  call    cs:__imp_GetLastError
0x18000fccb  test    eax, eax
0x18000fccd  jle     short loc_18000FCD7
0x18000fccf  movzx   eax, ax
0x18000fcd2  or      eax, 80070000h
0x18000fcd7  mov     ecx, eax; this
0x18000fcd9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000fcde  nop
0x18000fcdf  call    cs:__imp_GetLastError
0x18000fce5  test    eax, eax
0x18000fce7  jle     short loc_18000FCF1
0x18000fce9  movzx   eax, ax
0x18000fcec  or      eax, 80070000h
0x18000fcf1  mov     ecx, eax; this
0x18000fcf3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000fcf8  int     3; Trap to Debugger
0x18000fcf9  call    cs:__imp_GetLastError
0x18000fcff  test    eax, eax
0x18000fd01  jle     short loc_18000FD0B
0x18000fd03  movzx   eax, ax
0x18000fd06  or      eax, 80070000h
0x18000fd0b  mov     ecx, eax; this
  ... truncated ...
```
