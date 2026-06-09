# CChangeApplier::SaveChangeWithChangeUnitsComplete(void)

- ea: `0x180045000`
- end: `0x180045058`
- name: `?SaveChangeWithChangeUnitsComplete@CChangeApplier@@UEAAJXZ`
- size: `88`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x180045000`
- `0x180094010`

## string_xrefs

- `0x18004502c`: `CChangeApplier::SaveChangeWithChangeUnitsComplete`

## pseudocode

```c
__int64 __fastcall CChangeApplier::SaveChangeWithChangeUnitsComplete(CChangeApplier *this)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::SaveChangeWithChangeUnitsComplete");
  }
  return (*(__int64 (__fastcall **)(CChangeApplier *))(*(_QWORD *)this + 24LL))(this);
}

```

## disassembly

```asm
0x180045000  push    rbx
0x180045002  sub     rsp, 20h
0x180045006  mov     rbx, rcx
0x180045009  mov     rcx, cs:WPP_GLOBAL_Control
0x180045010  lea     rax, WPP_GLOBAL_Control
0x180045017  cmp     rcx, rax
0x18004501a  jz      short loc_180045044
0x18004501c  test    byte ptr [rcx+1Ch], 8
0x180045020  jz      short loc_180045044
0x180045022  cmp     byte ptr [rcx+19h], 5
0x180045026  jb      short loc_180045044
0x180045028  mov     rcx, [rcx+10h]
0x18004502c  lea     r9, aCchangeapplier_107; "CChangeApplier::SaveChangeWithChangeUni"...
0x180045033  mov     edx, 2Bh ; '+'
0x180045038  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18004503f  call    WPP_SF_s
0x180045044  mov     rax, [rbx]
0x180045047  mov     rcx, rbx
0x18004504a  mov     rax, [rax+18h]
0x18004504e  add     rsp, 20h
0x180045052  pop     rbx
0x180045053  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
