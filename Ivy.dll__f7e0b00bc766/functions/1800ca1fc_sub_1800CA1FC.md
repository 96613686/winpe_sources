# sub_1800CA1FC

- ea: `0x1800ca1fc`
- end: `0x1800ca5ba`
- name: `sub_1800CA1FC`
- size: `958`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: ``

## callers

- `0x1800c635c`
- `0x1800c66c8`
- `0x1800c6958`

## callees

- `0x180011ac4`
- `0x180011ae8`
- `0x1800130ec`
- `0x180013898`
- `0x180013d28`
- `0x1800c6d8c`
- `0x1800c6f6c`
- `0x1800c71b0`
- `0x1800c73e8`
- `0x1800c7658`
- `0x1800c78a8`
- `0x1800c797c`
- `0x1800c7a88`
- `0x1800c7b60`
- `0x1800c7c44`
- `0x1800c7d04`
- `0x1800c7e1c`
- `0x1800c7f7c`
- `0x1800ca1fc`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800ca591`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800ca591`

## string_xrefs

- `0x1800ca5ab`: `unknown token`

## pseudocode

```c
__int64 __fastcall sub_1800CA1FC(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rax
  unsigned __int16 v7; // bp
  unsigned __int16 v8; // di
  __int64 v9; // r8
  char v10; // r10
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  __int16 v15; // ax
  int v16; // r9d
  unsigned __int64 v17; // rdx
  _QWORD *v18; // rcx
  bool v19; // cc
  wchar_t *v20; // rdx
  __int16 v21; // r9
  unsigned __int64 v22; // rdx
  __int16 v23; // ax
  int v24; // r9d
  int v25; // ecx
  int v26; // ecx
  __int64 v27; // rcx
  __int16 v28; // ax
  int v29; // r9d
  __int16 v30; // ax
  int v31; // r9d
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  int v37; // ecx
  __int64 v38; // rcx
  int v39; // ecx
  const char *v40; // rax

  *(_OWORD *)(a3 + 48) = *(_OWORD *)(*(_QWORD *)(a2 + 104) + 16LL);
  *(_BYTE *)(a3 + 64) = *(_BYTE *)(*(_QWORD *)(a2 + 104) + 53LL);
  v6 = *(_QWORD *)(a2 + 104);
  v7 = *(_WORD *)(v6 + 36);
  v8 = *(_WORD *)(v6 + 34);
  if ( v8 < v7 )
  {
    while ( 1 )
    {
      v9 = *(_QWORD *)(a1 + 72);
      if ( v8 >= (unsigned __int64)((*(_QWORD *)(a1 + 80) - v9) >> 3) )
        invoke_watson(0, 0, 0, 0, 0);
      v10 = *(_BYTE *)(v9 + 8LL * v8 + 6);
      if ( (v10 & 4) != 0 && fabs(*(double *)(a2 + 56)) <= 0.000000001
        || (v10 & 8) != 0 && fabs(*(double *)(a2 + 40)) <= 0.000000001 )
      {
        goto LABEL_62;
      }
      v11 = *(unsigned __int8 *)(v9 + 8LL * v8);
      if ( (unsigned int)v11 > 0xA )
        break;
      if ( (_DWORD)v11 == 10 )
      {
        sub_1800C797C(v11, a2, *(unsigned __int16 *)(v9 + 8LL * v8 + 4));
        goto LABEL_62;
      }
      if ( (unsigned int)v11 > 5 )
      {
        v25 = v11 - 6;
        if ( v25 )
        {
          v26 = v25 - 1;
          if ( v26 )
          {
            v27 = (unsigned int)(v26 - 1);
            if ( (_DWORD)v27 )
            {
              if ( (_DWORD)v27 != 1 )
                goto LABEL_65;
              sub_1800C78A8(v27, a2, *(unsigned __int16 *)(v9 + 8LL * v8 + 4));
            }
            else
            {
              sub_1800C7658(v27, a2);
            }
          }
          else
          {
            v28 = *(_WORD *)(v9 + 8LL * v8 + 4);
            v29 = *(unsigned __int16 *)(v9 + 8LL * v8 + 2);
            LOBYTE(v9) = *(_BYTE *)(v9 + 8LL * v8 + 6);
            sub_1800C73E8(0, a2, v9, v29, v28);
          }
        }
        else
        {
          v30 = *(_WORD *)(v9 + 8LL * v8 + 4);
          v31 = *(unsigned __int16 *)(v9 + 8LL * v8 + 2);
          LOBYTE(v9) = *(_BYTE *)(v9 + 8LL * v8 + 6);
          sub_1800C71B0(0, a2, v9, v31, v30);
        }
        goto LABEL_62;
      }
      if ( (_DWORD)v11 == 5 )
      {
        v23 = *(_WORD *)(v9 + 8LL * v8 + 4);
        v24 = *(unsigned __int16 *)(v9 + 8LL * v8 + 2);
        LOBYTE(v9) = *(_BYTE *)(v9 + 8LL * v8 + 6);
        sub_1800C6F6C(5, a2, v9, v24, v23);
        goto LABEL_62;
      }
      if ( !*(_BYTE *)(v9 + 8LL * v8) )
      {
        v21 = *(_WORD *)(v9 + 8LL * v8 + 2);
        goto LABEL_25;
      }
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            if ( v14 != 1 )
              goto LABEL_65;
            v15 = *(_WORD *)(v9 + 8LL * v8 + 4);
            v16 = *(unsigned __int16 *)(v9 + 8LL * v8 + 2);
            LOBYTE(v9) = *(_BYTE *)(v9 + 8LL * v8 + 6);
            sub_1800C6D8C(1, a2, v9, v16, v15);
          }
          goto LABEL_62;
        }
        v17 = *(_QWORD *)(a2 + 88);
        v18 = (_QWORD *)(a2 + 72);
        if ( v17 < *(_QWORD *)(a2 + 96) )
        {
          v19 = *(_QWORD *)(a2 + 96) <= 7u;
          *(_QWORD *)(a2 + 88) = v17 + 1;
          if ( !v19 )
            v18 = (_QWORD *)*v18;
          *(_DWORD *)((char *)v18 + 2 * v17) = 32;
          goto LABEL_62;
        }
        goto LABEL_21;
      }
      v20 = *(wchar_t **)(a2 + 8);
      if ( v20 )
        goto LABEL_23;
LABEL_62:
      if ( ++v8 >= v7 )
        return sub_180013D28(a3 + 16, a2 + 72);
    }
    v32 = (unsigned int)(v11 - 11);
    if ( !(_DWORD)v32 )
    {
      sub_1800C7A88(v32, a2, *(unsigned __int16 *)(v9 + 8LL * v8 + 4));
      goto LABEL_62;
    }
    v33 = (unsigned int)(v32 - 1);
    if ( !(_DWORD)v33 )
    {
      sub_1800C7B60(v33, a2, *(unsigned __int16 *)(v9 + 8LL * v8 + 4));
      goto LABEL_62;
    }
    v34 = (unsigned int)(v33 - 1);
    if ( !(_DWORD)v34 )
    {
      sub_1800C7C44(v34, a2, *(unsigned __int16 *)(v9 + 8LL * v8 + 4));
      goto LABEL_62;
    }
    v35 = (unsigned int)(v34 - 1);
    if ( !(_DWORD)v35 )
    {
      sub_1800C7D04(v35, a2, *(unsigned __int16 *)(v9 + 8LL * v8 + 4));
      goto LABEL_62;
    }
    v36 = (unsigned int)(v35 - 1);
    if ( !(_DWORD)v36 )
    {
      sub_1800C7E1C(v36, a2);
      goto LABEL_62;
    }
    v37 = v36 - 1;
    if ( !v37 )
    {
      if ( *(_WORD *)(a2 + 24) < 0xCu )
      {
        v40 = "A";
        v20 = L"AM";
      }
      else
      {
        v40 = "P";
        v20 = L"PM";
      }
      if ( (v10 & 0x20) != 0 )
        v20 = (wchar_t *)v40;
LABEL_23:
      sub_1800130EC((void *)(a2 + 72), v20);
      goto LABEL_62;
    }
    v38 = (unsigned int)(v37 - 1);
    if ( !(_DWORD)v38 )
    {
      sub_1800C7F7C(v38, a2, *(unsigned __int16 *)(v9 + 8LL * v8 + 2), *(unsigned __int16 *)(v9 + 8LL * v8 + 4));
      goto LABEL_62;
    }
    v39 = v38 - 1;
    if ( v39 )
    {
      if ( v39 != 1 )
      {
LABEL_65:
        sub_180011AE8(508646419, &qword_1801AB2B8);
        sub_180011AC4(508646419, "unknown token");
      }
      v21 = *(_WORD *)(*(_QWORD *)(a2 + 32) + 20LL);
    }
    else
    {
      v21 = *(_WORD *)(*(_QWORD *)(a2 + 32) + 16LL);
    }
LABEL_25:
    v22 = *(_QWORD *)(a2 + 88);
    v18 = (_QWORD *)(a2 + 72);
    if ( v22 < *(_QWORD *)(a2 + 96) )
    {
      *(_QWORD *)(a2 + 88) = v22 + 1;
      if ( *(_QWORD *)(a2 + 96) > 7u )
        v18 = (_QWORD *)*v18;
      *((_WORD *)v18 + v22) = v21;
      *((_WORD *)v18 + v22 + 1) = 0;
      goto LABEL_62;
    }
LABEL_21:
    sub_180013898(v18);
    goto LABEL_62;
  }
  return sub_180013D28(a3 + 16, a2 + 72);
}

```

