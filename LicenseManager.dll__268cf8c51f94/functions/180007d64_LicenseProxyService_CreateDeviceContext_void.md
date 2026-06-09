# LicenseProxyService::CreateDeviceContext(void)

- ea: `0x180007d64`
- end: `0x1800085d0`
- name: `?CreateDeviceContext@LicenseProxyService@@CA?AVvalue@json@web@@XZ`
- size: `2156`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008e70`
- `0x18003fcd4`

## callees

- `0x1800061e0`
- `0x180007d64`
- `0x180012dc0`
- `0x1800171b0`
- `0x180017200`
- `0x1800178e0`
- `0x180045060`
- `0x180054a54`
- `0x180075e60`
- `0x18007b370`
- `0x18007b630`
- `0x18007cd10`
- `0x18007d1d0`
- `0x180090f34`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007e00`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007e67`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008083`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800080e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000832e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000838b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007e00`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007e67`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008083`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800080e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000832e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000838b`

## string_xrefs

- `0x180007def`: `Software\Microsoft\Windows\CurrentVersion\Store\Configuration`
- `0x180007e5d`: `Software\Microsoft\Windows\CurrentVersion\Store\Configuration`
- `0x180008072`: `Software\Microsoft\Windows\CurrentVersion\Store\Configuration`
- `0x1800080d6`: `Software\Microsoft\Windows\CurrentVersion\Store\Configuration`
- `0x18000831d`: `Software\Microsoft\Windows\CurrentVersion\Store\Configuration`
- `0x180008381`: `Software\Microsoft\Windows\CurrentVersion\Store\Configuration`
- `0x180007e78`: `onecoreuap\enduser\winstore\licensemanager\lib\registry.cpp`
- `0x1800080f1`: `onecoreuap\enduser\winstore\licensemanager\lib\registry.cpp`
- `0x18000839c`: `onecoreuap\enduser\winstore\licensemanager\lib\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall LicenseProxyService::CreateDeviceContext(__int64 a1)
{
  LSTATUS ValueW; // eax
  PVOID *pvData; // rax
  unsigned int v4; // eax
  PVOID *v5; // rcx
  __m128i *v6; // rcx
  int v7; // esi
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  LSTATUS v12; // eax
  PVOID *v13; // rax
  unsigned int v14; // eax
  PVOID *v15; // rcx
  __m128i *v16; // rcx
  int v17; // esi
  __int64 v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rax
  LSTATUS v22; // eax
  PVOID *v23; // rax
  unsigned int v24; // eax
  PVOID *v25; // rcx
  PVOID *v26; // rcx
  __m128i *v27; // rcx
  int v28; // esi
  __int64 v29; // rdi
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-E0h]
  DWORD pcbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v38; // [rsp+48h] [rbp-B8h]
  __int64 v39; // [rsp+50h] [rbp-B0h]
  PVOID v40[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h]
  unsigned __int64 v42; // [rsp+70h] [rbp-90h]
  __int128 v43; // [rsp+78h] [rbp-88h] BYREF
  __m128i v44; // [rsp+88h] [rbp-78h]
  __m128i v45; // [rsp+98h] [rbp-68h] BYREF
  __m128i v46; // [rsp+A8h] [rbp-58h]
  __m128i v47; // [rsp+B8h] [rbp-48h] BYREF
  __m128i si128; // [rsp+C8h] [rbp-38h]
  _BYTE v49[32]; // [rsp+D8h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v39 = a1;
  web::json::value::object(a1, 0);
  v38 = 1;
  *(_OWORD *)v40 = 0;
  v41 = 0;
  v42 = 7;
  LOWORD(v40[0]) = 0;
  pcbData[0] = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Store\\Configuration",
             L"MOID",
             2u,
             0,
             0,
             pcbData);
  if ( ValueW )
  {
    if ( ValueW != 2 )
      goto LABEL_13;
    v41 = 0;
    v5 = v40;
    if ( v42 > 7 )
      v5 = (PVOID *)v40[0];
    *(_WORD *)v5 = 0;
  }
  else
  {
    std::wstring::resize(v40, ((unsigned __int64)pcbData[0] >> 1) + 1, 0);
    pvData = v40;
    if ( v42 > 7 )
      pvData = (PVOID *)v40[0];
    v4 = RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Store\\Configuration",
           L"MOID",
           2u,
           0,
           pvData,
           pcbData);
    if ( v4 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x108,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\registry.cpp",
        (const char *)v4,
        pdwType);
    std::wstring::resize(v40, ((unsigned __int64)pcbData[0] >> 1) - 1, 0);
  }
  if ( v41 )
  {
    v6 = (__m128i *)std::wstring::wstring(v49, v40);
    v7 = 3;
    goto LABEL_14;
  }
LABEL_13:
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v47.m128i_i64[0] = 0x6C006200750050LL;
  v47.m128i_i64[1] = 6488169;
  v6 = &v47;
  v7 = 5;
LABEL_14:
  v38 = v7;
  v45 = 0;
  v46 = 0u;
  v45 = *v6;
  v46 = v6[1];
  v6[1].m128i_i64[0] = 0;
  v6[1].m128i_i64[1] = 7;
  v6->m128i_i16[0] = 0;
  v8 = web::json::value::string(pcbData, &v45);
  v43 = 0;
  v44 = 0;
  v9 = std::wstring::_Calculate_growth(14, 7);
  v10 = std::allocator<unsigned short>::allocate(&v43, v9 + 1);
  *(_QWORD *)&v43 = v10;
  v44.m128i_i64[0] = 14;
  v44.m128i_i64[1] = v9;
  *(_OWORD *)v10 = *(_OWORD *)L"mobileOperator";
  *(_OWORD *)(v10 + 12) = *(_OWORD *)L"Operator";
  *(_WORD *)(v10 + 28) = 0;
  v11 = web::json::value::operator[](a1, &v43);
  web::json::value::operator=(v11, v8);
  if ( v44.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v43, 2 * v44.m128i_i64[1] + 2);
  v44 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v43) = 0;
  if ( *(_QWORD *)pcbData )
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)pcbData + 192LL))(*(_QWORD *)pcbData, 1);
  if ( (v7 & 4) != 0 )
  {
    v7 &= ~4u;
    v38 = v7;
    ContentIdString::~ContentIdString((ContentIdString *)&v47);
  }
  if ( (v7 & 2) != 0 )
  {
    v7 &= ~2u;
    v38 = v7;
    ContentIdString::~ContentIdString((ContentIdString *)v49);
  }
  pcbData[0] = 0;
  v12 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Store\\Configuration",
          L"OEMID",
          2u,
          0,
          0,
          pcbData);
  if ( v12 )
  {
    if ( v12 != 2 )
      goto LABEL_34;
    v41 = 0;
    v15 = v40;
    if ( v42 > 7 )
      v15 = (PVOID *)v40[0];
    *(_WORD *)v15 = 0;
  }
  else
  {
    std::wstring::resize(v40, ((unsigned __int64)pcbData[0] >> 1) + 1, 0);
    v13 = v40;
    if ( v42 > 7 )
      v13 = (PVOID *)v40[0];
    v14 = RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Store\\Configuration",
            L"OEMID",
            2u,
            0,
            v13,
            pcbData);
    if ( v14 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x108,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\registry.cpp",
        (const char *)v14,
        pdwTypea);
    std::wstring::resize(v40, ((unsigned __int64)pcbData[0] >> 1) - 1, 0);
  }
  if ( v41 )
  {
    v16 = (__m128i *)std::wstring::wstring(v49, v40);
    v17 = v7 | 8;
    goto LABEL_35;
  }
LABEL_34:
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v47.m128i_i64[0] = 0x6C006200750050LL;
  v47.m128i_i64[1] = 6488169;
  v16 = &v47;
  v17 = v7 | 0x10;
LABEL_35:
  v38 = v17;
  v45 = 0;
  v46 = 0u;
  v45 = *v16;
  v46 = v16[1];
  v16[1].m128i_i64[0] = 0;
  v16[1].m128i_i64[1] = 7;
  v16->m128i_i16[0] = 0;
  v18 = web::json::value::string(pcbData, &v45);
  v43 = 0;
  v44 = 0;
  v19 = std::wstring::_Calculate_growth(20, 7);
  v20 = std::allocator<unsigned short>::allocate(&v43, v19 + 1);
  *(_QWORD *)&v43 = v20;
  v44.m128i_i64[0] = 20;
  v44.m128i_i64[1] = v19;
  *(_QWORD *)v20 = *(_QWORD *)L"hardwareManufacturer";
  *(_QWORD *)(v20 + 8) = *(_QWORD *)L"wareManufacturer";
  *(_QWORD *)(v20 + 16) = *(_QWORD *)L"Manufacturer";
  *(_QWORD *)(v20 + 24) = *(_QWORD *)L"facturer";
  *(_QWORD *)(v20 + 32) = *(_QWORD *)L"urer";
  *(_WORD *)(v20 + 40) = 0;
  v21 = web::json::value::operator[](a1, &v43);
  web::json::value::operator=(v21, v18);
  if ( v44.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v43, 2 * v44.m128i_i64[1] + 2);
  v44 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v43) = 0;
  if ( *(_QWORD *)pcbData )
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)pcbData + 192LL))(*(_QWORD *)pcbData, 1);
  if ( (v17 & 0x10) != 0 )
  {
    v17 &= ~0x10u;
    v38 = v17;
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v47.m128i_i64[0], 2 * si128.m128i_i64[1] + 2);
  }
  if ( (v17 & 8) != 0 )
  {
    v17 &= ~8u;
    v38 = v17;
    ContentIdString::~ContentIdString((ContentIdString *)v49);
  }
  pcbData[0] = 0;
  v22 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Store\\Configuration",
          L"SCMID",
          2u,
          0,
          0,
          pcbData);
  if ( v22 )
  {
    if ( v22 != 2 )
      goto LABEL_58;
    v41 = 0;
    v25 = v40;
    if ( v42 > 7 )
      v25 = (PVOID *)v40[0];
    *(_WORD *)v25 = 0;
  }
  else
  {
    std::wstring::resize(v40, ((unsigned __int64)pcbData[0] >> 1) + 1, 0);
    v23 = v40;
    if ( v42 > 7 )
      v23 = (PVOID *)v40[0];
    v24 = RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Store\\Configuration",
            L"SCMID",
            2u,
            0,
            v23,
            pcbData);
    if ( v24 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x108,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\registry.cpp",
        (const char *)v24,
        pdwTypeb);
    std::wstring::resize(v40, ((unsigned __int64)pcbData[0] >> 1) - 1, 0);
  }
  v26 = v40;
  if ( v42 > 7 )
    v26 = (PVOID *)v40[0];
  if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v26, v41, &LocaleName, 0) )
  {
    v27 = (__m128i *)std::wstring::wstring(v49, v40);
    v28 = v17 | 0x20;
    goto LABEL_59;
  }
LABEL_58:
  v46 = _mm_load_si128((const __m128i *)&_xmm);
  v45.m128i_i64[0] = 0x6C006200750050LL;
  v45.m128i_i64[1] = 6488169;
  v27 = &v45;
  v28 = v17 | 0x40;
LABEL_59:
  v38 = v28;
  v47 = 0;
  si128 = 0u;
  v47 = *v27;
  si128 = v27[1];
  v27[1].m128i_i64[0] = 0;
  v27[1].m128i_i64[1] = 7;
  v27->m128i_i16[0] = 0;
  v29 = web::json::value::string(pcbData, &v47);
  v43 = 0;
  v44 = 0;
  v30 = std::wstring::_Calculate_growth(12, 7);
  v31 = std::allocator<unsigned short>::allocate(&v43, v30 + 1);
  *(_QWORD *)&v43 = v31;
  v44.m128i_i64[0] = 12;
  v44.m128i_i64[1] = v30;
  *(_QWORD *)v31 = *(_QWORD *)L"hardwareType";
  *(_QWORD *)(v31 + 8) = *(_QWORD *)L"wareType";
  *(_QWORD *)(v31 + 16) = *(_QWORD *)L"Type";
  *(_WORD *)(v31 + 24) = 0;
  v32 = web::json::value::operator[](a1, &v43);
  web::json::value::operator=(v32, v29);
  if ( v44.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v43, 2 * v44.m128i_i64[1] + 2);
  v44 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v43) = 0;
  if ( *(_QWORD *)pcbData )
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)pcbData + 192LL))(*(_QWORD *)pcbData, 1);
  if ( (v28 & 0x40) != 0 )
  {
    LOBYTE(v28) = v28 & 0xBF;
    ContentIdString::~ContentIdString((ContentIdString *)&v45);
  }
  if ( (v28 & 0x20) != 0 )
    ContentIdString::~ContentIdString((ContentIdString *)v49);
  if ( v42 > 7 )
    std::_Deallocate<16>(v40[0], 2 * v42 + 2);
  return a1;
}

```

