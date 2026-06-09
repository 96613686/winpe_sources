# generateOutputSubroutine

- ea: `0x180070350`
- end: `0x1800706d3`
- name: `generateOutputSubroutine`
- size: `899`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180044538`

## callees

- `0x180005c54`
- `0x1800119e0`
- `0x180011d80`
- `0x18001c1c4`
- `0x180036688`
- `0x1800370c0`
- `0x18003abcc`
- `0x18003ff00`
- `0x1800443c8`
- `0x18004444c`
- `0x18004cfa0`
- `0x18005599c`
- `0x180070350`

## string_xrefs

- `0x180070628`: `CREATE BLOOM FILTER`

## pseudocode

```c
__int64 __fastcall generateOutputSubroutine(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        int a8)
{
  __int64 *v8; // r13
  __int64 v9; // rsi
  unsigned int *v10; // r15
  _DWORD *v12; // r12
  unsigned int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  __int64 v17; // rax
  int v18; // eax
  _QWORD *v19; // rdi
  __int64 v21; // r8
  int v22; // r9d
  int v23; // edx
  __int64 v24; // rcx
  int TempRange; // r9d
  unsigned int v26; // edi
  __int64 v27; // rcx
  unsigned int v28; // ebx
  __int64 v29; // rcx
  __int64 v30; // rdx
  unsigned int TempReg; // ebx
  int v32; // r8d
  int v33; // r8d
  int v34; // [rsp+20h] [rbp-68h]
  unsigned int v35; // [rsp+40h] [rbp-48h]
  unsigned int v36; // [rsp+90h] [rbp+8h]
  __int64 v37; // [rsp+98h] [rbp+10h]

  v37 = a2;
  v8 = (__int64 *)(a1 + 16);
  v9 = *(_QWORD *)(a1 + 16);
  v10 = (unsigned int *)(a3 + 16);
  v12 = (_DWORD *)(a3 + 12);
  v14 = *(_DWORD *)(v9 + 144);
  v15 = --*(_DWORD *)(a1 + 72);
  v35 = v14;
  v36 = v15;
  if ( a6 )
  {
    v16 = sqlite3VdbeAddOp3(v9, 17, a6, 0, 0);
    v17 = sqlite3KeyInfoRef(a7);
    v18 = sqlite3VdbeAddOp4(v9, 90, *v12, a6 + 1, *v10, v17, -8);
    sqlite3VdbeAddOp3(v9, 14, v18 + 2, v36, v18 + 2);
    *(_DWORD *)(sqlite3VdbeGetOp(v9, v16) + 8) = *(_DWORD *)(v9 + 144);
    sqlite3VdbeAddOp3(v9, 80, *v12, a6 + 1, *v10 - 1);
    sqlite3VdbeAddOp3(v9, 71, 1, a6, 0);
    a2 = v37;
    v19 = (_QWORD *)(a1 + 16);
    v15 = v36;
  }
  else
  {
    v19 = (_QWORD *)(a1 + 16);
  }
  if ( *(_BYTE *)(*(_QWORD *)a1 + 103LL) )
    return 0;
  codeOffset(v9, *(unsigned int *)(a2 + 12), v15);
  switch ( *(_BYTE *)a4 )
  {
    case 0xA:
      v23 = 79;
      v22 = *(_DWORD *)(a4 + 4);
      v24 = *v8;
      v34 = *v10;
LABEL_20:
      sqlite3VdbeAddOp3(v24, v23, *v12, v22, v34);
      goto LABEL_21;
    case 0xB:
      TempReg = sqlite3GetTempReg(a1);
      sqlite3VdbeAddOp4(v9, 97, *v12, *v10, TempReg, *(_QWORD *)(a4 + 24), *v10);
      sqlite3VdbeAddOp4Int(v9, 138, *(_DWORD *)(a4 + 4), TempReg, *v12, *v10);
      v32 = *(_DWORD *)(a4 + 8);
      if ( v32 > 0 )
      {
        sqlite3VdbeAddOp4Int(v9, 183, v32, 0, *v12, *v10);
        sqlite3VdbeExplain(a1, 0, "CREATE BLOOM FILTER");
      }
      v30 = TempReg;
      v29 = a1;
      break;
    case 0xC:
      v26 = sqlite3GetTempReg(a1);
      v28 = sqlite3GetTempReg(v27);
      sqlite3VdbeAddOp3(v9, 97, *v12, *v10, v26);
      sqlite3VdbeAddOp3(v9, 127, *(_DWORD *)(a4 + 4), v28, 0);
      sqlite3VdbeAddOp3(v9, 128, *(_DWORD *)(a4 + 4), v26, v28);
      sqlite3VdbeChangeP5(v9, 8);
      sqlite3ReleaseTempReg(a1, v28);
      v30 = v26;
      break;
    case 0xD:
      TempRange = *(_DWORD *)(a4 + 12);
      if ( !TempRange )
      {
        TempRange = sqlite3GetTempRange(a1, *v10, v21);
        *(_DWORD *)(a4 + 12) = TempRange;
        *(_DWORD *)(a4 + 16) = *v10;
      }
      sqlite3VdbeAddOp3(*v19, 79, *v12, TempRange, *v10);
      sqlite3VdbeAddOp3(v9, 12, *(_DWORD *)(a4 + 4), 0, 0);
      goto LABEL_21;
    default:
      v22 = *v10;
      v23 = 84;
      v34 = 0;
      LODWORD(v24) = v9;
      goto LABEL_20;
  }
  sqlite3ReleaseTempReg(v29, v30);
  v15 = v36;
LABEL_21:
  v33 = *(_DWORD *)(v37 + 8);
  if ( v33 )
    sqlite3VdbeAddOp3(v9, 61, v33, a8, 0);
  sqlite3VdbeResolveLabel(v9, v15);
  sqlite3VdbeAddOp3(v9, 67, a5, 0, 0);
  return v35;
}

