# MdmBase64Coder::Decode(ushort const *,unsigned __int64)

- ea: `0x180019c84`
- end: `0x180019e6e`
- name: `?Decode@MdmBase64Coder@@QEAAJPEBG_K@Z`
- size: `490`
- prototype: `__int64 __fastcall(void **this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009b24`

## callees

- `0x180001544`
- `0x180001bdc`
- `0x180001fd4`
- `0x180006548`
- `0x180019c84`

## string_xrefs

- `0x180019e41`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmbase64coder.cpp`

## pseudocode

```c
__int64 __fastcall MdmBase64Coder::Decode(void **this, const unsigned __int16 *a2, unsigned __int64 a3)
{
  int v6; // edx
  int v7; // ecx
  unsigned __int64 v8; // rcx
  int v9; // eax
  int v10; // ebp
  int v11; // edx
  _BYTE *v12; // rsi
  unsigned __int8 v13; // cl
  __int64 v14; // rcx
  _BYTE *v15; // rdx
  char v16; // r11
  unsigned __int8 v17; // r10
  unsigned __int8 v18; // r9
  char v19; // r8
  unsigned int v20; // ebx

  operator delete(*this);
  *this = 0;
  *((_DWORD *)this + 2) = 0;
  if ( !a3 || (a3 & 3) != 0 )
  {
    v12 = 0;
    v20 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        v6,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
        69,
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
    if ( (_BYTE)MdmBase64Coder::s_rgnDecodeTable )
    {
LABEL_12:
      v14 = 0;
      v15 = v12;
      if ( a3 <= 3 )
      {
LABEL_25:
        v20 = 0;
        *this = v12;
        v12 = 0;
        *((_DWORD *)this + 2) = v10;
      }
      else
      {
        while ( a2[v14] < 0x80u )
        {
          if ( a2[v14 + 1] >= 0x80u )
            break;
          if ( a2[v14 + 2] >= 0x80u )
            break;
          if ( a2[v14 + 3] >= 0x80u )
            break;
          v16 = *((_BYTE *)&MdmBase64Coder::s_rgnDecodeTable + a2[v14]);
          if ( v16 == -1 )
            break;
          v17 = *((_BYTE *)&MdmBase64Coder::s_rgnDecodeTable + a2[v14 + 1]);
          if ( v17 == 0xFF )
            break;
          v18 = *((_BYTE *)&MdmBase64Coder::s_rgnDecodeTable + a2[v14 + 2]);
          if ( v18 == 0xFF )
            break;
          v19 = *((_BYTE *)&MdmBase64Coder::s_rgnDecodeTable + a2[v14 + 3]);
          if ( v19 == -1 )
            break;
          v14 += 4;
          *v15 = (4 * v16) | (v17 >> 4) & 3;
          v15[1] = (16 * v17) | (v18 >> 2) & 0xF;
          v15[2] = (v18 << 6) | v19 & 0x3F;
          if ( v14 + 3 >= a3 )
            goto LABEL_25;
          v15 += 3;
        }
        v20 = -2147024809;
      }
    }
    else
    {
      LOBYTE(v11) = -1;
      memset_0(&MdmBase64Coder::s_rgnDecodeTable, v11, 0x80u);
      v13 = 0;
      while ( MdmBase64Coder::s_rgchBase64Digits[v13] < 0x80u )
      {
        *((_BYTE *)&MdmBase64Coder::s_rgnDecodeTable + MdmBase64Coder::s_rgchBase64Digits[v13]) = v13;
        if ( ++v13 >= 0x41u )
        {
          byte_1800304FD = 0;
          goto LABEL_12;
        }
      }
      v20 = -2147467259;
    }
  }
  operator delete(v12);
  return v20;
}

