# uus::Session::Session(wchar_t const *)

- ea: `0x18002e758`
- end: `0x18002e8aa`
- name: `??0Session@uus@@QEAA@PEB_W@Z`
- size: `338`
- prototype: `uus::Session *__fastcall(uus::Session *this, const wchar_t *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800150a0`
- `0x180048b08`

## callees

- `0x180009380`
- `0x18002e030`
- `0x18002e3dc`
- `0x18002e61c`
- `0x18002e758`
- `0x18002ebe8`
- `0x18002ed04`
- `0x18002ed7c`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e80b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e80b`

## string_xrefs

- `0x18002e831`: `uusbrain.dll`

## pseudocode

```c
uus::Session *__fastcall uus::Session::Session(uus::Session *this, const wchar_t *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rbx
  LPVOID pv[2]; // [rsp+20h] [rbp-39h] BYREF
  const wchar_t *v7; // [rsp+30h] [rbp-29h] BYREF
  __int64 v8; // [rsp+38h] [rbp-21h]
  _BYTE v9[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v10; // [rsp+60h] [rbp+7h]
  int v11; // [rsp+68h] [rbp+Fh]
  int v12; // [rsp+6Ch] [rbp+13h]
  unsigned __int64 v13; // [rsp+70h] [rbp+17h]
  const wchar_t *v14; // [rsp+78h] [rbp+1Fh]
  char v15[16]; // [rsp+80h] [rbp+27h] BYREF
  __m128i si128; // [rsp+90h] [rbp+37h]

  *(_QWORD *)this = &UpdateDiagnostics::update_diagnostics::`vftable';
  v10 = 32;
  v11 = 3;
  v12 = 8;
  v13 = 0x180000000uLL;
  v14 = a2;
  *(_OWORD *)v15 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  *(_WORD *)v15 = 0;
  pv[0] = 0;
  wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(
    pv,
    a2,
    0x180000000uLL);
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)pv[0] + v3) );
  v7 = (const wchar_t *)pv[0];
  v8 = v3;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v9, &v7);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  std::filesystem::path::remove_filename((std::filesystem::path *)v9);
  std::wstring::operator=(v15);
  std::wstring::~wstring(v9);
  v7 = L"uusbrain.dll";
  v8 = 12;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v9, &v7);
  std::filesystem::path::operator/=(v15);
  std::wstring::~wstring(v9);
  v4 = uus::Utility::GetBrainSession<uus::Brain3>(v15);
  std::wstring::~wstring(v15);
  *((_QWORD *)this + 1) = v4;
  return this;
}

```

## disassembly

```asm
0x18002e758  mov     [rsp-8+arg_10], rbx
0x18002e75d  mov     [rsp-8+arg_18], rdi
0x18002e762  push    rbp
0x18002e763  lea     rbp, [rsp-57h]
0x18002e768  sub     rsp, 0B0h
0x18002e76f  mov     rax, cs:__security_cookie
0x18002e776  xor     rax, rsp
0x18002e779  mov     [rbp+57h+var_10], rax
0x18002e77d  mov     rdi, rcx
0x18002e780  mov     [rbp+57h+pv], rcx
0x18002e784  xor     ebx, ebx
0x18002e786  lea     rax, ??_7update_diagnostics@UpdateDiagnostics@@6B@; const UpdateDiagnostics::update_diagnostics::`vftable'
0x18002e78d  mov     [rcx], rax
0x18002e790  mov     [rbp+57h+var_50], 20h ; ' '
0x18002e798  mov     [rbp+57h+var_48], 3
0x18002e79f  mov     [rbp+57h+var_44], 8
0x18002e7a6  lea     r8, cs:180000000h
0x18002e7ad  mov     [rbp+57h+var_40], r8
0x18002e7b1  mov     [rbp+57h+var_38], rdx
0x18002e7b5  xorps   xmm0, xmm0
0x18002e7b8  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x18002e7bc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002e7c4  movdqu  [rbp+57h+var_20], xmm1
0x18002e7c9  mov     word ptr [rbp+57h+var_30], bx
0x18002e7cd  mov     [rbp+57h+pv], rbx
0x18002e7d1  lea     rcx, [rbp+57h+pv]
0x18002e7d5  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEAXPEAUHINSTANCE__@@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *)
0x18002e7da  nop
0x18002e7db  mov     rax, [rbp+57h+pv]
0x18002e7df  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002e7e3  inc     rcx
0x18002e7e6  cmp     [rax+rcx*2], bx
0x18002e7ea  jnz     short loc_18002E7E3
0x18002e7ec  mov     [rbp+57h+var_80], rax
0x18002e7f0  mov     [rbp+57h+var_78], rcx
0x18002e7f4  lea     rdx, [rbp+57h+var_80]
0x18002e7f8  lea     rcx, [rbp+57h+var_70]
0x18002e7fc  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18002e801  nop
0x18002e802  mov     rcx, [rbp+57h+pv]; pv
0x18002e806  test    rcx, rcx
0x18002e809  jz      short loc_18002E812
0x18002e80b  call    cs:__imp_CoTaskMemFree
0x18002e811  nop
0x18002e812  lea     rcx, [rbp+57h+var_70]; this
0x18002e816  call    ?remove_filename@path@filesystem@std@@QEAAAEAV123@XZ; std::filesystem::path::remove_filename(void)
0x18002e81b  mov     rdx, rax
0x18002e81e  lea     rcx, [rbp+57h+var_30]; void *
0x18002e822  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002e827  nop
0x18002e828  lea     rcx, [rbp+57h+var_70]; void *
0x18002e82c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e831  lea     rax, aUusbrainDll; "uusbrain.dll"
0x18002e838  mov     [rbp+57h+var_80], rax
0x18002e83c  mov     [rbp+57h+var_78], 0Ch
0x18002e844  lea     rdx, [rbp+57h+var_80]
0x18002e848  lea     rcx, [rbp+57h+var_70]
0x18002e84c  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18002e851  nop
0x18002e852  lea     rdx, [rbp+57h+var_70]
0x18002e856  lea     rcx, [rbp+57h+var_30]; void *
0x18002e85a  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x18002e85f  nop
0x18002e860  lea     rcx, [rbp+57h+var_70]; void *
0x18002e864  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e869  lea     rdx, [rbp+57h+var_50]
0x18002e86d  lea     rcx, [rbp+57h+var_30]; char *
0x18002e871  call    ??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z; uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)
0x18002e876  mov     rbx, rax
0x18002e879  lea     rcx, [rbp+57h+var_30]; void *
0x18002e87d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e882  mov     [rdi+8], rbx
0x18002e886  mov     rax, rdi
0x18002e889  mov     rcx, [rbp+57h+var_10]
0x18002e88d  xor     rcx, rsp; StackCookie
0x18002e890  call    __security_check_cookie
0x18002e895  lea     r11, [rsp+0B0h+var_s0]
0x18002e89d  mov     rbx, [r11+20h]
0x18002e8a1  mov     rdi, [r11+28h]
0x18002e8a5  mov     rsp, r11
0x18002e8a8  pop     rbp
0x18002e8a9  retn
```
