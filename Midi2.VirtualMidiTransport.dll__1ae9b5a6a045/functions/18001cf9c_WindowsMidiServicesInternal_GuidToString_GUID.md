# WindowsMidiServicesInternal::GuidToString(_GUID)

- ea: `0x18001cf9c`
- end: `0x18001d07a`
- name: `?GuidToString@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001d680`

## callees

- `0x1800038f0`
- `0x18000bf6c`
- `0x18000cb48`
- `0x18001cf9c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001cfd3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001cfd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d00b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d00b`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::GuidToString(__int64 a1, const IID *a2)
{
  __int64 v3; // r8
  __int128 v4; // xmm0
  __m128i v5; // xmm1
  LPOLESTR lpsz; // [rsp+20h] [rbp-40h] BYREF
  __int128 v8; // [rsp+30h] [rbp-30h] BYREF
  __m128i si128; // [rsp+40h] [rbp-20h]

  lpsz = 0;
  if ( StringFromCLSID(a2, &lpsz) < 0 )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    std::wstring::_Construct<1,unsigned short const *>(a1, &S2);
  }
  else
  {
    si128 = 0;
    v3 = -1;
    v8 = 0;
    do
      ++v3;
    while ( lpsz[v3] );
    std::wstring::_Construct<1,unsigned short const *>(&v8, lpsz);
    CoTaskMemFree(lpsz);
    v4 = v8;
    LOWORD(v8) = 0;
    v5 = si128;
    *(_OWORD *)a1 = v4;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    *(__m128i *)(a1 + 16) = v5;
    std::wstring::~wstring(&v8);
  }
  return a1;
}

```

## disassembly

```asm
0x18001cf9c  mov     [rsp-8+arg_10], rbx
0x18001cfa1  mov     [rsp-8+arg_18], rdi
0x18001cfa6  push    rbp
0x18001cfa7  mov     rbp, rsp
0x18001cfaa  sub     rsp, 60h
0x18001cfae  mov     rax, cs:__security_cookie
0x18001cfb5  xor     rax, rsp
0x18001cfb8  mov     [rbp+var_10], rax
0x18001cfbc  mov     rax, rdx
0x18001cfbf  mov     [rbp+lpsz], rcx
0x18001cfc3  mov     rbx, rcx
0x18001cfc6  lea     rdx, [rbp+lpsz]; lplpsz
0x18001cfca  xor     edi, edi
0x18001cfcc  mov     rcx, rax; rclsid
0x18001cfcf  mov     [rbp+lpsz], rdi
0x18001cfd3  call    cs:__imp_StringFromCLSID
0x18001cfd9  xorps   xmm0, xmm0
0x18001cfdc  test    eax, eax
0x18001cfde  js      short loc_18001D03C
0x18001cfe0  mov     rdx, [rbp+lpsz]
0x18001cfe4  xorps   xmm1, xmm1
0x18001cfe7  movdqu  [rbp+var_20], xmm1
0x18001cfec  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001cff0  movups  [rbp+var_30], xmm0
0x18001cff4  inc     r8
0x18001cff7  cmp     [rdx+r8*2], di
0x18001cffc  jnz     short loc_18001CFF4
0x18001cffe  lea     rcx, [rbp+var_30]
0x18001d002  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d007  mov     rcx, [rbp+lpsz]; pv
0x18001d00b  call    cs:__imp_CoTaskMemFree
0x18001d011  movups  xmm0, [rbp+var_30]
0x18001d015  lea     rcx, [rbp+var_30]
0x18001d019  mov     word ptr [rbp+var_30], di
0x18001d01d  movups  xmm1, [rbp+var_20]
0x18001d021  movups  xmmword ptr [rbx], xmm0
0x18001d024  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001d02c  movdqu  [rbp+var_20], xmm0
0x18001d031  movups  xmmword ptr [rbx+10h], xmm1
0x18001d035  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d03a  jmp     short loc_18001D059
0x18001d03c  movups  xmmword ptr [rbx], xmm0
0x18001d03f  xor     r8d, r8d
0x18001d042  mov     [rbx+10h], rdi
0x18001d046  lea     rdx, S2
0x18001d04d  mov     [rbx+18h], rdi
0x18001d051  mov     rcx, rbx
0x18001d054  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d059  mov     rax, rbx
0x18001d05c  mov     rcx, [rbp+var_10]
0x18001d060  xor     rcx, rsp; StackCookie
0x18001d063  call    __security_check_cookie
0x18001d068  lea     r11, [rsp+60h+var_s0]
0x18001d06d  mov     rbx, [r11+20h]
0x18001d071  mov     rdi, [r11+28h]
0x18001d075  mov     rsp, r11
0x18001d078  pop     rbp
0x18001d079  retn
```
