# _anonymous_namespace_::I_s_NgcIsoGetIncrementedEphemeralCounter

- ea: `0x140026d20`
- end: `0x1400270ed`
- name: `_anonymous_namespace_::I_s_NgcIsoGetIncrementedEphemeralCounter`
- size: `973`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140009be0`
- `0x140009fa0`
- `0x14000ac7c`
- `0x14000b3a0`
- `0x14000cbe4`
- `0x14000d490`
- `0x14000e034`
- `0x14000f6a0`
- `0x14000f914`
- `0x14000fabc`
- `0x14000fb24`
- `0x1400104fc`
- `0x140015fa8`
- `0x140016eb8`
- `0x140017adc`
- `0x1400188c4`
- `0x14001b5fc`
- `0x14001cec0`
- `0x14001dc88`
- `0x14001e3d0`
- `0x14001e944`
- `0x1400204e4`
- `0x140026d20`
- `0x14002d05c`
- `0x140039058`
- `0x14003d360`
- `0x140071010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140026e69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140026e69`
- `bcrypt!BCryptGenRandom` at `0x140026eb3`
- `bcrypt!BCryptGenRandom` at `0x140026eb3`

## string_xrefs

- `0x140026de2`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140026ec9`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140026f9d`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140027028`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall anonymous_namespace_::I_s_NgcIsoGetIncrementedEphemeralCounter(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        _DWORD *a5,
        _QWORD *a6)
{
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rax
  NTSTATUS v12; // eax
  __int64 v13; // rbx
  __int64 v14; // rbx
  void *v15; // rdi
  int v16; // eax
  size_t v17; // rbx
  void *v18; // rax
  void *v19; // rsi
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  RTL_SRWLOCK *v22; // [rsp+38h] [rbp-C8h] BYREF
  UCHAR pbBuffer[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v24[3]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v26; // [rsp+68h] [rbp-98h]
  void *Src; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h]
  _BYTE v29[24]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v30[4]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v31[112]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v32[112]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v33; // [rsp+1A0h] [rbp+A0h]
  __int64 v34; // [rsp+1A8h] [rbp+A8h]
  _QWORD v35[42]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v35);
  v35[0] = &LogProvider::NgcIsoGetIncrementedEphemeralCounter::`vftable';
  LogProvider::NgcIsoGetIncrementedEphemeralCounter::StartActivity((LogProvider::NgcIsoGetIncrementedEphemeralCounter *)v35);
  std::shared_ptr<NgcIsoContainerImpl>::shared_ptr<NgcIsoContainerImpl>(&v25, a2);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v29);
  LOBYTE(v21) = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v25 + 32LL))(v25, a3, a4, v29);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x569,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)(unsigned int)v9,
      (int)&v21);
    goto LABEL_10;
  }
  Properties::FromCbor<Properties::TpmKeyMaterial>(v31, v29);
  if ( dword_14009DD1C > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_14009DD1C);
    if ( dword_14009DD1C == -1 )
    {
      std::map<std::vector<unsigned char>,unsigned __int64>::map<std::vector<unsigned char>,unsigned __int64>(&qword_14009DD20);
      atexit(_anonymous_namespace_::I_s_NgcIsoGetIncrementedEphemeralCounter_::_2_::_dynamic_atexit_destructor_for__ephemeralCountersMap__);
      Init_thread_footer(&dword_14009DD1C);
    }
  }
  AcquireSRWLockExclusive(&stru_14009D890);
  v22 = &stru_14009D890;
  std::_Tree<std::_Tmap_traits<std::vector<unsigned char>,unsigned __int64,std::less<std::vector<unsigned char>>,std::allocator<std::pair<std::vector<unsigned char> const,unsigned __int64>>,0>>::find(
    &qword_14009DD20,
    v24,
    v32);
  v11 = v24[0];
  if ( (void *)v24[0] == qword_14009DD20 )
  {
    *(_QWORD *)pbBuffer = 0;
    v12 = BCryptGenRandom(0, pbBuffer, 8u, 2u);
    v10 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x578,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
        (const char *)(unsigned int)v12,
        (int)&v21);
LABEL_9:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
      Properties::TpmKeyMaterial::~TpmKeyMaterial((Properties::TpmKeyMaterial *)v31);
LABEL_10:
      std::vector<unsigned char>::_Tidy(v29);
      if ( v26 )
        std::_Ref_count_base::_Decref(v26);
      goto LABEL_25;
    }
    v13 = *(_QWORD *)pbBuffer;
    *(_QWORD *)(*(_QWORD *)std::map<std::vector<unsigned char>,unsigned __int64>::_Try_emplace<std::vector<unsigned char> const &,>(
                             &qword_14009DD20,
                             v24,
                             v32)
              + 56LL) = v13;
    v14 = *(_QWORD *)pbBuffer;
  }
  else
  {
    ++*(_QWORD *)(v24[0] + 56LL);
    v14 = *(_QWORD *)(v11 + 56);
  }
  std::vector<unsigned char>::vector<unsigned char>(&Src, 8);
  if ( v33 == v34 )
  {
    v15 = Src;
    *(_QWORD *)Src = v14;
  }
  else
  {
    std::vector<unsigned char>::vector<unsigned char>(v30, 8);
    *(_QWORD *)v30[0] = v14;
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v24);
    v16 = ClientAuth::EncryptData();
    v10 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58B,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
        (const char *)(unsigned int)v16,
        (int)&v21);
      std::vector<unsigned char>::_Tidy(v24);
      std::vector<unsigned char>::_Tidy(v30);
LABEL_18:
      std::vector<unsigned char>::_Tidy(&Src);
      goto LABEL_9;
    }
    std::vector<unsigned char>::operator=(&Src, v24);
    std::vector<unsigned char>::_Tidy(v24);
    std::vector<unsigned char>::_Tidy(v30);
    v15 = Src;
  }
  v17 = v28 - (_QWORD)v15;
  v18 = MIDL_user_allocate(v28 - (_QWORD)v15);
  v19 = v18;
  v24[0] = v18;
  if ( !v18 )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x590,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)0x8007000ELL,
      (int)&v21);
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(v24);
    goto LABEL_18;
  }
  memcpy_0(v18, v15, v17);
  v24[0] = 0;
  *a6 = v19;
  *a5 = v17;
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v35, 0);
  std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(v24);
  std::vector<unsigned char>::_Tidy(&Src);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
  Properties::TpmKeyMaterial::~TpmKeyMaterial((Properties::TpmKeyMaterial *)v31);
  std::vector<unsigned char>::_Tidy(v29);
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  v10 = 0;
LABEL_25:
  LogProvider::NgcIsoGetIncrementedEphemeralCounter::~NgcIsoGetIncrementedEphemeralCounter((LogProvider::NgcIsoGetIncrementedEphemeralCounter *)v35);
  return v10;
}

```

