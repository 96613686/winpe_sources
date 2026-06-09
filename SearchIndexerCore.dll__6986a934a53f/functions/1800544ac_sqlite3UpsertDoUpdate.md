# sqlite3UpsertDoUpdate

- ea: `0x1800544ac`
- end: `0x18005474b`
- name: `sqlite3UpsertDoUpdate`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x180019470`

## callees

- `0x18000506c`
- `0x180007190`
- `0x180009ac0`
- `0x18000a954`
- `0x180015700`
- `0x1800168c0`
- `0x18001b16c`
- `0x18001cb40`
- `0x18004a418`
- `0x18004a478`
- `0x1800544ac`
- `0x180054754`
- `0x180054824`
- `0x18006a7b8`

## pseudocode

```c
__int64 __fastcall sqlite3UpsertDoUpdate(__int64 *a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v5; // rbp
  __int64 v6; // r14
  __int64 v7; // rsi
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r15
  __int64 v13; // r9
  int v14; // ebx
  __int64 i; // r13
  __int64 v16; // rbx
  __int64 v17; // rdi
  int *v18; // rax
  int v20; // r13d
  int TempReg; // ebx
  unsigned int v22; // ebx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rax
  int v27; // ecx
  int v28; // ebx
  int v29; // edx
  int v30; // eax
  int v31; // ebp
  __int16 v32; // ax
  int v33; // r11d
  __int64 v34; // [rsp+20h] [rbp-88h]
  int v35; // [rsp+40h] [rbp-68h]
  __int64 v36; // [rsp+48h] [rbp-60h]
  __int64 v37; // [rsp+58h] [rbp-50h]
  int v41; // [rsp+C8h] [rbp+20h]

  v5 = a2;
  v6 = a1[2];
  v7 = (__int64)a1;
  v37 = *a1;
  v9 = a3;
  v10 = sqlite3UpsertOfIndex(a2, a4);
  v36 = v10;
  v12 = v10;
  if ( v13 )
  {
    v20 = *(_DWORD *)(v5 + 76);
    if ( a5 == v20 )
    {
      v12 = v10;
    }
    else
    {
      if ( *(char *)(v11 + 48) < 0 )
      {
        v26 = sqlite3PrimaryKeyIndex(v11);
        v27 = *(_DWORD *)(v7 + 56);
        v28 = 0;
        v29 = *(unsigned __int16 *)(v26 + 94);
        v30 = v27 + 1;
        v41 = v29;
        v35 = v27 + 1;
        *(_DWORD *)(v7 + 56) = v29 + v27;
        if ( v29 )
        {
          v31 = v29;
          do
          {
            v32 = sqlite3TableColumnToIndex(a4);
            sqlite3VdbeAddOp3(v6, 94, a5, v32, v33);
            ++v28;
          }
          while ( v28 < v31 );
          v7 = (__int64)a1;
          v9 = a3;
          v5 = a2;
          v29 = v41;
          v30 = v35;
        }
        v22 = sqlite3VdbeAddOp4Int(v6, 29, v20, 0, v30, v29);
        sqlite3VdbeAddOp4(v6, 70, 11, 2, 0, (__int64)"corrupt database", -1);
        v25 = v7;
        if ( *(_QWORD *)(v7 + 176) )
          v25 = *(_QWORD *)(v7 + 176);
        *(_BYTE *)(v25 + 33) = 1;
        *(_DWORD *)(sqlite3VdbeGetOp(v6, v22, v23, v24) + 8) = *(_DWORD *)(v6 + 144);
      }
      else
      {
        TempReg = sqlite3GetTempReg(v7);
        sqlite3VdbeAddOp3(v6, 142, a5, TempReg, 0);
        sqlite3VdbeAddOp3(v6, 30, v20, 0, TempReg);
        sqlite3ReleaseTempReg(v7, TempReg);
      }
      v12 = v36;
    }
  }
  v14 = 0;
  for ( i = sqlite3SrcListDup(v37, *(_QWORD *)(v5 + 64), 0); v14 < *(__int16 *)(v9 + 54); ++v14 )
  {
    if ( *(_BYTE *)(*(_QWORD *)(v9 + 8) + 24LL * v14 + 12) == 69 )
      sqlite3VdbeAddOp3(v6, 87, v14 + *(_DWORD *)(v5 + 72), 0, 0);
  }
  v16 = *(_QWORD *)(v12 + 16);
  v17 = sqlite3ExprDup(v37, *(_QWORD *)(v12 + 24), 0);
  v18 = (int *)sqlite3ExprListDup(v37, v16, 0);
  LODWORD(v34) = 2;
  return sqlite3Update(v7, i, v18, v17, v34, 0, 0, v12);
}

