# StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)

- ea: `0x1800640a8`
- end: `0x180064149`
- name: `?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z`
- size: `161`
- prototype: `int(StateRepository::Cache::Key_NoThrow *__hidden this, unsigned __int64, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180063c0c`

## callees

- `0x18002c8d0`
- `0x1800640a8`
- `0x180088d45`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180064141`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180064141`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180064111`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180064111`

## string_xrefs

- `0x180064124`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::EnsureCapacity(
        StateRepository::Cache::Key_NoThrow *this,
        unsigned __int64 a2)
{
  __int64 v5; // rcx
  void *v6; // rax
  void *v7; // rsi
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 <= *((_QWORD *)this + 66) )
    return 0;
  v6 = (void *)SRCache_AllocStringBuffer((unsigned int)a2);
  v7 = v6;
  if ( v6 )
  {
    memcpy_0(v6, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
    v5 = *(_QWORD *)this;
    *(_QWORD *)this = v7;
    if ( v5 )
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
    v8);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800640a8  mov     [rsp+arg_0], rbx
0x1800640ad  mov     [rsp+arg_8], rsi
0x1800640b2  push    rdi; int
0x1800640b3  sub     rsp, 20h
0x1800640b7  mov     rdi, rdx
0x1800640ba  mov     rbx, rcx
0x1800640bd  cmp     rdx, [rcx+210h]
0x1800640c4  ja      short loc_18006410F
0x1800640c6  xor     eax, eax
0x1800640c8  mov     rbx, [rsp+28h+arg_0]
0x1800640cd  mov     rsi, [rsp+28h+arg_8]
0x1800640d2  add     rsp, 20h
0x1800640d6  pop     rdi
0x1800640d7  retn
0x1800640d8  mov     r8, [rbx+210h]
0x1800640df  mov     rcx, rsi; void *
0x1800640e2  mov     rdx, [rbx+218h]; Src
0x1800640e9  add     r8, r8; Size
0x1800640ec  call    memcpy_0
0x1800640f1  mov     rcx, [rbx]
0x1800640f4  mov     [rbx], rsi
0x1800640f7  test    rcx, rcx
0x1800640fa  jnz     short loc_180064141
0x1800640fc  mov     rax, [rbx]
0x1800640ff  mov     [rbx+218h], rax
0x180064106  mov     [rbx+210h], rdi
0x18006410d  jmp     short loc_1800640C6
0x18006410f  mov     ecx, edi
0x180064111  call    cs:__imp_SRCache_AllocStringBuffer
0x180064117  mov     rsi, rax
0x18006411a  test    rax, rax
0x18006411d  jnz     short loc_1800640D8
0x18006411f  mov     rcx, [rsp+28h]; this
0x180064124  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18006412b  mov     ebx, 8007000Eh
0x180064130  mov     edx, 193h; void *
0x180064135  mov     r9d, ebx; char *
0x180064138  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006413d  mov     eax, ebx
0x18006413f  jmp     short loc_1800640C8
0x180064141  call    cs:__imp_SRCache_Free
0x180064147  jmp     short loc_1800640FC
```
