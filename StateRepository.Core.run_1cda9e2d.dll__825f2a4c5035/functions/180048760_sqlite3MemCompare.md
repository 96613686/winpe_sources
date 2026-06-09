# sqlite3MemCompare

- ea: `0x180048760`
- end: `0x1800489cc`
- name: `sqlite3MemCompare`
- size: `620`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002a050`
- `0x180048060`
- `0x1800485b0`
- `0x180048670`
- `0x18007a8c0`

## callees

- `0x18000a460`
- `0x180028540`
- `0x180048760`
- `0x1800489d4`
- `0x18004b9b0`
- `0x180084768`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall sqlite3MemCompare(__int64 a1, __int64 a2, __int64 a3)
{
  __int16 v3; // r11
  __int16 v5; // bx
  char v6; // r10
  unsigned int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rax
  __int128 v13; // [rsp+30h] [rbp-39h] BYREF
  __int64 v14; // [rsp+40h] [rbp-29h]
  __int64 v15; // [rsp+48h] [rbp-21h]
  __int128 v16; // [rsp+50h] [rbp-19h]
  __int64 v17; // [rsp+60h] [rbp-9h]
  __int128 v18; // [rsp+68h] [rbp-1h] BYREF
  __int64 v19; // [rsp+78h] [rbp+Fh]
  __int64 v20; // [rsp+80h] [rbp+17h]
  __int128 v21; // [rsp+88h] [rbp+1Fh]
  __int64 v22; // [rsp+98h] [rbp+2Fh]

  v3 = *(_WORD *)(a2 + 20);
  v5 = *(_WORD *)(a1 + 20);
  v6 = v5 | v3;
  if ( (((unsigned __int8)v5 | (unsigned __int8)v3) & 1) != 0 )
    return (v3 & 1) - (v5 & 1u);
  if ( (v6 & 0x2C) == 0 )
  {
    if ( (v6 & 2) != 0 )
    {
      if ( (v5 & 2) == 0 )
        return 1;
      if ( (v3 & 2) == 0 )
        return 0xFFFFFFFFLL;
      if ( a3 )
      {
        if ( *(_BYTE *)(a1 + 22) == *(_BYTE *)(a3 + 8) )
        {
          return (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(a3 + 24))(
                   *(_QWORD *)(a3 + 16),
                   *(unsigned int *)(a1 + 16),
                   *(_QWORD *)(a1 + 8),
                   *(unsigned int *)(a2 + 16),
                   *(_QWORD *)(a2 + 8));
        }
        else
        {
          v17 = 0;
          v22 = 0;
          v10 = *(_QWORD *)(a1 + 24);
          v14 = 0x100000000LL;
          v19 = 0x100000000LL;
          v16 = 0;
          v15 = v10;
          v21 = 0;
          v20 = v10;
          v13 = 0;
          LODWORD(v16) = 0;
          v18 = 0;
          LODWORD(v21) = 0;
          sqlite3VdbeMemShallowCopy(&v13, a1, 0x4000);
          sqlite3VdbeMemShallowCopy(&v18, a2, 0x4000);
          v11 = sqlite3ValueText(&v13, *(unsigned __int8 *)(a3 + 8));
          v12 = sqlite3ValueText(&v18, *(unsigned __int8 *)(a3 + 8));
          if ( v11 && v12 )
            v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, __int64))(a3 + 24))(
                   *(_QWORD *)(a3 + 16),
                   (unsigned int)v14,
                   v11,
                   (unsigned int)v19,
                   v12);
          else
            v9 = 0;
          if ( (_DWORD)v16 )
            vdbeMemClear(&v13);
          if ( (_DWORD)v21 )
            vdbeMemClear(&v18);
        }
        return v9;
      }
    }
    return sqlite3BlobCompare();
  }
  if ( ((unsigned __int8)v5 & (unsigned __int8)v3 & 0x24) != 0 )
  {
    if ( *(_QWORD *)a1 < *(_QWORD *)a2 )
      return 0xFFFFFFFFLL;
    return *(_QWORD *)a1 > *(_QWORD *)a2;
  }
  if ( ((unsigned __int8)v5 & (unsigned __int8)v3 & 8) != 0 )
  {
    if ( *(double *)a2 > *(double *)a1 )
      return 0xFFFFFFFFLL;
    return *(double *)a1 > *(double *)a2;
  }
  if ( (v5 & 0x24) == 0 )
  {
    if ( (v5 & 8) != 0 )
    {
      if ( (v3 & 0x24) == 0 )
        return 0xFFFFFFFFLL;
      return (unsigned int)-sqlite3IntFloatCompare(*(_QWORD *)a2);
    }
    return 1;
  }
  if ( (v3 & 8) == 0 )
  {
    if ( (v3 & 0x24) != 0 && *(_QWORD *)a1 >= *(_QWORD *)a2 )
      return *(_QWORD *)a1 > *(_QWORD *)a2;
    return 0xFFFFFFFFLL;
  }
  return sqlite3IntFloatCompare(*(_QWORD *)a1);
}

```

