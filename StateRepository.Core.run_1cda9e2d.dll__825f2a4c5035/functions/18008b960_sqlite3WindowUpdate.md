# sqlite3WindowUpdate

- ea: `0x18008b960`
- end: `0x18008bbd4`
- name: `sqlite3WindowUpdate`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18004ed80`

## callees

- `0x1800055cc`
- `0x18000c960`
- `0x18000e808`
- `0x18003e1e0`
- `0x180060ce8`
- `0x18008a85c`
- `0x18008b960`
- `0x180097f4c`

## pseudocode

```c
char __fastcall sqlite3WindowUpdate(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  _BYTE *v7; // rdi
  const char *v8; // rax
  const char *v9; // r14
  int v10; // ecx
  __int64 v11; // r14
  __int64 v12; // rdx
  __int64 v13; // rsi
  __int64 v14; // rdx
  char v15; // dl
  const char *v17; // [rsp+20h] [rbp-99h]
  int v18; // [rsp+28h] [rbp-91h]
  int v19; // [rsp+2Ch] [rbp-8Dh]
  _DWORD v20[2]; // [rsp+30h] [rbp-89h]
  const char *v21; // [rsp+38h] [rbp-81h]
  int v22; // [rsp+40h] [rbp-79h]
  int v23; // [rsp+44h] [rbp-75h]
  int v24; // [rsp+48h] [rbp-71h]
  const char *v25; // [rsp+50h] [rbp-69h]
  int v26; // [rsp+58h] [rbp-61h]
  int v27; // [rsp+5Ch] [rbp-5Dh]
  int v28; // [rsp+60h] [rbp-59h]
  const char *v29; // [rsp+68h] [rbp-51h]
  int v30; // [rsp+70h] [rbp-49h]
  int v31; // [rsp+74h] [rbp-45h]
  int v32; // [rsp+78h] [rbp-41h]
  const char *v33; // [rsp+80h] [rbp-39h]
  int v34; // [rsp+88h] [rbp-31h]
  int v35; // [rsp+8Ch] [rbp-2Dh]
  int v36; // [rsp+90h] [rbp-29h]
  const char *v37; // [rsp+98h] [rbp-21h]
  int v38; // [rsp+A0h] [rbp-19h]
  int v39; // [rsp+A4h] [rbp-15h]
  int v40; // [rsp+A8h] [rbp-11h]
  const char *v41; // [rsp+B0h] [rbp-9h]
  int v42; // [rsp+B8h] [rbp-1h]
  int v43; // [rsp+BCh] [rbp+3h]
  int v44; // [rsp+C0h] [rbp+7h]
  void *v45; // [rsp+C8h] [rbp+Fh]
  int v46; // [rsp+D0h] [rbp+17h]
  int v47; // [rsp+D4h] [rbp+1Bh]
  int v48; // [rsp+D8h] [rbp+1Fh]

  v7 = (_BYTE *)(a3 + 32);
  if ( !*(_QWORD *)a3 || *v7 )
  {
    LOBYTE(v8) = sqlite3WindowChain(a1, a3, a2);
  }
  else
  {
    v8 = (const char *)windowFind();
    v9 = v8;
    if ( !v8 )
      return (char)v8;
    *(_QWORD *)(a3 + 16) = sqlite3ExprListDup(*a1, *((_QWORD *)v8 + 2), 0);
    *(_QWORD *)(a3 + 24) = sqlite3ExprListDup(*a1, *((_QWORD *)v9 + 3), 0);
    *(_QWORD *)(a3 + 40) = sqlite3ExprDup(*a1, *((_QWORD *)v9 + 5), 0);
    *(_QWORD *)(a3 + 48) = sqlite3ExprDup(*a1, *((_QWORD *)v9 + 6), 0);
    *(_BYTE *)(a3 + 33) = v9[33];
    *(_BYTE *)(a3 + 34) = v9[34];
    *v7 = v9[32];
    LOBYTE(v8) = v9[36];
    *(_BYTE *)(a3 + 36) = (_BYTE)v8;
  }
  if ( *v7 == 90
    && (*(_QWORD *)(a3 + 40) || *(_QWORD *)(a3 + 48))
    && ((v8 = *(const char **)(a3 + 24)) == 0 || *(_DWORD *)v8 != 1) )
  {
    LOBYTE(v8) = sqlite3ErrorMsg(a1, "RANGE with offset PRECEDING/FOLLOWING requires one ORDER BY expression");
  }
  else if ( (*(_DWORD *)(a4 + 4) & 0x10000) != 0 )
  {
    if ( *(_QWORD *)(a3 + 72) )
    {
      LOBYTE(v8) = sqlite3ErrorMsg(a1, "FILTER clause may only be used with aggregate window functions");
    }
    else
    {
      v22 = 90;
      v26 = 90;
      v17 = "row_number";
      v21 = "dense_rank";
      v25 = "rank";
      v18 = 77;
      v19 = 91;
      v30 = 93;
      v29 = "percent_rank";
      v33 = "cume_dist";
      v37 = "ntile";
      v41 = "lead";
      v8 = (const char *)&unk_1800A6964;
      v34 = 93;
      v10 = 0;
      v45 = &unk_1800A6964;
      v20[0] = 86;
      v23 = 91;
      v24 = 86;
      v27 = 91;
      v28 = 86;
      v31 = 86;
      v32 = 91;
      v35 = 87;
      v36 = 91;
      v38 = 77;
      v39 = 86;
      v40 = 91;
      v42 = 77;
      v43 = 91;
      v44 = 91;
      v46 = 77;
      v47 = 91;
      v48 = 86;
      while ( v10 < 8 )
      {
        v11 = 3LL * v10;
        v8 = (&v17)[3 * v10];
        if ( *(const char **)(a4 + 56) == v8 )
        {
          v12 = *(_QWORD *)(a3 + 40);
          v13 = *a1;
          if ( v12 )
            sqlite3ExprDeleteNN(v13, v12);
          v14 = *(_QWORD *)(a3 + 48);
          if ( v14 )
            sqlite3ExprDeleteNN(v13, v14);
          v15 = v20[2 * v11 - 1];
          *v7 = *((_BYTE *)&v18 + 8 * v11);
          LOBYTE(v8) = v20[2 * v11];
          *(_BYTE *)(a3 + 34) = (_BYTE)v8;
          *(_QWORD *)(a3 + 40) = 0;
          *(_QWORD *)(a3 + 48) = 0;
          *(_BYTE *)(a3 + 33) = v15;
          *(_BYTE *)(a3 + 36) = 0;
          if ( v15 == 87 )
          {
            v8 = (const char *)sqlite3Expr(v13, 156, "1");
            *(_QWORD *)(a3 + 40) = v8;
          }
          break;
        }
        ++v10;
      }
    }
  }
  *(_QWORD *)(a3 + 80) = a4;
  return (char)v8;
}

