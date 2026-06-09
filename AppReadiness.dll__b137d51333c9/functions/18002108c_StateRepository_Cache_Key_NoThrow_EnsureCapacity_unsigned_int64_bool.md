# StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)

- ea: `0x18002108c`
- end: `0x18002112d`
- name: `?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z`
- size: `161`
- prototype: `__int64 __fastcall(StateRepository::Cache::Key_NoThrow *__hidden this, unsigned __int64, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002ff94`
- `0x1800305a8`

## callees

- `0x18002108c`
- `0x180030914`
- `0x180075b58`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x1800210f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x1800210f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180021125`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180021125`

## string_xrefs

- `0x180021108`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::EnsureCapacity(
        StateRepository::Cache::Key_NoThrow *this,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rcx
  void *v8; // rax
  void *v9; // rsi
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 <= *((_QWORD *)this + 66) )
    return 0;
  v8 = (void *)SRCache_AllocStringBuffer((unsigned int)a2, a2, a3, a4);
  v9 = v8;
  if ( v8 )
  {
    memcpy_0(v8, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
    v7 = *(_QWORD *)this;
    *(_QWORD *)this = v9;
    if ( v7 )
      SRCache_Free();
    *((_QWORD *)this + 67) = *(_QWORD *)this;
    *((_QWORD *)this + 66) = a2;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x193,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
    (const char *)0x8007000ELL,
    v10);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18002108c  mov     [rsp+arg_0], rbx
0x180021091  mov     [rsp+arg_8], rsi
0x180021096  push    rdi; int
0x180021097  sub     rsp, 20h
0x18002109b  mov     rdi, rdx
0x18002109e  mov     rbx, rcx
0x1800210a1  cmp     rdx, [rcx+210h]
0x1800210a8  ja      short loc_1800210F3
0x1800210aa  xor     eax, eax
0x1800210ac  mov     rbx, [rsp+28h+arg_0]
0x1800210b1  mov     rsi, [rsp+28h+arg_8]
0x1800210b6  add     rsp, 20h
0x1800210ba  pop     rdi
0x1800210bb  retn
0x1800210bc  mov     r8, [rbx+210h]
0x1800210c3  mov     rcx, rsi; void *
0x1800210c6  mov     rdx, [rbx+218h]; Src
0x1800210cd  add     r8, r8; Size
0x1800210d0  call    memcpy_0
0x1800210d5  mov     rcx, [rbx]
0x1800210d8  mov     [rbx], rsi
0x1800210db  test    rcx, rcx
0x1800210de  jnz     short loc_180021125
0x1800210e0  mov     rax, [rbx]
0x1800210e3  mov     [rbx+218h], rax
0x1800210ea  mov     [rbx+210h], rdi
0x1800210f1  jmp     short loc_1800210AA
0x1800210f3  mov     ecx, edi
0x1800210f5  call    cs:__imp_SRCache_AllocStringBuffer
0x1800210fb  mov     rsi, rax
0x1800210fe  test    rax, rax
0x180021101  jnz     short loc_1800210BC
0x180021103  mov     rcx, [rsp+28h]; this
0x180021108  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002110f  mov     ebx, 8007000Eh
0x180021114  mov     edx, 193h; void *
0x180021119  mov     r9d, ebx; char *
0x18002111c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021121  mov     eax, ebx
0x180021123  jmp     short loc_1800210AC
0x180021125  call    cs:__imp_SRCache_Free
0x18002112b  jmp     short loc_1800210E0
```