## disassembly

```asm
0x140026d20  mov     [rsp-8+arg_0], rbx
0x140026d25  push    rbp
0x140026d26  push    rsi
0x140026d27  push    rdi
0x140026d28  push    r14
0x140026d2a  push    r15
0x140026d2c  lea     rbp, [rsp-280h]
0x140026d34  sub     rsp, 380h
0x140026d3b  mov     rax, cs:__security_cookie
0x140026d42  xor     rax, rsp
0x140026d45  mov     [rbp+2A0h+var_30], rax
0x140026d4c  mov     rsi, r9
0x140026d4f  mov     edi, r8d
0x140026d52  mov     rbx, rdx
0x140026d55  mov     r14, [rbp+2A0h+arg_20]
0x140026d5c  mov     r15, [rbp+2A0h+arg_28]
0x140026d63  lea     rdx, aNgcisogetincre; "NgcIsoGetIncrementedEphemeralCounter"
0x140026d6a  lea     rcx, [rbp+2A0h+var_180]; struct wil::details::IFailureCallback *
0x140026d71  call    ??0?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140026d76  lea     rax, ??_7NgcIsoGetIncrementedEphemeralCounter@LogProvider@@6B@; const LogProvider::NgcIsoGetIncrementedEphemeralCounter::`vftable'
0x140026d7d  mov     [rbp+2A0h+var_180], rax
0x140026d84  lea     rcx, [rbp+2A0h+var_180]; this
0x140026d8b  call    ?StartActivity@NgcIsoGetIncrementedEphemeralCounter@LogProvider@@QEAAXXZ; LogProvider::NgcIsoGetIncrementedEphemeralCounter::StartActivity(void)
0x140026d90  nop
0x140026d91  mov     rdx, rbx
0x140026d94  lea     rcx, [rsp+3A0h+var_340]
0x140026d99  call    ??0?$shared_ptr@VNgcIsoContainerImpl@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NgcIsoContainerImpl>::shared_ptr<NgcIsoContainerImpl>(std::shared_ptr<NgcIsoContainerImpl> const &)
0x140026d9e  nop
0x140026d9f  lea     rcx, [rbp+2A0h+var_318]
0x140026da3  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140026da8  nop
0x140026da9  mov     byte ptr [rsp+3A0h+var_370], 0
0x140026dae  mov     rcx, [rsp+3A0h+var_340]
0x140026db3  mov     rax, [rcx]
0x140026db6  lea     rdx, [rsp+3A0h+var_370]
0x140026dbb  mov     qword ptr [rsp+3A0h+var_380], rdx; int
0x140026dc0  lea     r9, [rbp+2A0h+var_318]
0x140026dc4  mov     r8, rsi
0x140026dc7  mov     edx, edi
0x140026dc9  mov     rax, [rax+20h]
0x140026dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026dd2  mov     ebx, eax
0x140026dd4  test    eax, eax
0x140026dd6  jns     short loc_140026DF8
0x140026dd8  mov     rcx, [rbp+2A8h]; this
0x140026ddf  mov     r9d, eax; char *
0x140026de2  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140026de9  mov     edx, 569h; void *
0x140026dee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026df3  jmp     loc_140026EF0
0x140026df8  lea     rdx, [rbp+2A0h+var_318]
0x140026dfc  lea     rcx, [rbp+2A0h+var_2E0]
0x140026e00  call    ??$FromCbor@UTpmKeyMaterial@Properties@@@Properties@@YA?AUTpmKeyMaterial@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Properties::FromCbor<Properties::TpmKeyMaterial>(std::vector<uchar> const &)
0x140026e05  nop
0x140026e06  mov     ecx, 4
0x140026e0b  mov     rax, gs:58h
0x140026e14  mov     rax, [rax]
0x140026e17  lea     rsi, qword_14009DD20
0x140026e1e  mov     eax, [rcx+rax]
0x140026e21  cmp     cs:dword_14009DD1C, eax
0x140026e27  jle     short loc_140026E5F
0x140026e29  lea     rcx, dword_14009DD1C
0x140026e30  call    _Init_thread_header
0x140026e35  cmp     cs:dword_14009DD1C, 0FFFFFFFFh
0x140026e3c  jnz     short loc_140026E5F
0x140026e3e  mov     rcx, rsi
0x140026e41  call    ??0?$map@V?$vector@EV?$allocator@E@std@@@std@@_KU?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@_K@std@@@2@@std@@QEAA@XZ; std::map<std::vector<uchar>,unsigned __int64>::map<std::vector<uchar>,unsigned __int64>(void)
0x140026e46  lea     rcx, __anonymous_namespace___I_s_NgcIsoGetIncrementedEphemeralCounter____2____dynamic_atexit_destructor_for__ephemeralCountersMap__; void (__cdecl *)()
0x140026e4d  call    atexit
0x140026e52  nop
0x140026e53  lea     rcx, dword_14009DD1C
0x140026e5a  call    _Init_thread_footer
0x140026e5f  lea     rbx, stru_14009D890
0x140026e66  mov     rcx, rbx; SRWLock
0x140026e69  call    cs:__imp_AcquireSRWLockExclusive
0x140026e6f  mov     [rsp+3A0h+var_368], rbx
0x140026e74  lea     r8, [rbp+2A0h+var_270]
0x140026e78  lea     rdx, [rsp+3A0h+var_358]
0x140026e7d  mov     rcx, rsi
0x140026e80  call    ?find@?$_Tree@V?$_Tmap_traits@V?$vector@EV?$allocator@E@std@@@std@@_KU?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@_K@std@@@std@@@std@@@2@AEBV?$vector@EV?$allocator@E@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::vector<uchar>,unsigned __int64,std::less<std::vector<uchar>>,std::allocator<std::pair<std::vector<uchar> const,unsigned __int64>>,0>>::find(std::vector<uchar> const &)
0x140026e85  mov     edi, 8
0x140026e8a  mov     rax, [rsp+3A0h+var_358]
0x140026e8f  cmp     rax, cs:qword_14009DD20
0x140026e96  jnz     loc_140026F36
0x140026e9c  mov     qword ptr [rsp+3A0h+pbBuffer], 0
0x140026ea5  lea     r9d, [rdi-6]; dwFlags
0x140026ea9  mov     r8d, edi; cbBuffer
0x140026eac  lea     rdx, [rsp+3A0h+pbBuffer]; pbBuffer
0x140026eb1  xor     ecx, ecx; hAlgorithm
0x140026eb3  call    cs:__imp_BCryptGenRandom
0x140026eb9  mov     ebx, eax
0x140026ebb  test    eax, eax
0x140026ebd  jns     short loc_140026F12
0x140026ebf  mov     rcx, [rbp+2A8h]; this
0x140026ec6  mov     r9d, eax; char *
0x140026ec9  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140026ed0  mov     edx, 578h; void *
0x140026ed5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026eda  nop
0x140026edb  lea     rcx, [rsp+3A0h+var_368]
0x140026ee0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140026ee5  nop
0x140026ee6  lea     rcx, [rbp+2A0h+var_2E0]; this
0x140026eea  call    ??1TpmKeyMaterial@Properties@@UEAA@XZ; Properties::TpmKeyMaterial::~TpmKeyMaterial(void)
0x140026eef  nop
0x140026ef0  lea     rcx, [rbp+2A0h+var_318]
0x140026ef4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140026ef9  nop
0x140026efa  mov     rcx, [rsp+3A0h+var_338]; this
0x140026eff  test    rcx, rcx
0x140026f02  jz      loc_1400270B9
0x140026f08  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140026f0d  jmp     loc_1400270B9
0x140026f12  mov     rbx, qword ptr [rsp+3A0h+pbBuffer]
0x140026f17  lea     r8, [rbp+2A0h+var_270]
0x140026f1b  lea     rdx, [rsp+3A0h+var_358]
0x140026f20  mov     rcx, rsi
0x140026f23  call    ??$_Try_emplace@AEBV?$vector@EV?$allocator@E@std@@@std@@$$V@?$map@V?$vector@EV?$allocator@E@std@@@std@@_KU?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@_K@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@_K@std@@PEAX@std@@_N@1@AEBV?$vector@EV?$allocator@E@std@@@1@@Z; std::map<std::vector<uchar>,unsigned __int64>::_Try_emplace<std::vector<uchar> const &,>(std::vector<uchar> const &)
0x140026f28  mov     rcx, [rax]
0x140026f2b  mov     [rcx+38h], rbx
0x140026f2f  mov     rbx, qword ptr [rsp+3A0h+pbBuffer]
0x140026f34  jmp     short loc_140026F3E
0x140026f36  inc     qword ptr [rax+38h]
0x140026f3a  mov     rbx, [rax+38h]
0x140026f3e  mov     rdx, rdi
0x140026f41  lea     rcx, [rsp+3A0h+Src]
0x140026f46  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x140026f4b  nop
0x140026f4c  mov     rax, [rbp+2A0h+var_1F8]
0x140026f53  cmp     [rbp+2A0h+var_200], rax
0x140026f5a  jnz     short loc_140026F69
0x140026f5c  mov     rdi, [rsp+3A0h+Src]
0x140026f61  mov     [rdi], rbx
0x140026f64  jmp     loc_140026FFC
0x140026f69  mov     rdx, rdi
0x140026f6c  lea     rcx, [rbp+2A0h+var_300]
0x140026f70  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x140026f75  nop
0x140026f76  mov     rax, [rbp+2A0h+var_300]
0x140026f7a  mov     [rax], rbx
0x140026f7d  lea     rcx, [rsp+3A0h+var_358]
0x140026f82  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140026f87  nop
0x140026f88  call    ?EncryptData@ClientAuth@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@0AEAV23@@Z; ClientAuth::EncryptData(std::vector<uchar> const &,std::vector<uchar> const &,std::vector<uchar> &)
0x140026f8d  mov     ebx, eax
0x140026f8f  test    eax, eax
0x140026f91  jns     short loc_140026FD3
0x140026f93  mov     rcx, [rbp+2A8h]; this
0x140026f9a  mov     r9d, eax; char *
0x140026f9d  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140026fa4  mov     edx, 58Bh; void *
0x140026fa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026fae  nop
0x140026faf  lea     rcx, [rsp+3A0h+var_358]
0x140026fb4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140026fb9  nop
0x140026fba  lea     rcx, [rbp+2A0h+var_300]
0x140026fbe  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140026fc3  nop
0x140026fc4  lea     rcx, [rsp+3A0h+Src]
0x140026fc9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140026fce  jmp     loc_140026EDB
0x140026fd3  lea     rdx, [rsp+3A0h+var_358]
0x140026fd8  lea     rcx, [rsp+3A0h+Src]
0x140026fdd  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140026fe2  nop
0x140026fe3  lea     rcx, [rsp+3A0h+var_358]
0x140026fe8  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140026fed  nop
0x140026fee  lea     rcx, [rbp+2A0h+var_300]
0x140026ff2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140026ff7  mov     rdi, [rsp+3A0h+Src]
0x140026ffc  mov     rbx, [rsp+3A0h+var_328]
0x140027001  sub     rbx, rdi
0x140027004  mov     rcx, rbx; size
0x140027007  call    MIDL_user_allocate
0x14002700c  mov     rsi, rax
0x14002700f  mov     [rsp+3A0h+var_358], rax
0x140027014  test    rax, rax
0x140027017  jnz     short loc_140027048
0x140027019  mov     rcx, [rbp+2A8h]; this
0x140027020  mov     ebx, 8007000Eh
0x140027025  mov     r9d, ebx; char *
0x140027028  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14002702f  mov     edx, 590h; void *
0x140027034  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140027039  lea     rcx, [rsp+3A0h+var_358]
0x14002703e  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x140027043  jmp     loc_140026FC4
0x140027048  mov     r8, rbx; Size
0x14002704b  mov     rdx, rdi; Src
0x14002704e  mov     rcx, rsi; void *
0x140027051  call    memcpy_0
0x140027056  mov     [rsp+3A0h+var_358], 0
0x14002705f  mov     [r15], rsi
0x140027062  mov     [r14], ebx
0x140027065  xor     edx, edx
0x140027067  lea     rcx, [rbp+2A0h+var_180]
0x14002706e  call    ?Stop@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140027073  lea     rcx, [rsp+3A0h+var_358]
0x140027078  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x14002707d  nop
0x14002707e  lea     rcx, [rsp+3A0h+Src]
0x140027083  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140027088  nop
0x140027089  lea     rcx, [rsp+3A0h+var_368]
0x14002708e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140027093  nop
0x140027094  lea     rcx, [rbp+2A0h+var_2E0]; this
0x140027098  call    ??1TpmKeyMaterial@Properties@@UEAA@XZ; Properties::TpmKeyMaterial::~TpmKeyMaterial(void)
0x14002709d  nop
0x14002709e  lea     rcx, [rbp+2A0h+var_318]
0x1400270a2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400270a7  nop
0x1400270a8  mov     rcx, [rsp+3A0h+var_338]; this
0x1400270ad  test    rcx, rcx
0x1400270b0  jz      short loc_1400270B7
0x1400270b2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400270b7  xor     ebx, ebx
0x1400270b9  lea     rcx, [rbp+2A0h+var_180]; this
0x1400270c0  call    ??1NgcIsoGetIncrementedEphemeralCounter@LogProvider@@QEAA@XZ; LogProvider::NgcIsoGetIncrementedEphemeralCounter::~NgcIsoGetIncrementedEphemeralCounter(void)
0x1400270c5  mov     eax, ebx
0x1400270c7  mov     rcx, [rbp+2A0h+var_30]
0x1400270ce  xor     rcx, rsp; StackCookie
0x1400270d1  call    __security_check_cookie
0x1400270d6  mov     rbx, [rsp+3A0h+arg_0]
0x1400270de  add     rsp, 380h
0x1400270e5  pop     r15
0x1400270e7  pop     r14
0x1400270e9  pop     rdi
0x1400270ea  pop     rsi
0x1400270eb  pop     rbp
0x1400270ec  retn
```
