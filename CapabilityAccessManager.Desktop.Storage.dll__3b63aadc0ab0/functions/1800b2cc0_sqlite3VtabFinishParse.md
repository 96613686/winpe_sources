# sqlite3VtabFinishParse

- ea: `0x1800b2cc0`
- end: `0x1800b3061`
- name: `sqlite3VtabFinishParse`
- size: `929`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x1800d8b00`

## callees

- `0x180005980`
- `0x180023bf0`
- `0x18003c1a0`
- `0x18004dba0`
- `0x18006b630`
- `0x1800838f0`
- `0x180088530`
- `0x180088ea0`
- `0x180089210`
- `0x1800a2f60`
- `0x1800a3040`
- `0x1800a3370`
- `0x1800a3b40`
- `0x1800aea10`
- `0x1800b2cc0`
- `0x1800e4dce`
- `0x18010d010`

## string_xrefs

- `0x1800b2d4c`: `CREATE VIRTUAL TABLE %T`
- `0x1800b2d94`: `UPDATE %Q.sqlite_master SET type='table', name=%Q, tbl_name=%Q, rootpage=0, sql=%Q WHERE rowid=#%d`

## pseudocode

```c
void __fastcall sqlite3VtabFinishParse(__int64 *a1, _DWORD *a2)
{
  int *v2; // r15
  __int64 v5; // r14
  _DWORD *v6; // r8
  __int64 *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rbx
  unsigned int v11; // edi
  __int64 v12; // rdx
  __int64 v13; // rbp
  __int64 v14; // rax
  unsigned int v15; // ebx
  __int64 v16; // r13
  __int64 v17; // rdx
  __int64 *v18; // r12
  __int64 v19; // rax
  size_t v20; // rbp
  _QWORD *i; // rdi
  __int64 v22; // rbx
  __int64 v23; // r8
  int v24; // eax
  _BYTE *v25; // r9
  _BYTE *v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-48h]
  int v28; // [rsp+30h] [rbp-38h]
  __int64 v29; // [rsp+70h] [rbp+8h]

  v2 = (int *)a1[43];
  if ( v2 )
  {
    v5 = *a1;
    addArgumentToVtab(a1);
    a1[47] = 0;
    if ( v2[16] >= 1 )
    {
      if ( !*(_BYTE *)(v5 + 197) )
      {
        v6 = a1 + 33;
        v7 = a1;
        if ( a1[21] )
          v7 = (__int64 *)a1[21];
        *((_BYTE *)v7 + 33) = 1;
        if ( a2 )
          *((_DWORD *)a1 + 68) = *a2 + a2[2] - *v6;
        v8 = sqlite3MPrintf(v5, "CREATE VIRTUAL TABLE %T", v6);
        v9 = *((_QWORD *)v2 + 12);
        v10 = (_QWORD *)v8;
        v11 = -32768;
        if ( v9 )
        {
          v12 = *(_QWORD *)(v5 + 32);
          v11 = 0;
          if ( *(_QWORD *)(v12 + 24) != v9 )
          {
            do
              ++v11;
            while ( *(_QWORD *)(32LL * (int)v11 + v12 + 24) != v9 );
          }
        }
        v28 = *((_DWORD *)a1 + 32);
        v27 = *(_QWORD *)v2;
        sqlite3NestedParse(
          a1,
          "UPDATE %Q.sqlite_master SET type='table', name=%Q, tbl_name=%Q, rootpage=0, sql=%Q WHERE rowid=#%d",
          *(_QWORD *)(32LL * (int)v11 + *(_QWORD *)(v5 + 32)));
        v13 = a1[2];
        if ( !v13 )
        {
          if ( !a1[21] && (*(_BYTE *)(*a1 + 96) & 8) == 0 )
            *((_BYTE *)a1 + 35) = 1;
          v13 = sqlite3VdbeCreate(a1);
        }
        sqlite3ChangeCookie(a1, v11);
        sqlite3VdbeAddOp0(v13, 166);
        v14 = sqlite3MPrintf(v5, "name=%Q AND sql=%Q", *(_QWORD *)v2, v10);
        sqlite3VdbeAddParseSchemaOp(v13, v11, v14, 0, v27, (_DWORD)v10, v28);
        if ( !v10 )
          goto LABEL_25;
        if ( (unsigned __int64)v10 < *(_QWORD *)(v5 + 496) )
        {
          if ( (unsigned __int64)v10 >= *(_QWORD *)(v5 + 480) )
          {
            *v10 = *(_QWORD *)(v5 + 472);
            *(_QWORD *)(v5 + 472) = v10;
LABEL_25:
            v15 = ++*((_DWORD *)a1 + 14);
            sqlite3VdbeLoadString(v13, v15, *(_QWORD *)v2);
            sqlite3VdbeAddOp2(v13, 171, v11, v15);
            return;
          }
          if ( (unsigned __int64)v10 >= *(_QWORD *)(v5 + 488) )
          {
            *v10 = *(_QWORD *)(v5 + 456);
            *(_QWORD *)(v5 + 456) = v10;
            goto LABEL_25;
          }
        }
        if ( *(_QWORD *)(v5 + 776) )
          measureAllocationSize(v5, v10);
        else
          sqlite3_free(v10);
        goto LABEL_25;
      }
      v16 = *((_QWORD *)v2 + 12);
      v29 = *(_QWORD *)v2;
      v18 = *(__int64 **)(findElementWithHash(v5 + 552, **((_QWORD **)v2 + 9), 0) + 16);
      if ( v18 )
      {
        v19 = *v18;
        if ( *v18 )
        {
          if ( *(int *)v19 >= 3 && *(_QWORD *)(v19 + 184) )
          {
            if ( *(_QWORD *)v2 )
              v20 = strlen_0(*(const char **)v2) & 0x3FFFFFFF;
            else
              LODWORD(v20) = 0;
            for ( i = *(_QWORD **)(*((_QWORD *)v2 + 12) + 16LL); i; i = (_QWORD *)*i )
            {
              v22 = i[2];
              if ( *(_BYTE *)(v22 + 63) || (*(_DWORD *)(v22 + 48) & 0x1000) != 0 )
                continue;
              v23 = *(_QWORD *)v2;
              if ( *(_QWORD *)v22 )
              {
                if ( !v23 )
                  continue;
                LODWORD(v17) = v20;
                v25 = *(_BYTE **)v22;
                if ( (_DWORD)v20 )
                {
                  while ( 1 )
                  {
                    v17 = (unsigned int)(v17 - 1);
                    if ( !*v25
                      || *((_BYTE *)qword_180114680 + (unsigned __int8)*v25) != *((_BYTE *)qword_180114680
                                                                                + *(unsigned __int8 *)v23) )
                    {
                      break;
                    }
                    ++v25;
                    ++v23;
                    if ( (int)v17 <= 0 )
                      goto LABEL_43;
                  }
                }
                else
                {
LABEL_43:
                  v17 = (unsigned int)(v17 - 1);
                }
                if ( (int)v17 < 0 )
                {
LABEL_47:
                  v26 = (_BYTE *)(*(_QWORD *)v22 + (unsigned int)v20);
                  if ( *v26 == 95
                    && (*(unsigned int (__fastcall **)(_BYTE *, __int64, __int64))(*v18 + 184))(v26 + 1, v17, v23) )
                  {
                    *(_DWORD *)(v22 + 48) |= 0x1000u;
                  }
                  continue;
                }
                v24 = *((unsigned __int8 *)qword_180114680 + (unsigned __int8)*v25)
                    - *((unsigned __int8 *)qword_180114680 + *(unsigned __int8 *)v23);
              }
              else
              {
                v23 = -v23;
                v24 = -(v23 != 0);
              }
              if ( !v24 )
                goto LABEL_47;
            }
          }
        }
      }
      if ( sqlite3HashInsert(v16 + 8, v29, v2) )
        sqlite3OomFault(v5);
      else
        a1[43] = 0;
    }
  }
}

```

