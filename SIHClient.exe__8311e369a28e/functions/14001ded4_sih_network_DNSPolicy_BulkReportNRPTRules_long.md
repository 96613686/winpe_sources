# sih::network::DNSPolicy::BulkReportNRPTRules(long)

- ea: `0x14001ded4`
- end: `0x14001e11a`
- name: `?BulkReportNRPTRules@DNSPolicy@network@sih@@AEAAXJ@Z`
- size: `582`
- prototype: `void __fastcall(sih::network::DNSPolicy *__hidden this, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001dc6c`

## callees

- `0x140005e6c`
- `0x1400071c0`
- `0x1400073f0`
- `0x14000cb54`
- `0x1400154b4`
- `0x14001ba3c`
- `0x14001ded4`
- `0x14001e5ac`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001e077`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001e077`

## pseudocode

```c
void __fastcall sih::network::DNSPolicy::BulkReportNRPTRules(sih::network::DNSPolicy *this, int a2)
{
  const wchar_t *v4; // rdx
  unsigned __int64 v5; // r8
  _QWORD *v6; // rbx
  __int64 **v7; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  _QWORD *v10; // r9
  __int128 *p_Src; // r8
  __int128 *v12; // rdx
  _OWORD v13[2]; // [rsp+40h] [rbp-49h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-29h] BYREF
  __int128 Src; // [rsp+68h] [rbp-21h] BYREF
  __m128i si128; // [rsp+78h] [rbp-11h]
  __int128 v17; // [rsp+88h] [rbp-1h] BYREF
  __int128 v18; // [rsp+98h] [rbp+Fh]
  _QWORD v19[4]; // [rsp+A8h] [rbp+1Fh] BYREF

  memset(v13, 0, sizeof(v13));
  std::wstring::_Construct<1,wchar_t const *>(v13, L"data", 4u);
  sih::network::RegQueryDNSConfigStringValue(v19, v13);
  std::wstring::~wstring(v13);
  if ( !v19[2] )
    std::wstring::operator=(v19, L"Empty");
  v4 = L"Fail";
  if ( a2 >= 0 )
    v4 = L"Succeed";
  v17 = 0;
  v18 = 0;
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  std::wstring::_Construct<1,wchar_t const *>(&v17, v4, v5);
  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  v6 = **(_QWORD ***)this;
  while ( v6 != *(_QWORD **)this )
  {
    std::wstring::append(&Src, v6 + 4);
    std::wstring::append(&Src, L";");
    v7 = (__int64 **)v6[2];
    if ( *((_BYTE *)v7 + 25) )
    {
      for ( i = v6[1]; !*(_BYTE *)(i + 25) && v6 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        v6 = (_QWORD *)i;
      v6 = (_QWORD *)i;
    }
    else
    {
      v6 = (_QWORD *)v6[2];
      for ( j = *v7; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v6 = j;
    }
  }
  WUTrace(0, 0, 0x400000, 4, 0, L"report [%x] on NRPT rules [%s]");
  ppv = 0;
  if ( CoCreateInstance(&CLSID_SUSInternal, 0, 4u, &GUID_2830575b_0989_4300_9c99_cc1f9828b8a6, &ppv) >= 0 )
  {
    v10 = v19;
    if ( v19[3] > 7u )
      v10 = (_QWORD *)v19[0];
    p_Src = &Src;
    if ( si128.m128i_i64[1] > 7uLL )
      p_Src = (__int128 *)Src;
    v12 = &v17;
    if ( *((_QWORD *)&v18 + 1) > 7u )
      v12 = (__int128 *)v17;
    (*(void (__fastcall **)(LPVOID, __int128 *, __int128 *, _QWORD *, int))(*(_QWORD *)ppv + 64LL))(
      ppv,
      v12,
      p_Src,
      v10,
      a2);
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  std::wstring::~wstring(&Src);
  std::wstring::~wstring(&v17);
  std::wstring::~wstring(v19);
}

```

## disassembly

