# Microsoft::WRL::Details::Make<WpnConnectionManager,Wns::ConnectionMultiplexer * &>(Wns::ConnectionMultiplexer * &)

- ea: `0x1800074f0`
- end: `0x18000772c`
- name: `??$Make@VWpnConnectionManager@@AEAPEAVConnectionMultiplexer@Wns@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWpnConnectionManager@@@12@AEAPEAVConnectionMultiplexer@Wns@@@Z`
- size: `572`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016c40`

## callees

- `0x1800074f0`
- `0x180007d60`
- `0x180008ba0`
- `0x18000a2a0`
- `0x18000c410`
- `0x18000cec8`
- `0x18000cee0`
- `0x180021048`
- `0x180026200`
- `0x18002660c`
- `0x180026654`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800075d4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800075d4`

## string_xrefs

- `0x1800075ed`: `WnsCMCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Microsoft::WRL::Details::Make<WpnConnectionManager,Wns::ConnectionMultiplexer * &>(_QWORD *a1)
{
  char *v2; // rax
  char *v3; // rbx
  Wns::ConnectionMultiplexer *v4; // rsi
  Wns *v5; // rcx
  void **v7; // [rsp+50h] [rbp-B0h] BYREF
  int v8; // [rsp+58h] [rbp-A8h] BYREF
  char v9; // [rsp+5Ch] [rbp-A4h]
  int v10; // [rsp+80h] [rbp-80h] BYREF
  const char *v11; // [rsp+88h] [rbp-78h]
  __int64 v12; // [rsp+90h] [rbp-70h]
  char v13; // [rsp+98h] [rbp-68h]
  int v14; // [rsp+A0h] [rbp-60h]
  __int128 v15; // [rsp+A8h] [rbp-58h]
  __int128 v16; // [rsp+B8h] [rbp-48h]
  __int128 v17; // [rsp+C8h] [rbp-38h]
  __int128 v18; // [rsp+D8h] [rbp-28h]
  __int128 v19; // [rsp+E8h] [rbp-18h]
  __int128 v20; // [rsp+F8h] [rbp-8h]
  __int128 v21; // [rsp+108h] [rbp+8h]
  __int128 v22; // [rsp+118h] [rbp+18h]
  __int128 v23; // [rsp+128h] [rbp+28h]
  __int64 v24; // [rsp+138h] [rbp+38h]
  __int128 v25; // [rsp+140h] [rbp+40h]
  int v26; // [rsp+150h] [rbp+50h]
  __int64 v27; // [rsp+158h] [rbp+58h]
  int *v28; // [rsp+160h] [rbp+60h]
  __int64 v29; // [rsp+168h] [rbp+68h]
  __int64 v30; // [rsp+170h] [rbp+70h]
  void ***v31; // [rsp+178h] [rbp+78h]
  __int64 v32; // [rsp+180h] [rbp+80h]
  int v33; // [rsp+188h] [rbp+88h]
  int *v34; // [rsp+190h] [rbp+90h]
  char v35; // [rsp+198h] [rbp+98h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  *a1 = 0;
  v2 = (char *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( v2 )
  {
    v4 = ConnectionManagerFactoryPrivate::s_theMux;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IConnectionManagerPrivate,IConnectionManagerPrivate2>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IConnectionManagerPrivate,IConnectionManagerPrivate2>(v2);
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IConnectionManagerPrivate,IConnectionManagerPrivate2>::`vftable'{for `IConnectionManagerPrivate'};
    *((_QWORD *)v3 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IConnectionManagerPrivate,IConnectionManagerPrivate2>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IConnectionManagerPrivate2>'};
    v5 = Microsoft::WRL::Details::ModuleBase::module_;
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = &WpnConnectionManager::`vftable'{for `IConnectionManagerPrivate'};
    *((_QWORD *)v3 + 1) = &WpnConnectionManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IConnectionManagerPrivate2>'};
    *((_QWORD *)v3 + 3) = v4;
    *((_QWORD *)v3 + 4) = Wns::GetUserIdForCaller(v5);
    *((_DWORD *)v3 + 10) = 0;
    *((_QWORD *)v3 + 6) = 0;
    *((_QWORD *)v3 + 7) = 0;
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v3 + 64), 0, 0);
    v8 = 0;
    v9 = 0;
    v13 = 0;
    v10 = 0;
    v11 = "WnsCMCreate";
    v12 = 0;
    v14 = 0;
    v25 = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v26 = 1;
    v27 = 0;
    v28 = &v8;
    v29 = 0;
    v30 = 0;
    v31 = &v7;
    v32 = 0;
    v33 = 0;
    v34 = &v10;
    v35 = 0;
    v7 = &WnsCPLog::WnsCMCreate::`vftable';
    WnsCPLog::WnsCMCreate::StartActivity((WnsCPLog::WnsCMCreate *)&v7, *((_QWORD *)v3 + 4));
    if ( !v4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\wpnconnectionmanager.cpp",
        (const char *)0x80070057LL,
        1);
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v7, 0);
    v7 = &WnsCPLog::WnsCMCreate::`vftable';
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v7);
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v7);
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v3;
    v3 = 0;
  }
  if ( v3 )
    operator delete(v3);
  return a1;
}

