# PluginResourceManager::SignalPluginPause(_GUID)

- ea: `0x180010350`
- end: `0x180010606`
- name: `?SignalPluginPause@PluginResourceManager@@UEAAJU_GUID@@@Z`
- size: `694`
- prototype: `int(PluginResourceManager *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000f880`
- `0x180010350`
- `0x1800110b8`
- `0x180012120`
- `0x180012190`
- `0x18002bf00`
- `0x1800771ac`
- `0x18009b43c`
- `0x1800fc1f8`
- `0x1801244c0`
- `0x1801249b0`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001053c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001053c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010390`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010390`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800104ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800104ae`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800103a8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800103a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001052d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001052d`

## string_xrefs

- `0x180010576`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1800105b4`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PluginResourceManager::SignalPluginPause(PluginResourceManager *this, struct _GUID *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r8
  void **v9; // r9
  __int64 v10; // rcx
  unsigned __int64 i; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // r14
  _QWORD *v16; // rdx
  void **v17; // rcx
  __int64 v18; // rcx
  void *v19; // rcx
  LPOLESTR lpsz; // [rsp+20h] [rbp-78h] BYREF
  void *v22; // [rsp+28h] [rbp-70h] BYREF
  unsigned __int64 v23[2]; // [rsp+30h] [rbp-68h] BYREF
  void *Block[2]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v25; // [rsp+50h] [rbp-48h]
  unsigned __int64 v26; // [rsp+58h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( !g_pGatheringService )
  {
    v6 = -2147215342;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x205,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
      (const char *)0x80041812LL,
      (int)lpsz);
    return v6;
  }
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 152);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v22 = v4;
  lpsz = 0;
  v5 = StringFromCLSID(a2, &lpsz);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20A,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
      (const char *)(unsigned int)v5,
      (int)lpsz);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v22);
    return v6;
  }
  *(_OWORD *)Block = 0;
  v25 = 0;
  v26 = 0;
  std::wstring::_Construct_empty(Block);
  v7 = -1;
  do
    ++v7;
  while ( lpsz[v7] );
  try
  {
    std::wstring::_Assign<wchar_t>(Block);
    v8 = v25;
    v9 = Block;
    if ( v26 > 7 )
      v9 = (void **)Block[0];
    v10 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 2 * v25; ++i )
      v10 = 0x100000001B3LL * (*((unsigned __int8 *)v9 + i) ^ (unsigned __int64)v10);
    v12 = 2 * (v10 & *((_QWORD *)this + 17));
    v13 = *((_QWORD *)this + 14);
    v14 = *(_QWORD *)(v13 + 8 * v12 + 8);
    if ( v14 != *((_QWORD *)this + 12) )
    {
      v15 = *(_QWORD *)(v13 + 8 * v12);
      while ( 1 )
      {
        v16 = (_QWORD *)(v14 + 16);
        if ( *(_QWORD *)(v14 + 40) > 7u )
          v16 = (_QWORD *)*v16;
        v17 = Block;
        if ( v26 > 7 )
          v17 = (void **)Block[0];
        if ( v8 == *(_QWORD *)(v14 + 32) )
        {
          if ( !v8 || !(unsigned int)std::_WChar_traits<wchar_t>::compare(v17, v16) )
            goto LABEL_40;
          v8 = v25;
        }
        if ( v14 == v15 )
          break;
        v14 = *(_QWORD *)(v14 + 8);
      }
    }
    v14 = 0;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      529,
      "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx");
  }
LABEL_40:
  if ( v14 && v14 != *((_QWORD *)this + 12) )
  {
    *(_QWORD *)(v14 + 64) = GetTickCount64();
    v18 = *(_QWORD *)(v14 + 80);
    *(struct _GUID *)v23 = *a2;
    (*(void (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v18 + 88LL))(v18, v23);
    *(_BYTE *)(v14 + 72) = 1;
  }
  if ( v26 > 7 )
  {
    v23[0] = 2 * v26 + 2;
    v19 = Block[0];
    v22 = Block[0];
    if ( v23[0] >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v22, v23);
      v19 = v22;
    }
    operator delete(v19);
  }
  v25 = 0;
  v26 = 7;
  LOWORD(Block[0]) = 0;
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( v4 )
    LeaveCriticalSection(v4);
  return 0;
}

```

## disassembly

