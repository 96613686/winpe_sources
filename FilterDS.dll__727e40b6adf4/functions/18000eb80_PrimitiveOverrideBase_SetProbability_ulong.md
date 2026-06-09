# PrimitiveOverrideBase::SetProbability(ulong)

- ea: `0x18000eb80`
- end: `0x18000ec05`
- name: `?SetProbability@PrimitiveOverrideBase@@UEAAJK@Z`
- size: `133`
- prototype: `int(PrimitiveOverrideBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000cd18`
- `0x18000eb80`
- `0x180024010`

## string_xrefs

- `0x18000ebf2`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrimitiveOverrideBase::SetProbability(PrimitiveOverrideBase *this, unsigned int a2)
{
  __int64 (__fastcall ***v3)(_QWORD); // rcx
  int v4; // eax
  __int64 result; // rax
  const char *v6; // r9
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = (__int64 (__fastcall ***)(_QWORD))*((_QWORD *)this + 2);
  try
  {
    v4 = (**v3)(v3);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v4,
        v7);
    result = (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(MEMORY[0] + 32LL))(0, a2);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4B,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\primitiveoverride.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000eb80  push    rbx; int
0x18000eb82  sub     rsp, 20h
0x18000eb86  mov     ebx, edx
0x18000eb88  mov     rcx, [rcx+10h]
0x18000eb8c  mov     [rsp+28h+arg_0], 0
0x18000eb95  mov     rax, [rcx]
0x18000eb98  lea     r8, [rsp+28h+arg_0]
0x18000eb9d  lea     rdx, _GUID_5f445657_746b_468a_9ebb_ae80a72c4f7a
0x18000eba4  mov     rax, [rax]
0x18000eba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebac  mov     rcx, [rsp+28h]; this
0x18000ebb1  test    eax, eax
0x18000ebb3  js      short loc_18000EBEF
0x18000ebb5  mov     rcx, [rsp+28h+arg_0]
0x18000ebba  mov     rax, [rcx]
0x18000ebbd  mov     edx, ebx
0x18000ebbf  mov     rax, [rax+20h]
0x18000ebc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebc8  mov     ebx, eax
0x18000ebca  mov     rcx, [rsp+28h+arg_0]
0x18000ebcf  test    rcx, rcx
0x18000ebd2  jz      short loc_18000EBE1
0x18000ebd4  mov     rdx, [rcx]
0x18000ebd7  mov     rax, [rdx+10h]
0x18000ebdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebe0  nop
0x18000ebe1  mov     eax, ebx
0x18000ebe3  jmp     short loc_18000EBE9
0x18000ebe5  mov     eax, dword ptr [rsp+28h+arg_0]
0x18000ebe9  add     rsp, 20h
0x18000ebed  pop     rbx
0x18000ebee  retn
0x18000ebef  mov     r9d, eax; char *
0x18000ebf2  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ebf9  mov     edx, 1CBEh; void *
0x18000ebfe  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
