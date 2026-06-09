# CtapCbor::WebAuthNCredentialDetails::FromCbor(SimpleCbor::Decoder &)

- ea: `0x1800c25e4`
- end: `0x1800c2cd6`
- name: `?FromCbor@WebAuthNCredentialDetails@CtapCbor@@SA?AU12@AEAVDecoder@SimpleCbor@@@Z`
- size: `1778`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c2cdc`
- `0x1800c3494`

## callees

- `0x18001d5fc`
- `0x18001df88`
- `0x180023bc8`
- `0x1800350b4`
- `0x180037f6c`
- `0x18003ab20`
- `0x180081648`
- `0x180081690`
- `0x1800816b8`
- `0x1800819cc`
- `0x180081a10`
- `0x180090c44`
- `0x180090dc0`
- `0x180091034`
- `0x1800912f4`
- `0x1800c1044`
- `0x1800c1184`
- `0x1800c12c4`
- `0x1800c1a14`
- `0x1800c1e48`
- `0x1800c1e84`
- `0x1800c25e4`
- `0x1800c2e80`
- `0x1800c3118`
- `0x1800c3688`
- `0x1800c3718`
- `0x18013c090`

## string_xrefs

- `0x1800c26f4`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c276b`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2797`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c27fd`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2827`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c28ab`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c28f4`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2916`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c294b`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c296a`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2997`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c29da`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2a0a`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2a3a`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2a58`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2a88`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2ab0`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2ad4`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2b02`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2b57`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2b82`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2bd3`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2bfa`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`
- `0x1800c2c27`: `onecore\ds\security\fido\ctap\lib_vtl1\ctapcborvtl1.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CtapCbor::WebAuthNCredentialDetails::FromCbor(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  int *v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 ByteString; // rax
  __int64 v8; // rax
  char v9; // al
  __int64 v10; // rcx
  __int64 v11; // rax
  char Credential; // al
  __int64 v13; // rax
  __int64 TextWString; // rax
  int v17; // [rsp+2Ch] [rbp-D4h]
  int v18; // [rsp+2Ch] [rbp-D4h]
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh]
  const char *v21; // [rsp+48h] [rbp-B8h]
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+54h] [rbp-ACh]
  const char *v24; // [rsp+58h] [rbp-A8h]
  int v25; // [rsp+60h] [rbp-A0h]
  __int64 Int; // [rsp+68h] [rbp-98h]
  __int64 v27; // [rsp+70h] [rbp-90h]
  _DWORD v28[2]; // [rsp+80h] [rbp-80h] BYREF
  const char *v29; // [rsp+88h] [rbp-78h]
  _DWORD v30[2]; // [rsp+90h] [rbp-70h] BYREF
  const char *v31; // [rsp+98h] [rbp-68h]
  _DWORD v32[2]; // [rsp+A0h] [rbp-60h] BYREF
  const char *v33; // [rsp+A8h] [rbp-58h]
  _DWORD v34[2]; // [rsp+B0h] [rbp-50h] BYREF
  const char *v35; // [rsp+B8h] [rbp-48h]
  _DWORD v36[2]; // [rsp+C0h] [rbp-40h] BYREF
  const char *v37; // [rsp+C8h] [rbp-38h]
  _DWORD v38[2]; // [rsp+D0h] [rbp-30h] BYREF
  const char *v39; // [rsp+D8h] [rbp-28h]
  _DWORD v40[2]; // [rsp+E0h] [rbp-20h] BYREF
  const char *v41; // [rsp+E8h] [rbp-18h]
  _DWORD v42[2]; // [rsp+F0h] [rbp-10h] BYREF
  const char *v43; // [rsp+F8h] [rbp-8h]
  _DWORD v44[2]; // [rsp+100h] [rbp+0h] BYREF
  const char *v45; // [rsp+108h] [rbp+8h]
  _DWORD v46[2]; // [rsp+110h] [rbp+10h] BYREF
  const char *v47; // [rsp+118h] [rbp+18h]
  _DWORD v48[2]; // [rsp+120h] [rbp+20h] BYREF
  const char *v49; // [rsp+128h] [rbp+28h]
  _DWORD v50[2]; // [rsp+130h] [rbp+30h] BYREF
  const char *v51; // [rsp+138h] [rbp+38h]
  _DWORD v52[2]; // [rsp+140h] [rbp+40h] BYREF
  const char *v53; // [rsp+148h] [rbp+48h]
  _DWORD v54[2]; // [rsp+150h] [rbp+50h] BYREF
  const char *v55; // [rsp+158h] [rbp+58h]
  _DWORD v56[2]; // [rsp+160h] [rbp+60h] BYREF
  const char *v57; // [rsp+168h] [rbp+68h]
  _DWORD v58[2]; // [rsp+170h] [rbp+70h] BYREF
  const char *v59; // [rsp+178h] [rbp+78h]
  _DWORD v60[2]; // [rsp+180h] [rbp+80h] BYREF
  const char *v61; // [rsp+188h] [rbp+88h]
  _DWORD v62[2]; // [rsp+190h] [rbp+90h] BYREF
  const char *v63; // [rsp+198h] [rbp+98h]
  _DWORD v64[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  const char *v65; // [rsp+1A8h] [rbp+A8h]
  _DWORD v66[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  const char *v67; // [rsp+1B8h] [rbp+B8h]
  __int64 v68; // [rsp+1C0h] [rbp+C0h]
  _BYTE v69[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v70; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v71; // [rsp+1F8h] [rbp+F8h] BYREF
  __int128 v72; // [rsp+200h] [rbp+100h]
  __int64 v73; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v74[32]; // [rsp+218h] [rbp+118h] BYREF
  _BYTE v75[32]; // [rsp+238h] [rbp+138h] BYREF
  __int64 v76; // [rsp+258h] [rbp+158h] BYREF
  __int128 v77; // [rsp+260h] [rbp+160h]
  __int64 v78; // [rsp+270h] [rbp+170h]
  _BYTE v79[32]; // [rsp+278h] [rbp+178h] BYREF
  _BYTE v80[32]; // [rsp+298h] [rbp+198h] BYREF
  __int64 v81; // [rsp+2B8h] [rbp+1B8h]
  _BYTE v82[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v83; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int64 v84; // [rsp+2F0h] [rbp+1F0h]
  __int64 v85; // [rsp+2F8h] [rbp+1F8h]
  _BYTE v86[96]; // [rsp+300h] [rbp+200h] BYREF

  v2 = a2;
  v3 = a1;
  v27 = a1;
  v68 = a1;
  v25 = 0;
  v70 = 4;
  v71 = 0;
  v72 = 0;
  v73 = 1;
  std::wstring::wstring(v74);
  std::wstring::wstring(v75);
  v76 = 1;
  v77 = 0;
  v78 = 0;
  std::wstring::wstring(v79);
  std::wstring::wstring(v80);
  v81 = 0;
  std::wstring::wstring(v82);
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v19 = 5510;
  v20 = v17;
  v21 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
  SimpleCbor::Decoder::EnterMap(v2, &v19);
  v18 = HIDWORD(v2);
  v19 = 5519;
  v20 = HIDWORD(v2);
  v21 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
  if ( !(unsigned __int8)SimpleCbor::Decoder::EndOfContainer(v2, &v19) )
  {
    while ( 1 )
    {
      v28[0] = 5521;
      v28[1] = HIDWORD(v2);
      v29 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
      Int = SimpleCbor::Decoder::GetInt(a2, v28);
      v30[0] = 5522;
      v30[1] = HIDWORD(v2);
      v31 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
      SimpleCbor::Decoder::NextItem(a2, v30);
      if ( Int > 5 )
        break;
      switch ( Int )
      {
        case 5LL:
          v44[0] = 5544;
          v44[1] = HIDWORD(v2);
          v45 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
          BYTE1(v81) = SimpleCbor::Decoder::GetBool(a2, v44);
          v46[0] = 5545;
          v46[1] = HIDWORD(v2);
          v47 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
          v4 = v46;
          goto LABEL_28;
        case 0LL:
          v40[0] = 5526;
          v40[1] = HIDWORD(v2);
          v41 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
          v8 = SimpleCbor::Decoder::GetInt(a2, v40);
          LODWORD(v70) = wil::safe_cast<unsigned long,__int64,0>(v8);
          v42[0] = 5527;
          v42[1] = HIDWORD(v2);
          v43 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
          v4 = v42;
          goto LABEL_28;
        case 1LL:
          v36[0] = 5530;
          v36[1] = HIDWORD(v2);
          v37 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
          ByteString = SimpleCbor::Decoder::GetByteString(a2, v69, v36);
          std::vector<unsigned char>::operator=(&v71, ByteString);
          std::vector<unsigned char>::_Tidy(v69);
          v38[0] = 5531;
          v38[1] = HIDWORD(v2);
          v39 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
          v4 = v38;
          goto LABEL_28;
        case 2LL:
          v6 = CtapCbor::WebAuthNRPEntityInformation::FromCbor(v86, a2);
          CtapCbor::WebAuthNRPEntityInformation::operator=(&v73, v6);
          CtapCbor::WebAuthNRPEntityInformation::~WebAuthNRPEntityInformation((CtapCbor::WebAuthNRPEntityInformation *)v86);
          break;
        case 3LL:
          v5 = CtapCbor::WebAuthNUserEntityInformation::FromCbor(v86, a2);
          CtapCbor::WebAuthNUserEntityInformation::operator=(&v76, v5);
          CtapCbor::WebAuthNUserEntityInformation::~WebAuthNUserEntityInformation((CtapCbor::WebAuthNUserEntityInformation *)v86);
          break;
        case 4LL:
          v32[0] = 5540;
          v32[1] = HIDWORD(v2);
          v33 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
          LOBYTE(v81) = SimpleCbor::Decoder::GetBool(a2, v32);
          v34[0] = 5541;
          v34[1] = HIDWORD(v2);
          v35 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
          v4 = v34;
          goto LABEL_28;
        default:
LABEL_19:
          v48[0] = 5582;
          v48[1] = HIDWORD(v2);
          v49 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
          v4 = v48;
LABEL_28:
          v10 = a2;
          goto LABEL_29;
      }
LABEL_30:
      v19 = 5519;
      v20 = HIDWORD(v2);
      v21 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
      if ( (unsigned __int8)SimpleCbor::Decoder::EndOfContainer(a2, &v19) )
      {
        v2 = a2;
        v3 = v27;
        goto LABEL_32;
      }
    }
    switch ( Int )
    {
      case 6LL:
        v66[0] = 5548;
        v66[1] = HIDWORD(v2);
        v67 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
        TextWString = SimpleCbor::Decoder::GetTextWString(a2, v69, v66);
        std::wstring::operator=(v82, TextWString);
        std::wstring::_Tidy_deallocate(v69);
        v22 = 5549;
        v23 = HIDWORD(v2);
        v24 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
        v4 = &v22;
        goto LABEL_28;
      case 7LL:
        v62[0] = 5552;
        v62[1] = HIDWORD(v2);
        v63 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
        v13 = SimpleCbor::Decoder::GetByteString(a2, v69, v62);
        std::vector<unsigned char>::operator=(&v83, v13);
        std::vector<unsigned char>::_Tidy(v69);
        v64[0] = 5553;
        v64[1] = HIDWORD(v2);
        v65 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
        v4 = v64;
        goto LABEL_28;
      case 8LL:
        Credential = VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>>();
        v10 = a2;
        if ( Credential )
        {
          v56[0] = 5559;
          v56[1] = HIDWORD(v2);
          v57 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
          LOBYTE(v85) = SimpleCbor::Decoder::GetBool(a2, v56);
          v58[0] = 5560;
          v58[1] = HIDWORD(v2);
          v59 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
          v4 = v58;
          goto LABEL_28;
        }
        v60[0] = 5564;
        v60[1] = HIDWORD(v2);
        v61 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
        v4 = v60;
        break;
      case 9LL:
        v9 = VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_WebAuthnApiUpdates>>();
        v10 = a2;
        if ( v9 )
        {
          v50[0] = 5572;
          v50[1] = HIDWORD(v2);
          v51 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
          v11 = SimpleCbor::Decoder::GetInt(a2, v50);
          HIDWORD(v85) = wil::safe_cast<unsigned long,__int64,0>(v11);
          v52[0] = 5573;
          v52[1] = HIDWORD(v2);
          v53 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
          v4 = v52;
          goto LABEL_28;
        }
        v54[0] = 5577;
        v54[1] = HIDWORD(v2);
        v55 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
        v4 = v54;
        break;
      default:
        goto LABEL_19;
    }
LABEL_29:
    SimpleCbor::Decoder::NextItem(v10, v4);
    goto LABEL_30;
  }
LABEL_32:
  if ( !(unsigned __int8)VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>>() )
  {
    v22 = 5588;
    v23 = v18;
    v24 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
    SimpleCbor::Decoder::LeaveContainer(v2, &v22);
  }
  CtapCbor::WebAuthNCredentialDetails::WebAuthNCredentialDetails(v3, &v70);
  v25 = 1;
  if ( (unsigned __int8)VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>>() )
  {
    v22 = 5515;
    v23 = v18;
    v24 = "onecore\\ds\\security\\fido\\ctap\\lib_vtl1\\ctapcborvtl1.cpp";
    SimpleCbor::Decoder::LeaveContainer(v2, &v22);
  }
  CtapCbor::WebAuthNCredentialDetails::~WebAuthNCredentialDetails((CtapCbor::WebAuthNCredentialDetails *)&v70);
  return v3;
}

```

