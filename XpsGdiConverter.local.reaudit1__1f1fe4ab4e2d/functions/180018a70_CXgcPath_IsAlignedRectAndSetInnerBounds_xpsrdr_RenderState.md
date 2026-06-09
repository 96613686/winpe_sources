# CXgcPath::IsAlignedRectAndSetInnerBounds(xpsrdr::RenderState &)

- ea: `0x180018a70`
- end: `0x180018c7c`
- name: `?IsAlignedRectAndSetInnerBounds@CXgcPath@@QEAAXAEAURenderState@xpsrdr@@@Z`
- size: `524`
- prototype: `void __fastcall(CXgcPath *__hidden this, struct xpsrdr::RenderState *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180019680`

## callees

- `0x180008830`
- `0x18000e15c`
- `0x18000e990`
- `0x180011b0c`
- `0x1800123bc`
- `0x180018a70`
- `0x180033a70`
- `0x180034cac`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CXgcPath::IsAlignedRectAndSetInnerBounds(CXgcPath *this, struct xpsrdr::RenderState *a2)
{
  char *v4; // rdi
  const struct D2D_RECT_F *v5; // rdx
  int v6; // edx
  const struct D2D_RECT_F *v7; // rdx
  __int128 v8; // [rsp+40h] [rbp-41h] BYREF
  _QWORD v9[2]; // [rsp+50h] [rbp-31h] BYREF
  int v10[4]; // [rsp+60h] [rbp-21h] BYREF
  struct D2D_RECT_F v11; // [rsp+70h] [rbp-11h] BYREF

  v8 = 0;
  v4 = (char *)this + 216;
  if ( (unsigned __int8)std::operator!=<ID3D11Device>((char *)this + 216)
    && (unsigned __int8)std::operator!=<ID3D11Device>(*(_QWORD *)v4 + 16LL) )
  {
    v11 = 0;
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v10);
    CXgcGeometry::GetBounds(*(_QWORD *)v4, v6, (_DWORD)this + 104, (int)v10, &v11);
    if ( xpsrdr::RectEmpty((xpsrdr *)&v11, v7) )
    {
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v10);
      return;
    }
    xpsrdr::CreateRectGeometry((__int64)v9, (__int64)a2, (__int64)&v11);
    if ( (unsigned __int8)std::operator!=<ID3D11Device>(v9) )
      (*(void (__fastcall **)(_QWORD, _QWORD, char *))(*(_QWORD *)v9[0] + 64LL))(
        v9[0],
        *(_QWORD *)(*(_QWORD *)v4 + 16LL),
        (char *)this + 104);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v9);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v10);
  }
  if ( !xpsrdr::RectEmpty((xpsrdr *)&v8, v5) )
  {
    *((_DWORD *)this + 18) = 0;
    *((_DWORD *)this + 19) = 0;
    *((_DWORD *)this + 20) = 0;
    *((_DWORD *)this + 21) = 0;
  }
}

