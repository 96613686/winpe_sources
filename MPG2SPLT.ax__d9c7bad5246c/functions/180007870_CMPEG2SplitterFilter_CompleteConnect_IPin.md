# CMPEG2SplitterFilter::CompleteConnect(IPin *)

- ea: `0x180007870`
- end: `0x180007a9f`
- name: `?CompleteConnect@CMPEG2SplitterFilter@@UEAAJPEAUIPin@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(CMPEG2SplitterFilter *__hidden this, struct IPin *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180007870`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMPEG2SplitterFilter::CompleteConnect(CMPEG2SplitterFilter *this, struct IPin *a2)
{
  __int64 v2; // rbx
  __int64 v4; // r14
  __int64 v5; // rbx
  __int64 v6; // r8
  int v7; // ebx
  __int64 v8; // rax
  int i; // esi
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  _QWORD v18[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v19; // [rsp+30h] [rbp-38h]
  __int128 v20; // [rsp+38h] [rbp-30h] BYREF
  __int128 v21; // [rsp+48h] [rbp-20h] BYREF

  v2 = *((_QWORD *)this + 16);
  v4 = v2 + 104;
  (*(void (__fastcall **)(_QWORD, struct IPin *))(**(_QWORD **)(v2 + 448) + 8LL))(*(_QWORD *)(v2 + 448), a2);
  v5 = *(_QWORD *)(v2 + 448);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v18[1] = v5;
  v19 = 0;
  v18[0] = &CParseReaderFromAsync::`vftable';
  v7 = -2147467259;
  if ( v4 != -16 )
  {
    v8 = (*(__int64 (__fastcall **)(CMPEG2SplitterFilter *, char *, __int64))(*(_QWORD *)this + 120LL))(
           this,
           (char *)this + 304,
           v4);
    *((_QWORD *)this + 37) = v8;
    v6 = v8;
    if ( v8 )
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v8 + 8LL))(v8, v18);
  }
  for ( i = 0; v7 < 0 && !i; i = 1 )
  {
    v10 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 37);
    v19 = 0;
    if ( v10 )
      (**v10)(v10, 1);
    *((_QWORD *)this + 37) = 0;
    *(_OWORD *)(v4 + 16) = *off_18003E0F8;
    v11 = (*(__int64 (__fastcall **)(CMPEG2SplitterFilter *, char *, __int64))(*(_QWORD *)this + 120LL))(
            this,
            (char *)this + 304,
            v4);
    *((_QWORD *)this + 37) = v11;
    v6 = v11;
    if ( v11 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v11 + 8LL))(v11, v18);
      if ( v7 == -2147220939 )
        break;
    }
  }
  v12 = *((_QWORD *)this + 37);
  if ( !v12 )
    return 2147942414LL;
  if ( v7 >= 0 )
  {
    *(_QWORD *)(*((_QWORD *)this + 16) + 304LL) = v12;
    v14 = *((_QWORD *)this + 16);
    v20 = 0;
    v21 = 0;
    v15 = *(_QWORD *)(v14 + 224);
    if ( !v15 )
      v15 = 24;
    (*(void (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v15 + 32LL))(v15, &v20, v6);
    (*(void (__fastcall **)(_QWORD, char *, __int128 *))(**((_QWORD **)this + 37) + 16LL))(
      *((_QWORD *)this + 37),
      (char *)&v20 + 4,
      &v20);
    v16 = (*(_QWORD *)(*((_QWORD *)this + 16) + 224LL) - 24LL)
        & -(__int64)(*(_QWORD *)(*((_QWORD *)this + 16) + 224LL) != 0);
    if ( v16 )
      v17 = v16 + 24;
    else
      v17 = 0;
    (*(void (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v17 + 24LL))(v17, &v20, &v21);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007870  push    rbp
0x180007872  push    rbx
0x180007873  push    rsi
0x180007874  push    rdi
0x180007875  push    r14
0x180007877  push    r15
0x180007879  mov     rbp, rsp
0x18000787c  sub     rsp, 68h
0x180007880  mov     rax, cs:__security_cookie
0x180007887  xor     rax, rsp
0x18000788a  mov     [rbp+var_10], rax
0x18000788e  mov     rbx, [rcx+80h]
0x180007895  mov     rdi, rcx
0x180007898  mov     rcx, [rbx+1C0h]
0x18000789f  lea     r14, [rbx+68h]
0x1800078a3  mov     rax, [rcx]
0x1800078a6  mov     rax, [rax+8]
0x1800078aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078af  mov     rbx, [rbx+1C0h]
0x1800078b6  mov     rcx, rbx
0x1800078b9  mov     rax, [rbx]
0x1800078bc  mov     rax, [rax+10h]
0x1800078c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078c5  lea     r15, [r14+10h]
0x1800078c9  mov     [rbp+var_40], rbx
0x1800078cd  mov     [rbp+var_38], 0
0x1800078d5  lea     rax, ??_7CParseReaderFromAsync@@6B@; const CParseReaderFromAsync::`vftable'
0x1800078dc  mov     [rbp+var_48], rax
0x1800078e0  mov     ebx, 80004005h
0x1800078e5  test    r15, r15
0x1800078e8  jz      short loc_180007927
0x1800078ea  mov     rax, [rdi]
0x1800078ed  lea     rdx, [rdi+130h]
0x1800078f4  mov     r8, r14
0x1800078f7  mov     rcx, rdi
0x1800078fa  mov     rax, [rax+78h]
0x1800078fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007903  mov     [rdi+128h], rax
0x18000790a  mov     r8, rax
0x18000790d  test    rax, rax
0x180007910  jz      short loc_180007927
0x180007912  mov     rcx, [rax]
0x180007915  lea     rdx, [rbp+var_48]
0x180007919  mov     rax, [rcx+8]
0x18000791d  mov     rcx, r8
0x180007920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007925  mov     ebx, eax
0x180007927  xor     esi, esi
0x180007929  jmp     loc_1800079C4
0x18000792e  cmp     esi, 1
0x180007931  jnb     loc_1800079CC
0x180007937  mov     rcx, [rdi+128h]
0x18000793e  mov     [rbp+var_38], 0
0x180007946  test    rcx, rcx
0x180007949  jz      short loc_18000795B
0x18000794b  mov     rax, [rcx]
0x18000794e  mov     edx, 1
0x180007953  mov     rax, [rax]
0x180007956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000795b  mov     qword ptr [rdi+128h], 0
0x180007966  lea     rcx, off_18003E0F8
0x18000796d  mov     eax, esi
0x18000796f  lea     rdx, [rdi+130h]
0x180007976  add     rax, rax
0x180007979  mov     r8, r14
0x18000797c  mov     rax, [rcx+rax*8]
0x180007980  mov     rcx, rdi
0x180007983  movups  xmm0, xmmword ptr [rax]
0x180007986  movdqu  xmmword ptr [r15], xmm0
0x18000798b  mov     rax, [rdi]
0x18000798e  mov     rax, [rax+78h]
0x180007992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007997  mov     [rdi+128h], rax
0x18000799e  mov     r8, rax
0x1800079a1  test    rax, rax
0x1800079a4  jz      short loc_1800079C2
0x1800079a6  mov     rcx, [rax]
0x1800079a9  lea     rdx, [rbp+var_48]
0x1800079ad  mov     rax, [rcx+8]
0x1800079b1  mov     rcx, r8
0x1800079b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079b9  mov     ebx, eax
0x1800079bb  cmp     eax, 80040235h
0x1800079c0  jz      short loc_1800079CC
0x1800079c2  inc     esi
0x1800079c4  test    ebx, ebx
0x1800079c6  js      loc_18000792E
0x1800079cc  mov     rcx, [rdi+128h]
0x1800079d3  test    rcx, rcx
0x1800079d6  jnz     short loc_1800079E2
0x1800079d8  mov     eax, 8007000Eh
0x1800079dd  jmp     loc_180007A86
0x1800079e2  test    ebx, ebx
0x1800079e4  js      loc_180007A84
0x1800079ea  mov     rax, [rdi+80h]
0x1800079f1  lea     rdx, [rbp+var_30]
0x1800079f5  xorps   xmm0, xmm0
0x1800079f8  xorps   xmm1, xmm1
0x1800079fb  mov     [rax+130h], rcx
0x180007a02  mov     rax, [rdi+80h]
0x180007a09  movups  [rbp+var_30], xmm0
0x180007a0d  movups  [rbp+var_20], xmm1
0x180007a11  mov     rcx, [rax+0E0h]
0x180007a18  mov     eax, 18h
0x180007a1d  test    rcx, rcx
0x180007a20  cmovz   rcx, rax
0x180007a24  mov     rax, [rcx]
0x180007a27  mov     rax, [rax+20h]
0x180007a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a30  mov     rcx, [rdi+128h]
0x180007a37  lea     r8, [rbp+var_30]
0x180007a3b  lea     rdx, [rbp+var_30+4]
0x180007a3f  mov     rax, [rcx]
0x180007a42  mov     rax, [rax+10h]
0x180007a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a4b  mov     rax, [rdi+80h]
0x180007a52  mov     rcx, [rax+0E0h]
0x180007a59  lea     rax, [rcx-18h]
0x180007a5d  neg     rcx
0x180007a60  sbb     rcx, rcx
0x180007a63  and     rcx, rax
0x180007a66  jz      short loc_180007A6E
0x180007a68  add     rcx, 18h
0x180007a6c  jmp     short loc_180007A70
0x180007a6e  xor     ecx, ecx
0x180007a70  mov     rax, [rcx]
0x180007a73  lea     r8, [rbp+var_20]
0x180007a77  lea     rdx, [rbp+var_30]
0x180007a7b  mov     rax, [rax+18h]
0x180007a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a84  mov     eax, ebx
0x180007a86  mov     rcx, [rbp+var_10]
0x180007a8a  xor     rcx, rsp; StackCookie
0x180007a8d  call    __security_check_cookie
0x180007a92  add     rsp, 68h
0x180007a96  pop     r15
0x180007a98  pop     r14
0x180007a9a  pop     rdi
0x180007a9b  pop     rsi
0x180007a9c  pop     rbx
0x180007a9d  pop     rbp
0x180007a9e  retn
```
