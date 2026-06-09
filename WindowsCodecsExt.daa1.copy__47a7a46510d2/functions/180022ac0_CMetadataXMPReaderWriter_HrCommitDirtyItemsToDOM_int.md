# CMetadataXMPReaderWriter::HrCommitDirtyItemsToDOM(int)

- ea: `0x180022ac0`
- end: `0x180022c3c`
- name: `?HrCommitDirtyItemsToDOM@CMetadataXMPReaderWriter@@MEAAJH@Z`
- size: `380`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180004500`
- `0x1800171c4`
- `0x180017d40`
- `0x180022ac0`
- `0x180032dcd`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180022ad9`
- `OLEAUT32!__imp_SysAllocString` at `0x180022ad9`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::HrCommitDirtyItemsToDOM(CMetadataXMPReaderWriter *this, int a2)
{
  unsigned __int16 *v4; // rbx
  bool v5; // zf
  unsigned int v6; // edi
  int v7; // eax
  int v8; // ecx
  __int64 v9; // rbp
  __int64 v10; // r15
  __int64 v11; // rcx
  int v12; // edx
  void (__fastcall ***v13)(_QWORD, __int64); // rcx
  unsigned int v14; // r14d
  __int64 v15; // rdi
  unsigned __int16 *v17; // [rsp+70h] [rbp+18h] BYREF

  v17 = SysAllocString(&word_180037ED4);
  v4 = v17;
  if ( v17 )
  {
    v7 = CMetadataRDFReaderWriter::HrCommitDirtyItemsToDOM(this, a2);
    v6 = v7;
    if ( v7 >= 0 )
    {
      v9 = 0;
      if ( !*((_DWORD *)this + 72) )
        goto LABEL_27;
      while ( 1 )
      {
        v10 = (unsigned int)v9;
        v11 = *(_QWORD *)(*((_QWORD *)this + 33) + 8 * v9);
        if ( (*(_BYTE *)(v11 + 8) & 4) != 0 )
        {
          v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(v11 + 16) + 216LL))(
                 *(_QWORD *)(v11 + 16),
                 v4);
          v12 = g_doStackCaptures;
          v6 = v7;
          if ( v7 < 0 )
          {
            if ( g_doStackCaptures )
              goto LABEL_5;
            goto LABEL_27;
          }
          if ( v7 )
          {
            v6 = -2147467259;
            v5 = g_doStackCaptures == 0;
            goto LABEL_24;
          }
          v13 = *(void (__fastcall ****)(_QWORD, __int64))(*((_QWORD *)this + 33) + 8 * v9);
          if ( v13 )
          {
            (**v13)(v13, 1);
            v12 = g_doStackCaptures;
          }
          v14 = v9;
          LODWORD(v9) = v9 - 1;
          if ( v14 >= *((_DWORD *)this + 72) && v12 )
            DoStackCapture(-2147024809);
          if ( *((_DWORD *)this + 72) - v14 != 1 )
          {
            v15 = *((_QWORD *)this + 33);
            memmove_0(
              (void *)(v15 + 8 * v10),
              (const void *)(v15 + 8LL * (v14 + 1)),
              8LL * (*((_DWORD *)this + 72) - v14 - 1));
            *(_QWORD *)(v15 + 8LL * (unsigned int)(*((_DWORD *)this + 72) - 1)) = 0;
          }
          --*((_DWORD *)this + 72);
          v6 = 0;
        }
        v9 = (unsigned int)(v9 + 1);
        if ( (unsigned int)v9 >= *((_DWORD *)this + 72) )
          goto LABEL_27;
      }
    }
    if ( !g_doStackCaptures )
      goto LABEL_27;
LABEL_5:
    v8 = v7;
LABEL_26:
    DoStackCapture(v8);
    goto LABEL_27;
  }
  v5 = g_doStackCaptures == 0;
  v6 = -2147024882;
LABEL_24:
  if ( !v5 )
  {
    v8 = v6;
    goto LABEL_26;
  }
LABEL_27:
  FreeBSTR(&v17);
  return v6;
}

