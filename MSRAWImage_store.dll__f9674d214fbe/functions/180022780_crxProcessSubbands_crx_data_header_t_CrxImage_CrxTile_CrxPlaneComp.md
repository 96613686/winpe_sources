# crxProcessSubbands(crx_data_header_t *,CrxImage *,CrxTile *,CrxPlaneComp *)

- ea: `0x180022780`
- end: `0x180022b8b`
- name: `?crxProcessSubbands@@YAHPEAUcrx_data_header_t@@PEAUCrxImage@@PEAUCrxTile@@PEAUCrxPlaneComp@@@Z`
- size: `1035`
- prototype: `__int64 __fastcall(struct crx_data_header_t *, struct CrxImage *, struct CrxTile *, struct CrxPlaneComp *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180022ba0`

## callees

- `0x180022780`

## pseudocode

```c
__int64 __fastcall crxProcessSubbands(
        struct crx_data_header_t *a1,
        struct CrxImage *a2,
        struct CrxTile *a3,
        struct CrxPlaneComp *a4)
{
  unsigned int v4; // r11d
  int v5; // r15d
  struct crx_data_header_t *v6; // rdi
  unsigned __int8 *v7; // rbx
  __int64 v8; // r10
  __int64 v9; // rax
  unsigned int v10; // r9d
  _WORD *v11; // rax
  __int64 v12; // r10
  int v13; // r12d
  char *v14; // rsi
  int v15; // r13d
  int v16; // edi
  int v17; // r10d
  int v18; // r14d
  int v19; // edx
  char v20; // bl
  int v21; // ebp
  __int16 v22; // r8
  __int16 v23; // cx
  __int16 v24; // r10
  __int16 v25; // cx
  __int16 v26; // r15
  __int16 v27; // r14
  __int16 v28; // r10
  __int16 v29; // r8
  __int16 v30; // cx
  __int16 v31; // r13
  __int16 v32; // bx
  __int16 v33; // si
  __int16 v34; // dx
  __int16 v35; // cx
  int v36; // ecx
  char v37; // di
  bool v38; // zf
  __int16 v39; // r9
  int v40; // ecx
  __int16 v42; // [rsp+0h] [rbp-98h]
  int v43; // [rsp+4h] [rbp-94h]
  __int16 v44; // [rsp+Ch] [rbp-8Ch]
  __int16 v45; // [rsp+10h] [rbp-88h]
  _WORD *v46; // [rsp+30h] [rbp-68h]
  _WORD *v47; // [rsp+38h] [rbp-60h]
  char *v48; // [rsp+40h] [rbp-58h]
  char *v49; // [rsp+48h] [rbp-50h]
  struct CrxImage *v51; // [rsp+A8h] [rbp+10h]
  struct CrxTile *v52; // [rsp+B0h] [rbp+18h]
  int v53; // [rsp+B8h] [rbp+20h]

  v52 = a3;
  v51 = a2;
  v4 = *((unsigned __int16 *)a3 + 14);
  LOWORD(v5) = 0;
  v6 = a1;
  v7 = (unsigned __int8 *)a2 + 9;
  v8 = 88LL * *((unsigned __int8 *)a2 + 8);
  v9 = *((_QWORD *)a4 + 1);
  LOWORD(a2) = 0;
  v10 = *((unsigned __int16 *)a3 + 15);
  v11 = (_WORD *)(v8 + v9 - 88);
  LOWORD(a3) = 0;
  v12 = *v7;
  if ( (_BYTE)v12 )
  {
    v43 = 0;
    LOWORD(v13) = 0;
    v14 = (char *)&exCoefNumTbl + 192 * v12 + 24 * (v4 & 7) - 192;
    v48 = v14;
    v49 = (char *)&exCoefNumTbl + 192 * v12 + 24 * (v10 & 7) - 192;
    v15 = 0;
    v53 = 0;
    do
    {
      LOWORD(v16) = 0;
      v17 = v4 & 1;
      v18 = v10 & 1;
      v4 = (v17 + v4) >> 1;
      v10 = (v18 + v10) >> 1;
      LOWORD(v19) = 0;
      v20 = *((_BYTE *)v52 + 8);
      LOWORD(v21) = 0;
      if ( (v20 & 1) != 0 )
      {
        v19 = *(_DWORD *)&v14[4 * v15];
        v21 = *(_DWORD *)&v14[4 * v15 + 4];
      }
      v22 = v19 + 1;
      if ( (v20 & 2) == 0 )
        v22 = v19;
      if ( (v20 & 4) != 0 )
      {
        v5 = *(_DWORD *)&v49[4 * v15];
        v16 = *(_DWORD *)&v49[4 * v15 + 4];
      }
      v23 = v22 - v17;
      v24 = v5 + 1;
      v25 = v4 + v23;
      v11[12] = v25;
      v45 = v25;
      if ( (v20 & 8) == 0 )
        v24 = v5;
      v11[13] = v10 + v24 - v18;
      v44 = v10 + v24 - v18;
      v26 = (v20 & 8) != 0;
      v47 = v11 + 40;
      v27 = (v20 & 2) != 0;
      v46 = v11 + 39;
      v28 = v24 - v26;
      v29 = v22 - v27;
      if ( *(_DWORD *)a1 == 512 )
      {
        v30 = 2 - v13;
        v31 = (v20 & 8) != 0;
        v32 = v29;
        v33 = v27;
        v42 = v28;
      }
      else
      {
        v30 = 0;
        v31 = 0;
        v47 = v11 + 40;
        v32 = 0;
        v46 = v11 + 39;
        v33 = 0;
        v42 = 0;
      }
      v34 = 2 - v13;
      v11[36] = v31;
      v11[37] = v42;
      v11[38] = v33;
      *v46 = v32;
      *v47 = v30;
      *(v11 - 32) = v4 + v21;
      *(v11 - 31) = v44;
      if ( *(_DWORD *)a1 != 512 )
      {
        LOWORD(v21) = 0;
        v26 = 0;
      }
      v35 = 2 - v13;
      if ( *(_DWORD *)a1 != 512 )
      {
        v35 = 0;
        v28 = 0;
      }
      *(v11 - 4) = v35;
      *(v11 - 8) = v26;
      LOWORD(v5) = 0;
      *(v11 - 7) = v28;
      *(v11 - 6) = 0;
      *(v11 - 5) = v21;
      *(v11 - 76) = v45;
      *(v11 - 75) = v10 + v16;
      if ( *(_DWORD *)a1 != 512 )
      {
        v29 = 0;
        v27 = 0;
        LOWORD(v16) = 0;
        v34 = 0;
      }
      v14 = v48;
      v13 = v43 + 1;
      *(v11 - 52) = 0;
      *(v11 - 51) = v16;
      v15 = v53 + 2;
      *(v11 - 50) = v27;
      *(v11 - 49) = v29;
      *(v11 - 48) = v34;
      v11 -= 132;
      v43 = v13;
      v53 += 2;
      v36 = *((unsigned __int8 *)v51 + 9);
    }
    while ( v13 < v36 );
    v7 = (unsigned __int8 *)v51 + 9;
    LOWORD(a2) = 0;
    LOWORD(a3) = 0;
    v37 = *((_BYTE *)v52 + 8);
    if ( (v37 & 1) != 0 )
      LODWORD(a3) = *(_DWORD *)&v48[8 * (unsigned __int8)v36 - 4];
    v38 = (v37 & 4) == 0;
    v6 = a1;
    if ( !v38 )
    {
      LODWORD(a2) = *(_DWORD *)&v49[8 * (unsigned __int8)v36 - 4];
      v7 = (unsigned __int8 *)v51 + 9;
    }
  }
  v11[12] = v4 + (_WORD)a3;
  v11[13] = v10 + (_WORD)a2;
  v39 = *v7;
  if ( (_BYTE)v39 )
  {
    v40 = *(_DWORD *)v6;
    v11[36] = 0;
    v11[38] = 0;
    if ( v40 == 512 )
    {
      v11[37] = (_WORD)a2;
      v11[39] = (_WORD)a3;
      v11[40] = 3 - v39;
      return 0;
    }
    v11[37] = 0;
    *(_DWORD *)(v11 + 39) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180022780  mov     rax, rsp
0x180022783  mov     [rax+18h], r8
0x180022787  mov     [rax+10h], rdx
0x18002278b  mov     [rax+8], rcx
0x18002278f  push    rdi
0x180022790  push    r15
0x180022792  sub     rsp, 88h
0x180022799  movzx   r11d, word ptr [r8+1Ch]
0x18002279e  xor     r15d, r15d
0x1800227a1  mov     [rax-18h], rbx
0x1800227a5  mov     rdi, rcx
0x1800227a8  mov     [rax-20h], rbp
0x1800227ac  mov     rbp, rdx
0x1800227af  movzx   eax, byte ptr [rdx+8]
0x1800227b3  lea     rbx, [rbp+9]
0x1800227b7  imul    r10, rax, 58h ; 'X'
0x1800227bb  mov     rax, [r9+8]
0x1800227bf  mov     edx, r15d
0x1800227c2  movzx   r9d, word ptr [r8+1Eh]
0x1800227c7  add     rax, 0FFFFFFFFFFFFFFA8h
0x1800227cb  add     rax, r10
0x1800227ce  mov     r8d, r15d
0x1800227d1  movzx   r10d, byte ptr [rbx]
0x1800227d5  test    r10b, r10b
0x1800227d8  jz      loc_180022B15
0x1800227de  mov     [rsp+98h+var_28], rsi
0x1800227e3  lea     rdi, ?exCoefNumTbl@@3PAHA; int near * exCoefNumTbl
0x1800227ea  mov     ecx, r11d
0x1800227ed  mov     [rsp+98h+var_30], r12
0x1800227f2  and     ecx, 7
0x1800227f5  mov     [rsp+98h+var_40], r14
0x1800227fa  lea     r8, [r10+r10*2]
0x1800227fe  mov     [rsp+98h+var_94], r15d
0x180022803  shl     r8, 4
0x180022807  mov     r12d, r15d
0x18002280a  lea     ecx, [rcx+rcx*2]
0x18002280d  lea     esi, [rcx+rcx]
0x180022810  mov     ecx, r9d
0x180022813  and     ecx, 7
0x180022816  add     rsi, 0FFFFFFFFFFFFFFD0h
0x18002281a  add     rsi, r8
0x18002281d  lea     ecx, [rcx+rcx*2]
0x180022820  lea     r14d, [rcx+rcx]
0x180022824  add     r14, 0FFFFFFFFFFFFFFD0h
0x180022828  lea     rsi, [rdi+rsi*4]
0x18002282c  add     r14, r8
0x18002282f  mov     [rsp+98h+var_58], rsi
0x180022834  lea     r14, [rdi+r14*4]
0x180022838  mov     [rsp+98h+var_50], r14
0x18002283d  test    r10b, r10b
0x180022840  jz      loc_180022ACE
0x180022846  mov     [rsp+98h+var_38], r13
0x18002284b  mov     r13d, r15d
0x18002284e  mov     [rsp+98h+arg_18], r15d
0x180022856  xor     ecx, ecx
0x180022858  mov     r10d, r11d
0x18002285b  mov     r14d, r9d
0x18002285e  mov     edi, ecx
0x180022860  mov     rcx, [rsp+98h+arg_10]
0x180022868  and     r10d, 1
0x18002286c  and     r14d, 1
0x180022870  add     r11d, r10d
0x180022873  add     r9d, r14d
0x180022876  shr     r11d, 1
0x180022879  shr     r9d, 1
0x18002287c  mov     edx, r15d
0x18002287f  movzx   ebx, byte ptr [rcx+8]
0x180022883  mov     ebp, r15d
0x180022886  movsxd  rcx, r13d
0x180022889  test    bl, 1
0x18002288c  jz      short loc_180022895
0x18002288e  mov     edx, [rsi+rcx*4]
0x180022891  mov     ebp, [rsi+rcx*4+4]
0x180022895  movzx   esi, bl
0x180022898  lea     r8d, [rdx+1]
0x18002289c  and     sil, 2
0x1800228a0  cmovz   r8d, edx
0x1800228a4  test    bl, 4
0x1800228a7  jz      short loc_1800228B6
0x1800228a9  mov     rdx, [rsp+98h+var_50]
0x1800228ae  mov     r15d, [rdx+rcx*4]
0x1800228b2  mov     edi, [rdx+rcx*4+4]
0x1800228b6  movzx   ecx, r8w
0x1800228ba  movzx   edx, r12w
0x1800228be  sub     cx, r10w
0x1800228c2  lea     r10d, [r15+1]
0x1800228c6  add     cx, r11w
0x1800228ca  mov     [rax+18h], cx
0x1800228ce  test    bl, 8
0x1800228d1  mov     dword ptr [rsp+98h+var_88], ecx
0x1800228d5  cmovz   r10w, r15w
0x1800228da  movzx   ecx, r10w
0x1800228de  sub     cx, r14w
0x1800228e2  add     cx, r9w
0x1800228e6  mov     [rax+1Ah], cx
0x1800228ea  mov     [rsp+98h+var_8C], ecx
0x1800228ee  xor     ecx, ecx
0x1800228f0  mov     r15d, ecx
0x1800228f3  mov     r14d, ecx
0x1800228f6  test    bl, 8
0x1800228f9  lea     rcx, [rax+48h]
0x1800228fd  mov     [rsp+98h+var_70], rcx
0x180022902  lea     rbx, [rax+50h]
0x180022906  setnz   r15b
0x18002290a  mov     [rsp+98h+var_60], rbx
0x18002290f  test    sil, sil
0x180022912  lea     rcx, [rax+4Ah]
0x180022916  mov     [rsp+98h+var_80], rcx
0x18002291b  lea     rsi, [rax+4Eh]
0x18002291f  setnz   r14b
0x180022923  mov     [rsp+98h+var_68], rsi
0x180022928  lea     rcx, [rax+4Ch]
0x18002292c  neg     dx
0x18002292f  mov     [rsp+98h+var_78], rcx
0x180022934  sub     r10w, r15w
0x180022938  mov     rcx, [rsp+98h+arg_0]
0x180022940  sub     r8w, r14w
0x180022944  cmp     dword ptr [rcx], 200h
0x18002294a  jnz     short loc_180022969
0x18002294c  mov     word ptr [rsp+98h+var_90], r15w
0x180022952  lea     ecx, [rdx+2]
0x180022955  mov     r13d, [rsp+98h+var_90]
0x18002295a  movzx   ebx, r8w
0x18002295e  movzx   esi, r14w
0x180022962  mov     word ptr [rsp+98h+var_98], r10w
0x180022967  jmp     short loc_18002299A
0x180022969  mov     r13, [rsp+98h+var_78]
0x18002296e  xor     r12d, r12d
0x180022971  mov     [rsp+98h+var_78], r13
0x180022976  mov     ecx, r12d
0x180022979  mov     r13, [rsp+98h+var_80]
0x18002297e  mov     [rsp+98h+var_80], r13
0x180022983  mov     r13d, r12d
0x180022986  mov     [rsp+98h+var_60], rbx
0x18002298b  mov     ebx, r12d
0x18002298e  mov     [rsp+98h+var_68], rsi
0x180022993  mov     esi, r12d
0x180022996  mov     [rsp+98h+var_98], r12d
0x18002299a  mov     r12, [rsp+98h+var_70]
0x18002299f  add     dx, 2
0x1800229a3  mov     [r12], r13w
0x1800229a8  mov     r12, [rsp+98h+var_80]
0x1800229ad  mov     r13d, [rsp+98h+var_98]
0x1800229b1  mov     [r12], r13w
0x1800229b6  mov     r13, [rsp+98h+var_78]
0x1800229bb  mov     [r13+0], si
0x1800229c0  mov     rsi, [rsp+98h+var_68]
0x1800229c5  mov     [rsi], bx
0x1800229c8  mov     rbx, [rsp+98h+var_60]
0x1800229cd  mov     [rbx], cx
0x1800229d0  lea     ecx, [r11+rbp]
0x1800229d4  mov     r12, [rsp+98h+arg_0]
0x1800229dc  mov     rbx, rax
0x1800229df  mov     [rax-40h], cx
0x1800229e3  mov     ecx, [rsp+98h+var_8C]
0x1800229e7  mov     [rax-3Eh], cx
0x1800229eb  mov     esi, [r12]
0x1800229ef  cmp     esi, 200h
0x1800229f5  jz      short loc_180022A00
0x1800229f7  xor     ecx, ecx
0x1800229f9  movzx   ebp, cx
0x1800229fc  movzx   r15d, cx
0x180022a00  mov     r13d, 0
0x180022a06  cmp     esi, 200h
0x180022a0c  movzx   ecx, dx
0x180022a0f  cmovnz  cx, r13w
0x180022a14  cmovnz  r10w, r13w
0x180022a19  mov     [rbx-8], cx
0x180022a1d  mov     ecx, dword ptr [rsp+98h+var_88]
0x180022a21  mov     [rax-10h], r15w
0x180022a26  mov     r15d, r13d
0x180022a29  mov     [rax-0Eh], r10w
0x180022a2e  mov     [rax-0Ch], r13w
0x180022a33  mov     [rax-0Ah], bp
0x180022a37  mov     [rax-98h], cx
0x180022a3e  lea     ecx, [r9+rdi]
0x180022a42  mov     [rax-96h], cx
0x180022a49  cmp     dword ptr [r12], 200h
0x180022a51  jz      short loc_180022A5F
0x180022a53  movzx   r8d, r13w
0x180022a57  movzx   r14d, r13w
0x180022a5b  movzx   edi, r13w
0x180022a5f  mov     r12d, [rsp+98h+var_94]
0x180022a64  cmovnz  dx, r13w
0x180022a69  mov     rsi, [rsp+98h+var_58]
0x180022a6e  inc     r12d
0x180022a71  mov     [rax-68h], r13w
0x180022a76  mov     r13d, [rsp+98h+arg_18]
0x180022a7e  mov     [rax-66h], di
0x180022a82  add     r13d, 2
0x180022a86  mov     [rax-64h], r14w
0x180022a8b  mov     [rax-62h], r8w
0x180022a90  mov     [rax-60h], dx
0x180022a94  sub     rax, 108h
0x180022a9a  mov     rbp, [rsp+98h+arg_8]
0x180022aa2  mov     [rsp+98h+var_94], r12d
0x180022aa7  mov     [rsp+98h+arg_18], r13d
0x180022aaf  movzx   ecx, byte ptr [rbp+9]
0x180022ab3  cmp     r12d, ecx
0x180022ab6  jl      loc_180022856
0x180022abc  mov     r13, [rsp+98h+var_38]
0x180022ac1  lea     rbx, [rbp+9]
0x180022ac5  mov     r14, [rsp+98h+var_50]
0x180022aca  movzx   r10d, cl
0x180022ace  mov     rcx, [rsp+98h+arg_10]
0x180022ad6  mov     edx, r15d
0x180022ad9  mov     r12, [rsp+98h+var_30]
0x180022ade  mov     r8d, r15d
0x180022ae1  movzx   edi, byte ptr [rcx+8]
0x180022ae5  movzx   ecx, r10b
0x180022ae9  test    dil, 1
0x180022aed  jz      short loc_180022AF4
0x180022aef  mov     r8d, [rsi+rcx*8-4]
0x180022af4  mov     rsi, [rsp+98h+var_28]
0x180022af9  test    dil, 4
0x180022afd  mov     rdi, [rsp+98h+arg_0]
0x180022b05  jz      short loc_180022B10
0x180022b07  mov     edx, [r14+rcx*8-4]
0x180022b0c  lea     rbx, [rbp+9]
0x180022b10  mov     r14, [rsp+98h+var_40]
0x180022b15  mov     rbp, [rsp+98h+var_20]
0x180022b1a  lea     ecx, [r11+r8]
0x180022b1e  mov     [rax+18h], cx
0x180022b22  lea     ecx, [r9+rdx]
0x180022b26  mov     [rax+1Ah], cx
0x180022b2a  movzx   r9d, byte ptr [rbx]
0x180022b2e  mov     rbx, [rsp+98h+var_18]
0x180022b36  test    r9b, r9b
0x180022b39  jz      short loc_180022B7E
0x180022b3b  mov     ecx, [rdi]
0x180022b3d  mov     [rax+48h], r15w
0x180022b42  mov     [rax+4Ch], r15w
0x180022b47  cmp     ecx, 200h
0x180022b4d  jnz     short loc_180022B72
0x180022b4f  mov     [rax+4Ah], dx
0x180022b53  mov     edx, 3
0x180022b58  sub     dx, r9w
0x180022b5c  mov     [rax+4Eh], r8w
0x180022b61  mov     [rax+50h], dx
0x180022b65  xor     eax, eax
0x180022b67  add     rsp, 88h
0x180022b6e  pop     r15
0x180022b70  pop     rdi
0x180022b71  retn
0x180022b72  mov     [rax+4Ah], r15w
0x180022b77  mov     dword ptr [rax+4Eh], 0
0x180022b7e  xor     eax, eax
0x180022b80  add     rsp, 88h
0x180022b87  pop     r15
0x180022b89  pop     rdi
0x180022b8a  retn
```
