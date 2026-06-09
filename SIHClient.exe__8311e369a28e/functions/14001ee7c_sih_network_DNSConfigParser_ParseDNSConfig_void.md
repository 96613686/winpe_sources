# sih::network::DNSConfigParser::ParseDNSConfig(void)

- ea: `0x14001ee7c`
- end: `0x14001f05b`
- name: `?ParseDNSConfig@DNSConfigParser@network@sih@@AEAAJXZ`
- size: `479`
- prototype: `__int64 __fastcall(sih::network::DNSConfigParser *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x14001eda8`

## callees

- `0x1400154b4`
- `0x14001ee7c`
- `0x14001f064`
- `0x14001f468`
- `0x14001f868`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14001efbe`
- `OLEAUT32!__imp_SysAllocString` at `0x14001efbe`

## string_xrefs

- `0x14001eee9`: `sih::network::DNSConfigParser::ParseDNSConfig`
- `0x14001efb7`: `DNSconfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall sih::network::DNSConfigParser::ParseDNSConfig(sih::network::DNSConfigParser *this)
{
  struct IXMLDOMDocument2 *XMLDOMDocument; // rbx
  int v3; // edi
  HRESULT (__stdcall *getElementsByTagName)(IXMLDOMDocument2 *, BSTR, IXMLDOMNodeList **); // rdi
  BSTR v6; // rax
  unsigned int i; // esi
  __int64 v8; // [rsp+20h] [rbp-40h]
  int v9; // [rsp+38h] [rbp-28h] BYREF
  __int64 v10; // [rsp+40h] [rbp-20h] BYREF
  struct IXMLDOMNode *v11; // [rsp+48h] [rbp-18h] BYREF

  v10 = 0;
  v9 = 0;
  XMLDOMDocument = sih::network::DNSConfigParser::GetXMLDOMDocument(this, *(wchar_t **)this);
  if ( !XMLDOMDocument )
  {
    v3 = -2147467261;
LABEL_3:
    LODWORD(v8) = v3;
    WUTrace("sih::network::DNSConfigParser::ParseDNSConfig", 98, 0x400000, 1, v8, &OutputString);
    goto LABEL_4;
  }
  *((_BYTE *)this + 24) = sih::network::DNSConfigParser::ParseOptionalBoolFlags(this, L"FeatureSwitchOn");
  *((_BYTE *)this + 25) = sih::network::DNSConfigParser::ParseOptionalBoolFlags(this, L"EnforceNRPTRule");
  *((_BYTE *)this + 26) = sih::network::DNSConfigParser::ParseOptionalBoolFlags(this, L"EnforceDomain");
  *((_BYTE *)this + 27) = sih::network::DNSConfigParser::ParseOptionalBoolFlags(this, L"SkipDefaultDNSResolver");
  getElementsByTagName = XMLDOMDocument->lpVtbl->getElementsByTagName;
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
  }
  v6 = SysAllocString(L"DNSconfig");
  v3 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, __int64 *))getElementsByTagName)(
         XMLDOMDocument,
         v6,
         &v10);
  if ( v3 < 0 )
    goto LABEL_3;
  v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 64LL))(v10, &v9);
  if ( v3 < 0 )
    goto LABEL_3;
  for ( i = 0; (int)i < v9; ++i )
  {
    v11 = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v10 + 56LL))(v10, i, &v11) >= 0 )
      sih::network::DNSConfigParser::UpdateDNSConfig(this, v11);
    if ( v11 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
  }
LABEL_4:
  if ( XMLDOMDocument )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))XMLDOMDocument->lpVtbl->Release)(XMLDOMDocument);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001ee7c  mov     [rsp-18h+arg_8], rbx
