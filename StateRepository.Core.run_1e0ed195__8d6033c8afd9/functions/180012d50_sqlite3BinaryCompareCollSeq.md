# sqlite3BinaryCompareCollSeq

- ea: `0x180012d50`
- end: `0x180013227`
- name: `sqlite3BinaryCompareCollSeq`
- size: `1239`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000eb78`
- `0x18000f134`
- `0x180012aa4`
- `0x18001477c`
- `0x18004053c`
- `0x18005aa88`
- `0x180062c90`

## callees

- `0x180012d50`
- `0x180013230`
- `0x180013270`
- `0x1800133ec`
- `0x1800624b4`

## pseudocode

```c
__int64 __fastcall sqlite3BinaryCompareCollSeq(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r8
  __int64 v6; // r10
  _QWORD *v7; // rdi
  char *v8; // rax
  char v9; // al
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r10
  _QWORD *v13; // rax
  __int64 v14; // r10
  char *v15; // rax
  char v16; // al
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r10
  __int64 v20; // rax
  __int64 v22; // r10
  char *v23; // rax
  char v24; // al
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // r10
  __int64 CollSeq; // rax
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rdx
  _DWORD *v32; // rcx
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // rdx
  _DWORD *v36; // rcx
  int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rdx
  _DWORD *v40; // rcx
  int i; // r8d
  __int64 v42; // rax
  int j; // r8d
  __int64 v44; // rax
  int k; // r8d
  __int64 v46; // rax

  v4 = a2;
  if ( (*(_DWORD *)(a2 + 4) & 0x200) != 0 )
    return sqlite3ExprCollSeq(a1, a2);
  if ( a3 && (*(_DWORD *)(a3 + 4) & 0x200) != 0 )
  {
    v22 = *a1;
    v7 = 0;
    while ( 1 )
    {
      if ( !a3 )
        return (__int64)v7;
      v23 = (char *)(*(_BYTE *)a3 == 0xB0 ? a3 + 2 : a3);
      v24 = *v23;
      if ( v24 == -86 )
        break;
      switch ( v24 )
      {
        case -88:
        case 78:
LABEL_32:
          v25 = *(__int16 *)(a3 + 48);
          if ( (v25 & 0x8000u) != 0LL )
            return (__int64)v7;
          v26 = sqlite3ColumnColl(*(_QWORD *)(*(_QWORD *)(a3 + 64) + 8LL) + 24 * v25);
          CollSeq = sqlite3FindCollSeq(v27, *(unsigned __int8 *)(v27 + 100), v26, 0);
LABEL_34:
          v7 = (_QWORD *)CollSeq;
          if ( !CollSeq || *(_QWORD *)(CollSeq + 24) )
            return (__int64)v7;
          goto LABEL_36;
        case 36:
        case -83:
          a3 = *(_QWORD *)(a3 + 16);
          break;
        case -79:
          a3 = *(_QWORD *)(*(_QWORD *)(a3 + 32) + 8LL);
          break;
        case 114:
          CollSeq = sqlite3GetCollSeq(a1, *(unsigned __int8 *)(v22 + 100), 0, *(_QWORD *)(a3 + 8));
          goto LABEL_34;
        default:
LABEL_66:
          v37 = *(_DWORD *)(a3 + 4);
          if ( (v37 & 0x200) == 0 )
            return (__int64)v7;
          v38 = *(_QWORD *)(a3 + 16);
          if ( v38 && (*(_DWORD *)(v38 + 4) & 0x200) != 0 )
          {
            a3 = *(_QWORD *)(a3 + 16);
          }
          else
          {
            v39 = *(_QWORD *)(a3 + 24);
            if ( (v37 & 0x1000) == 0 )
            {
              v40 = *(_DWORD **)(a3 + 32);
              if ( v40 )
              {
                if ( !*(_BYTE *)(v22 + 103) )
                {
                  for ( i = 0; i < *v40; ++i )
                  {
                    v42 = 8LL * i;
                    if ( (*(_DWORD *)(*(_QWORD *)&v40[v42 + 2] + 4LL) & 0x200) != 0 )
                    {
                      v39 = *(_QWORD *)&v40[v42 + 2];
                      break;
                    }
                  }
                }
              }
            }
            a3 = v39;
          }
          break;
      }
    }
    if ( *(_QWORD *)(a3 + 64) )
      goto LABEL_32;
    goto LABEL_66;
  }
  v6 = *a1;
  v7 = 0;
  while ( 1 )
  {
    if ( !v4 )
      goto LABEL_13;
    if ( *(_BYTE *)v4 == 0xB0 )
      v8 = (char *)(v4 + 2);
    else
      v8 = (char *)v4;
    v9 = *v8;
    if ( v9 == -86 )
    {
      if ( *(_QWORD *)(v4 + 64) )
        break;
      goto LABEL_44;
    }
    if ( v9 == -88 || v9 == 78 )
      break;
    switch ( v9 )
    {
      case 36:
      case -83:
        v4 = *(_QWORD *)(v4 + 16);
        break;
      case -79:
        v4 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + 8LL);
        break;
      case 114:
        v13 = (_QWORD *)sqlite3GetCollSeq(a1, *(unsigned __int8 *)(v6 + 100), 0, *(_QWORD *)(v4 + 8));
        goto LABEL_11;
      default:
LABEL_44:
        v29 = *(_DWORD *)(v4 + 4);
        if ( (v29 & 0x200) == 0 )
          goto LABEL_13;
        v30 = *(_QWORD *)(v4 + 16);
        if ( v30 && (*(_DWORD *)(v30 + 4) & 0x200) != 0 )
        {
          v4 = *(_QWORD *)(v4 + 16);
        }
        else
        {
          v31 = *(_QWORD *)(v4 + 24);
          if ( (v29 & 0x1000) == 0 )
          {
            v32 = *(_DWORD **)(v4 + 32);
            if ( v32 )
            {
              if ( !*(_BYTE *)(v6 + 103) )
              {
                for ( j = 0; j < *v32; ++j )
                {
                  v44 = 8LL * j;
                  if ( (*(_DWORD *)(*(_QWORD *)&v32[v44 + 2] + 4LL) & 0x200) != 0 )
                  {
                    v31 = *(_QWORD *)&v32[v44 + 2];
                    break;
                  }
                }
              }
            }
          }
          v4 = v31;
        }
        break;
    }
  }
  v10 = *(__int16 *)(v4 + 48);
  if ( (v10 & 0x8000u) == 0LL )
  {
    v11 = sqlite3ColumnColl(*(_QWORD *)(*(_QWORD *)(v4 + 64) + 8LL) + 24 * v10);
    v13 = (_QWORD *)sqlite3FindCollSeq(v12, *(unsigned __int8 *)(v12 + 100), v11, 0);
LABEL_11:
    v7 = v13;
    if ( !v13 || !v13[3] && !sqlite3GetCollSeq(a1, *(unsigned __int8 *)(*a1 + 100), v13, *v13) )
    {
LABEL_14:
      v14 = *a1;
      v7 = 0;
      while ( 1 )
      {
        if ( !a3 )
          return (__int64)v7;
        v15 = (char *)(*(_BYTE *)a3 == 0xB0 ? a3 + 2 : a3);
        v16 = *v15;
        if ( v16 == -86 )
          break;
        switch ( v16 )
        {
          case -88:
          case 78:
LABEL_20:
            v17 = *(__int16 *)(a3 + 48);
            if ( (v17 & 0x8000u) != 0LL )
              return (__int64)v7;
            v18 = sqlite3ColumnColl(*(_QWORD *)(*(_QWORD *)(a3 + 64) + 8LL) + 24 * v17);
            v20 = sqlite3FindCollSeq(v19, *(unsigned __int8 *)(v19 + 100), v18, 0);
            goto LABEL_22;
          case 36:
          case -83:
            a3 = *(_QWORD *)(a3 + 16);
            break;
          case -79:
            a3 = *(_QWORD *)(*(_QWORD *)(a3 + 32) + 8LL);
            break;
          case 114:
            v20 = sqlite3GetCollSeq(a1, *(unsigned __int8 *)(v14 + 100), 0, *(_QWORD *)(a3 + 8));
LABEL_22:
            v7 = (_QWORD *)v20;
            if ( v20 && !*(_QWORD *)(v20 + 24) )
            {
LABEL_36:
              if ( !sqlite3GetCollSeq(a1, *(unsigned __int8 *)(*a1 + 100), v7, *v7) )
                return 0;
            }
            return (__int64)v7;
          default:
LABEL_55:
            v33 = *(_DWORD *)(a3 + 4);
            if ( (v33 & 0x200) == 0 )
              return (__int64)v7;
            v34 = *(_QWORD *)(a3 + 16);
            if ( v34 && (*(_DWORD *)(v34 + 4) & 0x200) != 0 )
            {
              a3 = *(_QWORD *)(a3 + 16);
            }
            else
            {
              v35 = *(_QWORD *)(a3 + 24);
              if ( (v33 & 0x1000) == 0 )
              {
                v36 = *(_DWORD **)(a3 + 32);
                if ( v36 )
                {
                  if ( !*(_BYTE *)(v14 + 103) )
                  {
                    for ( k = 0; k < *v36; ++k )
                    {
                      v46 = 8LL * k;
                      if ( (*(_DWORD *)(*(_QWORD *)&v36[v46 + 2] + 4LL) & 0x200) != 0 )
                      {
                        v35 = *(_QWORD *)&v36[v46 + 2];
                        break;
                      }
                    }
                  }
                }
              }
              a3 = v35;
            }
            break;
        }
      }
      if ( *(_QWORD *)(a3 + 64) )
        goto LABEL_20;
      goto LABEL_55;
    }
  }
