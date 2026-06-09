# Windows::WU::WuProvider::SetServiceId(wil::com_ptr_t<IUpdateSearcher,wil::err_exception_policy>,Windows::WU::WUService const &)

- ea: `0x1402d6870`
- end: `0x1402d6cf2`
- name: `?SetServiceId@WuProvider@WU@Windows@@QEAAXV?$com_ptr_t@UIUpdateSearcher@@Uerr_exception_policy@wil@@@wil@@AEBW4WUService@23@@Z`
- size: `1154`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1402cf4cc`
- `0x1402d0950`

## callees

- `0x14003fee4`
- `0x1400413a8`
- `0x140041b3c`
- `0x14004296c`
- `0x140043354`
- `0x140043814`
- `0x1400447ac`
- `0x140045404`
- `0x1400574cc`
- `0x140072104`
- `0x1402d6870`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1402d6a34`
- `OLEAUT32!__imp_SysAllocString` at `0x1402d6a5d`
- `OLEAUT32!__imp_SysAllocString` at `0x1402d6b54`
- `OLEAUT32!__imp_SysAllocString` at `0x1402d6a34`
- `OLEAUT32!__imp_SysAllocString` at `0x1402d6a5d`
- `OLEAUT32!__imp_SysAllocString` at `0x1402d6b54`
- `OLEAUT32!__imp_SysFreeString` at `0x1402d6aaa`
- `OLEAUT32!__imp_SysFreeString` at `0x1402d6ab4`
- `OLEAUT32!__imp_SysFreeString` at `0x1402d6b0d`
- `OLEAUT32!__imp_SysFreeString` at `0x1402d6b8f`
- `OLEAUT32!__imp_SysFreeString` at `0x1402d6aaa`
- `OLEAUT32!__imp_SysFreeString` at `0x1402d6ab4`
- `OLEAUT32!__imp_SysFreeString` at `0x1402d6b0d`
- `OLEAUT32!__imp_SysFreeString` at `0x1402d6b8f`

## string_xrefs

