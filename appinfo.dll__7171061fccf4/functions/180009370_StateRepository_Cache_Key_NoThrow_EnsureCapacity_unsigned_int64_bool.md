# StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)

- ea: `0x180009370`
- end: `0x18000940e`
- name: `?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z`
- size: `158`
- prototype: `__int64 __fastcall(const void **this, const void *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180007230`
- `0x1800077c0`
- `0x1800089e0`
- `0x180008f10`

## callees

- `0x18000720c`
- `0x180009370`
- `0x180046e02`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800093e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800093e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180009390`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180009390`

## string_xrefs

- `0x1800093a3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::EnsureCapacity(const void **this, const void *a2)
{
  void *v4; // rax
  const void *v5; // rsi
  const void *v7; // rcx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > this[66] )
  {
    v4 = (void *)SRCache_AllocStringBuffer((unsigned int)a2);
    v5 = v4;
    if ( !v4 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x8007000ELL,
        v8);
      return 2147942414LL;
    }
    memcpy_0(v4, this[67], 2LL * (_QWORD)this[66]);
    v7 = *this;
    *this = v5;
    if ( v7 )
      SRCache_Free(v7);
    this[67] = *this;
    this[66] = a2;
  }
  return 0;
}

```

## disassembly

```asm
0x180009370  mov     [rsp+arg_0], rbx
0x180009375  mov     [rsp+arg_8], rsi
0x18000937a  push    rdi; int
0x18000937b  sub     rsp, 20h
0x18000937f  mov     rdi, rdx
0x180009382  mov     rbx, rcx
0x180009385  cmp     rdx, [rcx+210h]
0x18000938c  jbe     short loc_1800093FC
0x18000938e  mov     ecx, edi
0x180009390  call    cs:__imp_SRCache_AllocStringBuffer
0x180009396  mov     rsi, rax
0x180009399  test    rax, rax
0x18000939c  jnz     short loc_1800093C1
0x18000939e  mov     rcx, [rsp+28h]; this
0x1800093a3  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800093aa  mov     r9d, 8007000Eh; char *
0x1800093b0  mov     edx, 193h; void *
0x1800093b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800093ba  mov     eax, 8007000Eh
0x1800093bf  jmp     short loc_1800093FE
0x1800093c1  mov     r8, [rbx+210h]
0x1800093c8  mov     rcx, rsi; void *
0x1800093cb  mov     rdx, [rbx+218h]; Src
0x1800093d2  add     r8, r8; Size
0x1800093d5  call    memcpy_0
0x1800093da  mov     rcx, [rbx]
0x1800093dd  mov     [rbx], rsi
0x1800093e0  test    rcx, rcx
0x1800093e3  jz      short loc_1800093EB
0x1800093e5  call    cs:__imp_SRCache_Free
0x1800093eb  mov     rax, [rbx]
0x1800093ee  mov     [rbx+218h], rax
0x1800093f5  mov     [rbx+210h], rdi
0x1800093fc  xor     eax, eax
0x1800093fe  mov     rbx, [rsp+28h+arg_0]
0x180009403  mov     rsi, [rsp+28h+arg_8]
0x180009408  add     rsp, 20h
0x18000940c  pop     rdi
0x18000940d  retn
```
