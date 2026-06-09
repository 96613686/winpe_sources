# CDK_QmfDomain_Configure(CDK_QMF_DOMAIN *)

- ea: `0x18000a468`
- end: `0x18000a808`
- name: `?CDK_QmfDomain_Configure@@YA?AW4QMF_DOMAIN_ERROR@@PEAUCDK_QMF_DOMAIN@@@Z`
- size: `928`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000a810`
- `0x18007f544`

## callees

- `0x180006320`
- `0x180006914`
- `0x180009954`
- `0x18000a468`
- `0x180040934`
- `0x1800737b8`

## pseudocode

```c
__int64 __fastcall CDK_QmfDomain_Configure(__int64 a1)
{
  __int64 v1; // rbx
  _BYTE *v2; // rdx
  __int64 v3; // r8
  char v4; // cl
  int v5; // ecx
  unsigned int v6; // esi
  char v8; // al
  int v9; // r15d
  int v10; // r14d
  int v11; // ebp
  _QWORD *v12; // rdi
  int v13; // r11d
  int v14; // r8d
  int v15; // r8d
  __int64 v16; // rcx
  int v17; // ecx
  int v18; // r15d
  int v19; // r11d
  int v20; // r11d
  int v21; // ecx
  int v22; // [rsp+20h] [rbp-48h]

  v1 = a1;
  LOBYTE(a1) = *(_BYTE *)(a1 + 69);
  v2 = (_BYTE *)(v1 + 67);
  if ( (!(_BYTE)a1 || *v2 == 64) && *(_BYTE *)(v1 + 57) <= *v2 )
  {
    if ( *(_BYTE *)(v1 + 68) != (_BYTE)a1
      || *(_BYTE *)(v1 + 66) != *v2
      || (v3 = 0, *(_BYTE *)(v1 + 62) != *(_BYTE *)(v1 + 63)) )
    {
      v15 = 0;
      if ( (_BYTE)a1 )
      {
        do
        {
          v16 = v15++;
          a1 = v16 << 7;
          *(_BYTE *)(a1 + v1 + 153) = *v2;
          *(_BYTE *)(v1 + 66) = *v2;
          *(_BYTE *)(a1 + v1 + 152) = *(_BYTE *)(v1 + 63);
          LODWORD(a1) = *(unsigned __int8 *)(v1 + 69);
        }
        while ( v15 < (int)a1 );
      }
      *(_BYTE *)(v1 + 68) = a1;
      v3 = 1;
    }
    v4 = *(_BYTE *)(v1 + 2);
    if ( *(_BYTE *)(v1 + 1) != v4
      || *(_BYTE *)(v1 + 56) != *(_BYTE *)(v1 + 57)
      || *(_BYTE *)(v1 + 62) != *(_BYTE *)(v1 + 63)
      || *(_BYTE *)(v1 + 64) != *(_BYTE *)(v1 + 65)
      || *(_BYTE *)(v1 + 3) != *(_BYTE *)(v1 + 4)
      || *(_WORD *)(v1 + 58) != *(_WORD *)(v1 + 60)
      || *(_BYTE *)(v1 + 5) != *(_BYTE *)(v1 + 6) )
    {
      *(_BYTE *)(v1 + 56) = *(_BYTE *)(v1 + 57);
      *(_BYTE *)(v1 + 62) = *(_BYTE *)(v1 + 63);
      *(_BYTE *)(v1 + 64) = *(_BYTE *)(v1 + 65);
      *(_BYTE *)(v1 + 3) = *(_BYTE *)(v1 + 4);
      *(_WORD *)(v1 + 58) = *(_WORD *)(v1 + 60);
      v8 = *(_BYTE *)(v1 + 6);
      *(_BYTE *)(v1 + 1) = v4;
      *(_BYTE *)(v1 + 5) = v8;
      if ( (unsigned int)CDK_QmfDomain_AllocatePersistentMemory(v1, v2, v3) )
        goto LABEL_37;
      if ( *(_BYTE *)(v1 + 56) == 32 && *(_WORD *)(v1 + 58) == 32 && (*(_BYTE *)(v1 + 48) & 0x14) == 0 )
        *(_DWORD *)(v1 + 52) |= 0x40u;
      LODWORD(v3) = 1;
    }
    v5 = *(_DWORD *)(v1 + 52);
    v6 = 0;
    if ( *(_DWORD *)(v1 + 48) == v5 )
    {
      if ( !(_DWORD)v3 )
        return v6;
    }
    else
    {
      if ( (v5 & 0x14) == 0x14 )
      {
        v5 &= ~4u;
        *(_DWORD *)(v1 + 52) = v5;
      }
      *(_DWORD *)(v1 + 48) = v5;
    }
    v9 = 0;
    if ( *(_BYTE *)(v1 + 5) && *(_BYTE *)(v1 + 68) == 1 )
    {
      v17 = *(unsigned __int8 *)(v1 + 62);
      v18 = v17 * *(unsigned __int8 *)(v1 + 56);
      *(_BYTE *)(v1 + 281) = *(_BYTE *)(v1 + 56);
      *(_BYTE *)(v1 + 280) = v17;
      v9 = 2 * v18;
    }
    v10 = 2 * *(unsigned __int8 *)(v1 + 152) * *(unsigned __int8 *)(v1 + 153);
    v11 = v9 + v10 * *(unsigned __int8 *)(v1 + 68);
    if ( (unsigned int)v11 <= 0x2800 )
    {
      v12 = (_QWORD *)(v1 + 8);
      if ( v11 && !*v12 )
        *v12 = CDKaalloc_L(0x2000);
      if ( (unsigned int)v11 > 0x800 && !*(_QWORD *)(v1 + 16) )
        *(_QWORD *)(v1 + 16) = CDKaalloc_L(0x2000);
      if ( (unsigned int)v11 > 0x1000 && !*(_QWORD *)(v1 + 24) )
        *(_QWORD *)(v1 + 24) = CDKaalloc_L(0x2000);
      if ( v11 > 6144 && !*(_QWORD *)(v1 + 32) )
        *(_QWORD *)(v1 + 32) = CDKaalloc_L(0x2000);
      if ( v11 > 0x2000 && !*(_QWORD *)(v1 + 40) )
        *(_QWORD *)(v1 + 40) = CDKaalloc_L(0x2000);
      v13 = 0;
      if ( *(_BYTE *)(v1 + 68) )
      {
        do
        {
          CDK_QmfDomain_FeedWorkBuffer(v1, v13, v1 + 8, (unsigned __int16)v10 * (unsigned __int16)v13, v22, v10);
          v13 = v19 + 1;
        }
        while ( v13 < *(unsigned __int8 *)(v1 + 68) );
      }
      if ( *(_BYTE *)(v1 + 5) )
      {
        while ( v13 < *(unsigned __int8 *)(v1 + 1) )
        {
          CDK_QmfDomain_FeedWorkBuffer(v1, 1, v1 + 8, (unsigned __int16)v10 * *(unsigned __int8 *)(v1 + 68), v22, v9);
          v13 = v20 + 1;
        }
      }
      v14 = 0;
      if ( *(_BYTE *)(v1 + 3) )
      {
        do
        {
          LODWORD(v2) = 10 * v14;
          if ( !*(_DWORD *)(v1 + 80LL * v14 + 1144) && !*(_DWORD *)(v1 + 80LL * v14 + 1148) )
          {
            v21 = 64;
            *(_DWORD *)(v1 + 80LL * v14 + 1144) = *(unsigned __int8 *)(v1 + 57);
            if ( *(unsigned __int16 *)(v1 + 60) < 0x40u )
              v21 = *(unsigned __int16 *)(v1 + 60);
            *(_DWORD *)(v1 + 80LL * v14 + 1148) = v21;
          }
          ++v14;
        }
        while ( v14 < *(unsigned __int8 *)(v1 + 3) );
      }
      if ( !(unsigned int)CDK_QmfDomain_InitFilterBank((struct CDK_QMF_DOMAIN *)v1, (unsigned int)v2) )
        return v6;
      v6 = 2;
      goto LABEL_33;
    }
LABEL_37:
    v6 = 1;
LABEL_33:
    CDK_QmfDomain_FreeMem((struct CDK_QMF_DOMAIN *)v1);
    return v6;
  }
  return 2;
}

