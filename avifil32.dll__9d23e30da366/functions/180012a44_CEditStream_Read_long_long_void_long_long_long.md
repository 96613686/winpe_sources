# CEditStream::Read(long,long,void *,long,long *,long *)

- ea: `0x180012a44`
- end: `0x180012c4f`
- name: `?Read@CEditStream@@UEAAJJJPEAXJPEAJ1@Z`
- size: `523`
- prototype: `int(CEditStream *__hidden this, int, int, void *, int, int *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180012a30`

## callees

- `0x180001460`
- `0x180011300`
- `0x180012a44`
- `0x180012e88`
- `0x180017365`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CEditStream::Read(CEditStream *this, int a2, int a3, char *a4, unsigned int a5, int *a6, int *a7)
{
  int v7; // r15d
  int v10; // ecx
  CEditStream *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // esi
  int v16; // r8d
  unsigned int v17; // esi
  __int64 result; // rax
  __int64 v19; // rcx
  bool v20; // zf
  struct tagBITMAPINFOHEADER *v21; // rax
  struct tagBITMAPINFOHEADER *v22; // rsi
  int v23; // [rsp+40h] [rbp-38h]
  int v24; // [rsp+44h] [rbp-34h] BYREF
  int v25; // [rsp+48h] [rbp-30h] BYREF
  struct IAVIStream *v26; // [rsp+50h] [rbp-28h] BYREF
  CEditStream *v27; // [rsp+58h] [rbp-20h]
  int v28; // [rsp+60h] [rbp-18h] BYREF
  int v29; // [rsp+64h] [rbp-14h] BYREF

  v7 = a2;
  v23 = a3;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v29 = 0;
  v28 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  v10 = *((_DWORD *)this - 58);
  if ( a2 < v10 || a2 >= *((_DWORD *)this - 57) + v10 )
    return 2147762282LL;
  if ( !a3 )
    return 0;
  v12 = (CEditStream *)((char *)this - 272);
  v27 = (CEditStream *)((char *)this - 272);
  while ( 1 )
  {
    if ( (unsigned int)CEditStream::ResolveEdits(v12, v7, &v26, &v25, &v24, 0) )
      return 2147500037LL;
    v13 = 56LL * v24;
    v14 = *((_QWORD *)this - 5);
    v15 = *(_DWORD *)(v13 + v14 + 12);
    v16 = *(_DWORD *)(v13 + v14 + 8);
    v17 = v25 + v23 - v16 <= v15 ? v23 : v16 + v15 - v25;
    if ( *((_DWORD *)this - 12) )
      break;
    result = ((__int64 (__fastcall *)(struct IAVIStream *, _QWORD, _QWORD, char *, unsigned int, int *, int *))v26->lpVtbl->Read)(
               v26,
               (unsigned int)v25,
               v17,
               a4,
               a5,
               &v28,
               &v29);
    if ( (_DWORD)result )
      return result;
    v19 = v28;
    if ( a6 )
      *a6 += v28;
    if ( a7 )
      *a7 += v29;
    if ( a4 )
    {
      a4 += v19;
      a5 -= v19;
    }
    v7 += v17;
    if ( v7 < *((_DWORD *)this - 57) + *((_DWORD *)this - 58) )
    {
      v20 = v23 == v17;
      v23 -= v17;
      v12 = (CEditStream *)((char *)this - 272);
      if ( !v20 )
        continue;
    }
    return 0;
  }
  v21 = CEditStream::CallGetFrame(v27, v26, v25);
  v22 = v21;
  if ( !v21 )
    return 2147500037LL;
  if ( !a4 )
  {
LABEL_29:
    if ( a6 )
      *a6 = v22->biSizeImage;
    if ( a7 )
      *a7 = 1;
    return 0;
  }
  if ( (a5 & 0x80000000) == 0 && a5 >= v21->biSizeImage )
  {
    memmove_0(a4, (char *)&v21->biSize + 4 * v21->biClrUsed + v21->biSize, v21->biSizeImage);
    goto LABEL_29;
  }
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  return 2147762292LL;
}

