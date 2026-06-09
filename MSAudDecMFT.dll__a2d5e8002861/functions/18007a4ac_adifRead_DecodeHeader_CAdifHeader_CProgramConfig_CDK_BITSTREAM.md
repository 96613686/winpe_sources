# adifRead_DecodeHeader(CAdifHeader *,CProgramConfig *,CDK_BITSTREAM *)

- ea: `0x18007a4ac`
- end: `0x18007a6af`
- name: `?adifRead_DecodeHeader@@YA?AW4TRANSPORTDEC_ERROR@@PEAUCAdifHeader@@PEAUCProgramConfig@@PEAUCDK_BITSTREAM@@@Z`
- size: `515`
- prototype: `enum TRANSPORTDEC_ERROR __high(struct CAdifHeader *, struct CProgramConfig *, struct CDK_BITSTREAM *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000e684`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x1800127d8`
- `0x18004c56c`
- `0x18007a4ac`

## pseudocode

```c
__int64 __fastcall adifRead_DecodeHeader(__int64 a1, struct CProgramConfig *a2, __int64 a3)
{
  __int64 v6; // r8
  int v7; // edi
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // r8
  char v13; // al
  __int64 v14; // r8
  unsigned int v15; // eax
  int v16; // eax
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  int v22; // eax
  bool v23; // zf
  unsigned int v24; // eax
  int v25; // eax
  int i; // ebp
  int v27; // r8d
  int v28; // ecx
  int v29; // edi
  int v30; // eax
  int v31; // r8d
  int v32; // eax

  CDKsyncCache_0((int *)a3);
  v7 = *(_DWORD *)(a3 + 8);
  if ( v7 < 63 )
    return 257;
  if ( (unsigned int)CDKreadBits((_DWORD *)a3, 8, v6) != 65
    || (unsigned int)CDKreadBits((_DWORD *)a3, 8, v9) != 68
    || (unsigned int)CDKreadBits((_DWORD *)a3, 8, v10) != 73
    || (unsigned int)CDKreadBits((_DWORD *)a3, 8, v11) != 70 )
  {
    return 258;
  }
  v13 = CDKreadBits((_DWORD *)a3, 1, v12);
  *(_BYTE *)(a1 + 8) = v13;
  if ( v13 )
  {
    v15 = *(_DWORD *)(a3 + 4);
    if ( v15 <= 0x48 || *(_DWORD *)(a3 + 40) )
    {
      CDKsyncCache_0((int *)a3);
      v16 = *(_DWORD *)(a3 + 20) + 72;
      *(_DWORD *)(a3 + 8) += *(_BYTE *)(a3 + 40) != 0 ? 72 : -72;
      *(_DWORD *)(a3 + 20) = v16 & (*(_DWORD *)(a3 + 36) - 1);
    }
    else
    {
      *(_DWORD *)(a3 + 4) = v15 - 72;
    }
  }
  *(_BYTE *)(a1 + 9) = CDKreadBits((_DWORD *)a3, 1, v14);
  *(_BYTE *)(a1 + 10) = CDKreadBits((_DWORD *)a3, 1, v17);
  *(_BYTE *)(a1 + 11) = CDKreadBits((_DWORD *)a3, 1, v18);
  *(_DWORD *)(a1 + 4) = (unsigned int)CDKreadBits((_DWORD *)a3, 16, v19) << 7;
  *(_DWORD *)(a1 + 4) |= CDKreadBits((_DWORD *)a3, 7, v20);
  v22 = CDKreadBits((_DWORD *)a3, 4, v21);
  v23 = *(_BYTE *)(a1 + 11) == 0;
  *(_DWORD *)a1 = v22 + 1;
  if ( v23 )
  {
    v24 = *(_DWORD *)(a3 + 4);
    if ( v24 <= 0x14 || *(_DWORD *)(a3 + 40) )
    {
      CDKsyncCache_0((int *)a3);
      v25 = *(_DWORD *)(a3 + 20) + 20;
      *(_DWORD *)(a3 + 8) += *(_BYTE *)(a3 + 40) != 0 ? 20 : -20;
      *(_DWORD *)(a3 + 20) = v25 & (*(_DWORD *)(a3 + 36) - 1);
    }
    else
    {
      *(_DWORD *)(a3 + 4) = v24 - 20;
    }
  }
  for ( i = 0; i < *(_DWORD *)a1; ++i )
    CProgramConfig_Read(a2, (struct CDK_BITSTREAM *)a3, (unsigned int)v7);
  CDKsyncCache_0((int *)a3);
  v27 = *(_DWORD *)(a3 + 8);
  if ( *(_DWORD *)(a3 + 40) )
  {
    CDK_put(a3 + 8, 0, (v7 - v27) & 7);
  }
  else
  {
    v28 = *(_DWORD *)(a3 + 20);
    v29 = (v27 - v7) & 7;
    v30 = v29 + v27;
    v31 = v27 - v29;
    if ( *(_BYTE *)(a3 + 40) )
      v31 = v30;
    v32 = *(_DWORD *)(a3 + 36) - 1;
    *(_DWORD *)(a3 + 8) = v31;
    *(_DWORD *)(a3 + 20) = v32 & (v29 + v28);
  }
  return 0;
}

