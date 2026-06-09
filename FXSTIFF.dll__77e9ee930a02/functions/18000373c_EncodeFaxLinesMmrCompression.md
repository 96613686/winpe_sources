# EncodeFaxLinesMmrCompression

- ea: `0x18000373c`
- end: `0x180003b30`
- name: `EncodeFaxLinesMmrCompression`
- size: `1012`
- prototype: `__int64 __fastcall(__int64, char *, unsigned int, unsigned int, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004540`
- `0x180008390`

## callees

- `0x18000373c`
- `0x180004050`
- `0x180004110`
- `0x18000dfa0`
- `0x18000e104`
- `0x180018992`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EncodeFaxLinesMmrCompression(__int64 a1, char *a2, unsigned int a3, unsigned int a4, int *a5)
{
  char *v5; // r13
  unsigned int v9; // r14d
  unsigned int WhiteRun; // edi
  unsigned int v11; // ebp
  int v12; // edx
  int BlackRun; // eax
  unsigned int v14; // ecx
  int v15; // r8d
  unsigned int v16; // ecx
  unsigned int v17; // edx
  int v18; // eax
  char v19; // cl
  unsigned int v20; // r12d
  int v21; // eax
  unsigned int v22; // ecx
  int v23; // edx
  __int64 *v24; // r13
  __int64 *v25; // r8
  __int64 v26; // r12
  char v27; // bp
  int v28; // eax
  int v29; // eax
  int v30; // r13d
  __int64 v31; // rdx
  int v32; // eax
  unsigned int v33; // edi
  __int64 result; // rax
  int v35; // edx
  char *v36; // [rsp+20h] [rbp-48h]
  unsigned int v37; // [rsp+70h] [rbp+8h]

  v5 = *(char **)(a1 + 32);
  v36 = v5;
  v37 = 0;
LABEL_2:
  if ( *(_QWORD *)(a1 + 1592) < *(_QWORD *)(a1 + 1608) || (unsigned int)GrowCompBitsBuffer(a1) )
  {
    v9 = 0;
    if ( *a2 >= 0 )
      WhiteRun = FindWhiteRun(a2, 0, a3);
    else
      WhiteRun = 0;
    if ( *v5 >= 0 )
      v11 = FindWhiteRun(v5, 0, a3);
    else
      v11 = 0;
    while ( *(_QWORD *)(a1 + 1592) < *(_QWORD *)(a1 + 1608) || (unsigned int)GrowCompBitsBuffer(a1) )
    {
      if ( (int)v11 < (int)a3 )
      {
        if ( (((unsigned __int8)v5[(__int64)(int)v11 >> 3] >> (~(_BYTE)v11 & 7)) & 1) != 0 )
          BlackRun = FindBlackRun(v5, v11, a3);
        else
          BlackRun = FindWhiteRun(v5, v11, a3);
        v12 = BlackRun + v11;
      }
      else
      {
        v12 = a3;
      }
      if ( v12 >= (int)WhiteRun )
      {
        v16 = WhiteRun - v11;
        if ( WhiteRun - v11 + 3 > 6 )
        {
          if ( (int)WhiteRun < (int)a3 )
          {
            if ( (((unsigned __int8)a2[(__int64)(int)WhiteRun >> 3] >> (~(_BYTE)WhiteRun & 7)) & 1) != 0 )
              v21 = FindBlackRun(a2, WhiteRun, a3);
            else
              v21 = FindWhiteRun(a2, WhiteRun, a3);
            v20 = v21 + WhiteRun;
          }
          else
          {
            v20 = a3;
          }
          v22 = *(_DWORD *)(a1 + 1584) - 3;
          *(_DWORD *)(a1 + 1580) |= 1 << (*(_BYTE *)(a1 + 1584) - 3);
          v23 = *(_DWORD *)(a1 + 1580);
          *(_DWORD *)(a1 + 1584) = v22;
          if ( v22 <= 0x10 )
          {
            *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = HIBYTE(v23);
            *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = *(_BYTE *)(a1 + 1582);
            *(_DWORD *)(a1 + 1580) <<= 16;
            *(_DWORD *)(a1 + 1584) += 16;
          }
          if ( WhiteRun && (((unsigned __int8)a2[(__int64)(int)v9 >> 3] >> (~(_BYTE)v9 & 7)) & 1) != 0 )
          {
            v24 = qword_18001B050;
            v25 = qword_18001B390;
          }
          else
          {
            v24 = qword_18001B390;
            v25 = qword_18001B050;
          }
          OutputRun(a1, WhiteRun - v9, v25);
          OutputRun(a1, v20 - WhiteRun, v24);
          v5 = v36;
          v9 = v20;
        }
        else
        {
          v17 = *(_DWORD *)(a1 + 1584) - *((unsigned __int16 *)&qword_18001B530[1] + 2 * (int)v16 + 2);
          v18 = *((unsigned __int16 *)&qword_18001B530[1] + 2 * (int)v16 + 3);
          v19 = *(_BYTE *)(a1 + 1584) - *((_WORD *)&qword_18001B530[1] + 2 * (int)v16 + 2);
          *(_DWORD *)(a1 + 1584) = v17;
          *(_DWORD *)(a1 + 1580) |= v18 << v19;
          if ( v17 <= 0x10 )
          {
            *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = HIBYTE(*(_DWORD *)(a1 + 1580));
            *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = *(_BYTE *)(a1 + 1582);
            *(_DWORD *)(a1 + 1580) <<= 16;
            *(_DWORD *)(a1 + 1584) += 16;
          }
          v9 = WhiteRun;
        }
      }
      else
      {
        v14 = *(_DWORD *)(a1 + 1584) - 4;
        *(_DWORD *)(a1 + 1580) |= 1 << (*(_BYTE *)(a1 + 1584) - 4);
        v15 = *(_DWORD *)(a1 + 1580);
        *(_DWORD *)(a1 + 1584) = v14;
        if ( v14 <= 0x10 )
        {
          *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = HIBYTE(v15);
          *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = *(_BYTE *)(a1 + 1582);
          *(_DWORD *)(a1 + 1580) <<= 16;
          *(_DWORD *)(a1 + 1584) += 16;
        }
        v9 = v12;
      }
      if ( (int)v9 >= (int)a3 )
      {
        v33 = v37 + 1;
        v37 = v33;
        if ( v33 < a4 )
        {
          v5 = a2;
          v36 = a2;
          a2 += *(unsigned int *)(a1 + 1692);
          goto LABEL_2;
        }
        memcpy_0(*(void **)(a1 + 32), a2, (int)a3 / 8);
        *(_DWORD *)(a1 + 848) += v33;
        result = 1;
        v35 = *(_DWORD *)(a1 + 1592) - *(_DWORD *)(a1 + 1600);
        *a5 = v35;
        *(_DWORD *)(a1 + 856) = v35;
        return result;
      }
      v26 = (__int64)(int)v9 >> 3;
      v27 = ~(_BYTE)v9 & 7;
      if ( (((unsigned __int8)a2[v26] >> v27) & 1) != 0 )
        v28 = FindBlackRun(a2, v9, a3);
      else
        v28 = FindWhiteRun(a2, v9, a3);
      WhiteRun = v28 + v9;
      if ( (((unsigned __int8)a2[v26] >> v27) & 1) != 0 )
        v29 = FindWhiteRun(v5, v9, a3);
      else
        v29 = FindBlackRun(v5, v9, a3);
      v30 = v29 + v9;
      v31 = v29 + v9;
      if ( (((unsigned __int8)a2[v26] >> v27) & 1) != 0 )
        v32 = FindBlackRun(v36, v31, a3);
      else
        v32 = FindWhiteRun(v36, v31, a3);
      v11 = v32 + v30;
      v5 = v36;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000373c  mov     [rsp+arg_8], rbx
0x180003741  mov     [rsp+arg_18], r9d
0x180003746  push    rbp
0x180003747  push    rsi
0x180003748  push    rdi
0x180003749  push    r12
0x18000374b  push    r13
0x18000374d  push    r14
0x18000374f  push    r15
0x180003751  sub     rsp, 30h
0x180003755  mov     r13, [rcx+20h]
0x180003759  lea     r12, qword_18001B530
0x180003760  mov     [rsp+68h+var_48], r13
0x180003765  mov     esi, r8d
0x180003768  mov     r15, rdx
0x18000376b  mov     [rsp+68h+arg_0], 0
0x180003773  mov     rbx, rcx
0x180003776  mov     rax, [rbx+648h]
0x18000377d  cmp     [rbx+638h], rax
0x180003784  jb      short loc_180003796
0x180003786  mov     rcx, rbx
0x180003789  call    GrowCompBitsBuffer
0x18000378e  test    eax, eax
0x180003790  jz      loc_180003AD5
0x180003796  xor     r14d, r14d
0x180003799  cmp     [r15], r14b
0x18000379c  jge     short loc_1800037A2
0x18000379e  xor     edi, edi
0x1800037a0  jmp     short loc_1800037B1
0x1800037a2  mov     r8d, esi
0x1800037a5  xor     edx, edx
0x1800037a7  mov     rcx, r15
0x1800037aa  call    FindWhiteRun
0x1800037af  mov     edi, eax
0x1800037b1  cmp     [r13+0], r14b
0x1800037b5  jge     short loc_1800037BB
0x1800037b7  xor     ebp, ebp
0x1800037b9  jmp     short loc_1800037CA
0x1800037bb  mov     r8d, esi
0x1800037be  xor     edx, edx
0x1800037c0  mov     rcx, r13
0x1800037c3  call    FindWhiteRun
0x1800037c8  mov     ebp, eax
0x1800037ca  mov     rcx, [rbx+648h]
0x1800037d1  cmp     [rbx+638h], rcx
0x1800037d8  jb      short loc_1800037EA
0x1800037da  mov     rcx, rbx
0x1800037dd  call    GrowCompBitsBuffer
0x1800037e2  test    eax, eax
0x1800037e4  jz      loc_180003AD5
0x1800037ea  cmp     ebp, esi
0x1800037ec  jl      short loc_1800037F2
0x1800037ee  mov     edx, esi
0x1800037f0  jmp     short loc_180003822
0x1800037f2  mov     cl, bpl
0x1800037f5  movsxd  rax, ebp
0x1800037f8  sar     rax, 3
0x1800037fc  not     cl
0x1800037fe  and     cl, 7
0x180003801  mov     r8d, esi
0x180003804  mov     edx, ebp
0x180003806  mov     al, [rax+r13]
0x18000380a  shr     al, cl
0x18000380c  mov     rcx, r13
0x18000380f  test    al, 1
0x180003811  jz      short loc_18000381A
0x180003813  call    FindBlackRun
0x180003818  jmp     short loc_18000381F
0x18000381a  call    FindWhiteRun
0x18000381f  lea     edx, [rax+rbp]
0x180003822  cmp     edx, edi
0x180003824  jge     short loc_18000388F
0x180003826  mov     ecx, [rbx+630h]
0x18000382c  mov     eax, 1
0x180003831  add     ecx, 0FFFFFFFCh
0x180003834  shl     eax, cl
0x180003836  or      [rbx+62Ch], eax
0x18000383c  mov     r8d, [rbx+62Ch]
0x180003843  mov     [rbx+630h], ecx
0x180003849  cmp     ecx, 10h
0x18000384c  ja      short loc_180003887
0x18000384e  mov     rax, [rbx+638h]
0x180003855  shr     r8d, 18h
0x180003859  mov     [rax], r8b
0x18000385c  inc     qword ptr [rbx+638h]
0x180003863  mov     rcx, [rbx+638h]
0x18000386a  mov     al, [rbx+62Eh]
0x180003870  mov     [rcx], al
0x180003872  inc     qword ptr [rbx+638h]
0x180003879  shl     dword ptr [rbx+62Ch], 10h
0x180003880  add     dword ptr [rbx+630h], 10h
0x180003887  mov     r14d, edx
0x18000388a  jmp     loc_180003A0D
0x18000388f  mov     ecx, edi
0x180003891  sub     ecx, ebp
0x180003893  lea     eax, [rcx+3]
0x180003896  cmp     eax, 6
0x180003899  ja      short loc_18000390C
0x18000389b  mov     edx, [rbx+630h]
0x1800038a1  movsxd  rcx, ecx
0x1800038a4  movzx   eax, word ptr [r12+rcx*4+0Ch]
0x1800038aa  sub     edx, eax
0x1800038ac  movzx   eax, word ptr [r12+rcx*4+0Eh]
0x1800038b2  mov     ecx, edx
0x1800038b4  mov     [rbx+630h], edx
0x1800038ba  shl     eax, cl
0x1800038bc  or      [rbx+62Ch], eax
0x1800038c2  mov     ecx, [rbx+62Ch]
0x1800038c8  cmp     edx, 10h
0x1800038cb  ja      short loc_180003904
0x1800038cd  mov     rax, [rbx+638h]
0x1800038d4  shr     ecx, 18h
0x1800038d7  mov     [rax], cl
0x1800038d9  inc     qword ptr [rbx+638h]
0x1800038e0  mov     rcx, [rbx+638h]
0x1800038e7  mov     al, [rbx+62Eh]
0x1800038ed  mov     [rcx], al
0x1800038ef  inc     qword ptr [rbx+638h]
0x1800038f6  shl     dword ptr [rbx+62Ch], 10h
0x1800038fd  add     dword ptr [rbx+630h], 10h
0x180003904  mov     r14d, edi
0x180003907  jmp     loc_180003A0D
0x18000390c  cmp     edi, esi
0x18000390e  jl      short loc_180003915
0x180003910  mov     r12d, esi
0x180003913  jmp     short loc_180003946
0x180003915  mov     cl, dil
0x180003918  movsxd  rax, edi
0x18000391b  sar     rax, 3
0x18000391f  not     cl
0x180003921  and     cl, 7
0x180003924  mov     r8d, esi
0x180003927  mov     edx, edi
0x180003929  mov     al, [rax+r15]
0x18000392d  shr     al, cl
0x18000392f  mov     rcx, r15
0x180003932  test    al, 1
0x180003934  jz      short loc_18000393D
0x180003936  call    FindBlackRun
0x18000393b  jmp     short loc_180003942
0x18000393d  call    FindWhiteRun
0x180003942  lea     r12d, [rax+rdi]
0x180003946  mov     ecx, [rbx+630h]
0x18000394c  mov     eax, 1
0x180003951  add     ecx, 0FFFFFFFDh
0x180003954  shl     eax, cl
0x180003956  or      [rbx+62Ch], eax
0x18000395c  mov     edx, [rbx+62Ch]
0x180003962  mov     [rbx+630h], ecx
0x180003968  cmp     ecx, 10h
0x18000396b  ja      short loc_1800039A4
0x18000396d  mov     rax, [rbx+638h]
0x180003974  shr     edx, 18h
0x180003977  mov     [rax], dl
0x180003979  inc     qword ptr [rbx+638h]
0x180003980  mov     rcx, [rbx+638h]
0x180003987  mov     al, [rbx+62Eh]
0x18000398d  mov     [rcx], al
0x18000398f  inc     qword ptr [rbx+638h]
0x180003996  shl     dword ptr [rbx+62Ch], 10h
0x18000399d  add     dword ptr [rbx+630h], 10h
0x1800039a4  test    edi, edi
0x1800039a6  jz      short loc_1800039D1
0x1800039a8  movsxd  rax, r14d
0x1800039ab  mov     cl, r14b
0x1800039ae  sar     rax, 3
0x1800039b2  not     cl
0x1800039b4  and     cl, 7
0x1800039b7  mov     al, [rax+r15]
0x1800039bb  shr     al, cl
0x1800039bd  test    al, 1
0x1800039bf  jz      short loc_1800039D1
0x1800039c1  lea     r13, qword_18001B050
0x1800039c8  lea     r8, qword_18001B390
0x1800039cf  jmp     short loc_1800039DF
0x1800039d1  lea     r13, qword_18001B390
0x1800039d8  lea     r8, qword_18001B050
0x1800039df  mov     ebp, r12d
0x1800039e2  mov     rcx, rbx
0x1800039e5  sub     ebp, edi
0x1800039e7  sub     edi, r14d
0x1800039ea  mov     edx, edi
0x1800039ec  call    OutputRun
0x1800039f1  mov     r8, r13
0x1800039f4  mov     edx, ebp
0x1800039f6  mov     rcx, rbx
0x1800039f9  call    OutputRun
0x1800039fe  mov     r13, [rsp+68h+var_48]
0x180003a03  mov     r14d, r12d
0x180003a06  lea     r12, qword_18001B530
0x180003a0d  cmp     r14d, esi
0x180003a10  jge     loc_180003AAC
0x180003a16  movsxd  r12, r14d
0x180003a19  mov     bpl, r14b
0x180003a1c  sar     r12, 3
0x180003a20  not     bpl
0x180003a23  and     bpl, 7
0x180003a27  mov     r8d, esi
0x180003a2a  mov     cl, bpl
0x180003a2d  mov     edx, r14d
0x180003a30  mov     al, [r12+r15]
0x180003a34  shr     al, cl
0x180003a36  mov     rcx, r15
0x180003a39  test    al, 1
0x180003a3b  jz      short loc_180003A44
0x180003a3d  call    FindBlackRun
0x180003a42  jmp     short loc_180003A49
0x180003a44  call    FindWhiteRun
0x180003a49  lea     edi, [rax+r14]
0x180003a4d  mov     cl, bpl
0x180003a50  mov     al, [r12+r15]
0x180003a54  mov     r8d, esi
0x180003a57  shr     al, cl
0x180003a59  mov     edx, r14d
0x180003a5c  mov     rcx, r13
0x180003a5f  test    al, 1
0x180003a61  jnz     short loc_180003A6A
0x180003a63  call    FindBlackRun
0x180003a68  jmp     short loc_180003A6F
0x180003a6a  call    FindWhiteRun
0x180003a6f  lea     r13d, [rax+r14]
0x180003a73  mov     cl, bpl
0x180003a76  mov     al, [r12+r15]
0x180003a7a  mov     r8d, esi
0x180003a7d  shr     al, cl
0x180003a7f  mov     edx, r13d
0x180003a82  mov     rcx, [rsp+68h+var_48]
0x180003a87  test    al, 1
0x180003a89  jz      short loc_180003A92
0x180003a8b  call    FindBlackRun
0x180003a90  jmp     short loc_180003A97
0x180003a92  call    FindWhiteRun
0x180003a97  lea     ebp, [rax+r13]
0x180003a9b  mov     r13, [rsp+68h+var_48]
0x180003aa0  lea     r12, qword_18001B530
0x180003aa7  jmp     loc_1800037CA
0x180003aac  mov     edi, [rsp+68h+arg_0]
0x180003ab0  inc     edi
0x180003ab2  mov     [rsp+68h+arg_0], edi
0x180003ab6  cmp     edi, [rsp+68h+arg_18]
0x180003abd  jnb     short loc_180003AD9
0x180003abf  mov     eax, [rbx+69Ch]
0x180003ac5  mov     r13, r15
0x180003ac8  mov     [rsp+68h+var_48], r15
0x180003acd  add     r15, rax
0x180003ad0  jmp     loc_180003776
0x180003ad5  xor     eax, eax
0x180003ad7  jmp     short loc_180003B1A
0x180003ad9  mov     rcx, [rbx+20h]; void *
0x180003add  mov     eax, esi
0x180003adf  cdq
0x180003ae0  and     edx, 7
0x180003ae3  add     eax, edx
0x180003ae5  mov     rdx, r15; Src
0x180003ae8  sar     eax, 3
0x180003aeb  movsxd  r8, eax; Size
0x180003aee  call    memcpy_0
0x180003af3  add     [rbx+350h], edi
0x180003af9  mov     eax, 1
0x180003afe  mov     edx, [rbx+638h]
0x180003b04  sub     edx, [rbx+640h]
0x180003b0a  mov     rcx, [rsp+68h+arg_20]
0x180003b12  mov     [rcx], edx
0x180003b14  mov     [rbx+358h], edx
0x180003b1a  mov     rbx, [rsp+68h+arg_8]
0x180003b1f  add     rsp, 30h
0x180003b23  pop     r15
0x180003b25  pop     r14
0x180003b27  pop     r13
0x180003b29  pop     r12
0x180003b2b  pop     rdi
0x180003b2c  pop     rsi
0x180003b2d  pop     rbp
0x180003b2e  retn
```