- `0x1402d6c7d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1402d6c8f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1402d6ce0`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1402d6be9`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuProvider.cpp`
- `0x1402d6c0e`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuProvider.cpp`
- `0x1402d6c23`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuProvider.cpp`
- `0x1402d6c50`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuProvider.cpp`
- `0x1402d6c65`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuProvider.cpp`
- `0x1402d6ca4`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuProvider.cpp`
- `0x1402d6cb9`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuProvider.cpp`
- `0x1402d6cce`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuProvider.cpp`
- `0x1402d6a56`: `USO scan cab service`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Windows::WU::WuProvider::SetServiceId(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rax
  int v8; // eax
  const OLECHAR *v9; // rdi
  void ***v10; // rcx
  const OLECHAR *v11; // rax
  struct std::error_code *v12; // r8
  bool v13; // al
  const struct std::filesystem::path *v14; // r9
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, BSTR, OLECHAR *, _QWORD); // r13
  __int64 v20; // rcx
  const char *v21; // r9
  OLECHAR *v22; // r14
  BSTR v23; // rax
  const char *v24; // r9
  OLECHAR *v25; // rdi
  int v26; // eax
  __int64 *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // eax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, BSTR); // r14
  __int64 v33; // rax
  BSTR v34; // rax
  const char *v35; // r9
  OLECHAR *v36; // rbx
  int v37; // eax
  __int64 result; // rax
  int v39; // [rsp+20h] [rbp-99h]
  int v40; // [rsp+20h] [rbp-99h]
  char v41[8]; // [rsp+40h] [rbp-79h] BYREF
  void ***v42; // [rsp+48h] [rbp-71h]
  _BYTE v43[32]; // [rsp+60h] [rbp-59h] BYREF
  OLECHAR *v44; // [rsp+80h] [rbp-39h]
  _QWORD *v45; // [rsp+88h] [rbp-31h]
  __int64 v46; // [rsp+90h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-21h] BYREF
  __int128 v48; // [rsp+A0h] [rbp-19h] BYREF
  unsigned int v49; // [rsp+B0h] [rbp-9h]
  _BYTE v50[32]; // [rsp+B8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v45 = a2;
  if ( !*a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x367,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuProvider.cpp",
      (const char *)0x80070057LL,
      v39);
  v6 = qword_140549FC0;
  v7 = *(_QWORD *)(qword_140549FC0 + 8);
  for ( HIDWORD(v42) = 0; !*(_BYTE *)(v7 + 25); v7 = *(_QWORD *)v7 )
  {
    if ( *(_DWORD *)(v7 + 32) >= *a3 )
      v6 = v7;
    else
      v7 += 16;
  }
  if ( *(_BYTE *)(v6 + 25) || *a3 < *(_DWORD *)(v6 + 32) )
    std::_Xout_of_range("invalid map<K, T> key");
  v48 = *(_OWORD *)(v6 + 40);
  v49 = *(_DWORD *)(v6 + 56);
  std::wstring::wstring(v50, v6 + 64);
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, v49);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x36A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuProvider.cpp",
      (const char *)(unsigned int)v8,
      v39);
  if ( v49 == 3 )
  {
    if ( *(_BYTE *)(a1 + 104) && *a3 == 4 )
    {
      v9 = (const OLECHAR *)(a1 + 72);
      v10 = *(void ****)(a1 + 88);
      v11 = (const OLECHAR *)(a1 + 72);
      if ( *(_QWORD *)(a1 + 96) > 7u )
        v11 = *(const OLECHAR **)v9;
      *(_QWORD *)v41 = v11;
      v42 = v10;
      std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v43, v41);
      *(_QWORD *)v41 = 0;
      v42 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
      v13 = std::filesystem::exists((std::filesystem *)v43, (const struct std::filesystem::path *)v41, v12);
      if ( *(_DWORD *)v41 )
        std::filesystem::_Throw_fs_error((std::filesystem *)"exists", v41, (const struct std::error_code *)v43, v14);
      if ( !v13 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x370,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuProvider.cpp",
          (const char *)0x80070002LL,
          v39);
      std::wstring::~wstring(v43);
      v46 = 0;
      v15 = *(__int64 **)(a1 + 8);
      v16 = *v15;
      v46 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v16 + 136))(v15, &v46);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x372,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuProvider.cpp",
          (const char *)(unsigned int)v17,
          v39);
      v18 = v46;
      v19 = *(__int64 (__fastcall **)(__int64, BSTR, OLECHAR *, _QWORD))(*(_QWORD *)v46 + 96LL);
      v20 = *(_QWORD *)(a1 + 16);
      *(_QWORD *)(a1 + 16) = 0;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( !*(_BYTE *)(a1 + 104) )
        std::_Throw_bad_optional_access();
      if ( *(_QWORD *)(a1 + 96) > 7u )
        v9 = *(const OLECHAR **)v9;
      v22 = SysAllocString(v9);
      v44 = v22;
      if ( !v22 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x138D,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v21);
      v23 = SysAllocString(L"USO scan cab service");
      v25 = v23;
      *(_QWORD *)v41 = v23;
      if ( !v23 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x138D,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v24);
      v40 = a1 + 16;
      v26 = v19(v18, v23, v22, 0);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x377,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuProvider.cpp",
          (const char *)(unsigned int)v26,
          v40);
      SysFreeString(v25);
      SysFreeString(v22);
      bstrString = 0;
      v27 = *(__int64 **)(a1 + 16);
      v28 = *v27;
      bstrString = 0;
      v29 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v28 + 120))(v27, &bstrString);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x37A,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuProvider.cpp",
          (const char *)(unsigned int)v29,
          v40);
      v30 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(*(_QWORD *)*a2 + 192LL))(*a2, bstrString);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x37B,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuProvider.cpp",
          (const char *)(unsigned int)v30,
          v40);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v46 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    else
    {
      v31 = *a2;
      v32 = *(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)*a2 + 192LL);
      v33 = Windows::Strings::to_wstring(v43, &v48);
      if ( *(_QWORD *)(v33 + 24) > 7u )
        v33 = *(_QWORD *)v33;
      v34 = SysAllocString((const OLECHAR *)v33);
      v36 = v34;
      *(_QWORD *)v41 = v34;
      if ( !v34 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x138D,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v35);
      v37 = v32(v31, v34);
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x37F,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuProvider.cpp",
          (const char *)(unsigned int)v37,
          v39);
      SysFreeString(v36);
      std::wstring::~wstring(v43);
    }
  }
  result = std::wstring::~wstring(v50);
  if ( *a2 )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  return result;
}

```

