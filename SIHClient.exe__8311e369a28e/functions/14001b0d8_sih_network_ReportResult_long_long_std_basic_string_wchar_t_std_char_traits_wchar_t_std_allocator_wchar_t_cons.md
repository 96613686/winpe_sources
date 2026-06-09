# sih::network::ReportResult(long,long,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool,bool,bool)

- ea: `0x14001b0d8`
- end: `0x14001b318`
- name: `?ReportResult@network@sih@@YAXJJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00_N11@Z`
- size: `576`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001b350`

## callees

- `0x140005e6c`
- `0x1400071c0`
- `0x1400073f0`
- `0x1400154b4`
- `0x14001b0d8`
- `0x14001ba3c`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001b244`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001b244`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall sih::network::ReportResult(
        int a1,
        int a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        unsigned __int8 a6,
        unsigned __int8 a7,
        unsigned __int8 a8)
{
  _QWORD *v11; // r14
  const wchar_t *v12; // rdx
  unsigned __int64 v13; // r8
  _QWORD *v14; // r8
  const wchar_t *v15; // rdx
  const wchar_t *v16; // rcx
  const wchar_t *v17; // rax
  _QWORD *v18; // r8
  __int128 *v19; // rdx
  __int64 v20; // [rsp+38h] [rbp-A1h]
  __int64 v21; // [rsp+40h] [rbp-99h]
  __int64 v22; // [rsp+48h] [rbp-91h]
  __int64 v23; // [rsp+50h] [rbp-89h]
  _OWORD v25[2]; // [rsp+68h] [rbp-71h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp-51h] BYREF
  __int128 v27; // [rsp+90h] [rbp-49h] BYREF
  __int128 v28; // [rsp+A0h] [rbp-39h]
  _QWORD v29[4]; // [rsp+B0h] [rbp-29h] BYREF

  v11 = a5;
  memset(v25, 0, sizeof(v25));
  std::wstring::_Construct<1,wchar_t const *>(v25, L"data", 4u);
  sih::network::RegQueryDNSConfigStringValue(v29, v25);
  std::wstring::~wstring(v25);
  if ( !v29[2] )
    std::wstring::operator=(v29, L"Empty");
  v12 = L"Fail";
  if ( a1 >= 0 )
    v12 = L"Succeed";
  v27 = 0;
  v28 = 0;
  v13 = -1;
  do
    ++v13;
  while ( v12[v13] );
  std::wstring::_Construct<1,wchar_t const *>(&v27, v12, v13);
  HIDWORD(v14) = HIDWORD(a3);
  if ( a3[3] > 7u )
    v14 = (_QWORD *)*a3;
  v15 = L"false";
  v16 = L"false";
  if ( a8 )
    v16 = L"true";
  v17 = L"false";
  if ( a7 )
    v17 = L"true";
  if ( a6 )
    v15 = L"true";
  HIDWORD(v23) = HIDWORD(v16);
  HIDWORD(v22) = HIDWORD(v17);
  HIDWORD(v21) = HIDWORD(v15);
  HIDWORD(v20) = HIDWORD(v14);
  WUTrace(
    0,
    0,
    0x400000,
    4,
    0,
    L"report [%x] on [%s] with Alternate DNS needed[%s], fPassDefault[%s], fPassFallback[%s]");
  ppv = 0;
  if ( CoCreateInstance(&CLSID_SUSInternal, 0, 4u, &GUID_2830575b_0989_4300_9c99_cc1f9828b8a6, &ppv) >= 0 )
  {
    v18 = v29;
    if ( v29[3] > 7u )
      v18 = (_QWORD *)v29[0];
    if ( a5[3] > 7u )
      v11 = (_QWORD *)*a5;
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    if ( a3[3] > 7u )
      a3 = (_QWORD *)*a3;
    v19 = &v27;
    if ( *((_QWORD *)&v28 + 1) > 7u )
      v19 = (__int128 *)v27;
    LODWORD(v23) = a1;
    LODWORD(v22) = a2;
    LODWORD(v21) = a8;
    LODWORD(v20) = a7;
    (*(void (__fastcall **)(LPVOID, __int128 *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _DWORD, __int64, __int64, __int64, __int64))(*(_QWORD *)ppv + 72LL))(
      ppv,
      v19,
      a3,
      a4,
      v11,
      v18,
      a6,
      v20,
      v21,
      v22,
      v23);
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  std::wstring::~wstring(&v27);
  std::wstring::~wstring(v29);
}

```