## disassembly

```asm
0x180007d64  push    rbp
0x180007d66  push    rbx
0x180007d67  push    rsi
0x180007d68  push    rdi
0x180007d69  push    r12
0x180007d6b  push    r13
0x180007d6d  push    r14
0x180007d6f  push    r15
0x180007d71  lea     rbp, [rsp-8]
0x180007d76  sub     rsp, 108h
0x180007d7d  mov     rax, cs:__security_cookie
0x180007d84  xor     rax, rsp
0x180007d87  mov     [rbp+40h+var_48], rax
0x180007d8b  mov     r14, rcx
0x180007d8e  mov     [rsp+140h+var_F0], rcx
0x180007d93  xor     r12d, r12d
0x180007d96  mov     [rsp+140h+var_F8], r12d
0x180007d9b  xor     edx, edx
0x180007d9d  call    ?object@value@json@web@@SA?AV123@_N@Z; web::json::value::object(bool)
0x180007da2  mov     [rsp+140h+var_F8], 1
0x180007daa  xorps   xmm0, xmm0
0x180007dad  movups  xmmword ptr [rsp+140h+var_E8], xmm0
0x180007db2  mov     [rsp+140h+var_D8], r12
0x180007db7  lea     r13d, [r12+7]
0x180007dbc  mov     [rsp+140h+var_D0], r13
0x180007dc1  mov     word ptr [rsp+140h+var_E8], r12w
0x180007dc7  mov     [rsp+140h+var_100], r12d
0x180007dcc  lea     rax, [rsp+140h+var_100]
0x180007dd1  mov     [rsp+140h+pcbData], rax; pcbData
0x180007dd6  mov     [rsp+140h+pvData], r12; pvData
0x180007ddb  mov     [rsp+140h+pdwType], r12; pdwType
0x180007de0  lea     ebx, [r12+2]
0x180007de5  mov     r9d, ebx; dwFlags
0x180007de8  lea     r8, Value; "MOID"
0x180007def  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180007df6  mov     rdi, 0FFFFFFFF80000002h
0x180007dfd  mov     rcx, rdi; hkey
0x180007e00  call    cs:__imp_RegGetValueW
0x180007e06  mov     rdx, 6C006200750050h
0x180007e10  test    eax, eax
0x180007e12  jnz     loc_180007EAD
0x180007e18  xor     r8d, r8d
0x180007e1b  mov     edx, [rsp+140h+var_100]
0x180007e1f  shr     rdx, 1
0x180007e22  inc     rdx
0x180007e25  lea     rcx, [rsp+140h+var_E8]
0x180007e2a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180007e2f  lea     rax, [rsp+140h+var_E8]
0x180007e34  cmp     [rsp+140h+var_D0], r13
0x180007e39  cmova   rax, [rsp+140h+var_E8]
0x180007e3f  lea     rcx, [rsp+140h+var_100]
0x180007e44  mov     [rsp+140h+pcbData], rcx; pcbData
0x180007e49  mov     [rsp+140h+pvData], rax; pvData
0x180007e4e  mov     [rsp+140h+pdwType], r12; unsigned int
0x180007e53  mov     r9d, ebx; dwFlags
0x180007e56  lea     r8, Value; "MOID"
0x180007e5d  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180007e64  mov     rcx, rdi; hkey
0x180007e67  call    cs:__imp_RegGetValueW
0x180007e6d  mov     rcx, [rbp+48h]; this
0x180007e71  test    eax, eax
0x180007e73  jz      short loc_180007E8A
0x180007e75  mov     r9d, eax; char *
0x180007e78  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\licensem"...
0x180007e7f  mov     edx, 108h; void *
0x180007e84  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180007e8a  xor     r8d, r8d
0x180007e8d  mov     edx, [rsp+140h+var_100]
0x180007e91  shr     rdx, 1
0x180007e94  dec     rdx
0x180007e97  lea     rcx, [rsp+140h+var_E8]
0x180007e9c  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180007ea1  mov     rdx, 6C006200750050h
0x180007eab  jmp     short loc_180007ECA
0x180007ead  cmp     eax, ebx
0x180007eaf  jnz     short loc_180007EE9
0x180007eb1  mov     [rsp+140h+var_D8], r12
0x180007eb6  lea     rcx, [rsp+140h+var_E8]
0x180007ebb  cmp     [rsp+140h+var_D0], r13
0x180007ec0  cmova   rcx, [rsp+140h+var_E8]
0x180007ec6  mov     [rcx], r12w
0x180007eca  cmp     [rsp+140h+var_D8], r12
0x180007ecf  jz      short loc_180007EE9
0x180007ed1  lea     rdx, [rsp+140h+var_E8]
0x180007ed6  lea     rcx, [rbp+40h+var_68]
0x180007eda  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180007edf  mov     rcx, rax
0x180007ee2  mov     esi, 3
0x180007ee7  jmp     short loc_180007F16
0x180007ee9  xorps   xmm0, xmm0
0x180007eec  movups  [rbp+40h+var_88], xmm0
0x180007ef0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000006
0x180007ef8  movdqu  [rbp+40h+var_78], xmm1
0x180007efd  mov     qword ptr [rbp+40h+var_88], rdx
0x180007f01  mov     dword ptr [rbp+40h+var_88+8], 630069h
0x180007f08  mov     word ptr [rbp+40h+var_88+0Ch], r12w
0x180007f0d  lea     rcx, [rbp+40h+var_88]
0x180007f11  mov     esi, 5
0x180007f16  mov     [rsp+140h+var_F8], esi
0x180007f1a  xorps   xmm0, xmm0
0x180007f1d  movups  [rbp+40h+var_A8], xmm0
0x180007f21  mov     qword ptr [rbp+40h+var_98], r12
0x180007f25  mov     qword ptr [rbp+40h+var_98+8], r12
0x180007f29  movups  xmm0, xmmword ptr [rcx]
0x180007f2c  movups  [rbp+40h+var_A8], xmm0
0x180007f30  movups  xmm1, xmmword ptr [rcx+10h]
0x180007f34  movups  [rbp+40h+var_98], xmm1
0x180007f38  mov     [rcx+10h], r12
0x180007f3c  mov     [rcx+18h], r13
0x180007f40  mov     [rcx], r12w
0x180007f44  lea     rdx, [rbp+40h+var_A8]
0x180007f48  lea     rcx, [rsp+140h+var_100]
0x180007f4d  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x180007f52  mov     rdi, rax
0x180007f55  xorps   xmm0, xmm0
0x180007f58  movups  [rsp+140h+var_C8], xmm0
0x180007f5d  xorps   xmm1, xmm1
0x180007f60  movdqu  [rbp+40h+var_B8], xmm1
0x180007f65  mov     r8, 7FFFFFFFFFFFFFFEh
0x180007f6f  mov     rdx, r13
0x180007f72  mov     r15d, 0Eh
0x180007f78  mov     ecx, r15d
0x180007f7b  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180007f80  mov     rbx, rax
0x180007f83  lea     rdx, [rax+1]
0x180007f87  lea     rcx, [rsp+140h+var_C8]
0x180007f8c  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180007f91  mov     qword ptr [rsp+140h+var_C8], rax
0x180007f96  mov     qword ptr [rbp+40h+var_B8], r15
0x180007f9a  mov     qword ptr [rbp+40h+var_B8+8], rbx
0x180007f9e  movups  xmm0, xmmword ptr cs:aMobileoperator; "mobileOperator"
0x180007fa5  movups  xmmword ptr [rax], xmm0
0x180007fa8  movups  xmm1, xmmword ptr cs:aMobileoperator+0Ch; "Operator"
0x180007faf  movups  xmmword ptr [rax+0Ch], xmm1
0x180007fb3  mov     [rax+1Ch], r12w
0x180007fb8  lea     rdx, [rsp+140h+var_C8]
0x180007fbd  mov     rcx, r14
0x180007fc0  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x180007fc5  mov     rcx, rax
0x180007fc8  mov     rdx, rdi
0x180007fcb  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180007fd0  nop
0x180007fd1  mov     rdx, qword ptr [rbp+40h+var_B8+8]
0x180007fd5  cmp     rdx, r13
0x180007fd8  jbe     short loc_180007FEC
0x180007fda  lea     rdx, ds:2[rdx*2]
0x180007fe2  mov     rcx, qword ptr [rsp+140h+var_C8]
0x180007fe7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180007fec  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180007ff4  movdqu  [rbp+40h+var_B8], xmm0
0x180007ff9  mov     word ptr [rsp+140h+var_C8], r12w
0x180007fff  mov     rcx, qword ptr [rsp+140h+var_100]
0x180008004  test    rcx, rcx
0x180008007  jz      short loc_18000801E
0x180008009  mov     rax, [rcx]
0x18000800c  mov     edx, 1
0x180008011  mov     rax, [rax+0C0h]
0x180008018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000801d  nop
0x18000801e  test    sil, 4
0x180008022  jz      short loc_180008035
0x180008024  and     esi, 0FFFFFFFBh
0x180008027  mov     [rsp+140h+var_F8], esi
0x18000802b  lea     rcx, [rbp+40h+var_88]; this
0x18000802f  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180008034  nop
0x180008035  mov     ebx, 2
0x18000803a  test    bl, sil
0x18000803d  jz      short loc_18000804F
0x18000803f  and     esi, 0FFFFFFFDh
0x180008042  mov     [rsp+140h+var_F8], esi
0x180008046  lea     rcx, [rbp+40h+var_68]; this
0x18000804a  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18000804f  mov     [rsp+140h+var_100], r12d
0x180008054  lea     rax, [rsp+140h+var_100]
0x180008059  mov     [rsp+140h+pcbData], rax; pcbData
0x18000805e  mov     [rsp+140h+pvData], r12; pvData
0x180008063  mov     [rsp+140h+pdwType], r12; pdwType
0x180008068  mov     r9d, ebx; dwFlags
0x18000806b  lea     r8, aOemid; "OEMID"
0x180008072  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180008079  mov     rdi, 0FFFFFFFF80000002h
0x180008080  mov     rcx, rdi; hkey
0x180008083  call    cs:__imp_RegGetValueW
0x180008089  test    eax, eax
0x18000808b  jnz     loc_18000811C
0x180008091  xor     r8d, r8d
0x180008094  mov     edx, [rsp+140h+var_100]
0x180008098  shr     rdx, 1
0x18000809b  inc     rdx
0x18000809e  lea     rcx, [rsp+140h+var_E8]
0x1800080a3  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800080a8  lea     rax, [rsp+140h+var_E8]
0x1800080ad  cmp     [rsp+140h+var_D0], r13
0x1800080b2  cmova   rax, [rsp+140h+var_E8]
0x1800080b8  lea     rcx, [rsp+140h+var_100]
0x1800080bd  mov     [rsp+140h+pcbData], rcx; pcbData
0x1800080c2  mov     [rsp+140h+pvData], rax; pvData
0x1800080c7  mov     [rsp+140h+pdwType], r12; unsigned int
0x1800080cc  mov     r9d, ebx; dwFlags
0x1800080cf  lea     r8, aOemid; "OEMID"
0x1800080d6  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800080dd  mov     rcx, rdi; hkey
0x1800080e0  call    cs:__imp_RegGetValueW
0x1800080e6  mov     rcx, [rbp+48h]; this
0x1800080ea  test    eax, eax
0x1800080ec  jz      short loc_180008103
0x1800080ee  mov     r9d, eax; char *
0x1800080f1  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800080f8  mov     edx, 108h; void *
0x1800080fd  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180008103  xor     r8d, r8d
0x180008106  mov     edx, [rsp+140h+var_100]
0x18000810a  shr     rdx, 1
0x18000810d  dec     rdx
0x180008110  lea     rcx, [rsp+140h+var_E8]
0x180008115  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000811a  jmp     short loc_180008139
0x18000811c  cmp     eax, ebx
0x18000811e  jnz     short loc_180008156
0x180008120  mov     [rsp+140h+var_D8], r12
0x180008125  lea     rcx, [rsp+140h+var_E8]
0x18000812a  cmp     [rsp+140h+var_D0], r13
0x18000812f  cmova   rcx, [rsp+140h+var_E8]
0x180008135  mov     [rcx], r12w
0x180008139  cmp     [rsp+140h+var_D8], r12
0x18000813e  jz      short loc_180008156
0x180008140  lea     rdx, [rsp+140h+var_E8]
0x180008145  lea     rcx, [rbp+40h+var_68]
0x180008149  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000814e  mov     rcx, rax
0x180008151  or      esi, 8
0x180008154  jmp     short loc_18000818B
0x180008156  xorps   xmm0, xmm0
0x180008159  movups  [rbp+40h+var_88], xmm0
0x18000815d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000006
0x180008165  movdqu  [rbp+40h+var_78], xmm1
0x18000816a  mov     rax, 6C006200750050h
0x180008174  mov     qword ptr [rbp+40h+var_88], rax
0x180008178  mov     dword ptr [rbp+40h+var_88+8], 630069h
0x18000817f  mov     word ptr [rbp+40h+var_88+0Ch], r12w
0x180008184  lea     rcx, [rbp+40h+var_88]
0x180008188  or      esi, 10h
0x18000818b  mov     [rsp+140h+var_F8], esi
0x18000818f  xorps   xmm0, xmm0
0x180008192  movups  [rbp+40h+var_A8], xmm0
0x180008196  mov     qword ptr [rbp+40h+var_98], r12
0x18000819a  mov     qword ptr [rbp+40h+var_98+8], r12
0x18000819e  movups  xmm0, xmmword ptr [rcx]
0x1800081a1  movups  [rbp+40h+var_A8], xmm0
0x1800081a5  movups  xmm1, xmmword ptr [rcx+10h]
0x1800081a9  movups  [rbp+40h+var_98], xmm1
0x1800081ad  mov     [rcx+10h], r12
0x1800081b1  mov     [rcx+18h], r13
0x1800081b5  mov     [rcx], r12w
0x1800081b9  lea     rdx, [rbp+40h+var_A8]
0x1800081bd  lea     rcx, [rsp+140h+var_100]
0x1800081c2  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x1800081c7  mov     rdi, rax
0x1800081ca  xorps   xmm0, xmm0
0x1800081cd  movups  [rsp+140h+var_C8], xmm0
0x1800081d2  xorps   xmm1, xmm1
0x1800081d5  movdqu  [rbp+40h+var_B8], xmm1
0x1800081da  mov     r8, 7FFFFFFFFFFFFFFEh
0x1800081e4  mov     rdx, r13
0x1800081e7  mov     r15d, 14h
0x1800081ed  mov     ecx, r15d
0x1800081f0  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800081f5  mov     rbx, rax
0x1800081f8  lea     rdx, [rax+1]
0x1800081fc  lea     rcx, [rsp+140h+var_C8]
0x180008201  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180008206  mov     rcx, rax
0x180008209  mov     qword ptr [rsp+140h+var_C8], rax
0x18000820e  mov     qword ptr [rbp+40h+var_B8], r15
0x180008212  mov     qword ptr [rbp+40h+var_B8+8], rbx
0x180008216  mov     rax, qword ptr cs:aHardwaremanufa; "hardwareManufacturer"
0x18000821d  mov     [rcx], rax
0x180008220  mov     rax, qword ptr cs:aHardwaremanufa+8; "wareManufacturer"
0x180008227  mov     [rcx+8], rax
0x18000822b  mov     rax, qword ptr cs:aHardwaremanufa+10h; "Manufacturer"
0x180008232  mov     [rcx+10h], rax
0x180008236  mov     rax, qword ptr cs:aHardwaremanufa+18h; "facturer"
0x18000823d  mov     [rcx+18h], rax
0x180008241  mov     rax, qword ptr cs:aHardwaremanufa+20h; "urer"
0x180008248  mov     [rcx+20h], rax
0x18000824c  mov     [rcx+28h], r12w
0x180008251  lea     rdx, [rsp+140h+var_C8]
0x180008256  mov     rcx, r14
0x180008259  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18000825e  mov     rcx, rax
0x180008261  mov     rdx, rdi
0x180008264  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180008269  nop
0x18000826a  mov     rdx, qword ptr [rbp+40h+var_B8+8]
0x18000826e  cmp     rdx, r13
0x180008271  jbe     short loc_180008285
0x180008273  lea     rdx, ds:2[rdx*2]
0x18000827b  mov     rcx, qword ptr [rsp+140h+var_C8]
0x180008280  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
  ... truncated ...
```
