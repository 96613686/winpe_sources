# CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification(ushort const *,ushort const *)

- ea: `0x180007250`
- end: `0x180007601`
- name: `?CreateToastXmlDocumentForBatteryNotification@CBatteryNotificationManager@@CA?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@PEBG0@Z`
- size: `945`
- prototype: `__int64 (__fastcall ****__fastcall(__int64 (__fastcall ****)(_QWORD, __int64 *, LPVOID *), const wchar_t *, const wchar_t *))(_QWORD, __int64 *, LPVOID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800062e0`

## callees

- `0x180002314`
- `0x18000232c`
- `0x180003a28`
- `0x180005854`
- `0x180006920`
- `0x180007250`
- `0x18000bde4`
- `0x18000c010`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000759a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000759a`

## string_xrefs

- `0x1800072f3`: `<toast scenario="systemModalDialog">\n                <adaptive-card-json activationType="foreground"></adaptive-card-json>\n            </toast>`
- `0x180007394`: `/toast/adaptive-card-json`

## pseudocode

```c
__int64 (__fastcall ****__fastcall CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification(
        __int64 (__fastcall ****a1)(_QWORD, __int64 *, LPVOID *),
        const wchar_t *a2,
        const wchar_t *a3))(_QWORD, __int64 *, LPVOID *)
{
  __int64 (__fastcall ***v6)(_QWORD, __int64 *, LPVOID *); // rcx
  int v7; // eax
  LPVOID v8; // rcx
  int v9; // eax
  int *v10; // rdx
  __int64 (__fastcall ***v11)(_QWORD, __int64 *, LPVOID *); // rcx
  int v12; // eax
  LPVOID v13; // rcx
  int v14; // eax
  __int64 (__fastcall ***v15)(LPVOID, __int64 *, LPVOID *); // rdi
  LPVOID v16; // rbx
  __int64 (__fastcall ***v17)(LPVOID, __int64 *, LPVOID *); // r15
  int v18; // eax
  int v19; // eax
  volatile signed __int32 *v20; // rdi
  int v21; // eax
  LPVOID v22; // rcx
  int v23; // eax
  int v24; // r14d
  HANDLE ProcessHeap; // rax
  LPVOID v27; // [rsp+28h] [rbp-58h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v29; // [rsp+38h] [rbp-48h] BYREF
  int v30; // [rsp+40h] [rbp-40h] BYREF
  __int128 v31; // [rsp+48h] [rbp-38h]
  int *v32; // [rsp+58h] [rbp-28h]
  int v33; // [rsp+60h] [rbp-20h] BYREF
  int v34; // [rsp+64h] [rbp-1Ch]
  const wchar_t *v35; // [rsp+70h] [rbp-10h]
  __int64 (__fastcall ***v36)(int **, LPVOID *); // [rsp+C8h] [rbp+48h] BYREF

  v29 = &qword_180014768;
  _InterlockedIncrement64(&qword_180014768);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> )
  {
    _lambda_e39067982572d3667926157dc9eb0f0a_::operator()(
      a1,
      a1,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedAdd64(&qword_180014768, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_180014768, 0xFFFFFFFFFFFFFFFFuLL);
    lpMem = _lambda_e39067982572d3667926157dc9eb0f0a_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Xml::Dom::XmlDocument (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      a1,
      a1,
      &lpMem);
  }
  v33 = 1;
  v34 = 143;
  v35 = L"<toast scenario=\"systemModalDialog\">\n"
         "                <adaptive-card-json activationType=\"foreground\"></adaptive-card-json>\n"
         "            </toast>";
  v32 = &v33;
  v6 = *a1;
  v27 = 0;
  if ( v6 )
  {
    v7 = (**v6)(v6, winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlDocumentIO>, &v27);
    v8 = v27;
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
  v30 = 0;
  v31 = 0;
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v30);
  v30 = 0;
  v31 = 0;
  v9 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 48LL))(v8);
  if ( v9 < 0 )
    winrt::throw_hresult((unsigned int)v9, &v30);
  winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v27);
  CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification((int ***)&v36, a2, a3);
  v33 = 1;
  v34 = 25;
  v35 = L"/toast/adaptive-card-json";
  v10 = &v33;
  v32 = &v33;
  lpMem = 0;
  v11 = *a1;
  v27 = 0;
  if ( v11 )
  {
    v12 = (**v11)(v11, winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlNodeSelector>, &v27);
    v13 = v27;
    v10 = v32;
  }
  else
  {
    v12 = 0;
    v13 = 0;
  }
  v30 = 0;
  v31 = 0;
  if ( v12 < 0 )
    winrt::throw_hresult((unsigned int)v12, &v30);
  v30 = 0;
  v31 = 0;
  v14 = (*(__int64 (__fastcall **)(LPVOID, int *, LPVOID *))(*(_QWORD *)v13 + 48LL))(v13, v10, &lpMem);
  if ( v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, &v30);
  winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v27);
  v15 = (__int64 (__fastcall ***)(LPVOID, __int64 *, LPVOID *))lpMem;
  v29 = (__int64 *)lpMem;
  if ( lpMem )
  {
    lpMem = 0;
    v30 = 0;
    v31 = 0;
    v18 = (**v15)(v15, winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlElement>, &lpMem);
    if ( v18 < 0 )
      winrt::throw_hresult((unsigned int)v18, &v30);
    v16 = lpMem;
    v17 = (__int64 (__fastcall ***)(LPVOID, __int64 *, LPVOID *))lpMem;
  }
  else
  {
    v16 = 0;
    v17 = 0;
  }
  v27 = v16;
  if ( v15 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v29);
  lpMem = 0;
  v30 = 0;
  v31 = 0;
  v19 = (*v36)[7]((int **)v36, &lpMem);
  if ( v19 < 0 )
    winrt::throw_hresult((unsigned int)v19, &v30);
  v20 = (volatile signed __int32 *)lpMem;
  v29 = (__int64 *)lpMem;
  lpMem = 0;
  if ( v17 )
  {
    v21 = (**v17)(v17, winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlNodeSerializer>, &lpMem);
    v22 = lpMem;
  }
  else
  {
    v21 = 0;
    v22 = 0;
  }
  v30 = 0;
  v31 = 0;
  if ( v21 < 0 )
    winrt::throw_hresult((unsigned int)v21, &v30);
  v30 = 0;
  v31 = 0;
  v23 = (*(__int64 (__fastcall **)(LPVOID, volatile signed __int32 *))(*(_QWORD *)v22 + 64LL))(v22, v20);
  if ( v23 < 0 )
    winrt::throw_hresult((unsigned int)v23, &v30);
  winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&lpMem);
  if ( v20 )
  {
    v24 = _InterlockedDecrement(v20 + 6);
    if ( v24 )
    {
      if ( v24 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v20);
    }
  }
  if ( v16 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v27);
  if ( v36 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v36);
  return a1;
}

