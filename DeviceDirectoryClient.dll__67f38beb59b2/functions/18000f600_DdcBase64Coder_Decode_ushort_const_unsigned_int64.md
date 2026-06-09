# DdcBase64Coder::Decode(ushort const *,unsigned __int64)

- ea: `0x18000f600`
- end: `0x18000f7de`
- name: `?Decode@DdcBase64Coder@@QEAAJPEBG_K@Z`
- size: `478`
- prototype: `__int64 __fastcall(void **this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005b34`
- `0x1800063f4`
- `0x180006748`
- `0x180006da4`

## callees

- `0x1800028d4`
- `0x180002fc0`
- `0x1800032ac`
- `0x1800050b8`
- `0x18000f600`

## string_xrefs

- `0x18000f7b1`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcbase64coder.cpp`

## pseudocode

```c
__int64 __fastcall DdcBase64Coder::Decode(void **this, const unsigned __int16 *a2, unsigned __int64 a3)
{
  int v6; // edx
  int v7; // ecx
  unsigned __int64 v8; // rcx
  int v9; // eax
  int v10; // ebp
  int v11; // edx
  _BYTE *v12; // rsi
  unsigned __int8 i; // cl
  unsigned int v14; // ebx
  __int64 v15; // rcx
  _BYTE *v16; // r11
  __int64 v17; // rdx
  char v18; // r10
  unsigned __int8 v19; // r9
  unsigned __int8 v20; // r8
  char v21; // dl

  operator delete(*this);
  *this = 0;
  *((_DWORD *)this + 2) = 0;
  if ( !a3 || (a3 & 3) != 0 )
  {
    v12 = 0;
    v14 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        v6,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcbase64coder.cpp",
        60,
        "CBR(cchEncodedData > 0 && cchEncodedData % 4 == 0)");
  }
  else
  {
    v8 = 3 * (unsigned int)(a3 >> 2);
    v9 = v8 - 1;
    if ( a2[a3 - 1] != 61 )
      v9 = 3 * (a3 >> 2);
    v10 = v9 - 1;
    if ( a2[a3 - 2] != 61 )
      v10 = v9;
    v12 = operator new[](v8);
    if ( !(_BYTE)DdcBase64Coder::s_rgnDecodeTable )
    {
      LOBYTE(v11) = -1;
      memset_0(&DdcBase64Coder::s_rgnDecodeTable, v11, 0x80u);
      for ( i = 0; i < 0x41u; ++i )
      {
        if ( DdcBase64Coder::s_rgchBase64Digits[i] >= 0x80u )
        {
          v14 = -2147467259;
          goto LABEL_29;
        }
        *((_BYTE *)&DdcBase64Coder::s_rgnDecodeTable + DdcBase64Coder::s_rgchBase64Digits[i]) = i;
      }
      byte_18004970D = 0;
    }
    v15 = 0;
    v16 = v12;
    while ( v15 + 3 < a3 )
    {
      if ( a2[v15] >= 0x80u
        || a2[v15 + 1] >= 0x80u
        || a2[v15 + 2] >= 0x80u
        || (v17 = a2[v15 + 3], (unsigned __int16)v17 >= 0x80u)
        || (v18 = *((_BYTE *)&DdcBase64Coder::s_rgnDecodeTable + a2[v15]), v18 == -1)
        || (v19 = *((_BYTE *)&DdcBase64Coder::s_rgnDecodeTable + a2[v15 + 1]), v19 == 0xFF)
        || (v20 = *((_BYTE *)&DdcBase64Coder::s_rgnDecodeTable + a2[v15 + 2]), v20 == 0xFF)
        || (v21 = *((_BYTE *)&DdcBase64Coder::s_rgnDecodeTable + v17), v21 == -1) )
      {
        v14 = -2147024809;
        goto LABEL_29;
      }
      v15 += 4;
      *v16 = (4 * v18) | (v19 >> 4) & 3;
      v16[1] = (16 * v19) | (v20 >> 2) & 0xF;
      v16[2] = (v20 << 6) | v21 & 0x3F;
      v16 += 3;
    }
    v14 = 0;
    *this = v12;
    v12 = 0;
    *((_DWORD *)this + 2) = v10;
  }
LABEL_29:
  operator delete(v12);
  return v14;
}

