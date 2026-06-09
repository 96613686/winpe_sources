# MdmBase64Coder::Decode(ushort const *,unsigned __int64)

- ea: `0x18001a194`
- end: `0x18001a37f`
- name: `?Decode@MdmBase64Coder@@QEAAJPEBG_K@Z`
- size: `491`
- prototype: `__int64 __fastcall(void **this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009d18`

## callees

- `0x180001544`
- `0x180001bdc`
- `0x180001fd4`
- `0x1800065c0`
- `0x18001a194`

## string_xrefs

- `0x18001a351`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmbase64coder.cpp`

## pseudocode

```c
__int64 __fastcall MdmBase64Coder::Decode(void **this, const unsigned __int16 *a2, unsigned __int64 a3)
{
  unsigned __int16 *v6; // rdx
  int v7; // ecx
  unsigned __int64 v8; // rcx
  int v9; // eax
  int v10; // ebp
  int v11; // edx
  unsigned __int16 *v12; // rsi
  unsigned __int8 v13; // cl
  __int64 v14; // rcx
  char v15; // r11
  unsigned __int8 v16; // r10
  unsigned __int8 v17; // r9
  char v18; // r8
  unsigned int v19; // ebx

  operator delete(*this, (unsigned __int64)a2);
  *this = 0;
  *((_DWORD *)this + 2) = 0;
  if ( !a3 || (a3 & 3) != 0 )
  {
    v12 = 0;
    v19 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        (_DWORD)v6,
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
    v12 = (unsigned __int16 *)operator new[](v8);
    if ( (_BYTE)MdmBase64Coder::s_rgnDecodeTable )
    {
LABEL_12:
      v14 = 0;
      v6 = v12;
      if ( a3 <= 3 )
      {
LABEL_25:
        v19 = 0;
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
          v15 = *((_BYTE *)&MdmBase64Coder::s_rgnDecodeTable + a2[v14]);
          if ( v15 == -1 )
            break;
          v16 = *((_BYTE *)&MdmBase64Coder::s_rgnDecodeTable + a2[v14 + 1]);
          if ( v16 == 0xFF )
            break;
          v17 = *((_BYTE *)&MdmBase64Coder::s_rgnDecodeTable + a2[v14 + 2]);
          if ( v17 == 0xFF )
            break;
          v18 = *((_BYTE *)&MdmBase64Coder::s_rgnDecodeTable + a2[v14 + 3]);
          if ( v18 == -1 )
            break;
          v14 += 4;
          *(_BYTE *)v6 = (4 * v15) | (v16 >> 4) & 3;
          *((_BYTE *)v6 + 1) = (16 * v16) | (v17 >> 2) & 0xF;
          *((_BYTE *)v6 + 2) = (v17 << 6) | v18 & 0x3F;
          if ( v14 + 3 >= a3 )
            goto LABEL_25;
          v6 = (unsigned __int16 *)((char *)v6 + 3);
        }
        v19 = -2147024809;
      }
    }
    else
    {
      LOBYTE(v11) = -1;
      memset_0(&MdmBase64Coder::s_rgnDecodeTable, v11, 0x80u);
      v13 = 0;
      while ( 1 )
      {
        v6 = L"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/";
        if ( MdmBase64Coder::s_rgchBase64Digits[v13] >= 0x80u )
          break;
        *((_BYTE *)&MdmBase64Coder::s_rgnDecodeTable + MdmBase64Coder::s_rgchBase64Digits[v13]) = v13;
        if ( ++v13 >= 0x41u )
        {
          byte_1800304FD = 0;
          goto LABEL_12;
        }
      }
      v19 = -2147467259;
    }
  }
  operator delete(v12, (unsigned __int64)v6);
  return v19;
}