## disassembly

```asm
0x1800c25e4  mov     [rsp-8+arg_10], rbx
0x1800c25e9  push    rbp
0x1800c25ea  push    rsi
0x1800c25eb  push    rdi
0x1800c25ec  push    r12
0x1800c25ee  push    r13
0x1800c25f0  push    r14
0x1800c25f2  push    r15
0x1800c25f4  lea     rbp, [rsp-270h]
0x1800c25fc  sub     rsp, 370h
0x1800c2603  mov     rax, cs:__security_cookie
0x1800c260a  xor     rax, rsp
0x1800c260d  mov     [rbp+2A0h+var_40], rax
0x1800c2614  mov     rdi, rdx
0x1800c2617  mov     [rsp+3A0h+var_380], rdx
0x1800c261c  mov     rsi, rcx
0x1800c261f  mov     [rsp+3A0h+var_330], rcx
0x1800c2624  mov     [rbp+2A0h+var_1E0], rcx
0x1800c262b  mov     [rsp+3A0h+var_340], 0
0x1800c2633  mov     [rbp+2A0h+var_1B0], 4
0x1800c263e  mov     [rbp+2A0h+var_1A8], 0
0x1800c2649  xorps   xmm0, xmm0
0x1800c264c  movdqa  [rbp+2A0h+var_1A0], xmm0
0x1800c2654  mov     [rbp+2A0h+var_190], 1
0x1800c265f  lea     rcx, [rbp+2A0h+var_188]
0x1800c2666  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800c266b  lea     rcx, [rbp+2A0h+var_168]
0x1800c2672  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800c2677  mov     [rbp+2A0h+var_148], 1
0x1800c2682  xorps   xmm0, xmm0
0x1800c2685  movdqa  [rbp+2A0h+var_140], xmm0
0x1800c268d  mov     [rbp+2A0h+var_130], 0
0x1800c2698  lea     rcx, [rbp+2A0h+var_128]
0x1800c269f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800c26a4  lea     rcx, [rbp+2A0h+var_108]
0x1800c26ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800c26b0  xor     eax, eax
0x1800c26b2  mov     [rbp+2A0h+var_E8], rax
0x1800c26b9  lea     rcx, [rbp+2A0h+var_E0]
0x1800c26c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800c26c5  xorps   xmm1, xmm1
0x1800c26c8  movdqa  [rbp+2A0h+var_C0], xmm1
0x1800c26d0  mov     [rbp+2A0h+var_B0], 0
0x1800c26db  xor     eax, eax
0x1800c26dd  mov     [rbp+2A0h+var_A8], rax
0x1800c26e4  mov     [rsp+3A0h+var_360], 1586h
0x1800c26ec  mov     eax, [rsp+3A0h+var_374]
0x1800c26f0  mov     [rsp+3A0h+var_35C], eax
0x1800c26f4  lea     r14, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c26fb  mov     [rsp+3A0h+var_358], r14
0x1800c2700  lea     rdx, [rsp+3A0h+var_360]
0x1800c2705  mov     rcx, rdi
0x1800c2708  call    ?EnterMap@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EnterMap(SimpleCbor::impl::slim_source_location)
0x1800c270d  mov     [rsp+28h], rdi
0x1800c2712  mov     [rsp+3A0h+var_370], 1
0x1800c2717  mov     [rsp+3A0h+var_360], 158Fh
0x1800c271f  mov     ebx, [rsp+3A0h+var_374]
0x1800c2723  mov     [rsp+3A0h+var_35C], ebx
0x1800c2727  mov     [rsp+3A0h+var_358], r14
0x1800c272c  lea     rdx, [rsp+3A0h+var_360]
0x1800c2731  mov     rcx, rdi
0x1800c2734  call    ?EndOfContainer@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EndOfContainer(SimpleCbor::impl::slim_source_location)
0x1800c2739  test    al, al
0x1800c273b  jnz     loc_1800C2C2E
0x1800c2741  mov     r15d, [rsp+3A0h+var_374]
0x1800c2746  mov     r12d, [rsp+3A0h+var_374]
0x1800c274b  mov     r13d, [rsp+3A0h+var_374]
0x1800c2750  mov     edi, [rsp+3A0h+var_374]
0x1800c2754  mov     esi, [rsp+3A0h+var_374]
0x1800c2758  mov     r14d, [rsp+3A0h+var_374]
0x1800c275d  mov     [rbp+2A0h+var_320], 1591h
0x1800c2764  mov     eax, [rsp+3A0h+var_374]
0x1800c2768  mov     [rbp+2A0h+var_31C], eax
0x1800c276b  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2772  mov     [rbp+2A0h+var_318], rax
0x1800c2776  lea     rdx, [rbp+2A0h+var_320]
0x1800c277a  mov     rcx, [rsp+3A0h+var_380]
0x1800c277f  call    ?GetInt@Decoder@SimpleCbor@@QEAA_JUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetInt(SimpleCbor::impl::slim_source_location)
0x1800c2784  mov     [rsp+3A0h+var_338], rax
0x1800c2789  mov     [rbp+2A0h+var_310], 1592h
0x1800c2790  mov     eax, [rsp+3A0h+var_374]
0x1800c2794  mov     [rbp+2A0h+var_30C], eax
0x1800c2797  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c279e  mov     [rbp+2A0h+var_308], rax
0x1800c27a2  lea     rdx, [rbp+2A0h+var_310]
0x1800c27a6  mov     rcx, [rsp+3A0h+var_380]
0x1800c27ab  call    ?NextItem@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::NextItem(SimpleCbor::impl::slim_source_location)
0x1800c27b0  mov     rax, [rsp+3A0h+var_338]
0x1800c27b5  cmp     rax, 5
0x1800c27b9  jg      loc_1800C29AB
0x1800c27bf  jz      loc_1800C295F
0x1800c27c5  test    rax, rax
0x1800c27c8  jz      loc_1800C2908
0x1800c27ce  sub     rax, 1
0x1800c27d2  jz      loc_1800C289D
0x1800c27d8  sub     rax, 1
0x1800c27dc  jz      loc_1800C286C
0x1800c27e2  sub     rax, 1
0x1800c27e6  jz      short loc_1800C283B
0x1800c27e8  cmp     rax, 1
0x1800c27ec  jnz     loc_1800C29CF
0x1800c27f2  mov     [rbp+2A0h+var_300], 15A4h
0x1800c27f9  mov     [rbp+2A0h+var_2FC], r15d
0x1800c27fd  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2804  mov     [rbp+2A0h+var_2F8], rax
0x1800c2808  lea     rdx, [rbp+2A0h+var_300]
0x1800c280c  mov     rcx, [rsp+3A0h+var_380]
0x1800c2811  call    ?GetBool@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetBool(SimpleCbor::impl::slim_source_location)
0x1800c2816  mov     byte ptr [rbp+2A0h+var_E8], al
0x1800c281c  mov     [rbp+2A0h+var_2F0], 15A5h
0x1800c2823  mov     [rbp+2A0h+var_2EC], r12d
0x1800c2827  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c282e  mov     [rbp+2A0h+var_2E8], rax
0x1800c2832  lea     rdx, [rbp+2A0h+var_2F0]
0x1800c2836  jmp     loc_1800C2BE4
0x1800c283b  mov     rdx, [rsp+3A0h+var_380]
0x1800c2840  lea     rcx, [rbp+2A0h+var_A0]
0x1800c2847  call    ?FromCbor@WebAuthNUserEntityInformation@CtapCbor@@SA?AU12@AEAVDecoder@SimpleCbor@@@Z; CtapCbor::WebAuthNUserEntityInformation::FromCbor(SimpleCbor::Decoder &)
0x1800c284c  mov     rdx, rax
0x1800c284f  lea     rcx, [rbp+2A0h+var_148]
0x1800c2856  call    ??4WebAuthNUserEntityInformation@CtapCbor@@QEAAAEAU01@$$QEAU01@@Z; CtapCbor::WebAuthNUserEntityInformation::operator=(CtapCbor::WebAuthNUserEntityInformation &&)
0x1800c285b  lea     rcx, [rbp+2A0h+var_A0]; this
0x1800c2862  call    ??1WebAuthNUserEntityInformation@CtapCbor@@QEAA@XZ; CtapCbor::WebAuthNUserEntityInformation::~WebAuthNUserEntityInformation(void)
0x1800c2867  jmp     loc_1800C2BEE
0x1800c286c  mov     rdx, [rsp+3A0h+var_380]
0x1800c2871  lea     rcx, [rbp+2A0h+var_A0]
0x1800c2878  call    ?FromCbor@WebAuthNRPEntityInformation@CtapCbor@@SA?AU12@AEAVDecoder@SimpleCbor@@@Z; CtapCbor::WebAuthNRPEntityInformation::FromCbor(SimpleCbor::Decoder &)
0x1800c287d  mov     rdx, rax
0x1800c2880  lea     rcx, [rbp+2A0h+var_190]
0x1800c2887  call    ??4WebAuthNRPEntityInformation@CtapCbor@@QEAAAEAU01@$$QEAU01@@Z; CtapCbor::WebAuthNRPEntityInformation::operator=(CtapCbor::WebAuthNRPEntityInformation &&)
0x1800c288c  lea     rcx, [rbp+2A0h+var_A0]; this
0x1800c2893  call    ??1WebAuthNRPEntityInformation@CtapCbor@@QEAA@XZ; CtapCbor::WebAuthNRPEntityInformation::~WebAuthNRPEntityInformation(void)
0x1800c2898  jmp     loc_1800C2BEE
0x1800c289d  mov     [rbp+2A0h+var_2E0], 159Ah
0x1800c28a4  mov     eax, [rsp+3A0h+var_374]
0x1800c28a8  mov     [rbp+2A0h+var_2DC], eax
0x1800c28ab  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c28b2  mov     [rbp+2A0h+var_2D8], rax
0x1800c28b6  lea     r8, [rbp+2A0h+var_2E0]
0x1800c28ba  lea     rdx, [rbp+2A0h+var_1D0]
0x1800c28c1  mov     rcx, [rsp+3A0h+var_380]
0x1800c28c6  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x1800c28cb  mov     rdx, rax
0x1800c28ce  lea     rcx, [rbp+2A0h+var_1A8]
0x1800c28d5  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1800c28da  lea     rcx, [rbp+2A0h+var_1D0]
0x1800c28e1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800c28e6  mov     [rbp+2A0h+var_2D0], 159Bh
0x1800c28ed  mov     eax, [rsp+3A0h+var_374]
0x1800c28f1  mov     [rbp+2A0h+var_2CC], eax
0x1800c28f4  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c28fb  mov     [rbp+2A0h+var_2C8], rax
0x1800c28ff  lea     rdx, [rbp+2A0h+var_2D0]
0x1800c2903  jmp     loc_1800C2BE4
0x1800c2908  mov     [rbp+2A0h+var_2C0], 1596h
0x1800c290f  mov     eax, [rsp+3A0h+var_374]
0x1800c2913  mov     [rbp+2A0h+var_2BC], eax
0x1800c2916  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c291d  mov     [rbp+2A0h+var_2B8], rax
0x1800c2921  lea     rdx, [rbp+2A0h+var_2C0]
0x1800c2925  mov     rcx, [rsp+3A0h+var_380]
0x1800c292a  call    ?GetInt@Decoder@SimpleCbor@@QEAA_JUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetInt(SimpleCbor::impl::slim_source_location)
0x1800c292f  mov     rcx, rax
0x1800c2932  call    ??$safe_cast@K_J$0A@@wil@@YAK_J@Z; wil::safe_cast<ulong,__int64,0>(__int64)
0x1800c2937  mov     dword ptr [rbp+2A0h+var_1B0], eax
0x1800c293d  mov     [rbp+2A0h+var_2B0], 1597h
0x1800c2944  mov     eax, [rsp+3A0h+var_374]
0x1800c2948  mov     [rbp+2A0h+var_2AC], eax
0x1800c294b  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2952  mov     [rbp+2A0h+var_2A8], rax
0x1800c2956  lea     rdx, [rbp+2A0h+var_2B0]
0x1800c295a  jmp     loc_1800C2BE4
0x1800c295f  mov     [rbp+2A0h+var_2A0], 15A8h
0x1800c2966  mov     [rbp+2A0h+var_29C], r13d
0x1800c296a  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2971  mov     [rbp+2A0h+var_298], rax
0x1800c2975  lea     rdx, [rbp+2A0h+var_2A0]
0x1800c2979  mov     rcx, [rsp+3A0h+var_380]
0x1800c297e  call    ?GetBool@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetBool(SimpleCbor::impl::slim_source_location)
0x1800c2983  mov     byte ptr [rbp+2A0h+var_E8+1], al
0x1800c2989  mov     [rbp+2A0h+var_290], 15A9h
0x1800c2990  mov     eax, [rsp+3A0h+var_374]
0x1800c2994  mov     [rbp+2A0h+var_28C], eax
0x1800c2997  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c299e  mov     [rbp+2A0h+var_288], rax
0x1800c29a2  lea     rdx, [rbp+2A0h+var_290]
0x1800c29a6  jmp     loc_1800C2BE4
0x1800c29ab  sub     rax, 6
0x1800c29af  jz      loc_1800C2B6E
0x1800c29b5  sub     rax, 1
0x1800c29b9  jz      loc_1800C2AEE
0x1800c29bf  sub     rax, 1
0x1800c29c3  jz      loc_1800C2A6C
0x1800c29c9  cmp     rax, 1
0x1800c29cd  jz      short loc_1800C29EE
0x1800c29cf  mov     [rbp+2A0h+var_280], 15CEh
0x1800c29d6  mov     [rbp+2A0h+var_27C], r14d
0x1800c29da  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c29e1  mov     [rbp+2A0h+var_278], rax
0x1800c29e5  lea     rdx, [rbp+2A0h+var_280]
0x1800c29e9  jmp     loc_1800C2BE4
0x1800c29ee  call    ??$IsEnabled@V?$Feature@U__WilFeatureTraits_Feature_WebAuthnApiUpdates@@@wil@@@Velocity@VsmUtils@@SA_NXZ; VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_WebAuthnApiUpdates>>(void)
0x1800c29f3  mov     rcx, [rsp+3A0h+var_380]
0x1800c29f8  test    al, al
0x1800c29fa  jz      short loc_1800C2A4E
0x1800c29fc  mov     [rbp+2A0h+var_270], 15C4h
0x1800c2a03  mov     eax, [rsp+3A0h+var_374]
0x1800c2a07  mov     [rbp+2A0h+var_26C], eax
0x1800c2a0a  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2a11  mov     [rbp+2A0h+var_268], rax
0x1800c2a15  lea     rdx, [rbp+2A0h+var_270]
0x1800c2a19  call    ?GetInt@Decoder@SimpleCbor@@QEAA_JUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetInt(SimpleCbor::impl::slim_source_location)
0x1800c2a1e  mov     rcx, rax
0x1800c2a21  call    ??$safe_cast@K_J$0A@@wil@@YAK_J@Z; wil::safe_cast<ulong,__int64,0>(__int64)
0x1800c2a26  mov     dword ptr [rbp+2A0h+var_A8+4], eax
0x1800c2a2c  mov     [rbp+2A0h+var_260], 15C5h
0x1800c2a33  mov     eax, [rsp+3A0h+var_374]
0x1800c2a37  mov     [rbp+2A0h+var_25C], eax
0x1800c2a3a  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2a41  mov     [rbp+2A0h+var_258], rax
0x1800c2a45  lea     rdx, [rbp+2A0h+var_260]
0x1800c2a49  jmp     loc_1800C2BE4
0x1800c2a4e  mov     [rbp+2A0h+var_250], 15C9h
0x1800c2a55  mov     [rbp+2A0h+var_24C], esi
0x1800c2a58  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2a5f  mov     [rbp+2A0h+var_248], rax
0x1800c2a63  lea     rdx, [rbp+2A0h+var_250]
0x1800c2a67  jmp     loc_1800C2BE9
0x1800c2a6c  call    ??$IsEnabled@V?$Feature@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@wil@@@Velocity@VsmUtils@@SA_NXZ; VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>>(void)
0x1800c2a71  mov     rcx, [rsp+3A0h+var_380]
0x1800c2a76  test    al, al
0x1800c2a78  jz      short loc_1800C2AC4
0x1800c2a7a  mov     [rbp+2A0h+var_240], 15B7h
0x1800c2a81  mov     eax, [rsp+3A0h+var_374]
0x1800c2a85  mov     [rbp+2A0h+var_23C], eax
0x1800c2a88  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2a8f  mov     [rbp+2A0h+var_238], rax
0x1800c2a93  lea     rdx, [rbp+2A0h+var_240]
0x1800c2a97  call    ?GetBool@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetBool(SimpleCbor::impl::slim_source_location)
0x1800c2a9c  mov     byte ptr [rbp+2A0h+var_A8], al
0x1800c2aa2  mov     [rbp+2A0h+var_230], 15B8h
0x1800c2aa9  mov     eax, [rsp+3A0h+var_374]
0x1800c2aad  mov     [rbp+2A0h+var_22C], eax
0x1800c2ab0  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2ab7  mov     [rbp+2A0h+var_228], rax
0x1800c2abb  lea     rdx, [rbp+2A0h+var_230]
0x1800c2abf  jmp     loc_1800C2BE4
0x1800c2ac4  mov     [rbp+2A0h+var_220], 15BCh
0x1800c2ace  mov     [rbp+2A0h+var_21C], edi
0x1800c2ad4  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2adb  mov     [rbp+2A0h+var_218], rax
0x1800c2ae2  lea     rdx, [rbp+2A0h+var_220]
0x1800c2ae9  jmp     loc_1800C2BE9
0x1800c2aee  mov     [rbp+2A0h+var_210], 15B0h
0x1800c2af8  mov     eax, [rsp+3A0h+var_374]
0x1800c2afc  mov     [rbp+2A0h+var_20C], eax
0x1800c2b02  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2b09  mov     [rbp+2A0h+var_208], rax
0x1800c2b10  lea     r8, [rbp+2A0h+var_210]
0x1800c2b17  lea     rdx, [rbp+2A0h+var_1D0]
0x1800c2b1e  mov     rcx, [rsp+3A0h+var_380]
0x1800c2b23  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x1800c2b28  mov     rdx, rax
0x1800c2b2b  lea     rcx, [rbp+2A0h+var_C0]
0x1800c2b32  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1800c2b37  lea     rcx, [rbp+2A0h+var_1D0]
0x1800c2b3e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800c2b43  mov     [rbp+2A0h+var_200], 15B1h
0x1800c2b4d  mov     eax, [rsp+3A0h+var_374]
0x1800c2b51  mov     [rbp+2A0h+var_1FC], eax
0x1800c2b57  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2b5e  mov     [rbp+2A0h+var_1F8], rax
0x1800c2b65  lea     rdx, [rbp+2A0h+var_200]
0x1800c2b6c  jmp     short loc_1800C2BE4
0x1800c2b6e  mov     [rbp+2A0h+var_1F0], 15ACh
0x1800c2b78  mov     eax, [rsp+3A0h+var_374]
0x1800c2b7c  mov     [rbp+2A0h+var_1EC], eax
0x1800c2b82  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2b89  mov     [rbp+2A0h+var_1E8], rax
0x1800c2b90  lea     r8, [rbp+2A0h+var_1F0]
0x1800c2b97  lea     rdx, [rbp+2A0h+var_1D0]
0x1800c2b9e  mov     rcx, [rsp+3A0h+var_380]
0x1800c2ba3  call    ?GetTextWString@Decoder@SimpleCbor@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetTextWString(SimpleCbor::impl::slim_source_location)
0x1800c2ba8  mov     rdx, rax
0x1800c2bab  lea     rcx, [rbp+2A0h+var_E0]
0x1800c2bb2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800c2bb7  lea     rcx, [rbp+2A0h+var_1D0]
0x1800c2bbe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c2bc3  mov     [rsp+3A0h+var_350], 15ADh
0x1800c2bcb  mov     eax, [rsp+3A0h+var_374]
0x1800c2bcf  mov     [rsp+3A0h+var_34C], eax
0x1800c2bd3  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2bda  mov     [rsp+3A0h+var_348], rax
0x1800c2bdf  lea     rdx, [rsp+3A0h+var_350]
0x1800c2be4  mov     rcx, [rsp+3A0h+var_380]
0x1800c2be9  call    ?NextItem@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::NextItem(SimpleCbor::impl::slim_source_location)
0x1800c2bee  mov     [rsp+3A0h+var_360], 158Fh
0x1800c2bf6  mov     [rsp+3A0h+var_35C], ebx
0x1800c2bfa  lea     rax, aOnecoreDsSecur_29; "onecore\\ds\\security\\fido\\ctap\\lib_"...
0x1800c2c01  mov     [rsp+3A0h+var_358], rax
  ... truncated ...
```
