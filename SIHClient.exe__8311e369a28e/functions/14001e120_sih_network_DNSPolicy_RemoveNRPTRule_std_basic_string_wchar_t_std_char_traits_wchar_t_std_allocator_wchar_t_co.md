# sih::network::DNSPolicy::RemoveNRPTRule(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x14001e120`
- end: `0x14001e2e8`
- name: `?RemoveNRPTRule@DNSPolicy@network@sih@@AEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x140019e4c`

## callees

- `0x140006e74`
- `0x1400071c0`
- `0x1400073f0`
- `0x1400154b4`
- `0x14001e120`
- `0x14001e30c`
- `0x140045dc0`

## import_xrefs

- `DNSAPI!DnsRemoveNrptRule` at `0x14001e227`
- `DNSAPI!DnsRemoveNrptRule` at `0x14001e227`

## string_xrefs

- `0x14001e25d`: `DnsRemoveNrptRule [%ls].`
- `0x14001e28f`: `remove nrpt rule - [%ls].`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall sih::network::DNSPolicy::RemoveNRPTRule(__int64 a1, size_t *a2)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rsi
  size_t v6; // r14
  bool v7; // cf
  bool v8; // r14
  size_t v9; // r8
  const void *v10; // rdx
  const wchar_t *v11; // rdx
  const wchar_t *v12; // rcx
  size_t v13; // r15
  size_t v14; // r8
  int v15; // eax
  bool v16; // zf
  int v17; // eax
  size_t v18; // rcx
  int v19; // eax
  __int64 v21; // [rsp+20h] [rbp-39h]
  wchar_t *S2[2]; // [rsp+40h] [rbp-19h] BYREF
  size_t N; // [rsp+50h] [rbp-9h]
  unsigned __int64 v24; // [rsp+58h] [rbp-1h]
  wchar_t *S1[2]; // [rsp+68h] [rbp+Fh] BYREF
  size_t v26; // [rsp+78h] [rbp+1Fh]
  unsigned __int64 v27; // [rsp+80h] [rbp+27h]

  v4 = 0;
  *(_OWORD *)S2 = 0;
  N = 0;
  v24 = 0;
  std::wstring::_Construct<1,wchar_t const *>(S2, L"DNS_RESILIENCY_", 0xFu);
  v5 = a2 + 3;
  v6 = N;
  v7 = a2[2] < N;
  if ( a2[2] >= N )
  {
    *(_OWORD *)S1 = 0;
    v26 = 0;
    v27 = 0;
    v9 = N;
    if ( v7 )
      v9 = a2[2];
    v10 = a2;
    if ( *v5 > 7u )
      v10 = (const void *)*a2;
    std::wstring::_Construct<1,wchar_t const *>(S1, v10, v9);
    v11 = (const wchar_t *)S2;
    if ( v24 > 7 )
      v11 = S2[0];
    v12 = (const wchar_t *)S1;
    if ( v27 > 7 )
      v12 = S1[0];
    v13 = v26;
    v14 = v26;
    if ( v6 < v26 )
      v14 = v6;
    v15 = wmemcmp(v12, v11, v14);
    v16 = v15 == 0;
    if ( !v15 )
    {
      if ( v13 >= v6 )
        v17 = v13 > v6;
      else
        v17 = -1;
      v16 = v17 == 0;
    }
    v8 = v16;
    std::wstring::~wstring(S1);
  }
  else
  {
    v8 = 0;
  }
  std::wstring::~wstring(S2);
  if ( v8 )
  {
    v18 = (size_t)a2;
    if ( *v5 > 7u )
      v18 = *a2;
    v19 = DnsRemoveNrptRule(v18);
    if ( v19 )
    {
      if ( (unsigned int)(v19 - 2) > 1 )
      {
        v4 = (unsigned __int16)v19 | 0x80070000;
        if ( v19 <= 0 )
          v4 = v19;
        LODWORD(v21) = v4;
        WUTrace(0, 0, 0x400000, 1, v21, L"DnsRemoveNrptRule [%ls].");
      }
    }
    else
    {
      WUTrace(0, 0, 0x400000, 4, 0, L"remove nrpt rule - [%ls].");
      std::_Tree<std::_Tmap_traits<std::wstring,_DnsNrptRule,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_DnsNrptRule>>,0>>::erase(
        a1,
        a2);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14001e120  mov     [rsp-8+arg_10], rbx
0x14001e125  mov     [rsp-8+arg_18], rsi
0x14001e12a  push    rbp
0x14001e12b  push    rdi
0x14001e12c  push    r12
0x14001e12e  push    r14
0x14001e130  push    r15
0x14001e132  lea     rbp, [rsp-37h]
0x14001e137  sub     rsp, 90h
0x14001e13e  mov     rax, cs:__security_cookie
0x14001e145  xor     rax, rsp
0x14001e148  mov     [rbp+57h+var_28], rax
0x14001e14c  mov     rdi, rdx
0x14001e14f  mov     r12, rcx
0x14001e152  xor     ebx, ebx
0x14001e154  xorps   xmm0, xmm0
0x14001e157  movups  xmmword ptr [rbp+57h+S2], xmm0
0x14001e15b  mov     [rbp+57h+N], rbx
0x14001e15f  mov     [rbp+57h+var_58], rbx
0x14001e163  lea     r8d, [rbx+0Fh]
0x14001e167  lea     rdx, aDnsResiliency_0; "DNS_RESILIENCY_"
0x14001e16e  lea     rcx, [rbp+57h+S2]
0x14001e172  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001e177  nop
0x14001e178  lea     rsi, [rdi+18h]
0x14001e17c  mov     r14, [rbp+57h+N]
0x14001e180  cmp     [rdi+10h], r14
0x14001e184  jnb     short loc_14001E18B
0x14001e186  mov     r14b, bl
0x14001e189  jmp     short loc_14001E209
0x14001e18b  xorps   xmm0, xmm0
0x14001e18e  movups  xmmword ptr [rbp+57h+S1], xmm0
0x14001e192  mov     [rbp+57h+var_38], rbx
0x14001e196  mov     [rbp+57h+var_30], rbx
0x14001e19a  mov     r8, r14
0x14001e19d  cmovb   r8, [rdi+10h]
0x14001e1a2  mov     rdx, rdi
0x14001e1a5  cmp     qword ptr [rsi], 7
0x14001e1a9  jbe     short loc_14001E1AE
0x14001e1ab  mov     rdx, [rdi]
0x14001e1ae  lea     rcx, [rbp+57h+S1]
0x14001e1b2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001e1b7  lea     rdx, [rbp+57h+S2]
0x14001e1bb  cmp     [rbp+57h+var_58], 7
0x14001e1c0  cmova   rdx, [rbp+57h+S2]; S2
0x14001e1c5  lea     rcx, [rbp+57h+S1]
0x14001e1c9  cmp     [rbp+57h+var_30], 7
0x14001e1ce  cmova   rcx, [rbp+57h+S1]; S1
0x14001e1d3  mov     r15, [rbp+57h+var_38]
0x14001e1d7  mov     r8, r15
0x14001e1da  cmp     r14, r15
0x14001e1dd  cmovb   r8, r14; N
0x14001e1e1  call    wmemcmp
0x14001e1e6  test    eax, eax
0x14001e1e8  jnz     short loc_14001E1FB
0x14001e1ea  cmp     r15, r14
0x14001e1ed  jnb     short loc_14001E1F4
0x14001e1ef  or      eax, 0FFFFFFFFh
0x14001e1f2  jmp     short loc_14001E1F9
0x14001e1f4  mov     eax, ebx
0x14001e1f6  setnbe  al
0x14001e1f9  test    eax, eax
0x14001e1fb  setz    r14b
0x14001e1ff  lea     rcx, [rbp+57h+S1]; void *
0x14001e203  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001e208  nop
0x14001e209  lea     rcx, [rbp+57h+S2]; void *
0x14001e20d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001e212  test    r14b, r14b
0x14001e215  jz      loc_14001E2BE
0x14001e21b  mov     rcx, rdi
0x14001e21e  cmp     qword ptr [rsi], 7
0x14001e222  jbe     short loc_14001E227
0x14001e224  mov     rcx, [rdi]
0x14001e227  call    cs:__imp_DnsRemoveNrptRule
0x14001e22d  mov     ecx, eax
0x14001e22f  test    eax, eax
0x14001e231  jz      short loc_14001E27E
0x14001e233  add     eax, 0FFFFFFFEh
0x14001e236  mov     r9d, 1
0x14001e23c  cmp     eax, r9d
0x14001e23f  jbe     short loc_14001E2BE
0x14001e241  movzx   ebx, cx
0x14001e244  or      ebx, 80070000h
0x14001e24a  test    ecx, ecx
0x14001e24c  cmovle  ebx, ecx
0x14001e24f  cmp     qword ptr [rsi], 7
0x14001e253  jbe     short loc_14001E258
0x14001e255  mov     rdi, [rdi]
0x14001e258  mov     [rsp+0B0h+var_80], rdi
0x14001e25d  lea     rax, aDnsremovenrptr_0; "DnsRemoveNrptRule [%ls]."
0x14001e264  mov     [rsp+0B0h+var_88], rax
0x14001e269  mov     dword ptr [rsp+0B0h+var_90], ebx
0x14001e26d  xor     edx, edx
0x14001e26f  xor     ecx, ecx
0x14001e271  mov     r8d, 400000h
0x14001e277  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001e27c  jmp     short loc_14001E2BE
0x14001e27e  mov     rax, rdi
0x14001e281  cmp     qword ptr [rsi], 7
0x14001e285  jbe     short loc_14001E28A
0x14001e287  mov     rax, [rdi]
0x14001e28a  mov     [rsp+0B0h+var_80], rax
0x14001e28f  lea     rax, aRemoveNrptRule; "remove nrpt rule - [%ls]."
0x14001e296  mov     [rsp+0B0h+var_88], rax
0x14001e29b  mov     [rsp+0B0h+var_90], rbx
0x14001e2a0  xor     edx, edx
0x14001e2a2  xor     ecx, ecx
0x14001e2a4  lea     r9d, [rdx+4]
0x14001e2a8  mov     r8d, 400000h
0x14001e2ae  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001e2b3  mov     rdx, rdi
0x14001e2b6  mov     rcx, r12
0x14001e2b9  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U_DnsNrptRule@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U_DnsNrptRule@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_DnsNrptRule,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_DnsNrptRule>>,0>>::erase(std::wstring const &)
0x14001e2be  mov     eax, ebx
0x14001e2c0  mov     rcx, [rbp+57h+var_28]
0x14001e2c4  xor     rcx, rsp; StackCookie
0x14001e2c7  call    __security_check_cookie
0x14001e2cc  lea     r11, [rsp+0B0h+var_20]
0x14001e2d4  mov     rbx, [r11+40h]
0x14001e2d8  mov     rsi, [r11+48h]
0x14001e2dc  mov     rsp, r11
0x14001e2df  pop     r15
0x14001e2e1  pop     r14
0x14001e2e3  pop     r12
0x14001e2e5  pop     rdi
0x14001e2e6  pop     rbp
0x14001e2e7  retn
```
