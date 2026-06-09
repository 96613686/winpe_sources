# CMitigationClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180017260`
- end: `0x18001756e`
- name: `?CreateInstance@CMitigationClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `782`
- prototype: `__int64 __fastcall(unsigned __int64 this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ea68`
- `0x18000f6a8`
- `0x18001055c`
- `0x18001208c`
- `0x18001716c`
- `0x180017260`
- `0x180017670`
- `0x180017ba8`
- `0x180017cb4`
- `0x1800245a4`
- `0x1800350d4`
- `0x18005c010`

## import_xrefs

- `combase!__imp_CoAddRefSharedService` at `0x1800173fb`
- `combase!__imp_CoAddRefSharedService` at `0x1800173fb`

## string_xrefs

- `0x180017294`: `onecore\base\diagnosis\mitigation\client\dll\mitigationclassfactory.cpp`
- `0x180017428`: `onecore\base\diagnosis\mitigation\client\dll\mitigationclassfactory.cpp`
- `0x180017485`: `onecore\base\diagnosis\mitigation\client\dll\mitigationclassfactory.cpp`
- `0x1800174cb`: `onecore\base\diagnosis\mitigation\client\dll\mitigationclassfactory.cpp`
- `0x180017542`: `onecore\base\diagnosis\mitigation\client\dll\mitigationclassfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMitigationClassFactory::CreateInstance(
        unsigned __int64 this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rcx
  MitigationTelemetryClass *v9; // rax
  unsigned __int64 v10; // rcx
  struct IClientObjectStubManager *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  void *v19; // rbx
  __int64 (__fastcall *v20)(void *, GUID *, __int64 *); // rdi
  int v21; // eax
  _QWORD *v22; // rbx
  __int64 v23; // r14
  __int64 v24; // rdx
  int v25; // eax
  unsigned int v26; // edi
  _QWORD *v27; // rdx
  int v28; // eax
  struct _GUID v30; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  void *v32; // [rsp+68h] [rbp+38h] BYREF
  __int64 v33; // [rsp+78h] [rbp+48h] BYREF

  *a4 = 0;
  if ( !a2 )
  {
    if ( MitigationTelemetryClass::IsEnabled(this, 0) )
    {
      v9 = (MitigationTelemetryClass *)wil::details::static_lazy<MitigationTelemetryClass>::get(
                                         v8,
                                         _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_);
      v30 = *a3;
      MitigationTelemetryClass::ClassFactoryCreateInstance_(v9, *(_BYTE *)(this + 24), &v30);
    }
    v32 = 0;
    v10 = this & -(__int64)(*(_BYTE *)(this + 24) != 0);
    v11 = (struct IClientObjectStubManager *)((v10 + 8) & -(__int64)(v10 != 0));
    v12 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_c79a68dd_baba_4cab_bc48_b0af313ea5fe.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_c79a68dd_baba_4cab_bc48_b0af313ea5fe.Data1 )
      v12 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_c79a68dd_baba_4cab_bc48_b0af313ea5fe.Data4;
    if ( !v12 )
      goto LABEL_17;
    v13 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_39dfff64_6bee_4c8d_8575_b1a834f6bd2c.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_39dfff64_6bee_4c8d_8575_b1a834f6bd2c.Data1 )
      v13 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_39dfff64_6bee_4c8d_8575_b1a834f6bd2c.Data4;
    if ( v13 )
    {
      v14 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_d555b534_8777_464a_8acc_781e36aa123e.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_d555b534_8777_464a_8acc_781e36aa123e.Data1 )
        v14 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_d555b534_8777_464a_8acc_781e36aa123e.Data4;
      if ( v14 )
      {
        v7 = -2147467262;
        v16 = 2147500034LL;
        v17 = 41;
        goto LABEL_35;
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
      v15 = MitigationState::s_CreateInstance(a3, &v32, v11);
      v7 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationstate\\mitigationstate.cpp",
          (const char *)(unsigned int)v15,
          v30.Data1);
        v16 = v7;
        v17 = 37;
LABEL_35:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\dll\\mitigationclassfactory.cpp",
          (const char *)v16,
          v30.Data1);
        goto LABEL_36;
      }
    }
    else
    {
LABEL_17:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
      v18 = MitigationManager::s_CreateInstance(a3, &v32, v11);
      v7 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x43,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
          (const char *)(unsigned int)v18,
          v30.Data1);
        v16 = v7;
        v17 = 33;
        goto LABEL_35;
      }
    }
    if ( v11 )
    {
      if ( dword_180080AB8 )
        CoAddRefSharedService();
      _InterlockedIncrement((volatile signed __int32 *)&g_clientCount);
      wil::EnterCriticalSection(&v30, this + 48);
      if ( *(_BYTE *)(this + 120) )
      {
        v7 = -2147483622;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x38,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\dll\\mitigationclassfactory.cpp",
          (const char *)0x8000001ALL,
          v30.Data1);
LABEL_24:
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v30);
        goto LABEL_36;
      }
      v33 = 0;
      v19 = v32;
      v20 = **(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v32;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
      v21 = v20(v19, &GUID_00000000_0000_0000_c000_000000000046, &v33);
      v7 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\dll\\mitigationclassfactory.cpp",
          (const char *)(unsigned int)v21,
          v30.Data1);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
        goto LABEL_24;
      }
      v22 = (_QWORD *)(this + 88);
      v23 = v33;
      v24 = v22[1];
      if ( v24 == v22[3] )
      {
        v25 = CTSimpleArray<Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>>>::_EnsureCapacity(
                v22,
                v24 + 1);
        v26 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C,
            (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\dll\\mitigationclassfactory.cpp",
            (const char *)(unsigned int)v25,
            v30.Data1);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v30);
          v7 = v26;
          goto LABEL_36;
        }
      }
      v27 = (_QWORD *)(*v22 + 8 * v22[1]++);
      if ( v27 )
        *v27 = v23;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v30);
    }
    v28 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v32)(v32, a3, a4);
    v7 = v28;
    if ( v28 < 0 )
    {
      v16 = (unsigned int)v28;
      v17 = 63;
      goto LABEL_35;
    }
