# AllowApplication(HWND__ *,winrt::hstring const &,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes,bool,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes)

- ea: `0x180026784`
- end: `0x180027260`
- name: `?AllowApplication@@YAJPEAUHWND__@@AEBUhstring@winrt@@W4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@3@2_N2@Z`
- size: `2780`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, int, char, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001cdc0`

## callees

- `0x1800021c0`
- `0x180002d9d`
- `0x180009544`
- `0x18000b24c`
- `0x18000b5f0`
- `0x180022944`
- `0x180026784`
- `0x180027268`
- `0x180028918`
- `0x180028f60`
- `0x18002d010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180026aea`
- `OLEAUT32!__imp_VariantInit` at `0x180026aea`
- `OLEAUT32!__imp_VariantClear` at `0x180026b4d`
- `OLEAUT32!__imp_VariantClear` at `0x180026d63`
- `OLEAUT32!__imp_VariantClear` at `0x180026e46`
- `OLEAUT32!__imp_VariantClear` at `0x180026f20`
- `OLEAUT32!__imp_VariantClear` at `0x180026fd6`
- `OLEAUT32!__imp_VariantClear` at `0x1800270ca`
- `OLEAUT32!__imp_VariantClear` at `0x1800271b0`
- `OLEAUT32!__imp_VariantClear` at `0x1800271c3`
- `OLEAUT32!__imp_VariantClear` at `0x180026b4d`
- `OLEAUT32!__imp_VariantClear` at `0x180026d63`
- `OLEAUT32!__imp_VariantClear` at `0x180026e46`
- `OLEAUT32!__imp_VariantClear` at `0x180026f20`
- `OLEAUT32!__imp_VariantClear` at `0x180026fd6`
- `OLEAUT32!__imp_VariantClear` at `0x1800270ca`
- `OLEAUT32!__imp_VariantClear` at `0x1800271b0`
- `OLEAUT32!__imp_VariantClear` at `0x1800271c3`

## string_xrefs

- `0x180026897`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x1800268f7`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x180026960`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x1800269d8`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x180026a68`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x180026b33`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x180026c15`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x180026d1b`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x180026e12`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x180026eec`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x180026fa2`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x18002707e`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x180027165`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`

## pseudocode

