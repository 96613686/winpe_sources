# CRTFObject::GetEnhMetafilePict(void *,tagSIZE const &,int,CTxtEdit *)

- ea: `0x1801581e0`
- end: `0x18015839f`
- name: `?GetEnhMetafilePict@CRTFObject@@AEAAHPEAXAEBUtagSIZE@@HPEAVCTxtEdit@@@Z`
- size: `447`
- prototype: `int(CRTFObject *__hidden this, void *, const struct tagSIZE *, int, struct CTxtEdit *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180158afc`
- `0x180159bb0`

## callees

- `0x1800693d4`
- `0x18006e770`
- `0x18006fc24`
- `0x1800e9338`
- `0x1801581e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180158351`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180158364`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180158351`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180158364`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18015821d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18015821d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1801582ed`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1801582ed`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801582fe`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801582fe`
- `ext-ms-win-gdi-metafile-l1-1-1!GetWinMetaFileBits` at `0x1801582d8`
- `ext-ms-win-gdi-metafile-l1-1-1!GetWinMetaFileBits` at `0x18015832e`
- `ext-ms-win-gdi-metafile-l1-1-1!GetWinMetaFileBits` at `0x1801582d8`
- `ext-ms-win-gdi-metafile-l1-1-1!GetWinMetaFileBits` at `0x18015832e`
- `ext-ms-win-gdi-metafile-l1-1-1!GetEnhMetaFileHeader` at `0x180158211`
- `ext-ms-win-gdi-metafile-l1-1-1!GetEnhMetaFileHeader` at `0x180158238`
- `ext-ms-win-gdi-metafile-l1-1-1!GetEnhMetaFileHeader` at `0x180158211`
- `ext-ms-win-gdi-metafile-l1-1-1!GetEnhMetaFileHeader` at `0x180158238`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteEnhMetaFile` at `0x18015833e`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteEnhMetaFile` at `0x18015833e`
- `ext-ms-win-gdi-metafile-l1-1-0!GetEnhMetaFileBits` at `0x1801582a2`
- `ext-ms-win-gdi-metafile-l1-1-0!GetEnhMetaFileBits` at `0x18015831b`
- `ext-ms-win-gdi-metafile-l1-1-0!GetEnhMetaFileBits` at `0x1801582a2`
- `ext-ms-win-gdi-metafile-l1-1-0!GetEnhMetaFileBits` at `0x18015831b`

## pseudocode

```c
__int64 __fastcall CRTFObject::GetEnhMetafilePict(
        CRTFObject *this,
        HENHMETAFILE a2,
        const struct tagSIZE *a3,
        int a4,
        struct CTxtEdit *a5)
{
  HDC v7; // rbx
  unsigned int v9; // edi
  void *v10; // r15
  signed int EnhMetaFileHeader; // r14d
  struct tagENHMETAHEADER *v12; // rax
  __int16 *v13; // r12
  LONG cx; // ecx
  __int16 v15; // ax
  __int64 v16; // r11
  int v17; // ecx
  signed int WinMetaFileBits; // eax
  HDC hdcRef; // rax
  UINT v20; // r14d
  HGLOBAL v21; // rax
  BYTE *v22; // rax
  UINT v23; // eax
  void *v24; // rcx

