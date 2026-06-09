# CPictureCYUV420::CPictureCYUV420(long *,CRct const &,CRct const &)

- ea: `0x18001fa30`
- end: `0x18001fba4`
- name: `??0CPictureCYUV420@@QEAA@PEAJAEBVCRct@@1@Z`
- size: `372`
- prototype: `CPictureCYUV420 *__fastcall(CPictureCYUV420 *__hidden this, int *, const struct CRct *, const struct CRct *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180009ef4`
- `0x180012d34`

## callees

- `0x18000142c`
- `0x18001fa30`
- `0x18001fbac`
- `0x18001fc44`

## pseudocode

```c
CPictureCYUV420 *__fastcall CPictureCYUV420::CPictureCYUV420(
        CPictureCYUV420 *this,
        int *a2,
        const struct CRct *a3,
        const struct CRct *a4)
{
  int v8; // eax
  int v9; // ecx
  int v10; // ebx
  int v11; // ebx
  int v12; // r11d
  int v13; // r11d
  int v14; // edx
  int v15; // r8d
  int v16; // r10d
  int v17; // r10d
  int v18; // r9d
  int v19; // r9d
  CU8Image *v20; // rax
  unsigned __int8 v21; // r9
  CU8Image *v22; // rax
  CU8Image *v23; // rax
  unsigned __int8 v24; // r9
  CU8Image *v25; // rax
  CU8Image *v26; // rax
  unsigned __int8 v27; // r9
  CU8Image *v28; // rax
  _QWORD *v29; // rcx

  *((_DWORD *)this + 3) = -1;
  *((_DWORD *)this + 2) = -1;
  *((_DWORD *)this + 7) = -1;
  *((_DWORD *)this + 6) = -1;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  v8 = *(_DWORD *)a3;
  *(_DWORD *)this = *(_DWORD *)a3;
  v9 = *((_DWORD *)a3 + 1);
  *((_DWORD *)this + 1) = v9;
  v10 = *((_DWORD *)a3 + 2);
  *((_DWORD *)this + 2) = v10;
  v11 = v10 - v8;
  v12 = *((_DWORD *)a3 + 3);
  *((_DWORD *)this + 3) = v12;
  v13 = v12 - v9;
  v14 = *(_DWORD *)a4;
  *((_DWORD *)this + 4) = *(_DWORD *)a4;
  v15 = *((_DWORD *)a4 + 1);
  *((_DWORD *)this + 5) = v15;
  v16 = *((_DWORD *)a4 + 2);
  *((_DWORD *)this + 6) = v16;
  v17 = v16 - v14;
  v18 = *((_DWORD *)a4 + 3);
  *((_DWORD *)this + 8) = v11 * v13;
  *((_DWORD *)this + 7) = v18;
  v19 = v18 - v15;
  *((_DWORD *)this + 10) = v11;
  *((_DWORD *)this + 11) = v13;
  *((_DWORD *)this + 12) = v17;
  *((_DWORD *)this + 13) = v19;
  *((_DWORD *)this + 9) = v17 * v19;
  v20 = (CU8Image *)operator new(0x20u);
  if ( !v20 )
  {
    *((_QWORD *)this + 7) = 0;
    goto LABEL_14;
  }
  v22 = CU8Image::CU8Image(v20, a2, a3, v21);
  *((_QWORD *)this + 7) = v22;
  if ( !v22 )
    goto LABEL_14;
  if ( *a2 )
    goto LABEL_15;
  v23 = (CU8Image *)operator new(0x20u);
  if ( !v23 )
  {
    *((_QWORD *)this + 8) = 0;
    goto LABEL_14;
  }
  v25 = CU8Image::CU8Image(v23, a2, a4, v24);
  *((_QWORD *)this + 8) = v25;
  if ( !v25 )
    goto LABEL_14;
  if ( *a2 )
  {
LABEL_15:
    CPictureCYUV420::Clean(this);
    return this;
  }
  v26 = (CU8Image *)operator new(0x20u);
  if ( !v26 )
  {
    *((_QWORD *)this + 9) = 0;
    goto LABEL_14;
  }
  v28 = CU8Image::CU8Image(v26, a2, a4, v27);
  *((_QWORD *)this + 9) = v28;
  if ( !v28 )
  {
LABEL_14:
    *a2 = -3;
    goto LABEL_15;
  }
  if ( *a2 )
    goto LABEL_15;
  v29 = (_QWORD *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 10) = **((_QWORD **)this + 7);
  *((_QWORD *)this + 11) = *v29;
  *((_QWORD *)this + 12) = *(_QWORD *)v28;
  return this;
}

```

## disassembly

