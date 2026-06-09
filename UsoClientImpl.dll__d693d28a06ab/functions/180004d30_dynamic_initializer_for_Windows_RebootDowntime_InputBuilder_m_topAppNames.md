# _dynamic_initializer_for__Windows::RebootDowntime::InputBuilder::m_topAppNames__

- ea: `0x180004d30`
- end: `0x180004e4a`
- name: `_dynamic_initializer_for__Windows::RebootDowntime::InputBuilder::m_topAppNames__`
- size: `282`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180019208`
- `0x1800338a4`
- `0x180056568`
- `0x1800569e8`

## string_xrefs

- `0x180004deb`: `Microsoft Edge Update`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
int dynamic_initializer_for__Windows::RebootDowntime::InputBuilder::m_topAppNames__()
{
  _QWORD v1[2]; // [rsp+20h] [rbp-59h] BYREF
  _OWORD v2[2]; // [rsp+30h] [rbp-49h] BYREF
  _OWORD v3[2]; // [rsp+50h] [rbp-29h] BYREF
  _OWORD v4[2]; // [rsp+70h] [rbp-9h] BYREF
  _OWORD v5[2]; // [rsp+90h] [rbp+17h] BYREF
  _OWORD v6[2]; // [rsp+B0h] [rbp+37h] BYREF
  char vars0; // [rsp+D0h] [rbp+57h] BYREF

  memset(v2, 0, sizeof(v2));
  std::wstring::_Construct<1,wchar_t const *>(v2);
  memset(v3, 0, sizeof(v3));
  std::wstring::_Construct<1,wchar_t const *>(v3);
  memset(v4, 0, sizeof(v4));
  std::wstring::_Construct<1,wchar_t const *>(v4);
  memset(v5, 0, sizeof(v5));
  std::wstring::_Construct<1,wchar_t const *>(v5);
  memset(v6, 0, sizeof(v6));
  std::wstring::_Construct<1,wchar_t const *>(v6);
  v1[0] = v2;
  v1[1] = &vars0;
  std::vector<std::wstring>::vector<std::wstring>(Windows::RebootDowntime::InputBuilder::m_topAppNames, v1);
  `eh vector destructor iterator'(v2, 0x20u, 5u, std::wstring::~wstring);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Windows::RebootDowntime::InputBuilder::m_topAppNames__);
}

```

## disassembly

```asm
0x180004d30  push    rbp
0x180004d32  lea     rbp, [rsp-57h]
0x180004d37  sub     rsp, 0D0h
0x180004d3e  xorps   xmm0, xmm0
0x180004d41  movups  [rbp+57h+var_A0], xmm0
0x180004d45  xorps   xmm1, xmm1
0x180004d48  movdqa  [rbp+57h+var_90], xmm1
0x180004d4d  mov     r8d, 11h
0x180004d53  lea     rdx, aOnedrivesetupE; "OneDriveSetup.exe"
0x180004d5a  lea     rcx, [rbp+57h+var_A0]
0x180004d5e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004d63  nop
0x180004d64  xorps   xmm0, xmm0
0x180004d67  movups  [rbp+57h+var_80], xmm0
0x180004d6b  xorps   xmm1, xmm1
0x180004d6e  movdqa  [rbp+57h+var_70], xmm1
0x180004d73  mov     r8d, 15h
0x180004d79  lea     rdx, aMicrosoftEdgew; "Microsoft EdgeWebView"
0x180004d80  lea     rcx, [rbp+57h+var_80]
0x180004d84  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004d89  nop
0x180004d8a  xorps   xmm0, xmm0
0x180004d8d  movups  [rbp+57h+var_60], xmm0
0x180004d91  xorps   xmm1, xmm1
0x180004d94  movdqa  [rbp+57h+var_50], xmm1
0x180004d99  mov     r8d, 0Dh
0x180004d9f  lea     rdx, aGoogleChrome; "Google Chrome"
0x180004da6  lea     rcx, [rbp+57h+var_60]
0x180004daa  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004daf  nop
0x180004db0  xorps   xmm0, xmm0
0x180004db3  movups  [rbp+57h+var_40], xmm0
0x180004db7  xorps   xmm1, xmm1
0x180004dba  movdqa  [rbp+57h+var_30], xmm1
0x180004dbf  mov     r8d, 0Eh
0x180004dc5  lea     rdx, aMicrosoftEdge; "Microsoft Edge"
0x180004dcc  lea     rcx, [rbp+57h+var_40]
0x180004dd0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004dd5  nop
0x180004dd6  xorps   xmm0, xmm0
0x180004dd9  movups  [rbp+57h+var_20], xmm0
0x180004ddd  xorps   xmm1, xmm1
0x180004de0  movdqa  [rbp+57h+var_10], xmm1
0x180004de5  mov     r8d, 15h
0x180004deb  lea     rdx, aMicrosoftEdgeU; "Microsoft Edge Update"
0x180004df2  lea     rcx, [rbp+57h+var_20]
0x180004df6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004dfb  nop
0x180004dfc  lea     rax, [rbp+57h+var_A0]
0x180004e00  mov     [rbp+57h+var_B0], rax
0x180004e04  lea     rax, [rbp+57h+var_s0]
0x180004e08  mov     [rbp+57h+var_A8], rax
0x180004e0c  lea     rdx, [rbp+57h+var_B0]
0x180004e10  lea     rcx, ?m_topAppNames@InputBuilder@RebootDowntime@Windows@@0V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@B; std::vector<std::wstring> const Windows::RebootDowntime::InputBuilder::m_topAppNames
0x180004e17  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@V?$initializer_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@AEBV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(std::initializer_list<std::wstring>,std::allocator<std::wstring> const &)
0x180004e1c  nop
0x180004e1d  lea     r9, ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; void (*)(void *)
0x180004e24  mov     edx, 20h ; ' '; unsigned __int64
0x180004e29  lea     r8d, [rdx-1Bh]; unsigned __int64
0x180004e2d  lea     rcx, [rbp+57h+var_A0]; void *
0x180004e31  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180004e36  lea     rcx, _dynamic_atexit_destructor_for__Windows__RebootDowntime__InputBuilder__m_topAppNames__
0x180004e3d  add     rsp, 0D0h
0x180004e44  pop     rbp
0x180004e45  jmp     atexit
```