  v7 = 0;
  *((_QWORD *)this + 13) = 0;
  v9 = 0;
  v10 = 0;
  EnhMetaFileHeader = GetEnhMetaFileHeader(a2, 0, 0);
  v12 = (struct tagENHMETAHEADER *)malloc(EnhMetaFileHeader);
  v13 = (__int16 *)v12;
  if ( v12 )
  {
    if ( !GetEnhMetaFileHeader(a2, EnhMetaFileHeader, v12) )
      goto LABEL_16;
    *((_WORD *)this + 1) = 0;
    cx = a3->cx;
    *((_DWORD *)this + 24) = v13[40];
    *((_DWORD *)this + 25) = v13[42];
    v15 = CW32System::MulDivFunc(cx, 72, 127);
    v17 = *(_DWORD *)(v16 + 4);
    *((_WORD *)this + 20) = v15;
    *((_WORD *)this + 21) = CW32System::MulDivFunc(v17, 72, 127);
    if ( a4 )
    {
      *((_WORD *)this + 1) = 8;
      hdcRef = CTxtEdit::TxGetDC(a5);
      v7 = hdcRef;
      if ( !hdcRef )
        goto LABEL_16;
      WinMetaFileBits = GetWinMetaFileBits(a2, 0, 0, 8, hdcRef);
    }
    else
    {
      WinMetaFileBits = GetEnhMetaFileBits(a2, 0, 0);
    }
    v20 = WinMetaFileBits;
    if ( WinMetaFileBits )
    {
      v21 = GlobalAlloc(0x42u, WinMetaFileBits);
      v10 = v21;
      if ( v21 )
      {
        v22 = (BYTE *)GlobalLock(v21);
        *((_QWORD *)this + 13) = v22;
        if ( v22 )
        {
          v23 = a4 ? GetWinMetaFileBits(a2, v20, v22, 8, v7) : GetEnhMetaFileBits(a2, v20, v22);
          if ( v23 )
          {
            *((_DWORD *)this + 28) = v23;
            if ( DeleteEnhMetaFile(a2) )
              v9 = 1;
          }
        }
      }
    }
LABEL_16:
    free(v13);
    if ( v9 )
      goto LABEL_21;
  }
  v24 = (void *)*((_QWORD *)this + 13);
  if ( v24 )
    free(v24);
  if ( v10 )
    CW32System::GlobalFree(v10);
LABEL_21:
  if ( v7 )
    CTxtEdit::TxReleaseDC(a5, v7);
  return v9;
}

