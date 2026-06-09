# ShieldProvider::FirewallManager::GetNetworkDetails(NLM_NETWORK_CATEGORY,tagFIREWALL_PROFILE_INFO *)

- ea: `0x18004970c`
- end: `0x180049d99`
- name: `?GetNetworkDetails@FirewallManager@ShieldProvider@@AEAAJW4NLM_NETWORK_CATEGORY@@PEAUtagFIREWALL_PROFILE_INFO@@@Z`
- size: `1677`
- prototype: `__int64 __fastcall(ShieldProvider::FirewallManager *__hidden this, enum NLM_NETWORK_CATEGORY, struct tagFIREWALL_PROFILE_INFO *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048f0c`

## callees

- `0x18000a7ec`
- `0x18000ccb0`
- `0x18000d7fc`
- `0x180016d08`
- `0x18002e680`
- `0x180046dc8`
- `0x180048b60`
- `0x18004970c`
- `0x18004b014`
- `0x1800e1764`
- `0x1800e17e8`
- `0x1800e7010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800499b0`
- `ole32!CoTaskMemFree` at `0x1800499bd`
- `ole32!CoTaskMemFree` at `0x180049a72`
- `ole32!CoTaskMemFree` at `0x180049a7f`
- `ole32!CoTaskMemFree` at `0x180049c10`
- `ole32!CoTaskMemFree` at `0x180049c1d`
- `ole32!CoTaskMemFree` at `0x180049d11`
- `ole32!CoTaskMemFree` at `0x180049d22`
- `ole32!CoTaskMemFree` at `0x180049d89`
- `ole32!CoTaskMemFree` at `0x1800499b0`
- `ole32!CoTaskMemFree` at `0x1800499bd`
- `ole32!CoTaskMemFree` at `0x180049a72`
- `ole32!CoTaskMemFree` at `0x180049a7f`
- `ole32!CoTaskMemFree` at `0x180049c10`
- `ole32!CoTaskMemFree` at `0x180049c1d`
- `ole32!CoTaskMemFree` at `0x180049d11`
- `ole32!CoTaskMemFree` at `0x180049d22`
- `ole32!CoTaskMemFree` at `0x180049d89`
- `OLEAUT32!__imp_SysFreeString` at `0x180049992`
- `OLEAUT32!__imp_SysFreeString` at `0x180049a02`
- `OLEAUT32!__imp_SysFreeString` at `0x180049a5e`
- `OLEAUT32!__imp_SysFreeString` at `0x180049ac1`
- `OLEAUT32!__imp_SysFreeString` at `0x180049b0c`
- `OLEAUT32!__imp_SysFreeString` at `0x180049992`
- `OLEAUT32!__imp_SysFreeString` at `0x180049a02`
- `OLEAUT32!__imp_SysFreeString` at `0x180049a5e`
- `OLEAUT32!__imp_SysFreeString` at `0x180049ac1`
- `OLEAUT32!__imp_SysFreeString` at `0x180049b0c`

## string_xrefs

- `0x180049738`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\networkprotectionshield\firewallmanager.cpp`
- `0x18004976d`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\networkprotectionshield\firewallmanager.cpp`

## pseudocode