## disassembly

```asm
0x1402d6870  mov     [rsp-8+arg_10], rbx
0x1402d6875  mov     [rsp-8+arg_8], rdx
0x1402d687a  push    rbp
0x1402d687b  push    rsi
0x1402d687c  push    rdi
0x1402d687d  push    r12
0x1402d687f  push    r13
0x1402d6881  push    r14
0x1402d6883  push    r15
0x1402d6885  lea     rbp, [rsp-27h]
0x1402d688a  sub     rsp, 0E0h
0x1402d6891  mov     rax, cs:__security_cookie
0x1402d6898  xor     rax, rsp
0x1402d689b  mov     [rbp+57h+var_38], rax
0x1402d689f  mov     rbx, r8
0x1402d68a2  mov     rsi, rdx
0x1402d68a5  mov     r15, rcx
0x1402d68a8  mov     [rbp+57h+var_88], rdx
0x1402d68ac  xor     r12d, r12d
0x1402d68af  mov     [rsp+110h+var_E0], r12d
0x1402d68b4  mov     rcx, [rbp+5Fh]; this
0x1402d68b8  cmp     [rdx], r12
0x1402d68bb  jz      loc_1402D6C08
0x1402d68c1  mov     rdx, cs:qword_140549FC0
0x1402d68c8  mov     rax, [rdx+8]
0x1402d68cc  xor     ecx, ecx
0x1402d68ce  mov     [rbp+57h+var_C4], ecx
0x1402d68d1  cmp     [rax+19h], r12b
0x1402d68d5  jnz     short loc_1402D68F1
0x1402d68d7  mov     ecx, [r8]
0x1402d68da  cmp     [rax+20h], ecx
0x1402d68dd  jge     short loc_1402D68E5
0x1402d68df  add     rax, 10h
0x1402d68e3  jmp     short loc_1402D68E8
0x1402d68e5  mov     rdx, rax
0x1402d68e8  mov     rax, [rax]
0x1402d68eb  cmp     [rax+19h], r12b
0x1402d68ef  jz      short loc_1402D68DA
0x1402d68f1  cmp     [rdx+19h], r12b
0x1402d68f5  jnz     loc_1402D6BFB
0x1402d68fb  mov     eax, [rdx+20h]
0x1402d68fe  cmp     [r8], eax
0x1402d6901  jl      loc_1402D6BFB
0x1402d6907  movups  xmm0, xmmword ptr [rdx+28h]
0x1402d690b  movdqu  [rbp+57h+var_70], xmm0
0x1402d6910  mov     eax, [rdx+38h]
0x1402d6913  mov     [rbp+57h+var_60], eax
0x1402d6916  add     rdx, 40h ; '@'
0x1402d691a  lea     rcx, [rbp+57h+var_58]
0x1402d691e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1402d6923  nop
0x1402d6924  mov     rcx, [rsi]
0x1402d6927  mov     rax, [rcx]
0x1402d692a  mov     edx, [rbp+57h+var_60]
0x1402d692d  mov     rax, [rax+70h]
0x1402d6931  call    _guard_dispatch_icall
0x1402d6936  mov     rcx, [rbp+5Fh]; this
0x1402d693a  test    eax, eax
0x1402d693c  js      loc_1402D6C20
0x1402d6942  cmp     [rbp+57h+var_60], 3
0x1402d6946  jnz     loc_1402D6BA0
0x1402d694c  cmp     [r15+68h], r12b
0x1402d6950  jz      loc_1402D6B2C
0x1402d6956  cmp     dword ptr [rbx], 4
0x1402d6959  jnz     loc_1402D6B2C
0x1402d695f  lea     rdi, [r15+48h]
0x1402d6963  mov     rcx, [rdi+10h]
0x1402d6967  mov     rax, rdi
0x1402d696a  cmp     qword ptr [rdi+18h], 7
0x1402d696f  jbe     short loc_1402D6974
0x1402d6971  mov     rax, [rdi]
0x1402d6974  mov     qword ptr [rbp+57h+var_D0], rax
0x1402d6978  mov     [rbp-71h], rcx
0x1402d697c  lea     rdx, [rbp+57h+var_D0]
0x1402d6980  lea     rcx, [rbp+57h+var_B0]
0x1402d6984  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x1402d6989  nop
0x1402d698a  mov     qword ptr [rbp+57h+var_D0], r12
0x1402d698e  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1402d6995  mov     [rbp-71h], rax
0x1402d6999  lea     rdx, [rbp+57h+var_D0]; struct std::filesystem::path *
0x1402d699d  lea     rcx, [rbp+57h+var_B0]; this
0x1402d69a1  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x1402d69a6  cmp     dword ptr [rbp+57h+var_D0], r12d
0x1402d69aa  jnz     loc_1402D6C35
0x1402d69b0  mov     rcx, [rbp+5Fh]; this
0x1402d69b4  test    al, al
0x1402d69b6  jz      loc_1402D6C4A
0x1402d69bc  lea     rcx, [rbp+57h+var_B0]
0x1402d69c0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402d69c5  mov     [rbp+57h+var_80], r12
0x1402d69c9  mov     rcx, [r15+8]
0x1402d69cd  mov     rax, [rcx]
0x1402d69d0  mov     [rbp+57h+var_80], r12
0x1402d69d4  lea     rdx, [rbp+57h+var_80]
0x1402d69d8  mov     rax, [rax+88h]
0x1402d69df  call    _guard_dispatch_icall
0x1402d69e4  mov     rcx, [rbp+5Fh]; this
0x1402d69e8  test    eax, eax
0x1402d69ea  js      loc_1402D6C62
0x1402d69f0  mov     rbx, [rbp+57h+var_80]
0x1402d69f4  mov     rax, [rbx]
0x1402d69f7  mov     r13, [rax+60h]
0x1402d69fb  lea     r12, [r15+10h]
0x1402d69ff  mov     rcx, [r12]
0x1402d6a03  mov     qword ptr [r12], 0
0x1402d6a0b  test    rcx, rcx
0x1402d6a0e  jz      short loc_1402D6A1D
0x1402d6a10  mov     rax, [rcx]
0x1402d6a13  mov     rax, [rax+10h]
0x1402d6a17  call    _guard_dispatch_icall
0x1402d6a1c  nop
0x1402d6a1d  cmp     byte ptr [rdi+20h], 0
0x1402d6a21  jz      loc_1402D6C77
0x1402d6a27  cmp     qword ptr [rdi+18h], 7
0x1402d6a2c  jbe     short loc_1402D6A31
0x1402d6a2e  mov     rdi, [rdi]
0x1402d6a31  mov     rcx, rdi; psz
0x1402d6a34  call    cs:__imp_SysAllocString
0x1402d6a3a  mov     r14, rax
0x1402d6a3d  mov     [rbp+57h+var_90], rax
0x1402d6a41  mov     [rsp+110h+var_E0], 0Ah
0x1402d6a49  mov     rcx, [rbp+5Fh]; this
0x1402d6a4d  test    rax, rax
0x1402d6a50  jz      loc_1402D6C7D
0x1402d6a56  lea     rcx, aUsoScanCabServ; "USO scan cab service"
0x1402d6a5d  call    cs:__imp_SysAllocString
0x1402d6a63  mov     rdi, rax
0x1402d6a66  mov     qword ptr [rbp+57h+var_D0], rax
0x1402d6a6a  mov     [rsp+110h+var_E0], 0Eh
0x1402d6a72  mov     rcx, [rbp+5Fh]; this
0x1402d6a76  test    rax, rax
0x1402d6a79  jz      loc_1402D6C8F
0x1402d6a7f  mov     qword ptr [rsp+110h+var_F0], r12; int
0x1402d6a84  xor     r9d, r9d
0x1402d6a87  mov     r8, r14
0x1402d6a8a  mov     rdx, rax
0x1402d6a8d  mov     rcx, rbx
0x1402d6a90  mov     rax, r13
0x1402d6a93  call    _guard_dispatch_icall
0x1402d6a98  mov     rcx, [rbp+5Fh]; this
0x1402d6a9c  xor     r12d, r12d
0x1402d6a9f  test    eax, eax
0x1402d6aa1  js      loc_1402D6CA1
0x1402d6aa7  mov     rcx, rdi; bstrString
0x1402d6aaa  call    cs:__imp_SysFreeString
0x1402d6ab0  nop
0x1402d6ab1  mov     rcx, r14; bstrString
0x1402d6ab4  call    cs:__imp_SysFreeString
0x1402d6aba  mov     [rbp+57h+bstrString], r12
0x1402d6abe  mov     rcx, [r15+10h]
0x1402d6ac2  mov     rax, [rcx]
0x1402d6ac5  mov     [rbp+57h+bstrString], r12
0x1402d6ac9  lea     rdx, [rbp+57h+bstrString]
0x1402d6acd  mov     rax, [rax+78h]
0x1402d6ad1  call    _guard_dispatch_icall
0x1402d6ad6  mov     rcx, [rbp+5Fh]; this
0x1402d6ada  test    eax, eax
0x1402d6adc  js      loc_1402D6CB6
0x1402d6ae2  mov     rcx, [rsi]
0x1402d6ae5  mov     rax, [rcx]
0x1402d6ae8  mov     rdx, [rbp+57h+bstrString]
0x1402d6aec  mov     rax, [rax+0C0h]
0x1402d6af3  call    _guard_dispatch_icall
0x1402d6af8  mov     rcx, [rbp+5Fh]; this
0x1402d6afc  test    eax, eax
0x1402d6afe  js      loc_1402D6CCB
0x1402d6b04  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1402d6b08  test    rcx, rcx
0x1402d6b0b  jz      short loc_1402D6B14
0x1402d6b0d  call    cs:__imp_SysFreeString
0x1402d6b13  nop
0x1402d6b14  mov     rcx, [rbp+57h+var_80]
0x1402d6b18  test    rcx, rcx
0x1402d6b1b  jz      short loc_1402D6B2A
0x1402d6b1d  mov     rax, [rcx]
0x1402d6b20  mov     rax, [rax+10h]
0x1402d6b24  call    _guard_dispatch_icall
0x1402d6b29  nop
0x1402d6b2a  jmp     short loc_1402D6BA0
0x1402d6b2c  mov     rdi, [rsi]
0x1402d6b2f  mov     rax, [rdi]
0x1402d6b32  mov     r14, [rax+0C0h]
0x1402d6b39  lea     rdx, [rbp+57h+var_70]
0x1402d6b3d  lea     rcx, [rbp+57h+var_B0]
0x1402d6b41  call    ?to_wstring@Strings@Windows@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; Windows::Strings::to_wstring(_GUID const &)
0x1402d6b46  nop
0x1402d6b47  cmp     qword ptr [rax+18h], 7
0x1402d6b4c  jbe     short loc_1402D6B51
0x1402d6b4e  mov     rax, [rax]
0x1402d6b51  mov     rcx, rax; psz
0x1402d6b54  call    cs:__imp_SysAllocString
0x1402d6b5a  mov     rbx, rax
0x1402d6b5d  mov     qword ptr [rbp+57h+var_D0], rax
0x1402d6b61  mov     [rsp+110h+var_E0], 1
0x1402d6b69  mov     rcx, [rbp+5Fh]; this
0x1402d6b6d  test    rax, rax
0x1402d6b70  jz      loc_1402D6CE0
0x1402d6b76  mov     rdx, rax
0x1402d6b79  mov     rcx, rdi
0x1402d6b7c  mov     rax, r14
0x1402d6b7f  call    _guard_dispatch_icall
0x1402d6b84  mov     rcx, [rbp+5Fh]; this
0x1402d6b88  test    eax, eax
0x1402d6b8a  js      short loc_1402D6BE6
0x1402d6b8c  mov     rcx, rbx; bstrString
0x1402d6b8f  call    cs:__imp_SysFreeString
0x1402d6b95  nop
0x1402d6b96  lea     rcx, [rbp+57h+var_B0]
0x1402d6b9a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402d6b9f  nop
0x1402d6ba0  lea     rcx, [rbp+57h+var_58]
0x1402d6ba4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402d6ba9  nop
0x1402d6baa  mov     rcx, [rsi]
0x1402d6bad  test    rcx, rcx
0x1402d6bb0  jz      short loc_1402D6BBF
0x1402d6bb2  mov     rax, [rcx]
0x1402d6bb5  mov     rax, [rax+10h]
0x1402d6bb9  call    _guard_dispatch_icall
0x1402d6bbe  nop
0x1402d6bbf  mov     rcx, [rbp+57h+var_38]
0x1402d6bc3  xor     rcx, rsp; StackCookie
0x1402d6bc6  call    __security_check_cookie
0x1402d6bcb  mov     rbx, [rsp+110h+arg_10]
0x1402d6bd3  add     rsp, 0E0h
0x1402d6bda  pop     r15
0x1402d6bdc  pop     r14
0x1402d6bde  pop     r13
0x1402d6be0  pop     r12
0x1402d6be2  pop     rdi
0x1402d6be3  pop     rsi
0x1402d6be4  pop     rbp
0x1402d6be5  retn
0x1402d6be6  mov     r9d, eax; char *
0x1402d6be9  lea     r8, aCW1SSrcOrchest_111; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402d6bf0  mov     edx, 37Fh; void *
0x1402d6bf5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402d6bfb  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x1402d6c02  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1402d6c08  mov     r9d, 80070057h; char *
0x1402d6c0e  lea     r8, aCW1SSrcOrchest_111; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402d6c15  mov     edx, 367h; void *
0x1402d6c1a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402d6c20  mov     r9d, eax; char *
0x1402d6c23  lea     r8, aCW1SSrcOrchest_111; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402d6c2a  mov     edx, 36Ah; void *
0x1402d6c2f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402d6c35  lea     r8, [rbp+57h+var_B0]; struct std::error_code *
0x1402d6c39  lea     rdx, [rbp+57h+var_D0]; char *
0x1402d6c3d  lea     rcx, aExists; "exists"
0x1402d6c44  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
0x1402d6c4a  mov     r9d, 80070002h; char *
0x1402d6c50  lea     r8, aCW1SSrcOrchest_111; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402d6c57  mov     edx, 370h; void *
0x1402d6c5c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402d6c62  mov     r9d, eax; char *
0x1402d6c65  lea     r8, aCW1SSrcOrchest_111; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402d6c6c  mov     edx, 372h; void *
0x1402d6c71  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402d6c77  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x1402d6c7d  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1402d6c84  mov     edx, 138Dh; void *
0x1402d6c89  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1402d6c8f  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1402d6c96  mov     edx, 138Dh; void *
0x1402d6c9b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1402d6ca1  mov     r9d, eax; char *
0x1402d6ca4  lea     r8, aCW1SSrcOrchest_111; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402d6cab  mov     edx, 377h; void *
0x1402d6cb0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402d6cb6  mov     r9d, eax; char *
0x1402d6cb9  lea     r8, aCW1SSrcOrchest_111; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402d6cc0  mov     edx, 37Ah; void *
0x1402d6cc5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402d6ccb  mov     r9d, eax; char *
0x1402d6cce  lea     r8, aCW1SSrcOrchest_111; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402d6cd5  mov     edx, 37Bh; void *
0x1402d6cda  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402d6ce0  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1402d6ce7  mov     edx, 138Dh; void *
0x1402d6cec  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