```

## disassembly

```asm
0x180070350  mov     [rsp+arg_10], rbx
0x180070355  mov     [rsp+arg_8], rdx
0x18007035a  push    rbp
0x18007035b  push    rsi
0x18007035c  push    rdi
0x18007035d  push    r12
0x18007035f  push    r13
0x180070361  push    r14
0x180070363  push    r15
0x180070365  sub     rsp, 50h
0x180070369  mov     edi, [rsp+88h+arg_28]
0x180070370  lea     r13, [rcx+10h]
0x180070374  mov     rsi, [r13+0]
0x180070378  lea     r15, [r8+10h]
0x18007037c  mov     rbp, r9
0x18007037f  lea     r12, [r8+0Ch]
0x180070383  mov     r14, rcx
0x180070386  mov     eax, [rsi+90h]
0x18007038c  dec     dword ptr [rcx+48h]
0x18007038f  mov     ebx, [rcx+48h]
0x180070392  mov     [rsp+88h+var_48], eax
0x180070396  mov     [rsp+88h+arg_0], ebx
0x18007039d  test    edi, edi
0x18007039f  jz      loc_18007047A
0x1800703a5  xor     r9d, r9d
0x1800703a8  mov     [rsp+88h+var_68], 0
0x1800703b0  mov     r8d, edi
0x1800703b3  mov     rcx, rsi
0x1800703b6  lea     edx, [r9+11h]
0x1800703ba  call    sqlite3VdbeAddOp3
0x1800703bf  mov     rcx, [rsp+88h+arg_30]
0x1800703c7  mov     ebx, eax
0x1800703c9  call    sqlite3KeyInfoRef
0x1800703ce  mov     r8d, [r12]
0x1800703d2  lea     r9d, [rdi+1]
0x1800703d6  mov     [rsp+88h+var_58], 0FFFFFFF8h
0x1800703de  mov     edx, 5Ah ; 'Z'
0x1800703e3  mov     [rsp+88h+var_60], rax
0x1800703e8  mov     rcx, rsi
0x1800703eb  mov     eax, [r15]
0x1800703ee  mov     [rsp+88h+var_68], eax
0x1800703f2  call    sqlite3VdbeAddOp4
0x1800703f7  mov     r9d, [rsp+88h+arg_0]
0x1800703ff  mov     edx, 0Eh
0x180070404  mov     rcx, rsi
0x180070407  lea     r8d, [rax+2]
0x18007040b  mov     [rsp+88h+var_68], r8d
0x180070410  call    sqlite3VdbeAddOp3
0x180070415  mov     edx, ebx
0x180070417  mov     rcx, rsi
0x18007041a  call    sqlite3VdbeGetOp
0x18007041f  mov     rdx, rax
0x180070422  lea     r9d, [rdi+1]
0x180070426  mov     eax, [rsi+90h]
0x18007042c  mov     rcx, rsi
0x18007042f  mov     [rdx+8], eax
0x180070432  mov     edx, 50h ; 'P'
0x180070437  mov     eax, [r15]
0x18007043a  mov     r8d, [r12]
0x18007043e  dec     eax
0x180070440  mov     [rsp+88h+var_68], eax
0x180070444  call    sqlite3VdbeAddOp3
0x180070449  mov     edx, 47h ; 'G'
0x18007044e  mov     [rsp+88h+var_68], 0
0x180070456  mov     r9d, edi
0x180070459  mov     rcx, rsi
0x18007045c  lea     r8d, [rdx-46h]
0x180070460  call    sqlite3VdbeAddOp3
0x180070465  mov     rdx, [rsp+88h+arg_8]
0x18007046d  lea     rdi, [r14+10h]
0x180070471  mov     ebx, [rsp+88h+arg_0]
0x180070478  jmp     short loc_18007047D
0x18007047a  mov     rdi, r13
0x18007047d  mov     rax, [r14]
0x180070480  cmp     byte ptr [rax+67h], 0
0x180070484  jz      short loc_18007048D
0x180070486  xor     eax, eax
0x180070488  jmp     loc_1800706BB
0x18007048d  mov     edx, [rdx+0Ch]
0x180070490  mov     r8d, ebx
0x180070493  mov     rcx, rsi
0x180070496  call    codeOffset
0x18007049b  movzx   ecx, byte ptr [rbp+0]
0x18007049f  sub     ecx, 0Ah
0x1800704a2  jz      loc_180070643
0x1800704a8  sub     ecx, 1
0x1800704ab  jz      loc_1800705AD
0x1800704b1  sub     ecx, 1
0x1800704b4  jz      short loc_180070526
0x1800704b6  cmp     ecx, 1
0x1800704b9  jz      short loc_1800704D3
0x1800704bb  mov     r9d, [r15]
0x1800704be  mov     edx, 54h ; 'T'
0x1800704c3  mov     [rsp+88h+var_68], 0
0x1800704cb  mov     rcx, rsi
0x1800704ce  jmp     loc_180070657
0x1800704d3  mov     r9d, [rbp+0Ch]
0x1800704d7  test    r9d, r9d
0x1800704da  jnz     short loc_1800704F3
0x1800704dc  mov     edx, [r15]
0x1800704df  mov     rcx, r14
0x1800704e2  call    sqlite3GetTempRange
0x1800704e7  mov     r9d, eax
0x1800704ea  mov     [rbp+0Ch], eax
0x1800704ed  mov     eax, [r15]
0x1800704f0  mov     [rbp+10h], eax
0x1800704f3  mov     eax, [r15]
0x1800704f6  mov     edx, 4Fh ; 'O'
0x1800704fb  mov     r8d, [r12]
0x1800704ff  mov     rcx, [rdi]
0x180070502  mov     [rsp+88h+var_68], eax
0x180070506  call    sqlite3VdbeAddOp3
0x18007050b  mov     r8d, [rbp+4]
0x18007050f  xor     r9d, r9d
0x180070512  mov     [rsp+88h+var_68], 0
0x18007051a  mov     rcx, rsi
0x18007051d  lea     edx, [r9+0Ch]
0x180070521  jmp     loc_18007065B
0x180070526  mov     rcx, r14
0x180070529  call    sqlite3GetTempReg
0x18007052e  mov     edi, eax
0x180070530  call    sqlite3GetTempReg
0x180070535  mov     r9d, [r15]
0x180070538  mov     edx, 61h ; 'a'
0x18007053d  mov     r8d, [r12]
0x180070541  mov     rcx, rsi
0x180070544  mov     ebx, eax
0x180070546  mov     [rsp+88h+var_68], edi
0x18007054a  call    sqlite3VdbeAddOp3
0x18007054f  mov     r8d, [rbp+4]
0x180070553  mov     r9d, ebx
0x180070556  mov     edx, 7Fh
0x18007055b  mov     [rsp+88h+var_68], 0
0x180070563  mov     rcx, rsi
0x180070566  call    sqlite3VdbeAddOp3
0x18007056b  mov     r8d, [rbp+4]
0x18007056f  mov     r9d, edi
0x180070572  mov     edx, 80h
0x180070577  mov     [rsp+88h+var_68], ebx
0x18007057b  mov     rcx, rsi
0x18007057e  call    sqlite3VdbeAddOp3
0x180070583  mov     edx, 8
0x180070588  mov     rcx, rsi
0x18007058b  call    sqlite3VdbeChangeP5
0x180070590  mov     edx, ebx
0x180070592  mov     rcx, r14
0x180070595  call    sqlite3ReleaseTempReg
0x18007059a  mov     edx, edi
0x18007059c  call    sqlite3ReleaseTempReg
0x1800705a1  mov     ebx, [rsp+88h+arg_0]
0x1800705a8  jmp     loc_180070660
0x1800705ad  mov     rcx, r14
0x1800705b0  call    sqlite3GetTempReg
0x1800705b5  mov     r9d, [r15]
0x1800705b8  mov     ebx, eax
0x1800705ba  mov     rax, [rbp+18h]
0x1800705be  mov     edx, 61h ; 'a'
0x1800705c3  mov     r8d, [r12]
0x1800705c7  mov     rcx, rsi
0x1800705ca  mov     [rsp+88h+var_58], r9d
0x1800705cf  mov     [rsp+88h+var_60], rax
0x1800705d4  mov     [rsp+88h+var_68], ebx
0x1800705d8  call    sqlite3VdbeAddOp4
0x1800705dd  mov     eax, [r15]
0x1800705e0  mov     r9d, ebx
0x1800705e3  mov     r8d, [rbp+4]
0x1800705e7  mov     edx, 8Ah
0x1800705ec  mov     dword ptr [rsp+88h+var_60], eax
0x1800705f0  mov     rcx, rsi
0x1800705f3  mov     eax, [r12]
0x1800705f7  mov     [rsp+88h+var_68], eax
0x1800705fb  call    sqlite3VdbeAddOp4Int
0x180070600  mov     r8d, [rbp+8]
0x180070604  test    r8d, r8d
0x180070607  jle     short loc_180070639
0x180070609  mov     eax, [r15]
0x18007060c  xor     r9d, r9d
0x18007060f  mov     dword ptr [rsp+88h+var_60], eax
0x180070613  mov     edx, 0B7h
0x180070618  mov     eax, [r12]
0x18007061c  mov     rcx, rsi
0x18007061f  mov     [rsp+88h+var_68], eax
0x180070623  call    sqlite3VdbeAddOp4Int
0x180070628  lea     r8, aCreateBloomFil; "CREATE BLOOM FILTER"
0x18007062f  xor     edx, edx
0x180070631  mov     rcx, r14
0x180070634  call    sqlite3VdbeExplain
0x180070639  mov     edx, ebx
0x18007063b  mov     rcx, r14
0x18007063e  jmp     loc_18007059C
0x180070643  mov     eax, [r15]
0x180070646  mov     edx, 4Fh ; 'O'
0x18007064b  mov     r9d, [rbp+4]
0x18007064f  mov     rcx, [r13+0]
0x180070653  mov     [rsp+88h+var_68], eax
0x180070657  mov     r8d, [r12]
0x18007065b  call    sqlite3VdbeAddOp3
0x180070660  mov     r8, [rsp+88h+arg_8]
0x180070668  mov     r8d, [r8+8]
0x18007066c  test    r8d, r8d
0x18007066f  jz      short loc_18007068E
0x180070671  mov     r9d, [rsp+88h+arg_38]
0x180070679  mov     edx, 3Dh ; '='
0x18007067e  mov     rcx, rsi
0x180070681  mov     [rsp+88h+var_68], 0
0x180070689  call    sqlite3VdbeAddOp3
0x18007068e  mov     edx, ebx
0x180070690  mov     rcx, rsi
0x180070693  call    sqlite3VdbeResolveLabel
0x180070698  mov     r8d, [rsp+88h+arg_20]
0x1800706a0  xor     r9d, r9d
0x1800706a3  mov     rcx, rsi
0x1800706a6  mov     [rsp+88h+var_68], 0
0x1800706ae  lea     edx, [r9+43h]
0x1800706b2  call    sqlite3VdbeAddOp3
0x1800706b7  mov     eax, [rsp+88h+var_48]
0x1800706bb  mov     rbx, [rsp+88h+arg_10]
0x1800706c3  add     rsp, 50h
0x1800706c7  pop     r15
0x1800706c9  pop     r14
0x1800706cb  pop     r13
0x1800706cd  pop     r12
0x1800706cf  pop     rdi
0x1800706d0  pop     rsi
0x1800706d1  pop     rbp
0x1800706d2  retn
```
