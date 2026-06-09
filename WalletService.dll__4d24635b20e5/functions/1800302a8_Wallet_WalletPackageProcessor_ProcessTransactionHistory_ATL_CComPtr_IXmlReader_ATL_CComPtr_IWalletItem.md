# Wallet::WalletPackageProcessor::ProcessTransactionHistory(ATL::CComPtr<IXmlReader>,ATL::CComPtr<IWalletItem> &)

- ea: `0x1800302a8`
- end: `0x1800306a9`
- name: `?ProcessTransactionHistory@WalletPackageProcessor@Wallet@@AEAAJV?$CComPtr@UIXmlReader@@@ATL@@AEAV?$CComPtr@UIWalletItem@@@4@@Z`
- size: `1025`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800306b0`

## callees

- `0x180003ae4`
- `0x180003b40`
- `0x1800043b8`
- `0x180014328`
- `0x18001e754`
- `0x18002d048`
- `0x18002dffc`
- `0x18002e148`
- `0x18002e3e0`
- `0x18002e4d4`
- `0x1800302a8`
- `0x1800392b4`
- `0x180045010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003037a`
- `msvcrt!_wcsicmp` at `0x1800303ea`
- `msvcrt!_wcsicmp` at `0x18003045b`
- `msvcrt!_wcsicmp` at `0x1800304b2`
- `msvcrt!_wcsicmp` at `0x1800304e4`
- `msvcrt!_wcsicmp` at `0x180030519`
- `msvcrt!_wcsicmp` at `0x18003054e`
- `msvcrt!_wcsicmp` at `0x180030594`
- `msvcrt!_wcsicmp` at `0x1800305cb`
- `msvcrt!_wcsicmp` at `0x180030625`
- `msvcrt!_wcsicmp` at `0x18003037a`
- `msvcrt!_wcsicmp` at `0x1800303ea`
- `msvcrt!_wcsicmp` at `0x18003045b`
- `msvcrt!_wcsicmp` at `0x1800304b2`
- `msvcrt!_wcsicmp` at `0x1800304e4`
- `msvcrt!_wcsicmp` at `0x180030519`
- `msvcrt!_wcsicmp` at `0x18003054e`
- `msvcrt!_wcsicmp` at `0x180030594`
- `msvcrt!_wcsicmp` at `0x1800305cb`
- `msvcrt!_wcsicmp` at `0x180030625`

## string_xrefs

- `0x1800304ab`: `DisplayAmount`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Wallet::WalletPackageProcessor::ProcessTransactionHistory(__int64 *a1, __int64 *a2, _QWORD *a3)
{
  int WalletTransactionManager; // esi
  BOOL v6; // r15d
  BOOL v7; // r12d
  int v8; // eax
  __int64 v9; // r8
  _QWORD *v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // r8
  __int64 *v13; // rdx
  int v14; // eax
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // rbx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64 *); // rbx
  __int64 *v21; // rax
  wchar_t *String2; // [rsp+20h] [rbp-60h] BYREF
  struct IUnknown *v24; // [rsp+28h] [rbp-58h] BYREF
  __int64 v25; // [rsp+30h] [rbp-50h] BYREF
  __int64 v26; // [rsp+40h] [rbp-40h] BYREF
  __int64 v27; // [rsp+48h] [rbp-38h] BYREF
  __int64 v28; // [rsp+50h] [rbp-30h] BYREF
  __int64 v29; // [rsp+58h] [rbp-28h] BYREF
  __int64 v30; // [rsp+60h] [rbp-20h] BYREF
  __int64 v31; // [rsp+68h] [rbp-18h] BYREF
  __int64 v32; // [rsp+70h] [rbp-10h] BYREF
  __int64 v33; // [rsp+78h] [rbp-8h] BYREF
  int v35; // [rsp+D8h] [rbp+58h] BYREF

  v35 = 0;
  String2 = 0;
  v25 = 0;
  v24 = 0;
  v26 = 0;
  WalletTransactionManager = Wallet::Utils::GetWalletTransactionManager(&v26);
  if ( WalletTransactionManager >= 0 )
  {
    WalletTransactionManager = 0;
LABEL_3:
    v6 = 0;
    v7 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          while ( 1 )
          {
            while ( 1 )
            {
              if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)*a2 + 200LL))(*a2) )
                goto LABEL_45;
              v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)*a2 + 48LL))(*a2, &v35);
              if ( v8 < 0 )
                goto LABEL_44;
              if ( v35 != 1 )
                break;
              v8 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &String2, 0);
              if ( v8 >= 0 )
              {
                if ( _wcsicmp(L"TransactionItem", String2) )
                  continue;
                v19 = v26;
                v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 32LL);
                v21 = ce::pointerTo<IWalletNotification>((__int64 *)&v24);
                v8 = v20(v19, *a3, v21);
                if ( v8 >= 0 )
                  continue;
              }
              goto LABEL_44;
            }
            if ( v35 == 3 )
              break;
            if ( v35 == 15 )
            {
              v8 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &String2, 0);
              if ( v8 < 0 )
                goto LABEL_44;
              if ( !_wcsicmp(L"TransactionItem", String2) )
              {
                if ( !v7 || !v6 )
                {
LABEL_28:
                  WalletTransactionManager = -2143682462;
                  goto LABEL_45;
                }
                v10 = (_QWORD *)a1[10];
                if ( v10 == (_QWORD *)a1[11] )
                {
                  if ( !utl::vector<ATL::CComPtr<IWalletItemListener>,utl::allocator<ATL::CComPtr<IWalletItemListener>>>::_PushBackOne2<ATL::CComPtr<IWalletItemListener>>(
                          a1 + 9,
                          &v24,
                          v9) )
                  {
                    WalletTransactionManager = -2147024882;
                    goto LABEL_45;
                  }
                }
                else
                {
                  ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(
                    v10,
                    (__int64)v24);
                  a1[10] += 8;
                }
                if ( v24 )
                  ATL::AtlComPtrAssign(&v24, 0);
                goto LABEL_3;
              }
              if ( !_wcsicmp(L"TransactionHistory", String2) )
                goto LABEL_45;
            }
          }
        }
        while ( !String2 );
        if ( !v24 )
          goto LABEL_28;
        v8 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)*a2 + 128LL))(*a2, &v25, 0);
        if ( v8 < 0
          || (v8 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &String2, 0),
              v8 < 0) )
        {
LABEL_44:
          WalletTransactionManager = v8;
          goto LABEL_45;
        }
        if ( _wcsicmp(L"Description", String2) )
          break;
        v11 = v25;
        v7 = v25 != 0;
        ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(
          &v27,
          (__int64)v24);
        v12 = 30002;
        v13 = &v27;
LABEL_26:
        v14 = Wallet::WalletPackageProcessor::HandleStringProperty(a1, v13, v12, v11);
LABEL_27:
        if ( v14 < 0 )
          goto LABEL_28;
      }
      if ( !_wcsicmp(L"DisplayAmount", String2) )
      {
        v11 = v25;
        ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(
          &v28,
          (__int64)v24);
        v12 = 30001;
        v13 = &v28;
        goto LABEL_26;
      }
      if ( !_wcsicmp(L"Id", String2) )
      {
        v11 = v25;
        ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(
          &v29,
          (__int64)v24);
        v12 = 3001;
        v13 = &v29;
        goto LABEL_26;
      }
      if ( !_wcsicmp(L"DisplayLocation", String2) )
      {
        v11 = v25;
        ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(
          &v30,
          (__int64)v24);
        v12 = 30003;
        v13 = &v30;
        goto LABEL_26;
      }
      if ( !_wcsicmp(L"TransactionDate", String2) )
      {
        v15 = v25;
        v6 = v25 != 0;
        ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(
          &v31,
          (__int64)v24);
        v14 = Wallet::WalletPackageProcessor::HandleDateTimeProperty(&v31, 30004, v15);
        goto LABEL_27;
      }
      if ( !_wcsicmp(L"IgnoreTimeOfDay", String2) )
      {
        v16 = v25;
        ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(
          &v32,
          (__int64)v24);
        v14 = Wallet::WalletPackageProcessor::HandleBooleanProperty(&v32, v17, v16);
        goto LABEL_27;
      }
      if ( !_wcsicmp(L"IsLaunchable", String2) )
      {
        v18 = v25;
        ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(
          &v33,
          (__int64)v24);
        v14 = Wallet::WalletPackageProcessor::HandleBooleanAsStringProperty(&v33, 3002, v18);
        goto LABEL_27;
      }
    }
  }
LABEL_45:
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v26);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v24);
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(a2);
  return (unsigned int)WalletTransactionManager;
}

```