```asm
0x180010350  mov     [rsp+arg_10], rbx
0x180010355  push    rsi
0x180010356  push    rdi
0x180010357  push    r12
0x180010359  push    r14
0x18001035b  push    r15
0x18001035d  sub     rsp, 70h
0x180010361  mov     rax, cs:__security_cookie
0x180010368  xor     rax, rsp
0x18001036b  mov     [rsp+98h+var_38], rax
0x180010370  mov     r15, rdx
0x180010373  mov     rsi, rcx
0x180010376  xor     r12d, r12d
0x180010379  cmp     cs:?g_pGatheringService@@3PEAVCGatheringService@@EA, r12; CGatheringService * g_pGatheringService
0x180010380  jz      loc_180010566
0x180010386  lea     rdi, [rcx+98h]
0x18001038d  mov     rcx, rdi; lpCriticalSection
0x180010390  call    cs:__imp_EnterCriticalSection
0x180010396  mov     [rsp+98h+var_70], rdi
0x18001039b  mov     [rsp+98h+lpsz], r12; int
0x1800103a0  lea     rdx, [rsp+98h+lpsz]; lplpsz
0x1800103a5  mov     rcx, r15; rclsid
0x1800103a8  call    cs:__imp_StringFromCLSID
0x1800103ae  mov     ebx, eax
0x1800103b0  test    eax, eax
0x1800103b2  js      loc_1800105A9
0x1800103b8  xorps   xmm0, xmm0
0x1800103bb  movups  xmmword ptr [rsp+98h+Block], xmm0
0x1800103c0  mov     [rsp+98h+var_48], r12
0x1800103c5  mov     [rsp+98h+var_40], r12
0x1800103ca  lea     rcx, [rsp+98h+Block]
0x1800103cf  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800103d4  nop
0x1800103d5  mov     rdx, [rsp+98h+lpsz]
0x1800103da  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800103de  inc     r8
0x1800103e1  cmp     [rdx+r8*2], r12w
0x1800103e6  jnz     short loc_1800103DE
0x1800103e8  lea     rcx, [rsp+98h+Block]
0x1800103ed  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800103f2  nop
0x1800103f3  mov     r8, [rsp+98h+var_48]
0x1800103f8  lea     r9, [rsp+98h+Block]
0x1800103fd  cmp     [rsp+98h+var_40], 7
0x180010403  cmova   r9, [rsp+98h+Block]
0x180010409  mov     rcx, 0CBF29CE484222325h
0x180010413  lea     r10, [r8+r8]
0x180010417  mov     rdx, r12
0x18001041a  test    r10, r10
0x18001041d  jz      short loc_18001043D
0x18001041f  movzx   eax, byte ptr [r9+rdx]
0x180010424  xor     rcx, rax
0x180010427  mov     r11, 100000001B3h
0x180010431  imul    rcx, r11
0x180010435  inc     rdx
0x180010438  cmp     rdx, r10
0x18001043b  jb      short loc_18001041F
0x18001043d  mov     rax, [rsi+88h]
0x180010444  and     rax, rcx
0x180010447  add     rax, rax
0x18001044a  mov     rcx, [rsi+70h]
0x18001044e  mov     rbx, [rcx+rax*8+8]
0x180010453  cmp     rbx, [rsi+60h]
0x180010457  jz      short loc_1800104A0
0x180010459  mov     r14, [rcx+rax*8]
0x18001045d  lea     rdx, [rbx+10h]
0x180010461  cmp     qword ptr [rbx+28h], 7
0x180010466  jbe     short loc_18001046B
0x180010468  mov     rdx, [rdx]
0x18001046b  lea     rcx, [rsp+98h+Block]
0x180010470  cmp     [rsp+98h+var_40], 7
0x180010476  cmova   rcx, [rsp+98h+Block]
0x18001047c  cmp     r8, [rbx+20h]
0x180010480  jnz     short loc_180010495
0x180010482  test    r8, r8
0x180010485  jz      short loc_1800104A3
0x180010487  call    ?compare@?$_WChar_traits@_W@std@@SAHQEB_W0_K@Z; std::_WChar_traits<wchar_t>::compare(wchar_t const * const,wchar_t const * const,unsigned __int64)
0x18001048c  test    eax, eax
0x18001048e  jz      short loc_1800104A3
0x180010490  mov     r8, [rsp+98h+var_48]
0x180010495  cmp     rbx, r14
0x180010498  jz      short loc_1800104A0
0x18001049a  mov     rbx, [rbx+8]
0x18001049e  jmp     short loc_18001045D
0x1800104a0  mov     rbx, r12
0x1800104a3  test    rbx, rbx
0x1800104a6  jz      short loc_1800104DB
0x1800104a8  cmp     rbx, [rsi+60h]
0x1800104ac  jz      short loc_1800104DB
0x1800104ae  call    cs:__imp_GetTickCount64
0x1800104b4  mov     [rbx+40h], rax
0x1800104b8  mov     rcx, [rbx+50h]
0x1800104bc  movups  xmm0, xmmword ptr [r15]
0x1800104c0  movdqu  xmmword ptr [rsp+98h+var_68], xmm0
0x1800104c6  mov     rax, [rcx]
0x1800104c9  lea     rdx, [rsp+98h+var_68]
0x1800104ce  mov     rax, [rax+58h]
0x1800104d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104d7  mov     byte ptr [rbx+48h], 1
0x1800104db  mov     rdx, [rsp+98h+var_40]
0x1800104e0  cmp     rdx, 7
0x1800104e4  jbe     short loc_18001050F
0x1800104e6  lea     rdx, ds:2[rdx*2]
0x1800104ee  mov     [rsp+98h+var_68], rdx
0x1800104f3  mov     rcx, [rsp+98h+Block]; Block
0x1800104f8  mov     [rsp+98h+var_70], rcx
0x1800104fd  cmp     rdx, 1000h
0x180010504  jnb     loc_18001058B
0x18001050a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001050f  mov     [rsp+98h+var_48], r12
0x180010514  mov     [rsp+98h+var_40], 7
0x18001051d  mov     word ptr [rsp+98h+Block], r12w
0x180010523  mov     rcx, [rsp+98h+lpsz]; pv
0x180010528  test    rcx, rcx
0x18001052b  jz      short loc_180010534
0x18001052d  call    cs:__imp_CoTaskMemFree
0x180010533  nop
0x180010534  test    rdi, rdi
0x180010537  jz      short loc_180010542
0x180010539  mov     rcx, rdi; lpCriticalSection
0x18001053c  call    cs:__imp_LeaveCriticalSection
0x180010542  xor     eax, eax
0x180010544  mov     rcx, [rsp+98h+var_38]
0x180010549  xor     rcx, rsp; StackCookie
0x18001054c  call    __security_check_cookie
0x180010551  mov     rbx, [rsp+98h+arg_10]
0x180010559  add     rsp, 70h
0x18001055d  pop     r15
0x18001055f  pop     r14
0x180010561  pop     r12
0x180010563  pop     rdi
0x180010564  pop     rsi
0x180010565  retn
0x180010566  mov     rcx, [rsp+98h]; this
0x18001056e  mov     ebx, 80041812h
0x180010573  mov     r9d, ebx; char *
0x180010576  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18001057d  mov     edx, 205h; void *
0x180010582  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010587  mov     eax, ebx
0x180010589  jmp     short loc_180010544
0x18001058b  lea     rdx, [rsp+98h+var_68]; unsigned __int64 *
0x180010590  lea     rcx, [rsp+98h+var_70]; void **
0x180010595  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18001059a  mov     rdx, [rsp+98h+var_68]
0x18001059f  mov     rcx, [rsp+98h+var_70]
0x1800105a4  jmp     loc_18001050A
0x1800105a9  mov     rcx, [rsp+98h]; this
0x1800105b1  mov     r9d, ebx; char *
0x1800105b4  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800105bb  mov     edx, 20Ah; void *
0x1800105c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800105c5  nop
0x1800105c6  lea     rcx, [rsp+98h+lpsz]
0x1800105cb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800105d0  nop
0x1800105d1  lea     rcx, [rsp+98h+var_70]
0x1800105d6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800105db  jmp     short loc_180010587
0x1800105dd  lea     rcx, [rsp+98h+Block]; this
0x1800105e2  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x1800105e7  nop
0x1800105e8  lea     rcx, [rsp+98h+lpsz]
0x1800105ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800105f2  nop
0x1800105f3  lea     rcx, [rsp+98h+var_70]
0x1800105f8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800105fd  mov     eax, dword ptr [rsp+98h+var_68]
0x180010601  jmp     loc_180010544
```
