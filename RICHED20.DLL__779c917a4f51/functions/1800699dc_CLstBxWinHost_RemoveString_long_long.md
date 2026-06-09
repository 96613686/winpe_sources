# CLstBxWinHost::RemoveString(long,long)

- ea: `0x1800699dc`
- end: `0x180069d86`
- name: `?RemoveString@CLstBxWinHost@@QEAAHJJ@Z`
- size: `938`
- prototype: `__int64 __fastcall(CLstBxWinHost *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800673d8`

## callees

- `0x18004dcf8`
- `0x1800617bc`
- `0x180061fe0`
- `0x180066840`
- `0x1800668d8`
- `0x180067328`
- `0x18006783c`
- `0x18006800c`
- `0x1800699dc`
- `0x18006b434`
- `0x18006baec`
- `0x18006c070`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `USER32!IntersectRect` at `0x180069ca8`
- `USER32!IntersectRect` at `0x180069ca8`
- `USER32!InvalidateRect` at `0x180069cc9`
- `USER32!InvalidateRect` at `0x180069cc9`

## pseudocode

```c
__int64 __fastcall CLstBxWinHost::RemoveString(CLstBxWinHost *this, int a2, int a3)
{
  int v3; // r15d
  int v7; // r13d
  int v8; // esi
  int IsSelected; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // r12d
  unsigned int v12; // esi
  unsigned int v13; // r12d
  _DWORD *v14; // rbx
  _DWORD *v15; // rax
  __int64 v16; // rax
  int v17; // eax
  unsigned int i; // esi
  _DWORD *v19; // rax
  __int64 v20; // rax
  int v21; // ecx
  int v22; // eax
  bool v23; // zf
  int v24; // edx
  HWND v25; // rcx
  int v26; // eax
  int v27; // ecx
  int v28; // edx
  int v29; // ecx
  int v30; // [rsp+30h] [rbp-40h] BYREF
  struct ITextRange *v31; // [rsp+38h] [rbp-38h] BYREF
  int v32; // [rsp+40h] [rbp-30h]
  struct tagRECT rcDst; // [rsp+48h] [rbp-28h] BYREF
  struct tagRECT v34; // [rsp+58h] [rbp-18h] BYREF

  v3 = a3;
  v32 = a3;
  CLstBxWinHost::Freeze(this);
  v31 = 0;
  if ( !(unsigned int)CLstBxWinHost::GetRange(this, a2, v3, &v31) )
  {
    CLstBxWinHost::Unfreeze(this);
    return 0;
  }
  v30 = 0;
  if ( a2 )
  {
    ((void (__fastcall *)(struct ITextRange *, __int64, __int64, int *))v31->lpVtbl->MoveStart)(
      v31,
      1,
      0xFFFFFFFFLL,
      &v30);
    ((void (__fastcall *)(struct ITextRange *, __int64, __int64, int *))v31->lpVtbl->MoveEnd)(
      v31,
      1,
      0xFFFFFFFFLL,
      &v30);
  }
  if ( ((unsigned int (__fastcall *)(struct ITextRange *, __int64, _QWORD, int *))v31->lpVtbl->Delete)(v31, 1, 0, &v30)
    && *((int *)this + 48) > 1 )
  {
    CLstBxWinHost::Unfreeze(this);
    ((void (__fastcall *)(struct ITextRange *))v31->lpVtbl->Release)(v31);
    return 0;
  }
  ((void (__fastcall *)(struct ITextRange *))v31->lpVtbl->Release)(v31);
  v7 = *((_DWORD *)this + 48);
  v8 = a2 - 1;
  *((_DWORD *)this + 48) = a2 + v7 - v3 - 1;
  if ( a2 - 1 <= 0 )
    v8 = 0;
  if ( (*((_BYTE *)this + 128) & 1) == 0 )
  {
    IsSelected = CLstBxWinHost::IsSelected(this, v8);
    if ( (unsigned int)CLstBxWinHost::IsSelected(this, v3) != IsSelected || !*((_DWORD *)this + 48) )
    {
      v10 = -9999997;
      v11 = -9999997;
      if ( (unsigned int)CLstBxWinHost::IsSelected(this, v8) && *((_DWORD *)this + 48) )
      {
        v10 = *((_DWORD *)this + 37);
        v11 = *((_DWORD *)this + 38);
      }
      CLstBxWinHost::SetColors(this, v10, v11, v8, v8);
    }
  }
  v12 = v3 + 1;
  v13 = a2;
  if ( v3 + 1 < v7 )
  {
    do
    {
      v14 = (_DWORD *)CDynamicArray<CLbData>::Get((char *)this + 224, v12);
      v15 = (_DWORD *)CDynamicArray<CLbData>::operator[]((char *)this + 224, v13);
      *v15 ^= (*v14 ^ *v15) & 1;
      LODWORD(v14) = *(_DWORD *)(CDynamicArray<CLbData>::Get((char *)this + 224, v12) + 4);
      v16 = CDynamicArray<CLbData>::operator[]((char *)this + 224, v13++);
      ++v12;
      *(_DWORD *)(v16 + 4) = (_DWORD)v14;
    }
    while ( (int)v12 < v7 );
    v3 = v32;
  }
  v17 = *((_DWORD *)this + 48);
  for ( i = v12 - 1; (int)i >= v17; v17 = *((_DWORD *)this + 48) )
  {
    v19 = (_DWORD *)CDynamicArray<CLbData>::operator[]((char *)this + 224, i);
    *v19 &= ~1u;
    v20 = CDynamicArray<CLbData>::operator[]((char *)this + 224, i--);
    *(_DWORD *)(v20 + 4) = 0;
  }
  if ( v17 <= 0 )
  {
    CLstBxWinHost::SetTopViewableItem(this, 0);
    *(_QWORD *)((char *)this + 196) = -1;
  }
  else
  {
    v21 = *((_DWORD *)this + 50);
    if ( a2 <= v21 )
      --v21;
    v22 = v17 - 1;
    if ( v21 >= v22 )
      v21 = v22;
    v23 = *((_DWORD *)this + 33) == 3;
    *((_DWORD *)this + 50) = v21;
    if ( v23 )
    {
      v24 = *((_DWORD *)this + 49);
      if ( v21 < 0 || v24 >= 0 && a2 <= v24 && v24 <= v3 )
      {
        *((_DWORD *)this + 49) = -1;
        if ( v24 < v22 )
          v22 = v24;
        *((_DWORD *)this + 51) = v22;
      }
    }
    if ( (*((_BYTE *)this + 128) & 1) != 0 )
    {
      rcDst = 0;
      v34 = 0;
      CLstBxWinHost::LbGetItemRect(this, a2, &rcDst);
      CLstBxWinHost::LbGetItemRect(this, v3, &v34);
      rcDst.bottom = v34.bottom;
      if ( IntersectRect(&rcDst, &rcDst, (const RECT *)((char *)this + 164)) )
      {
        v25 = (HWND)*((_QWORD *)this + 2);
        rcDst.bottom = *((_DWORD *)this + 44);
        InvalidateRect(v25, &rcDst, 1);
      }
    }
  }
  if ( *((_DWORD *)this + 46) < *((_DWORD *)this + 45) && (*((_BYTE *)this + 128) & 8) != 0 )
  {
    v26 = *((_DWORD *)this + 47);
    if ( *((_DWORD *)this + 48) <= v26 && v7 > v26 )
      (*(void (__fastcall **)(CLstBxWinHost *, __int64, __int64))(*(_QWORD *)this + 48LL))(this, 1, 3);
  }
  CLstBxWinHost::LbDeleteItemNotify(this, a2, v3);
  v27 = *((_DWORD *)this + 48);
  if ( v27 )
  {
    v28 = *((_DWORD *)this + 31);
    v29 = v27 - 1;
    if ( v28 >= v29 )
      v28 = v29;
    CLstBxWinHost::LbShowIndex(this, v28, 0);
  }
  CLstBxWinHost::Unfreeze(this);
  return 1;
}

```

