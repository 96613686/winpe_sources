# BfeNetEventConvertToData

- ea: `0x14002a9a0`
- end: `0x14002aeee`
- name: `BfeNetEventConvertToData`
- size: `1358`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14002a310`
- `0x1400327f0`

## callees

- `0x14002a9a0`
- `0x14003acfc`
- `0x140050b54`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x14002aa37`
- `ntoskrnl!RtlLengthSid` at `0x14002aa86`
- `ntoskrnl!RtlLengthSid` at `0x14002aa37`
- `ntoskrnl!RtlLengthSid` at `0x14002aa86`

## pseudocode

```c
__int64 __fastcall BfeNetEventConvertToData(__int64 a1, unsigned int *a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // edx
  unsigned int *v7; // rcx
  unsigned int v8; // eax
  void *v9; // rsi
  ULONG v10; // eax
  __int64 v11; // rcx
  ULONG v12; // edx
  void *v13; // rsi
  ULONG v14; // eax
  __int64 v15; // rcx
  ULONG v16; // edx
  __int64 v17; // rcx
  __int64 v18; // rax
  unsigned int v20; // edx
  __int64 v21; // rax
  unsigned int v22; // ecx
  unsigned int v23; // edx
  unsigned int *v24; // rcx
  unsigned int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // r8
  unsigned int *v32; // rcx
  unsigned int *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // r8
  unsigned int v39; // edx
  __int64 v40; // rcx
  __int64 v41; // rax
  unsigned int *v42; // rcx
  unsigned int v43; // eax
  unsigned int *v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // r8
  unsigned int *v47; // rcx
  int v48; // eax
  __int64 v49; // rcx
  __int64 result; // rax

  *a2 = 0;
  *((_OWORD *)a2 + 25) = 0;
  v4 = 2LL * *a2;
  *(_QWORD *)&a2[2 * v4 + 2] = a1;
  *(_QWORD *)&a2[2 * v4 + 4] = 240;
  ++*a2;
  LODWORD(v4) = *(_DWORD *)(a1 + 8);
  v5 = *a2;
  if ( (v4 & 0x20) != 0 )
  {
    v6 = *(_DWORD *)(a1 + 64);
    if ( v6 )
    {
      v7 = &a2[4 * v5];
      *((_QWORD *)v7 + 1) = *(_QWORD *)(a1 + 72);
      v7[4] = v6;
      v7[5] = 0;
      ++*a2;
      v8 = ((v6 + 7) & 0xFFFFFFF8) - v6;
      if ( v8 )
      {
        *((_QWORD *)v7 + 3) = &qword_14009AA38;
        v7[8] = v8;
        v7[9] = 0;
        ++*a2;
      }
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x40) != 0 )
  {
    v9 = *(void **)(a1 + 80);
    v10 = RtlLengthSid(v9);
    if ( v10 )
    {
      v11 = 2LL * *a2;
      *(_QWORD *)&a2[2 * v11 + 2] = v9;
      a2[2 * v11 + 4] = v10;
      a2[2 * v11 + 5] = 0;
      ++*a2;
      v12 = ((v10 + 7) & 0xFFFFFFF8) - v10;
      if ( v12 )
      {
        *(_QWORD *)&a2[2 * v11 + 6] = &qword_14009AA38;
        a2[2 * v11 + 8] = v12;
        a2[2 * v11 + 9] = 0;
        ++*a2;
      }
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x400) != 0 )
  {
    v13 = *(void **)(a1 + 96);
    v14 = RtlLengthSid(v13);
    if ( v14 )
    {
      v15 = 2LL * *a2;
      *(_QWORD *)&a2[2 * v15 + 2] = v13;
      a2[2 * v15 + 4] = v14;
      a2[2 * v15 + 5] = 0;
      ++*a2;
      v16 = ((v14 + 7) & 0xFFFFFFF8) - v14;
      if ( v16 )
      {
        *(_QWORD *)&a2[2 * v15 + 6] = &qword_14009AA38;
        a2[2 * v15 + 8] = v16;
        a2[2 * v15 + 9] = 0;
        ++*a2;
      }
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x800) != 0 )
  {
    v17 = *(_QWORD *)(a1 + 104);
    v18 = -1;
    while ( *(_WORD *)(v17 + 2 * v18++ + 2) != 0 )
      ;
    v20 = 2 * v18 + 2;
    if ( 2 * (_DWORD)v18 != -2 )
    {
      v21 = 2LL * *a2;
      *(_QWORD *)&a2[2 * v21 + 2] = v17;
      a2[2 * v21 + 4] = v20;
      a2[2 * v21 + 5] = 0;
      ++*a2;
      v22 = ((v20 + 7) & 0xFFFFFFF8) - v20;
      if ( v22 )
      {
        *(_QWORD *)&a2[2 * v21 + 6] = &qword_14009AA38;
        a2[2 * v21 + 8] = v22;
        a2[2 * v21 + 9] = 0;
        ++*a2;
      }
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x2000) != 0 )
  {
    v23 = *(_DWORD *)(a1 + 120);
    if ( v23 )
    {
      v24 = &a2[4 * *a2];
      *((_QWORD *)v24 + 1) = *(_QWORD *)(a1 + 128);
      v24[4] = v23;
      v24[5] = 0;
      ++*a2;
      v25 = ((v23 + 7) & 0xFFFFFFF8) - v23;
      if ( v25 )
      {
        *((_QWORD *)v24 + 3) = &qword_14009AA38;
        v24[8] = v25;
        v24[9] = 0;
        ++*a2;
      }
    }
  }
  switch ( *(_DWORD *)(a1 + 136) )
  {
    case 0:
    case 2:
      v26 = 2LL * *a2;
      *(_QWORD *)&a2[2 * v26 + 2] = *(_QWORD *)(a1 + 144);
      *(_QWORD *)&a2[2 * v26 + 4] = 120;
      ++*a2;
      BfeEventDataPushStr(a2, *(_QWORD *)(*(_QWORD *)(a1 + 144) + 64LL));
      BfeEventDataPushStr(v27, *(_QWORD *)(*(_QWORD *)(a1 + 144) + 72LL));
      BfeEventDataPushStrArray(
        v28,
        *(_QWORD *)(*(_QWORD *)(a1 + 144) + 88LL),
        *(unsigned int *)(*(_QWORD *)(a1 + 144) + 80LL),
        a2 + 100);
      BfeEventDataPushStrArray(
        a2,
        *(_QWORD *)(*(_QWORD *)(a1 + 144) + 104LL),
        *(unsigned int *)(*(_QWORD *)(a1 + 144) + 96LL),
        a2 + 102);
      goto LABEL_44;
    case 1:
      v29 = 2LL * *a2;
      *(_QWORD *)&a2[2 * v29 + 2] = *(_QWORD *)(a1 + 144);
      *(_QWORD *)&a2[2 * v29 + 4] = 88;
      ++*a2;
      v30 = *(_QWORD *)(a1 + 144);
      v31 = *a2;
      if ( *(_DWORD *)(v30 + 20) != 1 )
        goto LABEL_44;
      if ( *(_DWORD *)(v30 + 24) == 256 )
      {
        v34 = 2 * v31;
        *(_QWORD *)&a2[2 * v34 + 2] = *(_QWORD *)(v30 + 32);
        *(_QWORD *)&a2[2 * v34 + 4] = 8;
        ++*a2;
        v35 = *(_QWORD *)(v30 + 48);
        v36 = 2LL * *a2;
        *(_QWORD *)&a2[4 * *a2 + 4] = 8;
LABEL_42:
        *(_QWORD *)&a2[2 * v36 + 2] = v35;
      }
      else
      {
        if ( *(_DWORD *)(v30 + 24) != 257 )
LABEL_56:
          __fastfail(5u);
        v32 = &a2[4 * (unsigned int)v31];
        *((_QWORD *)v32 + 1) = *(_QWORD *)(v30 + 32);
        *((_QWORD *)v32 + 2) = 17;
        ++*a2;
        *((_QWORD *)v32 + 3) = &qword_14009AA38;
        *((_QWORD *)v32 + 4) = 7;
        v33 = &a2[4 * ++*a2];
        *((_QWORD *)v33 + 1) = *(_QWORD *)(v30 + 48);
        *((_QWORD *)v33 + 2) = 17;
        ++*a2;
        *((_QWORD *)v33 + 3) = &qword_14009AA38;
        *((_QWORD *)v33 + 4) = 7;
      }
      goto LABEL_43;
    case 3:
      v37 = 2LL * *a2;
      *(_QWORD *)&a2[2 * v37 + 2] = *(_QWORD *)(a1 + 144);
      *(_QWORD *)&a2[2 * v37 + 4] = 56;
      ++*a2;
      v38 = *(_QWORD *)(a1 + 144);
      v39 = *(_DWORD *)(v38 + 32);
      if ( !v39 )
        goto LABEL_44;
      v40 = *a2;
      v41 = *(_QWORD *)(v38 + 40);
      goto LABEL_32;
    case 4:
    case 6:
    case 0x13:
    case 0x14:
      v35 = *(_QWORD *)(a1 + 144);
      v36 = 2LL * *a2;
      *(_QWORD *)&a2[4 * *a2 + 4] = 32;
      goto LABEL_42;
    case 5:
      v44 = &a2[4 * *a2];
      *((_QWORD *)v44 + 1) = *(_QWORD *)(a1 + 144);
      *((_QWORD *)v44 + 2) = 44;
      ++*a2;
      *((_QWORD *)v44 + 3) = &qword_14009AA38;
      *((_QWORD *)v44 + 4) = 4;
      goto LABEL_43;
    case 7:
    case 8:
      v35 = *(_QWORD *)(a1 + 144);
      v36 = 2LL * *a2;
      *(_QWORD *)&a2[4 * *a2 + 4] = 24;
      goto LABEL_42;
    case 9:
      v45 = 2LL * *a2;
      *(_QWORD *)&a2[2 * v45 + 2] = *(_QWORD *)(a1 + 144);
      *(_QWORD *)&a2[2 * v45 + 4] = 104;
      ++*a2;
      v46 = *(_QWORD *)(a1 + 144);
      v39 = *(_DWORD *)(v46 + 80);
      if ( !v39 )
        goto LABEL_44;
      v40 = *a2;
      v41 = *(_QWORD *)(v46 + 88);
LABEL_32:
      v42 = &a2[4 * v40];
      *((_QWORD *)v42 + 1) = v41;
      v42[4] = v39;
      v42[5] = 0;
      ++*a2;
      v43 = ((v39 + 7) & 0xFFFFFFF8) - v39;
      if ( v43 )
      {
        *((_QWORD *)v42 + 3) = &qword_14009AA38;
        v42[8] = v43;
        v42[9] = 0;
LABEL_43:
        ++*a2;
      }
LABEL_44:
      if ( (*(_DWORD *)(a1 + 152) & 1) != 0 )
        BfeEventDataPushStr(a2, *(_QWORD *)(a1 + 168));
      v48 = *(unsigned __int16 *)(a1 + 176);
      if ( (_WORD)v48 && 16 * v48 )
      {
        v49 = 2LL * *a2;
        *(_QWORD *)&a2[2 * v49 + 2] = *(_QWORD *)(a1 + 184);
        a2[2 * v49 + 4] = 16 * v48;
        a2[2 * v49 + 5] = 0;
        ++*a2;
      }
      if ( (*(_DWORD *)(a1 + 152) & 2) != 0 )
        BfeEventDataPushStr(a2, *(_QWORD *)(a1 + 192));
      if ( (*(_DWORD *)(a1 + 152) & 4) != 0 )
        BfeEventDataPushStr(a2, *(_QWORD *)(a1 + 208));
      result = *(unsigned int *)(a1 + 152);
      if ( (result & 8) != 0 )
        return BfeEventDataPushStr(a2, *(_QWORD *)(a1 + 232));
      return result;
    case 0xA:
      v47 = &a2[4 * *a2];
      *((_QWORD *)v47 + 1) = *(_QWORD *)(a1 + 144);
      *((_QWORD *)v47 + 2) = 4;
      ++*a2;
      *((_QWORD *)v47 + 3) = &qword_14009AA38;
      *((_QWORD *)v47 + 4) = 4;
      goto LABEL_43;
    case 0xD:
    case 0xE:
    case 0x10:
    case 0x11:
      v35 = *(_QWORD *)(a1 + 144);
      v36 = 2LL * *a2;
      *(_QWORD *)&a2[4 * *a2 + 4] = 40;
      goto LABEL_42;
    case 0xF:
    case 0x12:
      v35 = *(_QWORD *)(a1 + 144);
      v36 = 2LL * *a2;
      *(_QWORD *)&a2[4 * *a2 + 4] = 48;
      goto LABEL_42;
    default:
      goto LABEL_56;
  }
}

```