```

## disassembly

```asm
0x180007250  mov     [rsp-28h+arg_8], rbx
0x180007255  mov     [rsp-28h+arg_10], rsi
0x18000725a  mov     [rsp-28h+arg_0], rcx
0x18000725f  push    rbp
0x180007260  push    rdi
0x180007261  push    r12
0x180007263  push    r14
0x180007265  push    r15
0x180007267  mov     rbp, rsp
0x18000726a  sub     rsp, 80h
0x180007271  mov     rbx, r8
0x180007274  mov     rdi, rdx
0x180007277  mov     rsi, rcx
0x18000727a  xor     r12d, r12d
0x18000727d  mov     [rbp+var_60], r12d
0x180007281  lea     rax, qword_180014768
0x180007288  mov     [rbp+var_48], rax
0x18000728c  lock inc cs:qword_180014768
0x180007294  cmp     cs:??$factory_cache_entry_v@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A, r12; factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>
0x18000729b  jz      short loc_1800072BB
0x18000729d  lea     r8, ??$factory_cache_entry_v@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A; factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>
0x1800072a4  mov     rdx, rcx
0x1800072a7  call    ??R_lambda_e39067982572d3667926157dc9eb0f0a_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_e39067982572d3667926157dc9eb0f0a_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x1800072ac  nop
0x1800072ad  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800072b1  lock add cs:qword_180014768, r14
0x1800072b9  jmp     short loc_1800072DE
0x1800072bb  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800072bf  lock add cs:qword_180014768, r14
0x1800072c7  lea     rax, ?_lambda_invoker_cdecl_@_lambda_e39067982572d3667926157dc9eb0f0a_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_e39067982572d3667926157dc9eb0f0a_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x1800072ce  mov     [rbp+lpMem], rax
0x1800072d2  lea     r8, [rbp+lpMem]
0x1800072d6  mov     rdx, rsi
0x1800072d9  call    ??$call@P6A?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUXmlDocument@Dom@Xml@Data@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z
0x1800072de  mov     [rbp+var_60], 3
0x1800072e5  mov     [rbp+var_20], 1
0x1800072ec  mov     [rbp+var_1C], 8Fh
0x1800072f3  lea     rax, aToastScenarioS; "<toast scenario=\"systemModalDialog\">"...
0x1800072fa  mov     [rbp+var_10], rax
0x1800072fe  lea     rdx, [rbp+var_20]
0x180007302  mov     [rbp+var_28], rdx
0x180007306  mov     rcx, [rsi]
0x180007309  mov     [rbp+var_58], r12
0x18000730d  test    rcx, rcx
0x180007310  jnz     short loc_18000731A
0x180007312  mov     eax, r12d
0x180007315  mov     rcx, r12
0x180007318  jmp     short loc_18000733C
0x18000731a  mov     rax, [rcx]
0x18000731d  lea     r8, [rbp+var_58]
0x180007321  lea     rdx, ??$guid_v@UIXmlDocumentIO@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlDocumentIO>
0x180007328  mov     rax, [rax]
0x18000732b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007330  mov     rcx, [rbp+var_58]
0x180007334  mov     [rbp+var_58], rcx
0x180007338  mov     rdx, [rbp+var_28]
0x18000733c  mov     [rbp+var_40], r12d
0x180007340  xorps   xmm0, xmm0
0x180007343  movdqu  [rbp+var_38], xmm0
0x180007348  test    eax, eax
0x18000734a  js      loc_1800075AD
0x180007350  mov     [rbp+var_40], r12d
0x180007354  movdqu  [rbp+var_38], xmm0
0x180007359  mov     rax, [rcx]
0x18000735c  mov     rax, [rax+30h]
0x180007360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007365  test    eax, eax
0x180007367  js      loc_1800075B9
0x18000736d  lea     rcx, [rbp+var_58]
0x180007371  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180007376  mov     r8, rbx
0x180007379  mov     rdx, rdi
0x18000737c  lea     rcx, [rbp+arg_18]
0x180007380  call    ?CreateAdaptiveCardJsonForBatteryNotification@CBatteryNotificationManager@@CA?AUIJsonValue@Json@Data@Windows@winrt@@PEBG0@Z; CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification(ushort const *,ushort const *)
0x180007385  nop
0x180007386  mov     [rbp+var_20], 1
0x18000738d  mov     [rbp+var_1C], 19h
0x180007394  lea     rax, aToastAdaptiveC; "/toast/adaptive-card-json"
0x18000739b  mov     [rbp+var_10], rax
0x18000739f  lea     rdx, [rbp+var_20]
0x1800073a3  mov     [rbp+var_28], rdx
0x1800073a7  mov     [rbp+lpMem], r12
0x1800073ab  mov     rcx, [rsi]
0x1800073ae  mov     [rbp+var_58], r12
0x1800073b2  test    rcx, rcx
0x1800073b5  jnz     short loc_1800073BF
0x1800073b7  mov     eax, r12d
0x1800073ba  mov     rcx, r12
0x1800073bd  jmp     short loc_1800073E1
0x1800073bf  mov     rax, [rcx]
0x1800073c2  lea     r8, [rbp+var_58]
0x1800073c6  lea     rdx, ??$guid_v@UIXmlNodeSelector@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlNodeSelector>
0x1800073cd  mov     rax, [rax]
0x1800073d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073d5  mov     rcx, [rbp+var_58]
0x1800073d9  mov     [rbp+var_58], rcx
0x1800073dd  mov     rdx, [rbp+var_28]
0x1800073e1  mov     [rbp+var_40], r12d
0x1800073e5  xorps   xmm0, xmm0
0x1800073e8  movdqu  [rbp+var_38], xmm0
0x1800073ed  test    eax, eax
0x1800073ef  js      loc_1800075C5
0x1800073f5  mov     [rbp+var_40], r12d
0x1800073f9  movdqu  [rbp+var_38], xmm0
0x1800073fe  mov     rax, [rcx]
0x180007401  lea     r8, [rbp+lpMem]
0x180007405  mov     rax, [rax+30h]
0x180007409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000740e  test    eax, eax
0x180007410  js      loc_1800075D1
0x180007416  lea     rcx, [rbp+var_58]
0x18000741a  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18000741f  mov     rdi, [rbp+lpMem]
0x180007423  mov     [rbp+var_48], rdi
0x180007427  mov     [rbp+var_60], 7
0x18000742e  test    rdi, rdi
0x180007431  jnz     short loc_18000743B
0x180007433  mov     rbx, r12
0x180007436  mov     r15, r12
0x180007439  jmp     short loc_180007473
0x18000743b  mov     [rbp+lpMem], r12
0x18000743f  mov     [rbp+var_40], r12d
0x180007443  xorps   xmm0, xmm0
0x180007446  movdqu  [rbp+var_38], xmm0
0x18000744b  mov     rax, [rdi]
0x18000744e  lea     r8, [rbp+lpMem]
0x180007452  lea     rdx, ??$guid_v@UIXmlElement@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlElement>
0x180007459  mov     rcx, rdi
0x18000745c  mov     rax, [rax]
0x18000745f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007464  test    eax, eax
0x180007466  js      loc_1800075DD
0x18000746c  mov     rbx, [rbp+lpMem]
0x180007470  mov     r15, rbx
0x180007473  mov     [rbp+var_58], rbx
0x180007477  mov     [rbp+var_60], 1Fh
0x18000747e  test    rdi, rdi
0x180007481  jz      short loc_18000748C
0x180007483  lea     rcx, [rbp+var_48]
0x180007487  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18000748c  mov     [rbp+lpMem], r12
0x180007490  mov     rcx, [rbp+arg_18]
0x180007494  mov     [rbp+var_40], r12d
0x180007498  xorps   xmm0, xmm0
0x18000749b  movdqu  [rbp+var_38], xmm0
0x1800074a0  mov     rax, [rcx]
0x1800074a3  lea     rdx, [rbp+lpMem]
0x1800074a7  mov     rax, [rax+38h]
0x1800074ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074b0  test    eax, eax
0x1800074b2  js      loc_1800075E9
0x1800074b8  mov     rdi, [rbp+lpMem]
0x1800074bc  mov     [rbp+var_48], rdi
0x1800074c0  mov     [rbp+var_60], 3Fh ; '?'
0x1800074c7  mov     [rbp+lpMem], r12
0x1800074cb  test    r15, r15
0x1800074ce  jnz     short loc_1800074D8
0x1800074d0  mov     eax, r12d
0x1800074d3  mov     rcx, r12
0x1800074d6  jmp     short loc_1800074F9
0x1800074d8  mov     rax, [r15]
0x1800074db  lea     r8, [rbp+lpMem]
0x1800074df  lea     rdx, ??$guid_v@UIXmlNodeSerializer@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlNodeSerializer>
0x1800074e6  mov     rcx, r15
0x1800074e9  mov     rax, [rax]
0x1800074ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074f1  mov     rcx, [rbp+lpMem]
0x1800074f5  mov     [rbp+lpMem], rcx
0x1800074f9  mov     [rbp+var_40], r12d
0x1800074fd  xorps   xmm0, xmm0
0x180007500  movdqu  [rbp+var_38], xmm0
0x180007505  test    eax, eax
0x180007507  js      loc_1800075F5
0x18000750d  mov     [rbp+var_40], r12d
0x180007511  movdqu  [rbp+var_38], xmm0
0x180007516  mov     rax, [rcx]
0x180007519  mov     rdx, rdi
0x18000751c  mov     rax, [rax+40h]
0x180007520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007525  test    eax, eax
0x180007527  js      short loc_1800075A1
0x180007529  lea     rcx, [rbp+lpMem]
0x18000752d  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180007532  nop
0x180007533  test    rdi, rdi
0x180007536  jz      short loc_180007558
0x180007538  lock xadd [rdi+18h], r14d
0x18000753e  sub     r14d, 1
0x180007542  jnz     short loc_180007595
0x180007544  nop
0x180007545  call    WINRT_IMPL_GetProcessHeap
0x18000754a  mov     rcx, rax; hHeap
0x18000754d  mov     r8, rdi; lpMem
0x180007550  xor     edx, edx; dwFlags
0x180007552  call    WINRT_IMPL_HeapFree
0x180007557  nop
0x180007558  test    rbx, rbx
0x18000755b  jz      short loc_180007567
0x18000755d  lea     rcx, [rbp+var_58]
0x180007561  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180007566  nop
0x180007567  cmp     [rbp+arg_18], r12
0x18000756b  jz      short loc_180007576
0x18000756d  lea     rcx, [rbp+arg_18]
0x180007571  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180007576  mov     rax, rsi
0x180007579  lea     r11, [rsp+80h+var_s0]
0x180007581  mov     rbx, [r11+38h]
0x180007585  mov     rsi, [r11+40h]
0x180007589  mov     rsp, r11
0x18000758c  pop     r15
0x18000758e  pop     r14
0x180007590  pop     r12
0x180007592  pop     rdi
0x180007593  pop     rbp
0x180007594  retn
0x180007595  test    r14d, r14d
0x180007598  jns     short loc_180007558
0x18000759a  call    cs:__imp_abort
0x1800075a1  lea     rdx, [rbp+var_40]
0x1800075a5  mov     ecx, eax
0x1800075a7  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800075ad  lea     rdx, [rbp+var_40]
0x1800075b1  mov     ecx, eax
0x1800075b3  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800075b9  lea     rdx, [rbp+var_40]
0x1800075bd  mov     ecx, eax
0x1800075bf  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800075c5  lea     rdx, [rbp+var_40]
0x1800075c9  mov     ecx, eax
0x1800075cb  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800075d1  lea     rdx, [rbp+var_40]
0x1800075d5  mov     ecx, eax
0x1800075d7  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800075dd  lea     rdx, [rbp+var_40]
0x1800075e1  mov     ecx, eax
0x1800075e3  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800075e9  lea     rdx, [rbp+var_40]
0x1800075ed  mov     ecx, eax
0x1800075ef  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800075f5  lea     rdx, [rbp+var_40]
0x1800075f9  mov     ecx, eax
0x1800075fb  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
