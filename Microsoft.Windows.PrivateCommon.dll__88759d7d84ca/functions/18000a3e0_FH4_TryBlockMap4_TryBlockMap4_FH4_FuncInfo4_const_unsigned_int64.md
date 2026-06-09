# FH4::TryBlockMap4::TryBlockMap4(FH4::FuncInfo4 const *,unsigned __int64)

- ea: `0x18000a3e0`
- end: `0x18000a4c4`
- name: `??0TryBlockMap4@FH4@@QEAA@PEBUFuncInfo4@1@_K@Z`
- size: `228`
- prototype: `FH4::TryBlockMap4 *__fastcall(FH4::TryBlockMap4 *this, const struct FH4::FuncInfo4 *, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800095ac`
- `0x180009af8`
- `0x18000a060`

## callees

- `0x18000a3e0`

## pseudocode

```c
FH4::TryBlockMap4 *__fastcall FH4::TryBlockMap4::TryBlockMap4(
        FH4::TryBlockMap4 *this,
        const struct FH4::FuncInfo4 *a2,
        __int64 a3)
{
  _BYTE *v4; // rdx
  __int64 v5; // rcx
  _BYTE *v6; // rdx
  int v7; // eax
  __int64 v8; // rcx
  _BYTE *v9; // rdx
  int v10; // eax
  __int64 v11; // rcx
  _BYTE *v12; // rdx
  int v13; // eax
  __int64 v14; // rcx
  _DWORD *v15; // rdx

  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  if ( *((_DWORD *)a2 + 3) )
  {
    v4 = (_BYTE *)(a3 + *((int *)a2 + 3));
    *((_QWORD *)this + 1) = v4;
    v5 = *v4 & 0xF;
    v6 = &v4[-*((char *)&FH4::s_negLengthTab + v5)];
    v7 = *((_DWORD *)v6 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v5);
    *((_QWORD *)this + 1) = v6;
    *(_DWORD *)this = v7;
    *((_QWORD *)this + 2) = v6;
    v8 = *v6 & 0xF;
    v9 = &v6[-*((char *)&FH4::s_negLengthTab + v8)];
    v10 = *((_DWORD *)v9 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v8);
    *((_QWORD *)this + 1) = v9;
    *((_DWORD *)this + 6) = v10;
    v11 = *v9 & 0xF;
    v12 = &v9[-*((char *)&FH4::s_negLengthTab + v11)];
    v13 = *((_DWORD *)v12 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v11);
    *((_QWORD *)this + 1) = v12;
    *((_DWORD *)this + 7) = v13;
    v14 = *v12 & 0xF;
    v15 = &v12[-*((char *)&FH4::s_negLengthTab + v14)];
    *((_DWORD *)this + 8) = *(v15 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v14);
    *((_QWORD *)this + 1) = v15;
    LODWORD(v14) = *v15;
    *((_QWORD *)this + 1) = v15 + 1;
    *((_DWORD *)this + 9) = v14;
  }
  else
  {
    *(_DWORD *)this = 0;
  }
  return this;
}

```

## disassembly

```asm
0x18000a3e0  xor     eax, eax
0x18000a3e2  xorps   xmm0, xmm0
0x18000a3e5  mov     [rcx+8], rax
0x18000a3e9  mov     r9, rcx
0x18000a3ec  mov     [rcx+10h], rax
0x18000a3f0  movups  xmmword ptr [rcx+18h], xmm0
0x18000a3f4  cmp     [rdx+0Ch], eax
0x18000a3f7  jz      loc_18000A4BE
0x18000a3fd  movsxd  rdx, dword ptr [rdx+0Ch]
0x18000a401  add     rdx, r8
0x18000a404  lea     r8, cs:180000000h
0x18000a40b  mov     [rcx+8], rdx
0x18000a40f  movzx   ecx, byte ptr [rdx]
0x18000a412  and     ecx, 0Fh
0x18000a415  movsx   rax, byte ptr [rcx+r8+0D5E8h]
0x18000a41e  mov     cl, [rcx+r8+0D5F8h]
0x18000a426  sub     rdx, rax
0x18000a429  mov     eax, [rdx-4]
0x18000a42c  shr     eax, cl
0x18000a42e  mov     [r9+8], rdx
0x18000a432  mov     [r9], eax
0x18000a435  mov     [r9+10h], rdx
0x18000a439  movzx   ecx, byte ptr [rdx]
0x18000a43c  and     ecx, 0Fh
0x18000a43f  movsx   rax, byte ptr [rcx+r8+0D5E8h]
0x18000a448  mov     cl, [rcx+r8+0D5F8h]
0x18000a450  sub     rdx, rax
0x18000a453  mov     eax, [rdx-4]
0x18000a456  shr     eax, cl
0x18000a458  mov     [r9+8], rdx
0x18000a45c  mov     [r9+18h], eax
0x18000a460  movzx   ecx, byte ptr [rdx]
0x18000a463  and     ecx, 0Fh
0x18000a466  movsx   rax, byte ptr [rcx+r8+0D5E8h]
0x18000a46f  mov     cl, [rcx+r8+0D5F8h]
0x18000a477  sub     rdx, rax
0x18000a47a  mov     eax, [rdx-4]
0x18000a47d  shr     eax, cl
0x18000a47f  mov     [r9+8], rdx
0x18000a483  mov     [r9+1Ch], eax
0x18000a487  movzx   ecx, byte ptr [rdx]
0x18000a48a  and     ecx, 0Fh
0x18000a48d  movsx   rax, byte ptr [rcx+r8+0D5E8h]
0x18000a496  mov     cl, [rcx+r8+0D5F8h]
0x18000a49e  sub     rdx, rax
0x18000a4a1  mov     eax, [rdx-4]
0x18000a4a4  shr     eax, cl
0x18000a4a6  mov     [r9+20h], eax
0x18000a4aa  lea     rax, [rdx+4]
0x18000a4ae  mov     [r9+8], rdx
0x18000a4b2  mov     ecx, [rdx]
0x18000a4b4  mov     [r9+8], rax
0x18000a4b8  mov     [r9+24h], ecx
0x18000a4bc  jmp     short loc_18000A4C0
0x18000a4be  mov     [rcx], eax
0x18000a4c0  mov     rax, r9
0x18000a4c3  retn
```