## disassembly

```asm
0x14002a9a0  mov     [rsp+arg_8], rbx
0x14002a9a5  mov     [rsp+arg_10], rbp
0x14002a9aa  push    rdi
0x14002a9ab  push    r14
0x14002a9ad  push    r15
0x14002a9af  sub     rsp, 20h
0x14002a9b3  xor     r14d, r14d
0x14002a9b6  lea     r15, qword_14009AA38
0x14002a9bd  mov     [rdx], r14d
0x14002a9c0  mov     rdi, rcx
0x14002a9c3  xorps   xmm0, xmm0
0x14002a9c6  mov     rbx, rdx
0x14002a9c9  movups  xmmword ptr [rdx+190h], xmm0
0x14002a9d0  mov     eax, [rdx]
0x14002a9d2  add     rax, rax
0x14002a9d5  mov     [rdx+rax*8+8], rcx
0x14002a9da  mov     qword ptr [rdx+rax*8+10h], 0F0h
0x14002a9e3  inc     dword ptr [rdx]
0x14002a9e5  mov     eax, [rdi+8]
0x14002a9e8  mov     ecx, [rdx]
0x14002a9ea  test    al, 20h
0x14002a9ec  jz      short loc_14002AA24
0x14002a9ee  mov     edx, [rdi+40h]
0x14002a9f1  test    edx, edx
0x14002a9f3  jz      short loc_14002AA24
0x14002a9f5  mov     rax, [rdi+48h]
0x14002a9f9  shl     rcx, 4
0x14002a9fd  add     rcx, rbx
0x14002aa00  mov     [rcx+8], rax
0x14002aa04  lea     eax, [rdx+7]
0x14002aa07  mov     [rcx+10h], edx
0x14002aa0a  and     eax, 0FFFFFFF8h
0x14002aa0d  mov     [rcx+14h], r14d
0x14002aa11  inc     dword ptr [rbx]
0x14002aa13  sub     eax, edx
0x14002aa15  jz      short loc_14002AA24
0x14002aa17  mov     [rcx+18h], r15
0x14002aa1b  mov     [rcx+20h], eax
0x14002aa1e  mov     [rcx+24h], r14d
0x14002aa22  inc     dword ptr [rbx]
0x14002aa24  mov     eax, [rdi+8]
0x14002aa27  mov     [rsp+38h+arg_0], rsi
0x14002aa2c  test    al, 40h
0x14002aa2e  jz      short loc_14002AA76
0x14002aa30  mov     rsi, [rdi+50h]
0x14002aa34  mov     rcx, rsi; Sid
0x14002aa37  call    cs:__imp_RtlLengthSid
0x14002aa3e  nop     dword ptr [rax+rax+00h]
0x14002aa43  test    eax, eax
0x14002aa45  jz      short loc_14002AA76
0x14002aa47  mov     ecx, [rbx]
0x14002aa49  lea     edx, [rax+7]
0x14002aa4c  add     rcx, rcx
0x14002aa4f  and     edx, 0FFFFFFF8h
0x14002aa52  mov     [rbx+rcx*8+8], rsi
0x14002aa57  mov     [rbx+rcx*8+10h], eax
0x14002aa5b  mov     [rbx+rcx*8+14h], r14d
0x14002aa60  inc     dword ptr [rbx]
0x14002aa62  sub     edx, eax
0x14002aa64  jz      short loc_14002AA76
0x14002aa66  mov     [rbx+rcx*8+18h], r15
0x14002aa6b  mov     [rbx+rcx*8+20h], edx
0x14002aa6f  mov     [rbx+rcx*8+24h], r14d
0x14002aa74  inc     dword ptr [rbx]
0x14002aa76  test    dword ptr [rdi+8], 400h
0x14002aa7d  jz      short loc_14002AAC5
0x14002aa7f  mov     rsi, [rdi+60h]
0x14002aa83  mov     rcx, rsi; Sid
0x14002aa86  call    cs:__imp_RtlLengthSid
0x14002aa8d  nop     dword ptr [rax+rax+00h]
0x14002aa92  test    eax, eax
0x14002aa94  jz      short loc_14002AAC5
0x14002aa96  mov     ecx, [rbx]
0x14002aa98  lea     edx, [rax+7]
0x14002aa9b  add     rcx, rcx
0x14002aa9e  and     edx, 0FFFFFFF8h
0x14002aaa1  mov     [rbx+rcx*8+8], rsi
0x14002aaa6  mov     [rbx+rcx*8+10h], eax
0x14002aaaa  mov     [rbx+rcx*8+14h], r14d
0x14002aaaf  inc     dword ptr [rbx]
0x14002aab1  sub     edx, eax
0x14002aab3  jz      short loc_14002AAC5
0x14002aab5  mov     [rbx+rcx*8+18h], r15
0x14002aaba  mov     [rbx+rcx*8+20h], edx
0x14002aabe  mov     [rbx+rcx*8+24h], r14d
0x14002aac3  inc     dword ptr [rbx]
0x14002aac5  test    dword ptr [rdi+8], 800h
0x14002aacc  mov     rsi, [rsp+38h+arg_0]
0x14002aad1  jz      short loc_14002AB26
0x14002aad3  mov     rcx, [rdi+68h]
0x14002aad7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14002aade  xchg    ax, ax
0x14002aae0  cmp     [rcx+rax*2+2], r14w
0x14002aae6  lea     rax, [rax+1]
0x14002aaea  jnz     short loc_14002AAE0
0x14002aaec  lea     edx, ds:2[rax*2]
0x14002aaf3  test    edx, edx
0x14002aaf5  jz      short loc_14002AB26
0x14002aaf7  mov     eax, [rbx]
0x14002aaf9  add     rax, rax
0x14002aafc  mov     [rbx+rax*8+8], rcx
0x14002ab01  lea     ecx, [rdx+7]
0x14002ab04  mov     [rbx+rax*8+10h], edx
0x14002ab08  and     ecx, 0FFFFFFF8h
0x14002ab0b  mov     [rbx+rax*8+14h], r14d
0x14002ab10  inc     dword ptr [rbx]
0x14002ab12  sub     ecx, edx
0x14002ab14  jz      short loc_14002AB26
0x14002ab16  mov     [rbx+rax*8+18h], r15
0x14002ab1b  mov     [rbx+rax*8+20h], ecx
0x14002ab1f  mov     [rbx+rax*8+24h], r14d
0x14002ab24  inc     dword ptr [rbx]
0x14002ab26  test    dword ptr [rdi+8], 2000h
0x14002ab2d  jz      short loc_14002AB6A
0x14002ab2f  mov     edx, [rdi+78h]
0x14002ab32  test    edx, edx
0x14002ab34  jz      short loc_14002AB6A
0x14002ab36  mov     ecx, [rbx]
0x14002ab38  mov     rax, [rdi+80h]
0x14002ab3f  shl     rcx, 4
0x14002ab43  add     rcx, rbx
0x14002ab46  mov     [rcx+8], rax
0x14002ab4a  lea     eax, [rdx+7]
0x14002ab4d  mov     [rcx+10h], edx
0x14002ab50  and     eax, 0FFFFFFF8h
0x14002ab53  mov     [rcx+14h], r14d
0x14002ab57  inc     dword ptr [rbx]
0x14002ab59  sub     eax, edx
0x14002ab5b  jz      short loc_14002AB6A
0x14002ab5d  mov     [rcx+18h], r15
0x14002ab61  mov     [rcx+20h], eax
0x14002ab64  mov     [rcx+24h], r14d
0x14002ab68  inc     dword ptr [rbx]
0x14002ab6a  movsxd  rax, dword ptr [rdi+88h]
0x14002ab71  cmp     eax, 14h; switch 21 cases
0x14002ab74  ja      def_14002AB8B; jumptable 000000014002AB8B default case, cases 11,12
0x14002ab7a  lea     rdx, cs:140000000h
0x14002ab81  mov     ecx, ds:(jpt_14002AB8B - 140000000h)[rdx+rax*4]
0x14002ab88  add     rcx, rdx
0x14002ab8b  jmp     rcx; switch jump
0x14002ab91  mov     ecx, [rbx]; jumptable 000000014002AB8B cases 0,2
0x14002ab93  mov     rax, [rdi+90h]
0x14002ab9a  add     rcx, rcx
0x14002ab9d  mov     [rbx+rcx*8+8], rax
0x14002aba2  mov     qword ptr [rbx+rcx*8+10h], 78h ; 'x'
0x14002abab  mov     rcx, rbx
0x14002abae  inc     dword ptr [rbx]
0x14002abb0  mov     rdx, [rdi+90h]
0x14002abb7  mov     rdx, [rdx+40h]
0x14002abbb  call    BfeEventDataPushStr
0x14002abc0  mov     rdx, [rdi+90h]
0x14002abc7  mov     rdx, [rdx+48h]
0x14002abcb  call    BfeEventDataPushStr
0x14002abd0  mov     rdx, [rdi+90h]
0x14002abd7  lea     r9, [rbx+190h]
0x14002abde  mov     r8d, [rdx+50h]
0x14002abe2  mov     rdx, [rdx+58h]
0x14002abe6  call    BfeEventDataPushStrArray
0x14002abeb  mov     rdx, [rdi+90h]
0x14002abf2  lea     r9, [rbx+198h]
0x14002abf9  mov     rcx, rbx
0x14002abfc  mov     r8d, [rdx+60h]
0x14002ac00  mov     rdx, [rdx+68h]
0x14002ac04  call    BfeEventDataPushStrArray
0x14002ac09  jmp     loc_14002AE3D
0x14002ac0e  mov     ecx, [rbx]; jumptable 000000014002AB8B case 1
0x14002ac10  mov     rax, [rdi+90h]
0x14002ac17  add     rcx, rcx
0x14002ac1a  mov     [rbx+rcx*8+8], rax
0x14002ac1f  mov     qword ptr [rbx+rcx*8+10h], 58h ; 'X'
0x14002ac28  inc     dword ptr [rbx]
0x14002ac2a  mov     rdx, [rdi+90h]
0x14002ac31  mov     r8d, [rbx]
0x14002ac34  cmp     dword ptr [rdx+14h], 1
0x14002ac38  jnz     loc_14002AE3D
0x14002ac3e  mov     ecx, [rdx+18h]
0x14002ac41  sub     ecx, 100h
0x14002ac47  jz      short loc_14002ACA8
0x14002ac49  cmp     ecx, 1
0x14002ac4c  jnz     def_14002AB8B; jumptable 000000014002AB8B default case, cases 11,12
0x14002ac52  mov     rax, [rdx+20h]
0x14002ac56  mov     ecx, r8d
0x14002ac59  shl     rcx, 4
0x14002ac5d  add     rcx, rbx
0x14002ac60  mov     [rcx+8], rax
0x14002ac64  mov     qword ptr [rcx+10h], 11h
0x14002ac6c  inc     dword ptr [rbx]
0x14002ac6e  mov     [rcx+18h], r15
0x14002ac72  mov     qword ptr [rcx+20h], 7
0x14002ac7a  inc     dword ptr [rbx]
0x14002ac7c  mov     ecx, [rbx]
0x14002ac7e  mov     rax, [rdx+30h]
0x14002ac82  shl     rcx, 4
0x14002ac86  add     rcx, rbx
0x14002ac89  mov     [rcx+8], rax
0x14002ac8d  mov     qword ptr [rcx+10h], 11h
0x14002ac95  inc     dword ptr [rbx]
0x14002ac97  mov     [rcx+18h], r15
0x14002ac9b  mov     qword ptr [rcx+20h], 7
0x14002aca3  jmp     loc_14002AE3B
0x14002aca8  mov     rax, [rdx+20h]
0x14002acac  mov     rcx, r8
0x14002acaf  add     rcx, rcx
0x14002acb2  mov     [rbx+rcx*8+8], rax
0x14002acb7  mov     qword ptr [rbx+rcx*8+10h], 8
0x14002acc0  inc     dword ptr [rbx]
0x14002acc2  mov     ecx, [rbx]
0x14002acc4  mov     rax, [rdx+30h]
0x14002acc8  add     rcx, rcx
0x14002accb  mov     qword ptr [rbx+rcx*8+10h], 8
0x14002acd4  jmp     loc_14002AE36
0x14002acd9  mov     ecx, [rbx]; jumptable 000000014002AB8B case 3
0x14002acdb  mov     rax, [rdi+90h]
0x14002ace2  add     rcx, rcx
0x14002ace5  mov     [rbx+rcx*8+8], rax
0x14002acea  mov     qword ptr [rbx+rcx*8+10h], 38h ; '8'
0x14002acf3  inc     dword ptr [rbx]
0x14002acf5  mov     r8, [rdi+90h]
0x14002acfc  mov     eax, [rbx]
0x14002acfe  mov     edx, [r8+20h]
0x14002ad02  test    edx, edx
0x14002ad04  jz      loc_14002AE3D
0x14002ad0a  mov     ecx, eax
0x14002ad0c  mov     rax, [r8+28h]
0x14002ad10  shl     rcx, 4
0x14002ad14  add     rcx, rbx
0x14002ad17  mov     [rcx+8], rax
0x14002ad1b  lea     eax, [rdx+7]
0x14002ad1e  mov     [rcx+10h], edx
0x14002ad21  and     eax, 0FFFFFFF8h
0x14002ad24  mov     [rcx+14h], r14d
0x14002ad28  inc     dword ptr [rbx]
0x14002ad2a  sub     eax, edx
0x14002ad2c  jz      loc_14002AE3D
0x14002ad32  mov     [rcx+18h], r15
0x14002ad36  mov     [rcx+20h], eax
0x14002ad39  mov     [rcx+24h], r14d
0x14002ad3d  jmp     loc_14002AE3B
0x14002ad42  mov     ecx, [rbx]; jumptable 000000014002AB8B case 5
0x14002ad44  mov     rax, [rdi+90h]
0x14002ad4b  shl     rcx, 4
0x14002ad4f  add     rcx, rbx
0x14002ad52  mov     [rcx+8], rax
0x14002ad56  mov     qword ptr [rcx+10h], 2Ch ; ','
0x14002ad5e  inc     dword ptr [rbx]
0x14002ad60  mov     [rcx+18h], r15
0x14002ad64  mov     qword ptr [rcx+20h], 4
0x14002ad6c  jmp     loc_14002AE3B
0x14002ad71  mov     ecx, [rbx]; jumptable 000000014002AB8B cases 7,8
0x14002ad73  mov     rax, [rdi+90h]
0x14002ad7a  add     rcx, rcx
0x14002ad7d  mov     qword ptr [rbx+rcx*8+10h], 18h
0x14002ad86  jmp     loc_14002AE36
0x14002ad8b  mov     ecx, [rbx]; jumptable 000000014002AB8B case 9
0x14002ad8d  mov     rax, [rdi+90h]
0x14002ad94  add     rcx, rcx
0x14002ad97  mov     [rbx+rcx*8+8], rax
0x14002ad9c  mov     qword ptr [rbx+rcx*8+10h], 68h ; 'h'
0x14002ada5  inc     dword ptr [rbx]
0x14002ada7  mov     r8, [rdi+90h]
0x14002adae  mov     eax, [rbx]
0x14002adb0  mov     edx, [r8+50h]
0x14002adb4  test    edx, edx
0x14002adb6  jz      loc_14002AE3D
0x14002adbc  mov     ecx, eax
0x14002adbe  mov     rax, [r8+58h]
0x14002adc2  jmp     loc_14002AD10
0x14002adc7  mov     ecx, [rbx]; jumptable 000000014002AB8B case 10
0x14002adc9  mov     rax, [rdi+90h]
0x14002add0  shl     rcx, 4
0x14002add4  add     rcx, rbx
0x14002add7  mov     [rcx+8], rax
0x14002addb  mov     qword ptr [rcx+10h], 4
0x14002ade3  inc     dword ptr [rbx]
0x14002ade5  mov     [rcx+18h], r15
0x14002ade9  mov     qword ptr [rcx+20h], 4
0x14002adf1  jmp     short loc_14002AE3B
0x14002adf3  mov     ecx, [rbx]; jumptable 000000014002AB8B cases 13,14,16,17
0x14002adf5  mov     rax, [rdi+90h]
0x14002adfc  add     rcx, rcx
0x14002adff  mov     qword ptr [rbx+rcx*8+10h], 28h ; '('
0x14002ae08  jmp     short loc_14002AE36
0x14002ae0a  mov     ecx, [rbx]; jumptable 000000014002AB8B cases 15,18
0x14002ae0c  mov     rax, [rdi+90h]
0x14002ae13  add     rcx, rcx
0x14002ae16  mov     qword ptr [rbx+rcx*8+10h], 30h ; '0'
0x14002ae1f  jmp     short loc_14002AE36
0x14002ae21  mov     ecx, [rbx]; jumptable 000000014002AB8B cases 4,6,19,20
0x14002ae23  mov     rax, [rdi+90h]
0x14002ae2a  add     rcx, rcx
0x14002ae2d  mov     qword ptr [rbx+rcx*8+10h], 20h ; ' '
0x14002ae36  mov     [rbx+rcx*8+8], rax
0x14002ae3b  inc     dword ptr [rbx]
0x14002ae3d  mov     eax, [rdi+98h]
0x14002ae43  test    al, 1
0x14002ae45  jz      short loc_14002AE56
0x14002ae47  mov     rdx, [rdi+0A8h]
0x14002ae4e  mov     rcx, rbx
0x14002ae51  call    BfeEventDataPushStr
0x14002ae56  movzx   eax, word ptr [rdi+0B0h]
  ... truncated ...
```