```

## disassembly

```asm
0x18007a4ac  push    rbx
0x18007a4ae  push    rbp
0x18007a4af  push    rsi
0x18007a4b0  push    rdi
0x18007a4b1  push    r12
0x18007a4b3  push    r14
0x18007a4b5  sub     rsp, 28h
0x18007a4b9  mov     rsi, rcx
0x18007a4bc  mov     rbx, r8
0x18007a4bf  mov     rcx, r8
0x18007a4c2  mov     r14, rdx
0x18007a4c5  call    CDKsyncCache_0
0x18007a4ca  mov     edi, [rbx+8]
0x18007a4cd  cmp     edi, 3Fh ; '?'
0x18007a4d0  jge     short loc_18007A4DC
0x18007a4d2  mov     eax, 101h
0x18007a4d7  jmp     loc_18007A6A1
0x18007a4dc  mov     ebp, 8
0x18007a4e1  mov     rcx, rbx
0x18007a4e4  mov     edx, ebp
0x18007a4e6  call    CDKreadBits
0x18007a4eb  cmp     eax, 41h ; 'A'
0x18007a4ee  jnz     loc_18007A69C
0x18007a4f4  mov     edx, ebp
0x18007a4f6  mov     rcx, rbx
0x18007a4f9  call    CDKreadBits
0x18007a4fe  cmp     eax, 44h ; 'D'
0x18007a501  jnz     loc_18007A69C
0x18007a507  mov     edx, ebp
0x18007a509  mov     rcx, rbx
0x18007a50c  call    CDKreadBits
0x18007a511  cmp     eax, 49h ; 'I'
0x18007a514  jnz     loc_18007A69C
0x18007a51a  mov     edx, ebp
0x18007a51c  mov     rcx, rbx
0x18007a51f  call    CDKreadBits
0x18007a524  cmp     eax, 46h ; 'F'
0x18007a527  jnz     loc_18007A69C
0x18007a52d  lea     r12d, [rbp-7]
0x18007a531  mov     rcx, rbx
0x18007a534  mov     edx, r12d
0x18007a537  call    CDKreadBits
0x18007a53c  mov     [rsi+8], al
0x18007a53f  test    al, al
0x18007a541  jz      short loc_18007A585
0x18007a543  mov     eax, [rbx+4]
0x18007a546  cmp     eax, 48h ; 'H'
0x18007a549  jbe     short loc_18007A559
0x18007a54b  cmp     dword ptr [rbx+28h], 0
0x18007a54f  jnz     short loc_18007A559
0x18007a551  add     eax, 0FFFFFFB8h
0x18007a554  mov     [rbx+4], eax
0x18007a557  jmp     short loc_18007A585
0x18007a559  mov     rcx, rbx
0x18007a55c  call    CDKsyncCache_0
0x18007a561  mov     al, [rbx+28h]
0x18007a564  neg     al
0x18007a566  mov     eax, [rbx+14h]
0x18007a569  sbb     ecx, ecx
0x18007a56b  add     eax, 48h ; 'H'
0x18007a56e  and     ecx, 90h
0x18007a574  add     ecx, 0FFFFFFB8h
0x18007a577  add     [rbx+8], ecx
0x18007a57a  mov     ecx, [rbx+24h]
0x18007a57d  sub     ecx, r12d
0x18007a580  and     ecx, eax
0x18007a582  mov     [rbx+14h], ecx
0x18007a585  mov     edx, r12d
0x18007a588  mov     rcx, rbx
0x18007a58b  call    CDKreadBits
0x18007a590  mov     edx, r12d
0x18007a593  mov     [rsi+9], al
0x18007a596  mov     rcx, rbx
0x18007a599  call    CDKreadBits
0x18007a59e  mov     edx, r12d
0x18007a5a1  mov     [rsi+0Ah], al
0x18007a5a4  mov     rcx, rbx
0x18007a5a7  call    CDKreadBits
0x18007a5ac  mov     edx, 10h
0x18007a5b1  mov     [rsi+0Bh], al
0x18007a5b4  mov     rcx, rbx
0x18007a5b7  call    CDKreadBits
0x18007a5bc  shl     eax, 7
0x18007a5bf  mov     edx, 7
0x18007a5c4  mov     rcx, rbx
0x18007a5c7  mov     [rsi+4], eax
0x18007a5ca  call    CDKreadBits
0x18007a5cf  or      [rsi+4], eax
0x18007a5d2  mov     edx, 4
0x18007a5d7  mov     rcx, rbx
0x18007a5da  call    CDKreadBits
0x18007a5df  add     eax, r12d
0x18007a5e2  cmp     byte ptr [rsi+0Bh], 0
0x18007a5e6  mov     [rsi], eax
0x18007a5e8  jnz     short loc_18007A629
0x18007a5ea  mov     eax, [rbx+4]
0x18007a5ed  cmp     eax, 14h
0x18007a5f0  jbe     short loc_18007A600
0x18007a5f2  cmp     dword ptr [rbx+28h], 0
0x18007a5f6  jnz     short loc_18007A600
0x18007a5f8  add     eax, 0FFFFFFECh
0x18007a5fb  mov     [rbx+4], eax
0x18007a5fe  jmp     short loc_18007A629
0x18007a600  mov     rcx, rbx
0x18007a603  call    CDKsyncCache_0
0x18007a608  mov     al, [rbx+28h]
0x18007a60b  neg     al
0x18007a60d  mov     eax, [rbx+14h]
0x18007a610  sbb     ecx, ecx
0x18007a612  add     eax, 14h
0x18007a615  and     ecx, 28h
0x18007a618  add     ecx, 0FFFFFFECh
0x18007a61b  add     [rbx+8], ecx
0x18007a61e  mov     ecx, [rbx+24h]
0x18007a621  sub     ecx, r12d
0x18007a624  and     ecx, eax
0x18007a626  mov     [rbx+14h], ecx
0x18007a629  xor     ebp, ebp
0x18007a62b  cmp     [rsi], ebp
0x18007a62d  jle     short loc_18007A644
0x18007a62f  mov     r8d, edi; unsigned int
0x18007a632  mov     rdx, rbx; struct CDK_BITSTREAM *
0x18007a635  mov     rcx, r14; struct CProgramConfig *
0x18007a638  call    ?CProgramConfig_Read@@YAXPEAUCProgramConfig@@PEAUCDK_BITSTREAM@@I@Z; CProgramConfig_Read(CProgramConfig *,CDK_BITSTREAM *,uint)
0x18007a63d  add     ebp, r12d
0x18007a640  cmp     ebp, [rsi]
0x18007a642  jl      short loc_18007A62F
0x18007a644  mov     rcx, rbx
0x18007a647  call    CDKsyncCache_0
0x18007a64c  cmp     dword ptr [rbx+28h], 0
0x18007a650  mov     r8d, [rbx+8]
0x18007a654  jnz     short loc_18007A683
0x18007a656  mov     ecx, [rbx+14h]
0x18007a659  sub     edi, r8d
0x18007a65c  neg     edi
0x18007a65e  and     edi, 7
0x18007a661  lea     eax, [rdi+r8]
0x18007a665  sub     r8d, edi
0x18007a668  cmp     byte ptr [rbx+28h], 0
0x18007a66c  cmovnz  r8d, eax
0x18007a670  mov     eax, [rbx+24h]
0x18007a673  sub     eax, r12d
0x18007a676  mov     [rbx+8], r8d
0x18007a67a  add     ecx, edi
0x18007a67c  and     ecx, eax
0x18007a67e  mov     [rbx+14h], ecx
0x18007a681  jmp     short loc_18007A698
0x18007a683  sub     r8d, edi
0x18007a686  lea     rcx, [rbx+8]
0x18007a68a  neg     r8d
0x18007a68d  xor     edx, edx
0x18007a68f  and     r8d, 7
0x18007a693  call    CDK_put
0x18007a698  xor     eax, eax
0x18007a69a  jmp     short loc_18007A6A1
0x18007a69c  mov     eax, 102h
0x18007a6a1  add     rsp, 28h
0x18007a6a5  pop     r14
0x18007a6a7  pop     r12
0x18007a6a9  pop     rdi
0x18007a6aa  pop     rsi
0x18007a6ab  pop     rbp
0x18007a6ac  pop     rbx
0x18007a6ad  retn
```
