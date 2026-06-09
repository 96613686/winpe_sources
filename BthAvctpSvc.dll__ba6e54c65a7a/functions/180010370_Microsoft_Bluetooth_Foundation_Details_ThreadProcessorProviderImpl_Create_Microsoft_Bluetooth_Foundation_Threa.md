# Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProviderImpl::Create(Microsoft::Bluetooth::Foundation::ThreadProcessorTag)

- ea: `0x180010370`
- end: `0x180010697`
- name: `?Create@ThreadProcessorProviderImpl@Details@Foundation@Bluetooth@Microsoft@@UEAA?AV?$unique_ptr@VThreadProcessorControl@Foundation@Bluetooth@Microsoft@@U?$default_delete@VThreadProcessorControl@Foundation@Bluetooth@Microsoft@@@std@@@std@@W4ThreadProcessorTag@345@@Z`
- size: `807`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001dd0`
- `0x1800021dc`
- `0x180004040`
- `0x18000de78`
- `0x18000deb0`
- `0x18000ee08`
- `0x18000f3a0`
- `0x18000f6b8`
- `0x18000f9c8`
- `0x18000f9ec`
- `0x180010370`
- `0x180010b78`
- `0x180010bf4`
- `0x180010ce0`
- `0x180011874`
- `0x180012040`
- `0x180012240`
- `0x180012600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800103b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800103b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProviderImpl::Create(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3)
{
  __int64 v5; // rbx
  struct _GUID *v6; // rdx
  std::_Ref_count_base *v7; // r8
  char v8; // bl
  _UNKNOWN **v9; // rdx
  std::_Ref_count_base **v10; // rbx
  std::_Ref_count_base *v11; // rax
  std::_Ref_count_base *v12; // rdi
  char v13; // bl
  _DWORD *v14; // rax
  struct _GUID v15; // xmm6
  std::_Ref_count_base *v16; // r12
  std::_Ref_count_base *v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rcx
  std::_Ref_count_base *v20; // rax
  std::_Ref_count_base *v21; // rsi
  std::_Ref_count_base *v22; // rdx
  char v23; // r10
  int v24; // r8d
  char v25; // r10
  int v26; // edx
  __int64 v27; // rcx
  unsigned int v29; // [rsp+28h] [rbp-B9h]
  unsigned int v30; // [rsp+68h] [rbp-79h] BYREF
  std::_Ref_count_base *v31[2]; // [rsp+70h] [rbp-71h] BYREF
  std::_Ref_count_base *v32; // [rsp+80h] [rbp-61h] BYREF
  __int64 v33; // [rsp+88h] [rbp-59h] BYREF
  _QWORD v34[3]; // [rsp+90h] [rbp-51h] BYREF
  GUID v35[2]; // [rsp+A8h] [rbp-39h] BYREF
  std::_Ref_count_base *v36; // [rsp+C8h] [rbp-19h]
  std::_Ref_count_base *v37; // [rsp+D0h] [rbp-11h]
  struct _GUID v38; // [rsp+D8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+5Fh]

  v30 = a3;
  v5 = a1 + 32;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  v34[0] = v5;
  std::_Tree<std::_Tmap_traits<enum Microsoft::Bluetooth::Foundation::ThreadProcessorTag,std::pair<_GUID,std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadProcessorControl>>,std::less<enum Microsoft::Bluetooth::Foundation::ThreadProcessorTag>,std::allocator<std::pair<enum Microsoft::Bluetooth::Foundation::ThreadProcessorTag const,std::pair<_GUID,std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadProcessorControl>>>>,0>>::find(
    a1 + 72,
    &v32,
    &v30);
  v7 = *(std::_Ref_count_base **)(a1 + 72);
  if ( v32 != v7 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (v8 = 1, (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0)
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      v8 = 0;
    }
    v9 = &WPP_RECORDER_INITIALIZED;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = v8;
      WPP_RECORDER_AND_TRACE_SF_ThreadProcessorTagq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v9,
        (_DWORD)v7,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        2);
    }
    wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x1CE, (unsigned int)v7, (const char *)0xB7, v29);
  }
  v38 = *Microsoft::Bluetooth::Foundation::GuidFactory::GetNextId(v35, v6);
  v10 = (std::_Ref_count_base **)Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProviderImpl,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProviderImpl>>::Instance(v35);
  v11 = (std::_Ref_count_base *)operator new(0x48u);
  v32 = v11;
  v31[0] = *v10;
  v31[1] = v10[1];
  *v10 = 0;
  v10[1] = 0;
  v12 = (std::_Ref_count_base *)Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProvider::ThreadProcessorProviderToken::ThreadProcessorProviderToken(
                                  (__int64)v11,
                                  v30,
                                  (__int128 *)&v38,
                                  (__int64 *)v31);
  v32 = v12;
  if ( *(_QWORD *)v35[0].Data4 )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v35[0].Data4);
  *(_OWORD *)v31 = 0;
  v13 = 1;
  if ( v12 )
  {
    v14 = operator new(0x18u);
    v34[2] = v14;
    *(_OWORD *)v14 = 0;
    v14[2] = 1;
    v14[3] = 1;
    *(_QWORD *)v14 = &std::_Ref_count_resource<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProvider::ThreadProcessorProviderToken *,std::default_delete<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProvider::ThreadProcessorProviderToken>>::`vftable';
    *((_QWORD *)v14 + 2) = v12;
    v31[0] = v12;
    v31[1] = (std::_Ref_count_base *)v14;
    v32 = 0;
  }
  Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::MakeAutoStop(&v33, v30, v31);
  std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(
    v31,
    (_QWORD *)(v33 + 8));
  v15 = v38;
  v35[1] = v38;
  v16 = v31[0];
  v36 = v31[0];
  v17 = v31[1];
  v37 = v31[1];
  *(_OWORD *)v31 = 0;
  v18 = std::map<enum Microsoft::Bluetooth::Foundation::ThreadProcessorTag,std::pair<_GUID,std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadProcessorControl>>>::_Try_emplace<enum Microsoft::Bluetooth::Foundation::ThreadProcessorTag const &,>(
          (__int64 *)(a1 + 72),
          (__int64)v35,
          &v30);
  v19 = *(_QWORD *)v18;
  *(struct _GUID *)(*(_QWORD *)v18 + 40LL) = v15;
  v20 = v17;
  v21 = v17;
  if ( v17 )
  {
    _InterlockedAdd((volatile signed __int32 *)v17 + 3, 1u);
  }
  else
  {
    v16 = 0;
    v17 = 0;
  }
  *(_QWORD *)(v19 + 56) = v16;
  v22 = *(std::_Ref_count_base **)(v19 + 64);
  *(_QWORD *)(v19 + 64) = v17;
  if ( v22 )
    std::_Ref_count_base::_Decwref(v22);
  else
    v21 = v20;
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (v23 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    v23 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 24) )
    v13 = 0;
  if ( v23 || v13 )
  {
    std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(
      v31,
      (_QWORD *)(v33 + 8));
    LOBYTE(v24) = v13;
    LOBYTE(v26) = v25;
    WPP_RECORDER_AND_TRACE_SF_q_guid_I(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v26,
      v24,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    if ( v31[1] )
      std::_Ref_count_base::_Decref(v31[1]);
  }
  v27 = v33;
  v33 = 0;
  *a2 = v27;
  std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorControlAutoStop>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorControlAutoStop>(&v33);
  std::unique_ptr<Microsoft::Bluetooth::Foundation::EventNotifier::EventRegistration>::~unique_ptr<Microsoft::Bluetooth::Foundation::EventNotifier::EventRegistration>(&v32);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v34);
  return a2;
}

```

## disassembly

```asm
0x180010370  mov     rax, rsp
0x180010373  mov     [rax+20h], rbx
0x180010377  push    rbp
0x180010378  push    rsi
0x180010379  push    rdi
0x18001037a  push    r12
0x18001037c  push    r13
0x18001037e  push    r14
0x180010380  push    r15
0x180010382  lea     rbp, [rax-5Fh]
0x180010386  sub     rsp, 100h
0x18001038d  movaps  xmmword ptr [rax-48h], xmm6
0x180010391  mov     rax, cs:__security_cookie
0x180010398  xor     rax, rsp
0x18001039b  mov     [rbp+57h+var_50], rax
0x18001039f  mov     r14, rdx
0x1800103a2  mov     r15, rcx
0x1800103a5  mov     [rbp+57h+var_A8], rdx
0x1800103a9  mov     [rbp+57h+var_D0], r8d
0x1800103ad  xor     r13d, r13d
0x1800103b0  lea     rbx, [rcx+20h]
0x1800103b4  mov     rcx, rbx; lpCriticalSection
0x1800103b7  call    cs:__imp_EnterCriticalSection
0x1800103bd  mov     [rbp+57h+var_A8], rbx
0x1800103c1  lea     rsi, [r15+48h]
0x1800103c5  lea     r8, [rbp+57h+var_D0]
0x1800103c9  lea     rdx, [rbp+57h+var_B8]
0x1800103cd  mov     rcx, rsi
0x1800103d0  call    ?find@?$_Tree@V?$_Tmap_traits@W4ThreadProcessorTag@Foundation@Bluetooth@Microsoft@@U?$pair@U_GUID@@V?$weak_ptr@VThreadProcessorControl@Foundation@Bluetooth@Microsoft@@@std@@@std@@U?$less@W4ThreadProcessorTag@Foundation@Bluetooth@Microsoft@@@6@V?$allocator@U?$pair@$$CBW4ThreadProcessorTag@Foundation@Bluetooth@Microsoft@@U?$pair@U_GUID@@V?$weak_ptr@VThreadProcessorControl@Foundation@Bluetooth@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ThreadProcessorTag@Foundation@Bluetooth@Microsoft@@U?$pair@U_GUID@@V?$weak_ptr@VThreadProcessorControl@Foundation@Bluetooth@Microsoft@@@std@@@std@@@std@@@std@@@std@@@2@AEBW4ThreadProcessorTag@Foundation@Bluetooth@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Bluetooth::Foundation::ThreadProcessorTag,std::pair<_GUID,std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadProcessorControl>>,std::less<Microsoft::Bluetooth::Foundation::ThreadProcessorTag>,std::allocator<std::pair<Microsoft::Bluetooth::Foundation::ThreadProcessorTag const,std::pair<_GUID,std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadProcessorControl>>>>,0>>::find(Microsoft::Bluetooth::Foundation::ThreadProcessorTag const &)
0x1800103d5  mov     r8, [rsi]
0x1800103d8  cmp     [rbp+57h+var_B8], r8
0x1800103dc  jz      short loc_18001045A
0x1800103de  lea     rdx, WPP_GLOBAL_Control
0x1800103e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103ec  cmp     rcx, rdx
0x1800103ef  jz      short loc_180010400
0x1800103f1  lea     ebx, [r13+1]
0x1800103f5  test    [rcx+1Ch], bl
0x1800103f8  jz      short loc_180010400
0x1800103fa  cmp     byte ptr [rcx+19h], 2
0x1800103fe  jnb     short loc_180010403
0x180010400  mov     bl, r13b
0x180010403  lea     rdx, WPP_RECORDER_INITIALIZED
0x18001040a  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x180010411  setnz   r8b
0x180010415  test    bl, bl
0x180010417  jnz     short loc_18001041E
0x180010419  test    r8b, r8b
0x18001041c  jz      short loc_180010445
0x18001041e  mov     [rsp+130h+var_E8], r15
0x180010423  mov     eax, [rbp+57h+var_D0]
0x180010426  mov     dword ptr [rsp+130h+var_F0], eax
0x18001042a  mov     [rsp+130h+var_100], 1Dh
0x180010431  mov     byte ptr [rsp+130h+var_110], 2; unsigned int
0x180010436  mov     r9, [rcx+28h]
0x18001043a  mov     dl, bl
0x18001043c  mov     rcx, [rcx+10h]
0x180010440  call    WPP_RECORDER_AND_TRACE_SF_ThreadProcessorTagq
0x180010445  mov     rcx, [rbp+5Fh]; this
0x180010449  mov     edx, 1CEh; void *
0x18001044e  mov     r9d, 0B7h; char *
0x180010454  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001045a  lea     rcx, [rbp+57h+var_90]; this
0x18001045e  call    ?GetNextId@GuidFactory@Foundation@Bluetooth@Microsoft@@YA?AU_GUID@@XZ; Microsoft::Bluetooth::Foundation::GuidFactory::GetNextId(void)
0x180010463  movups  xmm0, xmmword ptr [rax]
0x180010466  movdqu  [rbp+57h+var_60], xmm0
0x18001046b  lea     rcx, [rbp+57h+var_90]
0x18001046f  call    ?Instance@?$SingletonWithFactory@VThreadProcessorProviderImpl@Details@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadProcessorProviderImpl@Details@Foundation@Bluetooth@Microsoft@@@345@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VThreadProcessorProviderImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProviderImpl,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProviderImpl>>::Instance(void)
0x180010474  mov     rbx, rax
0x180010477  mov     ecx, 48h ; 'H'; Size
0x18001047c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010481  mov     [rbp+57h+var_B8], rax
0x180010485  mov     rcx, [rbx]
0x180010488  mov     [rbp+57h+var_C8], rcx
0x18001048c  mov     rcx, [rbx+8]
0x180010490  mov     [rbp+57h+var_C8+8], rcx
0x180010494  mov     [rbx], r13
0x180010497  mov     [rbx+8], r13
0x18001049b  lea     r9, [rbp+57h+var_C8]
0x18001049f  lea     r8, [rbp+57h+var_60]
0x1800104a3  mov     edx, [rbp+57h+var_D0]
0x1800104a6  mov     rcx, rax
0x1800104a9  call    ??0ThreadProcessorProviderToken@ThreadProcessorProvider@Details@Foundation@Bluetooth@Microsoft@@QEAA@W4ThreadProcessorTag@345@AEBU_GUID@@V?$shared_ptr@VThreadProcessorProvider@Details@Foundation@Bluetooth@Microsoft@@@std@@@Z; Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProvider::ThreadProcessorProviderToken::ThreadProcessorProviderToken(Microsoft::Bluetooth::Foundation::ThreadProcessorTag,_GUID const &,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProvider>)
0x1800104ae  mov     rdi, rax
0x1800104b1  mov     [rbp+57h+var_B8], rax
0x1800104b5  mov     rcx, [rbp+57h+var_88]; this
0x1800104b9  test    rcx, rcx
0x1800104bc  jz      short loc_1800104C3
0x1800104be  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800104c3  xorps   xmm0, xmm0
0x1800104c6  movdqu  xmmword ptr [rbp+57h+var_C8], xmm0
0x1800104cb  mov     ebx, 1
0x1800104d0  test    rdi, rdi
0x1800104d3  jz      short loc_180010507
0x1800104d5  lea     ecx, [rbx+17h]; Size
0x1800104d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800104dd  mov     [rbp+57h+var_98], rax
0x1800104e1  xorps   xmm0, xmm0
0x1800104e4  movups  xmmword ptr [rax], xmm0
0x1800104e7  mov     [rax+8], ebx
0x1800104ea  mov     [rax+0Ch], ebx
0x1800104ed  lea     rcx, ??_7?$_Ref_count_resource@PEAVThreadProcessorProviderToken@ThreadProcessorProvider@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@VThreadProcessorProviderToken@ThreadProcessorProvider@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@6B@; const std::_Ref_count_resource<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProvider::ThreadProcessorProviderToken *,std::default_delete<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProvider::ThreadProcessorProviderToken>>::`vftable'
0x1800104f4  mov     [rax], rcx
0x1800104f7  mov     [rax+10h], rdi
0x1800104fb  mov     [rbp+57h+var_C8], rdi
0x1800104ff  mov     [rbp+57h+var_C8+8], rax
0x180010503  mov     [rbp+57h+var_B8], r13
0x180010507  lea     r8, [rbp+57h+var_C8]
0x18001050b  mov     edx, [rbp+57h+var_D0]
0x18001050e  lea     rcx, [rbp+57h+var_B0]
0x180010512  call    ?MakeAutoStop@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@SA?AV?$unique_ptr@VThreadProcessorControlAutoStop@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@VThreadProcessorControlAutoStop@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@W4ThreadProcessorTag@345@V?$shared_ptr@VThreadProcessorProviderToken@ThreadProcessorProvider@Details@Foundation@Bluetooth@Microsoft@@@7@@Z; Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::MakeAutoStop(Microsoft::Bluetooth::Foundation::ThreadProcessorTag,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProvider::ThreadProcessorProviderToken>)
0x180010517  nop
0x180010518  mov     rdx, [rbp+57h+var_B0]
0x18001051c  add     rdx, 8
0x180010520  lea     rcx, [rbp+57h+var_C8]
0x180010524  call    ??0?$shared_ptr@VThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl> const &)
0x180010529  nop
0x18001052a  movups  xmm6, [rbp+57h+var_60]
0x18001052e  movups  [rbp+57h+var_80], xmm6
0x180010532  mov     r12, [rbp+57h+var_C8]
0x180010536  mov     [rbp+57h+var_70], r12
0x18001053a  mov     rdi, [rbp+57h+var_C8+8]
0x18001053e  mov     [rbp+57h+var_68], rdi
0x180010542  xorps   xmm0, xmm0
0x180010545  movdqu  xmmword ptr [rbp+57h+var_C8], xmm0
0x18001054a  lea     r8, [rbp+57h+var_D0]
0x18001054e  lea     rdx, [rbp+57h+var_90]
0x180010552  mov     rcx, rsi
0x180010555  call    ??$_Try_emplace@AEBW4ThreadProcessorTag@Foundation@Bluetooth@Microsoft@@$$V@?$map@W4ThreadProcessorTag@Foundation@Bluetooth@Microsoft@@U?$pair@U_GUID@@V?$weak_ptr@VThreadProcessorControl@Foundation@Bluetooth@Microsoft@@@std@@@std@@U?$less@W4ThreadProcessorTag@Foundation@Bluetooth@Microsoft@@@6@V?$allocator@U?$pair@$$CBW4ThreadProcessorTag@Foundation@Bluetooth@Microsoft@@U?$pair@U_GUID@@V?$weak_ptr@VThreadProcessorControl@Foundation@Bluetooth@Microsoft@@@std@@@std@@@std@@@6@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4ThreadProcessorTag@Foundation@Bluetooth@Microsoft@@U?$pair@U_GUID@@V?$weak_ptr@VThreadProcessorControl@Foundation@Bluetooth@Microsoft@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBW4ThreadProcessorTag@Foundation@Bluetooth@Microsoft@@@Z; std::map<Microsoft::Bluetooth::Foundation::ThreadProcessorTag,std::pair<_GUID,std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadProcessorControl>>>::_Try_emplace<Microsoft::Bluetooth::Foundation::ThreadProcessorTag const &,>(Microsoft::Bluetooth::Foundation::ThreadProcessorTag const &)
0x18001055a  mov     rcx, [rax]
0x18001055d  movdqu  xmmword ptr [rcx+28h], xmm6
0x180010562  mov     rax, rdi
0x180010565  mov     rsi, rdi
0x180010568  test    rdi, rdi
0x18001056b  jz      short loc_180010573
0x18001056d  lock add [rdi+0Ch], ebx
0x180010571  jmp     short loc_180010579
0x180010573  mov     r12, r13
0x180010576  mov     rdi, r13
0x180010579  mov     [rcx+38h], r12
0x18001057d  mov     rdx, [rcx+40h]
0x180010581  mov     [rcx+40h], rdi
0x180010585  test    rdx, rdx
0x180010588  jz      short loc_180010594
0x18001058a  mov     rcx, rdx; this
0x18001058d  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180010592  jmp     short loc_180010597
0x180010594  mov     rsi, rax
0x180010597  test    rsi, rsi
0x18001059a  jz      short loc_1800105A5
0x18001059c  mov     rcx, rsi; this
0x18001059f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800105a4  nop
0x1800105a5  lea     rdx, WPP_GLOBAL_Control
0x1800105ac  mov     rax, cs:WPP_GLOBAL_Control
0x1800105b3  cmp     rax, rdx
0x1800105b6  jz      short loc_1800105C6
0x1800105b8  test    [rax+1Ch], bl
0x1800105bb  jz      short loc_1800105C6
0x1800105bd  cmp     byte ptr [rax+19h], 5
0x1800105c1  mov     r10b, bl
0x1800105c4  jnb     short loc_1800105C9
0x1800105c6  mov     r10b, r13b
0x1800105c9  lea     rdx, WPP_RECORDER_INITIALIZED
0x1800105d0  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1800105d7  jz      short loc_1800105E0
0x1800105d9  cmp     [rax+30h], r13w
0x1800105de  jnz     short loc_1800105E3
0x1800105e0  mov     bl, r13b
0x1800105e3  test    r10b, r10b
0x1800105e6  jnz     short loc_1800105EC
0x1800105e8  test    bl, bl
0x1800105ea  jz      short loc_180010640
0x1800105ec  mov     r8, [r15+50h]
0x1800105f0  mov     rdx, [rbp+57h+var_B0]
0x1800105f4  add     rdx, 8
0x1800105f8  lea     rcx, [rbp+57h+var_C8]
0x1800105fc  call    ??0?$shared_ptr@VThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl> const &)
0x180010601  mov     [rsp+130h+var_E0], r8
0x180010606  lea     rax, [rbp+57h+var_60]
0x18001060a  mov     [rsp+130h+var_E8], rax
0x18001060f  mov     rax, [rbp+57h+var_C8]
0x180010613  mov     [rsp+130h+var_F0], rax
0x180010618  mov     rcx, cs:WPP_GLOBAL_Control
0x18001061f  mov     r9, [rcx+28h]
0x180010623  mov     r8b, bl
0x180010626  mov     dl, r10b
0x180010629  mov     rcx, [rcx+10h]
0x18001062d  call    WPP_RECORDER_AND_TRACE_SF_q_guid_I
0x180010632  mov     rcx, [rbp+57h+var_C8+8]; this
0x180010636  test    rcx, rcx
0x180010639  jz      short loc_180010640
0x18001063b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010640  mov     rcx, [rbp+57h+var_B0]
0x180010644  mov     [rbp+57h+var_B0], r13
0x180010648  mov     [r14], rcx
0x18001064b  lea     rcx, [rbp+57h+var_B0]
0x18001064f  call    ??1?$unique_ptr@VThreadProcessorControlAutoStop@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@VThreadProcessorControlAutoStop@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorControlAutoStop>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorControlAutoStop>(void)
0x180010654  nop
0x180010655  lea     rcx, [rbp+57h+var_B8]
0x180010659  call    ??1?$unique_ptr@VEventRegistration@EventNotifier@Foundation@Bluetooth@Microsoft@@U?$default_delete@VEventRegistration@EventNotifier@Foundation@Bluetooth@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Bluetooth::Foundation::EventNotifier::EventRegistration>::~unique_ptr<Microsoft::Bluetooth::Foundation::EventNotifier::EventRegistration>(void)
0x18001065e  nop
0x18001065f  lea     rcx, [rbp+57h+var_A8]
0x180010663  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180010668  mov     rax, r14
0x18001066b  mov     rcx, [rbp+57h+var_50]
0x18001066f  xor     rcx, rsp; StackCookie
0x180010672  call    __security_check_cookie
0x180010677  lea     r11, [rsp+130h+var_30]
0x18001067f  mov     rbx, [r11+58h]
0x180010683  movaps  xmm6, xmmword ptr [r11-10h]
0x180010688  mov     rsp, r11
0x18001068b  pop     r15
0x18001068d  pop     r14
0x18001068f  pop     r13
0x180010691  pop     r12
0x180010693  pop     rdi
0x180010694  pop     rsi
0x180010695  pop     rbp
0x180010696  retn
```