```

## disassembly

```asm
0x18008b960  push    rbp
0x18008b962  push    rbx
0x18008b963  push    rsi
0x18008b964  push    rdi
0x18008b965  push    r14
0x18008b967  push    r15
0x18008b969  lea     rbp, [rsp-2Fh]
0x18008b96e  sub     rsp, 0E8h
0x18008b975  mov     rbx, r8
0x18008b978  mov     r15, r9
0x18008b97b  mov     r8, [r8]
0x18008b97e  mov     rsi, rcx
0x18008b981  lea     rdi, [rbx+20h]
0x18008b985  test    r8, r8
0x18008b988  jz      short loc_18008BA09
0x18008b98a  cmp     byte ptr [rdi], 0
0x18008b98d  jnz     short loc_18008BA09
0x18008b98f  call    windowFind
0x18008b994  mov     r14, rax
0x18008b997  test    rax, rax
0x18008b99a  jz      loc_18008BBC4
0x18008b9a0  mov     rdx, [rax+10h]
0x18008b9a4  xor     r8d, r8d
0x18008b9a7  mov     rcx, [rsi]
0x18008b9aa  call    sqlite3ExprListDup
0x18008b9af  mov     [rbx+10h], rax
0x18008b9b3  xor     r8d, r8d
0x18008b9b6  mov     rdx, [r14+18h]
0x18008b9ba  mov     rcx, [rsi]
0x18008b9bd  call    sqlite3ExprListDup
0x18008b9c2  mov     [rbx+18h], rax
0x18008b9c6  xor     r8d, r8d
0x18008b9c9  mov     rdx, [r14+28h]
0x18008b9cd  mov     rcx, [rsi]
0x18008b9d0  call    sqlite3ExprDup
0x18008b9d5  mov     [rbx+28h], rax
0x18008b9d9  xor     r8d, r8d
0x18008b9dc  mov     rdx, [r14+30h]
0x18008b9e0  mov     rcx, [rsi]
0x18008b9e3  call    sqlite3ExprDup
0x18008b9e8  mov     [rbx+30h], rax
0x18008b9ec  mov     al, [r14+21h]
0x18008b9f0  mov     [rbx+21h], al
0x18008b9f3  mov     al, [r14+22h]
0x18008b9f7  mov     [rbx+22h], al
0x18008b9fa  mov     al, [r14+20h]
0x18008b9fe  mov     [rdi], al
0x18008ba00  mov     al, [r14+24h]
0x18008ba04  mov     [rbx+24h], al
0x18008ba07  jmp     short loc_18008BA14
0x18008ba09  mov     r8, rdx
0x18008ba0c  mov     rdx, rbx
0x18008ba0f  call    sqlite3WindowChain
0x18008ba14  mov     ecx, 5Ah ; 'Z'
0x18008ba19  cmp     [rdi], cl
0x18008ba1b  jnz     short loc_18008BA42
0x18008ba1d  cmp     qword ptr [rbx+28h], 0
0x18008ba22  jnz     short loc_18008BA2B
0x18008ba24  cmp     qword ptr [rbx+30h], 0
0x18008ba29  jz      short loc_18008BA42
0x18008ba2b  mov     rax, [rbx+18h]
0x18008ba2f  test    rax, rax
0x18008ba32  jz      short loc_18008BA39
0x18008ba34  cmp     dword ptr [rax], 1
0x18008ba37  jz      short loc_18008BA42
0x18008ba39  lea     rdx, aRangeWithOffse; "RANGE with offset PRECEDING/FOLLOWING r"...
0x18008ba40  jmp     short loc_18008BA5E
0x18008ba42  test    dword ptr [r15+4], 10000h
0x18008ba4a  jz      loc_18008BBC0
0x18008ba50  cmp     qword ptr [rbx+48h], 0
0x18008ba55  jz      short loc_18008BA6B
0x18008ba57  lea     rdx, aFilterClauseMa; "FILTER clause may only be used with agg"...
0x18008ba5e  mov     rcx, rsi
0x18008ba61  call    sqlite3ErrorMsg
0x18008ba66  jmp     loc_18008BBC0
0x18008ba6b  mov     r9d, 4Dh ; 'M'
0x18008ba71  mov     [rbp+57h+var_D0], ecx
0x18008ba74  lea     rax, aRowNumber; "row_number"
0x18008ba7b  mov     [rbp+57h+var_B8], ecx
0x18008ba7e  mov     [rsp+110h+var_F0], rax
0x18008ba83  lea     rax, aDenseRank; "dense_rank"
0x18008ba8a  mov     [rsp+110h+var_D8], rax
0x18008ba8f  lea     rax, aRank; "rank"
0x18008ba96  lea     r8d, [r9+0Eh]
0x18008ba9a  mov     [rbp+57h+var_C0], rax
0x18008ba9e  lea     edx, [r9+9]
0x18008baa2  mov     [rsp+110h+var_E8], r9d
0x18008baa7  lea     ecx, [rdx+7]
0x18008baaa  mov     [rsp+110h+var_E4], r8d
0x18008baaf  lea     rax, aPercentRank; "percent_rank"
0x18008bab6  mov     [rbp+57h+var_A0], ecx
0x18008bab9  mov     [rbp+57h+var_A8], rax
0x18008babd  lea     rax, aCumeDist; "cume_dist"
0x18008bac4  mov     [rbp+57h+var_90], rax
0x18008bac8  lea     rax, aNtile; "ntile"
0x18008bacf  mov     [rbp+57h+var_78], rax
0x18008bad3  lea     rax, aLead; "lead"
0x18008bada  mov     [rbp+57h+var_60], rax
0x18008bade  lea     rax, unk_1800A6964
0x18008bae5  mov     [rbp+57h+var_88], ecx
0x18008bae8  xor     ecx, ecx
0x18008baea  mov     [rbp+57h+var_48], rax
0x18008baee  mov     [rsp+110h+var_E0], edx
0x18008baf2  mov     [rbp+57h+var_CC], r8d
0x18008baf6  mov     [rbp+57h+var_C8], edx
0x18008baf9  mov     [rbp+57h+var_B4], r8d
0x18008bafd  mov     [rbp+57h+var_B0], edx
0x18008bb00  mov     [rbp+57h+var_9C], edx
0x18008bb03  mov     [rbp+57h+var_98], r8d
0x18008bb07  mov     [rbp+57h+var_84], 57h ; 'W'
0x18008bb0e  mov     [rbp+57h+var_80], r8d
0x18008bb12  mov     [rbp+57h+var_70], r9d
0x18008bb16  mov     [rbp+57h+var_6C], edx
0x18008bb19  mov     [rbp+57h+var_68], r8d
0x18008bb1d  mov     [rbp+57h+var_58], r9d
0x18008bb21  mov     [rbp+57h+var_54], r8d
0x18008bb25  mov     [rbp+57h+var_50], r8d
0x18008bb29  mov     [rbp+57h+var_40], r9d
0x18008bb2d  mov     [rbp+57h+var_3C], r8d
0x18008bb31  mov     [rbp+57h+var_38], edx
0x18008bb34  cmp     ecx, 8
0x18008bb37  jge     loc_18008BBC0
0x18008bb3d  movsxd  rax, ecx
0x18008bb40  lea     r14, [rax+rax*2]
0x18008bb44  mov     rax, [rsp+r14*8+110h+var_F0]
0x18008bb49  cmp     [r15+38h], rax
0x18008bb4d  jz      short loc_18008BB53
0x18008bb4f  inc     ecx
0x18008bb51  jmp     short loc_18008BB34
0x18008bb53  mov     rdx, [rbx+28h]
0x18008bb57  mov     rsi, [rsi]
0x18008bb5a  test    rdx, rdx
0x18008bb5d  jz      short loc_18008BB67
0x18008bb5f  mov     rcx, rsi
0x18008bb62  call    sqlite3ExprDeleteNN
0x18008bb67  mov     rdx, [rbx+30h]
0x18008bb6b  test    rdx, rdx
0x18008bb6e  jz      short loc_18008BB78
0x18008bb70  mov     rcx, rsi
0x18008bb73  call    sqlite3ExprDeleteNN
0x18008bb78  mov     al, byte ptr [rsp+r14*8+110h+var_E8]
0x18008bb7d  mov     dl, byte ptr [rsp+r14*8+110h+var_E4]
0x18008bb82  mov     [rdi], al
0x18008bb84  mov     al, byte ptr [rsp+r14*8+110h+var_E0]
0x18008bb89  mov     [rbx+22h], al
0x18008bb8c  mov     qword ptr [rbx+28h], 0
0x18008bb94  mov     qword ptr [rbx+30h], 0
0x18008bb9c  mov     [rbx+21h], dl
0x18008bb9f  mov     byte ptr [rbx+24h], 0
0x18008bba3  cmp     dl, 57h ; 'W'
0x18008bba6  jnz     short loc_18008BBC0
0x18008bba8  lea     r8, a1; "1"
0x18008bbaf  mov     edx, 9Ch
0x18008bbb4  mov     rcx, rsi
0x18008bbb7  call    sqlite3Expr
0x18008bbbc  mov     [rbx+28h], rax
0x18008bbc0  mov     [rbx+50h], r15
0x18008bbc4  add     rsp, 0E8h
0x18008bbcb  pop     r15
0x18008bbcd  pop     r14
0x18008bbcf  pop     rdi
0x18008bbd0  pop     rsi
0x18008bbd1  pop     rbx
0x18008bbd2  pop     rbp
0x18008bbd3  retn
```
