# PrimitiveOverrideBase::GetProbability(ulong *)

- ea: `0x18000e570`
- end: `0x18000e5f7`
- name: `?GetProbability@PrimitiveOverrideBase@@UEAAJPEAK@Z`
- size: `135`
- prototype: `__int64 __fastcall(PrimitiveOverrideBase *this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000cd18`
- `0x18000e570`
- `0x180024010`

## string_xrefs

- `0x18000e5e4`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrimitiveOverrideBase::GetProbability(PrimitiveOverrideBase *this, unsigned int *a2)
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
    result = (*(unsigned int (__fastcall **)(_QWORD, unsigned int *))(MEMORY[0] + 24LL))(0, a2);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x45,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\primitiveoverride.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000e570  push    rbx; int
0x18000e572  sub     rsp, 20h
0x18000e576  mov     rbx, rdx
0x18000e579  mov     rcx, [rcx+10h]
0x18000e57d  mov     [rsp+28h+arg_0], 0
0x18000e586  mov     rax, [rcx]
0x18000e589  lea     r8, [rsp+28h+arg_0]
0x18000e58e  lea     rdx, _GUID_5f445657_746b_468a_9ebb_ae80a72c4f7a
0x18000e595  mov     rax, [rax]
0x18000e598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e59d  mov     rcx, [rsp+28h]; this
0x18000e5a2  test    eax, eax
0x18000e5a4  js      short loc_18000E5E1
0x18000e5a6  mov     rcx, [rsp+28h+arg_0]
0x18000e5ab  mov     rax, [rcx]
0x18000e5ae  mov     rdx, rbx
0x18000e5b1  mov     rax, [rax+18h]
0x18000e5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5ba  mov     ebx, eax
0x18000e5bc  mov     rcx, [rsp+28h+arg_0]
0x18000e5c1  test    rcx, rcx
0x18000e5c4  jz      short loc_18000E5D3
0x18000e5c6  mov     rdx, [rcx]
0x18000e5c9  mov     rax, [rdx+10h]
0x18000e5cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5d2  nop
0x18000e5d3  mov     eax, ebx
0x18000e5d5  jmp     short loc_18000E5DB
0x18000e5d7  mov     eax, dword ptr [rsp+28h+arg_0]
0x18000e5db  add     rsp, 20h
0x18000e5df  pop     rbx
0x18000e5e0  retn
0x18000e5e1  mov     r9d, eax; char *
0x18000e5e4  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e5eb  mov     edx, 1CBEh; void *
0x18000e5f0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