LABEL_36:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
    return v7;
  }
  v7 = -2147221232;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x18,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\dll\\mitigationclassfactory.cpp",
    (const char *)0x80040110LL,
    v30.Data1);
  return v7;
}

```

## disassembly

```asm
0x180017260  mov     [rsp-28h+arg_0], rbx
0x180017265  push    rbp
0x180017266  push    rsi
0x180017267  push    rdi
0x180017268  push    r14
0x18001726a  push    r15
0x18001726c  mov     rbp, rsp
0x18001726f  sub     rsp, 30h
0x180017273  mov     r15, r9
0x180017276  mov     rsi, r8
0x180017279  mov     r14, rcx
0x18001727c  mov     qword ptr [r9], 0
0x180017283  test    rdx, rdx
0x180017286  jz      short loc_1800172AA
0x180017288  mov     rcx, [rbp+28h]; this
0x18001728c  mov     ebx, 80040110h
0x180017291  mov     r9d, ebx; char *
0x180017294  lea     r8, aOnecoreBaseDia_37; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001729b  mov     edx, 18h; void *
0x1800172a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800172a5  jmp     loc_18001755B
0x1800172aa  call    ?IsEnabled@MitigationTelemetryClass@@SA_NE_K@Z; MitigationTelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800172af  test    al, al
0x1800172b1  jz      short loc_1800172D7
0x1800172b3  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_a44fdf97cbcc0b6240bb4609dde993dd_@@CA@XZ; _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_(void)
0x1800172ba  call    ?get@?$static_lazy@VMitigationTelemetryClass@@@details@wil@@QEAAPEAVMitigationTelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<MitigationTelemetryClass>::get(void (*)(void))
0x1800172bf  movups  xmm0, xmmword ptr [rsi]
0x1800172c2  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x1800172c7  lea     r8, [rbp+var_10]; struct _GUID
0x1800172cb  mov     dl, [r14+18h]; bool
0x1800172cf  mov     rcx, rax; this
0x1800172d2  call    ?ClassFactoryCreateInstance_@MitigationTelemetryClass@@QEAAX_NU_GUID@@@Z; MitigationTelemetryClass::ClassFactoryCreateInstance_(bool,_GUID)
0x1800172d7  mov     [rbp+arg_8], 0
0x1800172df  mov     al, [r14+18h]
0x1800172e3  neg     al
0x1800172e5  sbb     rcx, rcx
0x1800172e8  and     rcx, r14
0x1800172eb  lea     rax, [rcx+8]
0x1800172ef  neg     rcx
0x1800172f2  sbb     rdi, rdi
0x1800172f5  and     rdi, rax
0x1800172f8  mov     rax, [rsi]
0x1800172fb  sub     rax, qword ptr cs:_GUID_c79a68dd_baba_4cab_bc48_b0af313ea5fe.Data1
0x180017302  jnz     short loc_18001730F
0x180017304  mov     rax, [rsi+8]
0x180017308  sub     rax, qword ptr cs:_GUID_c79a68dd_baba_4cab_bc48_b0af313ea5fe.Data4
0x18001730f  test    rax, rax
0x180017312  jz      loc_1800173A5
0x180017318  mov     rax, [rsi]
0x18001731b  sub     rax, qword ptr cs:_GUID_39dfff64_6bee_4c8d_8575_b1a834f6bd2c.Data1
0x180017322  jnz     short loc_18001732F
0x180017324  mov     rax, [rsi+8]
0x180017328  sub     rax, qword ptr cs:_GUID_39dfff64_6bee_4c8d_8575_b1a834f6bd2c.Data4
0x18001732f  test    rax, rax
0x180017332  jz      short loc_1800173A5
0x180017334  mov     rax, [rsi]
0x180017337  sub     rax, qword ptr cs:_GUID_d555b534_8777_464a_8acc_781e36aa123e.Data1
0x18001733e  jnz     short loc_18001734B
0x180017340  mov     rax, [rsi+8]
0x180017344  sub     rax, qword ptr cs:_GUID_d555b534_8777_464a_8acc_781e36aa123e.Data4
0x18001734b  test    rax, rax
0x18001734e  jnz     short loc_180017393
0x180017350  lea     rcx, [rbp+arg_8]
0x180017354  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180017359  mov     r8, rdi; struct IClientObjectStubManager *
0x18001735c  lea     rdx, [rbp+arg_8]; void **
0x180017360  mov     rcx, rsi; struct _GUID *
0x180017363  call    ?s_CreateInstance@MitigationState@@SAJAEBU_GUID@@PEAPEAXPEAUIClientObjectStubManager@@@Z; MitigationState::s_CreateInstance(_GUID const &,void * *,IClientObjectStubManager *)
0x180017368  mov     ebx, eax
0x18001736a  test    eax, eax
0x18001736c  jns     short loc_1800173E8
0x18001736e  mov     rcx, [rbp+28h]; this
0x180017372  mov     r9d, eax; char *
0x180017375  lea     r8, aOnecoreBaseDia_6; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001737c  mov     edx, 32h ; '2'; void *
0x180017381  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017386  mov     r9d, ebx
0x180017389  mov     edx, 25h ; '%'
0x18001738e  jmp     loc_180017542
0x180017393  mov     ebx, 80004002h
0x180017398  mov     r9d, ebx
0x18001739b  mov     edx, 29h ; ')'
0x1800173a0  jmp     loc_180017542
0x1800173a5  lea     rcx, [rbp+arg_8]
0x1800173a9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800173ae  mov     r8, rdi; struct IClientObjectStubManager *
0x1800173b1  lea     rdx, [rbp+arg_8]; void **
0x1800173b5  mov     rcx, rsi; struct _GUID *
0x1800173b8  call    ?s_CreateInstance@MitigationManager@@SAJAEBU_GUID@@PEAPEAXPEAUIClientObjectStubManager@@@Z; MitigationManager::s_CreateInstance(_GUID const &,void * *,IClientObjectStubManager *)
0x1800173bd  mov     ebx, eax
0x1800173bf  test    eax, eax
0x1800173c1  jns     short loc_1800173E8
0x1800173c3  mov     rcx, [rbp+28h]; this
0x1800173c7  mov     r9d, eax; char *
0x1800173ca  lea     r8, aOnecoreBaseDia_24; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800173d1  mov     edx, 43h ; 'C'; void *
0x1800173d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800173db  mov     r9d, ebx
0x1800173de  mov     edx, 21h ; '!'
0x1800173e3  jmp     loc_180017542
0x1800173e8  test    rdi, rdi
0x1800173eb  jz      loc_18001751F
0x1800173f1  mov     ecx, cs:dword_180080AB8
0x1800173f7  test    ecx, ecx
0x1800173f9  jz      short loc_180017401
0x1800173fb  call    cs:__imp_CoAddRefSharedService
0x180017401  lock inc cs:?g_clientCount@@3KC; ulong volatile g_clientCount
0x180017408  lea     rdx, [r14+30h]
0x18001740c  lea     rcx, [rbp+var_10]
0x180017410  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180017415  cmp     byte ptr [r14+78h], 0
0x18001741a  jz      short loc_180017447
0x18001741c  mov     rcx, [rbp+28h]; this
0x180017420  mov     ebx, 8000001Ah
0x180017425  mov     r9d, ebx; char *
0x180017428  lea     r8, aOnecoreBaseDia_37; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001742f  mov     edx, 38h ; '8'; void *
0x180017434  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017439  lea     rcx, [rbp+var_10]
0x18001743d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180017442  jmp     loc_180017552
0x180017447  mov     [rbp+arg_18], 0
0x18001744f  mov     rbx, [rbp+arg_8]
0x180017453  mov     rax, [rbx]
0x180017456  mov     rdi, [rax]
0x180017459  lea     rcx, [rbp+arg_18]
0x18001745d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180017462  lea     r8, [rbp+arg_18]
0x180017466  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001746d  mov     rcx, rbx
0x180017470  mov     rax, rdi
0x180017473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017478  mov     ebx, eax
0x18001747a  test    eax, eax
0x18001747c  jns     short loc_1800174A1
0x18001747e  mov     rcx, [rbp+28h]; this
0x180017482  mov     r9d, eax; char *
0x180017485  lea     r8, aOnecoreBaseDia_37; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001748c  mov     edx, 3Bh ; ';'; void *
0x180017491  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017496  lea     rcx, [rbp+arg_18]
0x18001749a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001749f  jmp     short loc_180017439
0x1800174a1  lea     rbx, [r14+58h]
0x1800174a5  mov     r14, [rbp+arg_18]
0x1800174a9  mov     rdx, [rbx+8]
0x1800174ad  cmp     rdx, [rbx+18h]
0x1800174b1  jnz     short loc_1800174F2
0x1800174b3  inc     rdx
0x1800174b6  mov     rcx, rbx
0x1800174b9  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@VMitigationOneSettingsMetadata@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@VMitigationOneSettingsMetadata@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@VMitigationOneSettingsMetadata@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@VMitigationOneSettingsMetadata@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800174be  mov     edi, eax
0x1800174c0  test    eax, eax
0x1800174c2  jns     short loc_1800174F2
0x1800174c4  mov     rcx, [rbp+28h]; this
0x1800174c8  mov     r9d, eax; char *
0x1800174cb  lea     r8, aOnecoreBaseDia_37; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800174d2  mov     edx, 3Ch ; '<'; void *
0x1800174d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800174dc  lea     rcx, [rbp+arg_18]
0x1800174e0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800174e5  lea     rcx, [rbp+var_10]
0x1800174e9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800174ee  mov     ebx, edi
0x1800174f0  jmp     short loc_180017552
0x1800174f2  inc     qword ptr [rbx+8]
0x1800174f6  mov     rdx, [rbx+8]
0x1800174fa  mov     rax, [rbx]
0x1800174fd  dec     rdx
0x180017500  lea     rdx, [rax+rdx*8]
0x180017504  test    rdx, rdx
0x180017507  jz      short loc_18001750C
0x180017509  mov     [rdx], r14
0x18001750c  lea     rcx, [rbp+arg_18]
0x180017510  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180017515  lea     rcx, [rbp+var_10]
0x180017519  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001751e  nop
0x18001751f  mov     rcx, [rbp+arg_8]
0x180017523  mov     rax, [rcx]
0x180017526  mov     r8, r15
0x180017529  mov     rdx, rsi
0x18001752c  mov     rax, [rax]
0x18001752f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017534  mov     ebx, eax
0x180017536  test    eax, eax
0x180017538  jns     short loc_180017552
0x18001753a  mov     r9d, eax; char *
0x18001753d  mov     edx, 3Fh ; '?'; void *
0x180017542  lea     r8, aOnecoreBaseDia_37; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180017549  mov     rcx, [rbp+28h]; this
0x18001754d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017552  lea     rcx, [rbp+arg_8]
0x180017556  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001755b  mov     eax, ebx
0x18001755d  mov     rbx, [rsp+30h+arg_0]
0x180017562  add     rsp, 30h
0x180017566  pop     r15
0x180017568  pop     r14
0x18001756a  pop     rdi
0x18001756b  pop     rsi
0x18001756c  pop     rbp
0x18001756d  retn
```