## disassembly

```asm
0x1800ca1fc  mov     rax, rsp
0x1800ca1ff  mov     [rax+8], rbx
0x1800ca203  mov     [rax+10h], rbp
0x1800ca207  mov     [rax+18h], rsi
0x1800ca20b  mov     [rax+20h], rdi
0x1800ca20f  push    r12
0x1800ca211  push    r14
0x1800ca213  push    r15
0x1800ca215  sub     rsp, 40h
0x1800ca219  movaps  xmmword ptr [rax-28h], xmm7
0x1800ca21d  mov     rsi, r8
0x1800ca220  mov     rax, [rdx+68h]
0x1800ca224  mov     rbx, rdx
0x1800ca227  mov     r14, rcx
0x1800ca22a  movups  xmm0, xmmword ptr [rax+10h]
0x1800ca22e  movdqu  xmmword ptr [r8+30h], xmm0
0x1800ca234  mov     rax, [rdx+68h]
0x1800ca238  mov     r9b, [rax+35h]
0x1800ca23c  mov     [r8+40h], r9b
0x1800ca240  mov     rax, [rdx+68h]
0x1800ca244  movzx   ebp, word ptr [rax+24h]
0x1800ca248  movzx   edi, word ptr [rax+22h]
0x1800ca24c  cmp     di, bp
0x1800ca24f  jnb     loc_1800CA552
0x1800ca255  movsd   xmm7, cs:qword_1801BB3E0
0x1800ca25d  xor     r15d, r15d
0x1800ca260  lea     r12d, [r15+20h]
0x1800ca264  mov     r8, [r14+48h]
0x1800ca268  mov     rax, [r14+50h]
0x1800ca26c  sub     rax, r8
0x1800ca26f  movzx   edx, di
0x1800ca272  sar     rax, 3
0x1800ca276  cmp     rdx, rax
0x1800ca279  jnb     loc_1800CA582
0x1800ca27f  movzx   r10d, byte ptr [r8+rdx*8+6]
0x1800ca285  test    r10b, 4
0x1800ca289  jz      short loc_1800CA2A1
0x1800ca28b  movsd   xmm0, qword ptr [rbx+38h]
0x1800ca290  andps   xmm0, cs:xmmword_1801BBA10
0x1800ca297  comisd  xmm7, xmm0
0x1800ca29b  jnb     loc_1800CA546
0x1800ca2a1  test    r10b, 8
0x1800ca2a5  jz      short loc_1800CA2BD
0x1800ca2a7  movsd   xmm0, qword ptr [rbx+28h]
0x1800ca2ac  andps   xmm0, cs:xmmword_1801BBA10
0x1800ca2b3  comisd  xmm7, xmm0
0x1800ca2b7  jnb     loc_1800CA546
0x1800ca2bd  movzx   ecx, byte ptr [r8+rdx*8]
0x1800ca2c2  cmp     ecx, 0Ah
0x1800ca2c5  ja      loc_1800CA45A
0x1800ca2cb  jz      loc_1800CA447
0x1800ca2d1  cmp     ecx, 5
0x1800ca2d4  ja      loc_1800CA3CD
0x1800ca2da  jz      loc_1800CA3AC
0x1800ca2e0  test    ecx, ecx
0x1800ca2e2  jz      loc_1800CA376
0x1800ca2e8  sub     ecx, 1
0x1800ca2eb  jz      short loc_1800CA35B
0x1800ca2ed  sub     ecx, 1
0x1800ca2f0  jz      short loc_1800CA325
0x1800ca2f2  sub     ecx, 1
0x1800ca2f5  jz      loc_1800CA546
0x1800ca2fb  cmp     ecx, 1
0x1800ca2fe  jnz     loc_1800CA598
0x1800ca304  movzx   eax, word ptr [r8+rdx*8+4]
0x1800ca30a  movzx   r9d, word ptr [r8+rdx*8+2]
0x1800ca310  mov     r8b, r10b
0x1800ca313  mov     rdx, rbx
0x1800ca316  mov     word ptr [rsp+58h+Reserved], ax
0x1800ca31b  call    sub_1800C6D8C
0x1800ca320  jmp     loc_1800CA546
0x1800ca325  mov     rdx, [rbx+58h]
0x1800ca329  lea     rcx, [rbx+48h]; Src
0x1800ca32d  cmp     rdx, [rbx+60h]
0x1800ca331  jnb     short loc_1800CA34E
0x1800ca333  cmp     qword ptr [rbx+60h], 7
0x1800ca338  lea     rax, [rdx+1]
0x1800ca33c  mov     [rcx+10h], rax
0x1800ca340  jbe     short loc_1800CA345
0x1800ca342  mov     rcx, [rcx]
0x1800ca345  mov     [rcx+rdx*2], r12d
0x1800ca349  jmp     loc_1800CA546
0x1800ca34e  mov     r9d, r12d
0x1800ca351  call    sub_180013898
0x1800ca356  jmp     loc_1800CA546
0x1800ca35b  mov     rdx, [rbx+8]; void *
0x1800ca35f  test    rdx, rdx
0x1800ca362  jz      loc_1800CA546
0x1800ca368  lea     rcx, [rbx+48h]; Src
0x1800ca36c  call    sub_1800130EC
0x1800ca371  jmp     loc_1800CA546
0x1800ca376  movzx   r9d, word ptr [r8+rdx*8+2]
0x1800ca37c  mov     rdx, [rbx+58h]
0x1800ca380  lea     rcx, [rbx+48h]
0x1800ca384  cmp     rdx, [rbx+60h]
0x1800ca388  jnb     short loc_1800CA351
0x1800ca38a  lea     rax, [rdx+1]
0x1800ca38e  mov     [rcx+10h], rax
0x1800ca392  cmp     qword ptr [rbx+60h], 7
0x1800ca397  jbe     short loc_1800CA39C
0x1800ca399  mov     rcx, [rcx]
0x1800ca39c  mov     [rcx+rdx*2], r9w
0x1800ca3a1  mov     [rcx+rdx*2+2], r15w
0x1800ca3a7  jmp     loc_1800CA546
0x1800ca3ac  movzx   eax, word ptr [r8+rdx*8+4]
0x1800ca3b2  movzx   r9d, word ptr [r8+rdx*8+2]
0x1800ca3b8  mov     r8b, r10b
0x1800ca3bb  mov     rdx, rbx
0x1800ca3be  mov     word ptr [rsp+58h+Reserved], ax
0x1800ca3c3  call    sub_1800C6F6C
0x1800ca3c8  jmp     loc_1800CA546
0x1800ca3cd  sub     ecx, 6
0x1800ca3d0  jz      short loc_1800CA426
0x1800ca3d2  sub     ecx, 1
0x1800ca3d5  jz      short loc_1800CA405
0x1800ca3d7  sub     ecx, 1
0x1800ca3da  jz      short loc_1800CA3F8
0x1800ca3dc  cmp     ecx, 1
0x1800ca3df  jnz     loc_1800CA598
0x1800ca3e5  movzx   r8d, word ptr [r8+rdx*8+4]
0x1800ca3eb  mov     rdx, rbx
0x1800ca3ee  call    sub_1800C78A8
0x1800ca3f3  jmp     loc_1800CA546
0x1800ca3f8  mov     rdx, rbx
0x1800ca3fb  call    sub_1800C7658
0x1800ca400  jmp     loc_1800CA546
0x1800ca405  movzx   eax, word ptr [r8+rdx*8+4]
0x1800ca40b  movzx   r9d, word ptr [r8+rdx*8+2]
0x1800ca411  mov     r8b, r10b
0x1800ca414  mov     rdx, rbx
0x1800ca417  mov     word ptr [rsp+58h+Reserved], ax
0x1800ca41c  call    sub_1800C73E8
0x1800ca421  jmp     loc_1800CA546
0x1800ca426  movzx   eax, word ptr [r8+rdx*8+4]
0x1800ca42c  movzx   r9d, word ptr [r8+rdx*8+2]
0x1800ca432  mov     r8b, r10b
0x1800ca435  mov     rdx, rbx
0x1800ca438  mov     word ptr [rsp+58h+Reserved], ax
0x1800ca43d  call    sub_1800C71B0
0x1800ca442  jmp     loc_1800CA546
0x1800ca447  movzx   r8d, word ptr [r8+rdx*8+4]
0x1800ca44d  mov     rdx, rbx
0x1800ca450  call    sub_1800C797C
0x1800ca455  jmp     loc_1800CA546
0x1800ca45a  sub     ecx, 0Bh
0x1800ca45d  jz      loc_1800CA538
0x1800ca463  sub     ecx, 1
0x1800ca466  jz      loc_1800CA528
0x1800ca46c  sub     ecx, 1
0x1800ca46f  jz      loc_1800CA518
0x1800ca475  sub     ecx, 1
0x1800ca478  jz      loc_1800CA508
0x1800ca47e  sub     ecx, 1
0x1800ca481  jz      short loc_1800CA4FE
0x1800ca483  sub     ecx, 1
0x1800ca486  jz      short loc_1800CA4CD
0x1800ca488  sub     ecx, 1
0x1800ca48b  jz      short loc_1800CA4B7
0x1800ca48d  sub     ecx, 1
0x1800ca490  jz      short loc_1800CA4A9
0x1800ca492  cmp     ecx, 1
0x1800ca495  jnz     loc_1800CA598
0x1800ca49b  mov     rax, [rbx+20h]
0x1800ca49f  movzx   r9d, word ptr [rax+14h]
0x1800ca4a4  jmp     loc_1800CA37C
0x1800ca4a9  mov     rax, [rbx+20h]
0x1800ca4ad  movzx   r9d, word ptr [rax+10h]
0x1800ca4b2  jmp     loc_1800CA37C
0x1800ca4b7  movzx   r9d, word ptr [r8+rdx*8+4]
0x1800ca4bd  movzx   r8d, word ptr [r8+rdx*8+2]
0x1800ca4c3  mov     rdx, rbx
0x1800ca4c6  call    sub_1800C7F7C
0x1800ca4cb  jmp     short loc_1800CA546
0x1800ca4cd  cmp     word ptr [rbx+18h], 0Ch
0x1800ca4d2  jb      short loc_1800CA4E4
0x1800ca4d4  lea     rax, aP; "P"
0x1800ca4db  lea     rdx, aPm; "PM"
0x1800ca4e2  jmp     short loc_1800CA4F2
0x1800ca4e4  lea     rax, aA; "A"
0x1800ca4eb  lea     rdx, aAm; "AM"
0x1800ca4f2  test    r12b, r10b
0x1800ca4f5  cmovnz  rdx, rax
0x1800ca4f9  jmp     loc_1800CA368
0x1800ca4fe  mov     rdx, rbx
0x1800ca501  call    sub_1800C7E1C
0x1800ca506  jmp     short loc_1800CA546
0x1800ca508  movzx   r8d, word ptr [r8+rdx*8+4]
0x1800ca50e  mov     rdx, rbx
0x1800ca511  call    sub_1800C7D04
0x1800ca516  jmp     short loc_1800CA546
0x1800ca518  movzx   r8d, word ptr [r8+rdx*8+4]
0x1800ca51e  mov     rdx, rbx
0x1800ca521  call    sub_1800C7C44
0x1800ca526  jmp     short loc_1800CA546
0x1800ca528  movzx   r8d, word ptr [r8+rdx*8+4]
0x1800ca52e  mov     rdx, rbx
0x1800ca531  call    sub_1800C7B60
0x1800ca536  jmp     short loc_1800CA546
0x1800ca538  movzx   r8d, word ptr [r8+rdx*8+4]
0x1800ca53e  mov     rdx, rbx
0x1800ca541  call    sub_1800C7A88
0x1800ca546  inc     di
0x1800ca549  cmp     di, bp
0x1800ca54c  jb      loc_1800CA264
0x1800ca552  lea     rdx, [rbx+48h]
0x1800ca556  lea     rcx, [rsi+10h]
0x1800ca55a  mov     rbx, [rsp+58h+arg_0]
0x1800ca55f  mov     rbp, [rsp+58h+arg_8]
0x1800ca564  mov     rsi, [rsp+58h+arg_10]
0x1800ca569  mov     rdi, [rsp+58h+arg_18]
0x1800ca56e  movaps  xmm7, [rsp+58h+var_28]
0x1800ca573  add     rsp, 40h
0x1800ca577  pop     r15
0x1800ca579  pop     r14
0x1800ca57b  pop     r12
0x1800ca57d  jmp     sub_180013D28
0x1800ca582  xor     r9d, r9d; LineNo
0x1800ca585  mov     [rsp+58h+Reserved], r15; Reserved
0x1800ca58a  xor     r8d, r8d; FileName
0x1800ca58d  xor     edx, edx; FunctionName
0x1800ca58f  xor     ecx, ecx; Expression
0x1800ca591  call    cs:_invoke_watson
0x1800ca598  mov     ebx, 1E515413h
0x1800ca59d  lea     rdx, qword_1801AB2B8
0x1800ca5a4  mov     ecx, ebx
0x1800ca5a6  call    sub_180011AE8
0x1800ca5ab  lea     rdx, aUnknownToken; "unknown token"
0x1800ca5b2  mov     ecx, ebx
0x1800ca5b4  call    sub_180011AC4
```