## disassembly

```asm
0x1800302a8  mov     [rsp-38h+arg_0], rbx
0x1800302ad  mov     [rsp-38h+arg_10], r8
0x1800302b2  mov     [rsp-38h+arg_8], rdx
0x1800302b7  push    rbp
0x1800302b8  push    rsi
0x1800302b9  push    rdi
0x1800302ba  push    r12
0x1800302bc  push    r13
0x1800302be  push    r14
0x1800302c0  push    r15
0x1800302c2  mov     rbp, rsp
0x1800302c5  sub     rsp, 80h
0x1800302cc  mov     r14, rdx
0x1800302cf  mov     r13, rcx
0x1800302d2  xor     edi, edi
0x1800302d4  mov     [rbp+arg_18], edi
0x1800302d7  mov     [rbp+String2], rdi
0x1800302db  mov     [rbp+var_50], rdi
0x1800302df  mov     [rbp+var_58], rdi
0x1800302e3  mov     [rbp+var_40], rdi
0x1800302e7  lea     rcx, [rbp+var_40]
0x1800302eb  call    ?GetWalletTransactionManager@Utils@Wallet@@YAJAEAV?$CComPtr@UIWalletTransactionManager@@@ATL@@@Z; Wallet::Utils::GetWalletTransactionManager(ATL::CComPtr<IWalletTransactionManager> &)
0x1800302f0  mov     esi, eax
0x1800302f2  test    eax, eax
0x1800302f4  js      loc_180030668
0x1800302fa  mov     esi, edi
0x1800302fc  mov     r15d, edi
0x1800302ff  mov     r12d, edi
0x180030302  mov     rcx, [r14]
0x180030305  mov     rax, [rcx]
0x180030308  mov     rax, [rax+0C8h]
0x18003030f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030314  test    eax, eax
0x180030316  jnz     loc_180030668
0x18003031c  mov     rcx, [r14]
0x18003031f  mov     rax, [rcx]
0x180030322  lea     rdx, [rbp+arg_18]
0x180030326  mov     rax, [rax+30h]
0x18003032a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003032f  test    eax, eax
0x180030331  js      loc_180030666
0x180030337  mov     ecx, [rbp+arg_18]
0x18003033a  sub     ecx, 1
0x18003033d  jz      loc_180030600
0x180030343  sub     ecx, 2
0x180030346  jz      loc_1800303FD
0x18003034c  cmp     ecx, 0Ch
0x18003034f  jnz     short loc_180030302
0x180030351  mov     rcx, [r14]
0x180030354  mov     rax, [rcx]
0x180030357  xor     r8d, r8d
0x18003035a  lea     rdx, [rbp+String2]
0x18003035e  mov     rax, [rax+70h]
0x180030362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030367  test    eax, eax
0x180030369  js      loc_180030666
0x18003036f  mov     rdx, [rbp+String2]; String2
0x180030373  lea     rcx, aTransactionite; "TransactionItem"
0x18003037a  call    cs:__imp__wcsicmp
0x180030380  test    eax, eax
0x180030382  jnz     short loc_1800303DF
0x180030384  test    r12d, r12d
0x180030387  jz      loc_18003049D
0x18003038d  test    r15d, r15d
0x180030390  jz      loc_18003049D
0x180030396  mov     rcx, [r13+50h]
0x18003039a  cmp     rcx, [r13+58h]
0x18003039e  jz      short loc_1800303B0
0x1800303a0  mov     rdx, [rbp+var_58]
0x1800303a4  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x1800303a9  add     qword ptr [r13+50h], 8
0x1800303ae  jmp     short loc_1800303C5
0x1800303b0  lea     rdx, [rbp+var_58]
0x1800303b4  lea     rcx, [r13+48h]
0x1800303b8  call    ??$_PushBackOne2@V?$CComPtr@UIWalletItemListener@@@ATL@@@?$vector@V?$CComPtr@UIWalletItemListener@@@ATL@@V?$allocator@V?$CComPtr@UIWalletItemListener@@@ATL@@@utl@@@utl@@AEAA_N$$QEAV?$CComPtr@UIWalletItemListener@@@ATL@@@Z; utl::vector<ATL::CComPtr<IWalletItemListener>,utl::allocator<ATL::CComPtr<IWalletItemListener>>>::_PushBackOne2<ATL::CComPtr<IWalletItemListener>>(ATL::CComPtr<IWalletItemListener> &&)
0x1800303bd  test    al, al
0x1800303bf  jz      loc_1800306A1
0x1800303c5  cmp     [rbp+var_58], rdi
0x1800303c9  jz      loc_1800302FC
0x1800303cf  xor     edx, edx; struct IUnknown *
0x1800303d1  lea     rcx, [rbp+var_58]; struct IUnknown **
0x1800303d5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800303da  jmp     loc_1800302FC
0x1800303df  mov     rdx, [rbp+String2]; String2
0x1800303e3  lea     rcx, aTransactionhis; "TransactionHistory"
0x1800303ea  call    cs:__imp__wcsicmp
0x1800303f0  test    eax, eax
0x1800303f2  jnz     loc_180030302
0x1800303f8  jmp     loc_180030668
0x1800303fd  cmp     [rbp+String2], rdi
0x180030401  jz      loc_180030302
0x180030407  cmp     [rbp+var_58], rdi
0x18003040b  jz      loc_18003049D
0x180030411  mov     rcx, [r14]
0x180030414  mov     rax, [rcx]
0x180030417  xor     r8d, r8d
0x18003041a  lea     rdx, [rbp+var_50]
0x18003041e  mov     rax, [rax+80h]
0x180030425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003042a  test    eax, eax
0x18003042c  js      loc_180030666
0x180030432  mov     rcx, [r14]
0x180030435  mov     rax, [rcx]
0x180030438  xor     r8d, r8d
0x18003043b  lea     rdx, [rbp+String2]
0x18003043f  mov     rax, [rax+70h]
0x180030443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030448  test    eax, eax
0x18003044a  js      loc_180030666
0x180030450  mov     rdx, [rbp+String2]; String2
0x180030454  lea     rcx, aDescription_0; "Description"
0x18003045b  call    cs:__imp__wcsicmp
0x180030461  test    eax, eax
0x180030463  jnz     short loc_1800304A7
0x180030465  mov     r12d, edi
0x180030468  mov     rbx, [rbp+var_50]
0x18003046c  test    rbx, rbx
0x18003046f  setnz   r12b
0x180030473  mov     rdx, [rbp+var_58]
0x180030477  lea     rcx, [rbp+var_38]
0x18003047b  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x180030480  mov     r8d, 7532h
0x180030486  lea     rdx, [rbp+var_38]
0x18003048a  mov     r9, rbx
0x18003048d  mov     rcx, r13
0x180030490  call    ?HandleStringProperty@WalletPackageProcessor@Wallet@@AEAAJV?$CComPtr@UIWalletItem@@@ATL@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEBG@Z; Wallet::WalletPackageProcessor::HandleStringProperty(ATL::CComPtr<IWalletItem>,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ushort const *)
0x180030495  test    eax, eax
0x180030497  jns     loc_180030302
0x18003049d  mov     esi, 803A0062h
0x1800304a2  jmp     loc_180030668
0x1800304a7  mov     rdx, [rbp+String2]; String2
0x1800304ab  lea     rcx, aDisplayamount; "DisplayAmount"
0x1800304b2  call    cs:__imp__wcsicmp
0x1800304b8  test    eax, eax
0x1800304ba  jnz     short loc_1800304D9
0x1800304bc  mov     rbx, [rbp+var_50]
0x1800304c0  mov     rdx, [rbp+var_58]
0x1800304c4  lea     rcx, [rbp+var_30]
0x1800304c8  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x1800304cd  mov     r8d, 7531h
0x1800304d3  lea     rdx, [rbp+var_30]
0x1800304d7  jmp     short loc_18003048A
0x1800304d9  mov     rdx, [rbp+String2]; String2
0x1800304dd  lea     rcx, aId_1; "Id"
0x1800304e4  call    cs:__imp__wcsicmp
0x1800304ea  test    eax, eax
0x1800304ec  jnz     short loc_18003050E
0x1800304ee  mov     rbx, [rbp+var_50]
0x1800304f2  mov     rdx, [rbp+var_58]
0x1800304f6  lea     rcx, [rbp+var_28]
0x1800304fa  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x1800304ff  mov     r8d, 0BB9h
0x180030505  lea     rdx, [rbp+var_28]
0x180030509  jmp     loc_18003048A
0x18003050e  mov     rdx, [rbp+String2]; String2
0x180030512  lea     rcx, aDisplaylocatio; "DisplayLocation"
0x180030519  call    cs:__imp__wcsicmp
0x18003051f  test    eax, eax
0x180030521  jnz     short loc_180030543
0x180030523  mov     rbx, [rbp+var_50]
0x180030527  mov     rdx, [rbp+var_58]
0x18003052b  lea     rcx, [rbp+var_20]
0x18003052f  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x180030534  mov     r8d, 7533h
0x18003053a  lea     rdx, [rbp+var_20]
0x18003053e  jmp     loc_18003048A
0x180030543  mov     rdx, [rbp+String2]; String2
0x180030547  lea     rcx, aTransactiondat; "TransactionDate"
0x18003054e  call    cs:__imp__wcsicmp
0x180030554  test    eax, eax
0x180030556  jnz     short loc_180030589
0x180030558  mov     r15d, edi
0x18003055b  mov     rbx, [rbp+var_50]
0x18003055f  test    rbx, rbx
0x180030562  setnz   r15b
0x180030566  mov     rdx, [rbp+var_58]
0x18003056a  lea     rcx, [rbp+var_18]
0x18003056e  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x180030573  mov     r8, rbx
0x180030576  mov     edx, 7534h
0x18003057b  lea     rcx, [rbp+var_18]
0x18003057f  call    ?HandleDateTimeProperty@WalletPackageProcessor@Wallet@@CAJV?$CComPtr@UIWalletItem@@@ATL@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEBG@Z; Wallet::WalletPackageProcessor::HandleDateTimeProperty(ATL::CComPtr<IWalletItem>,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ushort const *)
0x180030584  jmp     loc_180030495
0x180030589  mov     rdx, [rbp+String2]; String2
0x18003058d  lea     rcx, aIgnoretimeofda; "IgnoreTimeOfDay"
0x180030594  call    cs:__imp__wcsicmp
0x18003059a  test    eax, eax
0x18003059c  jnz     short loc_1800305C0
0x18003059e  mov     rbx, [rbp+var_50]
0x1800305a2  mov     rdx, [rbp+var_58]
0x1800305a6  lea     rcx, [rbp+var_10]
0x1800305aa  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x1800305af  mov     r8, rbx
0x1800305b2  lea     rcx, [rbp+var_10]
0x1800305b6  call    ?HandleBooleanProperty@WalletPackageProcessor@Wallet@@CAJV?$CComPtr@UIWalletItem@@@ATL@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEBG@Z; Wallet::WalletPackageProcessor::HandleBooleanProperty(ATL::CComPtr<IWalletItem>,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ushort const *)
0x1800305bb  jmp     loc_180030495
0x1800305c0  mov     rdx, [rbp+String2]; String2
0x1800305c4  lea     rcx, aIslaunchable; "IsLaunchable"
0x1800305cb  call    cs:__imp__wcsicmp
0x1800305d1  test    eax, eax
0x1800305d3  jnz     loc_180030302
0x1800305d9  mov     rbx, [rbp+var_50]
0x1800305dd  mov     rdx, [rbp+var_58]
0x1800305e1  lea     rcx, [rbp+var_8]
0x1800305e5  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x1800305ea  mov     r8, rbx
0x1800305ed  mov     edx, 0BBAh
0x1800305f2  lea     rcx, [rbp+var_8]
0x1800305f6  call    ?HandleBooleanAsStringProperty@WalletPackageProcessor@Wallet@@CAJV?$CComPtr@UIWalletItem@@@ATL@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEBG@Z; Wallet::WalletPackageProcessor::HandleBooleanAsStringProperty(ATL::CComPtr<IWalletItem>,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ushort const *)
0x1800305fb  jmp     loc_180030495
0x180030600  mov     rcx, [r14]
0x180030603  mov     rax, [rcx]
0x180030606  xor     r8d, r8d
0x180030609  lea     rdx, [rbp+String2]
0x18003060d  mov     rax, [rax+70h]
0x180030611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030616  test    eax, eax
0x180030618  js      short loc_180030666
0x18003061a  mov     rdx, [rbp+String2]; String2
0x18003061e  lea     rcx, aTransactionite; "TransactionItem"
0x180030625  call    cs:__imp__wcsicmp
0x18003062b  test    eax, eax
0x18003062d  jnz     loc_180030302
0x180030633  mov     rdi, [rbp+var_40]
0x180030637  mov     rax, [rdi]
0x18003063a  mov     rbx, [rax+20h]
0x18003063e  lea     rcx, [rbp+var_58]
0x180030642  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x180030647  mov     r8, rax
0x18003064a  mov     rax, [rbp+arg_10]
0x18003064e  mov     rdx, [rax]
0x180030651  mov     rcx, rdi
0x180030654  mov     rax, rbx
0x180030657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003065c  xor     edi, edi
0x18003065e  test    eax, eax
0x180030660  jns     loc_180030302
0x180030666  mov     esi, eax
0x180030668  lea     rcx, [rbp+var_40]
0x18003066c  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180030671  nop
0x180030672  lea     rcx, [rbp+var_58]
0x180030676  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18003067b  nop
0x18003067c  mov     rcx, r14
0x18003067f  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x180030684  mov     eax, esi
0x180030686  mov     rbx, [rsp+80h+arg_0]
0x18003068e  add     rsp, 80h
0x180030695  pop     r15
0x180030697  pop     r14
0x180030699  pop     r13
0x18003069b  pop     r12
0x18003069d  pop     rdi
0x18003069e  pop     rsi
0x18003069f  pop     rbp
0x1800306a0  retn
0x1800306a1  mov     esi, 8007000Eh
0x1800306a6  jmp     short loc_180030668
```
