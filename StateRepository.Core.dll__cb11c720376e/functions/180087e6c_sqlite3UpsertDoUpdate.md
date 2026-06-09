# sqlite3UpsertDoUpdate

- ea: `0x180087e6c`
- end: `0x1800880f4`
- name: `sqlite3UpsertDoUpdate`
- size: `648`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x18001a8dc`

## callees

- `0x18000e808`
- `0x1800119e0`
- `0x180011d80`
- `0x1800167c0`
- `0x180036688`
- `0x18003abcc`
- `0x18003e1e0`
- `0x18003fc90`
- `0x18003ff00`
- `0x18004cfa0`
- `0x180062484`
- `0x180067de4`
- `0x180087e6c`
- `0x1800880fc`

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
  int v14; // r13d
  int TempReg; // ebx
  __int64 v16; // rax
  __int64 v17; // r8
  int v18; // ecx
  __int64 v19; // rbx
  int v20; // edx
  int v21; // eax
  int v22; // ebp
  __int16 v23; // ax
  int v24; // r11d
  unsigned int v25; // ebx
  __int64 v26; // rdx
  int v27; // ebx
  __int64 i; // r13
  __int64 v29; // rbx
  __int64 v30; // rdi
  int *v31; // rax
  int v33; // [rsp+40h] [rbp-68h]
  __int64 v34; // [rsp+48h] [rbp-60h]
  __int64 v35; // [rsp+50h] [rbp-58h]
  __int64 v36; // [rsp+58h] [rbp-50h]
  int v40; // [rsp+C8h] [rbp+20h]

  v5 = a2;
  v6 = a1[2];
  v7 = (__int64)a1;
  v36 = *a1;
  v9 = a3;
  v10 = sqlite3UpsertOfIndex(a2, a4);
  v34 = v10;
  v12 = v10;
  if ( v13 )
  {
    v14 = *(_DWORD *)(v5 + 76);
    if ( a5 == v14 )
    {
      v12 = v10;
    }
    else
    {
      if ( *(char *)(v11 + 48) < 0 )
      {
        v16 = sqlite3PrimaryKeyIndex(v11);
        v18 = *(_DWORD *)(v7 + 60);
        v19 = 0;
        v35 = v16;
        v20 = *(unsigned __int16 *)(v16 + 94);
        v21 = v18 + 1;
        v40 = v20;
        v33 = v18 + 1;
        *(_DWORD *)(v7 + 60) = v20 + v18;
        if ( v20 )
        {
          v22 = v20;
          do
          {
            v23 = sqlite3TableColumnToIndex(a4, *(unsigned __int16 *)(*(_QWORD *)(v35 + 8) + 2 * v19), v17);
            sqlite3VdbeAddOp3(v6, 94, a5, v23, v24);
            v19 = (unsigned int)(v19 + 1);
          }
          while ( (int)v19 < v22 );
          v7 = (__int64)a1;
          v9 = a3;
          v5 = a2;
          v20 = v40;
          v21 = v33;
        }
        v25 = sqlite3VdbeAddOp4Int(v6, 29, v14, 0, v21, v20);
        sqlite3VdbeAddOp4(v6, 70, 11, 2, 0, (__int64)"corrupt database", -1);
        v26 = v7;
        if ( *(_QWORD *)(v7 + 176) )
          v26 = *(_QWORD *)(v7 + 176);
        *(_BYTE *)(v26 + 33) = 1;
        *(_DWORD *)(sqlite3VdbeGetOp(v6, v25) + 8) = *(_DWORD *)(v6 + 144);
      }
      else
      {
        TempReg = sqlite3GetTempReg(v7);
        sqlite3VdbeAddOp3(v6, 142, a5, TempReg, 0);
        sqlite3VdbeAddOp3(v6, 30, v14, 0, TempReg);
        sqlite3ReleaseTempReg(v7, TempReg);
      }
      v12 = v34;
    }
  }
  v27 = 0;
  for ( i = sqlite3SrcListDup(v36, *(_QWORD *)(v5 + 64), 0); v27 < *(__int16 *)(v9 + 54); ++v27 )
  {
    if ( *(_BYTE *)(*(_QWORD *)(v9 + 8) + 24LL * v27 + 12) == 69 )
      sqlite3VdbeAddOp3(v6, 87, v27 + *(_DWORD *)(v5 + 72), 0, 0);
  }
  v29 = *(_QWORD *)(v12 + 16);
  v30 = sqlite3ExprDup(v36, *(_QWORD *)(v12 + 24), 0);
  v31 = (int *)sqlite3ExprListDup(v36, v29, 0);
  return sqlite3Update((__int64 *)v7, i, v31, v30, 2, 0, 0, v12);
}

```

