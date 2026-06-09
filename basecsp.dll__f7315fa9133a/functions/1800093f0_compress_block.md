# compress_block

- ea: `0x1800093f0`
- end: `0x180009818`
- name: `compress_block`
- size: `1064`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008a80`

## callees

- `0x1800093f0`

## pseudocode

```c
__int64 __fastcall compress_block(__int64 a1, __int64 a2, __int64 a3)
{
  int *v3; // r11
  __int64 v4; // r10
  _DWORD *v5; // rax
  __int64 v6; // r14
  _QWORD *v7; // rdi
  __int64 v8; // r12
  __int64 v10; // r9
  _QWORD *v11; // r13
  _DWORD *v12; // rsi
  int v13; // r8d
  __int64 v14; // r14
  int v15; // edx
  __int64 v16; // r14
  __int64 v17; // rbp
  int v18; // ecx
  unsigned __int16 v19; // r9
  int v20; // edi
  __int16 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rax
  int v24; // edx
  __int64 v25; // r13
  __int64 v26; // rcx
  unsigned __int16 v27; // r9
  int v28; // esi
  __int16 v29; // dx
  __int64 v30; // rcx
  char v31; // dl
  int v32; // r8d
  __int16 v33; // r9
  int v34; // r12d
  unsigned __int16 v35; // bp
  __int16 v36; // si
  int v37; // r8d
  char v38; // cl
  __int16 v39; // bp
  __int16 v40; // si
  unsigned int v41; // ecx
  int v42; // r12d
  unsigned __int16 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int16 v46; // r8
  _QWORD *v47; // r13
  int v48; // r12d
  _DWORD *v49; // rdx
  __int16 v50; // r9
  int v51; // ebp
  unsigned __int16 v52; // si
  __int16 v53; // r8
  int v54; // r8d
  unsigned __int16 v55; // r9
  int v56; // ebx
  int v57; // ecx
  __int16 v58; // dx
  __int64 result; // rax
  _QWORD *v60; // [rsp+0h] [rbp-58h]
  int v61; // [rsp+60h] [rbp+8h]
  __int64 v62; // [rsp+60h] [rbp+8h]

  v3 = (int *)(a1 + 5904);
  v4 = a1 + 5900;
  v5 = (_DWORD *)(a1 + 40);
  v6 = 0;
  v7 = (_QWORD *)(a1 + 16);
  v8 = a2;
  if ( *(_DWORD *)(a1 + 5876) )
  {
    while ( 1 )
    {
      v10 = *(_QWORD *)(a1 + 5864);
      v11 = v7;
      v60 = v7;
      v12 = v5;
      v13 = *(unsigned __int8 *)(v6 + v10);
      v14 = (unsigned int)(v6 + 1);
      v15 = *(unsigned __int8 *)(v14 + v10);
      v16 = (unsigned int)(v14 + 1);
      v61 = v13 + (v15 << 8);
      v17 = *(unsigned __int8 *)(v16 + v10);
      v6 = (unsigned int)(v16 + 1);
      if ( !v61 )
      {
        v18 = *v3;
        v19 = *(_WORD *)(v8 + 4 * v17);
        v20 = *(unsigned __int16 *)(v8 + 4 * v17 + 2);
        v21 = *(_WORD *)v4 | (v19 << *v3);
        if ( *v3 <= 16 - v20 )
        {
          *(_WORD *)v4 = v21;
          *v3 = v18 + v20;
          v5 = (_DWORD *)(a1 + 40);
          v7 = (_QWORD *)(a1 + 16);
        }
        else
        {
          v22 = *(unsigned int *)(a1 + 40);
          v23 = *(_QWORD *)(a1 + 16);
          *(_WORD *)v4 = v21;
          *(_BYTE *)(v22 + v23) = v21;
          *(_BYTE *)((unsigned int)++*(_DWORD *)(a1 + 40) + *(_QWORD *)(a1 + 16)) = *(_BYTE *)(v4 + 1);
          LODWORD(v23) = *v3;
          LOBYTE(v22) = 16 - *v3;
          ++*(_DWORD *)(a1 + 40);
          v24 = v20 + v23 - 16;
          v5 = (_DWORD *)(a1 + 40);
          v7 = (_QWORD *)(a1 + 16);
          *(_WORD *)v4 = v19 >> v22;
          *v3 = v24;
        }
        goto LABEL_26;
      }
      v25 = (unsigned __int8)length_code[v17];
      v26 = (unsigned int)(v25 + 257);
      v27 = *(_WORD *)(v8 + 4 * v26);
      v28 = *(unsigned __int16 *)(v8 + 4 * v26 + 2);
      v29 = *(_WORD *)v4 | (v27 << *v3);
      if ( *v3 <= 16 - v28 )
      {
        v32 = v28 + *v3;
        v33 = *(_WORD *)v4 | (v27 << *v3);
      }
      else
      {
        v30 = *v7;
        *(_WORD *)v4 = v29;
        *(_BYTE *)((unsigned int)(*v5)++ + v30) = v29;
        *(_BYTE *)((unsigned int)*v5 + *v7) = *(_BYTE *)(v4 + 1);
        LODWORD(v30) = *v3;
        v31 = 16 - *v3;
        ++*v5;
        v32 = v28 + v30 - 16;
        v33 = v27 >> v31;
      }
      *(_WORD *)v4 = v33;
      *v3 = v32;
      v34 = dword_18002F470[v25];
      if ( v34 )
      {
        v35 = v17 - word_18002FAE0[2 * v25];
        v36 = v33 | (v35 << v32);
        *(_WORD *)v4 = v36;
        if ( v32 <= 16 - v34 )
        {
          v32 += v34;
          v39 = v36;
        }
        else
        {
          *(_BYTE *)((unsigned int)(*v5)++ + *v7) = v36;
          *(_BYTE *)((unsigned int)*v5 + *v7) = *(_BYTE *)(v4 + 1);
          v37 = *v3;
          v38 = 16 - *v3;
          ++*v5;
          v39 = v35 >> v38;
          v32 = v34 + v37 - 16;
          *(_WORD *)v4 = v39;
        }
        *v3 = v32;
      }
      else
      {
        v39 = v33;
      }
      v40 = v61 - 1;
      v41 = v61 - 1;
      if ( (unsigned int)(v61 - 1) >= 0x100 )
        v41 = (v41 >> 7) + 256;
      v62 = 4LL * (unsigned __int8)dist_code[v41];
      v42 = *(unsigned __int16 *)(v62 + a3 + 2);
      v43 = *(_WORD *)(v62 + a3);
      if ( v32 <= 16 - v42 )
      {
        v48 = v32 + v42;
        v50 = v39 | (v43 << v32);
        v49 = (_DWORD *)(a1 + 40);
        v47 = (_QWORD *)(a1 + 16);
      }
      else
      {
        v44 = (unsigned int)*v5;
        v45 = *v7;
        v46 = v39 | (v43 << v32);
        *(_WORD *)v4 = v46;
        v47 = v7;
        *(_BYTE *)(v44 + v45) = v46;
        *(_BYTE *)((unsigned int)++*v5 + *v7) = *(_BYTE *)(v4 + 1);
        LODWORD(v45) = *v3;
        v48 = *v3 + v42 - 16;
        ++*v5;
        v49 = v5;
        v50 = v43 >> (16 - v45);
      }
      *(_WORD *)v4 = v50;
      *v3 = v48;
      v51 = *(_DWORD *)((char *)&qword_18002F490[12] + v62);
      if ( !v51 )
        goto LABEL_24;
      v52 = v40 - *(_WORD *)((char *)qword_18002FB60 + v62);
      v53 = v50 | (v52 << v48);
      *(_WORD *)v4 = v53;
      if ( v48 <= 16 - v51 )
        break;
      v11 = v7;
      *(_BYTE *)((unsigned int)(*v5)++ + *v7) = v53;
      *(_BYTE *)((unsigned int)*v5 + *v7) = *(_BYTE *)(v4 + 1);
      v54 = *v3;
      ++*v5;
      *(_WORD *)v4 = v52 >> (16 - v54);
      *v3 = v54 + v51 - 16;
      v12 = v5;
LABEL_25:
      v8 = a2;
LABEL_26:
      if ( (unsigned int)v6 >= *(_DWORD *)(a1 + 5876) )
        goto LABEL_29;
    }
    *v3 = v48 + v51;
LABEL_24:
    v12 = v5;
    v7 = v47;
    v11 = v60;
    v5 = v49;
    goto LABEL_25;
  }
  v12 = (_DWORD *)(a1 + 40);
  v11 = (_QWORD *)(a1 + 16);
LABEL_29:
  v55 = *(_WORD *)(v8 + 1024);
  v56 = *(unsigned __int16 *)(v8 + 1026);
  v57 = *v3;
  v58 = *(_WORD *)v4 | (v55 << *v3);
  *(_WORD *)v4 = v58;
  if ( v57 <= 16 - v56 )
  {
    result = (unsigned int)(v57 + v56);
    *v3 = result;
  }
  else
  {
    *(_BYTE *)((unsigned int)(*v12)++ + *v11) = v58;
    *(_BYTE *)((unsigned int)*v12 + *v11) = *(_BYTE *)(v4 + 1);
    result = (unsigned int)*v3;
    ++*v12;
    *(_WORD *)v4 = v55 >> (16 - result);
    *v3 = v56 + result - 16;
  }
  return result;
}