```

## disassembly

```asm
0x18001a194  push    rbx
0x18001a196  push    rbp
0x18001a197  push    rsi
0x18001a198  push    rdi
0x18001a199  push    r12
0x18001a19b  push    r13
0x18001a19d  push    r14
0x18001a19f  sub     rsp, 30h
0x18001a1a3  mov     rdi, rcx
0x18001a1a6  mov     rbx, r8
0x18001a1a9  mov     rcx, [rcx]; void *
0x18001a1ac  mov     r14, rdx
0x18001a1af  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a1b4  mov     qword ptr [rdi], 0
0x18001a1bb  mov     dword ptr [rdi+8], 0
0x18001a1c2  test    rbx, rbx
0x18001a1c5  jz      loc_18001A332
0x18001a1cb  test    bl, 3
0x18001a1ce  jnz     loc_18001A332
0x18001a1d4  mov     edx, 3Dh ; '='
0x18001a1d9  mov     rax, rbx
0x18001a1dc  shr     rax, 2
0x18001a1e0  cmp     dx, [r14+rbx*2-2]
0x18001a1e6  lea     ecx, [rax+rax*2]; unsigned __int64
0x18001a1e9  lea     eax, [rcx-1]
0x18001a1ec  cmovnz  eax, ecx
0x18001a1ef  cmp     dx, [r14+rbx*2-4]
0x18001a1f5  lea     ebp, [rax-1]
0x18001a1f8  cmovnz  ebp, eax
0x18001a1fb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a200  cmp     cs:?s_rgnDecodeTable@MdmBase64Coder@@0PAEA, 0; uchar near * MdmBase64Coder::s_rgnDecodeTable
0x18001a207  lea     r13, ?s_rgnDecodeTable@MdmBase64Coder@@0PAEA; uchar near * MdmBase64Coder::s_rgnDecodeTable
0x18001a20e  mov     rsi, rax
0x18001a211  mov     r12d, 80h
0x18001a217  jnz     short loc_18001A253
0x18001a219  mov     r8d, r12d; Size
0x18001a21c  mov     dl, 0FFh; Val
0x18001a21e  mov     rcx, r13; void *
0x18001a221  call    memset_0
0x18001a226  xor     cl, cl
0x18001a228  movzx   eax, cl
0x18001a22b  lea     rdx, ?s_rgchBase64Digits@MdmBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18001a232  cmp     [rdx+rax*2], r12w
0x18001a237  jnb     loc_18001A318
0x18001a23d  movzx   eax, word ptr [rdx+rax*2]
0x18001a241  mov     [rax+r13], cl
0x18001a245  inc     cl
0x18001a247  cmp     cl, 41h ; 'A'
0x18001a24a  jb      short loc_18001A228
0x18001a24c  mov     cs:byte_1800304FD, 0
0x18001a253  xor     ecx, ecx
0x18001a255  mov     rdx, rsi
0x18001a258  cmp     rbx, 3
0x18001a25c  jbe     loc_18001A326
0x18001a262  cmp     [r14+rcx*2], r12w
0x18001a267  jnb     loc_18001A31F
0x18001a26d  cmp     [r14+rcx*2+2], r12w
0x18001a273  jnb     loc_18001A31F
0x18001a279  cmp     [r14+rcx*2+4], r12w
0x18001a27f  jnb     loc_18001A31F
0x18001a285  cmp     [r14+rcx*2+6], r12w
0x18001a28b  jnb     loc_18001A31F
0x18001a291  movzx   eax, word ptr [r14+rcx*2]
0x18001a296  mov     r11b, [rax+r13]
0x18001a29a  cmp     r11b, 0FFh
0x18001a29e  jz      short loc_18001A31F
0x18001a2a0  movzx   eax, word ptr [r14+rcx*2+2]
0x18001a2a6  mov     r10b, [rax+r13]
0x18001a2aa  cmp     r10b, 0FFh
0x18001a2ae  jz      short loc_18001A31F
0x18001a2b0  movzx   eax, word ptr [r14+rcx*2+4]
0x18001a2b6  mov     r9b, [rax+r13]
0x18001a2ba  cmp     r9b, 0FFh
0x18001a2be  jz      short loc_18001A31F
0x18001a2c0  movzx   eax, word ptr [r14+rcx*2+6]
0x18001a2c6  mov     r8b, [rax+r13]
0x18001a2ca  cmp     r8b, 0FFh
0x18001a2ce  jz      short loc_18001A31F
0x18001a2d0  mov     al, r10b
0x18001a2d3  shl     r11b, 2
0x18001a2d7  shr     al, 4
0x18001a2da  add     rcx, 4
0x18001a2de  and     al, 3
0x18001a2e0  shl     r10b, 4
0x18001a2e4  or      al, r11b
0x18001a2e7  and     r8b, 3Fh
0x18001a2eb  mov     [rdx], al
0x18001a2ed  mov     al, r9b
0x18001a2f0  shr     al, 2
0x18001a2f3  and     al, 0Fh
0x18001a2f5  shl     r9b, 6
0x18001a2f9  or      al, r10b
0x18001a2fc  or      r8b, r9b
0x18001a2ff  mov     [rdx+1], al
0x18001a302  lea     rax, [rcx+3]
0x18001a306  mov     [rdx+2], r8b
0x18001a30a  cmp     rax, rbx
0x18001a30d  jnb     short loc_18001A326
0x18001a30f  add     rdx, 3
0x18001a313  jmp     loc_18001A262
0x18001a318  mov     ebx, 80004005h
0x18001a31d  jmp     short loc_18001A365
0x18001a31f  mov     ebx, 80070057h
0x18001a324  jmp     short loc_18001A365
0x18001a326  xor     ebx, ebx
0x18001a328  mov     [rdi], rsi
0x18001a32b  xor     esi, esi
0x18001a32d  mov     [rdi+8], ebp
0x18001a330  jmp     short loc_18001A365
0x18001a332  xor     esi, esi
0x18001a334  mov     ebx, 80070057h
0x18001a339  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a340  jz      short loc_18001A365
0x18001a342  lea     rax, aCbrCchencodedd; "CBR(cchEncodedData > 0 && cchEncodedDat"...
0x18001a349  mov     r8d, ebx
0x18001a34c  mov     [rsp+68h+var_40], rax
0x18001a351  lea     r9, aOnecoreuapShel_11; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001a358  mov     [rsp+68h+var_48], 145h
0x18001a360  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a365  mov     rcx, rsi; void *
0x18001a368  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a36d  mov     eax, ebx
0x18001a36f  add     rsp, 30h
0x18001a373  pop     r14
0x18001a375  pop     r13
0x18001a377  pop     r12
0x18001a379  pop     rdi
0x18001a37a  pop     rsi
0x18001a37b  pop     rbp
0x18001a37c  pop     rbx
0x18001a37d  retn
```
