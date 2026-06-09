# SolidPathCluster::GetColorFromBrush(std::shared_ptr<IXpsOMSolidColorBrush>,bool)

- ea: `0x180029010`
- end: `0x180029146`
- name: `?GetColorFromBrush@SolidPathCluster@@AEAA?AU_D3DCOLORVALUE@@V?$shared_ptr@UIXpsOMSolidColorBrush@@@std@@_N@Z`
- size: `310`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180028acc`
- `0x18002969c`
- `0x18002976c`
- `0x18002990c`

## callees

- `0x180008830`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x180029010`
- `0x180036250`
- `0x180037278`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SolidPathCluster::GetColorFromBrush(_QWORD *a1, __int64 a2, _QWORD *a3, char a4)
{
  __int64 **v8; // r8
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // esi
  int v12; // edx
  const char *v13; // r8
  int v14; // r9d
  int v15; // eax
  int v16; // edx
  const char *v17; // r8
  int v18; // r9d
  xpsrdr *v20; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v21[16]; // [rsp+28h] [rbp-31h] BYREF
  _QWORD v22[4]; // [rsp+38h] [rbp-21h] BYREF
  _OWORD v23[3]; // [rsp+58h] [rbp-1h] BYREF

  v22[3] = a3;
  memset(v23, 0, 44);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v21);
  LODWORD(v20) = 0;
  v9 = *v8;
  v10 = **v8;
  v22[0] = 0;
  v22[1] = &v20;
  v22[2] = v21;
  v11 = (*(__int64 (__fastcall **)(__int64 *, _OWORD *, _QWORD *))(v10 + 56))(v9, v23, v22);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v22);
  if ( (int)v20 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v20, v12, v13, v14);
  if ( v11 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v11, v12, v13, v14);
  *(_OWORD *)a2 = *(_OWORD *)xpsrdr::GetD2D1Color(v22, *a1, v23, v21);
  if ( a4 )
  {
    LODWORD(v20) = 1065353216;
    v15 = (*(__int64 (__fastcall **)(_QWORD, xpsrdr **))(*(_QWORD *)*a3 + 40LL))(*a3, &v20);
    if ( v15 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v15, v16, v17, v18);
    *(float *)(a2 + 12) = *(float *)&v20 * *(float *)(a2 + 12);
  }
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v21);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(a3);
  return a2;
}

```

## disassembly

```asm
0x180029010  mov     [rsp-8+arg_18], rbx
0x180029015  push    rbp
0x180029016  push    rsi
0x180029017  push    rdi
0x180029018  push    r14
0x18002901a  push    r15
0x18002901c  lea     rbp, [rsp-37h]
0x180029021  sub     rsp, 90h
0x180029028  mov     rax, cs:__security_cookie
0x18002902f  xor     rax, rsp
0x180029032  mov     [rbp+57h+var_28], rax
0x180029036  mov     r14b, r9b
0x180029039  mov     rdi, r8
0x18002903c  mov     rbx, rdx
0x18002903f  mov     r15, rcx
0x180029042  mov     [rbp+57h+var_60], r8
0x180029046  xorps   xmm0, xmm0
0x180029049  movups  [rbp+57h+var_58], xmm0
0x18002904d  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x180029051  movups  xmmword ptr [rbp+57h+var_48+0Ch], xmm0
0x180029055  lea     rcx, [rbp+57h+var_88]
0x180029059  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002905e  nop
0x18002905f  mov     dword ptr [rbp+57h+var_90], 0
0x180029066  mov     rcx, [r8]
0x180029069  mov     rax, [rcx]
0x18002906c  mov     [rbp+57h+var_78], 0
0x180029074  lea     rdx, [rbp+57h+var_90]
0x180029078  mov     [rbp+57h+var_70], rdx
0x18002907c  lea     rdx, [rbp+57h+var_88]
0x180029080  mov     [rbp+57h+var_68], rdx
0x180029084  lea     r8, [rbp+57h+var_78]
0x180029088  lea     rdx, [rbp+57h+var_58]
0x18002908c  mov     rax, [rax+38h]
0x180029090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029095  mov     esi, eax
0x180029097  lea     rcx, [rbp+57h+var_78]
0x18002909b  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800290a0  mov     ecx, dword ptr [rbp+57h+var_90]; this
0x1800290a3  test    ecx, ecx
0x1800290a5  jns     short loc_1800290AD
0x1800290a7  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800290ad  test    esi, esi
0x1800290af  jns     short loc_1800290B9
0x1800290b1  mov     ecx, esi; this
0x1800290b3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800290b9  lea     r9, [rbp+57h+var_88]
0x1800290bd  lea     r8, [rbp+57h+var_58]
0x1800290c1  mov     rdx, [r15]
0x1800290c4  lea     rcx, [rbp+57h+var_78]
0x1800290c8  call    ?GetD2D1Color@xpsrdr@@YA?AU_D3DCOLORVALUE@@AEAURenderState@1@AEBU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024@@AEBV?$shared_ptr@UIXpsOMColorProfileResource@@@std@@@Z; xpsrdr::GetD2D1Color(xpsrdr::RenderState &,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024 const &,std::shared_ptr<IXpsOMColorProfileResource> const &)
0x1800290cd  movups  xmm0, xmmword ptr [rax]
0x1800290d0  movdqu  xmmword ptr [rbx], xmm0
0x1800290d4  test    r14b, r14b
0x1800290d7  jz      short loc_18002910E
0x1800290d9  mov     dword ptr [rbp+57h+var_90], 3F800000h
0x1800290e0  mov     rcx, [rdi]
0x1800290e3  mov     rax, [rcx]
0x1800290e6  lea     rdx, [rbp+57h+var_90]
0x1800290ea  mov     rax, [rax+28h]
0x1800290ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290f3  test    eax, eax
0x1800290f5  jns     short loc_1800290FF
0x1800290f7  mov     ecx, eax; this
0x1800290f9  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800290ff  movss   xmm0, dword ptr [rbp+57h+var_90]
0x180029104  mulss   xmm0, dword ptr [rbx+0Ch]
0x180029109  movss   dword ptr [rbx+0Ch], xmm0
0x18002910e  lea     rcx, [rbp+57h+var_88]
0x180029112  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180029117  nop
0x180029118  mov     rcx, rdi
0x18002911b  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180029120  mov     rax, rbx
0x180029123  mov     rcx, [rbp+57h+var_28]
0x180029127  xor     rcx, rsp; StackCookie
0x18002912a  call    __security_check_cookie
0x18002912f  mov     rbx, [rsp+0B0h+arg_18]
0x180029137  add     rsp, 90h
0x18002913e  pop     r15
0x180029140  pop     r14
0x180029142  pop     rdi
0x180029143  pop     rsi
0x180029144  pop     rbp
0x180029145  retn
```
