# WaasMedic::CSandboxRpcWrapper::PrepareCommandLine(void)

- ea: `0x18001ef7c`
- end: `0x18001f172`
- name: `?PrepareCommandLine@CSandboxRpcWrapper@WaasMedic@@QEAAJXZ`
- size: `502`
- prototype: `__int64 __fastcall(WaasMedic::CSandboxRpcWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001ecdc`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x1800098f0`
- `0x180009cd0`
- `0x18001123c`
- `0x18001c554`
- `0x18001d650`
- `0x18001ef7c`
- `0x18002a32c`
- `0x18002a4e4`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001f0a6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001f0a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f07c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f07c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f04e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f04e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f102`

## string_xrefs

- `0x18001f15e`: `Failed to get cV in WaasMedic agent. hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::CSandboxRpcWrapper::PrepareCommandLine(WaasMedic::CSandboxRpcWrapper *this)
{
  WCHAR *v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // r8
  volatile signed __int64 *v5; // rcx
  __int64 v6; // rax
  SIZE_T v7; // rcx
  __int64 v8; // rdi
  WCHAR *lpWideCharStr; // rax
  void *v10; // rdx
  unsigned __int16 **v11; // r8
  WaasMedic *p_Src; // rcx
  unsigned int v13; // edi
  __int128 Src; // [rsp+38h] [rbp-C8h] BYREF
  __m128i si128; // [rsp+48h] [rbp-B8h]
  _OWORD v17[2]; // [rsp+58h] [rbp-A8h] BYREF
  CHAR MultiByteStr[144]; // [rsp+80h] [rbp-80h] BYREF

  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  memset_0(MultiByteStr, 0, 0x81u);
  v2 = 0;
  std::wstring::append(&Src);
  std::wstring::operator+=(&Src, L" ");
  v3 = *((_QWORD *)this + 1);
  memset(v17, 0, sizeof(v17));
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(v3 + 2 * v4) );
  std::wstring::_Construct<1,unsigned short const *>(v17, v3);
  std::wstring::append(&Src);
  v5 = (volatile signed __int64 *)*((_QWORD *)this + 10);
  if ( v5 )
  {
    if ( !TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v5,
            _InterlockedExchangeAdd64(v5 + 17, 0),
            MultiByteStr) )
    {
      v13 = -2147418113;
      LogLevelW(2u, L"Failed to get cV in WaasMedic agent. hr = 0x%08x", 2147549183LL);
      goto LABEL_13;
    }
  }
  else
  {
    MultiByteStr[0] = 0;
  }
  CoTaskMemFree(0);
  v2 = 0;
  v6 = -1;
  do
    ++v6;
  while ( MultiByteStr[v6] );
  v7 = 2 * v6 + 2;
  v8 = (unsigned int)(2 * v6 + 2);
  if ( v8 == v7 )
  {
    lpWideCharStr = (WCHAR *)CoTaskMemAlloc(v7);
    v2 = lpWideCharStr;
    if ( lpWideCharStr )
      MultiByteToWideChar(0, 0, MultiByteStr, -1, lpWideCharStr, (unsigned int)v8 >> 1);
  }
  std::wstring::operator+=(&Src, L" ");
  std::wstring::operator+=(&Src, v2);
  WaasMedic::SafeFree(*((WaasMedic **)this + 2), v10);
  *((_QWORD *)this + 2) = 0;
  p_Src = (WaasMedic *)&Src;
  if ( si128.m128i_i64[1] > 7uLL )
    p_Src = (WaasMedic *)Src;
  v13 = WaasMedic::SafeAllocString(p_Src, (const unsigned __int16 *)this + 8, v11);
LABEL_13:
  std::wstring::~wstring(v17);
  CoTaskMemFree(v2);
  std::wstring::~wstring(&Src);
  return v13;
}

```

## disassembly

