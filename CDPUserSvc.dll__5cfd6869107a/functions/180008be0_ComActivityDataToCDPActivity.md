# ComActivityDataToCDPActivity

- ea: `0x180008be0`
- end: `0x1800096e9`
- name: `ComActivityDataToCDPActivity`
- size: `2825`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800088a0`
- `0x180023240`

## callees

- `0x180008be0`
- `0x1800097d0`
- `0x180009824`
- `0x1800098e0`
- `0x180009960`
- `0x18001e798`
- `0x18002c5a0`
- `0x180064010`

## import_xrefs

- `cdp!CDPCreateCrossPlatformAppId` at `0x180008ca5`
- `cdp!CDPCreateCrossPlatformAppId` at `0x180008ca5`
- `cdp!CDPCreateActivityInternal` at `0x1800091df`
- `cdp!CDPCreateActivityInternal` at `0x1800091df`

## string_xrefs

- `0x180009184`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000929c`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800093fd`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000946b`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800094bb`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000950c`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180009557`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180009580`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800095b0`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800095f1`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall ComActivityDataToCDPActivity(__int64 *a1, __int64 a2, std::_Ref_count_base **a3)
{
  __int64 v5; // rax
  std::_Ref_count_base *v6; // rax
  std::_Ref_count_base *v7; // rcx
  std::_Ref_count_base *v8; // r12
  int v9; // r15d
  __int64 v10; // rsi
  std::_Ref_count_base *v11; // rcx
  volatile signed __int32 *v12; // rsi
  _QWORD *v13; // rsi
  _QWORD *v14; // r14
  __int64 v15; // rax
  int v16; // eax
  volatile signed __int32 *v17; // rsi
  volatile signed __int32 *v18; // rsi
  int v19; // esi
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  void (__fastcall **v23)(std::_Ref_count_base *, GUID *, __int64 *); // rax
  int v25; // edi
  _QWORD *v26; // rax
  std::_Ref_count_base *v27; // rcx
  _QWORD *v28; // rax
  __int64 v29; // rdx
  volatile signed __int32 *v30; // rbx
  volatile signed __int32 *v31; // rbx
  volatile signed __int32 *v32; // rbx
  int v33; // eax
  unsigned int v34; // ebx
  std::_Ref_count_base *v35; // rcx
  std::_Ref_count_base *v36; // rdx
  std::_Ref_count_base *v37; // rax
  std::_Ref_count_base *v38; // rcx
  __int64 v39; // rdx
  std::_Ref_count_base *v40[2]; // [rsp+20h] [rbp-49h] BYREF
  std::_Ref_count_base *v41[2]; // [rsp+30h] [rbp-39h] BYREF
  std::_Ref_count_base *v42[2]; // [rsp+40h] [rbp-29h] BYREF
  std::_Ref_count_base *v43[2]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v44; // [rsp+60h] [rbp-9h] BYREF
  std::_Ref_count_base *v45; // [rsp+68h] [rbp-1h]
  __int64 v46; // [rsp+70h] [rbp+7h]
  std::_Ref_count_base **v47; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  _DWORD *v49; // [rsp+D8h] [rbp+6Fh]
  _DWORD *v50; // [rsp+D8h] [rbp+6Fh]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F9,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x80070057LL,
      (int)v40[0]);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FA,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x80004003LL,
      (int)v40[0]);
    return 2147500035LL;
  }
  *(_OWORD *)v40 = 0;
  if ( !a1 )
    goto LABEL_60;
  v5 = *a1;
  v43[0] = 0;
  v43[1] = (std::_Ref_count_base *)v40;
  (*(void (__fastcall **)(__int64 *, __int64, std::_Ref_count_base **))(v5 + 48))(a1, a2, v43);
  if ( v43[0] )
  {
    v28 = std::shared_ptr<ICDPActivity>::shared_ptr<ICDPActivity>(&v44, (__int64)v43[0]);
    std::shared_ptr<CDPComActivityStoreManagementControl::ActivityStoreManagementCallback>::operator=(v43[1], v28);
    v7 = v45;
    if ( !v45 )
      goto LABEL_6;
  }
  else
  {
    v6 = v43[1];
    *(_QWORD *)v43[1] = 0;
    v7 = (std::_Ref_count_base *)*((_QWORD *)v6 + 1);
    *((_QWORD *)v6 + 1) = 0;
    if ( !v7 )
      goto LABEL_6;
  }
  std::_Ref_count_base::_Decref(v7);