```

## disassembly

```asm
0x1800074f0  push    rbp
0x1800074f2  push    rbx
0x1800074f3  push    rsi
0x1800074f4  push    rdi
0x1800074f5  push    r14
0x1800074f7  push    r15
0x1800074f9  lea     rbp, [rsp-0B8h]
0x180007501  sub     rsp, 1B8h
0x180007508  mov     rax, cs:__security_cookie
0x18000750f  xor     rax, rsp
0x180007512  mov     [rbp+0E0h+var_40], rax
0x180007519  mov     rdi, rcx
0x18000751c  mov     [rsp+1E0h+var_1B8], rcx
0x180007521  xor     r14d, r14d
0x180007524  mov     [rsp+1E0h+var_1C0], r14d
0x180007529  mov     [rcx], r14
0x18000752c  mov     [rsp+1E0h+var_1C0], 1; int
0x180007534  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000753b  mov     ecx, 68h ; 'h'; unsigned __int64
0x180007540  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007545  mov     rbx, rax
0x180007548  mov     [rsp+1E0h+var_1B0], rax
0x18000754d  mov     [rsp+1E0h+var_1A8], rax
0x180007552  test    rax, rax
0x180007555  jz      loc_1800076D6
0x18000755b  mov     [rsp+1E0h+var_1A0], rax
0x180007560  mov     rsi, cs:?s_theMux@ConnectionManagerFactoryPrivate@@0PEAVConnectionMultiplexer@Wns@@EA; Wns::ConnectionMultiplexer * ConnectionManagerFactoryPrivate::s_theMux
0x180007567  mov     rcx, rax
0x18000756a  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIConnectionManagerPrivate@@UIConnectionManagerPrivate2@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IConnectionManagerPrivate,IConnectionManagerPrivate2>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IConnectionManagerPrivate,IConnectionManagerPrivate2>(void)
0x18000756f  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIConnectionManagerPrivate@@UIConnectionManagerPrivate2@@@WRL@Microsoft@@6BIConnectionManagerPrivate@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IConnectionManagerPrivate,IConnectionManagerPrivate2>::`vftable'{for `IConnectionManagerPrivate'}
0x180007576  mov     [rbx], rcx
0x180007579  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIConnectionManagerPrivate@@UIConnectionManagerPrivate2@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIConnectionManagerPrivate2@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IConnectionManagerPrivate,IConnectionManagerPrivate2>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IConnectionManagerPrivate2>'}
0x180007580  mov     [rbx+8], rax
0x180007584  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000758b  test    rcx, rcx
0x18000758e  jz      short loc_18000759D
0x180007590  mov     rax, [rcx]
0x180007593  mov     rax, [rax+8]
0x180007597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000759c  nop
0x18000759d  lea     rax, ??_7WpnConnectionManager@@6BIConnectionManagerPrivate@@@; const WpnConnectionManager::`vftable'{for `IConnectionManagerPrivate'}
0x1800075a4  mov     [rbx], rax
0x1800075a7  lea     rax, ??_7WpnConnectionManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIConnectionManagerPrivate2@@@Details@WRL@Microsoft@@@; const WpnConnectionManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IConnectionManagerPrivate2>'}
0x1800075ae  mov     [rbx+8], rax
0x1800075b2  mov     [rbx+18h], rsi
0x1800075b6  call    ?GetUserIdForCaller@Wns@@YA_KXZ; Wns::GetUserIdForCaller(void)
0x1800075bb  mov     [rbx+20h], rax
0x1800075bf  mov     [rbx+28h], r14d
0x1800075c3  mov     [rbx+30h], r14
0x1800075c7  mov     [rbx+38h], r14
0x1800075cb  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800075cf  xor     r8d, r8d; Flags
0x1800075d2  xor     edx, edx; dwSpinCount
0x1800075d4  call    cs:__imp_InitializeCriticalSectionEx
0x1800075da  nop
0x1800075db  mov     [rsp+1E0h+var_188], r14d
0x1800075e0  mov     [rsp+1E0h+var_184], 0
0x1800075e5  mov     [rbp+0E0h+var_148], 0
0x1800075e9  mov     [rbp+0E0h+var_160], r14d
0x1800075ed  lea     rax, aWnscmcreate; "WnsCMCreate"
0x1800075f4  mov     [rbp+0E0h+var_158], rax
0x1800075f8  mov     [rbp+0E0h+var_150], r14
0x1800075fc  mov     [rbp+0E0h+var_140], r14d
0x180007600  xorps   xmm0, xmm0
0x180007603  movdqa  [rbp+0E0h+var_A0], xmm0
0x180007608  xorps   xmm1, xmm1
0x18000760b  xor     eax, eax
0x18000760d  movups  [rbp+0E0h+var_138], xmm1
0x180007611  movups  [rbp+0E0h+var_128], xmm1
0x180007615  movups  [rbp+0E0h+var_118], xmm1
0x180007619  movups  [rbp+0E0h+var_108], xmm1
0x18000761d  movups  [rbp+0E0h+var_F8], xmm1
0x180007621  movups  [rbp+0E0h+var_E8], xmm1
0x180007625  movups  [rbp+0E0h+var_D8], xmm1
0x180007629  movups  [rbp+0E0h+var_C8], xmm1
0x18000762d  movups  [rbp+0E0h+var_B8], xmm1
0x180007631  mov     [rbp+0E0h+var_A8], rax
0x180007635  mov     [rbp+0E0h+var_90], 1
0x18000763c  mov     [rbp+0E0h+var_88], rax
0x180007640  lea     rax, [rsp+1E0h+var_188]
0x180007645  mov     [rbp+0E0h+var_80], rax
0x180007649  mov     [rbp+0E0h+var_78], r14
0x18000764d  mov     [rbp+0E0h+var_70], r14
0x180007651  lea     rax, [rsp+1E0h+var_190]
0x180007656  mov     [rbp+0E0h+var_68], rax
0x18000765a  mov     [rbp+0E0h+var_60], r14
0x180007661  mov     [rbp+0E0h+var_58], r14d
0x180007668  lea     rax, [rbp+0E0h+var_160]
0x18000766c  mov     [rbp+0E0h+var_50], rax
0x180007673  mov     [rbp+0E0h+var_48], 0
0x18000767a  lea     r15, ??_7WnsCMCreate@WnsCPLog@@6B@; const WnsCPLog::WnsCMCreate::`vftable'
0x180007681  mov     [rsp+1E0h+var_190], r15
0x180007686  mov     rdx, [rbx+20h]; unsigned __int64
0x18000768a  lea     rcx, [rsp+1E0h+var_190]; this
0x18000768f  call    ?StartActivity@WnsCMCreate@WnsCPLog@@QEAAX_K@Z; WnsCPLog::WnsCMCreate::StartActivity(unsigned __int64)
0x180007694  nop
0x180007695  mov     rcx, [rbp+0E8h]; this
0x18000769c  test    rsi, rsi
0x18000769f  jz      short loc_180007705
0x1800076a1  xor     edx, edx
0x1800076a3  lea     rcx, [rsp+1E0h+var_190]
0x1800076a8  call    ?Stop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800076ad  nop
0x1800076ae  mov     [rsp+1E0h+var_190], r15
0x1800076b3  lea     rcx, [rsp+1E0h+var_190]
0x1800076b8  call    ?Destroy@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800076bd  lea     rcx, [rsp+1E0h+var_190]
0x1800076c2  call    ??1?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800076c7  nop
0x1800076c8  mov     rcx, [rdi]
0x1800076cb  test    rcx, rcx
0x1800076ce  jnz     short loc_18000771D
0x1800076d0  mov     [rdi], rbx
0x1800076d3  mov     rbx, r14
0x1800076d6  test    rbx, rbx
0x1800076d9  jz      short loc_1800076E3
0x1800076db  mov     rcx, rbx; Block
0x1800076de  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800076e3  mov     rax, rdi
0x1800076e6  mov     rcx, [rbp+0E0h+var_40]
0x1800076ed  xor     rcx, rsp; StackCookie
0x1800076f0  call    __security_check_cookie
0x1800076f5  add     rsp, 1B8h
0x1800076fc  pop     r15
0x1800076fe  pop     r14
0x180007700  pop     rdi
0x180007701  pop     rsi
0x180007702  pop     rbx
0x180007703  pop     rbp
0x180007704  retn
0x180007705  mov     r9d, 80070057h; char *
0x18000770b  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007712  mov     edx, 29h ; ')'; void *
0x180007717  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000771d  mov     rax, [rcx]
0x180007720  mov     rax, [rax+10h]
0x180007724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007729  jmp     short loc_1800076D0
```