```

## disassembly

```asm
0x18000f600  push    rbx
0x18000f602  push    rbp
0x18000f603  push    rsi
0x18000f604  push    rdi
0x18000f605  push    r12
0x18000f607  push    r13
0x18000f609  push    r14
0x18000f60b  sub     rsp, 30h
0x18000f60f  mov     rdi, rcx
0x18000f612  mov     rbx, r8
0x18000f615  mov     rcx, [rcx]; Block
0x18000f618  mov     r14, rdx
0x18000f61b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f620  mov     qword ptr [rdi], 0
0x18000f627  mov     dword ptr [rdi+8], 0
0x18000f62e  test    rbx, rbx
0x18000f631  jz      loc_18000F792
0x18000f637  test    bl, 3
0x18000f63a  jnz     loc_18000F792
0x18000f640  mov     edx, 3Dh ; '='
0x18000f645  mov     rax, rbx
0x18000f648  shr     rax, 2
0x18000f64c  cmp     dx, [r14+rbx*2-2]
0x18000f652  lea     ecx, [rax+rax*2]; unsigned __int64
0x18000f655  lea     eax, [rcx-1]
0x18000f658  cmovnz  eax, ecx
0x18000f65b  cmp     dx, [r14+rbx*2-4]
0x18000f661  lea     ebp, [rax-1]
0x18000f664  cmovnz  ebp, eax
0x18000f667  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f66c  cmp     cs:?s_rgnDecodeTable@DdcBase64Coder@@0PAEA, 0; uchar near * DdcBase64Coder::s_rgnDecodeTable
0x18000f673  lea     r13, ?s_rgnDecodeTable@DdcBase64Coder@@0PAEA; uchar near * DdcBase64Coder::s_rgnDecodeTable
0x18000f67a  mov     rsi, rax
0x18000f67d  mov     r12d, 80h
0x18000f683  jnz     short loc_18000F6C7
0x18000f685  mov     r8d, r12d; Size
0x18000f688  mov     dl, 0FFh; Val
0x18000f68a  mov     rcx, r13; void *
0x18000f68d  call    memset_0
0x18000f692  xor     cl, cl
0x18000f694  cmp     cl, 41h ; 'A'
0x18000f697  jnb     short loc_18000F6C0
0x18000f699  movzx   eax, cl
0x18000f69c  lea     rdx, ?s_rgchBase64Digits@DdcBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18000f6a3  cmp     [rdx+rax*2], r12w
0x18000f6a8  jnb     short loc_18000F6B6
0x18000f6aa  movzx   eax, word ptr [rdx+rax*2]
0x18000f6ae  mov     [rax+r13], cl
0x18000f6b2  inc     cl
0x18000f6b4  jmp     short loc_18000F694
0x18000f6b6  mov     ebx, 80004005h
0x18000f6bb  jmp     loc_18000F7C5
0x18000f6c0  mov     cs:byte_18004970D, 0
0x18000f6c7  xor     ecx, ecx
0x18000f6c9  mov     r11, rsi
0x18000f6cc  lea     rax, [rcx+3]
0x18000f6d0  cmp     rax, rbx
0x18000f6d3  jnb     loc_18000F786
0x18000f6d9  cmp     [r14+rcx*2], r12w
0x18000f6de  jnb     loc_18000F77F
0x18000f6e4  cmp     [r14+rcx*2+2], r12w
0x18000f6ea  jnb     loc_18000F77F
0x18000f6f0  cmp     [r14+rcx*2+4], r12w
0x18000f6f6  jnb     loc_18000F77F
0x18000f6fc  movzx   edx, word ptr [r14+rax*2]
0x18000f701  cmp     dx, r12w
0x18000f705  jnb     short loc_18000F77F
0x18000f707  movzx   eax, word ptr [r14+rcx*2]
0x18000f70c  mov     r10b, [rax+r13]
0x18000f710  cmp     r10b, 0FFh
0x18000f714  jz      short loc_18000F77F
0x18000f716  movzx   eax, word ptr [r14+rcx*2+2]
0x18000f71c  mov     r9b, [rax+r13]
0x18000f720  cmp     r9b, 0FFh
0x18000f724  jz      short loc_18000F77F
0x18000f726  movzx   eax, word ptr [r14+rcx*2+4]
0x18000f72c  mov     r8b, [rax+r13]
0x18000f730  cmp     r8b, 0FFh
0x18000f734  jz      short loc_18000F77F
0x18000f736  mov     dl, [rdx+r13]
0x18000f73a  cmp     dl, 0FFh
0x18000f73d  jz      short loc_18000F77F
0x18000f73f  mov     al, r9b
0x18000f742  shl     r10b, 2
0x18000f746  shr     al, 4
0x18000f749  and     dl, 3Fh
0x18000f74c  and     al, 3
0x18000f74e  shl     r9b, 4
0x18000f752  or      al, r10b
0x18000f755  add     rcx, 4
0x18000f759  mov     [r11], al
0x18000f75c  mov     al, r8b
0x18000f75f  shr     al, 2
0x18000f762  and     al, 0Fh
0x18000f764  shl     r8b, 6
0x18000f768  or      al, r9b
0x18000f76b  or      dl, r8b
0x18000f76e  mov     [r11+1], al
0x18000f772  mov     [r11+2], dl
0x18000f776  add     r11, 3
0x18000f77a  jmp     loc_18000F6CC
0x18000f77f  mov     ebx, 80070057h
0x18000f784  jmp     short loc_18000F7C5
0x18000f786  xor     ebx, ebx
0x18000f788  mov     [rdi], rsi
0x18000f78b  xor     esi, esi
0x18000f78d  mov     [rdi+8], ebp
0x18000f790  jmp     short loc_18000F7C5
0x18000f792  xor     esi, esi
0x18000f794  mov     ebx, 80070057h
0x18000f799  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000f7a0  jz      short loc_18000F7C5
0x18000f7a2  lea     rax, aCbrCchencodedd; "CBR(cchEncodedData > 0 && cchEncodedDat"...
0x18000f7a9  mov     r8d, ebx
0x18000f7ac  mov     [rsp+68h+var_40], rax
0x18000f7b1  lea     r9, aOnecoreuapShel_11; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000f7b8  mov     [rsp+68h+var_48], 13Ch
0x18000f7c0  call    McTemplateU0dsqs_EventWriteTransfer
0x18000f7c5  mov     rcx, rsi; Block
0x18000f7c8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f7cd  mov     eax, ebx
0x18000f7cf  add     rsp, 30h
0x18000f7d3  pop     r14
0x18000f7d5  pop     r13
0x18000f7d7  pop     r12
0x18000f7d9  pop     rdi
0x18000f7da  pop     rsi
0x18000f7db  pop     rbp
0x18000f7dc  pop     rbx
0x18000f7dd  retn
```
