# WindowsMidiServicesInternal::GuidToString(_GUID)

- ea: `0x1400250ac`
- end: `0x14002518a`
- name: `?GuidToString@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140024010`
- `0x14003b55c`
- `0x14003e0d0`

## callees

- `0x1400054c0`
- `0x1400072d4`
- `0x140007c20`
- `0x1400250ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1400250e3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1400250e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002511b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002511b`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::GuidToString(__int64 a1, const IID *a2)
{
  unsigned __int64 v3; // r8
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
    std::wstring::_Construct<1,unsigned short const *>((char **)a1, &S2, 0);
  }
  else
  {
    si128 = 0;
    v3 = -1;
    v8 = 0;
    do
      ++v3;
    while ( lpsz[v3] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v8, lpsz, v3);
    CoTaskMemFree(lpsz);
    v4 = v8;
    LOWORD(v8) = 0;
    v5 = si128;
    *(_OWORD *)a1 = v4;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    *(__m128i *)(a1 + 16) = v5;
    std::wstring::~wstring((char **)&v8);
  }
  return a1;
}

```

## disassembly

```asm
0x1400250ac  mov     [rsp-8+arg_10], rbx
0x1400250b1  mov     [rsp-8+arg_18], rdi
0x1400250b6  push    rbp
0x1400250b7  mov     rbp, rsp
0x1400250ba  sub     rsp, 60h
0x1400250be  mov     rax, cs:__security_cookie
0x1400250c5  xor     rax, rsp
0x1400250c8  mov     [rbp+var_10], rax
0x1400250cc  mov     rax, rdx
0x1400250cf  mov     [rbp+lpsz], rcx
0x1400250d3  mov     rbx, rcx
0x1400250d6  lea     rdx, [rbp+lpsz]; lplpsz
0x1400250da  xor     edi, edi
0x1400250dc  mov     rcx, rax; rclsid
0x1400250df  mov     [rbp+lpsz], rdi
0x1400250e3  call    cs:__imp_StringFromCLSID
0x1400250e9  xorps   xmm0, xmm0
0x1400250ec  test    eax, eax
0x1400250ee  js      short loc_14002514C
0x1400250f0  mov     rdx, [rbp+lpsz]
0x1400250f4  xorps   xmm1, xmm1
0x1400250f7  movdqu  [rbp+var_20], xmm1
0x1400250fc  or      r8, 0FFFFFFFFFFFFFFFFh
0x140025100  movups  [rbp+var_30], xmm0
0x140025104  inc     r8
0x140025107  cmp     [rdx+r8*2], di
0x14002510c  jnz     short loc_140025104
0x14002510e  lea     rcx, [rbp+var_30]
0x140025112  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140025117  mov     rcx, [rbp+lpsz]; pv
0x14002511b  call    cs:__imp_CoTaskMemFree
0x140025121  movups  xmm0, [rbp+var_30]
0x140025125  lea     rcx, [rbp+var_30]; void *
0x140025129  mov     word ptr [rbp+var_30], di
0x14002512d  movups  xmm1, [rbp+var_20]
0x140025131  movups  xmmword ptr [rbx], xmm0
0x140025134  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14002513c  movdqu  [rbp+var_20], xmm0
0x140025141  movups  xmmword ptr [rbx+10h], xmm1
0x140025145  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002514a  jmp     short loc_140025169
0x14002514c  movups  xmmword ptr [rbx], xmm0
0x14002514f  xor     r8d, r8d
0x140025152  mov     [rbx+10h], rdi
0x140025156  lea     rdx, S2
0x14002515d  mov     [rbx+18h], rdi
0x140025161  mov     rcx, rbx
0x140025164  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140025169  mov     rax, rbx
0x14002516c  mov     rcx, [rbp+var_10]
0x140025170  xor     rcx, rsp; StackCookie
0x140025173  call    __security_check_cookie
0x140025178  lea     r11, [rsp+60h+var_s0]
0x14002517d  mov     rbx, [r11+20h]
0x140025181  mov     rdi, [r11+28h]
0x140025185  mov     rsp, r11
0x140025188  pop     rbp
0x140025189  retn
```
