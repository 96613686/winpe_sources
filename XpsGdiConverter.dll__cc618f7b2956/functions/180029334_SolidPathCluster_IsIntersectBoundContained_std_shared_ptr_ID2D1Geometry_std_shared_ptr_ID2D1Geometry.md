# SolidPathCluster::IsIntersectBoundContained(std::shared_ptr<ID2D1Geometry>,std::shared_ptr<ID2D1Geometry>)

- ea: `0x180029334`
- end: `0x180029444`
- name: `?IsIntersectBoundContained@SolidPathCluster@@AEAA_NV?$shared_ptr@UID2D1Geometry@@@std@@0@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180028810`

## callees

- `0x180008830`
- `0x18000e990`
- `0x180011b0c`
- `0x180029334`
- `0x180033a70`
- `0x180034cac`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall SolidPathCluster::IsIntersectBoundContained(__int64 *a1, __int64 a2, _QWORD *a3)
{
  bool v6; // bl
  __int64 v7; // r8
  _QWORD *v8; // rdx
  unsigned int v9; // eax
  bool v10; // al
  int v11; // edx
  _QWORD v13[4]; // [rsp+38h] [rbp-38h] BYREF
  __int128 v14; // [rsp+58h] [rbp-18h] BYREF

  v13[2] = a2;
  v13[3] = a3;
  v14 = 0;
  v6 = 0;
  if ( (unsigned __int8)std::operator!=<ID3D11Device>(a2) )
  {
    if ( (unsigned __int8)std::operator!=<ID3D11Device>(v7) )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)*v8 + 32LL))(*v8, 0, &v14);
      v10 = xpsrdr::RectEmpty((xpsrdr *)&v14, (const struct D2D_RECT_F *)v9);
      v6 = v10;
      if ( v11 >= 0 && !v10 )
      {
        xpsrdr::CreateRectGeometry((__int64)v13, *a1, (__int64)&v14);
        if ( (unsigned __int8)std::operator!=<ID3D11Device>(v13) )
          (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v13[0] + 64LL))(v13[0], *a3, 0);
        v6 = 0;
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v13);
      }
    }
  }
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(a2);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(a3);
  return v6;
}

```

## disassembly

```asm
0x180029334  push    rbp
0x180029336  push    rbx
0x180029337  push    rsi
0x180029338  push    rdi
0x180029339  push    r14
0x18002933b  mov     rbp, rsp
0x18002933e  sub     rsp, 70h
0x180029342  mov     rax, cs:__security_cookie
0x180029349  xor     rax, rsp
0x18002934c  mov     [rbp+var_8], rax
0x180029350  mov     rdi, r8
0x180029353  mov     rsi, rdx
0x180029356  mov     r14, rcx
0x180029359  mov     [rbp+var_28], rdx
0x18002935d  mov     [rbp+var_20], r8
0x180029361  xorps   xmm0, xmm0
0x180029364  movups  [rbp+var_18], xmm0
0x180029368  xor     bl, bl
0x18002936a  mov     rcx, rdx
0x18002936d  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180029372  test    al, al
0x180029374  jz      loc_18002941A
0x18002937a  mov     rcx, r8
0x18002937d  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180029382  test    al, al
0x180029384  jz      loc_18002941A
0x18002938a  mov     rcx, [rdx]
0x18002938d  mov     rax, [rcx]
0x180029390  lea     r8, [rbp+var_18]
0x180029394  xor     edx, edx
0x180029396  mov     rax, [rax+20h]
0x18002939a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002939f  mov     edx, eax; struct D2D_RECT_F *
0x1800293a1  lea     rcx, [rbp+var_18]; this
0x1800293a5  call    ?RectEmpty@xpsrdr@@YA_NAEBUD2D_RECT_F@@@Z; xpsrdr::RectEmpty(D2D_RECT_F const &)
0x1800293aa  mov     bl, al
0x1800293ac  test    edx, edx
0x1800293ae  js      short loc_18002941A
0x1800293b0  test    al, al
0x1800293b2  jnz     short loc_18002941A
0x1800293b4  mov     [rbp+var_40], 0
0x1800293bb  lea     r8, [rbp+var_18]
0x1800293bf  mov     rdx, [r14]
0x1800293c2  lea     rcx, [rbp+var_38]
0x1800293c6  call    ?CreateRectGeometry@xpsrdr@@YA?AV?$shared_ptr@UID2D1Geometry@@@std@@AEAURenderState@1@AEBUD2D_RECT_F@@@Z; xpsrdr::CreateRectGeometry(xpsrdr::RenderState &,D2D_RECT_F const &)
0x1800293cb  nop
0x1800293cc  lea     rcx, [rbp+var_38]
0x1800293d0  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x1800293d5  test    al, al
0x1800293d7  jz      short loc_18002940E
0x1800293d9  mov     rcx, [rbp+var_38]
0x1800293dd  mov     rax, [rcx]
0x1800293e0  lea     rdx, [rbp+var_40]
0x1800293e4  mov     [rsp+70h+var_50], rdx
0x1800293e9  movss   xmm3, cs:__real@3d4ccccd
0x1800293f1  xor     r8d, r8d
0x1800293f4  mov     rdx, [rdi]
0x1800293f7  mov     rax, [rax+40h]
0x1800293fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029400  test    eax, eax
0x180029402  js      short loc_18002940E
0x180029404  cmp     [rbp+var_40], 2
0x180029408  jnz     short loc_18002940E
0x18002940a  mov     bl, 1
0x18002940c  jmp     short loc_180029410
0x18002940e  xor     bl, bl
0x180029410  lea     rcx, [rbp+var_38]
0x180029414  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180029419  nop
0x18002941a  mov     rcx, rsi
0x18002941d  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180029422  nop
0x180029423  mov     rcx, rdi
0x180029426  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002942b  mov     al, bl
0x18002942d  mov     rcx, [rbp+var_8]
0x180029431  xor     rcx, rsp; StackCookie
0x180029434  call    __security_check_cookie
0x180029439  add     rsp, 70h
0x18002943d  pop     r14
0x18002943f  pop     rdi
0x180029440  pop     rsi
0x180029441  pop     rbx
0x180029442  pop     rbp
0x180029443  retn
```