LABEL_6:
  if ( v40[0] )
    goto LABEL_7;
LABEL_60:
  v43[0] = 0;
  v43[1] = (std::_Ref_count_base *)v40;
  v25 = CDPCreateActivityInternal(a2, v43);
  if ( v43[0] )
  {
    v26 = std::shared_ptr<ICDPActivity>::shared_ptr<ICDPActivity>(&v44, (__int64)v43[0]);
    std::shared_ptr<CDPComActivityStoreManagementControl::ActivityStoreManagementCallback>::operator=(v43[1], v26);
    v27 = v45;
    if ( !v45 )
      goto LABEL_96;
    goto LABEL_62;
  }
  v36 = v43[1];
  *(_QWORD *)v43[1] = 0;
  v27 = (std::_Ref_count_base *)*((_QWORD *)v36 + 1);
  *((_QWORD *)v36 + 1) = 0;
  if ( v27 )
LABEL_62:
    std::_Ref_count_base::_Decref(v27);
LABEL_96:
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x305,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)v25,
      (int)v40[0]);
    if ( v40[1] )
      std::_Ref_count_base::_Decref(v40[1]);
    return (unsigned int)v25;
  }
LABEL_7:
  *(_OWORD *)v41 = 0;
  v47 = v41;
  v8 = 0;
  v46 = 0;
  *(_OWORD *)v43 = 0;
  v44 = 0;
  v45 = (std::_Ref_count_base *)v43;
  v9 = CDPCreateCrossPlatformAppId(&v44);
  v10 = v44;
  if ( v44 )
  {
    v49 = operator new(0x18u);
    *(_OWORD *)v49 = 0;
    v49[2] = 1;
    v49[3] = 1;
    *(_QWORD *)v49 = &std::_Ref_count_resource<ICDPCrossPlatformAppId *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppId>>::`vftable';
    *((_QWORD *)v49 + 2) = v10;
    v11 = v45;
    *(_QWORD *)v45 = v10;
    v12 = (volatile signed __int32 *)*((_QWORD *)v11 + 1);
    *((_QWORD *)v11 + 1) = v49;
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
  }
  else
  {
    v37 = v45;
    *(_QWORD *)v45 = 0;
    v38 = (std::_Ref_count_base *)*((_QWORD *)v37 + 1);
    *((_QWORD *)v37 + 1) = 0;
    if ( v38 )
      std::_Ref_count_base::_Decref(v38);
  }
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)v9,
      (int)v40[0]);
    if ( v43[1] )
      std::_Ref_count_base::_Decref(v43[1]);
  }
  else
  {
    v13 = *(_QWORD **)(a2 + 48);
    v14 = &v13[2 * *(unsigned int *)(a2 + 40)];
    while ( 1 )
    {
      v15 = *(_QWORD *)v43[0];
      if ( v13 == v14 )
        break;
      v16 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, _QWORD))(v15 + 64))(v43[0], *v13, v13[1]);
      v9 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4A,
          (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
          (const char *)(unsigned int)v16,
          (int)v40[0]);
        if ( v43[1] )
          std::_Ref_count_base::_Decref(v43[1]);
        goto LABEL_22;
      }
      v13 += 2;
    }
    (*(void (**)(void))(v15 + 8))();
    v8 = v43[0];
    v17 = (volatile signed __int32 *)v43[1];
    if ( v43[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    v9 = 0;
  }
LABEL_22:
  if ( v8 )
  {
    v50 = operator new(0x18u);
    *(_OWORD *)v50 = 0;
    v50[2] = 1;
    v50[3] = 1;
    *(_QWORD *)v50 = &std::_Ref_count_resource<ICDPCrossPlatformAppId *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppId>>::`vftable';
    *((_QWORD *)v50 + 2) = v8;
    v41[0] = v8;
    v18 = (volatile signed __int32 *)v41[1];
    v41[1] = (std::_Ref_count_base *)v50;
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
  }
  else
  {
    v41[0] = 0;
    v35 = v41[1];
    v41[1] = 0;
    if ( v35 )
      std::_Ref_count_base::_Decref(v35);
  }
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x309,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)v9,
      (int)v40[0]);
    if ( v41[1] )
      std::_Ref_count_base::_Decref(v41[1]);
    if ( v40[1] )
      std::_Ref_count_base::_Decref(v40[1]);
    return (unsigned int)v9;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 232LL))(
          v40[0],
          *(_QWORD *)(a2 + 56));
  if ( v19 < 0 )
  {
    v39 = 778;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 248LL))(
          v40[0],
          *(_QWORD *)(a2 + 64));
  if ( v19 < 0 )
  {
    v39 = 779;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base *))(*(_QWORD *)v40[0] + 216LL))(
          v40[0],
          v41[0]);
  if ( v19 < 0 )
  {
    v39 = 780;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v40[0] + 40LL))(v40[0], a2 + 16);
  if ( v19 < 0 )
  {
    v39 = 781;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 56LL))(
          v40[0],
          *(unsigned int *)(a2 + 32));
  if ( v19 < 0 )
  {
    v39 = 782;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 344LL))(
          v40[0],
          *(unsigned __int8 *)(a2 + 196));
  if ( v19 < 0 )
  {
    v39 = 783;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 72LL))(
          v40[0],
          *(_QWORD *)(a2 + 72));
  if ( v19 < 0 )
  {
    v39 = 784;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 88LL))(
          v40[0],
          *(_QWORD *)(a2 + 80));
  if ( v19 < 0 )
  {
    v39 = 785;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 104LL))(
          v40[0],
          *(unsigned __int8 *)(a2 + 36));
  if ( v19 < 0 )
  {
    v39 = 786;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 128LL))(
          v40[0],
          *(_QWORD *)(a2 + 104));
  if ( v19 < 0 )
  {
    v39 = 787;
LABEL_110:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)v19,
      (int)v40[0]);
    if ( v41[1] )
      std::_Ref_count_base::_Decref(v41[1]);
    if ( v40[1] )
      std::_Ref_count_base::_Decref(v40[1]);
    return (unsigned int)v19;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 144LL))(
          v40[0],
          *(_QWORD *)(a2 + 120));
  if ( v19 < 0 )
  {
    v39 = 788;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 168LL))(
          v40[0],
          *(_QWORD *)(a2 + 88));
  if ( v19 < 0 )
  {
    v39 = 789;
    goto LABEL_110;
  }
  LOBYTE(v20) = *(_DWORD *)(a2 + 96) != 0;
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v40[0] + 184LL))(v40[0], v20);
  if ( v19 < 0 )
  {
    v39 = 790;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 232LL))(
          v40[0],
          *(_QWORD *)(a2 + 56));
  if ( v19 < 0 )
  {
    v39 = 791;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 264LL))(
          v40[0],
          *(_QWORD *)(a2 + 160));
  if ( v19 < 0 )
  {
    v39 = 792;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 280LL))(
          v40[0],
          *(_QWORD *)(a2 + 168));
  if ( v19 < 0 )
  {
    v39 = 793;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 296LL))(
          v40[0],
          *(_QWORD *)(a2 + 176));
  if ( v19 < 0 )
  {
    v39 = 794;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 360LL))(
          v40[0],
          *(_QWORD *)(a2 + 200));
  if ( v19 < 0 )
  {
    v39 = 795;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 376LL))(
          v40[0],
          *(_QWORD *)(a2 + 208));
  if ( v19 < 0 )
  {
    v39 = 796;
    goto LABEL_110;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 392LL))(
          v40[0],
          *(unsigned __int8 *)(a2 + 216));
  if ( v19 < 0 )
  {
    v39 = 797;
    goto LABEL_110;
  }
  LOBYTE(v21) = *(_DWORD *)(a2 + 220) != 0;
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v40[0] + 408LL))(v40[0], v21);
  if ( v19 < 0 )
  {
    v39 = 798;
    goto LABEL_110;
  }
  LOBYTE(v22) = *(_DWORD *)(a2 + 100) != 0;
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v40[0] + 328LL))(v40[0], v22);
  if ( v19 < 0 )
  {
    v39 = 801;
    goto LABEL_110;
  }
  *(_OWORD *)v42 = 0;
  if ( v40[0] )
  {
    v23 = *(void (__fastcall ***)(std::_Ref_count_base *, GUID *, __int64 *))v40[0];
    v44 = 0;
    v45 = (std::_Ref_count_base *)v42;
    (*v23)(v40[0], &IID_ICDPActivityInternal, &v44);
    cdp::detail::address_of<ICDPActivityInternal>::~address_of<ICDPActivityInternal>(&v44);
  }
  if ( !v42[0] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x324,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x80004002LL,
      (int)v40[0]);
    if ( v42[1] )
      std::_Ref_count_base::_Decref(v42[1]);
    if ( v41[1] )
      std::_Ref_count_base::_Decref(v41[1]);
    if ( v40[1] )
      std::_Ref_count_base::_Decref(v40[1]);
    return 2147500034LL;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v42[0] + 24LL))(
          v42[0],
          *(_QWORD *)(a2 + 128));
  if ( v19 < 0 )
  {
    v29 = 811;
LABEL_68:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)v19,
      (int)v40[0]);
    v30 = (volatile signed __int32 *)v42[1];
    if ( v42[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v42[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
        if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
      }
    }
    v31 = (volatile signed __int32 *)v41[1];
    if ( v41[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
        if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
      }
    }
    v32 = (volatile signed __int32 *)v40[1];
    if ( v40[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v40[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
      }
    }
    return (unsigned int)v19;
  }
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v42[0] + 32LL))(
          v42[0],
          *(_QWORD *)(a2 + 184));
  if ( v19 < 0 )
  {
    v29 = 812;
    goto LABEL_68;
  }
  v33 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v40[0] + 424LL))(
          v40[0],
          *(_QWORD *)(a2 + 224));
  v34 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32E,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)v33,
      (int)v40[0]);
    if ( v42[1] )
      std::_Ref_count_base::_Decref(v42[1]);
    if ( v41[1] )
      std::_Ref_count_base::_Decref(v41[1]);
    if ( v40[1] )
      std::_Ref_count_base::_Decref(v40[1]);
    return v34;
  }
  else
  {
    (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v40[0] + 8LL))(v40[0]);
    *a3 = v40[0];
    if ( v42[1] )
      std::_Ref_count_base::_Decref(v42[1]);
    if ( v41[1] )
      std::_Ref_count_base::_Decref(v41[1]);
    if ( v40[1] )
      std::_Ref_count_base::_Decref(v40[1]);
    return 0;
  }
}