LABEL_13:
  if ( !v7 )
    goto LABEL_14;
  return (__int64)v7;
}

```

## disassembly

```asm
0x180012d50  mov     [rsp+arg_10], rbx
0x180012d55  push    r14
0x180012d57  sub     rsp, 20h
0x180012d5b  test    dword ptr [rdx+4], 200h
0x180012d62  mov     rbx, r8
0x180012d65  mov     r8, rdx
0x180012d68  mov     r14, rcx
0x180012d6b  jnz     loc_18001309E
0x180012d71  mov     [rsp+28h+arg_0], rsi
0x180012d76  mov     [rsp+28h+arg_8], rdi
0x180012d7b  test    rbx, rbx
0x180012d7e  jnz     loc_180012E80
0x180012d84  mov     r10, [rcx]
0x180012d87  xor     esi, esi
0x180012d89  mov     edi, esi
0x180012d8b  test    r8, r8
0x180012d8e  jz      short loc_180012DF4
0x180012d90  cmp     byte ptr [r8], 0B0h
0x180012d94  jz      loc_180013120
0x180012d9a  mov     rax, r8
0x180012d9d  movzx   eax, byte ptr [rax]
0x180012da0  cmp     al, 0AAh
0x180012da2  jz      loc_180013129
0x180012da8  cmp     al, 0A8h
0x180012daa  jnz     loc_180012F21
0x180012db0  movsx   rax, word ptr [r8+30h]
0x180012db5  test    ax, ax
0x180012db8  js      short loc_180012DF4
0x180012dba  lea     rdx, [rax+rax*2]
0x180012dbe  mov     rax, [r8+40h]
0x180012dc2  mov     rcx, [rax+8]
0x180012dc6  lea     rcx, [rcx+rdx*8]
0x180012dca  call    sqlite3ColumnColl
0x180012dcf  movzx   edx, byte ptr [r10+64h]
0x180012dd4  mov     r8, rax
0x180012dd7  xor     r9d, r9d
0x180012dda  mov     rcx, r10
0x180012ddd  call    sqlite3FindCollSeq
0x180012de2  mov     rdi, rax
0x180012de5  test    rax, rax
0x180012de8  jz      short loc_180012DF9
0x180012dea  cmp     [rax+18h], rsi
0x180012dee  jz      loc_180013192
0x180012df4  test    rdi, rdi
0x180012df7  jnz     short loc_180012E67
0x180012df9  mov     r10, [r14]
0x180012dfc  mov     rdi, rsi
0x180012dff  test    rbx, rbx
0x180012e02  jz      short loc_180012E67
0x180012e04  cmp     byte ptr [rbx], 0B0h
0x180012e07  jz      loc_1800131B5
0x180012e0d  mov     rax, rbx
0x180012e10  movzx   eax, byte ptr [rax]
0x180012e13  cmp     al, 0AAh
0x180012e15  jz      loc_1800131BE
0x180012e1b  cmp     al, 0A8h
0x180012e1d  jnz     loc_180012F89
0x180012e23  movsx   rax, word ptr [rbx+30h]
0x180012e28  test    ax, ax
0x180012e2b  js      short loc_180012E67
0x180012e2d  mov     rdx, [rbx+40h]
0x180012e31  lea     rcx, [rax+rax*2]
0x180012e35  mov     rax, [rdx+8]
0x180012e39  lea     rcx, [rax+rcx*8]
0x180012e3d  call    sqlite3ColumnColl
0x180012e42  movzx   edx, byte ptr [r10+64h]
0x180012e47  mov     r8, rax
0x180012e4a  xor     r9d, r9d
0x180012e4d  mov     rcx, r10
0x180012e50  call    sqlite3FindCollSeq
0x180012e55  mov     rdi, rax
0x180012e58  test    rax, rax
0x180012e5b  jz      short loc_180012E67
0x180012e5d  cmp     [rax+18h], rsi
0x180012e61  jz      loc_180012F00
0x180012e67  mov     rsi, [rsp+28h+arg_0]
0x180012e6c  mov     rax, rdi
0x180012e6f  mov     rdi, [rsp+28h+arg_8]
0x180012e74  mov     rbx, [rsp+28h+arg_10]
0x180012e79  add     rsp, 20h
0x180012e7d  pop     r14
0x180012e7f  retn
0x180012e80  test    dword ptr [rbx+4], 200h
0x180012e87  jz      loc_180012D84
0x180012e8d  mov     r10, [rcx]
0x180012e90  xor     esi, esi
0x180012e92  mov     edi, esi
0x180012e94  test    rbx, rbx
0x180012e97  jz      short loc_180012E67
0x180012e99  cmp     byte ptr [rbx], 0B0h
0x180012e9c  jz      loc_1800130AE
0x180012ea2  mov     rax, rbx
0x180012ea5  movzx   eax, byte ptr [rax]
0x180012ea8  cmp     al, 0AAh
0x180012eaa  jz      loc_1800130B7
0x180012eb0  cmp     al, 0A8h
0x180012eb2  jnz     loc_180012FF0
0x180012eb8  movsx   rax, word ptr [rbx+30h]
0x180012ebd  test    ax, ax
0x180012ec0  js      short loc_180012E67
0x180012ec2  lea     rdx, [rax+rax*2]
0x180012ec6  mov     rax, [rbx+40h]
0x180012eca  mov     rcx, [rax+8]
0x180012ece  lea     rcx, [rcx+rdx*8]
0x180012ed2  call    sqlite3ColumnColl
0x180012ed7  movzx   edx, byte ptr [r10+64h]
0x180012edc  mov     r8, rax
0x180012edf  xor     r9d, r9d
0x180012ee2  mov     rcx, r10
0x180012ee5  call    sqlite3FindCollSeq
0x180012eea  mov     rdi, rax
0x180012eed  test    rax, rax
0x180012ef0  jz      loc_180012E67
0x180012ef6  cmp     [rax+18h], rsi
0x180012efa  jnz     loc_180012E67
0x180012f00  mov     rdx, [r14]
0x180012f03  mov     r8, rdi
0x180012f06  mov     r9, [rdi]
0x180012f09  mov     rcx, r14
0x180012f0c  movzx   edx, byte ptr [rdx+64h]
0x180012f10  call    sqlite3GetCollSeq
0x180012f15  test    rax, rax
0x180012f18  cmovz   rdi, rsi
0x180012f1c  jmp     loc_180012E67
0x180012f21  cmp     al, 4Eh ; 'N'
0x180012f23  jz      loc_180012DB0
0x180012f29  cmp     al, 24h ; '$'
0x180012f2b  jz      loc_180013189
0x180012f31  cmp     al, 0ADh
0x180012f33  jz      loc_180013189
0x180012f39  cmp     al, 0B1h
0x180012f3b  jz      loc_180013138
0x180012f41  cmp     al, 72h ; 'r'
0x180012f43  jz      loc_180013053
0x180012f49  mov     eax, [r8+4]
0x180012f4d  bt      eax, 9
0x180012f51  jnb     loc_180012DF4
0x180012f57  mov     rcx, [r8+10h]
0x180012f5b  test    rcx, rcx
0x180012f5e  jnz     loc_180013145
0x180012f64  mov     rdx, [r8+18h]
0x180012f68  bt      eax, 0Ch
0x180012f6c  jb      short loc_180012F81
0x180012f6e  mov     rcx, [r8+20h]
0x180012f72  test    rcx, rcx
0x180012f75  jz      short loc_180012F81
0x180012f77  cmp     [r10+67h], sil
0x180012f7b  jz      loc_18001315A
0x180012f81  mov     r8, rdx
0x180012f84  jmp     loc_180012D8B
0x180012f89  cmp     al, 4Eh ; 'N'
0x180012f8b  jz      loc_180012E23
0x180012f91  cmp     al, 24h ; '$'
0x180012f93  jz      loc_18001321E
0x180012f99  cmp     al, 0ADh
0x180012f9b  jz      loc_18001321E
0x180012fa1  cmp     al, 0B1h
0x180012fa3  jz      loc_1800131CD
0x180012fa9  cmp     al, 72h ; 'r'
0x180012fab  jz      loc_18001306C
0x180012fb1  mov     eax, [rbx+4]
0x180012fb4  bt      eax, 9
0x180012fb8  jnb     loc_180012E67
0x180012fbe  mov     rcx, [rbx+10h]
0x180012fc2  test    rcx, rcx
0x180012fc5  jnz     loc_1800131DA
0x180012fcb  mov     rdx, [rbx+18h]
0x180012fcf  bt      eax, 0Ch
0x180012fd3  jb      short loc_180012FE8
0x180012fd5  mov     rcx, [rbx+20h]
0x180012fd9  test    rcx, rcx
0x180012fdc  jz      short loc_180012FE8
0x180012fde  cmp     [r10+67h], sil
0x180012fe2  jz      loc_1800131EF
0x180012fe8  mov     rbx, rdx
0x180012feb  jmp     loc_180012DFF
0x180012ff0  cmp     al, 4Eh ; 'N'
0x180012ff2  jz      loc_180012EB8
0x180012ff8  cmp     al, 24h ; '$'
0x180012ffa  jz      loc_180013117
0x180013000  cmp     al, 0ADh
0x180013002  jz      loc_180013117
0x180013008  cmp     al, 0B1h
0x18001300a  jz      loc_1800130C6
0x180013010  cmp     al, 72h ; 'r'
0x180013012  jz      short loc_180013085
0x180013014  mov     eax, [rbx+4]
0x180013017  bt      eax, 9
0x18001301b  jnb     loc_180012E67
0x180013021  mov     rcx, [rbx+10h]
0x180013025  test    rcx, rcx
0x180013028  jnz     loc_1800130D3
0x18001302e  mov     rdx, [rbx+18h]
0x180013032  bt      eax, 0Ch
0x180013036  jb      short loc_18001304B
0x180013038  mov     rcx, [rbx+20h]
0x18001303c  test    rcx, rcx
0x18001303f  jz      short loc_18001304B
0x180013041  cmp     [r10+67h], sil
0x180013045  jz      loc_1800130E8
0x18001304b  mov     rbx, rdx
0x18001304e  jmp     loc_180012E94
0x180013053  mov     r9, [r8+8]
0x180013057  mov     rcx, r14
0x18001305a  movzx   edx, byte ptr [r10+64h]
0x18001305f  xor     r8d, r8d
0x180013062  call    sqlite3GetCollSeq
0x180013067  jmp     loc_180012DE2
0x18001306c  mov     r9, [rbx+8]
0x180013070  xor     r8d, r8d
0x180013073  movzx   edx, byte ptr [r10+64h]
0x180013078  mov     rcx, r14
0x18001307b  call    sqlite3GetCollSeq
0x180013080  jmp     loc_180012E55
0x180013085  mov     r9, [rbx+8]
0x180013089  xor     r8d, r8d
0x18001308c  movzx   edx, byte ptr [r10+64h]
0x180013091  mov     rcx, r14
0x180013094  call    sqlite3GetCollSeq
0x180013099  jmp     loc_180012EEA
0x18001309e  mov     rbx, [rsp+28h+arg_10]
0x1800130a3  add     rsp, 20h
0x1800130a7  pop     r14
0x1800130a9  jmp     sqlite3ExprCollSeq
0x1800130ae  lea     rax, [rbx+2]
0x1800130b2  jmp     loc_180012EA5
0x1800130b7  cmp     [rbx+40h], rsi
0x1800130bb  jnz     loc_180012EB8
0x1800130c1  jmp     loc_180013014
0x1800130c6  mov     rbx, [rbx+20h]
0x1800130ca  mov     rbx, [rbx+8]
0x1800130ce  jmp     loc_180012E94
0x1800130d3  test    dword ptr [rcx+4], 200h
0x1800130da  jz      loc_18001302E
0x1800130e0  mov     rbx, rcx
0x1800130e3  jmp     loc_180012E94
0x1800130e8  mov     r8d, esi
0x1800130eb  cmp     r8d, [rcx]
0x1800130ee  jge     loc_18001304B
0x1800130f4  movsxd  rax, r8d
0x1800130f7  shl     rax, 5
0x1800130fb  mov     r9, [rax+rcx+8]
0x180013100  test    dword ptr [r9+4], 200h
0x180013108  jnz     short loc_18001310F
0x18001310a  inc     r8d
0x18001310d  jmp     short loc_1800130EB
0x18001310f  mov     rdx, r9
0x180013112  jmp     loc_18001304B
0x180013117  mov     rbx, [rbx+10h]
0x18001311b  jmp     loc_180012E94
0x180013120  lea     rax, [r8+2]
0x180013124  jmp     loc_180012D9D
0x180013129  cmp     [r8+40h], rsi
0x18001312d  jnz     loc_180012DB0
0x180013133  jmp     loc_180012F49
0x180013138  mov     rax, [r8+20h]
0x18001313c  mov     r8, [rax+8]
0x180013140  jmp     loc_180012D8B
0x180013145  test    dword ptr [rcx+4], 200h
0x18001314c  jz      loc_180012F64
0x180013152  mov     r8, rcx
0x180013155  jmp     loc_180012D8B
0x18001315a  mov     r8d, esi
0x18001315d  cmp     r8d, [rcx]
0x180013160  jge     loc_180012F81
0x180013166  movsxd  rax, r8d
0x180013169  shl     rax, 5
0x18001316d  mov     r9, [rax+rcx+8]
0x180013172  test    dword ptr [r9+4], 200h
0x18001317a  jnz     short loc_180013181
0x18001317c  inc     r8d
0x18001317f  jmp     short loc_18001315D
0x180013181  mov     rdx, r9
0x180013184  jmp     loc_180012F81
0x180013189  mov     r8, [r8+10h]
0x18001318d  jmp     loc_180012D8B
0x180013192  mov     rdx, [r14]
0x180013195  mov     r8, rdi
0x180013198  mov     r9, [rdi]
0x18001319b  mov     rcx, r14
0x18001319e  movzx   edx, byte ptr [rdx+64h]
0x1800131a2  call    sqlite3GetCollSeq
0x1800131a7  test    rax, rax
0x1800131aa  jz      loc_180012DF9
0x1800131b0  jmp     loc_180012DF4
0x1800131b5  lea     rax, [rbx+2]
0x1800131b9  jmp     loc_180012E10
0x1800131be  cmp     [rbx+40h], rsi
0x1800131c2  jnz     loc_180012E23
0x1800131c8  jmp     loc_180012FB1
0x1800131cd  mov     rbx, [rbx+20h]
0x1800131d1  mov     rbx, [rbx+8]
0x1800131d5  jmp     loc_180012DFF
0x1800131da  test    dword ptr [rcx+4], 200h
0x1800131e1  jz      loc_180012FCB
0x1800131e7  mov     rbx, rcx
0x1800131ea  jmp     loc_180012DFF
0x1800131ef  mov     r8d, esi
0x1800131f2  cmp     r8d, [rcx]
0x1800131f5  jge     loc_180012FE8
  ... truncated ...
```
