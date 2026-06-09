# sih::network::DNSConfigBuilder::BuildDefaultDNSConfig(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x14001ca64`
- end: `0x14001ccc6`
- name: `?BuildDefaultDNSConfig@DNSConfigBuilder@network@sih@@AEAA?AUPerHostDNSConfig@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `610`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14001cdf8`

## callees

- `0x140005e6c`
- `0x140005eec`
- `0x140005f98`
- `0x140006e74`
- `0x1400073f0`
- `0x1400154b4`
- `0x14001bcc4`
- `0x14001ca64`
- `0x14001cccc`
- `0x14001d4f4`
- `0x140045dc0`

## string_xrefs

- `0x14001cc37`: `BuildDefaultDNSConfig(%ls) with none matches.`
- `0x14001cc08`: `.delivery.mp.microsoft.com`
- `0x14001cb7c`: `.update.microsoft.com`
- `0x14001cbf3`: `fe6cr.delivery.mp.microsoft.com`
- `0x14001cbc2`: `fe3cr.delivery.mp.microsoft.com`
- `0x14001cb67`: `slscr.update.microsoft.com`
- `0x14001cc18`: `/clientwebservice/ping`

## pseudocode

```c
__int64 __fastcall sih::network::DNSConfigBuilder::BuildDefaultDNSConfig(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 RuleName; // rax
  const wchar_t *v5; // rcx
  unsigned __int64 v6; // rbx
  size_t v7; // r8
  wchar_t *v8; // rdx
  const wchar_t *v9; // rcx
  unsigned __int64 v10; // rbx
  size_t v11; // r8
  const wchar_t *v12; // rcx
  unsigned __int64 v13; // rbx
  size_t v14; // r8
  _QWORD v16[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *S1[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v18; // [rsp+90h] [rbp-70h]
  unsigned __int64 v19; // [rsp+98h] [rbp-68h]
  __int128 v20; // [rsp+A0h] [rbp-60h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-50h]
  _OWORD v22[2]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v23[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v24[2]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v25[2]; // [rsp+120h] [rbp+20h] BYREF
  __int16 v26; // [rsp+140h] [rbp+40h]
  char v27; // [rsp+142h] [rbp+42h]
  int v28; // [rsp+143h] [rbp+43h]
  char v29; // [rsp+147h] [rbp+47h]

  v20 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v20) = 0;
  v22[0] = 0;
  v22[1] = si128;
  LOWORD(v22[0]) = 0;
  v23[0] = 0;
  v23[1] = si128;
  LOWORD(v23[0]) = 0;
  v24[0] = 0;
  v24[1] = si128;
  LOWORD(v24[0]) = 0;
  v25[0] = 0;
  v25[1] = si128;
  LOWORD(v25[0]) = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  std::wstring::wstring((__int64)S1, a3);
  std::wstring::operator=(&v20);
  RuleName = sih::network::CreateRuleName(v16, S1);
  std::wstring::operator=(v24, RuleName);
  std::wstring::~wstring(v16);
  std::wstring::operator=(v25, L"1.1.1.1");
  v5 = (const wchar_t *)S1;
  if ( v19 > 7 )
    v5 = S1[0];
  v6 = v18;
  v7 = v18;
  if ( v18 > 0x1A )
    v7 = 26;
  if ( !wmemcmp(v5, L"slscr.update.microsoft.com", v7) && v6 == 26 )
  {
    std::wstring::operator=(v22, L".update.microsoft.com");
    v8 = L"/sls/ping";
  }
  else
  {
    v9 = (const wchar_t *)S1;
    if ( v19 > 7 )
      v9 = S1[0];
    v10 = v18;
    v11 = v18;
    if ( v18 > 0x1F )
      v11 = 31;
    if ( wmemcmp(v9, L"fe3cr.delivery.mp.microsoft.com", v11) || v10 != 31 )
    {
      v12 = (const wchar_t *)S1;
      if ( v19 > 7 )
        v12 = S1[0];
      v13 = v18;
      v14 = v18;
      if ( v18 > 0x1F )
        v14 = 31;
      if ( wmemcmp(v12, L"fe6cr.delivery.mp.microsoft.com", v14) || v13 != 31 )
      {
        WUTrace(0, 0, 0x400000, 4, 0, L"BuildDefaultDNSConfig(%ls) with none matches.");
        goto LABEL_23;
      }
    }
    std::wstring::operator=(v22, L".delivery.mp.microsoft.com");
    v8 = L"/clientwebservice/ping";
  }
  std::wstring::operator=(v23, v8);
LABEL_23:
  sih::network::PerHostDNSConfig::PerHostDNSConfig(a2, (__int64)&v20);
  std::wstring::~wstring(S1);
  std::wstring::~wstring(v25);
  std::wstring::~wstring(v24);
  std::wstring::~wstring(v23);
  std::wstring::~wstring(v22);
  std::wstring::~wstring(&v20);
  return a2;
}

```