```c
__int64 __fastcall ShieldProvider::FirewallManager::GetNetworkDetails(
        ShieldProvider::FirewallManager *this,
        enum NLM_NETWORK_CATEGORY a2,
        struct tagFIREWALL_PROFILE_INFO *a3)
{
  unsigned int v3; // r12d
  int v7; // edi
  int IsProviderReady; // eax
  unsigned int v9; // ebx
  __int64 v11; // rcx
  int v12; // r14d
  __int64 v13; // rbx
  unsigned int (__fastcall *v14)(__int64, __int64, struct INetwork **); // rsi
  unsigned __int64 v15; // r8
  bool v16; // r9
  unsigned __int16 *v17; // r8
  _DWORD *v18; // rbx
  int v19; // eax
  ShieldProvider::FirewallManager *v20; // rcx
  _QWORD *v21; // rsi
  void *v22; // rcx
  __int64 v23; // rcx
  void *v24; // rcx
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  _QWORD *v28; // rbx
  unsigned __int16 *v29; // r8
  void *v30; // rcx
  __int64 v31; // rbx
  _QWORD *j; // r14
  __int64 v33; // r15
  int v34; // eax
  void *v35; // rcx
  __int64 i; // rbx
  int v37; // [rsp+20h] [rbp-50h]
  _WORD v38[2]; // [rsp+30h] [rbp-40h] BYREF
  int v39; // [rsp+34h] [rbp-3Ch] BYREF
  struct INetwork *v40; // [rsp+38h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-30h] BYREF
  __int64 v42; // [rsp+48h] [rbp-28h] BYREF
  __int128 v43; // [rsp+50h] [rbp-20h] BYREF
  __int64 v44; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  LPVOID pv; // [rsp+C0h] [rbp+50h] BYREF
  bool v47; // [rsp+C8h] [rbp+58h] BYREF

  v3 = 0;
  if ( !a3 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41F,
      (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\networkprotectionshield"
                    "\\firewallmanager.cpp",
      (const char *)0x80070057LL,
      v37);
    return (unsigned int)v7;
  }
  *((_DWORD *)a3 + 10) = 0;
  *((_QWORD *)a3 + 6) = 0;
  IsProviderReady = ShieldProvider::FirewallManager::IsProviderReady(this);
  v9 = IsProviderReady;
  if ( IsProviderReady < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x426,
      (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\networkprotectionshield"
                    "\\firewallmanager.cpp",
      (const char *)(unsigned int)IsProviderReady,
      v37);
    return v9;
  }
  v11 = *((_QWORD *)this + 16);
  v42 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v11 + 56LL))(v11, 1, &v42);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids,
        (unsigned int)v7);
    goto LABEL_89;
  }
  v40 = 0;
  v38[0] = 0;
  v12 = 0;
  v39 = 0;
  std::vector<_incompatibleDriver>::vector<_incompatibleDriver>(&v43);
  while ( 1 )
  {
    v13 = v42;
    v14 = *(unsigned int (__fastcall **)(__int64, __int64, struct INetwork **))(*(_QWORD *)v42 + 64LL);
    if ( v40 )
    {
      ((void (__fastcall *)(struct INetwork *))v40->lpVtbl->Release)(v40);
      v40 = 0;
    }
    if ( v14(v13, 1, &v40) )
      break;
    pv = 0;
    LOBYTE(v15) = 1;
    v7 = CommonUtil::UtilCoTaskMemAlloc((CommonUtil *)&pv, (void **)0x18, v15, v16);
    if ( v7 < 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v26 = 51;
LABEL_69:
        WPP_SF_d(v25[2], v26, &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids, (unsigned int)v7);
      }
LABEL_65:
      v18 = pv;
      goto LABEL_58;
    }
    v7 = ((__int64 (__fastcall *)(struct INetwork *, int *))v40->lpVtbl->GetCategory)(v40, &v39);
    if ( v7 < 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v26 = 52;
        goto LABEL_69;
      }
      goto LABEL_65;
    }
    if ( a2 != v39 )
    {
      v21 = pv;
      goto LABEL_33;
    }
    bstrString = 0;
    v7 = ((__int64 (__fastcall *)(struct INetwork *, BSTR *))v40->lpVtbl->GetName)(v40, &bstrString);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids,
          (unsigned int)v7);
      if ( bstrString )
        SysFreeString(bstrString);
      goto LABEL_65;
    }
    v18 = pv;
    CommonUtil::UtilCoDuplicateString((CommonUtil *)((char *)pv + 8), (unsigned __int16 **)bstrString, v17);
    v7 = ((__int64 (__fastcall *)(struct INetwork *, _WORD *))v40->lpVtbl->get_IsConnected)(v40, v38);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids,
          (unsigned int)v7);
      if ( bstrString )
        SysFreeString(bstrString);
LABEL_58:
      if ( v18 )
        goto LABEL_50;
      goto LABEL_42;
    }
    if ( !v12 )
    {
      if ( v38[0] != 0xFFFF )
        goto LABEL_22;
      *((_DWORD *)a3 + 4) = 1;
      v12 = 1;
    }
    v19 = 1;
    if ( v38[0] != 0xFFFF )
LABEL_22:
      v19 = 0;
    *v18 = v19;
    v7 = ((__int64 (__fastcall *)(struct INetwork *, _WORD *))v40->lpVtbl->get_IsConnectedToInternet)(v40, v38);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids,
          (unsigned int)v7);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v18 )
      {
LABEL_50:
        v24 = (void *)*((_QWORD *)v18 + 1);
        if ( v24 )
        {
          CoTaskMemFree(v24);
          *((_QWORD *)v18 + 1) = 0;
        }
      }
      CoTaskMemFree(v18);
LABEL_42:
      v23 = v43;
      if ( !(_QWORD)v43 )
        goto LABEL_88;
LABEL_86:
      std::_Deallocate<16>(v23, 8 * ((v44 - v23) >> 3));
      v44 = 0;
LABEL_87:
      v43 = 0;
      goto LABEL_88;
    }
    LOBYTE(pv) = 0;
    v47 = 0;
    v18[1] = v38[0] == 0xFFFF;
    if ( ShieldProvider::FirewallManager::GetConnectionDetails(v20, v40, (bool *)&pv, &v47) < 0 )
    {
      v18[4] = 0;
    }
    else if ( (_BYTE)pv )
    {
      v18[4] = v47 + 2;
    }
    else
    {
      v18[4] = 1;
    }
    v21 = 0;
    v7 = CommonUtil::HrStdPushBack<CommonUtil::CStdVector<tagNETWORK_PROFILE_INFO,std::allocator<tagNETWORK_PROFILE_INFO>>,tagNETWORK_PROFILE_INFO>(
           &v43,
           v18);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids,
          (unsigned int)v7);
      if ( bstrString )
        SysFreeString(bstrString);
      goto LABEL_42;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
LABEL_33:
      if ( v21 )
      {
        v22 = (void *)v21[1];
        if ( v22 )
        {
          CoTaskMemFree(v22);
          v21[1] = 0;
        }
        CoTaskMemFree(v21);
      }
    }
  }
  v27 = *((_QWORD *)&v43 + 1);
  if ( (_QWORD)v43 == *((_QWORD *)&v43 + 1) )
  {
LABEL_105:
    for ( i = v43; i != v27; i += 24 )
    {
      CoTaskMemFree(*(LPVOID *)(i + 8));
      v27 = *((_QWORD *)&v43 + 1);
    }
    goto LABEL_85;
  }
  v28 = 0;
  pv = 0;
  if ( 8 * ((__int64)(*((_QWORD *)&v43 + 1) - v43) >> 3) / 0x18uLL != 0xAAAAAAAAAAAAAAABuLL
                                                                    * ((__int64)(*((_QWORD *)&v43 + 1) - v43) >> 3) )
  {
    v7 = -2147024809;
LABEL_78:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids,
        (unsigned int)v7);
    if ( v28 )
    {
      v30 = (void *)v28[1];
      if ( v30 )
      {
        CoTaskMemFree(v30);
        v28[1] = 0;
      }
      CoTaskMemFree(v28);
    }
LABEL_85:
    v23 = v43;
    if ( !(_QWORD)v43 )
      goto LABEL_88;
    goto LABEL_86;
  }
  LOBYTE(v15) = 1;
  v7 = CommonUtil::UtilCoTaskMemAlloc(
         (CommonUtil *)&pv,
         (void **)(8 * ((__int64)(*((_QWORD *)&v43 + 1) - v43) >> 3)),
         v15,
         8 * ((__int64)(*((_QWORD *)&v43 + 1) - v43) >> 3));
  if ( v7 < 0 )
  {
    v28 = pv;
    goto LABEL_78;
  }
  v31 = v43;
  for ( j = pv; ; LODWORD(j[v33 + 2]) = v34 )
  {
    v27 = *((_QWORD *)&v43 + 1);
    if ( v31 == *((_QWORD *)&v43 + 1) )
    {
      *((_QWORD *)a3 + 6) = j;
      *((_DWORD *)a3 + 10) = -1431655765 * ((v27 - (__int64)v43) >> 3);
      goto LABEL_105;
    }
    v33 = 3LL * v3;
    v7 = CommonUtil::UtilCoDuplicateString((CommonUtil *)&j[3 * v3 + 1], *(unsigned __int16 ***)(v31 + 8), v29);
    if ( v7 < 0 )
      break;
    ++v3;
    HIDWORD(j[v33]) = *(_DWORD *)(v31 + 4);
    LODWORD(j[v33]) = *(_DWORD *)v31;
    v34 = *(_DWORD *)(v31 + 16);
    v31 += 24;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids,
      (unsigned int)v7);
  if ( j )
  {
    v35 = (void *)j[1];
    if ( v35 )
    {
      CoTaskMemFree(v35);
      j[1] = 0;
    }
    CoTaskMemFree(j);
  }
  if ( (_QWORD)v43 )
  {
    std::_Deallocate<16>(v43, 8 * ((v44 - (__int64)v43) >> 3));
    v44 = 0;
    goto LABEL_87;
  }
LABEL_88:
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v40);
LABEL_89:
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v42);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004970c  mov     [rsp-38h+arg_0], rbx
0x180049711  push    rbp
0x180049712  push    rsi
0x180049713  push    rdi
0x180049714  push    r12
0x180049716  push    r13
0x180049718  push    r14
0x18004971a  push    r15
0x18004971c  mov     rbp, rsp
0x18004971f  sub     rsp, 70h
0x180049723  xor     r12d, r12d
0x180049726  mov     r13, r8
0x180049729  mov     r15d, edx
0x18004972c  mov     rdi, rcx
0x18004972f  test    r8, r8
0x180049732  jnz     short loc_180049756
0x180049734  mov     rcx, [rbp+38h]; this
0x180049738  lea     r8, aOnecoreAmcoreA_12; "onecore\\amcore\\antimalware\\source\\s"...
0x18004973f  mov     edi, 80070057h
0x180049744  mov     edx, 41Fh; void *
0x180049749  mov     r9d, edi; char *
0x18004974c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049751  jmp     loc_180049C66
0x180049756  mov     [r8+28h], r12d
0x18004975a  mov     [r8+30h], r12
0x18004975e  call    ?IsProviderReady@FirewallManager@ShieldProvider@@AEAAJXZ; ShieldProvider::FirewallManager::IsProviderReady(void)
0x180049763  mov     ebx, eax
0x180049765  test    eax, eax
0x180049767  jns     short loc_180049788
0x180049769  mov     rcx, [rbp+38h]; this
0x18004976d  lea     r8, aOnecoreAmcoreA_12; "onecore\\amcore\\antimalware\\source\\s"...
0x180049774  mov     r9d, eax; char *
0x180049777  mov     edx, 426h; void *
0x18004977c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049781  mov     eax, ebx
0x180049783  jmp     loc_180049C68
0x180049788  mov     rcx, [rdi+80h]
0x18004978f  lea     r8, [rbp+var_28]
0x180049793  mov     [rbp+var_28], r12
0x180049797  mov     edx, 1
0x18004979c  mov     rax, [rcx]
0x18004979f  mov     rax, [rax+38h]
0x1800497a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497a8  mov     edi, eax
0x1800497aa  test    eax, eax
0x1800497ac  jns     short loc_1800497EC
0x1800497ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800497b5  lea     rax, WPP_GLOBAL_Control
0x1800497bc  cmp     rcx, rax
0x1800497bf  jz      loc_180049C5D
0x1800497c5  test    byte ptr [rcx+1Ch], 1
0x1800497c9  jz      loc_180049C5D
0x1800497cf  mov     rcx, [rcx+10h]
0x1800497d3  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x1800497da  mov     edx, 32h ; '2'
0x1800497df  mov     r9d, edi
0x1800497e2  call    WPP_SF_d
0x1800497e7  jmp     loc_180049C5D
0x1800497ec  lea     rcx, [rbp+var_20]
0x1800497f0  mov     [rbp+var_38], r12
0x1800497f4  mov     [rbp+var_40], r12w
0x1800497f9  mov     r14d, r12d
0x1800497fc  mov     [rbp+var_3C], r12d
0x180049800  call    ??0?$vector@U_incompatibleDriver@@V?$allocator@U_incompatibleDriver@@@std@@@std@@QEAA@XZ; std::vector<_incompatibleDriver>::vector<_incompatibleDriver>(void)
0x180049805  mov     rbx, [rbp+var_28]
0x180049809  mov     rcx, [rbp+var_38]
0x18004980d  mov     rax, [rbx]
0x180049810  mov     rsi, [rax+40h]
0x180049814  test    rcx, rcx
0x180049817  jz      short loc_180049829
0x180049819  mov     rdx, [rcx]
0x18004981c  mov     rax, [rdx+10h]
0x180049820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049825  mov     [rbp+var_38], r12
0x180049829  xor     r9d, r9d
0x18004982c  lea     r8, [rbp+var_38]
0x180049830  mov     rcx, rbx
0x180049833  mov     rax, rsi
0x180049836  lea     edx, [r9+1]
0x18004983a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004983f  test    eax, eax
0x180049841  jnz     loc_180049B6B
0x180049847  lea     esi, [rax+1]
0x18004984a  mov     [rbp+pv], r12
0x18004984e  mov     r8b, sil; unsigned __int64
0x180049851  lea     edx, [rax+18h]; void **
0x180049854  lea     rcx, [rbp+pv]; this
0x180049858  call    ?UtilCoTaskMemAlloc@CommonUtil@@YAJPEAPEAX_K_N@Z; CommonUtil::UtilCoTaskMemAlloc(void * *,unsigned __int64,bool)
0x18004985d  mov     edi, eax
0x18004985f  test    eax, eax
0x180049861  js      loc_180049B4B
0x180049867  mov     rcx, [rbp+var_38]
0x18004986b  lea     rdx, [rbp+var_3C]
0x18004986f  mov     rax, [rcx]
0x180049872  mov     rax, [rax+90h]
0x180049879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004987e  mov     edi, eax
0x180049880  test    eax, eax
0x180049882  js      loc_180049B18
0x180049888  cmp     r15d, [rbp+var_3C]
0x18004988c  jnz     loc_18004999A
0x180049892  mov     rcx, [rbp+var_38]
0x180049896  lea     rdx, [rbp+bstrString]
0x18004989a  mov     [rbp+bstrString], r12
0x18004989e  mov     rax, [rcx]
0x1800498a1  mov     rax, [rax+38h]
0x1800498a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498aa  mov     edi, eax
0x1800498ac  test    eax, eax
0x1800498ae  js      loc_180049AD2
0x1800498b4  mov     rbx, [rbp+pv]
0x1800498b8  mov     rdx, [rbp+bstrString]; unsigned __int16 **
0x1800498bc  lea     rcx, [rbx+8]; this
0x1800498c0  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800498c5  mov     rcx, [rbp+var_38]
0x1800498c9  lea     rdx, [rbp+var_40]
0x1800498cd  mov     rax, [rcx]
0x1800498d0  mov     rax, [rax+80h]
0x1800498d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498dc  mov     edi, eax
0x1800498de  test    eax, eax
0x1800498e0  js      loc_180049A87
0x1800498e6  test    r14d, r14d
0x1800498e9  jnz     short loc_1800498F9
0x1800498eb  cmp     [rbp+var_40], 0FFFFh
0x1800498f0  jnz     short loc_180049902
0x1800498f2  mov     [r13+10h], esi
0x1800498f6  mov     r14d, esi
0x1800498f9  cmp     [rbp+var_40], 0FFFFh
0x1800498fe  mov     eax, esi
0x180049900  jz      short loc_180049905
0x180049902  mov     eax, r12d
0x180049905  mov     [rbx], eax
0x180049907  lea     rdx, [rbp+var_40]
0x18004990b  mov     rcx, [rbp+var_38]
0x18004990f  mov     rax, [rcx]
0x180049912  mov     rax, [rax+78h]
0x180049916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004991b  mov     edi, eax
0x18004991d  test    eax, eax
0x18004991f  js      loc_180049A24
0x180049925  cmp     [rbp+var_40], 0FFFFh
0x18004992a  lea     r9, [rbp+arg_18]; bool *
0x18004992e  mov     eax, r12d
0x180049931  mov     byte ptr [rbp+pv], r12b
0x180049935  setz    al
0x180049938  mov     [rbp+arg_18], r12b
0x18004993c  mov     [rbx+4], eax
0x18004993f  lea     r8, [rbp+pv]; bool *
0x180049943  mov     rdx, [rbp+var_38]; struct INetwork *
0x180049947  call    ?GetConnectionDetails@FirewallManager@ShieldProvider@@AEAAJPEAUINetwork@@PEA_N1@Z; ShieldProvider::FirewallManager::GetConnectionDetails(INetwork *,bool *,bool *)
0x18004994c  test    eax, eax
0x18004994e  js      short loc_18004996C
0x180049950  cmp     byte ptr [rbp+pv], r12b
0x180049954  jz      short loc_180049967
0x180049956  mov     al, [rbp+arg_18]
0x180049959  neg     al
0x18004995b  sbb     ecx, ecx
0x18004995d  neg     ecx
0x18004995f  add     ecx, 2
0x180049962  mov     [rbx+10h], ecx
0x180049965  jmp     short loc_180049970
0x180049967  mov     [rbx+10h], esi
0x18004996a  jmp     short loc_180049970
0x18004996c  mov     [rbx+10h], r12d
0x180049970  mov     rdx, rbx
0x180049973  lea     rcx, [rbp+var_20]
0x180049977  mov     rsi, r12
0x18004997a  call    ??$HrStdPushBack@V?$CStdVector@UtagNETWORK_PROFILE_INFO@@V?$allocator@UtagNETWORK_PROFILE_INFO@@@std@@@CommonUtil@@UtagNETWORK_PROFILE_INFO@@@CommonUtil@@YAJAEAV?$CStdVector@UtagNETWORK_PROFILE_INFO@@V?$allocator@UtagNETWORK_PROFILE_INFO@@@std@@@0@AEBUtagNETWORK_PROFILE_INFO@@@Z; CommonUtil::HrStdPushBack<CommonUtil::CStdVector<tagNETWORK_PROFILE_INFO,std::allocator<tagNETWORK_PROFILE_INFO>>,tagNETWORK_PROFILE_INFO>(CommonUtil::CStdVector<tagNETWORK_PROFILE_INFO,std::allocator<tagNETWORK_PROFILE_INFO>> &,tagNETWORK_PROFILE_INFO const &)
0x18004997f  mov     edi, eax
0x180049981  test    eax, eax
0x180049983  js      short loc_1800499C8
0x180049985  mov     rcx, [rbp+bstrString]; bstrString
0x180049989  test    rcx, rcx
0x18004998c  jz      loc_180049805
0x180049992  call    cs:__imp_SysFreeString
0x180049998  jmp     short loc_18004999E
0x18004999a  mov     rsi, [rbp+pv]
0x18004999e  test    rsi, rsi
0x1800499a1  jz      loc_180049805
0x1800499a7  mov     rcx, [rsi+8]; pv
0x1800499ab  test    rcx, rcx
0x1800499ae  jz      short loc_1800499BA
0x1800499b0  call    cs:__imp_CoTaskMemFree
0x1800499b6  mov     [rsi+8], r12
0x1800499ba  mov     rcx, rsi; pv
0x1800499bd  call    cs:__imp_CoTaskMemFree
0x1800499c3  jmp     loc_180049805
0x1800499c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800499cf  lea     rax, WPP_GLOBAL_Control
0x1800499d6  cmp     rcx, rax
0x1800499d9  jz      short loc_1800499F9
0x1800499db  test    byte ptr [rcx+1Ch], 1
0x1800499df  jz      short loc_1800499F9
0x1800499e1  mov     rcx, [rcx+10h]
0x1800499e5  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x1800499ec  mov     edx, 39h ; '9'
0x1800499f1  mov     r9d, edi
0x1800499f4  call    WPP_SF_d
0x1800499f9  mov     rcx, [rbp+bstrString]; bstrString
0x1800499fd  test    rcx, rcx
0x180049a00  jz      short loc_180049A08
0x180049a02  call    cs:__imp_SysFreeString
0x180049a08  mov     rcx, qword ptr [rbp+var_20]
0x180049a0c  test    rcx, rcx
0x180049a0f  jz      loc_180049C54
0x180049a15  mov     rsi, 0AAAAAAAAAAAAAAABh
0x180049a1f  jmp     loc_180049C2C
0x180049a24  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a2b  lea     rax, WPP_GLOBAL_Control
0x180049a32  cmp     rcx, rax
0x180049a35  jz      short loc_180049A55
0x180049a37  test    [rcx+1Ch], sil
0x180049a3b  jz      short loc_180049A55
0x180049a3d  mov     rcx, [rcx+10h]
0x180049a41  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x180049a48  mov     edx, 38h ; '8'
0x180049a4d  mov     r9d, edi
0x180049a50  call    WPP_SF_d
0x180049a55  mov     rcx, [rbp+bstrString]; bstrString
0x180049a59  test    rcx, rcx
0x180049a5c  jz      short loc_180049A64
0x180049a5e  call    cs:__imp_SysFreeString
0x180049a64  test    rbx, rbx
0x180049a67  jz      short loc_180049A7C
0x180049a69  mov     rcx, [rbx+8]; pv
0x180049a6d  test    rcx, rcx
0x180049a70  jz      short loc_180049A7C
0x180049a72  call    cs:__imp_CoTaskMemFree
0x180049a78  mov     [rbx+8], r12
0x180049a7c  mov     rcx, rbx; pv
0x180049a7f  call    cs:__imp_CoTaskMemFree
0x180049a85  jmp     short loc_180049A08
0x180049a87  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a8e  lea     rax, WPP_GLOBAL_Control
0x180049a95  cmp     rcx, rax
0x180049a98  jz      short loc_180049AB8
0x180049a9a  test    [rcx+1Ch], sil
0x180049a9e  jz      short loc_180049AB8
0x180049aa0  mov     rcx, [rcx+10h]
0x180049aa4  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x180049aab  mov     edx, 37h ; '7'
0x180049ab0  mov     r9d, edi
0x180049ab3  call    WPP_SF_d
0x180049ab8  mov     rcx, [rbp+bstrString]; bstrString
0x180049abc  test    rcx, rcx
0x180049abf  jz      short loc_180049AC7
0x180049ac1  call    cs:__imp_SysFreeString
0x180049ac7  test    rbx, rbx
0x180049aca  jz      loc_180049A08
0x180049ad0  jmp     short loc_180049A69
0x180049ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x180049ad9  lea     rax, WPP_GLOBAL_Control
0x180049ae0  cmp     rcx, rax
0x180049ae3  jz      short loc_180049B03
0x180049ae5  test    [rcx+1Ch], sil
0x180049ae9  jz      short loc_180049B03
0x180049aeb  mov     rcx, [rcx+10h]
0x180049aef  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x180049af6  mov     edx, 35h ; '5'
0x180049afb  mov     r9d, edi
0x180049afe  call    WPP_SF_d
0x180049b03  mov     rcx, [rbp+bstrString]; bstrString
0x180049b07  test    rcx, rcx
0x180049b0a  jz      short loc_180049B12
0x180049b0c  call    cs:__imp_SysFreeString
0x180049b12  mov     rbx, [rbp+pv]
0x180049b16  jmp     short loc_180049AC7
0x180049b18  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b1f  lea     rax, WPP_GLOBAL_Control
0x180049b26  cmp     rcx, rax
0x180049b29  jz      short loc_180049B12
0x180049b2b  test    [rcx+1Ch], sil
0x180049b2f  jz      short loc_180049B12
0x180049b31  mov     edx, 34h ; '4'
0x180049b36  mov     rcx, [rcx+10h]
0x180049b3a  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x180049b41  mov     r9d, edi
0x180049b44  call    WPP_SF_d
0x180049b49  jmp     short loc_180049B12
0x180049b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b52  lea     rax, WPP_GLOBAL_Control
0x180049b59  cmp     rcx, rax
0x180049b5c  jz      short loc_180049B12
0x180049b5e  test    [rcx+1Ch], sil
0x180049b62  jz      short loc_180049B12
0x180049b64  mov     edx, 33h ; '3'
0x180049b69  jmp     short loc_180049B36
0x180049b6b  mov     rcx, qword ptr [rbp+var_20+8]
0x180049b6f  mov     rsi, 0AAAAAAAAAAAAAAABh
0x180049b79  cmp     qword ptr [rbp+var_20], rcx
0x180049b7d  jz      loc_180049D78
0x180049b83  sub     rcx, qword ptr [rbp+var_20]
0x180049b87  mov     rax, rsi
0x180049b8a  sar     rcx, 3
0x180049b8e  mov     rbx, r12
0x180049b91  imul    rcx, rsi
0x180049b95  mov     [rbp+pv], rbx
0x180049b99  lea     r9, [rcx+rcx*2]
0x180049b9d  shl     r9, 3; bool
  ... truncated ...
```
