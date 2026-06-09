# AiSetTokenAttributes

- ea: `0x140029678`
- end: `0x14002970d`
- name: `AiSetTokenAttributes`
- size: `149`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001faf4`
- `0x140034550`
- `0x1400373b0`

## callees

- `0x140006a20`
- `0x140029678`

## import_xrefs

- `ntoskrnl!SeSetSecurityAttributesToken` at `0x1400296c5`
- `ntoskrnl!SeSetSecurityAttributesToken` at `0x1400296e8`
- `ntoskrnl!SeSetSecurityAttributesToken` at `0x1400296c5`
- `ntoskrnl!SeSetSecurityAttributesToken` at `0x1400296e8`

## pseudocode

```c
__int64 __fastcall AiSetTokenAttributes(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __m128i si128; // xmm0
  __m128i v6; // [rsp+20h] [rbp-28h] BYREF
  int v7; // [rsp+30h] [rbp-18h]

  if ( *(_DWORD *)(a2 + 4) > 5u )
    return 3221225701LL;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v7 = _mm_cvtsi128_si32(si128);
  v6 = si128;
  result = ((__int64 (__fastcall *)(__int64, _QWORD, __m128i *, __int64 *))SeSetSecurityAttributesToken)(
             a1,
             0,
             &v6,
             &AipDefaultAttributes);
  if ( (int)result >= 0 )
  {
    if ( *(_DWORD *)(a2 + 4) )
      return ((__int64 (__fastcall *)(__int64, _QWORD, __m128i *, __int64))SeSetSecurityAttributesToken)(a1, 0, &v6, a2);
  }
  return result;
}

```

## disassembly

```asm
0x140029678  mov     [rsp+arg_10], rbx
0x14002967d  push    rdi
0x14002967e  sub     rsp, 40h
0x140029682  mov     rax, cs:__security_cookie
0x140029689  xor     rax, rsp
0x14002968c  mov     [rsp+48h+var_10], rax
0x140029691  cmp     dword ptr [rdx+4], 5
0x140029695  mov     rbx, rdx
0x140029698  mov     rdi, rcx
0x14002969b  jbe     short loc_1400296A4
0x14002969d  mov     eax, 0C00000E5h
0x1400296a2  jmp     short loc_1400296F4
0x1400296a4  movdqa  xmm0, cs:__xmm@00000004000000040000000400000004
0x1400296ac  lea     r9, AipDefaultAttributes
0x1400296b3  lea     r8, [rsp+48h+var_28]
0x1400296b8  movd    [rsp+48h+var_18], xmm0
0x1400296be  xor     edx, edx
0x1400296c0  movups  [rsp+48h+var_28], xmm0
0x1400296c5  call    cs:__imp_SeSetSecurityAttributesToken
0x1400296cc  nop     dword ptr [rax+rax+00h]
0x1400296d1  test    eax, eax
0x1400296d3  js      short loc_1400296F4
0x1400296d5  cmp     dword ptr [rbx+4], 0
0x1400296d9  jz      short loc_1400296F4
0x1400296db  mov     r9, rbx
0x1400296de  lea     r8, [rsp+48h+var_28]
0x1400296e3  xor     edx, edx
0x1400296e5  mov     rcx, rdi
0x1400296e8  call    cs:__imp_SeSetSecurityAttributesToken
0x1400296ef  nop     dword ptr [rax+rax+00h]
0x1400296f4  mov     rcx, [rsp+48h+var_10]
0x1400296f9  xor     rcx, rsp; StackCookie
0x1400296fc  call    __security_check_cookie
0x140029701  mov     rbx, [rsp+48h+arg_10]
0x140029706  add     rsp, 40h
0x14002970a  pop     rdi
0x14002970b  retn
```
