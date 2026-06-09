# CPictureCYUV420::CPictureCYUV420(long *,CRct const &,CRct const &)

- ea: `0x18001faf0`
- end: `0x18001fc64`
- name: `??0CPictureCYUV420@@QEAA@PEAJAEBVCRct@@1@Z`
- size: `372`
- prototype: `CPictureCYUV420 *__fastcall(CPictureCYUV420 *__hidden this, int *, const struct CRct *, const struct CRct *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180009fb4`
- `0x180012df4`

## callees

- `0x18000145c`
- `0x18001faf0`
- `0x18001fc6c`
- `0x18001fd04`

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
0x18001faf0  push    rbx
0x18001faf2  push    rbp
0x18001faf3  push    rsi
0x18001faf4  push    rdi
0x18001faf5  push    r14
0x18001faf7  push    r15
0x18001faf9  sub     rsp, 28h
0x18001fafd  mov     rdi, rcx
0x18001fb00  or      eax, 0FFFFFFFFh
0x18001fb03  mov     [rcx+0Ch], eax
0x18001fb06  xor     ebp, ebp
0x18001fb08  mov     [rcx+8], eax
0x18001fb0b  mov     r14, r9
0x18001fb0e  mov     [rcx+1Ch], eax
0x18001fb11  mov     rsi, rdx
0x18001fb14  mov     [rcx+18h], eax
0x18001fb17  mov     r15, r8
0x18001fb1a  mov     [rcx], rbp
0x18001fb1d  mov     [rcx+10h], rbp
0x18001fb21  mov     [rcx+38h], rbp
0x18001fb25  mov     [rcx+40h], rbp
0x18001fb29  mov     [rcx+48h], rbp
0x18001fb2d  mov     eax, [r8]
0x18001fb30  mov     [rcx], eax
0x18001fb32  mov     ecx, [r8+4]
0x18001fb36  mov     [rdi+4], ecx
0x18001fb39  mov     ebx, [r8+8]
0x18001fb3d  mov     [rdi+8], ebx
0x18001fb40  sub     ebx, eax
0x18001fb42  mov     r11d, [r8+0Ch]
0x18001fb46  mov     [rdi+0Ch], r11d
0x18001fb4a  sub     r11d, ecx
0x18001fb4d  mov     edx, [r9]
0x18001fb50  mov     eax, r11d
0x18001fb53  imul    eax, ebx
0x18001fb56  mov     [rdi+10h], edx
0x18001fb59  mov     r8d, [r9+4]
0x18001fb5d  mov     [rdi+14h], r8d
0x18001fb61  mov     r10d, [r9+8]
0x18001fb65  mov     [rdi+18h], r10d
0x18001fb69  sub     r10d, edx
0x18001fb6c  mov     r9d, [r9+0Ch]
0x18001fb70  mov     [rdi+20h], eax
0x18001fb73  mov     [rdi+1Ch], r9d
0x18001fb77  sub     r9d, r8d
0x18001fb7a  mov     eax, r9d
0x18001fb7d  mov     [rdi+28h], ebx
0x18001fb80  imul    eax, r10d
0x18001fb84  lea     ebx, [rbp+20h]
0x18001fb87  mov     ecx, ebx; Size
0x18001fb89  mov     [rdi+2Ch], r11d
0x18001fb8d  mov     [rdi+30h], r10d
0x18001fb91  mov     [rdi+34h], r9d
0x18001fb95  mov     [rdi+24h], eax
0x18001fb98  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fb9d  test    rax, rax
0x18001fba0  jz      loc_18001FC42
0x18001fba6  mov     r8, r15; struct CRct *
0x18001fba9  mov     rdx, rsi; int *
0x18001fbac  mov     rcx, rax; this
0x18001fbaf  call    ??0CU8Image@@QEAA@PEAJAEBVCRct@@E@Z; CU8Image::CU8Image(long *,CRct const &,uchar)
0x18001fbb4  mov     [rdi+38h], rax
0x18001fbb8  test    rax, rax
0x18001fbbb  jz      loc_18001FC46
0x18001fbc1  cmp     [rsi], ebp
0x18001fbc3  jnz     loc_18001FC4C
0x18001fbc9  mov     ecx, ebx; Size
0x18001fbcb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fbd0  test    rax, rax
0x18001fbd3  jz      short loc_18001FC3C
0x18001fbd5  mov     r8, r14; struct CRct *
0x18001fbd8  mov     rdx, rsi; int *
0x18001fbdb  mov     rcx, rax; this
0x18001fbde  call    ??0CU8Image@@QEAA@PEAJAEBVCRct@@E@Z; CU8Image::CU8Image(long *,CRct const &,uchar)
0x18001fbe3  mov     [rdi+40h], rax
0x18001fbe7  test    rax, rax
0x18001fbea  jz      short loc_18001FC46
0x18001fbec  cmp     [rsi], ebp
0x18001fbee  jnz     short loc_18001FC4C
0x18001fbf0  mov     ecx, ebx; Size
0x18001fbf2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fbf7  test    rax, rax
0x18001fbfa  jz      short loc_18001FC36
0x18001fbfc  mov     r8, r14; struct CRct *
0x18001fbff  mov     rdx, rsi; int *
0x18001fc02  mov     rcx, rax; this
0x18001fc05  call    ??0CU8Image@@QEAA@PEAJAEBVCRct@@E@Z; CU8Image::CU8Image(long *,CRct const &,uchar)
0x18001fc0a  mov     [rdi+48h], rax
0x18001fc0e  test    rax, rax
0x18001fc11  jz      short loc_18001FC46
0x18001fc13  cmp     [rsi], ebp
0x18001fc15  jnz     short loc_18001FC4C
0x18001fc17  mov     rcx, [rdi+38h]
0x18001fc1b  mov     rdx, [rcx]
0x18001fc1e  mov     rcx, [rdi+40h]
0x18001fc22  mov     [rdi+50h], rdx
0x18001fc26  mov     rdx, [rcx]
0x18001fc29  mov     [rdi+58h], rdx
0x18001fc2d  mov     rax, [rax]
0x18001fc30  mov     [rdi+60h], rax
0x18001fc34  jmp     short loc_18001FC54
0x18001fc36  mov     [rdi+48h], rbp
0x18001fc3a  jmp     short loc_18001FC46
0x18001fc3c  mov     [rdi+40h], rbp
0x18001fc40  jmp     short loc_18001FC46
0x18001fc42  mov     [rdi+38h], rbp
0x18001fc46  mov     dword ptr [rsi], 0FFFFFFFDh
0x18001fc4c  mov     rcx, rdi; this
0x18001fc4f  call    ?Clean@CPictureCYUV420@@QEAAXXZ; CPictureCYUV420::Clean(void)
0x18001fc54  mov     rax, rdi
0x18001fc57  add     rsp, 28h
0x18001fc5b  pop     r15
0x18001fc5d  pop     r14
0x18001fc5f  pop     rdi
0x18001fc60  pop     rsi
0x18001fc61  pop     rbp
0x18001fc62  pop     rbx
0x18001fc63  retn
```
