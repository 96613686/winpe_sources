# WindowsMidiServicesInternal::GuidToString(_GUID)

- ea: `0x1800253a8`
- end: `0x180025486`
- name: `?GuidToString@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@Z`
- size: `222`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180025070`
- `0x18003b10c`

## callees

- `0x180005020`
- `0x18000d430`
- `0x180013118`
- `0x1800253a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800253df`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800253df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025417`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025417`

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
    std::wstring::_Construct<1,unsigned short const *>(a1);
  }
  else
  {
    si128 = 0;
    v3 = -1;
    v8 = 0;
    do
      ++v3;
    while ( lpsz[v3] );
    std::wstring::_Construct<1,unsigned short const *>(&v8);
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
0x1800253a8  mov     [rsp-8+arg_10], rbx
0x1800253ad  mov     [rsp-8+arg_18], rdi
0x1800253b2  push    rbp
0x1800253b3  mov     rbp, rsp
0x1800253b6  sub     rsp, 60h
0x1800253ba  mov     rax, cs:__security_cookie
0x1800253c1  xor     rax, rsp
0x1800253c4  mov     [rbp+var_10], rax
0x1800253c8  mov     rax, rdx
0x1800253cb  mov     [rbp+lpsz], rcx
0x1800253cf  mov     rbx, rcx
0x1800253d2  lea     rdx, [rbp+lpsz]; lplpsz
0x1800253d6  xor     edi, edi
0x1800253d8  mov     rcx, rax; rclsid
0x1800253db  mov     [rbp+lpsz], rdi
0x1800253df  call    cs:__imp_StringFromCLSID
0x1800253e5  xorps   xmm0, xmm0
0x1800253e8  test    eax, eax
0x1800253ea  js      short loc_180025448
0x1800253ec  mov     rdx, [rbp+lpsz]
0x1800253f0  xorps   xmm1, xmm1
0x1800253f3  movdqu  [rbp+var_20], xmm1
0x1800253f8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800253fc  movups  [rbp+var_30], xmm0
0x180025400  inc     r8
0x180025403  cmp     [rdx+r8*2], di
0x180025408  jnz     short loc_180025400
0x18002540a  lea     rcx, [rbp+var_30]
0x18002540e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180025413  mov     rcx, [rbp+lpsz]; pv
0x180025417  call    cs:__imp_CoTaskMemFree
0x18002541d  movups  xmm0, [rbp+var_30]
0x180025421  lea     rcx, [rbp+var_30]; void *
0x180025425  mov     word ptr [rbp+var_30], di
0x180025429  movups  xmm1, [rbp+var_20]
0x18002542d  movups  xmmword ptr [rbx], xmm0
0x180025430  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180025438  movdqu  [rbp+var_20], xmm0
0x18002543d  movups  xmmword ptr [rbx+10h], xmm1
0x180025441  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025446  jmp     short loc_180025465
0x180025448  movups  xmmword ptr [rbx], xmm0
0x18002544b  xor     r8d, r8d
0x18002544e  mov     [rbx+10h], rdi
0x180025452  lea     rdx, S1
0x180025459  mov     [rbx+18h], rdi
0x18002545d  mov     rcx, rbx
0x180025460  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180025465  mov     rax, rbx
0x180025468  mov     rcx, [rbp+var_10]
0x18002546c  xor     rcx, rsp; StackCookie
0x18002546f  call    __security_check_cookie
0x180025474  lea     r11, [rsp+60h+var_s0]
0x180025479  mov     rbx, [r11+20h]
0x18002547d  mov     rdi, [r11+28h]
0x180025481  mov     rsp, r11
0x180025484  pop     rbp
0x180025485  retn
```