```

## disassembly

```asm
0x18000a468  push    rbx
0x18000a46a  push    rbp
0x18000a46b  push    rsi
0x18000a46c  push    rdi
0x18000a46d  push    r13
0x18000a46f  push    r14
0x18000a471  push    r15
0x18000a473  sub     rsp, 30h
0x18000a477  mov     rbx, rcx
0x18000a47a  mov     cl, [rcx+45h]
0x18000a47d  lea     rdx, [rbx+43h]; unsigned int
0x18000a481  test    cl, cl
0x18000a483  jnz     loc_18000A561
0x18000a489  mov     al, [rdx]
0x18000a48b  cmp     [rbx+39h], al
0x18000a48e  ja      loc_18000A56A
0x18000a494  mov     edi, 1
0x18000a499  cmp     [rbx+44h], cl
0x18000a49c  jnz     loc_18000A630
0x18000a4a2  cmp     [rbx+42h], al
0x18000a4a5  jnz     loc_18000A630
0x18000a4ab  mov     al, [rbx+3Fh]
0x18000a4ae  xor     r8d, r8d
0x18000a4b1  cmp     [rbx+3Eh], al
0x18000a4b4  jnz     loc_18000A630
0x18000a4ba  mov     cl, [rbx+2]
0x18000a4bd  cmp     [rbx+1], cl
0x18000a4c0  jnz     short loc_18000A519
0x18000a4c2  mov     al, [rbx+39h]
0x18000a4c5  cmp     [rbx+38h], al
0x18000a4c8  jnz     short loc_18000A519
0x18000a4ca  mov     al, [rbx+3Fh]
0x18000a4cd  cmp     [rbx+3Eh], al
0x18000a4d0  jnz     short loc_18000A519
0x18000a4d2  mov     al, [rbx+41h]
0x18000a4d5  cmp     [rbx+40h], al
0x18000a4d8  jnz     short loc_18000A519
0x18000a4da  mov     al, [rbx+4]
0x18000a4dd  cmp     [rbx+3], al
0x18000a4e0  jnz     short loc_18000A519
0x18000a4e2  movzx   eax, word ptr [rbx+3Ch]
0x18000a4e6  cmp     [rbx+3Ah], ax
0x18000a4ea  jnz     short loc_18000A519
0x18000a4ec  mov     al, [rbx+6]
0x18000a4ef  cmp     [rbx+5], al
0x18000a4f2  jnz     short loc_18000A519
0x18000a4f4  mov     ecx, [rbx+34h]
0x18000a4f7  xor     esi, esi
0x18000a4f9  cmp     [rbx+30h], ecx
0x18000a4fc  jnz     loc_18000A68F
0x18000a502  test    r8d, r8d
0x18000a505  jnz     short loc_18000A571
0x18000a507  mov     eax, esi
0x18000a509  add     rsp, 30h
0x18000a50d  pop     r15
0x18000a50f  pop     r14
0x18000a511  pop     r13
0x18000a513  pop     rdi
0x18000a514  pop     rsi
0x18000a515  pop     rbp
0x18000a516  pop     rbx
0x18000a517  retn
0x18000a519  mov     al, [rbx+39h]
0x18000a51c  mov     [rbx+38h], al
0x18000a51f  mov     al, [rbx+3Fh]
0x18000a522  mov     [rbx+3Eh], al
0x18000a525  mov     al, [rbx+41h]
0x18000a528  mov     [rbx+40h], al
0x18000a52b  mov     al, [rbx+4]
0x18000a52e  mov     [rbx+3], al
0x18000a531  movzx   eax, word ptr [rbx+3Ch]
0x18000a535  mov     [rbx+3Ah], ax
0x18000a539  mov     al, [rbx+6]
0x18000a53c  mov     [rbx+1], cl
0x18000a53f  mov     rcx, rbx
0x18000a542  mov     [rbx+5], al
0x18000a545  call    CDK_QmfDomain_AllocatePersistentMemory
0x18000a54a  test    eax, eax
0x18000a54c  jnz     loc_18000A66D
0x18000a552  cmp     byte ptr [rbx+38h], 20h ; ' '
0x18000a556  jz      loc_18000A671
0x18000a55c  mov     r8d, edi
0x18000a55f  jmp     short loc_18000A4F4
0x18000a561  cmp     byte ptr [rdx], 40h ; '@'
0x18000a564  jz      loc_18000A489
0x18000a56a  mov     eax, 2
0x18000a56f  jmp     short loc_18000A509
0x18000a571  xor     r15d, r15d
0x18000a574  cmp     [rbx+5], sil
0x18000a578  jnz     loc_18000A6A6
0x18000a57e  movzx   r14d, byte ptr [rbx+99h]
0x18000a586  movzx   eax, byte ptr [rbx+98h]
0x18000a58d  movzx   ebp, byte ptr [rbx+44h]
0x18000a591  imul    r14d, eax
0x18000a595  add     r14d, r14d
0x18000a598  imul    ebp, r14d
0x18000a59c  add     ebp, r15d
0x18000a59f  cmp     ebp, 2800h
0x18000a5a5  ja      loc_18000A66D
0x18000a5ab  lea     rdi, [rbx+8]
0x18000a5af  mov     r13d, 2000h
0x18000a5b5  test    ebp, ebp
0x18000a5b7  jnz     loc_18000A6D3
0x18000a5bd  cmp     ebp, 800h
0x18000a5c3  ja      loc_18000A6EC
0x18000a5c9  cmp     ebp, 1000h
0x18000a5cf  ja      loc_18000A707
0x18000a5d5  cmp     ebp, 1800h
0x18000a5db  jg      loc_18000A722
0x18000a5e1  cmp     ebp, r13d
0x18000a5e4  jg      loc_18000A73D
0x18000a5ea  xor     r11d, r11d
0x18000a5ed  cmp     [rbx+44h], sil
0x18000a5f1  ja      loc_18000A758
0x18000a5f7  cmp     [rbx+5], sil
0x18000a5fb  jnz     loc_18000A7AD
0x18000a601  xor     r8d, r8d
0x18000a604  cmp     [rbx+3], sil
0x18000a608  ja      loc_18000A7BB
0x18000a60e  mov     rcx, rbx; struct CDK_QMF_DOMAIN *
0x18000a611  call    ?CDK_QmfDomain_InitFilterBank@@YAHPEAUCDK_QMF_DOMAIN@@I@Z; CDK_QmfDomain_InitFilterBank(CDK_QMF_DOMAIN *,uint)
0x18000a616  test    eax, eax
0x18000a618  jz      loc_18000A507
0x18000a61e  mov     esi, 2
0x18000a623  mov     rcx, rbx; struct CDK_QMF_DOMAIN *
0x18000a626  call    ?CDK_QmfDomain_FreeMem@@YAXPEAUCDK_QMF_DOMAIN@@@Z; CDK_QmfDomain_FreeMem(CDK_QMF_DOMAIN *)
0x18000a62b  jmp     loc_18000A507
0x18000a630  xor     r8d, r8d
0x18000a633  test    cl, cl
0x18000a635  jz      short loc_18000A662
0x18000a637  mov     al, [rdx]
0x18000a639  movsxd  rcx, r8d
0x18000a63c  add     r8d, edi
0x18000a63f  shl     rcx, 7
0x18000a643  mov     [rcx+rbx+99h], al
0x18000a64a  mov     al, [rdx]
0x18000a64c  mov     [rbx+42h], al
0x18000a64f  mov     al, [rbx+3Fh]
0x18000a652  mov     [rcx+rbx+98h], al
0x18000a659  movzx   ecx, byte ptr [rbx+45h]
0x18000a65d  cmp     r8d, ecx
0x18000a660  jl      short loc_18000A637
0x18000a662  mov     [rbx+44h], cl
0x18000a665  mov     r8d, edi
0x18000a668  jmp     loc_18000A4BA
0x18000a66d  mov     esi, edi
0x18000a66f  jmp     short loc_18000A623
0x18000a671  cmp     word ptr [rbx+3Ah], 20h ; ' '
0x18000a676  jnz     loc_18000A55C
0x18000a67c  test    byte ptr [rbx+30h], 14h
0x18000a680  jnz     loc_18000A55C
0x18000a686  or      dword ptr [rbx+34h], 40h
0x18000a68a  jmp     loc_18000A55C
0x18000a68f  mov     eax, ecx
0x18000a691  and     eax, 14h
0x18000a694  cmp     al, 14h
0x18000a696  jnz     short loc_18000A69E
0x18000a698  and     ecx, 0FFFFFFFBh
0x18000a69b  mov     [rbx+34h], ecx
0x18000a69e  mov     [rbx+30h], ecx
0x18000a6a1  jmp     loc_18000A571
0x18000a6a6  cmp     [rbx+44h], dil
0x18000a6aa  jnz     loc_18000A57E
0x18000a6b0  movzx   eax, byte ptr [rbx+38h]
0x18000a6b4  movzx   ecx, byte ptr [rbx+3Eh]
0x18000a6b8  mov     r15d, eax
0x18000a6bb  imul    r15d, ecx
0x18000a6bf  mov     [rbx+119h], al
0x18000a6c5  mov     [rbx+118h], cl
0x18000a6cb  add     r15d, r15d
0x18000a6ce  jmp     loc_18000A57E
0x18000a6d3  cmp     [rdi], rsi
0x18000a6d6  jnz     loc_18000A5BD
0x18000a6dc  mov     ecx, r13d
0x18000a6df  call    CDKaalloc_L
0x18000a6e4  mov     [rdi], rax
0x18000a6e7  jmp     loc_18000A5BD
0x18000a6ec  cmp     [rdi+8], rsi
0x18000a6f0  jnz     loc_18000A5C9
0x18000a6f6  mov     ecx, r13d
0x18000a6f9  call    CDKaalloc_L
0x18000a6fe  mov     [rdi+8], rax
0x18000a702  jmp     loc_18000A5C9
0x18000a707  cmp     [rdi+10h], rsi
0x18000a70b  jnz     loc_18000A5D5
0x18000a711  mov     ecx, r13d
0x18000a714  call    CDKaalloc_L
0x18000a719  mov     [rdi+10h], rax
0x18000a71d  jmp     loc_18000A5D5
0x18000a722  cmp     [rdi+18h], rsi
0x18000a726  jnz     loc_18000A5E1
0x18000a72c  mov     ecx, r13d
0x18000a72f  call    CDKaalloc_L
0x18000a734  mov     [rdi+18h], rax
0x18000a738  jmp     loc_18000A5E1
0x18000a73d  cmp     [rdi+20h], rsi
0x18000a741  jnz     loc_18000A5EA
0x18000a747  mov     ecx, r13d
0x18000a74a  call    CDKaalloc_L
0x18000a74f  mov     [rdi+20h], rax
0x18000a753  jmp     loc_18000A5EA
0x18000a758  movzx   eax, r14w
0x18000a75c  mov     r8, rdi
0x18000a75f  movzx   r9d, r11w
0x18000a763  mov     edx, r11d
0x18000a766  imul    r9d, eax
0x18000a76a  mov     rcx, rbx
0x18000a76d  mov     [rsp+68h+var_40], r14d
0x18000a772  call    CDK_QmfDomain_FeedWorkBuffer
0x18000a777  movzx   eax, byte ptr [rbx+44h]
0x18000a77b  inc     r11d
0x18000a77e  cmp     r11d, eax
0x18000a781  jl      short loc_18000A758
0x18000a783  jmp     loc_18000A5F7
0x18000a788  movzx   r9d, byte ptr [rbx+44h]
0x18000a78d  mov     r8, rdi
0x18000a790  movzx   ecx, r14w
0x18000a794  mov     edx, 1
0x18000a799  imul    r9d, ecx
0x18000a79d  mov     rcx, rbx
0x18000a7a0  mov     [rsp+68h+var_40], r15d
0x18000a7a5  call    CDK_QmfDomain_FeedWorkBuffer
0x18000a7aa  inc     r11d
0x18000a7ad  movzx   eax, byte ptr [rbx+1]
0x18000a7b1  cmp     r11d, eax
0x18000a7b4  jl      short loc_18000A788
0x18000a7b6  jmp     loc_18000A601
0x18000a7bb  movsxd  rax, r8d
0x18000a7be  lea     rdx, [rax+rax*4]
0x18000a7c2  add     rdx, rdx
0x18000a7c5  cmp     [rbx+rdx*8+478h], esi
0x18000a7cc  jnz     short loc_18000A7F7
0x18000a7ce  cmp     [rbx+rdx*8+47Ch], esi
0x18000a7d5  jnz     short loc_18000A7F7
0x18000a7d7  movzx   eax, byte ptr [rbx+39h]
0x18000a7db  mov     ecx, 40h ; '@'
0x18000a7e0  mov     [rbx+rdx*8+478h], eax
0x18000a7e7  movzx   eax, word ptr [rbx+3Ch]
0x18000a7eb  cmp     eax, ecx
0x18000a7ed  cmovb   ecx, eax
0x18000a7f0  mov     [rbx+rdx*8+47Ch], ecx
0x18000a7f7  movzx   eax, byte ptr [rbx+3]
0x18000a7fb  inc     r8d
0x18000a7fe  cmp     r8d, eax
0x18000a801  jl      short loc_18000A7BB
0x18000a803  jmp     loc_18000A60E
```