```

## disassembly

```asm
0x1800093f0  mov     [rsp+arg_10], r8
0x1800093f5  mov     [rsp+arg_8], rdx
0x1800093fa  push    rbx
0x1800093fb  push    rsi
0x1800093fc  push    r13
0x1800093fe  push    r15
0x180009400  sub     rsp, 38h
0x180009404  mov     [rsp+58h+var_30], rdi
0x180009409  lea     r11, [rcx+1710h]
0x180009410  mov     [rsp+58h+var_38], r12
0x180009415  lea     r10, [rcx+170Ch]
0x18000941c  mov     [rsp+58h+var_40], r14
0x180009421  lea     rax, [rcx+28h]
0x180009425  xor     r14d, r14d
0x180009428  lea     rdi, [rcx+10h]
0x18000942c  mov     r12, rdx
0x18000942f  mov     rbx, rcx
0x180009432  mov     r15d, 10h
0x180009438  cmp     [rcx+16F4h], r14d
0x18000943f  jz      loc_18000977E
0x180009445  mov     [rsp+58h+var_28], rbp
0x18000944a  nop     word ptr [rax+rax+00h]
0x180009450  mov     r9, [rbx+16E8h]
0x180009457  mov     r13, rdi
0x18000945a  mov     [rsp+58h+var_58], rdi
0x18000945e  mov     rsi, rax
0x180009461  mov     [rsp+58h+arg_18], rax
0x180009466  movzx   r8d, byte ptr [r14+r9]
0x18000946b  inc     r14d
0x18000946e  movzx   edx, byte ptr [r14+r9]
0x180009473  inc     r14d
0x180009476  shl     edx, 8
0x180009479  add     edx, r8d
0x18000947c  mov     dword ptr [rsp+58h+arg_0], edx
0x180009480  movzx   ebp, byte ptr [r14+r9]
0x180009485  inc     r14d
0x180009488  test    edx, edx
0x18000948a  jnz     loc_180009517
0x180009490  mov     ecx, [r11]
0x180009493  mov     eax, r15d
0x180009496  movzx   r9d, word ptr [r12+rbp*4]
0x18000949b  movzx   edi, word ptr [r12+rbp*4+2]
0x1800094a1  movzx   r8d, r9w
0x1800094a5  shl     r8w, cl
0x1800094a9  sub     eax, edi
0x1800094ab  or      r8w, [r10]
0x1800094af  cmp     ecx, eax
0x1800094b1  jle     short loc_1800094FC
0x1800094b3  mov     ecx, [rbx+28h]
0x1800094b6  mov     rax, [rbx+10h]
0x1800094ba  mov     [r10], r8w
0x1800094be  mov     [rcx+rax], r8b
0x1800094c2  inc     dword ptr [rbx+28h]
0x1800094c5  mov     edx, [rbx+28h]
0x1800094c8  movzx   eax, byte ptr [r10+1]
0x1800094cd  mov     rcx, [rbx+10h]
0x1800094d1  mov     [rdx+rcx], al
0x1800094d4  mov     ecx, r15d
0x1800094d7  mov     eax, [r11]
0x1800094da  sub     cl, al
0x1800094dc  inc     dword ptr [rbx+28h]
0x1800094df  lea     edx, [rax-10h]
0x1800094e2  add     edx, edi
0x1800094e4  lea     rax, [rbx+28h]
0x1800094e8  shr     r9w, cl
0x1800094ec  lea     rdi, [rbx+10h]
0x1800094f0  mov     [r10], r9w
0x1800094f4  mov     [r11], edx
0x1800094f7  jmp     loc_18000976A
0x1800094fc  lea     edx, [rcx+rdi]
0x1800094ff  mov     [r10], r8w
0x180009503  mov     [r11], edx
0x180009506  lea     rax, [rbx+28h]
0x18000950a  movzx   r9d, r8w
0x18000950e  lea     rdi, [rbx+10h]
0x180009512  jmp     loc_18000976A
0x180009517  mov     r8d, [r11]
0x18000951a  lea     rcx, __ImageBase
0x180009521  movzx   r13d, ds:rva _length_code[rcx+rbp]
0x18000952a  lea     ecx, [r13+101h]
0x180009531  movzx   r9d, word ptr [r12+rcx*4]
0x180009536  movzx   esi, word ptr [r12+rcx*4+2]
0x18000953c  movzx   edx, r9w
0x180009540  mov     ecx, r8d
0x180009543  shl     dx, cl
0x180009546  mov     ecx, r15d
0x180009549  or      dx, [r10]
0x18000954d  sub     ecx, esi
0x18000954f  cmp     r8d, ecx
0x180009552  jle     short loc_180009590
0x180009554  mov     rcx, [rdi]
0x180009557  movzx   r8d, dx
0x18000955b  mov     [r10], dx
0x18000955f  mov     edx, [rax]
0x180009561  mov     [rdx+rcx], r8b
0x180009565  inc     dword ptr [rax]
0x180009567  mov     r8d, [rax]
0x18000956a  mov     rdx, [rdi]
0x18000956d  movzx   ecx, byte ptr [r10+1]
0x180009572  mov     [r8+rdx], cl
0x180009576  mov     edx, r15d
0x180009579  mov     ecx, [r11]
0x18000957c  sub     dl, cl
0x18000957e  inc     dword ptr [rax]
0x180009580  lea     r8d, [rcx-10h]
0x180009584  movzx   ecx, dl
0x180009587  add     r8d, esi
0x18000958a  shr     r9w, cl
0x18000958e  jmp     short loc_180009597
0x180009590  add     r8d, esi
0x180009593  movzx   r9d, dx
0x180009597  mov     rcx, r13
0x18000959a  mov     [r10], r9w
0x18000959e  lea     r13, __ImageBase
0x1800095a5  mov     [r11], r8d
0x1800095a8  mov     r12d, ds:rva dword_18002F470[r13+rcx*4]
0x1800095b0  test    r12d, r12d
0x1800095b3  jz      short loc_18000961D
0x1800095b5  sub     bp, ds:rva word_18002FAE0[r13+rcx*4]
0x1800095be  mov     ecx, r8d
0x1800095c1  movzx   esi, bp
0x1800095c4  shl     si, cl
0x1800095c7  mov     ecx, r15d
0x1800095ca  or      si, r9w
0x1800095ce  sub     ecx, r12d
0x1800095d1  mov     [r10], si
0x1800095d5  cmp     r8d, ecx
0x1800095d8  jle     short loc_180009612
0x1800095da  mov     edx, [rax]
0x1800095dc  mov     rcx, [rdi]
0x1800095df  mov     [rdx+rcx], sil
0x1800095e3  inc     dword ptr [rax]
0x1800095e5  mov     r8d, [rax]
0x1800095e8  movzx   ecx, byte ptr [r10+1]
0x1800095ed  mov     rdx, [rdi]
0x1800095f0  mov     [r8+rdx], cl
0x1800095f4  mov     ecx, r15d
0x1800095f7  mov     r8d, [r11]
0x1800095fa  sub     cl, r8b
0x1800095fd  inc     dword ptr [rax]
0x1800095ff  add     r8d, 0FFFFFFF0h
0x180009603  shr     bp, cl
0x180009606  add     r8d, r12d
0x180009609  mov     [r10], bp
0x18000960d  mov     [r11], r8d
0x180009610  jmp     short loc_180009621
0x180009612  add     r8d, r12d
0x180009615  movzx   ebp, si
0x180009618  mov     [r11], r8d
0x18000961b  jmp     short loc_180009621
0x18000961d  movzx   ebp, r9w
0x180009621  mov     esi, dword ptr [rsp+58h+arg_0]
0x180009625  dec     esi
0x180009627  mov     ecx, esi
0x180009629  cmp     esi, 100h
0x18000962f  jb      short loc_18000963A
0x180009631  shr     ecx, 7
0x180009634  add     ecx, 100h
0x18000963a  mov     edx, ecx
0x18000963c  movzx   edx, byte ptr [rdx+r13+2F270h]
0x180009645  lea     rcx, ds:0[rdx*4]
0x18000964d  mov     rdx, [rsp+58h+arg_10]
0x180009652  mov     [rsp+58h+arg_0], rcx
0x180009657  movzx   r12d, word ptr [rcx+rdx+2]
0x18000965d  movzx   r9d, word ptr [rcx+rdx]
0x180009662  mov     edx, r15d
0x180009665  sub     edx, r12d
0x180009668  mov     ecx, r8d
0x18000966b  cmp     r8d, edx
0x18000966e  jle     short loc_1800096BA
0x180009670  mov     edx, [rax]
0x180009672  movzx   r8d, r9w
0x180009676  shl     r8w, cl
0x18000967a  add     r12d, 0FFFFFFF0h
0x18000967e  mov     rcx, [rdi]
0x180009681  or      r8w, bp
0x180009685  mov     [r10], r8w
0x180009689  mov     r13, rdi
0x18000968c  mov     [rdx+rcx], r8b
0x180009690  inc     dword ptr [rax]
0x180009692  mov     rdx, [rdi]
0x180009695  mov     r8d, [rax]
0x180009698  movzx   ecx, byte ptr [r10+1]
0x18000969d  mov     [r8+rdx], cl
0x1800096a1  mov     edx, r15d
0x1800096a4  mov     ecx, [r11]
0x1800096a7  add     r12d, ecx
0x1800096aa  inc     dword ptr [rax]
0x1800096ac  sub     dl, cl
0x1800096ae  movzx   ecx, dl
0x1800096b1  mov     rdx, rax
0x1800096b4  shr     r9w, cl
0x1800096b8  jmp     short loc_1800096CD
0x1800096ba  add     r12d, r8d
0x1800096bd  shl     r9w, cl
0x1800096c1  or      r9w, bp
0x1800096c5  lea     rdx, [rbx+28h]
0x1800096c9  lea     r13, [rbx+10h]
0x1800096cd  mov     rcx, [rsp+58h+arg_0]
0x1800096d2  lea     r8, __ImageBase
0x1800096d9  mov     [r10], r9w
0x1800096dd  mov     [r11], r12d
0x1800096e0  mov     ebp, [rcx+r8+2F4F0h]
0x1800096e8  test    ebp, ebp
0x1800096ea  jz      short loc_180009756
0x1800096ec  sub     si, [rcx+r8+2FB60h]
0x1800096f5  mov     ecx, r12d
0x1800096f8  movzx   r8d, si
0x1800096fc  shl     r8w, cl
0x180009700  mov     ecx, r15d
0x180009703  or      r8w, r9w
0x180009707  sub     ecx, ebp
0x180009709  mov     [r10], r8w
0x18000970d  cmp     r12d, ecx
0x180009710  jle     short loc_18000974F
0x180009712  mov     edx, [rax]
0x180009714  mov     r13, rdi
0x180009717  mov     rcx, [rdi]
0x18000971a  mov     [rdx+rcx], r8b
0x18000971e  inc     dword ptr [rax]
0x180009720  mov     r8d, [rax]
0x180009723  movzx   ecx, byte ptr [r10+1]
0x180009728  mov     rdx, [rdi]
0x18000972b  mov     [r8+rdx], cl
0x18000972f  mov     ecx, r15d
0x180009732  mov     r8d, [r11]
0x180009735  sub     cl, r8b
0x180009738  inc     dword ptr [rax]
0x18000973a  shr     si, cl
0x18000973d  lea     ecx, [rbp-10h]
0x180009740  add     ecx, r8d
0x180009743  mov     [r10], si
0x180009747  mov     [r11], ecx
0x18000974a  mov     rsi, rax
0x18000974d  jmp     short loc_180009765
0x18000974f  lea     eax, [r12+rbp]
0x180009753  mov     [r11], eax
0x180009756  mov     rsi, [rsp+58h+arg_18]
0x18000975b  mov     rdi, r13
0x18000975e  mov     r13, [rsp+58h+var_58]
0x180009762  mov     rax, rdx
0x180009765  mov     r12, [rsp+58h+arg_8]
0x18000976a  cmp     r14d, [rbx+16F4h]
0x180009771  jb      loc_180009450
0x180009777  mov     rbp, [rsp+58h+var_28]
0x18000977c  jmp     short loc_180009784
0x18000977e  mov     rsi, rax
0x180009781  mov     r13, rdi
0x180009784  movzx   r9d, word ptr [r12+400h]
0x18000978d  mov     eax, r15d
0x180009790  movzx   ebx, word ptr [r12+402h]
0x180009799  movzx   edx, r9w
0x18000979d  mov     ecx, [r11]
0x1800097a0  sub     eax, ebx
0x1800097a2  mov     r14, [rsp+58h+var_40]
0x1800097a7  mov     r12, [rsp+58h+var_38]
0x1800097ac  mov     rdi, [rsp+58h+var_30]
0x1800097b1  shl     dx, cl
0x1800097b4  or      dx, [r10]
0x1800097b8  mov     [r10], dx
0x1800097bc  cmp     ecx, eax
0x1800097be  jle     short loc_180009807
0x1800097c0  mov     rax, [r13+0]
0x1800097c4  movzx   r8d, dx
0x1800097c8  mov     edx, [rsi]
0x1800097ca  mov     [rdx+rax], r8b
0x1800097ce  inc     dword ptr [rsi]
0x1800097d0  mov     r8d, [rsi]
0x1800097d3  mov     rdx, [r13+0]
0x1800097d7  movzx   eax, byte ptr [r10+1]
0x1800097dc  mov     [r8+rdx], al
0x1800097e0  mov     eax, [r11]
0x1800097e3  sub     r15b, al
0x1800097e6  inc     dword ptr [rsi]
0x1800097e8  movzx   ecx, r15b
0x1800097ec  lea     edx, [rax-10h]
0x1800097ef  add     edx, ebx
0x1800097f1  shr     r9w, cl
0x1800097f5  mov     [r10], r9w
0x1800097f9  mov     [r11], edx
0x1800097fc  add     rsp, 38h
0x180009800  pop     r15
0x180009802  pop     r13
0x180009804  pop     rsi
0x180009805  pop     rbx
0x180009806  retn
0x180009807  lea     eax, [rcx+rbx]
0x18000980a  mov     [r11], eax
0x18000980d  add     rsp, 38h
0x180009811  pop     r15
0x180009813  pop     r13
0x180009815  pop     rsi
0x180009816  pop     rbx
0x180009817  retn
```