## disassembly

```asm
0x14001b0d8  push    rbp
0x14001b0da  push    rbx
0x14001b0db  push    rsi
0x14001b0dc  push    rdi
0x14001b0dd  push    r13
0x14001b0df  push    r14
0x14001b0e1  push    r15
0x14001b0e3  lea     rbp, [rsp-7]
0x14001b0e8  sub     rsp, 0E0h
0x14001b0ef  mov     rax, cs:__security_cookie
0x14001b0f6  xor     rax, rsp
0x14001b0f9  mov     [rbp+37h+var_40], rax
0x14001b0fd  mov     rsi, r9
0x14001b100  mov     rdi, r8
0x14001b103  mov     [rbp+37h+var_B0], edx
0x14001b106  mov     r15d, ecx
0x14001b109  mov     r14, [rbp+37h+arg_20]
0x14001b10d  xorps   xmm0, xmm0
0x14001b110  movups  [rbp+37h+var_A8], xmm0
0x14001b114  xorps   xmm1, xmm1
0x14001b117  movdqu  [rbp+37h+var_98], xmm1
0x14001b11c  mov     r8d, 4
0x14001b122  lea     rdx, aData; "data"
0x14001b129  lea     rcx, [rbp+37h+var_A8]
0x14001b12d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001b132  nop
0x14001b133  lea     rdx, [rbp+37h+var_A8]
0x14001b137  lea     rcx, [rbp+37h+var_60]
0x14001b13b  call    ?RegQueryDNSConfigStringValue@network@sih@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@@Z; sih::network::RegQueryDNSConfigStringValue(std::wstring const &)
0x14001b140  nop
0x14001b141  lea     rcx, [rbp+37h+var_A8]; void *
0x14001b145  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001b14a  xor     r13d, r13d
0x14001b14d  cmp     [rbp+37h+var_50], r13
0x14001b151  jnz     short loc_14001B163
0x14001b153  lea     rdx, aEmpty; "Empty"
0x14001b15a  lea     rcx, [rbp+37h+var_60]; void *
0x14001b15e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x14001b163  lea     rax, aSucceed; "Succeed"
0x14001b16a  lea     rdx, aFail; "Fail"
0x14001b171  test    r15d, r15d
0x14001b174  cmovns  rdx, rax
0x14001b178  xorps   xmm0, xmm0
0x14001b17b  movups  [rbp+37h+var_80], xmm0
0x14001b17f  xorps   xmm1, xmm1
0x14001b182  movdqu  [rbp+37h+var_70], xmm1
0x14001b187  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001b18b  inc     r8
0x14001b18e  cmp     [rdx+r8*2], r13w
0x14001b193  jnz     short loc_14001B18B
0x14001b195  lea     rcx, [rbp+37h+var_80]
0x14001b199  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001b19e  nop
0x14001b19f  mov     r8, rdi
0x14001b1a2  cmp     qword ptr [rdi+18h], 7
0x14001b1a7  jbe     short loc_14001B1AC
0x14001b1a9  mov     r8, [rdi]
0x14001b1ac  movzx   ebx, [rbp+37h+arg_38]
0x14001b1b0  lea     r9, aTrue; "true"
0x14001b1b7  lea     rdx, aFalse; "false"
0x14001b1be  mov     rcx, rdx
0x14001b1c1  test    bl, bl
0x14001b1c3  cmovnz  rcx, r9
0x14001b1c7  mov     rax, rdx
0x14001b1ca  cmp     [rbp+37h+arg_30], r13b
0x14001b1ce  cmovnz  rax, r9
0x14001b1d2  movzx   r13d, [rbp+37h+arg_28]
0x14001b1d7  test    r13b, r13b
0x14001b1da  cmovnz  rdx, r9
0x14001b1de  mov     [rsp+110h+var_C0], rcx
0x14001b1e3  mov     [rsp+110h+var_C8], rax
0x14001b1e8  mov     [rsp+110h+var_D0], rdx
0x14001b1ed  mov     [rsp+110h+var_D8], r8
0x14001b1f2  mov     [rsp+110h+var_E0], r15d
0x14001b1f7  lea     rax, aReportXOnSWith; "report [%x] on [%s] with Alternate DNS "...
0x14001b1fe  mov     [rsp+110h+var_E8], rax
0x14001b203  mov     [rsp+110h+ppv], 0
0x14001b20c  xor     edx, edx
0x14001b20e  xor     ecx, ecx
0x14001b210  lea     r9d, [rdx+4]
0x14001b214  mov     r8d, 400000h
0x14001b21a  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001b21f  mov     [rbp+37h+var_88], 0
0x14001b227  lea     rax, [rbp+37h+var_88]
0x14001b22b  mov     [rsp+110h+ppv], rax; ppv
0x14001b230  lea     r9, _GUID_2830575b_0989_4300_9c99_cc1f9828b8a6; riid
0x14001b237  xor     edx, edx; pUnkOuter
0x14001b239  lea     r8d, [rdx+4]; dwClsContext
0x14001b23d  lea     rcx, CLSID_SUSInternal; rclsid
0x14001b244  call    cs:__imp_CoCreateInstance
0x14001b24a  test    eax, eax
0x14001b24c  js      short loc_14001B2CA
0x14001b24e  mov     rcx, [rbp+37h+var_88]
0x14001b252  mov     rax, [rcx]
0x14001b255  lea     r8, [rbp+37h+var_60]
0x14001b259  cmp     [rbp+37h+var_48], 7
0x14001b25e  cmova   r8, [rbp+37h+var_60]
0x14001b263  cmp     qword ptr [r14+18h], 7
0x14001b268  jbe     short loc_14001B26D
0x14001b26a  mov     r14, [r14]
0x14001b26d  cmp     qword ptr [rsi+18h], 7
0x14001b272  jbe     short loc_14001B277
0x14001b274  mov     rsi, [rsi]
0x14001b277  cmp     qword ptr [rdi+18h], 7
0x14001b27c  jbe     short loc_14001B281
0x14001b27e  mov     rdi, [rdi]
0x14001b281  lea     rdx, [rbp+37h+var_80]
0x14001b285  cmp     qword ptr [rbp+37h+var_70+8], 7
0x14001b28a  cmova   rdx, qword ptr [rbp+37h+var_80]
0x14001b28f  movzx   r11d, [rbp+37h+arg_30]
0x14001b294  mov     dword ptr [rsp+110h+var_C0], r15d
0x14001b299  mov     r9d, [rbp+37h+var_B0]
0x14001b29d  mov     dword ptr [rsp+110h+var_C8], r9d
0x14001b2a2  mov     dword ptr [rsp+110h+var_D0], ebx
0x14001b2a6  mov     dword ptr [rsp+110h+var_D8], r11d
0x14001b2ab  mov     [rsp+110h+var_E0], r13d
0x14001b2b0  mov     [rsp+110h+var_E8], r8
0x14001b2b5  mov     [rsp+110h+ppv], r14
0x14001b2ba  mov     r9, rsi
0x14001b2bd  mov     r8, rdi
0x14001b2c0  mov     rax, [rax+48h]
0x14001b2c4  call    _guard_dispatch_icall
0x14001b2c9  nop
0x14001b2ca  mov     rcx, [rbp+37h+var_88]
0x14001b2ce  test    rcx, rcx
0x14001b2d1  jz      short loc_14001B2E7
0x14001b2d3  mov     rax, [rcx]
0x14001b2d6  mov     rax, [rax+10h]
0x14001b2da  call    _guard_dispatch_icall
0x14001b2df  mov     [rbp+37h+var_88], 0
0x14001b2e7  lea     rcx, [rbp+37h+var_80]; void *
0x14001b2eb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001b2f0  nop
0x14001b2f1  lea     rcx, [rbp+37h+var_60]; void *
0x14001b2f5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001b2fa  mov     rcx, [rbp+37h+var_40]
0x14001b2fe  xor     rcx, rsp; StackCookie
0x14001b301  call    __security_check_cookie
0x14001b306  add     rsp, 0E0h
0x14001b30d  pop     r15
0x14001b30f  pop     r14
0x14001b311  pop     r13
0x14001b313  pop     rdi
0x14001b314  pop     rsi
0x14001b315  pop     rbx
0x14001b316  pop     rbp
0x14001b317  retn
```
