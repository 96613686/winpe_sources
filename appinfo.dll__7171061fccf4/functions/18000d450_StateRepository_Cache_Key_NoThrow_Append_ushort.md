# StateRepository::Cache::Key_NoThrow::Append(ushort)

- ea: `0x18000d450`
- end: `0x18000d532`
- name: `?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z`
- size: `226`
- prototype: `__int64 __fastcall(StateRepository::Cache::Key_NoThrow *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d7f0`

## callees

- `0x18000720c`
- `0x18000d450`
- `0x180046e02`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d4ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d4ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18000d47c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18000d47c`

## string_xrefs

- `0x18000d48f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000d4ab`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::Append(StateRepository::Cache::Key_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  void *v4; // rax
  void *v5; // rsi
  __int64 v7; // rcx
  int v8; // [rsp+20h] [rbp-8h]
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *((_QWORD *)this + 65);
  v3 = v2 + 2;
  if ( (unsigned __int64)(v2 + 2) > *((_QWORD *)this + 66) )
  {
    v4 = (void *)SRCache_AllocStringBuffer((unsigned int)v3);
    v5 = v4;
    if ( !v4 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x8007000ELL,
        v8);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16D,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x8007000ELL,
        v9);
      return 2147942414LL;
    }
    memcpy_0(v4, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
    v7 = *(_QWORD *)this;
    *(_QWORD *)this = v5;
    if ( v7 )
      SRCache_Free(v7);
    v2 = *((_QWORD *)this + 65);
    *((_QWORD *)this + 67) = *(_QWORD *)this;
    *((_QWORD *)this + 66) = v3;
  }
  *(_DWORD *)(*((_QWORD *)this + 67) + 2 * v2) = 94;
  ++*((_QWORD *)this + 65);
  return 0;
}

```

## disassembly

```asm
0x18000d450  mov     [rsp+arg_0], rbx
0x18000d455  mov     [rsp+arg_8], rsi
0x18000d45a  push    rdi; int
0x18000d45b  sub     rsp, 20h
0x18000d45f  mov     rbx, rcx
0x18000d462  mov     rcx, [rcx+208h]
0x18000d469  lea     rdi, [rcx+2]
0x18000d46d  cmp     rdi, [rbx+210h]
0x18000d474  jbe     loc_18000D50B
0x18000d47a  mov     ecx, edi
0x18000d47c  call    cs:__imp_SRCache_AllocStringBuffer
0x18000d482  mov     rsi, rax
0x18000d485  test    rax, rax
0x18000d488  jnz     short loc_18000D4C9
0x18000d48a  mov     rcx, [rsp+28h]; this
0x18000d48f  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000d496  mov     r9d, 8007000Eh; char *
0x18000d49c  mov     edx, 193h; void *
0x18000d4a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d4a6  mov     rcx, [rsp+28h]; this
0x18000d4ab  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000d4b2  mov     r9d, 8007000Eh; char *
0x18000d4b8  mov     edx, 16Dh; void *
0x18000d4bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d4c2  mov     eax, 8007000Eh
0x18000d4c7  jmp     short loc_18000D522
0x18000d4c9  mov     r8, [rbx+210h]
0x18000d4d0  mov     rcx, rsi; void *
0x18000d4d3  mov     rdx, [rbx+218h]; Src
0x18000d4da  add     r8, r8; Size
0x18000d4dd  call    memcpy_0
0x18000d4e2  mov     rcx, [rbx]
0x18000d4e5  mov     [rbx], rsi
0x18000d4e8  test    rcx, rcx
0x18000d4eb  jz      short loc_18000D4F3
0x18000d4ed  call    cs:__imp_SRCache_Free
0x18000d4f3  mov     rax, [rbx]
0x18000d4f6  mov     rcx, [rbx+208h]
0x18000d4fd  mov     [rbx+218h], rax
0x18000d504  mov     [rbx+210h], rdi
0x18000d50b  mov     rax, [rbx+218h]
0x18000d512  mov     dword ptr [rax+rcx*2], 5Eh ; '^'
0x18000d519  inc     qword ptr [rbx+208h]
0x18000d520  xor     eax, eax
0x18000d522  mov     rbx, [rsp+28h+arg_0]
0x18000d527  mov     rsi, [rsp+28h+arg_8]
0x18000d52c  add     rsp, 20h
0x18000d530  pop     rdi
0x18000d531  retn
```