```

## disassembly

```asm
0x180008be0  push    rbp
0x180008be2  push    rbx
0x180008be3  push    rsi
0x180008be4  push    rdi
0x180008be5  push    r12
0x180008be7  push    r13
0x180008be9  push    r14
0x180008beb  push    r15
0x180008bed  lea     rbp, [rsp-1Fh]
0x180008bf2  sub     rsp, 88h
0x180008bf9  mov     r13, r8
0x180008bfc  mov     rbx, rdx
0x180008bff  xor     r14d, r14d
0x180008c02  mov     dword ptr [rbp+57h+arg_8], r14d
0x180008c06  test    rdx, rdx
0x180008c09  jz      loc_18000954D
0x180008c0f  test    r8, r8
0x180008c12  jz      loc_1800095E7
0x180008c18  xorps   xmm0, xmm0
0x180008c1b  movdqu  xmmword ptr [rbp+57h+var_A0], xmm0
0x180008c20  test    rcx, rcx
0x180008c23  jz      loc_1800091CC
0x180008c29  mov     rax, [rcx]
0x180008c2c  mov     [rbp+57h+var_70], r14
0x180008c30  lea     rdx, [rbp+57h+var_A0]
0x180008c34  mov     [rbp+57h+var_70+8], rdx
0x180008c38  lea     r8, [rbp+57h+var_70]
0x180008c3c  mov     rdx, rbx
0x180008c3f  mov     rax, [rax+30h]
0x180008c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c48  nop
0x180008c49  mov     rdx, [rbp+57h+var_70]
0x180008c4d  test    rdx, rdx
0x180008c50  jnz     loc_180009225
0x180008c56  mov     rax, [rbp+57h+var_70+8]
0x180008c5a  mov     [rax], r14
0x180008c5d  mov     rcx, [rax+8]
0x180008c61  mov     [rax+8], r14
0x180008c65  test    rcx, rcx
0x180008c68  jnz     loc_18000924C
0x180008c6e  cmp     [rbp+57h+var_A0], 0
0x180008c73  jz      loc_1800091CC
0x180008c79  xorps   xmm0, xmm0
0x180008c7c  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180008c81  lea     rax, [rbp+57h+var_90]
0x180008c85  mov     [rbp+57h+var_48], rax
0x180008c89  mov     r12, r14
0x180008c8c  mov     [rbp+57h+var_50], r14
0x180008c90  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180008c95  mov     [rbp+57h+var_60], r14
0x180008c99  lea     rax, [rbp+57h+var_70]
0x180008c9d  mov     [rbp+57h+var_58], rax
0x180008ca1  lea     rcx, [rbp+57h+var_60]
0x180008ca5  call    cs:__imp_CDPCreateCrossPlatformAppId
0x180008cab  mov     r15d, eax
0x180008cae  mov     edi, 0FFFFFFFFh
0x180008cb3  mov     rsi, [rbp+57h+var_60]
0x180008cb7  test    rsi, rsi
0x180008cba  jz      loc_180009492
0x180008cc0  mov     ecx, 18h; Size
0x180008cc5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008cca  mov     [rbp+57h+arg_8], rax
0x180008cce  xorps   xmm0, xmm0
0x180008cd1  movups  xmmword ptr [rax], xmm0
0x180008cd4  mov     dword ptr [rax+8], 1
0x180008cdb  mov     dword ptr [rax+0Ch], 1
0x180008ce2  lea     rcx, ??_7?$_Ref_count_resource@PEAVICDPCrossPlatformAppId@@U?$iunknown_deleter@VICDPCrossPlatformAppId@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<ICDPCrossPlatformAppId *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppId>>::`vftable'
0x180008ce9  mov     [rax], rcx
0x180008cec  mov     [rax+10h], rsi
0x180008cf0  mov     rcx, [rbp+57h+var_58]
0x180008cf4  mov     [rcx], rsi
0x180008cf7  mov     rsi, [rcx+8]
0x180008cfb  mov     [rcx+8], rax
0x180008cff  test    rsi, rsi
0x180008d02  jz      short loc_180008D2E
0x180008d04  mov     eax, edi
0x180008d06  lock xadd [rsi+8], eax
0x180008d0b  cmp     eax, 1
0x180008d0e  jnz     short loc_180008D2E
0x180008d10  mov     rax, [rsi]
0x180008d13  mov     rcx, rsi
0x180008d16  mov     rax, [rax]
0x180008d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d1e  mov     eax, edi
0x180008d20  lock xadd [rsi+0Ch], eax
0x180008d25  cmp     eax, 1
0x180008d28  jz      loc_18000960C
0x180008d2e  test    r15d, r15d
0x180008d31  js      loc_180009579
0x180008d37  mov     rsi, [rbx+30h]
0x180008d3b  mov     r14d, [rbx+28h]
0x180008d3f  shl     r14, 4
0x180008d43  add     r14, rsi
0x180008d46  mov     rcx, [rbp+57h+var_70]
0x180008d4a  mov     rax, [rcx]
0x180008d4d  cmp     rsi, r14
0x180008d50  jz      short loc_180008D73
0x180008d52  mov     r8, [rsi+8]
0x180008d56  mov     rdx, [rsi]
0x180008d59  mov     rax, [rax+40h]
0x180008d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d62  mov     r15d, eax
0x180008d65  test    eax, eax
0x180008d67  js      loc_1800093F6
0x180008d6d  add     rsi, 10h
0x180008d71  jmp     short loc_180008D46
0x180008d73  mov     rax, [rax+8]
0x180008d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d7c  mov     r12, [rbp+57h+var_70]
0x180008d80  mov     rsi, [rbp+57h+var_70+8]
0x180008d84  test    rsi, rsi
0x180008d87  jz      short loc_180008DBE
0x180008d89  mov     eax, edi
0x180008d8b  lock xadd [rsi+8], eax
0x180008d90  cmp     eax, 1
0x180008d93  jnz     short loc_180008DBE
0x180008d95  mov     rax, [rsi]
0x180008d98  mov     rcx, rsi
0x180008d9b  mov     rax, [rax]
0x180008d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008da3  mov     eax, edi
0x180008da5  lock xadd [rsi+0Ch], eax
0x180008daa  cmp     eax, 1
0x180008dad  jnz     short loc_180008DBE
0x180008daf  mov     rax, [rsi]
0x180008db2  mov     rcx, rsi
0x180008db5  mov     rax, [rax+8]
0x180008db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dbe  xor     r14d, r14d
0x180008dc1  mov     r15d, r14d
0x180008dc4  test    r12, r12
0x180008dc7  jz      loc_180009425
0x180008dcd  mov     ecx, 18h; Size
0x180008dd2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008dd7  mov     [rbp+57h+arg_8], rax
0x180008ddb  xorps   xmm0, xmm0
0x180008dde  movups  xmmword ptr [rax], xmm0
0x180008de1  mov     dword ptr [rax+8], 1
0x180008de8  mov     dword ptr [rax+0Ch], 1
0x180008def  lea     rcx, ??_7?$_Ref_count_resource@PEAVICDPCrossPlatformAppId@@U?$iunknown_deleter@VICDPCrossPlatformAppId@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<ICDPCrossPlatformAppId *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppId>>::`vftable'
0x180008df6  mov     [rax], rcx
0x180008df9  mov     [rax+10h], r12
0x180008dfd  mov     [rbp+57h+var_90], r12
0x180008e01  mov     rsi, [rbp+57h+var_90+8]
0x180008e05  mov     [rbp+57h+var_90+8], rax
0x180008e09  test    rsi, rsi
0x180008e0c  jz      short loc_180008E38
0x180008e0e  mov     eax, edi
0x180008e10  lock xadd [rsi+8], eax
0x180008e15  cmp     eax, 1
0x180008e18  jnz     short loc_180008E38
0x180008e1a  mov     rax, [rsi]
0x180008e1d  mov     rcx, rsi
0x180008e20  mov     rax, [rax]
0x180008e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e28  mov     eax, edi
0x180008e2a  lock xadd [rsi+0Ch], eax
0x180008e2f  cmp     eax, 1
0x180008e32  jz      loc_180009620
0x180008e38  test    r15d, r15d
0x180008e3b  js      loc_1800095A9
0x180008e41  mov     rcx, [rbp+57h+var_A0]
0x180008e45  mov     rax, [rcx]
0x180008e48  mov     rdx, [rbx+38h]
0x180008e4c  mov     rax, [rax+0E8h]
0x180008e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e58  mov     esi, eax
0x180008e5a  test    eax, eax
0x180008e5c  js      loc_180009634
0x180008e62  mov     rcx, [rbp+57h+var_A0]
0x180008e66  mov     rax, [rcx]
0x180008e69  mov     rdx, [rbx+40h]
0x180008e6d  mov     rax, [rax+0F8h]
0x180008e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e79  mov     esi, eax
0x180008e7b  test    eax, eax
0x180008e7d  js      loc_18000963E
0x180008e83  mov     rcx, [rbp+57h+var_A0]
0x180008e87  mov     rax, [rcx]
0x180008e8a  mov     rdx, [rbp+57h+var_90]
0x180008e8e  mov     rax, [rax+0D8h]
0x180008e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e9a  mov     esi, eax
0x180008e9c  test    eax, eax
0x180008e9e  js      loc_18000953F
0x180008ea4  mov     rcx, [rbp+57h+var_A0]
0x180008ea8  mov     rax, [rcx]
0x180008eab  lea     rdx, [rbx+10h]
0x180008eaf  mov     rax, [rax+28h]
0x180008eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eb8  mov     esi, eax
0x180008eba  test    eax, eax
0x180008ebc  js      loc_180009648
0x180008ec2  mov     rcx, [rbp+57h+var_A0]
0x180008ec6  mov     rax, [rcx]
0x180008ec9  mov     edx, [rbx+20h]
0x180008ecc  mov     rax, [rax+38h]
0x180008ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ed5  mov     esi, eax
0x180008ed7  test    eax, eax
0x180008ed9  js      loc_180009652
0x180008edf  mov     rcx, [rbp+57h+var_A0]
0x180008ee3  mov     rax, [rcx]
0x180008ee6  movzx   edx, byte ptr [rbx+0C4h]
0x180008eed  mov     rax, [rax+158h]
0x180008ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef9  mov     esi, eax
0x180008efb  test    eax, eax
0x180008efd  js      loc_18000965C
0x180008f03  mov     rcx, [rbp+57h+var_A0]
0x180008f07  mov     rax, [rcx]
0x180008f0a  mov     rdx, [rbx+48h]
0x180008f0e  mov     rax, [rax+48h]
0x180008f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f17  mov     esi, eax
0x180008f19  test    eax, eax
0x180008f1b  js      loc_180009666
0x180008f21  mov     rcx, [rbp+57h+var_A0]
0x180008f25  mov     rax, [rcx]
0x180008f28  mov     rdx, [rbx+50h]
0x180008f2c  mov     rax, [rax+58h]
0x180008f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f35  mov     esi, eax
0x180008f37  test    eax, eax
0x180008f39  js      loc_180009546
0x180008f3f  mov     rcx, [rbp+57h+var_A0]
0x180008f43  mov     rax, [rcx]
0x180008f46  movzx   edx, byte ptr [rbx+24h]
0x180008f4a  mov     rax, [rax+68h]
0x180008f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f53  mov     esi, eax
0x180008f55  test    eax, eax
0x180008f57  js      loc_180009670
0x180008f5d  mov     rcx, [rbp+57h+var_A0]
0x180008f61  mov     rax, [rcx]
0x180008f64  mov     rdx, [rbx+68h]
0x180008f68  mov     rax, [rax+80h]
0x180008f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f74  mov     esi, eax
0x180008f76  test    eax, eax
0x180008f78  js      loc_180009500
0x180008f7e  mov     rcx, [rbp+57h+var_A0]
0x180008f82  mov     rax, [rcx]
0x180008f85  mov     rdx, [rbx+78h]
0x180008f89  mov     rax, [rax+90h]
0x180008f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f95  mov     esi, eax
0x180008f97  test    eax, eax
0x180008f99  js      loc_18000967A
0x180008f9f  mov     rcx, [rbp+57h+var_A0]
0x180008fa3  mov     rax, [rcx]
0x180008fa6  mov     rdx, [rbx+58h]
0x180008faa  mov     rax, [rax+0A8h]
0x180008fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fb6  mov     esi, eax
0x180008fb8  test    eax, eax
0x180008fba  js      loc_180009684
0x180008fc0  mov     rcx, [rbp+57h+var_A0]
0x180008fc4  mov     rax, [rcx]
0x180008fc7  cmp     dword ptr [rbx+60h], 0
0x180008fcb  setnz   dl
0x180008fce  mov     rax, [rax+0B8h]
0x180008fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fda  mov     esi, eax
0x180008fdc  test    eax, eax
0x180008fde  js      loc_18000968E
0x180008fe4  mov     rcx, [rbp+57h+var_A0]
0x180008fe8  mov     rax, [rcx]
0x180008feb  mov     rdx, [rbx+38h]
0x180008fef  mov     rax, [rax+0E8h]
0x180008ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ffb  mov     esi, eax
0x180008ffd  test    eax, eax
0x180008fff  js      loc_180009698
0x180009005  mov     rcx, [rbp+57h+var_A0]
0x180009009  mov     rax, [rcx]
0x18000900c  mov     rdx, [rbx+0A0h]
0x180009013  mov     rax, [rax+108h]
0x18000901a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000901f  mov     esi, eax
0x180009021  test    eax, eax
0x180009023  js      loc_1800096A2
0x180009029  mov     rcx, [rbp+57h+var_A0]
0x18000902d  mov     rax, [rcx]
0x180009030  mov     rdx, [rbx+0A8h]
0x180009037  mov     rax, [rax+118h]
0x18000903e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009043  mov     esi, eax
0x180009045  test    eax, eax
0x180009047  js      loc_1800096AC
0x18000904d  mov     rcx, [rbp+57h+var_A0]
0x180009051  mov     rax, [rcx]
0x180009054  mov     rdx, [rbx+0B0h]
0x18000905b  mov     rax, [rax+128h]
0x180009062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009067  mov     esi, eax
0x180009069  test    eax, eax
0x18000906b  js      loc_1800096B6
0x180009071  mov     rcx, [rbp+57h+var_A0]
0x180009075  mov     rax, [rcx]
  ... truncated ...
```