```asm
0x14001ded4  mov     [rsp-8+arg_0], rbx
0x14001ded9  mov     [rsp-8+arg_10], rsi
0x14001dede  push    rbp
0x14001dedf  push    rdi
0x14001dee0  push    r14
0x14001dee2  lea     rbp, [rsp-47h]
0x14001dee7  sub     rsp, 0D0h
0x14001deee  mov     rax, cs:__security_cookie
0x14001def5  xor     rax, rsp
0x14001def8  mov     [rbp+57h+var_18], rax
0x14001defc  mov     esi, edx
0x14001defe  mov     rdi, rcx
0x14001df01  xorps   xmm0, xmm0
0x14001df04  movups  [rbp+57h+var_A0], xmm0
0x14001df08  xorps   xmm1, xmm1
0x14001df0b  movdqu  [rbp+57h+var_90], xmm1
0x14001df10  mov     r8d, 4
0x14001df16  lea     rdx, aData_1; "data"
0x14001df1d  lea     rcx, [rbp+57h+var_A0]
0x14001df21  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001df26  nop
0x14001df27  lea     rdx, [rbp+57h+var_A0]
0x14001df2b  lea     rcx, [rbp+57h+var_38]
0x14001df2f  call    ?RegQueryDNSConfigStringValue@network@sih@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@@Z; sih::network::RegQueryDNSConfigStringValue(std::wstring const &)
0x14001df34  nop
0x14001df35  lea     rcx, [rbp+57h+var_A0]; void *
0x14001df39  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001df3e  xor     r14d, r14d
0x14001df41  cmp     [rbp+57h+var_28], r14
0x14001df45  jnz     short loc_14001DF57
0x14001df47  lea     rdx, aEmpty; "Empty"
0x14001df4e  lea     rcx, [rbp+57h+var_38]; void *
0x14001df52  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x14001df57  lea     rax, aSucceed; "Succeed"
0x14001df5e  lea     rdx, aFail; "Fail"
0x14001df65  test    esi, esi
0x14001df67  cmovns  rdx, rax
0x14001df6b  xorps   xmm0, xmm0
0x14001df6e  movups  [rbp+57h+var_58], xmm0
0x14001df72  xorps   xmm1, xmm1
0x14001df75  movdqu  [rbp+57h+var_48], xmm1
0x14001df7a  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001df7e  inc     r8
0x14001df81  cmp     [rdx+r8*2], r14w
0x14001df86  jnz     short loc_14001DF7E
0x14001df88  lea     rcx, [rbp+57h+var_58]
0x14001df8c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001df91  nop
0x14001df92  xorps   xmm0, xmm0
0x14001df95  movups  [rbp+57h+Src], xmm0
0x14001df99  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14001dfa1  movdqu  [rbp+57h+var_68], xmm1
0x14001dfa6  mov     word ptr [rbp+57h+Src], r14w
0x14001dfab  mov     rax, [rdi]
0x14001dfae  mov     rbx, [rax]
0x14001dfb1  cmp     rbx, rax
0x14001dfb4  jz      short loc_14001E01B
0x14001dfb6  lea     rdx, [rbx+20h]
0x14001dfba  lea     rcx, [rbp+57h+Src]; Src
0x14001dfbe  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x14001dfc3  lea     rdx, asc_1400569A4; ";"
0x14001dfca  lea     rcx, [rbp+57h+Src]; Src
0x14001dfce  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x14001dfd3  mov     rcx, [rbx+10h]
0x14001dfd7  cmp     [rcx+19h], r14b
0x14001dfdb  jz      short loc_14001DFFB
0x14001dfdd  mov     rax, [rbx+8]
0x14001dfe1  jmp     short loc_14001DFF0
0x14001dfe3  cmp     rbx, [rax+10h]
0x14001dfe7  jnz     short loc_14001DFF6
0x14001dfe9  mov     rbx, rax
0x14001dfec  mov     rax, [rax+8]
0x14001dff0  cmp     [rax+19h], r14b
0x14001dff4  jz      short loc_14001DFE3
0x14001dff6  mov     rbx, rax
0x14001dff9  jmp     short loc_14001E016
0x14001dffb  mov     rbx, rcx
0x14001dffe  mov     rcx, [rcx]
0x14001e001  cmp     [rcx+19h], r14b
0x14001e005  jnz     short loc_14001E016
0x14001e007  mov     rbx, rcx
0x14001e00a  mov     rax, [rcx]
0x14001e00d  mov     rcx, rax
0x14001e010  cmp     [rax+19h], r14b
0x14001e014  jz      short loc_14001E007
0x14001e016  cmp     rbx, [rdi]
0x14001e019  jnz     short loc_14001DFB6
0x14001e01b  lea     rax, [rbp+57h+Src]
0x14001e01f  cmp     qword ptr [rbp+57h+var_68+8], 7
0x14001e024  cmova   rax, qword ptr [rbp+57h+Src]
0x14001e029  mov     [rsp+0E0h+var_A8], rax
0x14001e02e  mov     [rsp+0E0h+var_B0], esi
0x14001e032  lea     rax, aReportXOnNrptR; "report [%x] on NRPT rules [%s]"
0x14001e039  mov     [rsp+0E0h+var_B8], rax
0x14001e03e  mov     [rsp+0E0h+ppv], r14
0x14001e043  xor     edx, edx
0x14001e045  xor     ecx, ecx
0x14001e047  lea     r9d, [rdx+4]
0x14001e04b  mov     r8d, 400000h
0x14001e051  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001e056  mov     [rbp+57h+var_80], r14
0x14001e05a  lea     rax, [rbp+57h+var_80]
0x14001e05e  mov     [rsp+0E0h+ppv], rax; ppv
0x14001e063  lea     r9, _GUID_2830575b_0989_4300_9c99_cc1f9828b8a6; riid
0x14001e06a  xor     edx, edx; pUnkOuter
0x14001e06c  lea     r8d, [rdx+4]; dwClsContext
0x14001e070  lea     rcx, CLSID_SUSInternal; rclsid
0x14001e077  call    cs:__imp_CoCreateInstance
0x14001e07d  test    eax, eax
0x14001e07f  js      short loc_14001E0C0
0x14001e081  mov     rcx, [rbp+57h+var_80]
0x14001e085  mov     rax, [rcx]
0x14001e088  lea     r9, [rbp+57h+var_38]
0x14001e08c  cmp     [rbp+57h+var_20], 7
0x14001e091  cmova   r9, [rbp+57h+var_38]
0x14001e096  lea     r8, [rbp+57h+Src]
0x14001e09a  cmp     qword ptr [rbp+57h+var_68+8], 7
0x14001e09f  cmova   r8, qword ptr [rbp+57h+Src]
0x14001e0a4  lea     rdx, [rbp+57h+var_58]
0x14001e0a8  cmp     qword ptr [rbp+57h+var_48+8], 7
0x14001e0ad  cmova   rdx, qword ptr [rbp+57h+var_58]
0x14001e0b2  mov     dword ptr [rsp+0E0h+ppv], esi
0x14001e0b6  mov     rax, [rax+40h]
0x14001e0ba  call    _guard_dispatch_icall
0x14001e0bf  nop
0x14001e0c0  mov     rcx, [rbp+57h+var_80]
0x14001e0c4  test    rcx, rcx
0x14001e0c7  jz      short loc_14001E0D9
0x14001e0c9  mov     rax, [rcx]
0x14001e0cc  mov     rax, [rax+10h]
0x14001e0d0  call    _guard_dispatch_icall
0x14001e0d5  mov     [rbp+57h+var_80], r14
0x14001e0d9  lea     rcx, [rbp+57h+Src]; void *
0x14001e0dd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001e0e2  nop
0x14001e0e3  lea     rcx, [rbp+57h+var_58]; void *
0x14001e0e7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001e0ec  nop
0x14001e0ed  lea     rcx, [rbp+57h+var_38]; void *
0x14001e0f1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001e0f6  mov     rcx, [rbp+57h+var_18]
0x14001e0fa  xor     rcx, rsp; StackCookie
0x14001e0fd  call    __security_check_cookie
0x14001e102  lea     r11, [rsp+0E0h+var_10]
0x14001e10a  mov     rbx, [r11+20h]
0x14001e10e  mov     rsi, [r11+30h]
0x14001e112  mov     rsp, r11
0x14001e115  pop     r14
0x14001e117  pop     rdi
0x14001e118  pop     rbp
0x14001e119  retn
```
