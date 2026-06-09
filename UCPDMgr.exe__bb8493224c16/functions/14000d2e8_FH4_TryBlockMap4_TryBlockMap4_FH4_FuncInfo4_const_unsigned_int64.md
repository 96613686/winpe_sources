# FH4::TryBlockMap4::TryBlockMap4(FH4::FuncInfo4 const *,unsigned __int64)

- ea: `0x14000d2e8`
- end: `0x14000d3cc`
- name: `??0TryBlockMap4@FH4@@QEAA@PEBUFuncInfo4@1@_K@Z`
- size: `228`
- prototype: `FH4::TryBlockMap4 *__fastcall(FH4::TryBlockMap4 *this, const struct FH4::FuncInfo4 *, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c4a4`
- `0x14000c9e4`
- `0x14000cf60`

## callees

- `0x14000d2e8`

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
0x14000d2e8  xor     eax, eax
0x14000d2ea  xorps   xmm0, xmm0
0x14000d2ed  mov     [rcx+8], rax
0x14000d2f1  mov     r9, rcx
0x14000d2f4  mov     [rcx+10h], rax
0x14000d2f8  movups  xmmword ptr [rcx+18h], xmm0
0x14000d2fc  cmp     [rdx+0Ch], eax
0x14000d2ff  jz      loc_14000D3C6
0x14000d305  movsxd  rdx, dword ptr [rdx+0Ch]
0x14000d309  add     rdx, r8
0x14000d30c  lea     r8, cs:140000000h
0x14000d313  mov     [rcx+8], rdx
0x14000d317  movzx   ecx, byte ptr [rdx]
0x14000d31a  and     ecx, 0Fh
0x14000d31d  movsx   rax, byte ptr [rcx+r8+115A0h]
0x14000d326  mov     cl, [rcx+r8+115B0h]
0x14000d32e  sub     rdx, rax
0x14000d331  mov     eax, [rdx-4]
0x14000d334  shr     eax, cl
0x14000d336  mov     [r9+8], rdx
0x14000d33a  mov     [r9], eax
0x14000d33d  mov     [r9+10h], rdx
0x14000d341  movzx   ecx, byte ptr [rdx]
0x14000d344  and     ecx, 0Fh
0x14000d347  movsx   rax, byte ptr [rcx+r8+115A0h]
0x14000d350  mov     cl, [rcx+r8+115B0h]
0x14000d358  sub     rdx, rax
0x14000d35b  mov     eax, [rdx-4]
0x14000d35e  shr     eax, cl
0x14000d360  mov     [r9+8], rdx
0x14000d364  mov     [r9+18h], eax
0x14000d368  movzx   ecx, byte ptr [rdx]
0x14000d36b  and     ecx, 0Fh
0x14000d36e  movsx   rax, byte ptr [rcx+r8+115A0h]
0x14000d377  mov     cl, [rcx+r8+115B0h]
0x14000d37f  sub     rdx, rax
0x14000d382  mov     eax, [rdx-4]
0x14000d385  shr     eax, cl
0x14000d387  mov     [r9+8], rdx
0x14000d38b  mov     [r9+1Ch], eax
0x14000d38f  movzx   ecx, byte ptr [rdx]
0x14000d392  and     ecx, 0Fh
0x14000d395  movsx   rax, byte ptr [rcx+r8+115A0h]
0x14000d39e  mov     cl, [rcx+r8+115B0h]
0x14000d3a6  sub     rdx, rax
0x14000d3a9  mov     eax, [rdx-4]
0x14000d3ac  shr     eax, cl
0x14000d3ae  mov     [r9+20h], eax
0x14000d3b2  lea     rax, [rdx+4]
0x14000d3b6  mov     [r9+8], rdx
0x14000d3ba  mov     ecx, [rdx]
0x14000d3bc  mov     [r9+8], rax
0x14000d3c0  mov     [r9+24h], ecx
0x14000d3c4  jmp     short loc_14000D3C8
0x14000d3c6  mov     [rcx], eax
0x14000d3c8  mov     rax, r9
0x14000d3cb  retn
```
