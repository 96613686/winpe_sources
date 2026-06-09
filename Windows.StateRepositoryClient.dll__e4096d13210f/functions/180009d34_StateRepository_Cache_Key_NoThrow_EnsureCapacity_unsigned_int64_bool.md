# StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)

- ea: `0x180009d34`
- end: `0x180009dd1`
- name: `?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z`
- size: `157`
- prototype: `__int64 __fastcall(const void **this, const void *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180009800`
- `0x18000a52c`
- `0x180013264`
- `0x180015190`

## callees

- `0x1800075e4`
- `0x180009d34`
- `0x180026690`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009da8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009da8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180009d54`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180009d54`

## string_xrefs

- `0x180009d67`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`

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
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Key.hpp",
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
0x180009d34  mov     [rsp+arg_0], rbx
0x180009d39  mov     [rsp+arg_8], rsi
0x180009d3e  push    rdi; int
0x180009d3f  sub     rsp, 20h
0x180009d43  mov     rdi, rdx
0x180009d46  mov     rbx, rcx
0x180009d49  cmp     rdx, [rcx+210h]
0x180009d50  jbe     short loc_180009DBF
0x180009d52  mov     ecx, edi
0x180009d54  call    cs:__imp_SRCache_AllocStringBuffer
0x180009d5a  mov     rsi, rax
0x180009d5d  test    rax, rax
0x180009d60  jnz     short loc_180009D84
0x180009d62  mov     rcx, [rsp+28h]; this
0x180009d67  lea     r8, aOnecoreBaseApp_20
0x180009d6e  mov     ebx, 8007000Eh
0x180009d73  mov     edx, 193h; void *
0x180009d78  mov     r9d, ebx; char *
0x180009d7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180009d80  mov     eax, ebx
0x180009d82  jmp     short loc_180009DC1
0x180009d84  mov     r8, [rbx+210h]
0x180009d8b  mov     rcx, rsi; void *
0x180009d8e  mov     rdx, [rbx+218h]; Src
0x180009d95  add     r8, r8; Size
0x180009d98  call    memcpy_0
0x180009d9d  mov     rcx, [rbx]
0x180009da0  mov     [rbx], rsi
0x180009da3  test    rcx, rcx
0x180009da6  jz      short loc_180009DAE
0x180009da8  call    cs:__imp_SRCache_Free
0x180009dae  mov     rax, [rbx]
0x180009db1  mov     [rbx+218h], rax
0x180009db8  mov     [rbx+210h], rdi
0x180009dbf  xor     eax, eax
0x180009dc1  mov     rbx, [rsp+28h+arg_0]
0x180009dc6  mov     rsi, [rsp+28h+arg_8]
0x180009dcb  add     rsp, 20h
0x180009dcf  pop     rdi
0x180009dd0  retn
```
