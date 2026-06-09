# SRCacheContext::StringToInt64(ushort const *,__int64 *)

- ea: `0x18000c8ac`
- end: `0x18000c921`
- name: `?StringToInt64@SRCacheContext@@CAJPEBGPEA_J@Z`
- size: `117`
- prototype: `static int(const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c244`
- `0x18000c2e8`

## callees

- `0x18000940c`
- `0x18000c8ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoll` at `0x18000c8d0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoll` at `0x18000c8d0`

## string_xrefs

- `0x18000c8f6`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext::StringToInt64(const unsigned __int16 *a1, __int64 *a2)
{
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  wchar_t *v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  *a2 = wcstoll(a1, &v6, 16);
  if ( v6 && v6 != a1 && !*v6 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x176,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)0x8000FFFFLL,
    v4);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18000c8ac  mov     rax, rsp
0x18000c8af  mov     [rax+8], rbx
0x18000c8b3  mov     [rax+18h], rsi
0x18000c8b7  push    rdi; int
0x18000c8b8  sub     rsp, 20h
0x18000c8bc  xor     esi, esi
0x18000c8be  mov     rbx, rdx
0x18000c8c1  lea     rdx, [rax+10h]; EndPtr
0x18000c8c5  mov     [rax+10h], rsi
0x18000c8c9  mov     rdi, rcx
0x18000c8cc  lea     r8d, [rsi+10h]; Radix
0x18000c8d0  call    cs:__imp_wcstoll
0x18000c8d6  mov     [rbx], rax
0x18000c8d9  mov     rax, [rsp+28h+arg_8]
0x18000c8de  test    rax, rax
0x18000c8e1  jz      short loc_18000C8F1
0x18000c8e3  cmp     rax, rdi
0x18000c8e6  jz      short loc_18000C8F1
0x18000c8e8  cmp     [rax], si
0x18000c8eb  jnz     short loc_18000C8F1
0x18000c8ed  xor     eax, eax
0x18000c8ef  jmp     short loc_18000C911
0x18000c8f1  mov     rcx, [rsp+28h]; this
0x18000c8f6  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c8fd  mov     ebx, 8000FFFFh
0x18000c902  mov     edx, 176h; void *
0x18000c907  mov     r9d, ebx; char *
0x18000c90a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c90f  mov     eax, ebx
0x18000c911  mov     rbx, [rsp+28h+arg_0]
0x18000c916  mov     rsi, [rsp+28h+arg_10]
0x18000c91b  add     rsp, 20h
0x18000c91f  pop     rdi
0x18000c920  retn
```