## disassembly

```asm
0x180048760  push    rbp
0x180048762  push    rbx
0x180048763  push    rsi
0x180048764  push    rdi
0x180048765  push    r14
0x180048767  lea     rbp, [rsp-37h]
0x18004876c  sub     rsp, 0A0h
0x180048773  movzx   r11d, word ptr [rdx+14h]
0x180048778  mov     r14, r8
0x18004877b  movzx   ebx, word ptr [rcx+14h]
0x18004877f  mov     r10d, r11d
0x180048782  or      r10d, ebx
0x180048785  mov     rsi, rdx
0x180048788  mov     rdi, rcx
0x18004878b  test    r10b, 1
0x18004878f  jnz     loc_180048873
0x180048795  test    r10b, 2Ch
0x180048799  jz      short loc_1800487E5
0x18004879b  movzx   ecx, r11w
0x18004879f  movzx   eax, bx
0x1800487a2  and     ecx, eax
0x1800487a4  test    cl, 24h
0x1800487a7  jnz     short loc_180048809
0x1800487a9  test    cl, 8
0x1800487ac  jnz     loc_1800488AE
0x1800487b2  test    bl, 24h
0x1800487b5  jz      loc_1800488E0
0x1800487bb  test    r11b, 8
0x1800487bf  jnz     loc_1800488CF
0x1800487c5  test    r11b, 24h
0x1800487c9  jz      short loc_1800487F6
0x1800487cb  mov     rax, [rdx]
0x1800487ce  cmp     [rdi], rax
0x1800487d1  jl      short loc_1800487F6
0x1800487d3  jg      short loc_180048813
0x1800487d5  xor     eax, eax
0x1800487d7  add     rsp, 0A0h
0x1800487de  pop     r14
0x1800487e0  pop     rdi
0x1800487e1  pop     rsi
0x1800487e2  pop     rbx
0x1800487e3  pop     rbp
0x1800487e4  retn
0x1800487e5  test    r10b, 2
0x1800487e9  jz      short loc_180048826
0x1800487eb  test    bl, 2
0x1800487ee  jz      short loc_180048813
0x1800487f0  test    r11b, 2
0x1800487f4  jnz     short loc_18004882D
0x1800487f6  mov     eax, 0FFFFFFFFh
0x1800487fb  add     rsp, 0A0h
0x180048802  pop     r14
0x180048804  pop     rdi
0x180048805  pop     rsi
0x180048806  pop     rbx
0x180048807  pop     rbp
0x180048808  retn
0x180048809  mov     rax, [rdx]
0x18004880c  cmp     [rdi], rax
0x18004880f  jl      short loc_1800487F6
0x180048811  jle     short loc_1800487D5
0x180048813  mov     eax, 1
0x180048818  add     rsp, 0A0h
0x18004881f  pop     r14
0x180048821  pop     rdi
0x180048822  pop     rsi
0x180048823  pop     rbx
0x180048824  pop     rbp
0x180048825  retn
0x180048826  call    sqlite3BlobCompare
0x18004882b  jmp     short loc_1800487D7
0x18004882d  test    r14, r14
0x180048830  jz      short loc_180048826
0x180048832  movzx   eax, byte ptr [r8+8]
0x180048837  cmp     [rcx+16h], al
0x18004883a  jnz     loc_180048906
0x180048840  mov     rcx, [rdx+8]
0x180048844  mov     r9d, [rdx+10h]
0x180048848  mov     r8, [rdi+8]
0x18004884c  mov     edx, [rdi+10h]
0x18004884f  mov     rax, [r14+18h]
0x180048853  mov     [rsp+0C0h+var_A0], rcx
0x180048858  mov     rcx, [r14+10h]
0x18004885c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048861  mov     ebx, eax
0x180048863  mov     eax, ebx
0x180048865  add     rsp, 0A0h
0x18004886c  pop     r14
0x18004886e  pop     rdi
0x18004886f  pop     rsi
0x180048870  pop     rbx
0x180048871  pop     rbp
0x180048872  retn
0x180048873  and     r11d, 1
0x180048877  and     ebx, 1
0x18004887a  sub     r11d, ebx
0x18004887d  mov     eax, r11d
0x180048880  add     rsp, 0A0h
0x180048887  pop     r14
0x180048889  pop     rdi
0x18004888a  pop     rsi
0x18004888b  pop     rbx
0x18004888c  pop     rbp
0x18004888d  retn
0x18004888e  cmp     dword ptr [rbp+57h+var_70], 0
0x180048892  jz      short loc_18004889D
0x180048894  lea     rcx, [rbp+57h+var_90]
0x180048898  call    vdbeMemClear
0x18004889d  cmp     dword ptr [rbp+57h+var_38], 0
0x1800488a1  jz      short loc_180048863
0x1800488a3  lea     rcx, [rbp+57h+var_58]
0x1800488a7  call    vdbeMemClear
0x1800488ac  jmp     short loc_180048863
0x1800488ae  movsd   xmm0, qword ptr [rdx]
0x1800488b2  movsd   xmm1, qword ptr [rdi]
0x1800488b6  comisd  xmm0, xmm1
0x1800488ba  ja      loc_1800487F6
0x1800488c0  comisd  xmm1, xmm0
0x1800488c4  ja      loc_180048813
0x1800488ca  jmp     loc_1800487D5
0x1800488cf  movsd   xmm1, qword ptr [rdx]
0x1800488d3  mov     rcx, [rdi]
0x1800488d6  call    sqlite3IntFloatCompare
0x1800488db  jmp     loc_1800487D7
0x1800488e0  test    bl, 8
0x1800488e3  jz      loc_180048813
0x1800488e9  test    r11b, 24h
0x1800488ed  jz      loc_1800487F6
0x1800488f3  movsd   xmm1, qword ptr [rdi]
0x1800488f7  mov     rcx, [rdx]
0x1800488fa  call    sqlite3IntFloatCompare
0x1800488ff  neg     eax
0x180048901  jmp     loc_1800487D7
0x180048906  xorps   xmm0, xmm0
0x180048909  xor     eax, eax
0x18004890b  xorps   xmm1, xmm1
0x18004890e  mov     [rbp+57h+var_60], rax
0x180048912  mov     ecx, 1
0x180048917  mov     [rbp+57h+var_28], rax
0x18004891b  mov     rax, [rdi+18h]
0x18004891f  mov     r8d, 4000h
0x180048925  movups  [rbp+57h+var_80], xmm0
0x180048929  mov     word ptr [rbp+57h+var_80+4], cx
0x18004892d  mov     rdx, rdi
0x180048930  movups  [rbp+57h+var_48], xmm1
0x180048934  mov     word ptr [rbp+57h+var_48+4], cx
0x180048938  lea     rcx, [rbp+57h+var_90]
0x18004893c  movups  [rbp+57h+var_70], xmm0
0x180048940  mov     qword ptr [rbp+57h+var_80+8], rax
0x180048944  movups  [rbp+57h+var_38], xmm1
0x180048948  mov     qword ptr [rbp+57h+var_48+8], rax
0x18004894c  movups  [rbp+57h+var_90], xmm0
0x180048950  mov     dword ptr [rbp+57h+var_70], 0
0x180048957  movups  [rbp+57h+var_58], xmm1
0x18004895b  mov     dword ptr [rbp+57h+var_38], 0
0x180048962  call    sqlite3VdbeMemShallowCopy
0x180048967  mov     r8d, 4000h
0x18004896d  lea     rcx, [rbp+57h+var_58]
0x180048971  mov     rdx, rsi
0x180048974  call    sqlite3VdbeMemShallowCopy
0x180048979  movzx   edx, byte ptr [r14+8]
0x18004897e  lea     rcx, [rbp+57h+var_90]
0x180048982  call    sqlite3ValueText
0x180048987  movzx   edx, byte ptr [r14+8]
0x18004898c  lea     rcx, [rbp+57h+var_58]
0x180048990  mov     rbx, rax
0x180048993  call    sqlite3ValueText
0x180048998  test    rbx, rbx
0x18004899b  jz      short loc_1800489C5
0x18004899d  test    rax, rax
0x1800489a0  jz      short loc_1800489C5
0x1800489a2  mov     r9d, dword ptr [rbp+57h+var_48]
0x1800489a6  mov     r8, rbx
0x1800489a9  mov     edx, dword ptr [rbp+57h+var_80]
0x1800489ac  mov     rcx, [r14+10h]
0x1800489b0  mov     [rsp+0C0h+var_A0], rax
0x1800489b5  mov     rax, [r14+18h]
0x1800489b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489be  mov     ebx, eax
0x1800489c0  jmp     loc_18004888E
0x1800489c5  xor     ebx, ebx
0x1800489c7  jmp     loc_18004888E
```