## disassembly

```asm
0x1800b2cc0  push    rbx
0x1800b2cc2  push    rsi
0x1800b2cc3  push    r15
0x1800b2cc5  sub     rsp, 50h
0x1800b2cc9  mov     r15, [rcx+158h]
0x1800b2cd0  mov     rbx, rdx
0x1800b2cd3  mov     rsi, rcx
0x1800b2cd6  test    r15, r15
0x1800b2cd9  jz      loc_1800B3058
0x1800b2cdf  mov     [rsp+68h+var_28], r14
0x1800b2ce4  mov     r14, [rcx]
0x1800b2ce7  call    addArgumentToVtab
0x1800b2cec  mov     qword ptr [rsi+178h], 0
0x1800b2cf7  cmp     dword ptr [r15+40h], 1
0x1800b2cfc  jl      loc_1800B3053
0x1800b2d02  cmp     byte ptr [r14+0C5h], 0
0x1800b2d0a  mov     [rsp+68h+arg_8], rbp
0x1800b2d0f  mov     [rsp+68h+arg_10], rdi
0x1800b2d17  jnz     loc_1800B2EBB
0x1800b2d1d  mov     rax, [rsi+0A8h]
0x1800b2d24  lea     r8, [rsi+108h]
0x1800b2d2b  test    rax, rax
0x1800b2d2e  mov     rcx, rsi
0x1800b2d31  cmovnz  rcx, rax
0x1800b2d35  mov     byte ptr [rcx+21h], 1
0x1800b2d39  test    rbx, rbx
0x1800b2d3c  jz      short loc_1800B2D4C
0x1800b2d3e  mov     eax, [rbx+8]
0x1800b2d41  sub     eax, [r8]
0x1800b2d44  add     eax, [rbx]
0x1800b2d46  mov     [rsi+110h], eax
0x1800b2d4c  lea     rdx, aCreateVirtualT; "CREATE VIRTUAL TABLE %T"
0x1800b2d53  mov     rcx, r14
0x1800b2d56  call    sqlite3MPrintf
0x1800b2d5b  mov     rcx, [r15+60h]
0x1800b2d5f  mov     rbx, rax
0x1800b2d62  mov     edi, 0FFFF8000h
0x1800b2d67  test    rcx, rcx
0x1800b2d6a  jz      short loc_1800B2D90
0x1800b2d6c  mov     rdx, [r14+20h]
0x1800b2d70  xor     edi, edi
0x1800b2d72  cmp     [rdx+18h], rcx
0x1800b2d76  jz      short loc_1800B2D90
0x1800b2d78  nop     dword ptr [rax+rax+00000000h]
0x1800b2d80  inc     edi
0x1800b2d82  movsxd  rax, edi
0x1800b2d85  shl     rax, 5
0x1800b2d89  cmp     [rax+rdx+18h], rcx
0x1800b2d8e  jnz     short loc_1800B2D80
0x1800b2d90  mov     r8, [r14+20h]
0x1800b2d94  lea     rdx, aUpdateQSqliteM; "UPDATE %Q.sqlite_master SET type='table"...
0x1800b2d9b  mov     eax, [rsi+80h]
0x1800b2da1  mov     r9, [r15]
0x1800b2da4  mov     [rsp+68h+var_38], eax
0x1800b2da8  movsxd  rcx, edi
0x1800b2dab  shl     rcx, 5
0x1800b2daf  mov     [rsp+68h+var_40], rbx
0x1800b2db4  mov     [rsp+68h+var_48], r9
0x1800b2db9  mov     r8, [rcx+r8]
0x1800b2dbd  mov     rcx, rsi
0x1800b2dc0  call    sqlite3NestedParse
0x1800b2dc5  mov     rbp, [rsi+10h]
0x1800b2dc9  test    rbp, rbp
0x1800b2dcc  jnz     short loc_1800B2DEF
0x1800b2dce  cmp     [rsi+0A8h], rbp
0x1800b2dd5  jnz     short loc_1800B2DE4
0x1800b2dd7  mov     rax, [rsi]
0x1800b2dda  test    byte ptr [rax+60h], 8
0x1800b2dde  jnz     short loc_1800B2DE4
0x1800b2de0  mov     byte ptr [rsi+23h], 1
0x1800b2de4  mov     rcx, rsi
0x1800b2de7  call    sqlite3VdbeCreate
0x1800b2dec  mov     rbp, rax
0x1800b2def  mov     edx, edi
0x1800b2df1  mov     rcx, rsi
0x1800b2df4  call    sqlite3ChangeCookie
0x1800b2df9  mov     edx, 0A6h
0x1800b2dfe  mov     rcx, rbp
0x1800b2e01  call    sqlite3VdbeAddOp0
0x1800b2e06  mov     r8, [r15]
0x1800b2e09  lea     rdx, aNameQAndSqlQ; "name=%Q AND sql=%Q"
0x1800b2e10  mov     r9, rbx
0x1800b2e13  mov     rcx, r14
0x1800b2e16  call    sqlite3MPrintf
0x1800b2e1b  xor     r9d, r9d
0x1800b2e1e  mov     r8, rax
0x1800b2e21  mov     edx, edi
0x1800b2e23  mov     rcx, rbp
0x1800b2e26  call    sqlite3VdbeAddParseSchemaOp
0x1800b2e2b  test    rbx, rbx
0x1800b2e2e  jz      short loc_1800B2E90
0x1800b2e30  cmp     rbx, [r14+1F0h]
0x1800b2e37  jnb     short loc_1800B2E71
0x1800b2e39  cmp     rbx, [r14+1E0h]
0x1800b2e40  jb      short loc_1800B2E55
0x1800b2e42  mov     rax, [r14+1D8h]
0x1800b2e49  mov     [rbx], rax
0x1800b2e4c  mov     [r14+1D8h], rbx
0x1800b2e53  jmp     short loc_1800B2E90
0x1800b2e55  cmp     rbx, [r14+1E8h]
0x1800b2e5c  jb      short loc_1800B2E71
0x1800b2e5e  mov     rax, [r14+1C8h]
0x1800b2e65  mov     [rbx], rax
0x1800b2e68  mov     [r14+1C8h], rbx
0x1800b2e6f  jmp     short loc_1800B2E90
0x1800b2e71  cmp     qword ptr [r14+308h], 0
0x1800b2e79  jz      short loc_1800B2E88
0x1800b2e7b  mov     rdx, rbx
0x1800b2e7e  mov     rcx, r14
0x1800b2e81  call    measureAllocationSize
0x1800b2e86  jmp     short loc_1800B2E90
0x1800b2e88  mov     rcx, rbx
0x1800b2e8b  call    sqlite3_free
0x1800b2e90  inc     dword ptr [rsi+38h]
0x1800b2e93  mov     rcx, rbp
0x1800b2e96  mov     ebx, [rsi+38h]
0x1800b2e99  mov     edx, ebx
0x1800b2e9b  mov     r8, [r15]
0x1800b2e9e  call    sqlite3VdbeLoadString
0x1800b2ea3  mov     r9d, ebx
0x1800b2ea6  mov     r8d, edi
0x1800b2ea9  mov     edx, 0ABh
0x1800b2eae  mov     rcx, rbp
0x1800b2eb1  call    sqlite3VdbeAddOp2
0x1800b2eb6  jmp     loc_1800B3046
0x1800b2ebb  mov     rdx, [r15+48h]
0x1800b2ebf  lea     rcx, [r14+228h]
0x1800b2ec6  mov     rax, [r15]
0x1800b2ec9  xor     r8d, r8d
0x1800b2ecc  mov     [rsp+68h+arg_18], r12
0x1800b2ed4  mov     [rsp+68h+var_20], r13
0x1800b2ed9  mov     rdx, [rdx]
0x1800b2edc  mov     r13, [r15+60h]
0x1800b2ee0  mov     [rsp+68h+arg_0], rax
0x1800b2ee5  call    findElementWithHash
0x1800b2eea  mov     r12, [rax+10h]
0x1800b2eee  test    r12, r12
0x1800b2ef1  jz      loc_1800B300E
0x1800b2ef7  mov     rax, [r12]
0x1800b2efb  test    rax, rax
0x1800b2efe  jz      loc_1800B300E
0x1800b2f04  cmp     dword ptr [rax], 3
0x1800b2f07  jl      loc_1800B300E
0x1800b2f0d  cmp     qword ptr [rax+0B8h], 0
0x1800b2f15  jz      loc_1800B300E
0x1800b2f1b  mov     rcx, [r15]; Str
0x1800b2f1e  test    rcx, rcx
0x1800b2f21  jnz     short loc_1800B2F27
0x1800b2f23  xor     ebp, ebp
0x1800b2f25  jmp     short loc_1800B2F35
0x1800b2f27  call    strlen_0
0x1800b2f2c  mov     rbp, rax
0x1800b2f2f  and     ebp, 3FFFFFFFh
0x1800b2f35  mov     rcx, [r15+60h]
0x1800b2f39  mov     rdi, [rcx+10h]
0x1800b2f3d  test    rdi, rdi
0x1800b2f40  jz      loc_1800B300E
0x1800b2f46  lea     r11, qword_180114680
0x1800b2f4d  nop     dword ptr [rax]
0x1800b2f50  mov     rbx, [rdi+10h]
0x1800b2f54  cmp     byte ptr [rbx+3Fh], 0
0x1800b2f58  jnz     loc_1800B3002
0x1800b2f5e  test    dword ptr [rbx+30h], 1000h
0x1800b2f65  jnz     loc_1800B3002
0x1800b2f6b  mov     r10, [rbx]
0x1800b2f6e  mov     r8, [r15]
0x1800b2f71  test    r10, r10
0x1800b2f74  jnz     short loc_1800B2F7D
0x1800b2f76  neg     r8
0x1800b2f79  sbb     eax, eax
0x1800b2f7b  jmp     short loc_1800B2FCF
0x1800b2f7d  test    r8, r8
0x1800b2f80  jz      loc_1800B3002
0x1800b2f86  mov     edx, ebp
0x1800b2f88  mov     r9, r10
0x1800b2f8b  test    ebp, ebp
0x1800b2f8d  jz      short loc_1800B2FB5
0x1800b2f8f  nop
0x1800b2f90  movzx   eax, byte ptr [r9]
0x1800b2f94  dec     edx
0x1800b2f96  test    al, al
0x1800b2f98  jz      short loc_1800B2FB7
0x1800b2f9a  mov     ecx, eax
0x1800b2f9c  movzx   eax, byte ptr [r8]
0x1800b2fa0  movzx   eax, byte ptr [rax+r11]
0x1800b2fa5  cmp     [rcx+r11], al
0x1800b2fa9  jnz     short loc_1800B2FB7
0x1800b2fab  inc     r9
0x1800b2fae  inc     r8
0x1800b2fb1  test    edx, edx
0x1800b2fb3  jg      short loc_1800B2F90
0x1800b2fb5  dec     edx
0x1800b2fb7  test    edx, edx
0x1800b2fb9  js      short loc_1800B2FD3
0x1800b2fbb  movzx   eax, byte ptr [r8]
0x1800b2fbf  movzx   ecx, byte ptr [rax+r11]
0x1800b2fc4  movzx   eax, byte ptr [r9]
0x1800b2fc8  movzx   eax, byte ptr [rax+r11]
0x1800b2fcd  sub     eax, ecx
0x1800b2fcf  test    eax, eax
0x1800b2fd1  jnz     short loc_1800B3002
0x1800b2fd3  mov     ecx, ebp
0x1800b2fd5  add     rcx, r10
0x1800b2fd8  cmp     byte ptr [rcx], 5Fh ; '_'
0x1800b2fdb  jnz     short loc_1800B3002
0x1800b2fdd  mov     rax, [r12]
0x1800b2fe1  inc     rcx
0x1800b2fe4  mov     rax, [rax+0B8h]
0x1800b2feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2ff0  lea     r11, qword_180114680
0x1800b2ff7  test    eax, eax
0x1800b2ff9  jz      short loc_1800B3002
0x1800b2ffb  or      dword ptr [rbx+30h], 1000h
0x1800b3002  mov     rdi, [rdi]
0x1800b3005  test    rdi, rdi
0x1800b3008  jnz     loc_1800B2F50
0x1800b300e  mov     rdx, [rsp+68h+arg_0]
0x1800b3013  lea     rcx, [r13+8]
0x1800b3017  mov     r8, r15
0x1800b301a  call    sqlite3HashInsert
0x1800b301f  mov     r13, [rsp+68h+var_20]
0x1800b3024  mov     r12, [rsp+68h+arg_18]
0x1800b302c  test    rax, rax
0x1800b302f  jz      short loc_1800B303B
0x1800b3031  mov     rcx, r14
0x1800b3034  call    sqlite3OomFault
0x1800b3039  jmp     short loc_1800B3046
0x1800b303b  mov     qword ptr [rsi+158h], 0
0x1800b3046  mov     rdi, [rsp+68h+arg_10]
0x1800b304e  mov     rbp, [rsp+68h+arg_8]
0x1800b3053  mov     r14, [rsp+68h+var_28]
0x1800b3058  add     rsp, 50h
0x1800b305c  pop     r15
0x1800b305e  pop     rsi
0x1800b305f  pop     rbx
0x1800b3060  retn
```