```

## disassembly

```asm
0x180018a70  mov     rax, rsp
0x180018a73  mov     [rax+18h], rbx
0x180018a77  mov     [rax+20h], rsi
0x180018a7b  push    rbp
0x180018a7c  push    rdi
0x180018a7d  push    r14
0x180018a7f  lea     rbp, [rax-5Fh]
0x180018a83  sub     rsp, 0C0h
0x180018a8a  movaps  xmmword ptr [rax-28h], xmm6
0x180018a8e  movaps  xmmword ptr [rax-38h], xmm7
0x180018a92  movaps  xmmword ptr [rax-48h], xmm8
0x180018a97  movaps  xmmword ptr [rax-58h], xmm9
0x180018a9c  mov     rax, cs:__security_cookie
0x180018aa3  xor     rax, rsp
0x180018aa6  mov     [rbp+57h+var_58], rax
0x180018aaa  mov     rsi, rdx
0x180018aad  mov     rbx, rcx
0x180018ab0  xorps   xmm0, xmm0
0x180018ab3  movups  [rbp+57h+var_98], xmm0
0x180018ab7  lea     rdi, [rcx+0D8h]
0x180018abe  mov     rcx, rdi
0x180018ac1  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180018ac6  test    al, al
0x180018ac8  jz      loc_180018C13
0x180018ace  mov     rcx, [rdi]
0x180018ad1  add     rcx, 10h
0x180018ad5  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180018ada  test    al, al
0x180018adc  jz      loc_180018C13
0x180018ae2  movups  xmmword ptr [rbp+57h+var_68.left], xmm0
0x180018ae6  lea     rcx, [rbp+57h+var_78]
0x180018aea  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180018aef  nop
0x180018af0  lea     rax, [rbp+57h+var_68]
0x180018af4  mov     [rsp+0D0h+var_B0], rax; struct D2D_RECT_F *
0x180018af9  lea     r9, [rbp+57h+var_78]; int
0x180018afd  lea     r8, [rbx+68h]; int
0x180018b01  mov     rcx, [rdi]; int
0x180018b04  call    ?GetBounds@CXgcGeometry@@QEAAXAEAURenderState@xpsrdr@@AEBUD2D_MATRIX_3X2_F@@AEBV?$shared_ptr@VCXgcPenStyle@@@std@@AEAUD2D_RECT_F@@@Z; CXgcGeometry::GetBounds(xpsrdr::RenderState &,D2D_MATRIX_3X2_F const &,std::shared_ptr<CXgcPenStyle> const &,D2D_RECT_F &)
0x180018b09  lea     rcx, [rbp+57h+var_68]; this
0x180018b0d  call    ?RectEmpty@xpsrdr@@YA_NAEBUD2D_RECT_F@@@Z; xpsrdr::RectEmpty(D2D_RECT_F const &)
0x180018b12  test    al, al
0x180018b14  jz      short loc_180018B24
0x180018b16  lea     rcx, [rbp+57h+var_78]
0x180018b1a  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180018b1f  jmp     loc_180018C44
0x180018b24  lea     r8, [rbp+57h+var_68]
0x180018b28  mov     rdx, rsi
0x180018b2b  lea     rcx, [rbp+57h+var_88]
0x180018b2f  call    ?CreateRectGeometry@xpsrdr@@YA?AV?$shared_ptr@UID2D1Geometry@@@std@@AEAURenderState@1@AEBUD2D_RECT_F@@@Z; xpsrdr::CreateRectGeometry(xpsrdr::RenderState &,D2D_RECT_F const &)
0x180018b34  lea     rcx, [rbp+57h+var_88]
0x180018b38  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180018b3d  test    al, al
0x180018b3f  jz      loc_180018BF0
0x180018b45  mov     [rbp+57h+var_A0], 0
0x180018b4c  mov     rcx, [rbp+57h+var_88]
0x180018b50  mov     rax, [rcx]
0x180018b53  mov     rdx, [rdi]
0x180018b56  lea     r8, [rbp+57h+var_A0]
0x180018b5a  mov     [rsp+0D0h+var_B0], r8
0x180018b5f  movss   xmm3, cs:__real@3e800000
0x180018b67  lea     r8, [rbx+68h]
0x180018b6b  mov     rdx, [rdx+10h]
0x180018b6f  mov     rax, [rax+40h]
0x180018b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b78  cmp     [rbp+57h+var_A0], 2
0x180018b7c  jnz     short loc_180018BF0
0x180018b7e  mov     byte ptr [rbx+1Dh], 1
0x180018b82  lea     rcx, [rbx+0A8h]
0x180018b89  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180018b8e  test    al, al
0x180018b90  jnz     short loc_180018BF0
0x180018b92  movss   xmm9, [rbp+57h+var_68.left]
0x180018b98  movss   xmm0, cs:__real@40000000
0x180018ba0  mulss   xmm9, xmm0
0x180018ba5  subss   xmm9, dword ptr [rbx+38h]
0x180018bab  movss   dword ptr [rbp+57h+var_98], xmm9
0x180018bb1  movss   xmm8, [rbp+57h+var_68.top]
0x180018bb7  mulss   xmm8, xmm0
0x180018bbc  subss   xmm8, dword ptr [rbx+3Ch]
0x180018bc2  movss   dword ptr [rbp+57h+var_98+4], xmm8
0x180018bc8  movss   xmm7, [rbp+57h+var_68.right]
0x180018bcd  mulss   xmm7, xmm0
0x180018bd1  subss   xmm7, dword ptr [rbx+40h]
0x180018bd6  movss   dword ptr [rbp+57h+var_98+8], xmm7
0x180018bdb  movss   xmm6, [rbp+57h+var_68.bottom]
0x180018be0  mulss   xmm6, xmm0
0x180018be4  subss   xmm6, dword ptr [rbx+44h]
0x180018be9  movss   dword ptr [rbp+57h+var_98+0Ch], xmm6
0x180018bee  jmp     short loc_180018BFE
0x180018bf0  xorps   xmm6, xmm6
0x180018bf3  xorps   xmm7, xmm7
0x180018bf6  xorps   xmm8, xmm8
0x180018bfa  xorps   xmm9, xmm9
0x180018bfe  lea     rcx, [rbp+57h+var_88]
0x180018c02  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180018c07  nop
0x180018c08  lea     rcx, [rbp+57h+var_78]
0x180018c0c  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180018c11  jmp     short loc_180018C21
0x180018c13  xorps   xmm9, xmm9
0x180018c17  xorps   xmm8, xmm8
0x180018c1b  xorps   xmm7, xmm7
0x180018c1e  xorps   xmm6, xmm6
0x180018c21  lea     rcx, [rbp+57h+var_98]; this
0x180018c25  call    ?RectEmpty@xpsrdr@@YA_NAEBUD2D_RECT_F@@@Z; xpsrdr::RectEmpty(D2D_RECT_F const &)
0x180018c2a  test    al, al
0x180018c2c  jnz     short loc_180018C44
0x180018c2e  movss   dword ptr [rbx+48h], xmm9
0x180018c34  movss   dword ptr [rbx+4Ch], xmm8
0x180018c3a  movss   dword ptr [rbx+50h], xmm7
0x180018c3f  movss   dword ptr [rbx+54h], xmm6
0x180018c44  mov     rcx, [rbp+57h+var_58]
0x180018c48  xor     rcx, rsp; StackCookie
0x180018c4b  call    __security_check_cookie
0x180018c50  lea     r11, [rsp+0D0h+var_10]
0x180018c58  mov     rbx, [r11+30h]
0x180018c5c  mov     rsi, [r11+38h]
0x180018c60  movaps  xmm6, xmmword ptr [r11-10h]
0x180018c65  movaps  xmm7, xmmword ptr [r11-20h]
0x180018c6a  movaps  xmm8, xmmword ptr [r11-30h]
0x180018c6f  movaps  xmm9, xmmword ptr [r11-40h]
0x180018c74  mov     rsp, r11
0x180018c77  pop     r14
0x180018c79  pop     rdi
0x180018c7a  pop     rbp
0x180018c7b  retn
```