```

## disassembly

```asm
0x1800544ac  mov     [rsp+arg_10], r8
0x1800544b1  mov     [rsp+arg_8], rdx
0x1800544b6  mov     [rsp+arg_0], rcx
0x1800544bb  push    rbx
0x1800544bc  push    rbp
0x1800544bd  push    rsi
0x1800544be  push    rdi
0x1800544bf  push    r12
0x1800544c1  push    r13
0x1800544c3  push    r14
0x1800544c5  push    r15
0x1800544c7  sub     rsp, 68h
0x1800544cb  mov     rax, [rcx]
0x1800544ce  mov     rbp, rdx
0x1800544d1  mov     r14, [rcx+10h]
0x1800544d5  mov     rsi, rcx
0x1800544d8  mov     rcx, rbp
0x1800544db  mov     [rsp+0A8h+var_50], rax
0x1800544e0  mov     rdx, r9
0x1800544e3  mov     r12, r9
0x1800544e6  mov     rdi, r8
0x1800544e9  call    sqlite3UpsertOfIndex
0x1800544ee  mov     [rsp+0A8h+var_60], rax
0x1800544f3  mov     r15, rax
0x1800544f6  test    r9, r9
0x1800544f9  jnz     loc_1800545A5
0x1800544ff  mov     r12, [rsp+0A8h+var_50]
0x180054504  xor     r8d, r8d
0x180054507  mov     rdx, [rbp+40h]
0x18005450b  mov     rcx, r12
0x18005450e  call    sqlite3SrcListDup
0x180054513  xor     ecx, ecx
0x180054515  xor     ebx, ebx
0x180054517  mov     r13, rax
0x18005451a  cmp     cx, [rdi+36h]
0x18005451e  jge     short loc_180054540
0x180054520  mov     rax, [rdi+8]
0x180054524  movsxd  rcx, ebx
0x180054527  lea     rdx, [rcx+rcx*2]
0x18005452b  cmp     byte ptr [rax+rdx*8+0Ch], 45h ; 'E'
0x180054530  jz      loc_180054728
0x180054536  movsx   eax, word ptr [rdi+36h]
0x18005453a  inc     ebx
0x18005453c  cmp     ebx, eax
0x18005453e  jl      short loc_180054520
0x180054540  mov     rdx, [r15+18h]
0x180054544  xor     r8d, r8d
0x180054547  mov     rbx, [r15+10h]
0x18005454b  mov     rcx, r12
0x18005454e  call    sqlite3ExprDup
0x180054553  xor     r8d, r8d
0x180054556  mov     rdx, rbx
0x180054559  mov     rcx, r12
0x18005455c  mov     rdi, rax
0x18005455f  call    sqlite3ExprListDup
0x180054564  mov     [rsp+0A8h+var_70], r15
0x180054569  mov     r8, rax
0x18005456c  mov     [rsp+0A8h+var_78], 0
0x180054575  mov     r9, rdi
0x180054578  mov     [rsp+0A8h+var_80], 0
0x180054581  mov     rdx, r13
0x180054584  mov     rcx, rsi
0x180054587  mov     dword ptr [rsp+0A8h+var_88], 2
0x18005458f  call    sqlite3Update
0x180054594  add     rsp, 68h
0x180054598  pop     r15
0x18005459a  pop     r14
0x18005459c  pop     r13
0x18005459e  pop     r12
0x1800545a0  pop     rdi
0x1800545a1  pop     rsi
0x1800545a2  pop     rbp
0x1800545a3  pop     rbx
0x1800545a4  retn
0x1800545a5  mov     r13d, [rbp+4Ch]
0x1800545a9  mov     r15d, [rsp+0A8h+arg_20]
0x1800545b1  cmp     r15d, r13d
0x1800545b4  jnz     short loc_1800545BE
0x1800545b6  mov     r15, rax
0x1800545b9  jmp     loc_1800544FF
0x1800545be  test    byte ptr [r8+30h], 80h
0x1800545c3  jnz     loc_1800546B6
0x1800545c9  mov     rcx, rsi
0x1800545cc  call    sqlite3GetTempReg
0x1800545d1  mov     r9d, eax
0x1800545d4  mov     dword ptr [rsp+0A8h+var_88], 0
0x1800545dc  mov     r8d, r15d
0x1800545df  mov     edx, 8Eh
0x1800545e4  mov     rcx, r14
0x1800545e7  mov     ebx, eax
0x1800545e9  call    sqlite3VdbeAddOp3
0x1800545ee  xor     r9d, r9d
0x1800545f1  mov     dword ptr [rsp+0A8h+var_88], ebx
0x1800545f5  mov     r8d, r13d
0x1800545f8  mov     rcx, r14
0x1800545fb  lea     edx, [r9+1Eh]
0x1800545ff  call    sqlite3VdbeAddOp3
0x180054604  mov     edx, ebx
0x180054606  mov     rcx, rsi
0x180054609  call    sqlite3ReleaseTempReg
0x18005460e  jmp     loc_1800546AC
0x180054613  mov     rsi, [rsp+0A8h+arg_0]
0x18005461b  mov     rdi, [rsp+0A8h+arg_10]
0x180054623  mov     rbp, [rsp+0A8h+arg_8]
0x18005462b  mov     edx, [rsp+0A8h+arg_18]
0x180054632  mov     eax, [rsp+0A8h+var_68]
0x180054636  mov     dword ptr [rsp+0A8h+var_80], edx
0x18005463a  xor     r9d, r9d
0x18005463d  mov     r8d, r13d
0x180054640  mov     dword ptr [rsp+0A8h+var_88], eax
0x180054644  mov     rcx, r14
0x180054647  lea     edx, [r9+1Dh]
0x18005464b  call    sqlite3VdbeAddOp4Int
0x180054650  mov     edx, 46h ; 'F'
0x180054655  mov     dword ptr [rsp+0A8h+var_78], 0FFFFFFFFh
0x18005465d  mov     ebx, eax
0x18005465f  mov     rcx, r14
0x180054662  lea     rax, aCorruptDatabas; "corrupt database"
0x180054669  mov     [rsp+0A8h+var_80], rax
0x18005466e  lea     r9d, [rdx-44h]
0x180054672  mov     dword ptr [rsp+0A8h+var_88], 0
0x18005467a  lea     r8d, [rdx-3Bh]
0x18005467e  call    sqlite3VdbeAddOp4
0x180054683  mov     rcx, [rsi+0B0h]
0x18005468a  mov     rdx, rsi
0x18005468d  test    rcx, rcx
0x180054690  cmovnz  rdx, rcx
0x180054694  mov     rcx, r14
0x180054697  mov     byte ptr [rdx+21h], 1
0x18005469b  mov     edx, ebx
0x18005469d  call    sqlite3VdbeGetOp
0x1800546a2  mov     ecx, [r14+90h]
0x1800546a9  mov     [rax+8], ecx
0x1800546ac  mov     r15, [rsp+0A8h+var_60]
0x1800546b1  jmp     loc_1800544FF
0x1800546b6  mov     rcx, r8
0x1800546b9  call    sqlite3PrimaryKeyIndex
0x1800546be  mov     ecx, [rsi+38h]
0x1800546c1  xor     ebx, ebx
0x1800546c3  mov     [rsp+0A8h+var_58], rax
0x1800546c8  movzx   edx, word ptr [rax+5Eh]
0x1800546cc  lea     eax, [rcx+1]
0x1800546cf  mov     [rsp+0A8h+arg_18], edx
0x1800546d6  add     ecx, edx
0x1800546d8  mov     [rsp+0A8h+var_68], eax
0x1800546dc  mov     [rsi+38h], ecx
0x1800546df  test    edx, edx
0x1800546e1  jz      loc_180054636
0x1800546e7  mov     rdi, [rsp+0A8h+var_58]
0x1800546ec  mov     ebp, edx
0x1800546ee  mov     esi, eax
0x1800546f0  mov     rdx, [rdi+8]
0x1800546f4  lea     r11d, [rsi+rbx]
0x1800546f8  mov     rcx, r12
0x1800546fb  movzx   edx, word ptr [rdx+rbx*2]
0x1800546ff  call    sqlite3TableColumnToIndex
0x180054704  movsx   r9d, ax
0x180054708  mov     r8d, r15d
0x18005470b  mov     edx, 5Eh ; '^'
0x180054710  mov     dword ptr [rsp+0A8h+var_88], r11d
0x180054715  mov     rcx, r14
0x180054718  call    sqlite3VdbeAddOp3
0x18005471d  inc     ebx
0x18005471f  cmp     ebx, ebp
0x180054721  jl      short loc_1800546F0
0x180054723  jmp     loc_180054613
0x180054728  mov     r8d, [rbp+48h]
0x18005472c  xor     r9d, r9d
0x18005472f  add     r8d, ebx
0x180054732  mov     dword ptr [rsp+0A8h+var_88], 0
0x18005473a  mov     rcx, r14
0x18005473d  lea     edx, [r9+57h]
0x180054741  call    sqlite3VdbeAddOp3
0x180054746  jmp     loc_180054536
```
