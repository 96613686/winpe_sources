# CommonUtil::CreateNewRefObject<ShieldProvider::PathAdder>(ShieldProvider::PathAdder * *)

- ea: `0x1400039a4`
- end: `0x140003a8d`
- name: `??$CreateNewRefObject@VPathAdder@ShieldProvider@@@CommonUtil@@YAJPEAPEAVPathAdder@ShieldProvider@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003a94`

## callees

- `0x14000162c`
- `0x1400039a4`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall CommonUtil::CreateNewRefObject<ShieldProvider::PathAdder>(_QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rdi
  void (__fastcall ***v4)(_QWORD); // rcx

  v2 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  *v2 = ShieldProvider::PathAdder::`vbtable';
  v2[4] = &IRefCounted::`vftable';
  v2[4] = &CRefCountedBaseX::`vftable';
  *(_DWORD *)((char *)v2 + *(int *)(*v2 + 4LL) - 4) = *(_DWORD *)(*v2 + 4LL) - 24;
  *((_DWORD *)v2 + 2) = 0;
  *(_QWORD *)((char *)v2 + *(int *)(*v2 + 4LL)) = &CRefCountedBase::`vftable';
  *(_DWORD *)((char *)v2 + *(int *)(*v2 + 4LL) - 4) = *(_DWORD *)(*v2 + 4LL) - 24;
  *(_QWORD *)((char *)v2 + *(int *)(*v2 + 4LL)) = &ShieldProvider::PathAdder::`vftable';
  *(_DWORD *)((char *)v2 + *(int *)(*v2 + 4LL) - 4) = 0;
  v2[2] = 0;
  v4 = (void (__fastcall ***)(_QWORD))((char *)v2 + *(int *)(*v2 + 4LL));
  (**v4)(v4);
  *a1 = v3;
  return 0;
}

```

## disassembly

```asm
0x1400039a4  mov     [rsp+arg_0], rbx
0x1400039a9  mov     [rsp+arg_18], rsi
0x1400039ae  push    rdi
0x1400039af  sub     rsp, 30h
0x1400039b3  mov     rsi, rcx
0x1400039b6  xor     ebx, ebx
0x1400039b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400039bf  lea     ecx, [rbx+28h]; unsigned __int64
0x1400039c2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400039c7  mov     rdi, rax
0x1400039ca  test    rax, rax
0x1400039cd  jz      loc_140003A68
0x1400039d3  lea     rax, ??_8PathAdder@ShieldProvider@@7B@; const ShieldProvider::PathAdder::`vbtable'
0x1400039da  mov     [rdi], rax
0x1400039dd  lea     rax, ??_7IRefCounted@@6B@; const IRefCounted::`vftable'
0x1400039e4  mov     [rdi+20h], rax
0x1400039e8  movsxd  rax, cs:dword_1400159D4
0x1400039ef  lea     rcx, ??_7CRefCountedBaseX@@6B@; const CRefCountedBaseX::`vftable'
0x1400039f6  mov     [rax+rdi], rcx
0x1400039fa  mov     rax, [rdi]
0x1400039fd  movsxd  rcx, dword ptr [rax+4]
0x140003a01  lea     edx, [rcx-18h]
0x140003a04  mov     [rcx+rdi-4], edx
0x140003a08  mov     [rdi+8], ebx
0x140003a0b  mov     rax, [rdi]
0x140003a0e  movsxd  rcx, dword ptr [rax+4]
0x140003a12  lea     rax, ??_7CRefCountedBase@@6B@; const CRefCountedBase::`vftable'
0x140003a19  mov     [rcx+rdi], rax
0x140003a1d  mov     rax, [rdi]
0x140003a20  movsxd  rcx, dword ptr [rax+4]
0x140003a24  lea     edx, [rcx-18h]
0x140003a27  mov     [rcx+rdi-4], edx
0x140003a2b  mov     rax, [rdi]
0x140003a2e  movsxd  rcx, dword ptr [rax+4]
0x140003a32  lea     rax, ??_7PathAdder@ShieldProvider@@6B@; const ShieldProvider::PathAdder::`vftable'
0x140003a39  mov     [rcx+rdi], rax
0x140003a3d  mov     rax, [rdi]
0x140003a40  movsxd  rcx, dword ptr [rax+4]
0x140003a44  mov     [rcx+rdi-4], ebx
0x140003a48  mov     [rdi+10h], rbx
0x140003a4c  mov     rax, [rdi]
0x140003a4f  movsxd  rcx, dword ptr [rax+4]
0x140003a53  add     rcx, rdi
0x140003a56  mov     rax, [rcx]
0x140003a59  mov     rax, [rax]
0x140003a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a61  mov     [rsi], rdi
0x140003a64  xor     eax, eax
0x140003a66  jmp     short loc_140003A7C
0x140003a68  mov     eax, 8007000Eh
0x140003a6d  jmp     short loc_140003A7C
0x140003a6f  xor     ebx, ebx
0x140003a71  cmp     [rsp+38h+arg_8], ebx
0x140003a75  cmovl   ebx, [rsp+38h+arg_10]
0x140003a7a  mov     eax, ebx
0x140003a7c  mov     rbx, [rsp+38h+arg_0]
0x140003a81  mov     rsi, [rsp+38h+arg_18]
0x140003a86  add     rsp, 30h
0x140003a8a  pop     rdi
0x140003a8b  retn
```