```asm
0x18001ef7c  mov     [rsp-8+arg_8], rbx
0x18001ef81  mov     [rsp-8+arg_10], rsi
0x18001ef86  push    rbp
0x18001ef87  push    rdi
0x18001ef88  push    r14
0x18001ef8a  lea     rbp, [rsp-20h]
0x18001ef8f  sub     rsp, 120h
0x18001ef96  mov     rax, cs:__security_cookie
0x18001ef9d  xor     rax, rsp
0x18001efa0  mov     [rbp+30h+var_20], rax
0x18001efa4  mov     rsi, rcx
0x18001efa7  xorps   xmm0, xmm0
0x18001efaa  movups  [rsp+130h+Src], xmm0
0x18001efaf  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001efb7  movdqu  [rsp+130h+var_E8], xmm1
0x18001efbd  xor     r14d, r14d
0x18001efc0  mov     word ptr [rsp+130h+Src], r14w
0x18001efc6  xor     edx, edx; Val
0x18001efc8  mov     r8d, 81h; Size
0x18001efce  lea     rcx, [rbp+30h+MultiByteStr]; void *
0x18001efd2  call    memset_0
0x18001efd7  mov     ebx, r14d
0x18001efda  mov     [rsp+130h+var_100], rbx
0x18001efdf  lea     rdx, [rsi+28h]
0x18001efe3  lea     rcx, [rsp+130h+Src]; Src
0x18001efe8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18001efed  lea     rdx, asc_180078780; " "
0x18001eff4  lea     rcx, [rsp+130h+Src]; Src
0x18001eff9  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18001effe  mov     rdx, [rsi+8]
0x18001f002  xorps   xmm0, xmm0
0x18001f005  movups  [rsp+130h+var_D8], xmm0
0x18001f00a  xorps   xmm1, xmm1
0x18001f00d  movdqu  [rsp+130h+var_C8], xmm1
0x18001f013  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f017  inc     r8
0x18001f01a  cmp     [rdx+r8*2], r14w
0x18001f01f  jnz     short loc_18001F017
0x18001f021  lea     rcx, [rsp+130h+var_D8]
0x18001f026  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001f02b  nop
0x18001f02c  lea     rdx, [rsp+130h+var_D8]
0x18001f031  lea     rcx, [rsp+130h+Src]; Src
0x18001f036  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18001f03b  mov     rcx, [rsi+50h]; this
0x18001f03f  test    rcx, rcx
0x18001f042  jnz     loc_18001F139
0x18001f048  mov     [rbp+30h+MultiByteStr], r14b
0x18001f04c  xor     ecx, ecx; pv
0x18001f04e  call    cs:__imp_CoTaskMemFree
0x18001f054  mov     rbx, r14
0x18001f057  mov     [rsp+130h+var_100], rbx
0x18001f05c  lea     rcx, [rbp+30h+MultiByteStr]
0x18001f060  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f064  inc     rax
0x18001f067  cmp     [rcx+rax], r14b
0x18001f06b  jnz     short loc_18001F064
0x18001f06d  lea     rcx, ds:2[rax*2]; cb
0x18001f075  mov     edi, ecx
0x18001f077  cmp     rdi, rcx
0x18001f07a  jnz     short loc_18001F0AC
0x18001f07c  call    cs:__imp_CoTaskMemAlloc
0x18001f082  mov     rbx, rax
0x18001f085  mov     [rsp+130h+var_100], rax
0x18001f08a  test    rax, rax
0x18001f08d  jz      short loc_18001F0AC
0x18001f08f  shr     edi, 1
0x18001f091  mov     [rsp+130h+cchWideChar], edi; cchWideChar
0x18001f095  mov     [rsp+130h+lpWideCharStr], rax; lpWideCharStr
0x18001f09a  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001f09e  lea     r8, [rbp+30h+MultiByteStr]; lpMultiByteStr
0x18001f0a2  xor     edx, edx; dwFlags
0x18001f0a4  xor     ecx, ecx; CodePage
0x18001f0a6  call    cs:__imp_MultiByteToWideChar
0x18001f0ac  lea     rdx, asc_180078780; " "
0x18001f0b3  lea     rcx, [rsp+130h+Src]; Src
0x18001f0b8  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18001f0bd  mov     rdx, rbx; void *
0x18001f0c0  lea     rcx, [rsp+130h+Src]; Src
0x18001f0c5  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18001f0ca  lea     rdi, [rsi+10h]
0x18001f0ce  mov     rcx, [rdi]; this
0x18001f0d1  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f0d6  mov     [rdi], r14
0x18001f0d9  lea     rcx, [rsp+130h+Src]
0x18001f0de  cmp     qword ptr [rsp+130h+var_E8+8], 7
0x18001f0e4  cmova   rcx, qword ptr [rsp+130h+Src]; this
0x18001f0ea  mov     rdx, rdi; unsigned __int16 *
0x18001f0ed  call    ?SafeAllocString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeAllocString(ushort const *,ushort * *)
0x18001f0f2  mov     edi, eax
0x18001f0f4  lea     rcx, [rsp+130h+var_D8]; void *
0x18001f0f9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f0fe  nop
0x18001f0ff  mov     rcx, rbx; pv
0x18001f102  call    cs:__imp_CoTaskMemFree
0x18001f108  nop
0x18001f109  lea     rcx, [rsp+130h+Src]; void *
0x18001f10e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f113  mov     eax, edi
0x18001f115  mov     rcx, [rbp+30h+var_20]
0x18001f119  xor     rcx, rsp; StackCookie
0x18001f11c  call    __security_check_cookie
0x18001f121  lea     r11, [rsp+130h+var_10]
0x18001f129  mov     rbx, [r11+28h]
0x18001f12d  mov     rsi, [r11+30h]
0x18001f131  mov     rsp, r11
0x18001f134  pop     r14
0x18001f136  pop     rdi
0x18001f137  pop     rbp
0x18001f138  retn
0x18001f139  mov     rdx, r14
0x18001f13c  lock xadd [rcx+88h], rdx; unsigned __int64
0x18001f145  lea     r8, [rbp+30h+MultiByteStr]; char *
0x18001f149  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18001f14e  test    al, al
0x18001f150  jnz     loc_18001F04C
0x18001f156  mov     edi, 8000FFFFh
0x18001f15b  mov     r8d, edi
0x18001f15e  lea     rdx, aFailedToGetCvI_1; "Failed to get cV in WaasMedic agent. hr"...
0x18001f165  mov     ecx, 2; unsigned __int8
0x18001f16a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001f16f  jmp     short loc_18001F0F4
```