```asm
0x18001fa30  push    rbx
0x18001fa32  push    rbp
0x18001fa33  push    rsi
0x18001fa34  push    rdi
0x18001fa35  push    r14
0x18001fa37  push    r15
0x18001fa39  sub     rsp, 28h
0x18001fa3d  mov     rdi, rcx
0x18001fa40  or      eax, 0FFFFFFFFh
0x18001fa43  mov     [rcx+0Ch], eax
0x18001fa46  xor     ebp, ebp
0x18001fa48  mov     [rcx+8], eax
0x18001fa4b  mov     r14, r9
0x18001fa4e  mov     [rcx+1Ch], eax
0x18001fa51  mov     rsi, rdx
0x18001fa54  mov     [rcx+18h], eax
0x18001fa57  mov     r15, r8
0x18001fa5a  mov     [rcx], rbp
0x18001fa5d  mov     [rcx+10h], rbp
0x18001fa61  mov     [rcx+38h], rbp
0x18001fa65  mov     [rcx+40h], rbp
0x18001fa69  mov     [rcx+48h], rbp
0x18001fa6d  mov     eax, [r8]
0x18001fa70  mov     [rcx], eax
0x18001fa72  mov     ecx, [r8+4]
0x18001fa76  mov     [rdi+4], ecx
0x18001fa79  mov     ebx, [r8+8]
0x18001fa7d  mov     [rdi+8], ebx
0x18001fa80  sub     ebx, eax
0x18001fa82  mov     r11d, [r8+0Ch]
0x18001fa86  mov     [rdi+0Ch], r11d
0x18001fa8a  sub     r11d, ecx
0x18001fa8d  mov     edx, [r9]
0x18001fa90  mov     eax, r11d
0x18001fa93  imul    eax, ebx
0x18001fa96  mov     [rdi+10h], edx
0x18001fa99  mov     r8d, [r9+4]
0x18001fa9d  mov     [rdi+14h], r8d
0x18001faa1  mov     r10d, [r9+8]
0x18001faa5  mov     [rdi+18h], r10d
0x18001faa9  sub     r10d, edx
0x18001faac  mov     r9d, [r9+0Ch]
0x18001fab0  mov     [rdi+20h], eax
0x18001fab3  mov     [rdi+1Ch], r9d
0x18001fab7  sub     r9d, r8d
0x18001faba  mov     eax, r9d
0x18001fabd  mov     [rdi+28h], ebx
0x18001fac0  imul    eax, r10d
0x18001fac4  lea     ebx, [rbp+20h]
0x18001fac7  mov     ecx, ebx; Size
0x18001fac9  mov     [rdi+2Ch], r11d
0x18001facd  mov     [rdi+30h], r10d
0x18001fad1  mov     [rdi+34h], r9d
0x18001fad5  mov     [rdi+24h], eax
0x18001fad8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fadd  test    rax, rax
0x18001fae0  jz      loc_18001FB82
0x18001fae6  mov     r8, r15; struct CRct *
0x18001fae9  mov     rdx, rsi; int *
0x18001faec  mov     rcx, rax; this
0x18001faef  call    ??0CU8Image@@QEAA@PEAJAEBVCRct@@E@Z; CU8Image::CU8Image(long *,CRct const &,uchar)
0x18001faf4  mov     [rdi+38h], rax
0x18001faf8  test    rax, rax
0x18001fafb  jz      loc_18001FB86
0x18001fb01  cmp     [rsi], ebp
0x18001fb03  jnz     loc_18001FB8C
0x18001fb09  mov     ecx, ebx; Size
0x18001fb0b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fb10  test    rax, rax
0x18001fb13  jz      short loc_18001FB7C
0x18001fb15  mov     r8, r14; struct CRct *
0x18001fb18  mov     rdx, rsi; int *
0x18001fb1b  mov     rcx, rax; this
0x18001fb1e  call    ??0CU8Image@@QEAA@PEAJAEBVCRct@@E@Z; CU8Image::CU8Image(long *,CRct const &,uchar)
0x18001fb23  mov     [rdi+40h], rax
0x18001fb27  test    rax, rax
0x18001fb2a  jz      short loc_18001FB86
0x18001fb2c  cmp     [rsi], ebp
0x18001fb2e  jnz     short loc_18001FB8C
0x18001fb30  mov     ecx, ebx; Size
0x18001fb32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fb37  test    rax, rax
0x18001fb3a  jz      short loc_18001FB76
0x18001fb3c  mov     r8, r14; struct CRct *
0x18001fb3f  mov     rdx, rsi; int *
0x18001fb42  mov     rcx, rax; this
0x18001fb45  call    ??0CU8Image@@QEAA@PEAJAEBVCRct@@E@Z; CU8Image::CU8Image(long *,CRct const &,uchar)
0x18001fb4a  mov     [rdi+48h], rax
0x18001fb4e  test    rax, rax
0x18001fb51  jz      short loc_18001FB86
0x18001fb53  cmp     [rsi], ebp
0x18001fb55  jnz     short loc_18001FB8C
0x18001fb57  mov     rcx, [rdi+38h]
0x18001fb5b  mov     rdx, [rcx]
0x18001fb5e  mov     rcx, [rdi+40h]
0x18001fb62  mov     [rdi+50h], rdx
0x18001fb66  mov     rdx, [rcx]
0x18001fb69  mov     [rdi+58h], rdx
0x18001fb6d  mov     rax, [rax]
0x18001fb70  mov     [rdi+60h], rax
0x18001fb74  jmp     short loc_18001FB94
0x18001fb76  mov     [rdi+48h], rbp
0x18001fb7a  jmp     short loc_18001FB86
0x18001fb7c  mov     [rdi+40h], rbp
0x18001fb80  jmp     short loc_18001FB86
0x18001fb82  mov     [rdi+38h], rbp
0x18001fb86  mov     dword ptr [rsi], 0FFFFFFFDh
0x18001fb8c  mov     rcx, rdi; this
0x18001fb8f  call    ?Clean@CPictureCYUV420@@QEAAXXZ; CPictureCYUV420::Clean(void)
0x18001fb94  mov     rax, rdi
0x18001fb97  add     rsp, 28h
0x18001fb9b  pop     r15
0x18001fb9d  pop     r14
0x18001fb9f  pop     rdi
0x18001fba0  pop     rsi
0x18001fba1  pop     rbp
0x18001fba2  pop     rbx
0x18001fba3  retn
```