```

## disassembly

```asm
0x180012a44  push    rbp
0x180012a46  push    rbx
0x180012a47  push    rsi
0x180012a48  push    rdi
0x180012a49  push    r12
0x180012a4b  push    r13
0x180012a4d  push    r14
0x180012a4f  push    r15
0x180012a51  mov     rbp, rsp
0x180012a54  sub     rsp, 78h
0x180012a58  mov     rax, cs:__security_cookie
0x180012a5f  xor     rax, rsp
0x180012a62  mov     [rbp+var_10], rax
0x180012a66  mov     rdi, [rbp+arg_28]
0x180012a6a  mov     r15d, edx
0x180012a6d  mov     rbx, [rbp+arg_30]
0x180012a71  xor     edx, edx
0x180012a73  mov     [rbp+var_38], r8d
0x180012a77  mov     r12, r9
0x180012a7a  mov     [rbp+var_28], rdx
0x180012a7e  mov     r14, rcx
0x180012a81  mov     [rbp+var_30], edx
0x180012a84  mov     [rbp+var_34], edx
0x180012a87  mov     [rbp+var_14], edx
0x180012a8a  mov     [rbp+var_18], edx
0x180012a8d  test    rdi, rdi
0x180012a90  jz      short loc_180012A94
0x180012a92  mov     [rdi], edx
0x180012a94  test    rbx, rbx
0x180012a97  jz      short loc_180012A9B
0x180012a99  mov     [rbx], edx
0x180012a9b  mov     ecx, [rcx-0E8h]
0x180012aa1  cmp     r15d, ecx
0x180012aa4  jl      loc_180012C2D
0x180012aaa  add     ecx, [r14-0E4h]
0x180012ab1  cmp     r15d, ecx
0x180012ab4  jge     loc_180012C2D
0x180012aba  test    r8d, r8d
0x180012abd  jz      loc_180012C05
0x180012ac3  mov     r13d, [rbp+arg_20]
0x180012ac7  lea     rax, [r14-110h]
0x180012ace  mov     [rbp+var_20], rax
0x180012ad2  mov     [rsp+78h+var_50], edx; int
0x180012ad6  lea     rcx, [rbp+var_34]
0x180012ada  mov     [rsp+78h+var_58], rcx; int *
0x180012adf  lea     r9, [rbp+var_30]; int *
0x180012ae3  mov     rcx, rax; this
0x180012ae6  lea     r8, [rbp+var_28]; struct IAVIStream **
0x180012aea  mov     edx, r15d; int
0x180012aed  call    ?ResolveEdits@CEditStream@@AEAAJJPEAPEAUIAVIStream@@PEAJ1H@Z; CEditStream::ResolveEdits(long,IAVIStream * *,long *,long *,int)
0x180012af2  test    eax, eax
0x180012af4  jnz     loc_180012C26
0x180012afa  movsxd  rax, [rbp+var_34]
0x180012afe  mov     edx, [rbp+var_30]
0x180012b01  imul    rcx, rax, 38h ; '8'
0x180012b05  mov     rax, [r14-28h]
0x180012b09  mov     esi, [rcx+rax+0Ch]
0x180012b0d  mov     r8d, [rcx+rax+8]
0x180012b12  mov     ecx, [rbp+var_38]
0x180012b15  mov     eax, ecx
0x180012b17  sub     eax, r8d
0x180012b1a  add     eax, edx
0x180012b1c  cmp     eax, esi
0x180012b1e  jle     short loc_180012B27
0x180012b20  sub     esi, edx
0x180012b22  add     esi, r8d
0x180012b25  jmp     short loc_180012B29
0x180012b27  mov     esi, ecx
0x180012b29  cmp     dword ptr [r14-30h], 0
0x180012b2e  jnz     short loc_180012BAF
0x180012b30  mov     rcx, [rbp+var_28]
0x180012b34  lea     r8, [rbp+var_14]
0x180012b38  mov     [rsp+78h+var_48], r8
0x180012b3d  mov     r9, r12
0x180012b40  lea     r8, [rbp+var_18]
0x180012b44  mov     qword ptr [rsp+78h+var_50], r8
0x180012b49  mov     r8d, esi
0x180012b4c  mov     rax, [rcx]
0x180012b4f  mov     dword ptr [rsp+78h+var_58], r13d
0x180012b54  mov     rax, [rax+40h]
0x180012b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b5d  xor     edx, edx
0x180012b5f  test    eax, eax
0x180012b61  jnz     loc_180012C32
0x180012b67  movsxd  rcx, [rbp+var_18]
0x180012b6b  test    rdi, rdi
0x180012b6e  jz      short loc_180012B72
0x180012b70  add     [rdi], ecx
0x180012b72  test    rbx, rbx
0x180012b75  jz      short loc_180012B7C
0x180012b77  mov     eax, [rbp+var_14]
0x180012b7a  add     [rbx], eax
0x180012b7c  test    r12, r12
0x180012b7f  jz      short loc_180012B87
0x180012b81  add     r12, rcx
0x180012b84  sub     r13d, ecx
0x180012b87  mov     eax, [r14-0E8h]
0x180012b8e  add     r15d, esi
0x180012b91  add     eax, [r14-0E4h]
0x180012b98  cmp     r15d, eax
0x180012b9b  jge     short loc_180012C05
0x180012b9d  sub     [rbp+var_38], esi
0x180012ba0  lea     rax, [r14-110h]
0x180012ba7  jnz     loc_180012AD2
0x180012bad  jmp     short loc_180012C05
0x180012baf  mov     rcx, [rbp+var_20]; this
0x180012bb3  mov     r8d, edx; int
0x180012bb6  mov     rdx, [rbp+var_28]; struct IAVIStream *
0x180012bba  call    ?CallGetFrame@CEditStream@@AEAAPEAUtagBITMAPINFOHEADER@@PEAUIAVIStream@@J@Z; CEditStream::CallGetFrame(IAVIStream *,long)
0x180012bbf  mov     rsi, rax
0x180012bc2  test    rax, rax
0x180012bc5  jz      short loc_180012C26
0x180012bc7  test    r12, r12
0x180012bca  jz      short loc_180012BF0
0x180012bcc  test    r13d, r13d
0x180012bcf  js      short loc_180012C09
0x180012bd1  cmp     r13d, [rax+14h]
0x180012bd5  jb      short loc_180012C09
0x180012bd7  mov     edx, [rax]
0x180012bd9  mov     rcx, r12; void *
0x180012bdc  mov     r9d, [rax+20h]
0x180012be0  add     rdx, rax
0x180012be3  mov     r8d, [rax+14h]; Size
0x180012be7  lea     rdx, [rdx+r9*4]; Src
0x180012beb  call    memmove_0
0x180012bf0  test    rdi, rdi
0x180012bf3  jz      short loc_180012BFA
0x180012bf5  mov     eax, [rsi+14h]
0x180012bf8  mov     [rdi], eax
0x180012bfa  test    rbx, rbx
0x180012bfd  jz      short loc_180012C05
0x180012bff  mov     dword ptr [rbx], 1
0x180012c05  xor     eax, eax
0x180012c07  jmp     short loc_180012C32
0x180012c09  test    rdi, rdi
0x180012c0c  jz      short loc_180012C14
0x180012c0e  mov     dword ptr [rdi], 0
0x180012c14  test    rbx, rbx
0x180012c17  jz      short loc_180012C1F
0x180012c19  mov     dword ptr [rbx], 0
0x180012c1f  mov     eax, 80044074h
0x180012c24  jmp     short loc_180012C32
0x180012c26  mov     eax, 80004005h
0x180012c2b  jmp     short loc_180012C32
0x180012c2d  mov     eax, 8004406Ah
0x180012c32  mov     rcx, [rbp+var_10]
0x180012c36  xor     rcx, rsp; StackCookie
0x180012c39  call    __security_check_cookie
0x180012c3e  add     rsp, 78h
0x180012c42  pop     r15
0x180012c44  pop     r14
0x180012c46  pop     r13
0x180012c48  pop     r12
0x180012c4a  pop     rdi
0x180012c4b  pop     rsi
0x180012c4c  pop     rbx
0x180012c4d  pop     rbp
0x180012c4e  retn
```