## disassembly

```asm
0x180087e6c  mov     [rsp+arg_10], r8
0x180087e71  mov     [rsp+arg_8], rdx
0x180087e76  mov     [rsp+arg_0], rcx
0x180087e7b  push    rbx
0x180087e7c  push    rbp
0x180087e7d  push    rsi
0x180087e7e  push    rdi
0x180087e7f  push    r12
0x180087e81  push    r13
0x180087e83  push    r14
0x180087e85  push    r15
0x180087e87  sub     rsp, 68h
0x180087e8b  mov     rax, [rcx]
0x180087e8e  mov     rbp, rdx
0x180087e91  mov     r14, [rcx+10h]
0x180087e95  mov     rsi, rcx
0x180087e98  mov     rcx, rbp
0x180087e9b  mov     [rsp+0A8h+var_50], rax
0x180087ea0  mov     rdx, r9
0x180087ea3  mov     r12, r9
0x180087ea6  mov     rdi, r8
0x180087ea9  call    sqlite3UpsertOfIndex
0x180087eae  mov     [rsp+0A8h+var_60], rax
0x180087eb3  mov     r15, rax
0x180087eb6  test    r9, r9
0x180087eb9  jz      loc_180088034
0x180087ebf  mov     r13d, [rbp+4Ch]
0x180087ec3  mov     r15d, [rsp+0A8h+arg_20]
0x180087ecb  cmp     r15d, r13d
0x180087ece  jz      loc_180088031
0x180087ed4  test    byte ptr [r8+30h], 80h
0x180087ed9  jnz     short loc_180087F2A
0x180087edb  mov     rcx, rsi
0x180087ede  call    sqlite3GetTempReg
0x180087ee3  mov     r9d, eax
0x180087ee6  mov     [rsp+0A8h+var_88], 0
0x180087eee  mov     r8d, r15d
0x180087ef1  mov     edx, 8Eh
0x180087ef6  mov     rcx, r14
0x180087ef9  mov     ebx, eax
0x180087efb  call    sqlite3VdbeAddOp3
0x180087f00  xor     r9d, r9d
0x180087f03  mov     [rsp+0A8h+var_88], ebx
0x180087f07  mov     r8d, r13d
0x180087f0a  mov     rcx, r14
0x180087f0d  lea     edx, [r9+1Eh]
0x180087f11  call    sqlite3VdbeAddOp3
0x180087f16  mov     edx, ebx
0x180087f18  mov     rcx, rsi
0x180087f1b  call    sqlite3ReleaseTempReg
0x180087f20  mov     r15, [rsp+0A8h+var_60]
0x180087f25  jmp     loc_180088034
0x180087f2a  mov     rcx, r8
0x180087f2d  call    sqlite3PrimaryKeyIndex
0x180087f32  mov     ecx, [rsi+3Ch]
0x180087f35  xor     ebx, ebx
0x180087f37  mov     [rsp+0A8h+var_58], rax
0x180087f3c  movzx   edx, word ptr [rax+5Eh]
0x180087f40  lea     eax, [rcx+1]
0x180087f43  mov     [rsp+0A8h+arg_18], edx
0x180087f4a  add     ecx, edx
0x180087f4c  mov     [rsp+0A8h+var_68], eax
0x180087f50  mov     [rsi+3Ch], ecx
0x180087f53  test    edx, edx
0x180087f55  jz      short loc_180087FB6
0x180087f57  mov     rdi, [rsp+0A8h+var_58]
0x180087f5c  mov     ebp, edx
0x180087f5e  mov     esi, eax
0x180087f60  mov     rdx, [rdi+8]
0x180087f64  lea     r11d, [rsi+rbx]
0x180087f68  mov     rcx, r12
0x180087f6b  movzx   edx, word ptr [rdx+rbx*2]
0x180087f6f  call    sqlite3TableColumnToIndex
0x180087f74  movsx   r9d, ax
0x180087f78  mov     r8d, r15d
0x180087f7b  mov     edx, 5Eh ; '^'
0x180087f80  mov     [rsp+0A8h+var_88], r11d
0x180087f85  mov     rcx, r14
0x180087f88  call    sqlite3VdbeAddOp3
0x180087f8d  inc     ebx
0x180087f8f  cmp     ebx, ebp
0x180087f91  jl      short loc_180087F60
0x180087f93  mov     rsi, [rsp+0A8h+arg_0]
0x180087f9b  mov     rdi, [rsp+0A8h+arg_10]
0x180087fa3  mov     rbp, [rsp+0A8h+arg_8]
0x180087fab  mov     edx, [rsp+0A8h+arg_18]
0x180087fb2  mov     eax, [rsp+0A8h+var_68]
0x180087fb6  mov     dword ptr [rsp+0A8h+var_80], edx
0x180087fba  xor     r9d, r9d
0x180087fbd  mov     r8d, r13d
0x180087fc0  mov     [rsp+0A8h+var_88], eax
0x180087fc4  mov     rcx, r14
0x180087fc7  lea     edx, [r9+1Dh]
0x180087fcb  call    sqlite3VdbeAddOp4Int
0x180087fd0  mov     edx, 46h ; 'F'
0x180087fd5  mov     dword ptr [rsp+0A8h+var_78], 0FFFFFFFFh
0x180087fdd  mov     ebx, eax
0x180087fdf  mov     rcx, r14
0x180087fe2  lea     rax, aCorruptDatabas; "corrupt database"
0x180087fe9  mov     [rsp+0A8h+var_80], rax
0x180087fee  lea     r9d, [rdx-44h]
0x180087ff2  mov     [rsp+0A8h+var_88], 0
0x180087ffa  lea     r8d, [rdx-3Bh]
0x180087ffe  call    sqlite3VdbeAddOp4
0x180088003  mov     rcx, [rsi+0B0h]
0x18008800a  mov     rdx, rsi
0x18008800d  test    rcx, rcx
0x180088010  cmovnz  rdx, rcx
0x180088014  mov     rcx, r14
0x180088017  mov     byte ptr [rdx+21h], 1
0x18008801b  mov     edx, ebx
0x18008801d  call    sqlite3VdbeGetOp
0x180088022  mov     ecx, [r14+90h]
0x180088029  mov     [rax+8], ecx
0x18008802c  jmp     loc_180087F20
0x180088031  mov     r15, rax
0x180088034  mov     r12, [rsp+0A8h+var_50]
0x180088039  xor     r8d, r8d
0x18008803c  mov     rdx, [rbp+40h]
0x180088040  mov     rcx, r12
0x180088043  call    sqlite3SrcListDup
0x180088048  xor     ecx, ecx
0x18008804a  xor     ebx, ebx
0x18008804c  mov     r13, rax
0x18008804f  cmp     cx, [rdi+36h]
0x180088053  jge     short loc_18008808F
0x180088055  mov     rax, [rdi+8]
0x180088059  movsxd  rcx, ebx
0x18008805c  lea     rdx, [rcx+rcx*2]
0x180088060  cmp     byte ptr [rax+rdx*8+0Ch], 45h ; 'E'
0x180088065  jnz     short loc_180088085
0x180088067  mov     r8d, [rbp+48h]
0x18008806b  xor     r9d, r9d
0x18008806e  add     r8d, ebx
0x180088071  mov     [rsp+0A8h+var_88], 0
0x180088079  mov     rcx, r14
0x18008807c  lea     edx, [r9+57h]
0x180088080  call    sqlite3VdbeAddOp3
0x180088085  movsx   eax, word ptr [rdi+36h]
0x180088089  inc     ebx
0x18008808b  cmp     ebx, eax
0x18008808d  jl      short loc_180088055
0x18008808f  mov     rdx, [r15+18h]
0x180088093  xor     r8d, r8d
0x180088096  mov     rbx, [r15+10h]
0x18008809a  mov     rcx, r12
0x18008809d  call    sqlite3ExprDup
0x1800880a2  xor     r8d, r8d
0x1800880a5  mov     rdx, rbx
0x1800880a8  mov     rcx, r12
0x1800880ab  mov     rdi, rax
0x1800880ae  call    sqlite3ExprListDup
0x1800880b3  mov     [rsp+0A8h+var_70], r15
0x1800880b8  mov     r8, rax
0x1800880bb  mov     [rsp+0A8h+var_78], 0
0x1800880c4  mov     r9, rdi
0x1800880c7  mov     [rsp+0A8h+var_80], 0
0x1800880d0  mov     rdx, r13
0x1800880d3  mov     rcx, rsi
0x1800880d6  mov     [rsp+0A8h+var_88], 2
0x1800880de  call    sqlite3Update
0x1800880e3  add     rsp, 68h
0x1800880e7  pop     r15
0x1800880e9  pop     r14
0x1800880eb  pop     r13
0x1800880ed  pop     r12
0x1800880ef  pop     rdi
0x1800880f0  pop     rsi
0x1800880f1  pop     rbp
0x1800880f2  pop     rbx
0x1800880f3  retn
```