0x14001ee81  mov     [rsp-18h+arg_10], rsi
0x14001ee86  push    rbp
0x14001ee87  push    rdi
0x14001ee88  push    r14
0x14001ee8a  mov     rbp, rsp
0x14001ee8d  sub     rsp, 60h
0x14001ee91  mov     rax, cs:__security_cookie
0x14001ee98  xor     rax, rsp
0x14001ee9b  mov     [rbp+var_10], rax
0x14001ee9f  mov     r14, rcx
0x14001eea2  mov     [rbp+var_20], 0
0x14001eeaa  mov     [rbp+var_28], 0
0x14001eeb1  mov     rdx, [rcx]; wchar_t *
0x14001eeb4  call    ?GetXMLDOMDocument@DNSConfigParser@network@sih@@AEAAPEAUIXMLDOMDocument2@@PEA_W@Z; sih::network::DNSConfigParser::GetXMLDOMDocument(wchar_t *)
0x14001eeb9  mov     rbx, rax
0x14001eebc  mov     [rbp+var_30], rax
0x14001eec0  test    rax, rax
0x14001eec3  jnz     short loc_14001EF44
0x14001eec5  mov     edi, 80004003h
0x14001eeca  lea     rax, OutputString
0x14001eed1  mov     [rsp+60h+var_38], rax
0x14001eed6  mov     dword ptr [rsp+60h+var_40], edi
0x14001eeda  mov     edx, 62h ; 'b'
0x14001eedf  lea     r9d, [rdx-61h]
0x14001eee3  mov     r8d, 400000h
0x14001eee9  lea     rcx, aSihNetworkDnsc_2; "sih::network::DNSConfigParser::ParseDNS"...
0x14001eef0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001eef5  nop
0x14001eef6  test    rbx, rbx
0x14001eef9  jz      short loc_14001EF0B
0x14001eefb  mov     rax, [rbx]
0x14001eefe  mov     rcx, rbx
0x14001ef01  mov     rax, [rax+10h]
0x14001ef05  call    _guard_dispatch_icall
0x14001ef0a  nop
0x14001ef0b  mov     rcx, [rbp+var_20]
0x14001ef0f  test    rcx, rcx
0x14001ef12  jz      short loc_14001EF21
0x14001ef14  mov     rax, [rcx]
0x14001ef17  mov     rax, [rax+10h]
0x14001ef1b  call    _guard_dispatch_icall
0x14001ef20  nop
0x14001ef21  mov     eax, edi
0x14001ef23  mov     rcx, [rbp+var_10]
0x14001ef27  xor     rcx, rsp; StackCookie
0x14001ef2a  call    __security_check_cookie
0x14001ef2f  lea     r11, [rsp+60h+var_s0]
0x14001ef34  mov     rbx, [r11+28h]
0x14001ef38  mov     rsi, [r11+30h]
0x14001ef3c  mov     rsp, r11
0x14001ef3f  pop     r14
0x14001ef41  pop     rdi
0x14001ef42  pop     rbp
0x14001ef43  retn
0x14001ef44  lea     rdx, aFeatureswitcho_1; "FeatureSwitchOn"
0x14001ef4b  mov     rcx, r14; this
0x14001ef4e  call    ?ParseOptionalBoolFlags@DNSConfigParser@network@sih@@AEAA_NPEB_W@Z; sih::network::DNSConfigParser::ParseOptionalBoolFlags(wchar_t const *)
0x14001ef53  mov     [r14+18h], al
0x14001ef57  lea     rdx, aEnforcenrptrul_0; "EnforceNRPTRule"
0x14001ef5e  mov     rcx, r14; this
0x14001ef61  call    ?ParseOptionalBoolFlags@DNSConfigParser@network@sih@@AEAA_NPEB_W@Z; sih::network::DNSConfigParser::ParseOptionalBoolFlags(wchar_t const *)
0x14001ef66  mov     [r14+19h], al
0x14001ef6a  lea     rdx, aEnforcedomain_0; "EnforceDomain"
0x14001ef71  mov     rcx, r14; this
0x14001ef74  call    ?ParseOptionalBoolFlags@DNSConfigParser@network@sih@@AEAA_NPEB_W@Z; sih::network::DNSConfigParser::ParseOptionalBoolFlags(wchar_t const *)
0x14001ef79  mov     [r14+1Ah], al
0x14001ef7d  lea     rdx, aSkipdefaultdns_0; "SkipDefaultDNSResolver"
0x14001ef84  mov     rcx, r14; this
0x14001ef87  call    ?ParseOptionalBoolFlags@DNSConfigParser@network@sih@@AEAA_NPEB_W@Z; sih::network::DNSConfigParser::ParseOptionalBoolFlags(wchar_t const *)
0x14001ef8c  mov     [r14+1Bh], al
0x14001ef90  mov     rax, [rbx]
0x14001ef93  mov     rdi, [rax+1B8h]
0x14001ef9a  mov     rcx, [rbp+var_20]
0x14001ef9e  test    rcx, rcx
0x14001efa1  jz      short loc_14001EFB7
0x14001efa3  mov     rax, [rcx]
0x14001efa6  mov     rax, [rax+10h]
0x14001efaa  call    _guard_dispatch_icall
0x14001efaf  mov     [rbp+var_20], 0
0x14001efb7  lea     rcx, psz; "DNSconfig"
0x14001efbe  call    cs:__imp_SysAllocString
0x14001efc4  lea     r8, [rbp+var_20]
0x14001efc8  mov     rdx, rax
0x14001efcb  mov     rcx, rbx
0x14001efce  mov     rax, rdi
0x14001efd1  call    _guard_dispatch_icall
0x14001efd6  mov     edi, eax
0x14001efd8  test    eax, eax
0x14001efda  js      loc_14001EECA
0x14001efe0  mov     rcx, [rbp+var_20]
0x14001efe4  mov     rax, [rcx]
0x14001efe7  lea     rdx, [rbp+var_28]
0x14001efeb  mov     rax, [rax+40h]
0x14001efef  call    _guard_dispatch_icall
0x14001eff4  mov     edi, eax
0x14001eff6  test    eax, eax
0x14001eff8  js      loc_14001EECA
0x14001effe  xor     esi, esi
0x14001f000  cmp     [rbp+var_28], esi
0x14001f003  jle     loc_14001EEF6
0x14001f009  mov     [rbp+var_18], 0
0x14001f011  mov     rcx, [rbp+var_20]
0x14001f015  mov     rax, [rcx]
0x14001f018  lea     r8, [rbp+var_18]
0x14001f01c  mov     edx, esi
0x14001f01e  mov     rax, [rax+38h]
0x14001f022  call    _guard_dispatch_icall
0x14001f027  test    eax, eax
0x14001f029  js      short loc_14001F038
0x14001f02b  mov     rdx, [rbp+var_18]; struct IXMLDOMNode *
0x14001f02f  mov     rcx, r14; this
0x14001f032  call    ?UpdateDNSConfig@DNSConfigParser@network@sih@@AEAAJPEAUIXMLDOMNode@@@Z; sih::network::DNSConfigParser::UpdateDNSConfig(IXMLDOMNode *)
0x14001f037  nop
0x14001f038  mov     rcx, [rbp+var_18]
0x14001f03c  test    rcx, rcx
0x14001f03f  jz      short loc_14001F04E
0x14001f041  mov     rax, [rcx]
0x14001f044  mov     rax, [rax+10h]
0x14001f048  call    _guard_dispatch_icall
0x14001f04d  nop
0x14001f04e  inc     esi
0x14001f050  cmp     esi, [rbp+var_28]
0x14001f053  jl      short loc_14001F009
0x14001f055  jmp     loc_14001EEF6
```