```

## disassembly

```asm
0x180022ac0  push    rbx
0x180022ac2  push    rbp
0x180022ac3  push    rsi
0x180022ac4  push    rdi
0x180022ac5  push    r14
0x180022ac7  push    r15
0x180022ac9  sub     rsp, 28h
0x180022acd  mov     rsi, rcx
0x180022ad0  mov     edi, edx
0x180022ad2  lea     rcx, word_180037ED4; psz
0x180022ad9  call    cs:__imp_SysAllocString
0x180022adf  mov     [rsp+58h+arg_10], rax
0x180022ae4  mov     rbx, rax
0x180022ae7  test    rax, rax
0x180022aea  jnz     short loc_180022AFC
0x180022aec  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x180022af2  mov     edi, 8007000Eh
0x180022af7  jmp     loc_180022C1A
0x180022afc  mov     edx, edi; int
0x180022afe  mov     rcx, rsi; this
0x180022b01  call    ?HrCommitDirtyItemsToDOM@CMetadataRDFReaderWriter@@MEAAJH@Z; CMetadataRDFReaderWriter::HrCommitDirtyItemsToDOM(int)
0x180022b06  mov     edi, eax
0x180022b08  test    eax, eax
0x180022b0a  jns     short loc_180022B24
0x180022b0c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180022b13  jz      short loc_180022B1C
0x180022b15  mov     ecx, eax
0x180022b17  jmp     loc_180022C1E
0x180022b1c  test    eax, eax
0x180022b1e  js      loc_180022C23
0x180022b24  xor     ebp, ebp
0x180022b26  cmp     [rsi+120h], ebp
0x180022b2c  jbe     loc_180022C23
0x180022b32  mov     rax, [rsi+108h]
0x180022b39  mov     r15d, ebp
0x180022b3c  mov     rcx, [rax+rbp*8]
0x180022b40  test    byte ptr [rcx+8], 4
0x180022b44  jz      loc_180022C03
0x180022b4a  mov     rcx, [rcx+10h]
0x180022b4e  mov     rdx, rbx
0x180022b51  mov     rax, [rcx]
0x180022b54  mov     rax, [rax+0D8h]
0x180022b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b60  mov     edx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180022b66  mov     edi, eax
0x180022b68  test    eax, eax
0x180022b6a  jns     short loc_180022B78
0x180022b6c  test    edx, edx
0x180022b6e  jnz     short loc_180022B15
0x180022b70  test    eax, eax
0x180022b72  js      loc_180022C23
0x180022b78  jnz     loc_180022C13
0x180022b7e  mov     rax, [rsi+108h]
0x180022b85  mov     rcx, [rax+rbp*8]
0x180022b89  test    rcx, rcx
0x180022b8c  jz      short loc_180022BA4
0x180022b8e  mov     rax, [rcx]
0x180022b91  mov     edx, 1
0x180022b96  mov     rax, [rax]
0x180022b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b9e  mov     edx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180022ba4  mov     r14d, ebp
0x180022ba7  dec     ebp
0x180022ba9  cmp     r14d, [rsi+120h]
0x180022bb0  jb      short loc_180022BC0
0x180022bb2  test    edx, edx
0x180022bb4  jz      short loc_180022BC0
0x180022bb6  mov     ecx, 80070057h; int
0x180022bbb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180022bc0  mov     eax, [rsi+120h]
0x180022bc6  sub     eax, r14d
0x180022bc9  sub     eax, 1
0x180022bcc  jz      short loc_180022BFB
0x180022bce  mov     rdi, [rsi+108h]
0x180022bd5  mov     r8d, eax
0x180022bd8  lea     eax, [r14+1]
0x180022bdc  shl     r8, 3; Size
0x180022be0  lea     rdx, [rdi+rax*8]; Src
0x180022be4  lea     rcx, [rdi+r15*8]; void *
0x180022be8  call    memmove_0
0x180022bed  mov     ecx, [rsi+120h]
0x180022bf3  dec     ecx
0x180022bf5  xor     eax, eax
0x180022bf7  mov     [rdi+rcx*8], rax
0x180022bfb  dec     dword ptr [rsi+120h]
0x180022c01  xor     edi, edi
0x180022c03  inc     ebp
0x180022c05  cmp     ebp, [rsi+120h]
0x180022c0b  jb      loc_180022B32
0x180022c11  jmp     short loc_180022C23
0x180022c13  mov     edi, 80004005h
0x180022c18  test    edx, edx
0x180022c1a  jz      short loc_180022C23
0x180022c1c  mov     ecx, edi; int
0x180022c1e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180022c23  lea     rcx, [rsp+58h+arg_10]; unsigned __int16 **
0x180022c28  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180022c2d  mov     eax, edi
0x180022c2f  add     rsp, 28h
0x180022c33  pop     r15
0x180022c35  pop     r14
0x180022c37  pop     rdi
0x180022c38  pop     rsi
0x180022c39  pop     rbp
0x180022c3a  pop     rbx
0x180022c3b  retn
```