## disassembly

```asm
0x1800699dc  mov     [rsp-38h+arg_18], rbx
0x1800699e1  push    rbp
0x1800699e2  push    rsi
0x1800699e3  push    rdi
0x1800699e4  push    r12
0x1800699e6  push    r13
0x1800699e8  push    r14
0x1800699ea  push    r15
0x1800699ec  mov     rbp, rsp
0x1800699ef  sub     rsp, 70h
0x1800699f3  mov     rax, cs:__security_cookie
0x1800699fa  xor     rax, rsp
0x1800699fd  mov     [rbp+var_8], rax
0x180069a01  mov     r15d, r8d
0x180069a04  mov     [rbp+var_30], r8d
0x180069a08  mov     r14d, edx
0x180069a0b  mov     rdi, rcx
0x180069a0e  call    ?Freeze@CLstBxWinHost@@QEAAXXZ; CLstBxWinHost::Freeze(void)
0x180069a13  xor     r12d, r12d
0x180069a16  lea     r9, [rbp+var_38]; struct ITextRange **
0x180069a1a  mov     r8d, r15d; int
0x180069a1d  mov     [rbp+var_38], r12
0x180069a21  mov     edx, r14d; int
0x180069a24  mov     rcx, rdi; this
0x180069a27  call    ?GetRange@CLstBxWinHost@@QEAAHJJPEAPEAUITextRange@@@Z; CLstBxWinHost::GetRange(long,long,ITextRange * *)
0x180069a2c  test    eax, eax
0x180069a2e  jnz     short loc_180069A3F
0x180069a30  mov     rcx, rdi; this
0x180069a33  call    ?Unfreeze@CLstBxWinHost@@QEAAXXZ; CLstBxWinHost::Unfreeze(void)
0x180069a38  xor     eax, eax
0x180069a3a  jmp     loc_180069D62
0x180069a3f  or      ebx, 0FFFFFFFFh
0x180069a42  mov     [rbp+var_40], r12d
0x180069a46  test    r14d, r14d
0x180069a49  jz      short loc_180069A85
0x180069a4b  mov     rcx, [rbp+var_38]
0x180069a4f  lea     r9, [rbp+var_40]
0x180069a53  mov     r8d, ebx
0x180069a56  lea     edx, [rbx+2]
0x180069a59  mov     rax, [rcx]
0x180069a5c  mov     rax, [rax+120h]
0x180069a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a68  mov     rcx, [rbp+var_38]
0x180069a6c  lea     r9, [rbp+var_40]
0x180069a70  mov     r8d, ebx
0x180069a73  lea     edx, [rbx+2]
0x180069a76  mov     rax, [rcx]
0x180069a79  mov     rax, [rax+128h]
0x180069a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a85  mov     rcx, [rbp+var_38]
0x180069a89  lea     r9, [rbp+var_40]
0x180069a8d  xor     r8d, r8d
0x180069a90  mov     rax, [rcx]
0x180069a93  lea     edx, [r8+1]
0x180069a97  mov     rax, [rax+178h]
0x180069a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069aa3  test    eax, eax
0x180069aa5  jz      short loc_180069ACD
0x180069aa7  cmp     dword ptr [rdi+0C0h], 1
0x180069aae  jle     short loc_180069ACD
0x180069ab0  mov     rcx, rdi; this
0x180069ab3  call    ?Unfreeze@CLstBxWinHost@@QEAAXXZ; CLstBxWinHost::Unfreeze(void)
0x180069ab8  mov     rcx, [rbp+var_38]
0x180069abc  mov     rax, [rcx]
0x180069abf  mov     rax, [rax+10h]
0x180069ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069ac8  jmp     loc_180069A38
0x180069acd  mov     rcx, [rbp+var_38]
0x180069ad1  mov     rax, [rcx]
0x180069ad4  mov     rax, [rax+10h]
0x180069ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069add  mov     r13d, [rdi+0C0h]
0x180069ae4  lea     esi, [r14-1]
0x180069ae8  mov     eax, r13d
0x180069aeb  sub     eax, r15d
0x180069aee  dec     eax
0x180069af0  add     eax, r14d
0x180069af3  test    esi, esi
0x180069af5  mov     [rdi+0C0h], eax
0x180069afb  cmovle  esi, r12d
0x180069aff  test    byte ptr [rdi+80h], 1
0x180069b06  jnz     short loc_180069B6C
0x180069b08  mov     edx, esi; int
0x180069b0a  mov     rcx, rdi; this
0x180069b0d  call    ?IsSelected@CLstBxWinHost@@QEAAHJ@Z; CLstBxWinHost::IsSelected(long)
0x180069b12  mov     edx, r15d; int
0x180069b15  mov     rcx, rdi; this
0x180069b18  mov     ebx, eax
0x180069b1a  call    ?IsSelected@CLstBxWinHost@@QEAAHJ@Z; CLstBxWinHost::IsSelected(long)
0x180069b1f  cmp     eax, ebx
0x180069b21  jnz     short loc_180069B2C
0x180069b23  cmp     [rdi+0C0h], r12d
0x180069b2a  jnz     short loc_180069B6C
0x180069b2c  mov     ebx, 0FF676983h
0x180069b31  mov     edx, esi; int
0x180069b33  mov     rcx, rdi; this
0x180069b36  mov     r12d, ebx
0x180069b39  call    ?IsSelected@CLstBxWinHost@@QEAAHJ@Z; CLstBxWinHost::IsSelected(long)
0x180069b3e  test    eax, eax
0x180069b40  jz      short loc_180069B58
0x180069b42  cmp     dword ptr [rdi+0C0h], 0
0x180069b49  jz      short loc_180069B58
0x180069b4b  mov     ebx, [rdi+94h]
0x180069b51  mov     r12d, [rdi+98h]
0x180069b58  mov     r9d, esi; int
0x180069b5b  mov     [rsp+70h+var_50], esi; int
0x180069b5f  mov     r8d, r12d; unsigned int
0x180069b62  mov     edx, ebx; unsigned int
0x180069b64  mov     rcx, rdi; this
0x180069b67  call    ?SetColors@CLstBxWinHost@@IEAAHKKJJ@Z; CLstBxWinHost::SetColors(ulong,ulong,long,long)
0x180069b6c  lea     esi, [r15+1]
0x180069b70  mov     r12d, r14d
0x180069b73  cmp     esi, r13d
0x180069b76  jge     short loc_180069BC9
0x180069b78  lea     r15, [rdi+0E0h]
0x180069b7f  mov     edx, esi
0x180069b81  mov     rcx, r15
0x180069b84  call    ?Get@?$CDynamicArray@VCLbData@@@@QEAAAEBVCLbData@@H@Z; CDynamicArray<CLbData>::Get(int)
0x180069b89  mov     edx, r12d
0x180069b8c  mov     rcx, r15
0x180069b8f  mov     rbx, rax
0x180069b92  call    ??A?$CDynamicArray@VCLbData@@@@QEAAAEAVCLbData@@H@Z; CDynamicArray<CLbData>::operator[](int)
0x180069b97  mov     edx, esi
0x180069b99  mov     ecx, [rax]
0x180069b9b  xor     ecx, [rbx]
0x180069b9d  and     ecx, 1
0x180069ba0  xor     [rax], ecx
0x180069ba2  mov     rcx, r15
0x180069ba5  call    ?Get@?$CDynamicArray@VCLbData@@@@QEAAAEBVCLbData@@H@Z; CDynamicArray<CLbData>::Get(int)
0x180069baa  mov     edx, r12d
0x180069bad  mov     rcx, r15
0x180069bb0  mov     ebx, [rax+4]
0x180069bb3  call    ??A?$CDynamicArray@VCLbData@@@@QEAAAEAVCLbData@@H@Z; CDynamicArray<CLbData>::operator[](int)
0x180069bb8  inc     r12d
0x180069bbb  inc     esi
0x180069bbd  mov     [rax+4], ebx
0x180069bc0  cmp     esi, r13d
0x180069bc3  jl      short loc_180069B7F
0x180069bc5  mov     r15d, [rbp+var_30]
0x180069bc9  mov     eax, [rdi+0C0h]
0x180069bcf  dec     esi
0x180069bd1  cmp     esi, eax
0x180069bd3  jl      short loc_180069C06
0x180069bd5  lea     rbx, [rdi+0E0h]
0x180069bdc  mov     edx, esi
0x180069bde  mov     rcx, rbx
0x180069be1  call    ??A?$CDynamicArray@VCLbData@@@@QEAAAEAVCLbData@@H@Z; CDynamicArray<CLbData>::operator[](int)
0x180069be6  mov     edx, esi
0x180069be8  mov     rcx, rbx
0x180069beb  and     dword ptr [rax], 0FFFFFFFEh
0x180069bee  call    ??A?$CDynamicArray@VCLbData@@@@QEAAAEAVCLbData@@H@Z; CDynamicArray<CLbData>::operator[](int)
0x180069bf3  dec     esi
0x180069bf5  mov     dword ptr [rax+4], 0
0x180069bfc  mov     eax, [rdi+0C0h]
0x180069c02  cmp     esi, eax
0x180069c04  jge     short loc_180069BDC
0x180069c06  test    eax, eax
0x180069c08  jle     loc_180069CD1
0x180069c0e  mov     ecx, [rdi+0C8h]
0x180069c14  cmp     r14d, ecx
0x180069c17  jg      short loc_180069C1B
0x180069c19  dec     ecx
0x180069c1b  dec     eax
0x180069c1d  cmp     ecx, eax
0x180069c1f  cmovge  ecx, eax
0x180069c22  cmp     dword ptr [rdi+84h], 3
0x180069c29  mov     [rdi+0C8h], ecx
0x180069c2f  jnz     short loc_180069C5E
0x180069c31  mov     edx, [rdi+0C4h]
0x180069c37  test    ecx, ecx
0x180069c39  js      short loc_180069C49
0x180069c3b  test    edx, edx
0x180069c3d  js      short loc_180069C5E
0x180069c3f  cmp     r14d, edx
0x180069c42  jg      short loc_180069C5E
0x180069c44  cmp     edx, r15d
0x180069c47  jg      short loc_180069C5E
0x180069c49  cmp     edx, eax
0x180069c4b  mov     dword ptr [rdi+0C4h], 0FFFFFFFFh
0x180069c55  cmovl   eax, edx
0x180069c58  mov     [rdi+0CCh], eax
0x180069c5e  test    byte ptr [rdi+80h], 1
0x180069c65  jz      short loc_180069CE6
0x180069c67  xorps   xmm0, xmm0
0x180069c6a  lea     r8, [rbp+rcDst]; struct tagRECT *
0x180069c6e  xorps   xmm1, xmm1
0x180069c71  mov     edx, r14d; int
0x180069c74  mov     rcx, rdi; this
0x180069c77  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x180069c7b  movups  xmmword ptr [rbp+var_18.left], xmm1
0x180069c7f  call    ?LbGetItemRect@CLstBxWinHost@@QEAAHHPEAUtagRECT@@@Z; CLstBxWinHost::LbGetItemRect(int,tagRECT *)
0x180069c84  lea     r8, [rbp+var_18]; struct tagRECT *
0x180069c88  mov     edx, r15d; int
0x180069c8b  mov     rcx, rdi; this
0x180069c8e  call    ?LbGetItemRect@CLstBxWinHost@@QEAAHHPEAUtagRECT@@@Z; CLstBxWinHost::LbGetItemRect(int,tagRECT *)
0x180069c93  mov     eax, [rbp+var_18.bottom]
0x180069c96  lea     r8, [rdi+0A4h]; lprcSrc2
0x180069c9d  lea     rdx, [rbp+rcDst]; lprcSrc1
0x180069ca1  mov     [rbp+rcDst.bottom], eax
0x180069ca4  lea     rcx, [rbp+rcDst]; lprcDst
0x180069ca8  call    cs:__imp_IntersectRect
0x180069cae  test    eax, eax
0x180069cb0  jz      short loc_180069CE6
0x180069cb2  mov     eax, [rdi+0B0h]
0x180069cb8  lea     rdx, [rbp+rcDst]; lpRect
0x180069cbc  mov     rcx, [rdi+10h]; hWnd
0x180069cc0  mov     r8d, 1; bErase
0x180069cc6  mov     [rbp+rcDst.bottom], eax
0x180069cc9  call    cs:__imp_InvalidateRect
0x180069ccf  jmp     short loc_180069CE6
0x180069cd1  xor     edx, edx; int
0x180069cd3  mov     rcx, rdi; this
0x180069cd6  call    ?SetTopViewableItem@CLstBxWinHost@@IEAAHJ@Z; CLstBxWinHost::SetTopViewableItem(long)
0x180069cdb  mov     qword ptr [rdi+0C4h], 0FFFFFFFFFFFFFFFFh
0x180069ce6  mov     eax, [rdi+0B4h]
0x180069cec  cmp     [rdi+0B8h], eax
0x180069cf2  jge     short loc_180069D28
0x180069cf4  test    byte ptr [rdi+80h], 8
0x180069cfb  jz      short loc_180069D28
0x180069cfd  mov     eax, [rdi+0BCh]
0x180069d03  cmp     [rdi+0C0h], eax
0x180069d09  jg      short loc_180069D28
0x180069d0b  cmp     r13d, eax
0x180069d0e  jle     short loc_180069D28
0x180069d10  mov     rax, [rdi]
0x180069d13  mov     edx, 1
0x180069d18  mov     rcx, rdi
0x180069d1b  mov     rax, [rax+30h]
0x180069d1f  lea     r8d, [rdx+2]
0x180069d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069d28  mov     r8d, r15d; int
0x180069d2b  mov     edx, r14d; int
0x180069d2e  mov     rcx, rdi; this
0x180069d31  call    ?LbDeleteItemNotify@CLstBxWinHost@@QEAAXHH@Z; CLstBxWinHost::LbDeleteItemNotify(int,int)
0x180069d36  mov     ecx, [rdi+0C0h]
0x180069d3c  test    ecx, ecx
0x180069d3e  jz      short loc_180069D55
0x180069d40  mov     edx, [rdi+7Ch]
0x180069d43  dec     ecx
0x180069d45  cmp     edx, ecx
0x180069d47  cmovge  edx, ecx; int
0x180069d4a  xor     r8d, r8d; int
0x180069d4d  mov     rcx, rdi; this
0x180069d50  call    ?LbShowIndex@CLstBxWinHost@@QEAAHJH@Z; CLstBxWinHost::LbShowIndex(long,int)
0x180069d55  mov     rcx, rdi; this
0x180069d58  call    ?Unfreeze@CLstBxWinHost@@QEAAXXZ; CLstBxWinHost::Unfreeze(void)
0x180069d5d  mov     eax, 1
0x180069d62  mov     rcx, [rbp+var_8]
0x180069d66  xor     rcx, rsp; StackCookie
0x180069d69  call    __security_check_cookie
0x180069d6e  mov     rbx, [rsp+70h+arg_18]
0x180069d76  add     rsp, 70h
0x180069d7a  pop     r15
0x180069d7c  pop     r14
0x180069d7e  pop     r13
0x180069d80  pop     r12
0x180069d82  pop     rdi
0x180069d83  pop     rsi
0x180069d84  pop     rbp
0x180069d85  retn
```