```c
__int64 __fastcall AllowApplication(__int64 a1, __int64 a2, unsigned int a3, int a4, char a5, int a6)
{
  __int64 result; // rax
  unsigned int CurrentFwConfig; // esi
  HRESULT v11; // eax
  LPVOID v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // edi
  int v18; // eax
  unsigned int v19; // edi
  int v20; // eax
  unsigned int v21; // edi
  int v22; // eax
  unsigned int v23; // edi
  int v24; // eax
  unsigned int v25; // edi
  int v26; // eax
  int v27; // r8d
  __int64 v28; // rdi
  int v29; // eax
  unsigned int v30; // esi
  int v31; // eax
  unsigned int v32; // edi
  __int64 (__fastcall *v33)(_QWORD, _QWORD); // rax
  int v34; // eax
  unsigned int v35; // edi
  int v36; // eax
  unsigned int v37; // edi
  int v38; // eax
  unsigned int v39; // edi
  int v40; // eax
  int ppv; // [rsp+20h] [rbp-108h]
  __int64 v42; // [rsp+50h] [rbp-D8h] BYREF
  _BYTE v43[8]; // [rsp+58h] [rbp-D0h] BYREF
  __int64 v44; // [rsp+60h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v45)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+70h] [rbp-B8h] BYREF
  LPVOID v47; // [rsp+78h] [rbp-B0h] BYREF
  unsigned int v48; // [rsp+80h] [rbp-A8h] BYREF
  LPVOID v49; // [rsp+88h] [rbp-A0h] BYREF
  __int64 v50; // [rsp+90h] [rbp-98h] BYREF
  int v51; // [rsp+98h] [rbp-90h] BYREF
  unsigned int v52; // [rsp+9Ch] [rbp-8Ch]
  VARIANTARG pvarg; // [rsp+A0h] [rbp-88h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-70h]
  IID rclsid; // [rsp+C0h] [rbp-68h] BYREF
  _DWORD v56[4]; // [rsp+D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v54 = a2;
  if ( !a3 )
    return 2147942487LL;
  try
  {
    CurrentFwConfig = GetCurrentFwConfig();
    v52 = CurrentFwConfig;
    v56[0] = -450442504;
    v56[1] = 1078407108;
    v56[2] = -1021467751;
    v56[3] = -106233320;
    rclsid = CLSID_MultiObjectElevationFactory;
    v49 = 0;
    *(_DWORD *)&pvarg.vt = 0;
    *(_OWORD *)&pvarg.decVal.Lo32 = 0;
    v11 = CoCreateInstance_0(&rclsid, 0, 1u, &winrt::impl::guid_v<IMultiObjectElevationFactory>, &v49);
    if ( v11 < 0 )
      winrt::throw_hresult((unsigned int)v11, &pvarg);
    v12 = v49;
    v47 = v49;
    v13 = (*(__int64 (__fastcall **)(LPVOID, __int64, _DWORD *))(*(_QWORD *)v49 + 24LL))(v49, a1, v56);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
        (const char *)(unsigned int)v13,
        ppv);
      if ( v12 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v47);
      return v14;
    }
    v42 = 0;
    v16 = (*(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v12 + 40LL))(
            v12,
            &GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd,
            &GUID_98325047_c671_4174_8d81_defcd3f03186,
            &v42);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
        (const char *)(unsigned int)v16,
        ppv);
      if ( v42 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v42);
      if ( v12 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v47);
      return v17;
    }
    v44 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 144LL))(v42, &v44);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
        (const char *)(unsigned int)v18,
        ppv);
      if ( v44 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v44);
      if ( v42 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v42);
      if ( v12 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v47);
      return v19;
    }
    v45 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v44 + 88LL))(
            v44,
            &v45);
    v21 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
        (const char *)(unsigned int)v20,
        ppv);
      if ( v45 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v45);
      if ( v44 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v44);
      if ( v42 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v42);
      if ( v12 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v47);
      return v21;
    }
    v46 = 0;
    v22 = (**v45)(v45, &IID_IEnumVARIANT, &v46);
    v23 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAE,
        (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
        (const char *)(unsigned int)v22,
        ppv);
      if ( v46 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v46);
      if ( v45 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v45);
      if ( v44 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v44);
      if ( v42 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v42);
      if ( v12 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v47);
      return v23;
    }
    while ( 1 )
    {
      VariantInit(&pvarg);
      v51 = 0;
      v24 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *, int *))(*(_QWORD *)v46 + 24LL))(
              v46,
              1,
              &pvarg,
              &v51);
      v25 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB6,
          (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
          (const char *)(unsigned int)v24,
          ppv);
        VariantClear(&pvarg);
        if ( v46 )
          winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v46);
        if ( v45 )
          winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v45);
        if ( v44 )
          winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v44);
        if ( v42 )
          winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v42);
        if ( v12 )
          winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v47);
        return v25;
      }
      if ( v24 == 1 || v51 != 1 || pvarg.vt != 9 )
      {
        VariantClear(&pvarg);
        if ( v46 )
          winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v46);
        if ( v45 )
          winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v45);
        if ( v44 )
          winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v44);
        if ( v42 )
          winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v42);
        if ( v12 )
          winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v47);
        return 0;
      }
      *(_QWORD *)&rclsid.Data1 = 0;
      v26 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, IID *))pvarg.llVal)(
              pvarg.llVal,
              &GUID_af230d27_baba_4e42_aced_f524f22cfce2,
              &rclsid);
      if ( v26 >= 0 )
      {
        if ( !*(_QWORD *)&rclsid.Data1 )
          goto LABEL_153;
        v48 = 0;
        LODWORD(v50) = 0;
        v43[0] = 0;
        if ( (int)CheckIfRuleNeedsUpdate(*(__int64 *)&rclsid.Data1, v54, a3, a5, a6, a4, v43, &v48, (int *)&v50) >= 0
          && v43[0] )
        {
          if ( a5 )
          {
            v27 = v50;
            if ( (_DWORD)v50 == a6 )
              v27 = 0;
          }
          else
          {
            v27 = a4;
          }
          if ( (CurrentFwConfig & v27) != 0 )
          {
            v50 = 0;
            v28 = CopyRule(v12, *(_QWORD *)&rclsid.Data1);
            v50 = v28;
            v29 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 64LL))(v44, v28);
            v30 = v29;
            if ( v29 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x102,
                (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
                (const char *)(unsigned int)v29,
                ppv);
              if ( v28 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v50);
              if ( *(_QWORD *)&rclsid.Data1 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&rclsid);
              VariantClear(&pvarg);
              if ( v46 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v46);
              if ( v45 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v45);
              if ( v44 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v44);
              if ( v42 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v42);
              if ( v12 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v47);
              return v30;
            }
            if ( v28 )
              winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v50);
            CurrentFwConfig = v52;
          }
          v31 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&rclsid.Data1 + 336LL))(
                  *(_QWORD *)&rclsid.Data1,
                  1);
          v32 = v31;
          if ( v31 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x107,
              (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
              (const char *)(unsigned int)v31,
              ppv);
            if ( *(_QWORD *)&rclsid.Data1 )
              winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&rclsid);
            VariantClear(&pvarg);
            if ( v46 )
              winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v46);
            if ( v45 )
              winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v45);
            if ( v44 )
              winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v44);
            if ( v42 )
              winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v42);
            if ( v12 )
              winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v47);
            return v32;
          }
          v33 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)&rclsid.Data1 + 304LL);
          if ( a5 )
          {
            v34 = v33(*(_QWORD *)&rclsid.Data1, v48);
            v35 = v34;
            if ( v34 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x10B,
                (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
                (const char *)(unsigned int)v34,
                ppv);
              if ( *(_QWORD *)&rclsid.Data1 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&rclsid);
              VariantClear(&pvarg);
              if ( v46 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v46);
              if ( v45 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v45);
              if ( v44 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v44);
              if ( v42 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v42);
              if ( v12 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v47);
              return v35;
            }
          }
          else
          {
            v36 = v33(*(_QWORD *)&rclsid.Data1, a3);
            v37 = v36;
            if ( v36 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x10F,
                (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
                (const char *)(unsigned int)v36,
                ppv);
              if ( *(_QWORD *)&rclsid.Data1 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&rclsid);
              VariantClear(&pvarg);
              if ( v46 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v46);
              if ( v45 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v45);
              if ( v44 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v44);
              if ( v42 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v42);
              if ( v12 )
                winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v47);
              return v37;
            }
          }
          v49 = 0;
          v38 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, LPVOID *))&rclsid.Data1)(
                  *(_QWORD *)&rclsid.Data1,
                  &GUID_9c27c8da_189b_4dde_89f7_8b39a316782c,
                  &v49);
          v39 = v38;
          if ( v38 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x113,
              (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
              (const char *)(unsigned int)v38,
              ppv);
            if ( v49 )
              winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v49);
            if ( *(_QWORD *)&rclsid.Data1 )
              winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&rclsid);
            VariantClear(&pvarg);
            if ( v46 )
              winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v46);
            if ( v45 )
              winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v45);
            if ( v44 )
              winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v44);
            if ( v42 )
              winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v42);
            if ( v12 )
              winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v47);
            return v39;
          }
          v40 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v49 + 352LL))(
                  v49,
                  ((unsigned __int8)a5 ^ 1u) + 2);
          if ( v40 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x116,
              (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
              (const char *)(unsigned int)v40,
              ppv);
          if ( v49 )
            winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v49);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBE,
          (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
          (const char *)(unsigned int)v26,
          ppv);
      }
      if ( *(_QWORD *)&rclsid.Data1 )
        winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&rclsid);
LABEL_153:
      VariantClear(&pvarg);
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x11A,
                           (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x180026784  push    rbx
0x180026786  push    rsi
0x180026787  push    rdi
0x180026788  push    r12
0x18002678a  push    r13
0x18002678c  push    r14
0x18002678e  sub     rsp, 0F8h
0x180026795  mov     rax, cs:__security_cookie
0x18002679c  xor     rax, rsp
0x18002679f  mov     [rsp+128h+var_48], rax
0x1800267a7  mov     r13d, r9d
0x1800267aa  mov     r12d, r8d
0x1800267ad  mov     [rsp+128h+var_70], rdx
0x1800267b5  mov     rdi, rcx
0x1800267b8  xor     r14d, r14d
0x1800267bb  test    r8d, r8d
0x1800267be  jnz     short loc_1800267CA
0x1800267c0  mov     eax, 80070057h
0x1800267c5  jmp     loc_18002722E
0x1800267ca  call    ?GetCurrentFwConfig@@YAKXZ; GetCurrentFwConfig(void)
0x1800267cf  mov     esi, eax
0x1800267d1  mov     [rsp+128h+var_8C], eax
0x1800267d8  mov     [rsp+128h+var_58], 0E526CAF8h
0x1800267e3  mov     [rsp+128h+var_54], 40472FC4h
0x1800267ee  mov     [rsp+128h+var_50], 0C31DA399h
0x1800267f9  mov     [rsp+128h+var_4C], 0F9AB0218h
0x180026804  movups  xmm0, xmmword ptr cs:CLSID_MultiObjectElevationFactory.Data1
0x18002680b  movdqu  xmmword ptr [rsp+128h+rclsid.Data1], xmm0
0x180026814  mov     [rsp+128h+var_A0], r14
0x18002681c  mov     dword ptr [rsp+128h+pvarg], r14d
0x180026824  xorps   xmm0, xmm0
0x180026827  movdqu  xmmword ptr [rsp+128h+pvarg+8], xmm0
0x180026830  lea     rax, [rsp+128h+var_A0]
0x180026838  mov     [rsp+128h+ppv], rax; int
0x18002683d  lea     r9, ??$guid_v@UIMultiObjectElevationFactory@@@impl@winrt@@3Uguid@2@B; riid
0x180026844  xor     edx, edx; pUnkOuter
0x180026846  lea     r8d, [rdx+1]; dwClsContext
0x18002684a  lea     rcx, [rsp+128h+rclsid]; rclsid
0x180026852  call    CoCreateInstance_0
0x180026857  test    eax, eax
0x180026859  js      loc_18002724F
0x18002685f  mov     rbx, [rsp+128h+var_A0]
0x180026867  mov     [rsp+128h+var_B0], rbx
0x18002686c  mov     rax, [rbx]
0x18002686f  lea     r8, [rsp+128h+var_58]
0x180026877  mov     rdx, rdi
0x18002687a  mov     rcx, rbx
0x18002687d  mov     rax, [rax+18h]
0x180026881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026886  mov     edi, eax
0x180026888  test    eax, eax
0x18002688a  jns     short loc_1800268BF
0x18002688c  mov     rcx, [rsp+128h]; this
0x180026894  mov     r9d, eax; char *
0x180026897  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x18002689e  mov     edx, 0A1h; void *
0x1800268a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800268a8  nop
0x1800268a9  test    rbx, rbx
0x1800268ac  jz      short loc_1800268B8
0x1800268ae  lea     rcx, [rsp+128h+var_B0]
0x1800268b3  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x1800268b8  mov     eax, edi
0x1800268ba  jmp     loc_18002722E
0x1800268bf  mov     [rsp+128h+var_D8], r14
0x1800268c4  mov     rax, [rbx]
0x1800268c7  lea     r9, [rsp+128h+var_D8]
0x1800268cc  lea     r8, _GUID_98325047_c671_4174_8d81_defcd3f03186
0x1800268d3  lea     rdx, _GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd
0x1800268da  mov     rcx, rbx
0x1800268dd  mov     rax, [rax+28h]
0x1800268e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268e6  mov     edi, eax
0x1800268e8  test    eax, eax
0x1800268ea  jns     short loc_180026931
0x1800268ec  mov     rcx, [rsp+128h]; this
0x1800268f4  mov     r9d, eax; char *
0x1800268f7  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x1800268fe  mov     edx, 0A5h; void *
0x180026903  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026908  nop
0x180026909  cmp     [rsp+128h+var_D8], r14
0x18002690e  jz      short loc_18002691B
0x180026910  lea     rcx, [rsp+128h+var_D8]
0x180026915  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x18002691a  nop
0x18002691b  test    rbx, rbx
0x18002691e  jz      short loc_18002692A
0x180026920  lea     rcx, [rsp+128h+var_B0]
0x180026925  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x18002692a  mov     eax, edi
0x18002692c  jmp     loc_18002722E
0x180026931  mov     [rsp+128h+var_C8], r14
0x180026936  mov     rcx, [rsp+128h+var_D8]
0x18002693b  mov     rax, [rcx]
0x18002693e  lea     rdx, [rsp+128h+var_C8]
0x180026943  mov     rax, [rax+90h]
0x18002694a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002694f  mov     edi, eax
0x180026951  test    eax, eax
0x180026953  jns     short loc_1800269AC
0x180026955  mov     rcx, [rsp+128h]; this
0x18002695d  mov     r9d, eax; char *
0x180026960  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x180026967  mov     edx, 0A8h; void *
0x18002696c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026971  nop
0x180026972  cmp     [rsp+128h+var_C8], r14
0x180026977  jz      short loc_180026984
0x180026979  lea     rcx, [rsp+128h+var_C8]
0x18002697e  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026983  nop
0x180026984  cmp     [rsp+128h+var_D8], r14
0x180026989  jz      short loc_180026996
0x18002698b  lea     rcx, [rsp+128h+var_D8]
0x180026990  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026995  nop
0x180026996  test    rbx, rbx
0x180026999  jz      short loc_1800269A5
0x18002699b  lea     rcx, [rsp+128h+var_B0]
0x1800269a0  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x1800269a5  mov     eax, edi
0x1800269a7  jmp     loc_18002722E
0x1800269ac  mov     [rsp+128h+var_C0], r14
0x1800269b1  mov     rcx, [rsp+128h+var_C8]
0x1800269b6  mov     rax, [rcx]
0x1800269b9  lea     rdx, [rsp+128h+var_C0]
0x1800269be  mov     rax, [rax+58h]
0x1800269c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269c7  mov     edi, eax
0x1800269c9  test    eax, eax
0x1800269cb  jns     short loc_180026A36
0x1800269cd  mov     rcx, [rsp+128h]; this
0x1800269d5  mov     r9d, eax; char *
0x1800269d8  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x1800269df  mov     edx, 0ABh; void *
0x1800269e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800269e9  nop
0x1800269ea  cmp     [rsp+128h+var_C0], r14
0x1800269ef  jz      short loc_1800269FC
0x1800269f1  lea     rcx, [rsp+128h+var_C0]
0x1800269f6  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x1800269fb  nop
0x1800269fc  cmp     [rsp+128h+var_C8], r14
0x180026a01  jz      short loc_180026A0E
0x180026a03  lea     rcx, [rsp+128h+var_C8]
0x180026a08  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026a0d  nop
0x180026a0e  cmp     [rsp+128h+var_D8], r14
0x180026a13  jz      short loc_180026A20
0x180026a15  lea     rcx, [rsp+128h+var_D8]
0x180026a1a  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026a1f  nop
0x180026a20  test    rbx, rbx
0x180026a23  jz      short loc_180026A2F
0x180026a25  lea     rcx, [rsp+128h+var_B0]
0x180026a2a  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026a2f  mov     eax, edi
0x180026a31  jmp     loc_18002722E
0x180026a36  mov     [rsp+128h+var_B8], r14
0x180026a3b  mov     rcx, [rsp+128h+var_C0]
0x180026a40  mov     rax, [rcx]
0x180026a43  lea     r8, [rsp+128h+var_B8]
0x180026a48  lea     rdx, IID_IEnumVARIANT
0x180026a4f  mov     rax, [rax]
0x180026a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a57  mov     edi, eax
0x180026a59  test    eax, eax
0x180026a5b  jns     short loc_180026AD8
0x180026a5d  mov     rcx, [rsp+128h]; this
0x180026a65  mov     r9d, eax; char *
0x180026a68  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x180026a6f  mov     edx, 0AEh; void *
0x180026a74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026a79  nop
0x180026a7a  cmp     [rsp+128h+var_B8], r14
0x180026a7f  jz      short loc_180026A8C
0x180026a81  lea     rcx, [rsp+128h+var_B8]
0x180026a86  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026a8b  nop
0x180026a8c  cmp     [rsp+128h+var_C0], r14
0x180026a91  jz      short loc_180026A9E
0x180026a93  lea     rcx, [rsp+128h+var_C0]
0x180026a98  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026a9d  nop
0x180026a9e  cmp     [rsp+128h+var_C8], r14
0x180026aa3  jz      short loc_180026AB0
0x180026aa5  lea     rcx, [rsp+128h+var_C8]
0x180026aaa  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026aaf  nop
0x180026ab0  cmp     [rsp+128h+var_D8], r14
0x180026ab5  jz      short loc_180026AC2
0x180026ab7  lea     rcx, [rsp+128h+var_D8]
0x180026abc  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026ac1  nop
0x180026ac2  test    rbx, rbx
0x180026ac5  jz      short loc_180026AD1
0x180026ac7  lea     rcx, [rsp+128h+var_B0]
0x180026acc  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026ad1  mov     eax, edi
0x180026ad3  jmp     loc_18002722E
0x180026ad8  mov     r14d, [rsp+128h+arg_28]
0x180026ae0  xor     edi, edi
0x180026ae2  lea     rcx, [rsp+128h+pvarg]; pvarg
0x180026aea  call    cs:__imp_VariantInit
0x180026af0  nop
0x180026af1  mov     [rsp+128h+var_90], edi
0x180026af8  mov     rcx, [rsp+128h+var_B8]
0x180026afd  mov     rax, [rcx]
0x180026b00  lea     r9, [rsp+128h+var_90]
0x180026b08  lea     r8, [rsp+128h+pvarg]
0x180026b10  mov     edx, 1
0x180026b15  mov     rax, [rax+18h]
0x180026b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b1e  mov     edi, eax
0x180026b20  test    eax, eax
0x180026b22  jns     loc_180026BB4
0x180026b28  mov     rcx, [rsp+128h]; this
0x180026b30  mov     r9d, eax; char *
0x180026b33  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x180026b3a  mov     edx, 0B6h; void *
0x180026b3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026b44  nop
0x180026b45  lea     rcx, [rsp+128h+pvarg]; pvarg
0x180026b4d  call    cs:__imp_VariantClear
0x180026b53  nop
0x180026b54  xor     esi, esi
0x180026b56  cmp     [rsp+128h+var_B8], rsi
0x180026b5b  jz      short loc_180026B68
0x180026b5d  lea     rcx, [rsp+128h+var_B8]
0x180026b62  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026b67  nop
0x180026b68  cmp     [rsp+128h+var_C0], rsi
0x180026b6d  jz      short loc_180026B7A
0x180026b6f  lea     rcx, [rsp+128h+var_C0]
0x180026b74  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026b79  nop
0x180026b7a  cmp     [rsp+128h+var_C8], rsi
0x180026b7f  jz      short loc_180026B8C
0x180026b81  lea     rcx, [rsp+128h+var_C8]
0x180026b86  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026b8b  nop
0x180026b8c  cmp     [rsp+128h+var_D8], rsi
0x180026b91  jz      short loc_180026B9E
0x180026b93  lea     rcx, [rsp+128h+var_D8]
0x180026b98  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026b9d  nop
0x180026b9e  test    rbx, rbx
0x180026ba1  jz      short loc_180026BAD
0x180026ba3  lea     rcx, [rsp+128h+var_B0]
0x180026ba8  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180026bad  mov     eax, edi
0x180026baf  jmp     loc_18002722E
0x180026bb4  cmp     edi, 1
0x180026bb7  jz      loc_1800271BB
0x180026bbd  cmp     [rsp+128h+var_90], 1
0x180026bc5  jnz     loc_1800271BB
0x180026bcb  cmp     word ptr [rsp+128h+pvarg], 9
0x180026bd4  jnz     loc_1800271BB
0x180026bda  xor     edi, edi
0x180026bdc  mov     qword ptr [rsp+128h+rclsid.Data1], rdi
0x180026be4  mov     rcx, qword ptr [rsp+128h+pvarg+8]
0x180026bec  mov     rax, [rcx]
0x180026bef  lea     r8, [rsp+128h+rclsid]
0x180026bf7  lea     rdx, _GUID_af230d27_baba_4e42_aced_f524f22cfce2
0x180026bfe  mov     rax, [rax]
0x180026c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c06  mov     rcx, [rsp+128h]; this
0x180026c0e  test    eax, eax
0x180026c10  jns     short loc_180026C2B
0x180026c12  mov     r9d, eax; char *
0x180026c15  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x180026c1c  mov     edx, 0BEh; void *
0x180026c21  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026c26  jmp     loc_18002718F
0x180026c2b  mov     rcx, qword ptr [rsp+128h+rclsid.Data1]
0x180026c33  test    rcx, rcx
0x180026c36  jz      loc_1800271A8
0x180026c3c  mov     [rsp+128h+var_A8], edi
0x180026c43  mov     dword ptr [rsp+128h+var_98], edi
0x180026c4a  mov     [rsp+128h+var_D0], dil
0x180026c4f  lea     rax, [rsp+128h+var_98]
0x180026c57  mov     [rsp+128h+var_E8], rax
0x180026c5c  lea     rax, [rsp+128h+var_A8]
0x180026c64  mov     [rsp+128h+var_F0], rax
0x180026c69  lea     rax, [rsp+128h+var_D0]
0x180026c6e  mov     [rsp+128h+var_F8], rax
0x180026c73  mov     [rsp+128h+var_100], r13d
0x180026c78  mov     dword ptr [rsp+128h+ppv], r14d; int
0x180026c7d  mov     r9b, [rsp+128h+arg_20]
0x180026c85  mov     r8d, r12d
0x180026c88  mov     rdx, [rsp+128h+var_70]
0x180026c90  call    ?CheckIfRuleNeedsUpdate@@YAJPEAUINetFwRule@@AEBUhstring@winrt@@W4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@3@_N22PEA_NPEAW4456783@5@Z; CheckIfRuleNeedsUpdate(INetFwRule *,winrt::hstring const &,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes,bool,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes,bool *,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes *,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes *)
0x180026c95  test    eax, eax
0x180026c97  js      loc_18002718F
0x180026c9d  cmp     [rsp+128h+var_D0], dil
0x180026ca2  jz      loc_18002718F
0x180026ca8  cmp     [rsp+128h+arg_20], dil
0x180026cb0  jnz     short loc_180026CB7
0x180026cb2  mov     r8d, r13d
  ... truncated ...
```