## disassembly

```asm
0x14001ca64  mov     [rsp-8+arg_0], rbx
0x14001ca69  mov     [rsp-8+arg_18], rsi
0x14001ca6e  push    rbp
0x14001ca6f  push    rdi
0x14001ca70  push    r14
0x14001ca72  lea     rbp, [rsp-60h]
0x14001ca77  sub     rsp, 160h
0x14001ca7e  mov     rax, cs:__security_cookie
0x14001ca85  xor     rax, rsp
0x14001ca88  mov     [rbp+70h+var_20], rax
0x14001ca8c  mov     rdi, rdx
0x14001ca8f  mov     [rsp+170h+var_120], rdx
0x14001ca94  xor     r14d, r14d
0x14001ca97  xorps   xmm0, xmm0
0x14001ca9a  movups  [rbp+70h+var_D0], xmm0
0x14001ca9e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14001caa6  movdqa  [rbp+70h+var_C0], xmm1
0x14001caab  mov     word ptr [rbp+70h+var_D0], r14w
0x14001cab0  movups  [rbp+70h+var_B0], xmm0
0x14001cab4  movdqa  [rbp+70h+var_A0], xmm1
0x14001cab9  mov     word ptr [rbp+70h+var_B0], r14w
0x14001cabe  movups  [rbp+70h+var_90], xmm0
0x14001cac2  movdqa  [rbp+70h+var_80], xmm1
0x14001cac7  mov     word ptr [rbp+70h+var_90], r14w
0x14001cacc  movups  [rbp+70h+var_70], xmm0
0x14001cad0  movdqa  [rbp+70h+var_60], xmm1
0x14001cad5  mov     word ptr [rbp+70h+var_70], r14w
0x14001cada  movups  [rbp+70h+var_50], xmm0
0x14001cade  movdqa  [rbp+70h+var_40], xmm1
0x14001cae3  mov     word ptr [rbp+70h+var_50], r14w
0x14001cae8  mov     [rbp+70h+var_30], r14w
0x14001caed  mov     [rbp+70h+var_2E], r14b
0x14001caf1  xor     eax, eax
0x14001caf3  mov     [rbp+70h+var_2D], eax
0x14001caf6  mov     [rbp+70h+var_29], al
0x14001caf9  mov     rdx, r8
0x14001cafc  lea     rcx, [rbp+70h+S1]
0x14001cb00  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001cb05  nop
0x14001cb06  lea     rdx, [rbp+70h+S1]
0x14001cb0a  lea     rcx, [rbp+70h+var_D0]; void *
0x14001cb0e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14001cb13  lea     rdx, [rbp+70h+S1]; Src
0x14001cb17  lea     rcx, [rsp+170h+var_110]; void *
0x14001cb1c  call    ?CreateRuleName@network@sih@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@@Z; sih::network::CreateRuleName(std::wstring const &)
0x14001cb21  mov     rdx, rax
0x14001cb24  lea     rcx, [rbp+70h+var_70]
0x14001cb28  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14001cb2d  lea     rcx, [rsp+170h+var_110]; void *
0x14001cb32  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001cb37  lea     rdx, a1111; "1.1.1.1"
0x14001cb3e  lea     rcx, [rbp+70h+var_50]; void *
0x14001cb42  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x14001cb47  lea     rcx, [rbp+70h+S1]
0x14001cb4b  cmp     [rbp+70h+var_D8], 7
0x14001cb50  cmova   rcx, [rbp+70h+S1]; S1
0x14001cb55  mov     rbx, [rbp+70h+var_E0]
0x14001cb59  mov     r8, rbx
0x14001cb5c  lea     esi, [r14+1Ah]
0x14001cb60  cmp     rbx, rsi
0x14001cb63  cmova   r8, rsi; N
0x14001cb67  lea     rdx, aSlscrUpdateMic_0; "slscr.update.microsoft.com"
0x14001cb6e  call    wmemcmp
0x14001cb73  test    eax, eax
0x14001cb75  jnz     short loc_14001CBA1
0x14001cb77  cmp     rbx, rsi
0x14001cb7a  jnz     short loc_14001CBA1
0x14001cb7c  lea     rdx, aUpdateMicrosof; ".update.microsoft.com"
0x14001cb83  lea     rcx, [rbp+70h+var_B0]; void *
0x14001cb87  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x14001cb8c  lea     rdx, aSlsPing; "/sls/ping"
0x14001cb93  lea     rcx, [rbp+70h+var_90]; void *
0x14001cb97  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x14001cb9c  jmp     loc_14001CC5B
0x14001cba1  lea     rcx, [rbp+70h+S1]
0x14001cba5  cmp     [rbp+70h+var_D8], 7
0x14001cbaa  cmova   rcx, [rbp+70h+S1]; S1
0x14001cbaf  mov     rbx, [rbp+70h+var_E0]
0x14001cbb3  mov     r8, rbx
0x14001cbb6  mov     esi, 1Fh
0x14001cbbb  cmp     rbx, rsi
0x14001cbbe  cmova   r8, rsi; N
0x14001cbc2  lea     rdx, aFe3crDeliveryM; "fe3cr.delivery.mp.microsoft.com"
0x14001cbc9  call    wmemcmp
0x14001cbce  test    eax, eax
0x14001cbd0  jnz     short loc_14001CBD7
0x14001cbd2  cmp     rbx, rsi
0x14001cbd5  jz      short loc_14001CC08
0x14001cbd7  lea     rcx, [rbp+70h+S1]
0x14001cbdb  cmp     [rbp+70h+var_D8], 7
0x14001cbe0  cmova   rcx, [rbp+70h+S1]; S1
0x14001cbe5  mov     rbx, [rbp+70h+var_E0]
0x14001cbe9  mov     r8, rbx
0x14001cbec  cmp     rbx, rsi
0x14001cbef  cmova   r8, rsi; N
0x14001cbf3  lea     rdx, aFe6crDeliveryM; "fe6cr.delivery.mp.microsoft.com"
0x14001cbfa  call    wmemcmp
0x14001cbff  test    eax, eax
0x14001cc01  jnz     short loc_14001CC24
0x14001cc03  cmp     rbx, rsi
0x14001cc06  jnz     short loc_14001CC24
0x14001cc08  lea     rdx, aDeliveryMpMicr; ".delivery.mp.microsoft.com"
0x14001cc0f  lea     rcx, [rbp+70h+var_B0]; void *
0x14001cc13  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x14001cc18  lea     rdx, aClientwebservi; "/clientwebservice/ping"
0x14001cc1f  jmp     loc_14001CB93
0x14001cc24  lea     rax, [rbp+70h+S1]
0x14001cc28  cmp     [rbp+70h+var_D8], 7
0x14001cc2d  cmova   rax, [rbp+70h+S1]
0x14001cc32  mov     [rsp+170h+var_140], rax
0x14001cc37  lea     rax, aBuilddefaultdn; "BuildDefaultDNSConfig(%ls) with none ma"...
0x14001cc3e  mov     [rsp+170h+var_148], rax
0x14001cc43  mov     [rsp+170h+var_150], r14
0x14001cc48  xor     edx, edx
0x14001cc4a  xor     ecx, ecx
0x14001cc4c  lea     r9d, [rdx+4]
0x14001cc50  mov     r8d, 400000h
0x14001cc56  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001cc5b  lea     rdx, [rbp+70h+var_D0]
0x14001cc5f  mov     rcx, rdi
0x14001cc62  call    ??0PerHostDNSConfig@network@sih@@QEAA@$$QEAU012@@Z; sih::network::PerHostDNSConfig::PerHostDNSConfig(sih::network::PerHostDNSConfig &&)
0x14001cc67  nop
0x14001cc68  lea     rcx, [rbp+70h+S1]; void *
0x14001cc6c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001cc71  nop
0x14001cc72  lea     rcx, [rbp+70h+var_50]; void *
0x14001cc76  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001cc7b  lea     rcx, [rbp+70h+var_70]; void *
0x14001cc7f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001cc84  lea     rcx, [rbp+70h+var_90]; void *
0x14001cc88  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001cc8d  lea     rcx, [rbp+70h+var_B0]; void *
0x14001cc91  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001cc96  lea     rcx, [rbp+70h+var_D0]; void *
0x14001cc9a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001cc9f  mov     rax, rdi
0x14001cca2  mov     rcx, [rbp+70h+var_20]
0x14001cca6  xor     rcx, rsp; StackCookie
0x14001cca9  call    __security_check_cookie
0x14001ccae  lea     r11, [rsp+170h+var_10]
0x14001ccb6  mov     rbx, [r11+20h]
0x14001ccba  mov     rsi, [r11+38h]
0x14001ccbe  mov     rsp, r11
0x14001ccc1  pop     r14
0x14001ccc3  pop     rdi
0x14001ccc4  pop     rbp
0x14001ccc5  retn
```
