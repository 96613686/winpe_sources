# generateSortTail

- ea: `0x1800706dc`
- end: `0x180070c49`
- name: `generateSortTail`
- size: `1389`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180037194`

## callees

- `0x180005c54`
- `0x1800119e0`
- `0x180011d80`
- `0x18001c1c4`
- `0x18001c220`
- `0x180036688`
- `0x1800370c0`
- `0x18003abcc`
- `0x18003ff00`
- `0x1800443c8`
- `0x18004cfa0`
- `0x18005599c`
- `0x1800706dc`

## string_xrefs

- `0x180070784`: `USE TEMP B-TREE FOR %sORDER BY`
- `0x18007075c`: `USE TEMP B-TREE FOR LAST %d TERMS OF ORDER BY`

## pseudocode

```c
__int64 __fastcall generateSortTail(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, unsigned __int8 *a5)
{
  __int64 v8; // rbx
  __int64 v9; // r12
  unsigned int v10; // eax
  int v11; // ecx
  int v12; // r13d
  int v13; // r15d
  const char *v14; // r9
  int v15; // r9d
  unsigned int v16; // edx
  int v17; // r10d
  __int64 v18; // r8
  unsigned int TempReg; // r13d
  unsigned int TempRange; // esi
  unsigned int v21; // ebp
  int v22; // r9d
  int v23; // ebp
  __int64 v24; // r9
  int v25; // r8d
  int v26; // ebp
  unsigned int i; // edx
  int v28; // ecx
  int v29; // r15d
  int v30; // ecx
  int v31; // r9d
  char v32; // dl
  int v33; // r8d
  unsigned int v34; // r9d
  int v35; // edx
  int v36; // r15d
  int v37; // ebp
  int v38; // r8d
  int v40; // [rsp+40h] [rbp-68h]
  int v41; // [rsp+44h] [rbp-64h]
  unsigned int v42; // [rsp+48h] [rbp-60h]
  unsigned int v43; // [rsp+4Ch] [rbp-5Ch]
  int v44; // [rsp+50h] [rbp-58h]
  __int64 v45; // [rsp+58h] [rbp-50h]
  int v46; // [rsp+B0h] [rbp+8h]
  int v48; // [rsp+B8h] [rbp+10h]
  int v49; // [rsp+B8h] [rbp+10h]
  int v51; // [rsp+C8h] [rbp+20h]

  --*(_DWORD *)(a1 + 72);
  v8 = *(_QWORD *)(a1 + 16);
  v9 = a3;
  v42 = *(_DWORD *)(a3 + 28);
  v10 = *(_DWORD *)(a1 + 72);
  v11 = *(_DWORD *)(a3 + 8);
  v12 = *a5;
  v43 = v10;
  v40 = *((_DWORD *)a5 + 1);
  v51 = v12;
  v45 = *(_QWORD *)(a2 + 32) + 8LL;
  v13 = **(_DWORD **)a3 - v11;
  if ( !v11 || v13 == 1 )
  {
    v14 = "LAST TERM OF ";
    if ( !v11 )
      v14 = byte_18009EEF0;
    sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %sORDER BY", v14);
  }
  else
  {
    sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR LAST %d TERMS OF ORDER BY", v13);
  }
  v15 = *(_DWORD *)(v9 + 20);
  v16 = 0;
  if ( v15 )
  {
    sqlite3VdbeAddOp3(v8, 10, *(_DWORD *)(v9 + 16), v15, 0);
    sqlite3VdbeAddOp3(v8, 9, 0, v42, 0);
    sqlite3VdbeResolveLabel(v8, *(unsigned int *)(v9 + 20));
    v16 = 0;
  }
  v17 = *(_DWORD *)(v9 + 12);
  v41 = v17;
  if ( ((v12 - 9) & 0xFFFFFFFB) == 0 )
    goto LABEL_16;
  if ( v12 == 10 )
  {
    if ( *(_DWORD *)(a2 + 12) )
    {
      sqlite3VdbeAddOp3(v8, 75, 0, *((_DWORD *)a5 + 3), 0);
      v17 = v41;
      v16 = 0;
    }
LABEL_16:
    TempRange = *((_DWORD *)a5 + 3);
    TempReg = 0;
    goto LABEL_17;
  }
  TempReg = sqlite3GetTempReg(a1);
  if ( ((v51 - 12) & 0xFFFFFFFD) != 0 )
  {
    TempRange = sqlite3GetTempRange(a1, a4, v18);
    v16 = 0;
  }
  else
  {
    TempRange = sqlite3GetTempReg(a1);
    a4 = v16;
  }
LABEL_17:
  if ( (*(_BYTE *)(v9 + 36) & 1) != 0 )
  {
    ++*(_DWORD *)(a1 + 60);
    v21 = v16;
    v48 = *(_DWORD *)(a1 + 60);
    v46 = *(_DWORD *)(a1 + 56);
    *(_DWORD *)(a1 + 56) = v46 + 1;
    if ( *(_DWORD *)(v9 + 20) != v16 )
      v21 = sqlite3VdbeAddOp3(v8, 15, 0, 0, v16);
    sqlite3VdbeAddOp3(v8, 121, v46, v48, a4 + v13 + 1);
    v22 = 0;
    if ( v21 )
      *(_DWORD *)(sqlite3VdbeGetOp(v8, v21) + 8) = *(_DWORD *)(v8 + 144);
    v44 = sqlite3VdbeAddOp3(v8, 34, v41, v42, v22) + 1;
    sqlite3VdbeAddOp3(v8, 133, v41, v48, v46);
    v23 = 0;
  }
  else
  {
    v44 = sqlite3VdbeAddOp3(v8, 35, v17, v42, v16) + 1;
    codeOffset(v8, *(unsigned int *)(a2 + 12), v43);
    v23 = 1;
    v46 = v41;
    if ( *(int *)(a2 + 12) > 0 )
      sqlite3VdbeAddOp3(v8, 86, *(_DWORD *)(a2 + 8), -1, 0);
  }
  v24 = v45;
  v25 = v13 + v23;
  v49 = v13 + v23;
  v26 = v13 + v23 - 1;
  for ( i = 0; (int)i < (int)a4; v26 = v28 )
  {
    v28 = v26 + 1;
    if ( *(_WORD *)(32LL * i + v45 + 24) )
      v28 = v26;
    ++i;
  }
  v29 = a4 - 1;
  if ( (int)(a4 - 1) >= 0 )
  {
    do
    {
      v30 = *(unsigned __int16 *)(32LL * (unsigned int)v29 + v24 + 24);
      if ( (_WORD)v30 )
        v31 = v30 - 1;
      else
        v31 = v26--;
      sqlite3VdbeAddOp3(v8, 94, v46, v31, v29 + TempRange);
      --v29;
      v24 = v45;
    }
    while ( v29 >= 0 );
    v9 = a3;
    v25 = v49;
  }
  v32 = v51;
  if ( v51 != 10 )
  {
    switch ( v51 )
    {
      case 11:
        sqlite3VdbeAddOp4(v8, 97, TempRange, a4, TempReg, *((_QWORD *)a5 + 3), a4);
        sqlite3VdbeAddOp4Int(v8, 138, v40, TempReg, TempRange, a4);
        break;
      case 12:
      case 14:
        sqlite3VdbeAddOp3(v8, 94, v46, v25, TempRange);
        sqlite3VdbeAddOp3(v8, 127, v40, TempReg, 0);
        sqlite3VdbeAddOp3(v8, 128, v40, TempRange, TempReg);
        sqlite3VdbeChangeP5(v8, 8);
        break;
      case 15:
        v36 = *((_DWORD *)a5 + 2);
        v37 = sqlite3GetTempReg(a1);
        sqlite3VdbeAddOp3(v8, 97, ((unsigned int)v36 >> 31) + TempRange, a4 - ((unsigned int)v36 >> 31), v37);
        if ( v36 >= 0 )
          sqlite3VdbeAddOp4Int(v8, 138, v40, v37, TempRange, v36);
        else
          sqlite3VdbeAddOp3(v8, 128, v40, v37, TempRange);
        break;
      default:
        if ( (_BYTE)v51 == 9 )
        {
          v33 = *((_DWORD *)a5 + 3);
          v34 = a4;
          v35 = 84;
        }
        else
        {
          v33 = *((_DWORD *)a5 + 1);
          v34 = 0;
          v35 = 12;
        }
        sqlite3VdbeAddOp3(v8, v35, v33, v34, 0);
        break;
    }
    v32 = v51;
  }
  if ( TempReg )
  {
    if ( v32 == 11 )
      sqlite3ReleaseTempRange(a1, TempRange, a4);
    else
      sqlite3ReleaseTempReg(a1, TempRange);
    sqlite3ReleaseTempReg(a1, TempReg);
  }
  sqlite3VdbeResolveLabel(v8, v43);
  sqlite3VdbeAddOp3(v8, 2 * ((*(_BYTE *)(v9 + 36) & 1) == 0) + 37, v41, v44, 0);
  v38 = *(_DWORD *)(v9 + 16);
  if ( v38 )
    sqlite3VdbeAddOp3(v8, 67, v38, 0, 0);
  return sqlite3VdbeResolveLabel(v8, v42);
}