```

## disassembly

```asm
0x180019c84  push    rbx
0x180019c86  push    rbp
0x180019c87  push    rsi
0x180019c88  push    rdi
0x180019c89  push    r12
0x180019c8b  push    r13
0x180019c8d  push    r14
0x180019c8f  sub     rsp, 30h
0x180019c93  mov     rdi, rcx
0x180019c96  mov     rbx, r8
0x180019c99  mov     rcx, [rcx]; void *
0x180019c9c  mov     r14, rdx
0x180019c9f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019ca4  mov     qword ptr [rdi], 0
0x180019cab  mov     dword ptr [rdi+8], 0
0x180019cb2  test    rbx, rbx
0x180019cb5  jz      loc_180019E22
0x180019cbb  test    bl, 3
0x180019cbe  jnz     loc_180019E22
0x180019cc4  mov     edx, 3Dh ; '='
0x180019cc9  mov     rax, rbx
0x180019ccc  shr     rax, 2
0x180019cd0  cmp     dx, [r14+rbx*2-2]
0x180019cd6  lea     ecx, [rax+rax*2]; unsigned __int64
0x180019cd9  lea     eax, [rcx-1]
0x180019cdc  cmovnz  eax, ecx
0x180019cdf  cmp     dx, [r14+rbx*2-4]
0x180019ce5  lea     ebp, [rax-1]
0x180019ce8  cmovnz  ebp, eax
0x180019ceb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019cf0  cmp     cs:?s_rgnDecodeTable@MdmBase64Coder@@0PAEA, 0; uchar near * MdmBase64Coder::s_rgnDecodeTable
0x180019cf7  lea     r13, ?s_rgnDecodeTable@MdmBase64Coder@@0PAEA; uchar near * MdmBase64Coder::s_rgnDecodeTable
0x180019cfe  mov     rsi, rax
0x180019d01  mov     r12d, 80h
0x180019d07  jnz     short loc_180019D43
0x180019d09  mov     r8d, r12d; Size
0x180019d0c  mov     dl, 0FFh; Val
0x180019d0e  mov     rcx, r13; void *
0x180019d11  call    memset_0
0x180019d16  xor     cl, cl
0x180019d18  movzx   eax, cl
0x180019d1b  lea     rdx, ?s_rgchBase64Digits@MdmBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x180019d22  cmp     [rdx+rax*2], r12w
0x180019d27  jnb     loc_180019E08
0x180019d2d  movzx   eax, word ptr [rdx+rax*2]
0x180019d31  mov     [rax+r13], cl
0x180019d35  inc     cl
0x180019d37  cmp     cl, 41h ; 'A'
0x180019d3a  jb      short loc_180019D18
0x180019d3c  mov     cs:byte_1800304FD, 0
0x180019d43  xor     ecx, ecx
0x180019d45  mov     rdx, rsi
0x180019d48  cmp     rbx, 3
0x180019d4c  jbe     loc_180019E16
0x180019d52  cmp     [r14+rcx*2], r12w
0x180019d57  jnb     loc_180019E0F
0x180019d5d  cmp     [r14+rcx*2+2], r12w
0x180019d63  jnb     loc_180019E0F
0x180019d69  cmp     [r14+rcx*2+4], r12w
0x180019d6f  jnb     loc_180019E0F
0x180019d75  cmp     [r14+rcx*2+6], r12w
0x180019d7b  jnb     loc_180019E0F
0x180019d81  movzx   eax, word ptr [r14+rcx*2]
0x180019d86  mov     r11b, [rax+r13]
0x180019d8a  cmp     r11b, 0FFh
0x180019d8e  jz      short loc_180019E0F
0x180019d90  movzx   eax, word ptr [r14+rcx*2+2]
0x180019d96  mov     r10b, [rax+r13]
0x180019d9a  cmp     r10b, 0FFh
0x180019d9e  jz      short loc_180019E0F
0x180019da0  movzx   eax, word ptr [r14+rcx*2+4]
0x180019da6  mov     r9b, [rax+r13]
0x180019daa  cmp     r9b, 0FFh
0x180019dae  jz      short loc_180019E0F
0x180019db0  movzx   eax, word ptr [r14+rcx*2+6]
0x180019db6  mov     r8b, [rax+r13]
0x180019dba  cmp     r8b, 0FFh
0x180019dbe  jz      short loc_180019E0F
0x180019dc0  mov     al, r10b
0x180019dc3  shl     r11b, 2
0x180019dc7  shr     al, 4
0x180019dca  add     rcx, 4
0x180019dce  and     al, 3
0x180019dd0  shl     r10b, 4
0x180019dd4  or      al, r11b
0x180019dd7  and     r8b, 3Fh
0x180019ddb  mov     [rdx], al
0x180019ddd  mov     al, r9b
0x180019de0  shr     al, 2
0x180019de3  and     al, 0Fh
0x180019de5  shl     r9b, 6
0x180019de9  or      al, r10b
0x180019dec  or      r8b, r9b
0x180019def  mov     [rdx+1], al
0x180019df2  lea     rax, [rcx+3]
0x180019df6  mov     [rdx+2], r8b
0x180019dfa  cmp     rax, rbx
0x180019dfd  jnb     short loc_180019E16
0x180019dff  add     rdx, 3
0x180019e03  jmp     loc_180019D52
0x180019e08  mov     ebx, 80004005h
0x180019e0d  jmp     short loc_180019E55
0x180019e0f  mov     ebx, 80070057h
0x180019e14  jmp     short loc_180019E55
0x180019e16  xor     ebx, ebx
0x180019e18  mov     [rdi], rsi
0x180019e1b  xor     esi, esi
0x180019e1d  mov     [rdi+8], ebp
0x180019e20  jmp     short loc_180019E55
0x180019e22  xor     esi, esi
0x180019e24  mov     ebx, 80070057h
0x180019e29  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180019e30  jz      short loc_180019E55
0x180019e32  lea     rax, aCbrCchencodedd; "CBR(cchEncodedData > 0 && cchEncodedDat"...
0x180019e39  mov     r8d, ebx
0x180019e3c  mov     [rsp+68h+var_40], rax
0x180019e41  lea     r9, aOnecoreuapShel_11; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180019e48  mov     [rsp+68h+var_48], 145h
0x180019e50  call    McTemplateU0dsqs_EventWriteTransfer
0x180019e55  mov     rcx, rsi; void *
0x180019e58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019e5d  mov     eax, ebx
0x180019e5f  add     rsp, 30h
0x180019e63  pop     r14
0x180019e65  pop     r13
0x180019e67  pop     r12
0x180019e69  pop     rdi
0x180019e6a  pop     rsi
0x180019e6b  pop     rbp
0x180019e6c  pop     rbx
0x180019e6d  retn
```
