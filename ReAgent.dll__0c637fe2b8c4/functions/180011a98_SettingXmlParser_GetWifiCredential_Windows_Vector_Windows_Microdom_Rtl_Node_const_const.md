# SettingXmlParser::GetWifiCredential(Windows::Vector<Windows::Microdom::Rtl::Node const> const *)

- ea: `0x180011a98`
- end: `0x180011f83`
- name: `?GetWifiCredential@SettingXmlParser@@IEAAKPEBU?$Vector@$$CBUNode@Rtl@Microdom@Windows@@@Windows@@@Z`
- size: `1259`
- prototype: `__int64 __fastcall(BasicXmlParser *this, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013e50`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x180011a98`
- `0x180012614`
- `0x180017014`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180011f6e`
- `ntdll!RtlNtStatusToDosError` at `0x180011f6e`

## string_xrefs

- `0x180011e05`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x180011ea9`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x180011f4c`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x180011e1b`: `SettingXmlParser::GetWifiCredential %s (0x%x) in file %S line %d`
- `0x180011eb3`: `SettingXmlParser::GetWifiCredential %s (0x%x) in file %S line %d`
- `0x180011f56`: `SettingXmlParser::GetWifiCredential %s (0x%x) in file %S line %d`
- `0x180011e50`: `Failed to get ssid attribute.`
- `0x180011e44`: `Empty ssid attribute.`
- `0x180011e72`: `Find wifi node: ssid=%s`
- `0x180011ea2`: `failed to copy ssid`
- `0x180011ef6`: `failed to copy password`

## pseudocode

```c
__int64 __fastcall SettingXmlParser::GetWifiCredential(BasicXmlParser *this, _QWORD *a2)
{
  unsigned int v4; // ebx
  __int64 *v5; // rcx
  __int64 v6; // rax
  NTSTATUS v7; // edi
  ULONG v8; // ebx
  __int64 *v10; // rcx
  __int64 v11; // rax
  __int64 (__fastcall *v12)(__int64 *, struct Node *, struct Node *, _QWORD *); // rax
  const wchar_t *v13; // r8
  _QWORD *v14; // r8
  unsigned int v15; // esi
  unsigned int v16; // r15d
  __int64 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // esi
  unsigned __int64 v22; // r11
  const wchar_t *v23; // r8
  int v24; // [rsp+28h] [rbp-D8h]
  int v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+28h] [rbp-D8h]
  struct Node v27[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct Node v28[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v29[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v31; // [rsp+70h] [rbp-90h] BYREF
  __m128i si128; // [rsp+80h] [rbp-80h] BYREF
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  char v35; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v36; // [rsp+120h] [rbp+20h]
  unsigned __int16 v37[304]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v38[304]; // [rsp+390h] [rbp+290h] BYREF

  v33 = 0x2000;
  v34 = 8193;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  memset_0(v37, 0, 0x25Cu);
  memset_0(v38, 0, 0x25Cu);
  v4 = 0;
  v30[0] = 0;
  v31 = 0;
  if ( !a2[1] )
  {
LABEL_5:
    UnattendLogW(1, L"Failed to find wifi credential node");
    goto LABEL_6;
  }
  while ( 1 )
  {
    v5 = (__int64 *)*((_QWORD *)this + 4);
    v6 = *v5;
    *(_OWORD *)&v28[0].lpVtbl = *(_OWORD *)(*a2 + 16LL * v4);
    v7 = (*(__int64 (__fastcall **)(__int64 *, struct Node *, __int128 *))(v6 + 88))(v5, v28, &v31);
    if ( v7 < 0 )
    {
      v24 = 3493;
LABEL_49:
      v13 = L"failed to cast";
LABEL_50:
      UnattendLogW(
        2,
        L"SettingXmlParser::GetWifiCredential %s (0x%x) in file %S line %d",
        v13,
        (unsigned int)v7,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
        v24);
      goto LABEL_51;
    }
    *(_OWORD *)&v28[0].lpVtbl = v31;
    if ( (unsigned int)BasicXmlParser::IsNodeByTag(
                         this,
                         (struct Node)v28,
                         (const struct _LUTF8_STRING *)&SettingXmlParser::Utf8WifiCredentialTag) )
      break;
    if ( (unsigned __int64)++v4 >= a2[1] )
      goto LABEL_5;
  }
  v10 = (__int64 *)*((_QWORD *)this + 4);
  *(_OWORD *)&v27[0].lpVtbl = v31;
  v11 = *v10;
  v29[0] = &v35;
  v28[0].lpVtbl = (struct NodeVtbl *)&si128;
  v29[1] = 6;
  v12 = *(__int64 (__fastcall **)(__int64 *, struct Node *, struct Node *, _QWORD *))(v11 + 152);
  v28[1].lpVtbl = (struct NodeVtbl *)6;
  v7 = v12(v10, v27, v28, v29);
  if ( v7 < 0 )
  {
    v24 = 3510;
    v13 = L"failed to get properties";
    goto LABEL_50;
  }
  v14 = v36;
  v8 = 0;
  if ( !v36 || !v36[1] )
  {
    UnattendLogW(0, L"No nodes found under wifi credential");
    return v8;
  }
  v15 = 0;
  v16 = 0;
  while ( 2 )
  {
    v17 = (__int64 *)*((_QWORD *)this + 4);
    v18 = *v17;
    *(_OWORD *)&v27[0].lpVtbl = *(_OWORD *)(*v14 + 16LL * v16);
    v7 = (*(__int64 (__fastcall **)(__int64 *, struct Node *, __int128 *))(v18 + 88))(v17, v27, &v31);
    if ( v7 < 0 )
    {
      v24 = 3526;
      goto LABEL_49;
    }
    *(_OWORD *)&v27[0].lpVtbl = v31;
    if ( !(unsigned int)BasicXmlParser::IsNodeByTag(
                          this,
                          (struct Node)v27,
                          (const struct _LUTF8_STRING *)&SettingXmlParser::Utf8WifiTag) )
      goto LABEL_26;
    if ( ++v15 != 1 )
      goto LABEL_26;
    v19 = *((_QWORD *)this + 4);
    *(_OWORD *)&v27[0].lpVtbl = v31;
    v7 = (*(__int64 (__fastcall **)(__int64, struct Node *, void *, _QWORD *))(*(_QWORD *)v19 + 264LL))(
           v19,
           v27,
           &SettingXmlParser::Utf8WifiSsidAttrTag,
           v30);
    if ( v7 < 0 || !v30[0] )
    {
      UnattendLogW(1, L"Failed to get ssid attribute.");
      goto LABEL_45;
    }
    if ( *(_QWORD *)v30[0] )
    {
      v8 = winreUtf8ToUnicode(v30[0], v37, 0);
      if ( v8 )
      {
        v25 = 3552;
      }
      else
      {
        v20 = *((_QWORD *)this + 4);
        *(_OWORD *)&v27[0].lpVtbl = v31;
        v7 = (*(__int64 (__fastcall **)(__int64, struct Node *, void *, _QWORD *))(*(_QWORD *)v20 + 264LL))(
               v20,
               v27,
               &SettingXmlParser::Utf8WifiPasswordAttrTag,
               v30);
        if ( v7 < 0 || !v30[0] )
        {
          UnattendLogW(1, L"Failed to get password attribute.");
          goto LABEL_45;
        }
        if ( !*(_QWORD *)v30[0] )
        {
          UnattendLogW(0, L"Empty password attribute.");
          v38[0] = 0;
          goto LABEL_26;
        }
        v8 = winreUtf8ToUnicode(v30[0], v38, 0);
        if ( !v8 )
        {
LABEL_26:
          v14 = v36;
          if ( (unsigned __int64)++v16 < v36[1] )
            continue;
          if ( v15 > 1 )
          {
            UnattendLogW(1, L"Multiple wifi nodes found: %u", v15);
            v8 = 13;
            goto LABEL_45;
          }
          if ( v15 )
          {
            UnattendLogW(0, L"Find wifi node: ssid=%s", v37);
            v21 = StringCchCopyW(*((unsigned __int16 **)this + 8), 0x12Eu, v37);
            if ( v21 >= 0 )
            {
              v21 = StringCchCopyW((unsigned __int16 *)(*((_QWORD *)this + 8) + 604LL), v22, v38);
              if ( v21 >= 0 )
              {
                *(_DWORD *)(*((_QWORD *)this + 8) + 1228LL) |= 1u;
                goto LABEL_45;
              }
              v26 = 3593;
              v23 = L"failed to copy password";
            }
            else
            {
              v26 = 3592;
              v23 = L"failed to copy ssid";
            }
            UnattendLogW(
              2,
              L"SettingXmlParser::GetWifiCredential %s (0x%x) in file %S line %d",
              v23,
              (unsigned int)v21,
              "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
              v26);
            v8 = (unsigned __int16)v21;
            goto LABEL_45;
          }
          UnattendLogW(0, L"No wifi nodes found");
LABEL_45:
          if ( v7 < 0 )
LABEL_51:
            v8 = RtlNtStatusToDosError(v7);
          if ( v8 )
            goto LABEL_7;
          return v8;
        }
        v25 = 3572;
      }
      UnattendLogW(
        2,
        L"SettingXmlParser::GetWifiCredential %s (0x%x) in file %S line %d",
        L"failed to convert utf8 to unicode",
        v8,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
        v25);
      goto LABEL_7;
    }
    break;
  }
  UnattendLogW(1, L"Empty ssid attribute.");
LABEL_6:
  v8 = 13;
LABEL_7:
  UnattendLogW(2, L"failed to get wifi credential: 0x%x", v8);
  return v8;
}

```

## disassembly

```asm
0x180011a98  mov     [rsp-8+arg_10], rbx
0x180011a9d  mov     [rsp-8+arg_18], rsi
0x180011aa2  push    rbp
0x180011aa3  push    rdi
0x180011aa4  push    r13
0x180011aa6  push    r14
0x180011aa8  push    r15
0x180011aaa  lea     rbp, [rsp-500h]
0x180011ab2  sub     rsp, 600h
0x180011ab9  mov     rax, cs:__security_cookie
0x180011ac0  xor     rax, rsp
0x180011ac3  mov     [rbp+520h+var_30], rax
0x180011aca  movdqa  xmm0, cs:__xmm@00002008000020090000200500002004
0x180011ad2  mov     rsi, rdx
0x180011ad5  mov     r14, rcx
0x180011ad8  mov     [rbp+520h+var_590], 2000h
0x180011adf  mov     ebx, 25Ch
0x180011ae4  mov     [rbp+520h+var_58C], 2001h
0x180011aeb  mov     r8d, ebx; Size
0x180011aee  lea     rcx, [rbp+520h+var_4F0]; void *
0x180011af2  xor     edx, edx; Val
0x180011af4  movdqu  [rbp+520h+var_5A0], xmm0
0x180011af9  call    memset_0
0x180011afe  mov     r8d, ebx; Size
0x180011b01  lea     rcx, [rbp+520h+var_290]; void *
0x180011b08  xor     edx, edx; Val
0x180011b0a  call    memset_0
0x180011b0f  xor     ebx, ebx
0x180011b11  mov     [rsp+620h+var_5C0], 0
0x180011b1a  xorps   xmm0, xmm0
0x180011b1d  movups  [rsp+620h+var_5B0], xmm0
0x180011b22  lea     r13d, [rbx+1]
0x180011b26  cmp     [rsi+8], rbx
0x180011b2a  jbe     short loc_180011B90
0x180011b2c  mov     rax, [rsi]
0x180011b2f  lea     r8, [rsp+620h+var_5B0]
0x180011b34  mov     rcx, [r14+20h]
0x180011b38  mov     edx, ebx
0x180011b3a  add     rdx, rdx
0x180011b3d  movups  xmm0, xmmword ptr [rax+rdx*8]
0x180011b41  mov     rax, [rcx]
0x180011b44  lea     rdx, [rsp+620h+var_5E0]
0x180011b49  movdqu  xmmword ptr [rsp+620h+var_5E0.lpVtbl], xmm0
0x180011b4f  mov     rax, [rax+58h]
0x180011b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b58  mov     edi, eax
0x180011b5a  test    eax, eax
0x180011b5c  js      loc_180011F3D
0x180011b62  movaps  xmm0, [rsp+620h+var_5B0]
0x180011b67  lea     r8, ?Utf8WifiCredentialTag@SettingXmlParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180011b6e  lea     rdx, [rsp+620h+var_5E0]; struct Node
0x180011b73  movdqa  xmmword ptr [rsp+620h+var_5E0.lpVtbl], xmm0
0x180011b79  mov     rcx, r14; this
0x180011b7c  call    ?IsNodeByTag@BasicXmlParser@@IEAAHUNode@Rtl@Microdom@Windows@@PEBU_LUTF8_STRING@@@Z; BasicXmlParser::IsNodeByTag(Windows::Microdom::Rtl::Node,_LUTF8_STRING const *)
0x180011b81  test    eax, eax
0x180011b83  jnz     short loc_180011BE5
0x180011b85  add     ebx, r13d
0x180011b88  mov     eax, ebx
0x180011b8a  cmp     rax, [rsi+8]
0x180011b8e  jb      short loc_180011B2C
0x180011b90  lea     rdx, aFailedToFindWi_1; "Failed to find wifi credential node"
0x180011b97  mov     ecx, r13d
0x180011b9a  call    UnattendLogW
0x180011b9f  mov     ebx, 0Dh
0x180011ba4  mov     r8d, ebx
0x180011ba7  lea     rdx, aFailedToGetWif_2; "failed to get wifi credential: 0x%x"
0x180011bae  mov     ecx, 2
0x180011bb3  call    UnattendLogW
0x180011bb8  mov     eax, ebx
0x180011bba  mov     rcx, [rbp+520h+var_30]
0x180011bc1  xor     rcx, rsp; StackCookie
0x180011bc4  call    __security_check_cookie
0x180011bc9  lea     r11, [rsp+620h+var_20]
0x180011bd1  mov     rbx, [r11+40h]
0x180011bd5  mov     rsi, [r11+48h]
0x180011bd9  mov     rsp, r11
0x180011bdc  pop     r15
0x180011bde  pop     r14
0x180011be0  pop     r13
0x180011be2  pop     rdi
0x180011be3  pop     rbp
0x180011be4  retn
0x180011be5  mov     rcx, [r14+20h]
0x180011be9  lea     rdx, [rbp+520h+var_580]
0x180011bed  movaps  xmm0, [rsp+620h+var_5B0]
0x180011bf2  lea     r9, [rsp+620h+var_5D0]
0x180011bf7  mov     r8d, 6
0x180011bfd  movdqa  xmmword ptr [rsp+620h+var_5F0.lpVtbl], xmm0
0x180011c03  mov     rax, [rcx]
0x180011c06  mov     [rsp+620h+var_5D0], rdx
0x180011c0b  lea     rdx, [rbp+520h+var_5A0]
0x180011c0f  mov     [rsp+620h+var_5E0.lpVtbl], rdx
0x180011c14  lea     rdx, [rsp+620h+var_5F0]
0x180011c19  mov     [rsp+620h+var_5C8], r8
0x180011c1e  mov     rax, [rax+98h]
0x180011c25  mov     [rsp+620h+var_5E0.lpVtbl+8], r8
0x180011c2a  lea     r8, [rsp+620h+var_5E0]
0x180011c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c34  mov     edi, eax
0x180011c36  test    eax, eax
0x180011c38  jns     short loc_180011C4E
0x180011c3a  mov     [rsp+620h+var_5F8], 0DB6h
0x180011c42  lea     r8, aFailedToGetPro_1; "failed to get properties"
0x180011c49  jmp     loc_180011F4C
0x180011c4e  mov     r8, [rbp+520h+var_500]
0x180011c52  xor     ebx, ebx
0x180011c54  test    r8, r8
0x180011c57  jz      loc_180011F2A
0x180011c5d  mov     rax, [r8+8]
0x180011c61  test    rax, rax
0x180011c64  jz      loc_180011F2A
0x180011c6a  xor     esi, esi
0x180011c6c  xor     r15d, r15d
0x180011c6f  test    rax, rax
0x180011c72  jz      loc_180011F16
0x180011c78  mov     rax, [r8]
0x180011c7b  lea     r8, [rsp+620h+var_5B0]
0x180011c80  mov     rcx, [r14+20h]
0x180011c84  mov     edx, r15d
0x180011c87  add     rdx, rdx
0x180011c8a  movups  xmm0, xmmword ptr [rax+rdx*8]
0x180011c8e  mov     rax, [rcx]
0x180011c91  lea     rdx, [rsp+620h+var_5F0]
0x180011c96  movdqu  xmmword ptr [rsp+620h+var_5F0.lpVtbl], xmm0
0x180011c9c  mov     rax, [rax+58h]
0x180011ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ca5  mov     edi, eax
0x180011ca7  test    eax, eax
0x180011ca9  js      loc_180011F0C
0x180011caf  movaps  xmm0, [rsp+620h+var_5B0]
0x180011cb4  lea     r8, ?Utf8WifiTag@SettingXmlParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180011cbb  lea     rdx, [rsp+620h+var_5F0]; struct Node
0x180011cc0  movdqa  xmmword ptr [rsp+620h+var_5F0.lpVtbl], xmm0
0x180011cc6  mov     rcx, r14; this
0x180011cc9  call    ?IsNodeByTag@BasicXmlParser@@IEAAHUNode@Rtl@Microdom@Windows@@PEBU_LUTF8_STRING@@@Z; BasicXmlParser::IsNodeByTag(Windows::Microdom::Rtl::Node,_LUTF8_STRING const *)
0x180011cce  test    eax, eax
0x180011cd0  jz      loc_180011DC4
0x180011cd6  add     esi, r13d
0x180011cd9  cmp     esi, r13d
0x180011cdc  jnz     loc_180011DC4
0x180011ce2  mov     rcx, [r14+20h]
0x180011ce6  lea     r9, [rsp+620h+var_5C0]
0x180011ceb  movaps  xmm0, [rsp+620h+var_5B0]
0x180011cf0  lea     r8, ?Utf8WifiSsidAttrTag@SettingXmlParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const SettingXmlParser::Utf8WifiSsidAttrTag
0x180011cf7  lea     rdx, [rsp+620h+var_5F0]
0x180011cfc  movdqa  xmmword ptr [rsp+620h+var_5F0.lpVtbl], xmm0
0x180011d02  mov     rax, [rcx]
0x180011d05  mov     rax, [rax+108h]
0x180011d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d11  mov     edi, eax
0x180011d13  test    eax, eax
0x180011d15  js      loc_180011E50
0x180011d1b  mov     rcx, [rsp+620h+var_5C0]
0x180011d20  test    rcx, rcx
0x180011d23  jz      loc_180011E50
0x180011d29  cmp     qword ptr [rcx], 0
0x180011d2d  jz      loc_180011E44
0x180011d33  xor     r8d, r8d
0x180011d36  lea     rdx, [rbp+520h+var_4F0]
0x180011d3a  call    winreUtf8ToUnicode
0x180011d3f  mov     ebx, eax
0x180011d41  test    eax, eax
0x180011d43  jnz     loc_180011E3A
0x180011d49  mov     rcx, [r14+20h]
0x180011d4d  lea     r9, [rsp+620h+var_5C0]
0x180011d52  movaps  xmm0, [rsp+620h+var_5B0]
0x180011d57  lea     r8, ?Utf8WifiPasswordAttrTag@SettingXmlParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const SettingXmlParser::Utf8WifiPasswordAttrTag
0x180011d5e  movdqa  xmmword ptr [rsp+620h+var_5F0.lpVtbl], xmm0
0x180011d64  mov     rdx, [rcx]
0x180011d67  mov     rax, [rdx+108h]
0x180011d6e  lea     rdx, [rsp+620h+var_5F0]
0x180011d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d78  mov     edi, eax
0x180011d7a  test    eax, eax
0x180011d7c  js      loc_180011E31
0x180011d82  mov     rcx, [rsp+620h+var_5C0]
0x180011d87  test    rcx, rcx
0x180011d8a  jz      loc_180011E31
0x180011d90  cmp     qword ptr [rcx], 0
0x180011d94  jnz     short loc_180011DAF
0x180011d96  lea     rdx, aEmptyPasswordA; "Empty password attribute."
0x180011d9d  xor     ecx, ecx
0x180011d9f  call    UnattendLogW
0x180011da4  xor     eax, eax
0x180011da6  mov     [rbp+520h+var_290], ax
0x180011dad  jmp     short loc_180011DC4
0x180011daf  xor     r8d, r8d
0x180011db2  lea     rdx, [rbp+520h+var_290]
0x180011db9  call    winreUtf8ToUnicode
0x180011dbe  mov     ebx, eax
0x180011dc0  test    eax, eax
0x180011dc2  jnz     short loc_180011DFD
0x180011dc4  mov     r8, [rbp+520h+var_500]
0x180011dc8  add     r15d, r13d
0x180011dcb  mov     eax, r15d
0x180011dce  cmp     rax, [r8+8]
0x180011dd2  jb      loc_180011C78
0x180011dd8  cmp     esi, r13d
0x180011ddb  jbe     loc_180011E64
0x180011de1  mov     r8d, esi
0x180011de4  lea     rdx, aMultipleWifiNo; "Multiple wifi nodes found: %u"
0x180011deb  mov     ecx, r13d
0x180011dee  call    UnattendLogW
0x180011df3  mov     ebx, 0Dh
0x180011df8  jmp     loc_180011F24
0x180011dfd  mov     [rsp+620h+var_5F8], 0DF4h
0x180011e05  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180011e0c  mov     r9d, ebx
0x180011e0f  lea     r8, aFailedToConver_5; "failed to convert utf8 to unicode"
0x180011e16  mov     [rsp+620h+var_600], rax
0x180011e1b  lea     rdx, aSettingxmlpars_0; "SettingXmlParser::GetWifiCredential %s "...
0x180011e22  mov     ecx, 2
0x180011e27  call    UnattendLogW
0x180011e2c  jmp     loc_180011BA4
0x180011e31  lea     rdx, aFailedToGetPas; "Failed to get password attribute."
0x180011e38  jmp     short loc_180011E57
0x180011e3a  mov     [rsp+620h+var_5F8], 0DE0h
0x180011e42  jmp     short loc_180011E05
0x180011e44  lea     rdx, aEmptySsidAttri; "Empty ssid attribute."
0x180011e4b  jmp     loc_180011B97
0x180011e50  lea     rdx, aFailedToGetSsi; "Failed to get ssid attribute."
0x180011e57  mov     ecx, r13d
0x180011e5a  call    UnattendLogW
0x180011e5f  jmp     loc_180011F24
0x180011e64  test    esi, esi
0x180011e66  jz      loc_180011F16
0x180011e6c  lea     r8, [rbp+520h+var_4F0]
0x180011e70  xor     ecx, ecx
0x180011e72  lea     rdx, aFindWifiNodeSs; "Find wifi node: ssid=%s"
0x180011e79  call    UnattendLogW
0x180011e7e  mov     rcx, [r14+40h]; unsigned __int16 *
0x180011e82  lea     r8, [rbp+520h+var_4F0]; unsigned __int16 *
0x180011e86  mov     r11d, 12Eh
0x180011e8c  mov     edx, r11d; unsigned __int64
0x180011e8f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011e94  mov     esi, eax
0x180011e96  test    eax, eax
0x180011e98  jns     short loc_180011ECE
0x180011e9a  mov     [rsp+620h+var_5F8], 0E08h
0x180011ea2  lea     r8, aFailedToCopySs; "failed to copy ssid"
0x180011ea9  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180011eb0  mov     r9d, esi
0x180011eb3  lea     rdx, aSettingxmlpars_0; "SettingXmlParser::GetWifiCredential %s "...
0x180011eba  mov     [rsp+620h+var_600], rax
0x180011ebf  mov     ecx, 2
0x180011ec4  call    UnattendLogW
0x180011ec9  movzx   ebx, si
0x180011ecc  jmp     short loc_180011F24
0x180011ece  mov     rcx, [r14+40h]
0x180011ed2  lea     r8, [rbp+520h+var_290]; unsigned __int16 *
0x180011ed9  add     rcx, 25Ch; unsigned __int16 *
0x180011ee0  mov     rdx, r11; unsigned __int64
0x180011ee3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011ee8  mov     esi, eax
0x180011eea  test    eax, eax
0x180011eec  jns     short loc_180011EFF
0x180011eee  mov     [rsp+620h+var_5F8], 0E09h
0x180011ef6  lea     r8, aFailedToCopyPa_0; "failed to copy password"
0x180011efd  jmp     short loc_180011EA9
0x180011eff  mov     rax, [r14+40h]
0x180011f03  or      [rax+4CCh], r13d
0x180011f0a  jmp     short loc_180011F24
0x180011f0c  mov     [rsp+620h+var_5F8], 0DC6h
0x180011f14  jmp     short loc_180011F45
0x180011f16  lea     rdx, aNoWifiNodesFou; "No wifi nodes found"
0x180011f1d  xor     ecx, ecx
0x180011f1f  call    UnattendLogW
0x180011f24  test    edi, edi
0x180011f26  jns     short loc_180011F76
0x180011f28  jmp     short loc_180011F6C
0x180011f2a  lea     rdx, aNoNodesFoundUn; "No nodes found under wifi credential"
0x180011f31  xor     ecx, ecx
0x180011f33  call    UnattendLogW
0x180011f38  jmp     loc_180011BB8
0x180011f3d  mov     [rsp+620h+var_5F8], 0DA5h
0x180011f45  lea     r8, aFailedToCast; "failed to cast"
0x180011f4c  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180011f53  mov     r9d, edi
0x180011f56  lea     rdx, aSettingxmlpars_0; "SettingXmlParser::GetWifiCredential %s "...
0x180011f5d  mov     [rsp+620h+var_600], rax
0x180011f62  mov     ecx, 2
0x180011f67  call    UnattendLogW
0x180011f6c  mov     ecx, edi; Status
0x180011f6e  call    cs:__imp_RtlNtStatusToDosError
0x180011f74  mov     ebx, eax
0x180011f76  test    ebx, ebx
0x180011f78  jz      loc_180011BB8
0x180011f7e  jmp     loc_180011BA4
```