```

## disassembly

```asm
0x1800706dc  mov     [rsp+arg_10], r8
0x1800706e1  mov     [rsp+arg_8], rdx
0x1800706e6  push    rbx
0x1800706e7  push    rbp
0x1800706e8  push    rsi
0x1800706e9  push    rdi
0x1800706ea  push    r12
0x1800706ec  push    r13
0x1800706ee  push    r14
0x1800706f0  push    r15
0x1800706f2  sub     rsp, 68h
0x1800706f6  dec     dword ptr [rcx+48h]
0x1800706f9  mov     rdi, rcx
0x1800706fc  mov     eax, [r8+1Ch]
0x180070700  mov     rbp, rdx
0x180070703  mov     rsi, [rsp+0A8h+arg_20]
0x18007070b  mov     r14d, r9d
0x18007070e  mov     rbx, [rcx+10h]
0x180070712  mov     r12, r8
0x180070715  mov     [rsp+0A8h+var_60], eax
0x180070719  mov     eax, [rcx+48h]
0x18007071c  mov     ecx, [r8+8]
0x180070720  movzx   r13d, byte ptr [rsi]
0x180070724  mov     [rsp+0A8h+var_5C], eax
0x180070728  mov     eax, [rsi+4]
0x18007072b  mov     [rsp+0A8h+var_68], eax
0x18007072f  mov     rax, [rdx+20h]
0x180070733  xor     edx, edx
0x180070735  add     rax, 8
0x180070739  mov     [rsp+0A8h+arg_18], r13d
0x180070741  mov     [rsp+0A8h+var_50], rax
0x180070746  mov     rax, [r8]
0x180070749  mov     r15d, [rax]
0x18007074c  sub     r15d, ecx
0x18007074f  test    ecx, ecx
0x180070751  jz      short loc_18007076D
0x180070753  cmp     r15d, 1
0x180070757  jz      short loc_18007076D
0x180070759  mov     r9d, r15d
0x18007075c  lea     r8, aUseTempBTreeFo; "USE TEMP B-TREE FOR LAST %d TERMS OF OR"...
0x180070763  mov     rcx, rdi
0x180070766  call    sqlite3VdbeExplain
0x18007076b  jmp     short loc_180070790
0x18007076d  test    ecx, ecx
0x18007076f  lea     rax, byte_18009EEF0
0x180070776  lea     r9, aLastTermOf; "LAST TERM OF "
0x18007077d  mov     rcx, rdi
0x180070780  cmovz   r9, rax
0x180070784  lea     r8, aUseTempBTreeFo_1; "USE TEMP B-TREE FOR %sORDER BY"
0x18007078b  call    sqlite3VdbeExplain
0x180070790  mov     r9d, [r12+14h]
0x180070795  xor     edx, edx
0x180070797  test    r9d, r9d
0x18007079a  jz      short loc_1800707DD
0x18007079c  mov     r8d, [r12+10h]
0x1800707a1  mov     rcx, rbx
0x1800707a4  mov     [rsp+0A8h+var_88], edx
0x1800707a8  mov     edx, 0Ah
0x1800707ad  call    sqlite3VdbeAddOp3
0x1800707b2  xor     r9d, r9d
0x1800707b5  xor     r8d, r8d
0x1800707b8  mov     [rsp+0A8h+var_88], r9d
0x1800707bd  mov     rcx, rbx
0x1800707c0  mov     r9d, [rsp+0A8h+var_60]
0x1800707c5  lea     edx, [r8+9]
0x1800707c9  call    sqlite3VdbeAddOp3
0x1800707ce  mov     edx, [r12+14h]
0x1800707d3  mov     rcx, rbx
0x1800707d6  call    sqlite3VdbeResolveLabel
0x1800707db  xor     edx, edx
0x1800707dd  mov     r10d, [r12+0Ch]
0x1800707e2  lea     eax, [r13-9]
0x1800707e6  mov     [rsp+0A8h+var_64], r10d
0x1800707eb  test    eax, 0FFFFFFFBh
0x1800707f0  jz      short loc_180070855
0x1800707f2  cmp     r13d, 0Ah
0x1800707f6  jz      short loc_180070832
0x1800707f8  mov     rcx, rdi
0x1800707fb  call    sqlite3GetTempReg
0x180070800  mov     ecx, [rsp+0A8h+arg_18]
0x180070807  mov     r13d, eax
0x18007080a  add     ecx, 0FFFFFFF4h
0x18007080d  test    ecx, 0FFFFFFFDh
0x180070813  mov     rcx, rdi
0x180070816  jz      short loc_180070826
0x180070818  mov     edx, r14d
0x18007081b  call    sqlite3GetTempRange
0x180070820  mov     esi, eax
0x180070822  xor     edx, edx
0x180070824  jmp     short loc_18007085B
0x180070826  call    sqlite3GetTempReg
0x18007082b  mov     esi, eax
0x18007082d  mov     r14d, edx
0x180070830  jmp     short loc_18007085B
0x180070832  cmp     [rbp+0Ch], edx
0x180070835  jz      short loc_180070855
0x180070837  mov     r9d, [rsi+0Ch]
0x18007083b  xor     r8d, r8d
0x18007083e  mov     [rsp+0A8h+var_88], edx
0x180070842  mov     rcx, rbx
0x180070845  lea     edx, [r8+4Bh]
0x180070849  call    sqlite3VdbeAddOp3
0x18007084e  mov     r10d, [rsp+0A8h+var_64]
0x180070853  xor     edx, edx
0x180070855  mov     esi, [rsi+0Ch]
0x180070858  mov     r13d, edx
0x18007085b  test    byte ptr [r12+24h], 1
0x180070861  jz      loc_180070935
0x180070867  inc     dword ptr [rdi+3Ch]
0x18007086a  mov     ebp, edx
0x18007086c  mov     eax, [rdi+3Ch]
0x18007086f  mov     dword ptr [rsp+0A8h+arg_8], eax
0x180070876  mov     eax, [rdi+38h]
0x180070879  mov     [rsp+0A8h+arg_0], eax
0x180070880  inc     eax
0x180070882  mov     [rdi+38h], eax
0x180070885  cmp     [r12+14h], edx
0x18007088a  jz      short loc_1800708A4
0x18007088c  xor     r9d, r9d
0x18007088f  mov     [rsp+0A8h+var_88], edx
0x180070893  xor     r8d, r8d
0x180070896  mov     rcx, rbx
0x180070899  lea     edx, [r9+0Fh]
0x18007089d  call    sqlite3VdbeAddOp3
0x1800708a2  mov     ebp, eax
0x1800708a4  mov     r9d, dword ptr [rsp+0A8h+arg_8]
0x1800708ac  lea     ecx, [r15+1]
0x1800708b0  mov     r8d, [rsp+0A8h+arg_0]
0x1800708b8  add     ecx, r14d
0x1800708bb  mov     [rsp+0A8h+var_88], ecx
0x1800708bf  mov     edx, 79h ; 'y'
0x1800708c4  mov     rcx, rbx
0x1800708c7  call    sqlite3VdbeAddOp3
0x1800708cc  xor     r9d, r9d
0x1800708cf  test    ebp, ebp
0x1800708d1  jz      short loc_1800708E6
0x1800708d3  mov     edx, ebp
0x1800708d5  mov     rcx, rbx
0x1800708d8  call    sqlite3VdbeGetOp
0x1800708dd  mov     ecx, [rbx+90h]
0x1800708e3  mov     [rax+8], ecx
0x1800708e6  mov     r8d, [rsp+0A8h+var_64]
0x1800708eb  mov     edx, 22h ; '"'
0x1800708f0  mov     [rsp+0A8h+var_88], r9d
0x1800708f5  mov     rcx, rbx
0x1800708f8  mov     r9d, [rsp+0A8h+var_60]
0x1800708fd  call    sqlite3VdbeAddOp3
0x180070902  mov     r9d, dword ptr [rsp+0A8h+arg_8]
0x18007090a  inc     eax
0x18007090c  mov     r8d, [rsp+0A8h+var_64]
0x180070911  mov     edx, 85h
0x180070916  mov     [rsp+0A8h+var_58], eax
0x18007091a  mov     rcx, rbx
0x18007091d  mov     eax, [rsp+0A8h+arg_0]
0x180070924  mov     [rsp+0A8h+var_88], eax
0x180070928  call    sqlite3VdbeAddOp3
0x18007092d  xor     r10d, r10d
0x180070930  mov     ebp, r10d
0x180070933  jmp     short loc_1800709A0
0x180070935  mov     r9d, [rsp+0A8h+var_60]
0x18007093a  mov     r8d, r10d
0x18007093d  mov     [rsp+0A8h+var_88], edx
0x180070941  mov     rcx, rbx
0x180070944  mov     edx, 23h ; '#'
0x180070949  call    sqlite3VdbeAddOp3
0x18007094e  mov     r8d, [rsp+0A8h+var_5C]
0x180070953  inc     eax
0x180070955  mov     edx, [rbp+0Ch]
0x180070958  mov     rcx, rbx
0x18007095b  mov     [rsp+0A8h+var_58], eax
0x18007095f  call    codeOffset
0x180070964  mov     r8, [rsp+0A8h+arg_8]
0x18007096c  xor     r10d, r10d
0x18007096f  mov     eax, [rsp+0A8h+var_64]
0x180070973  mov     ebp, 1
0x180070978  mov     [rsp+0A8h+arg_0], eax
0x18007097f  cmp     [r8+0Ch], r10d
0x180070983  jle     short loc_1800709A0
0x180070985  mov     r8d, [r8+8]
0x180070989  lea     edx, [rbp+55h]
0x18007098c  or      r9d, 0FFFFFFFFh
0x180070990  mov     [rsp+0A8h+var_88], r10d
0x180070995  mov     rcx, rbx
0x180070998  call    sqlite3VdbeAddOp3
0x18007099d  xor     r10d, r10d
0x1800709a0  mov     r9, [rsp+0A8h+var_50]
0x1800709a5  lea     r8d, [r15+rbp]
0x1800709a9  mov     dword ptr [rsp+0A8h+arg_8], r8d
0x1800709b1  lea     ebp, [r8-1]
0x1800709b5  mov     edx, r10d
0x1800709b8  test    r14d, r14d
0x1800709bb  jle     short loc_1800709D8
0x1800709bd  mov     eax, edx
0x1800709bf  lea     ecx, [rbp+1]
0x1800709c2  shl     rax, 5
0x1800709c6  cmp     [rax+r9+18h], r10w
0x1800709cc  cmovnz  ecx, ebp
0x1800709cf  inc     edx
0x1800709d1  mov     ebp, ecx
0x1800709d3  cmp     edx, r14d
0x1800709d6  jl      short loc_1800709BD
0x1800709d8  lea     r15d, [r14-1]
0x1800709dc  test    r15d, r15d
0x1800709df  js      short loc_180070A3F
0x1800709e1  mov     r12d, [rsp+0A8h+arg_0]
0x1800709e9  mov     eax, r15d
0x1800709ec  shl     rax, 5
0x1800709f0  movzx   ecx, word ptr [rax+r9+18h]
0x1800709f6  test    cx, cx
0x1800709f9  jz      short loc_180070A01
0x1800709fb  lea     r9d, [rcx-1]
0x1800709ff  jmp     short loc_180070A06
0x180070a01  mov     r9d, ebp
0x180070a04  dec     ebp
0x180070a06  lea     eax, [r15+rsi]
0x180070a0a  mov     r8d, r12d
0x180070a0d  mov     edx, 5Eh ; '^'
0x180070a12  mov     [rsp+0A8h+var_88], eax
0x180070a16  mov     rcx, rbx
0x180070a19  call    sqlite3VdbeAddOp3
0x180070a1e  sub     r15d, 1
0x180070a22  mov     r9, [rsp+0A8h+var_50]
0x180070a27  mov     r10d, 0
0x180070a2d  jns     short loc_1800709E9
0x180070a2f  mov     r12, [rsp+0A8h+arg_10]
0x180070a37  mov     r8d, dword ptr [rsp+0A8h+arg_8]
0x180070a3f  mov     edx, [rsp+0A8h+arg_18]
0x180070a46  mov     ecx, edx
0x180070a48  sub     ecx, 0Ah
0x180070a4b  jz      loc_180070BB2
0x180070a51  sub     ecx, 1
0x180070a54  jz      loc_180070B5F
0x180070a5a  sub     ecx, 1
0x180070a5d  jz      loc_180070AFD
0x180070a63  sub     ecx, 2
0x180070a66  jz      loc_180070AFD
0x180070a6c  mov     rax, [rsp+0A8h+arg_20]
0x180070a74  cmp     ecx, 1
0x180070a77  jz      short loc_180070AA9
0x180070a79  mov     [rsp+0A8h+var_88], r10d
0x180070a7e  mov     rcx, rbx
0x180070a81  cmp     dl, 9
0x180070a84  jnz     short loc_180070A9C
0x180070a86  mov     r8d, [rax+0Ch]
0x180070a8a  mov     r9d, r14d
0x180070a8d  mov     edx, 54h ; 'T'
0x180070a92  call    sqlite3VdbeAddOp3
0x180070a97  jmp     loc_180070BAB
0x180070a9c  mov     r8d, [rax+4]
0x180070aa0  xor     r9d, r9d
0x180070aa3  lea     edx, [r9+0Ch]
0x180070aa7  jmp     short loc_180070A92
0x180070aa9  mov     r15d, [rax+8]
0x180070aad  mov     rcx, rdi
0x180070ab0  call    sqlite3GetTempReg
0x180070ab5  mov     ecx, r15d
0x180070ab8  mov     [rsp+0A8h+var_88], eax
0x180070abc  shr     ecx, 1Fh
0x180070abf  mov     r9d, r14d
0x180070ac2  sub     r9d, ecx
0x180070ac5  mov     edx, 61h ; 'a'
0x180070aca  mov     ebp, eax
0x180070acc  lea     r8d, [rcx+rsi]
0x180070ad0  mov     rcx, rbx
0x180070ad3  call    sqlite3VdbeAddOp3
0x180070ad8  mov     r8d, [rsp+0A8h+var_68]
0x180070add  mov     r9d, ebp
0x180070ae0  mov     rcx, rbx
0x180070ae3  test    r15d, r15d
0x180070ae6  jns     short loc_180070AF3
0x180070ae8  mov     [rsp+0A8h+var_88], esi
0x180070aec  mov     edx, 80h
0x180070af1  jmp     short loc_180070A92
0x180070af3  mov     dword ptr [rsp+0A8h+var_80], r15d
0x180070af8  jmp     loc_180070B9D
0x180070afd  mov     r9d, r8d
0x180070b00  mov     [rsp+0A8h+var_88], esi
0x180070b04  mov     r8d, [rsp+0A8h+arg_0]
0x180070b0c  mov     edx, 5Eh ; '^'
0x180070b11  mov     rcx, rbx
0x180070b14  call    sqlite3VdbeAddOp3
0x180070b19  mov     r8d, [rsp+0A8h+var_68]
0x180070b1e  xor     r9d, r9d
0x180070b21  mov     [rsp+0A8h+var_88], r9d
0x180070b26  mov     edx, 7Fh
0x180070b2b  mov     r9d, r13d
0x180070b2e  mov     rcx, rbx
0x180070b31  call    sqlite3VdbeAddOp3
0x180070b36  mov     r8d, [rsp+0A8h+var_68]
0x180070b3b  mov     r9d, esi
0x180070b3e  mov     edx, 80h
0x180070b43  mov     [rsp+0A8h+var_88], r13d
0x180070b48  mov     rcx, rbx
0x180070b4b  call    sqlite3VdbeAddOp3
0x180070b50  mov     edx, 8
0x180070b55  mov     rcx, rbx
0x180070b58  call    sqlite3VdbeChangeP5
0x180070b5d  jmp     short loc_180070BAB
0x180070b5f  mov     rax, [rsp+0A8h+arg_20]
0x180070b67  mov     r9d, r14d
  ... truncated ...
```