```

## disassembly

```asm
0x1801581e0  mov     [rsp+arg_10], r8
0x1801581e5  push    rbx
0x1801581e6  push    rbp
0x1801581e7  push    rsi
0x1801581e8  push    rdi
0x1801581e9  push    r12
0x1801581eb  push    r13
0x1801581ed  push    r14
0x1801581ef  push    r15
0x1801581f1  sub     rsp, 38h
0x1801581f5  mov     rsi, rdx
0x1801581f8  mov     rbp, rcx
0x1801581fb  xor     ebx, ebx
0x1801581fd  xor     r8d, r8d; lpEnhMetaHeader
0x180158200  mov     [rcx+68h], rbx
0x180158204  xor     edx, edx; nSize
0x180158206  mov     rcx, rsi; hemf
0x180158209  mov     r13d, r9d
0x18015820c  xor     edi, edi
0x18015820e  xor     r15d, r15d
0x180158211  call    cs:__imp_GetEnhMetaFileHeader
0x180158217  movsxd  r14, eax
0x18015821a  mov     rcx, r14; Size
0x18015821d  call    cs:__imp_malloc
0x180158223  mov     r12, rax
0x180158226  test    rax, rax
0x180158229  jz      loc_18015835B
0x18015822f  mov     r8, rax; lpEnhMetaHeader
0x180158232  mov     edx, r14d; nSize
0x180158235  mov     rcx, rsi; hemf
0x180158238  call    cs:__imp_GetEnhMetaFileHeader
0x18015823e  test    eax, eax
0x180158240  jz      loc_18015834E
0x180158246  mov     r11, [rsp+78h+arg_10]
0x18015824e  lea     r14d, [rdi+48h]
0x180158252  xor     eax, eax
0x180158254  lea     r8d, [rdi+7Fh]; int
0x180158258  mov     [rbp+2], ax
0x18015825c  mov     edx, r14d; int
0x18015825f  movsx   eax, word ptr [r12+50h]
0x180158265  mov     ecx, [r11]; int
0x180158268  mov     [rbp+60h], eax
0x18015826b  movsx   eax, word ptr [r12+54h]
0x180158271  mov     [rbp+64h], eax
0x180158274  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180158279  mov     ecx, [r11+4]; int
0x18015827d  lea     r8d, [rdi+7Fh]; int
0x180158281  mov     edx, r14d; int
0x180158284  mov     [rbp+28h], ax
0x180158288  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18015828d  mov     [rbp+2Ah], ax
0x180158291  lea     r14d, [rdi+8]
0x180158295  test    r13d, r13d
0x180158298  jnz     short loc_1801582AA
0x18015829a  xor     r8d, r8d; lpData
0x18015829d  xor     edx, edx; nSize
0x18015829f  mov     rcx, rsi; hEMF
0x1801582a2  call    cs:__imp_GetEnhMetaFileBits
0x1801582a8  jmp     short loc_1801582DE
0x1801582aa  mov     rcx, [rsp+78h+arg_20]; this
0x1801582b2  mov     [rbp+2], r14w
0x1801582b7  call    ?TxGetDC@CTxtEdit@@QEAAPEAUHDC__@@XZ; CTxtEdit::TxGetDC(void)
0x1801582bc  mov     rbx, rax
0x1801582bf  test    rax, rax
0x1801582c2  jz      loc_18015834E
0x1801582c8  mov     r9d, r14d; iMapMode
0x1801582cb  mov     [rsp+78h+hdcRef], rax; hdcRef
0x1801582d0  xor     r8d, r8d; pData16
0x1801582d3  xor     edx, edx; cbData16
0x1801582d5  mov     rcx, rsi; hemf
0x1801582d8  call    cs:__imp_GetWinMetaFileBits
0x1801582de  mov     r14d, eax
0x1801582e1  test    eax, eax
0x1801582e3  jz      short loc_18015834E
0x1801582e5  movsxd  rdx, eax; dwBytes
0x1801582e8  mov     ecx, 42h ; 'B'; uFlags
0x1801582ed  call    cs:__imp_GlobalAlloc
0x1801582f3  mov     r15, rax
0x1801582f6  test    rax, rax
0x1801582f9  jz      short loc_18015834E
0x1801582fb  mov     rcx, rax; hMem
0x1801582fe  call    cs:__imp_GlobalLock
0x180158304  mov     [rbp+68h], rax
0x180158308  test    rax, rax
0x18015830b  jz      short loc_18015834E
0x18015830d  mov     r8, rax; pData16
0x180158310  mov     edx, r14d; cbData16
0x180158313  mov     rcx, rsi; hemf
0x180158316  test    r13d, r13d
0x180158319  jnz     short loc_180158323
0x18015831b  call    cs:__imp_GetEnhMetaFileBits
0x180158321  jmp     short loc_180158334
0x180158323  mov     r9d, 8; iMapMode
0x180158329  mov     [rsp+78h+hdcRef], rbx; hdcRef
0x18015832e  call    cs:__imp_GetWinMetaFileBits
0x180158334  test    eax, eax
0x180158336  jz      short loc_18015834E
0x180158338  mov     rcx, rsi; hmf
0x18015833b  mov     [rbp+70h], eax
0x18015833e  call    cs:__imp_DeleteEnhMetaFile
0x180158344  test    eax, eax
0x180158346  mov     ecx, 1
0x18015834b  cmovnz  edi, ecx
0x18015834e  mov     rcx, r12; Block
0x180158351  call    cs:__imp_free
0x180158357  test    edi, edi
0x180158359  jnz     short loc_180158377
0x18015835b  mov     rcx, [rbp+68h]; Block
0x18015835f  test    rcx, rcx
0x180158362  jz      short loc_18015836A
0x180158364  call    cs:__imp_free
0x18015836a  test    r15, r15
0x18015836d  jz      short loc_180158377
0x18015836f  mov     rcx, r15; void *
0x180158372  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x180158377  test    rbx, rbx
0x18015837a  jz      short loc_18015838C
0x18015837c  mov     rcx, [rsp+78h+arg_20]; this
0x180158384  mov     rdx, rbx; HDC
0x180158387  call    ?TxReleaseDC@CTxtEdit@@QEAAHPEAUHDC__@@@Z; CTxtEdit::TxReleaseDC(HDC__ *)
0x18015838c  mov     eax, edi
0x18015838e  add     rsp, 38h
0x180158392  pop     r15
0x180158394  pop     r14
0x180158396  pop     r13
0x180158398  pop     r12
0x18015839a  pop     rdi
0x18015839b  pop     rsi
0x18015839c  pop     rbp
0x18015839d  pop     rbx
0x18015839e  retn
```
