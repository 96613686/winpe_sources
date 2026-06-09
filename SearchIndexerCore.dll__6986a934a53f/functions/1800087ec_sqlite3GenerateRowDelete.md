# sqlite3GenerateRowDelete

- ea: `0x1800087ec`
- end: `0x180008be2`
- name: `sqlite3GenerateRowDelete`
- size: `1014`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x180008c0c`
- `0x180019470`

## callees

- `0x1800087ec`
- `0x180008be8`
- `0x180009760`
- `0x180009ac0`
- `0x180009b98`
- `0x180009ccc`
- `0x18000a710`
- `0x1800151f0`
- `0x1800168c0`
- `0x18001c9b4`
- `0x18001e090`
- `0x18001e860`
- `0x180051e60`
- `0x18005d8a0`
- `0x18005e21c`
- `0x180070114`
- `0x180072bd8`
- `0x1800923ec`

## pseudocode

```c
__int64 __fastcall sqlite3GenerateRowDelete(
        __int64 a1,
        __int16 *a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        __int16 a7,
        char a8,
        unsigned __int8 a9,
        char a10,
        int a11)
{
  __int64 v11; // rbp
  int v12; // r14d
  int v15; // r12d
  int v18; // r13d
  __int64 v19; // rdx
  __int64 i; // rbx
  __int64 v22; // rax
  int v23; // ebx
  int v24; // eax
  int v25; // edx
  __int64 v26; // r8
  __int64 v27; // r9
  signed int v28; // ebx
  int v29; // r14d
  __int16 v30; // ax
  int v31; // ebx
  unsigned int v32; // [rsp+90h] [rbp+8h]
  int v33; // [rsp+98h] [rbp+10h]

  v11 = *(_QWORD *)(a1 + 16);
  v12 = -1;
  --*(_DWORD *)(a1 + 68);
  v15 = *((_DWORD *)a2 + 12) & 0x80;
  v32 = *(_DWORD *)(a1 + 68);
  if ( !a10 )
    sqlite3VdbeAddOp4Int(v11, v15 != 0 ? 28 : 31, a4, *(_DWORD *)(a1 + 68), a6, a7);
  if ( (unsigned int)sqlite3FkRequired(a1, a2, 0, 0) || (v18 = 0, a3) )
  {
    v23 = sqlite3TriggerColmask(a1, a3, 0, 0, 3, (__int64)a2, a9);
    v24 = sqlite3FkOldmask(a1, a2);
    v25 = *(_DWORD *)(a1 + 56);
    v33 = v24 | v23;
    v18 = v25 + 1;
    *(_DWORD *)(a1 + 56) = a2[27] + 1 + v25;
    sqlite3VdbeAddOp3(v11, 80, a6, v25 + 1, 0);
    v28 = 0;
    if ( a2[27] > 0 )
    {
      v29 = v33;
      do
      {
        if ( v33 == -1 || v28 <= 31 && _bittest(&v29, v28) )
        {
          v30 = sqlite3TableColumnToStorage(a2, (unsigned __int16)v28, v26, v27);
          sqlite3ExprCodeGetColumnOfTable(v11, (_DWORD)a2, a4, v28, v18 + v30 + 1);
        }
        ++v28;
      }
      while ( v28 < a2[27] );
      v12 = -1;
    }
    v31 = *(_DWORD *)(v11 + 144);
    sqlite3CodeRowTrigger(a1, a3, 128, 0, 1, (__int64)a2, v18, a9, v32);
    if ( v31 >= *(_DWORD *)(v11 + 144) )
      v12 = a11;
    else
      sqlite3VdbeAddOp4Int(v11, v15 != 0 ? 28 : 31, a4, v32, a6, a7);
    sqlite3FkCheck(a1, (_DWORD)a2, v18, 0, 0, 0);
  }
  else
  {
    v12 = a11;
  }
  if ( *((_BYTE *)a2 + 63) != 2 )
  {
    sqlite3GenerateRowIndexDelete(a1, (_DWORD)a2, a4, a5, 0, v12);
    sqlite3VdbeAddOp3(v11, 130, a4, a8 != 0, 0);
    if ( !*(_BYTE *)(a1 + 30) || *(_QWORD *)a2 && !(unsigned int)sqlite3StrICmp(*(_QWORD *)a2, "sqlite_stat1") )
      sqlite3VdbeAppendP4(v11, a2, 4294967291LL);
    if ( a10 )
      sqlite3VdbeChangeP5(v11, 4);
    if ( v12 >= 0 && v12 != a4 )
      sqlite3VdbeAddOp3(v11, 130, v12, 0, 0);
    v19 = 2;
    if ( a10 != 2 )
      LOWORD(v19) = 0;
    sqlite3VdbeChangeP5(v11, v19);
  }
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x4000LL) != 0 )
  {
    for ( i = *(_QWORD *)(findElementWithHash(*((_QWORD *)a2 + 12) + 80LL, *(_QWORD *)a2, 0) + 16);
          i;
          i = *(_QWORD *)(i + 24) )
    {
      v22 = fkActionTrigger(a1, a2, i, 0);
      if ( v22 )
        sqlite3CodeRowTriggerDirect(a1, v22, (_DWORD)a2, v18, 2, 0);
    }
  }
  if ( a3 )
    sqlite3CodeRowTrigger(a1, a3, 128, 0, 2, (__int64)a2, v18, a9, v32);
  return sqlite3VdbeResolveLabel(v11, v32);
}

```

## disassembly

```asm
0x1800087ec  mov     [rsp+arg_18], rbx
0x1800087f1  mov     [rsp+arg_10], r8
0x1800087f6  push    rbp
0x1800087f7  push    rsi
0x1800087f8  push    rdi
0x1800087f9  push    r12
0x1800087fb  push    r13
0x1800087fd  push    r14
0x1800087ff  push    r15
0x180008801  sub     rsp, 50h
0x180008805  mov     rbp, [rcx+10h]
0x180008809  or      r14d, 0FFFFFFFFh
0x18000880d  add     [rcx+44h], r14d
0x180008811  mov     rbx, r8
0x180008814  mov     r12d, [rdx+30h]
0x180008818  mov     r15d, r9d
0x18000881b  mov     r8d, [rcx+44h]
0x18000881f  and     r12d, 80h
0x180008826  cmp     [rsp+88h+arg_48], 0
0x18000882e  mov     rdi, rdx
0x180008831  mov     rsi, rcx
0x180008834  mov     [rsp+88h+arg_0], r8d
0x18000883c  jz      loc_1800089D4
0x180008842  xor     r9d, r9d
0x180008845  xor     r8d, r8d
0x180008848  mov     rdx, rdi
0x18000884b  mov     rcx, rsi
0x18000884e  call    sqlite3FkRequired
0x180008853  test    eax, eax
0x180008855  jnz     loc_180008A0B
0x18000885b  xor     r13d, r13d
0x18000885e  test    rbx, rbx
0x180008861  jnz     loc_180008A0B
0x180008867  mov     r14d, [rsp+88h+arg_50]
0x18000886f  xor     r12d, r12d
0x180008872  cmp     byte ptr [rdi+3Fh], 2
0x180008876  jz      loc_180008915
0x18000887c  mov     r9d, [rsp+88h+arg_20]
0x180008884  mov     r8d, r15d
0x180008887  mov     dword ptr [rsp+88h+var_60], r14d
0x18000888c  mov     rdx, rdi
0x18000888f  mov     rcx, rsi
0x180008892  mov     [rsp+88h+var_68], r12
0x180008897  call    sqlite3GenerateRowIndexDelete
0x18000889c  cmp     [rsp+88h+arg_38], r12b
0x1800088a4  mov     r9d, r12d
0x1800088a7  mov     r8d, r15d
0x1800088aa  mov     dword ptr [rsp+88h+var_68], r12d
0x1800088af  setnz   r9b
0x1800088b3  mov     edx, 82h
0x1800088b8  mov     rcx, rbp
0x1800088bb  call    sqlite3VdbeAddOp3
0x1800088c0  cmp     [rsi+1Eh], r12b
0x1800088c4  jnz     loc_1800089AF
0x1800088ca  mov     r8d, 0FFFFFFFBh
0x1800088d0  mov     rdx, rdi
0x1800088d3  mov     rcx, rbp
0x1800088d6  call    sqlite3VdbeAppendP4
0x1800088db  mov     bl, [rsp+88h+arg_48]
0x1800088e2  test    bl, bl
0x1800088e4  jz      short loc_1800088F3
0x1800088e6  mov     edx, 4
0x1800088eb  mov     rcx, rbp
0x1800088ee  call    sqlite3VdbeChangeP5
0x1800088f3  test    r14d, r14d
0x1800088f6  js      short loc_180008901
0x1800088f8  cmp     r14d, r15d
0x1800088fb  jnz     loc_180008B86
0x180008901  mov     edx, 2
0x180008906  mov     rcx, rbp
0x180008909  cmp     bl, dl
0x18000890b  cmovnz  dx, r12w
0x180008910  call    sqlite3VdbeChangeP5
0x180008915  mov     rax, [rsi]
0x180008918  mov     ecx, [rax+30h]
0x18000891b  bt      rcx, 0Eh
0x180008920  jb      short loc_180008959
0x180008922  mov     rdx, [rsp+88h+arg_10]
0x18000892a  test    rdx, rdx
0x18000892d  jnz     loc_180008BA3
0x180008933  mov     edx, [rsp+88h+arg_0]
0x18000893a  mov     rcx, rbp
0x18000893d  mov     rbx, [rsp+88h+arg_18]
0x180008945  add     rsp, 50h
0x180008949  pop     r15
0x18000894b  pop     r14
0x18000894d  pop     r13
0x18000894f  pop     r12
0x180008951  pop     rdi
0x180008952  pop     rsi
0x180008953  pop     rbp
0x180008954  jmp     sqlite3VdbeResolveLabel
0x180008959  mov     rcx, [rdi+60h]
0x18000895d  xor     r8d, r8d
0x180008960  mov     rdx, [rdi]
0x180008963  add     rcx, 50h ; 'P'
0x180008967  call    findElementWithHash
0x18000896c  mov     rbx, [rax+10h]
0x180008970  test    rbx, rbx
0x180008973  jz      short loc_180008922
0x180008975  xor     r9d, r9d
0x180008978  mov     r8, rbx
0x18000897b  mov     rdx, rdi
0x18000897e  mov     rcx, rsi
0x180008981  call    fkActionTrigger
0x180008986  test    rax, rax
0x180008989  jz      short loc_1800089A9
0x18000898b  mov     dword ptr [rsp+88h+var_60], r12d
0x180008990  mov     r9d, r13d
0x180008993  mov     r8, rdi
0x180008996  mov     dword ptr [rsp+88h+var_68], 2
0x18000899e  mov     rdx, rax
0x1800089a1  mov     rcx, rsi
0x1800089a4  call    sqlite3CodeRowTriggerDirect
0x1800089a9  mov     rbx, [rbx+18h]
0x1800089ad  jmp     short loc_180008970
0x1800089af  mov     rcx, [rdi]
0x1800089b2  test    rcx, rcx
0x1800089b5  jz      loc_1800088DB
0x1800089bb  lea     rdx, aSqliteStat1; "sqlite_stat1"
0x1800089c2  call    sqlite3StrICmp
0x1800089c7  test    eax, eax
0x1800089c9  jz      loc_1800088CA
0x1800089cf  jmp     loc_1800088DB
0x1800089d4  movsx   ecx, [rsp+88h+arg_30]
0x1800089dc  mov     eax, r12d
0x1800089df  neg     eax
0x1800089e1  mov     dword ptr [rsp+88h+var_60], ecx
0x1800089e5  mov     eax, [rsp+88h+arg_28]
0x1800089ec  mov     r9d, r8d
0x1800089ef  sbb     edx, edx
0x1800089f1  mov     dword ptr [rsp+88h+var_68], eax
0x1800089f5  and     edx, 0FFFFFFFDh
0x1800089f8  mov     r8d, r15d
0x1800089fb  add     edx, 1Fh
0x1800089fe  mov     rcx, rbp
0x180008a01  call    sqlite3VdbeAddOp4Int
0x180008a06  jmp     loc_180008842
0x180008a0b  movzx   eax, [rsp+88h+arg_40]
0x180008a13  xor     r9d, r9d
0x180008a16  mov     [rsp+88h+var_58], eax
0x180008a1a  xor     r8d, r8d
0x180008a1d  mov     [rsp+88h+var_60], rdi
0x180008a22  mov     rdx, rbx
0x180008a25  mov     rcx, rsi
0x180008a28  mov     dword ptr [rsp+88h+var_68], 3
0x180008a30  call    sqlite3TriggerColmask
0x180008a35  mov     rdx, rdi
0x180008a38  mov     rcx, rsi
0x180008a3b  mov     ebx, eax
0x180008a3d  call    sqlite3FkOldmask
0x180008a42  mov     edx, [rsi+38h]
0x180008a45  or      ebx, eax
0x180008a47  movsx   ecx, word ptr [rdi+36h]
0x180008a4b  mov     r8d, [rsp+88h+arg_28]
0x180008a53  inc     ecx
0x180008a55  mov     [rsp+88h+arg_8], ebx
0x180008a5c  lea     r13d, [rdx+1]
0x180008a60  mov     dword ptr [rsp+88h+var_68], 0
0x180008a68  add     edx, ecx
0x180008a6a  mov     r9d, r13d
0x180008a6d  mov     [rsi+38h], edx
0x180008a70  mov     rcx, rbp
0x180008a73  mov     edx, 50h ; 'P'
0x180008a78  call    sqlite3VdbeAddOp3
0x180008a7d  xor     eax, eax
0x180008a7f  xor     ebx, ebx
0x180008a81  cmp     ax, [rdi+36h]
0x180008a85  jge     short loc_180008AD4
0x180008a87  mov     r14d, [rsp+88h+arg_8]
0x180008a8f  cmp     r14d, 0FFFFFFFFh
0x180008a93  jz      short loc_180008AA0
0x180008a95  cmp     ebx, 1Fh
0x180008a98  jg      short loc_180008AC6
0x180008a9a  bt      r14d, ebx
0x180008a9e  jnb     short loc_180008AC6
0x180008aa0  movzx   edx, bx
0x180008aa3  mov     rcx, rdi
0x180008aa6  call    sqlite3TableColumnToStorage
0x180008aab  cwde
0x180008aac  mov     r9d, ebx
0x180008aaf  inc     eax
0x180008ab1  mov     r8d, r15d
0x180008ab4  add     eax, r13d
0x180008ab7  mov     rdx, rdi
0x180008aba  mov     rcx, rbp
0x180008abd  mov     dword ptr [rsp+88h+var_68], eax
0x180008ac1  call    sqlite3ExprCodeGetColumnOfTable
0x180008ac6  movsx   eax, word ptr [rdi+36h]
0x180008aca  inc     ebx
0x180008acc  cmp     ebx, eax
0x180008ace  jl      short loc_180008A8F
0x180008ad0  or      r14d, 0FFFFFFFFh
0x180008ad4  mov     eax, [rsp+88h+arg_0]
0x180008adb  xor     r9d, r9d
0x180008ade  mov     rdx, [rsp+88h+arg_10]
0x180008ae6  mov     r8d, 80h
0x180008aec  mov     ebx, [rbp+90h]
0x180008af2  mov     rcx, rsi
0x180008af5  mov     [rsp+88h+var_48], eax
0x180008af9  movzx   eax, [rsp+88h+arg_40]
0x180008b01  mov     [rsp+88h+var_50], eax
0x180008b05  mov     [rsp+88h+var_58], r13d
0x180008b0a  mov     [rsp+88h+var_60], rdi
0x180008b0f  mov     dword ptr [rsp+88h+var_68], 1
0x180008b17  call    sqlite3CodeRowTrigger
0x180008b1c  cmp     ebx, [rbp+90h]
0x180008b22  jge     short loc_180008B5B
0x180008b24  movsx   eax, [rsp+88h+arg_30]
0x180008b2c  neg     r12d
0x180008b2f  mov     r9d, [rsp+88h+arg_0]
0x180008b37  mov     r8d, r15d
0x180008b3a  sbb     edx, edx
0x180008b3c  mov     dword ptr [rsp+88h+var_60], eax
0x180008b40  mov     eax, [rsp+88h+arg_28]
0x180008b47  and     edx, 0FFFFFFFDh
0x180008b4a  add     edx, 1Fh
0x180008b4d  mov     dword ptr [rsp+88h+var_68], eax
0x180008b51  mov     rcx, rbp
0x180008b54  call    sqlite3VdbeAddOp4Int
0x180008b59  jmp     short loc_180008B63
0x180008b5b  mov     r14d, [rsp+88h+arg_50]
0x180008b63  xor     r12d, r12d
0x180008b66  xor     r9d, r9d
0x180008b69  mov     dword ptr [rsp+88h+var_60], r12d
0x180008b6e  mov     r8d, r13d
0x180008b71  mov     rdx, rdi
0x180008b74  mov     [rsp+88h+var_68], r12
0x180008b79  mov     rcx, rsi
0x180008b7c  call    sqlite3FkCheck
0x180008b81  jmp     loc_180008872
0x180008b86  xor     r9d, r9d
0x180008b89  mov     dword ptr [rsp+88h+var_68], r12d
0x180008b8e  mov     r8d, r14d
0x180008b91  mov     edx, 82h
0x180008b96  mov     rcx, rbp
0x180008b99  call    sqlite3VdbeAddOp3
0x180008b9e  jmp     loc_180008901
0x180008ba3  movzx   eax, [rsp+88h+arg_40]
0x180008bab  xor     r9d, r9d
0x180008bae  mov     ecx, [rsp+88h+arg_0]
0x180008bb5  mov     r8d, 80h
0x180008bbb  mov     [rsp+88h+var_48], ecx
0x180008bbf  mov     rcx, rsi
0x180008bc2  mov     [rsp+88h+var_50], eax
0x180008bc6  mov     [rsp+88h+var_58], r13d
0x180008bcb  mov     [rsp+88h+var_60], rdi
0x180008bd0  mov     dword ptr [rsp+88h+var_68], 2
0x180008bd8  call    sqlite3CodeRowTrigger
0x180008bdd  jmp     loc_180008933
```
