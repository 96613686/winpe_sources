# xpsrdr::CreateRectGeometry(xpsrdr::RenderState &,D2D_RECT_F const &)

- ea: `0x1800aa378`
- end: `0x1800aa58d`
- name: `?CreateRectGeometry@xpsrdr@@YA?AV?$shared_ptr@UID2D1Geometry@@@std@@AEAURenderState@1@AEBUD2D_RECT_F@@@Z`
- size: `533`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800b1150`
- `0x1800bb854`

## callees

- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800aa378`
- `0x1800b20e8`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
std::_Ref_count_base **__fastcall xpsrdr::CreateRectGeometry(std::_Ref_count_base **a1, __int64 a2, __int64 a3)
{
  __int64 *v5; // rcx
  __int64 v6; // rax
  int v7; // edi
  int v8; // edx
  const char *v9; // r8
  int v10; // r9d
  __int64 v11; // rax
  int v12; // edi
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d
  __int64 v16; // rax
  int v17; // eax
  int v18; // edx
  const char *v19; // r8
  int v20; // r9d
  std::_Ref_count_base *v22[2]; // [rsp+28h] [rbp-38h] BYREF
  std::_Ref_count_base *v23[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v24; // [rsp+48h] [rbp-18h] BYREF
  xpsrdr **v25; // [rsp+50h] [rbp-10h]
  std::_Ref_count_base **v26; // [rsp+58h] [rbp-8h]
  xpsrdr *v27; // [rsp+88h] [rbp+28h] BYREF
  unsigned __int64 v28; // [rsp+98h] [rbp+38h] BYREF

  *(_OWORD *)v23 = 0;
  LODWORD(v27) = 0;
  v5 = *(__int64 **)(a2 + 16);
  v6 = *v5;
  v24 = 0;
  v25 = &v27;
  v26 = v23;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v6 + 80))(v5, &v24);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v24);
  if ( (int)v27 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v27, v8, v9, v10);
  if ( v7 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v7, v8, v9, v10);
  *(_OWORD *)v22 = 0;
  LODWORD(v27) = 0;
  v11 = *(_QWORD *)v23[0];
  v24 = 0;
  v25 = &v27;
  v26 = v22;
  v12 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64 *))(v11 + 136))(v23[0], &v24);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v24);
  if ( (int)v27 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v27, v13, v14, v15);
  if ( v12 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v12, v13, v14, v15);
  (*(void (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v22[0] + 24LL))(v22[0], 1);
  v28 = *(_QWORD *)a3;
  v16 = *(_QWORD *)v22[0];
  v28 = _mm_unpacklo_ps((__m128)(unsigned int)v28, (__m128)HIDWORD(v28)).m128_u64[0];
  (*(void (__fastcall **)(std::_Ref_count_base *, unsigned __int64, _QWORD))(v16 + 40))(v22[0], v28, 0);
  LODWORD(v28) = *(_DWORD *)(a3 + 8);
  HIDWORD(v28) = *(_DWORD *)(a3 + 4);
  (*(void (__fastcall **)(std::_Ref_count_base *, unsigned __int64 *, __int64))(*(_QWORD *)v22[0] + 48LL))(
    v22[0],
    &v28,
    1);
  v28 = *(_QWORD *)(a3 + 8);
  (*(void (__fastcall **)(std::_Ref_count_base *, unsigned __int64 *, __int64))(*(_QWORD *)v22[0] + 48LL))(
    v22[0],
    &v28,
    1);
  LODWORD(v28) = *(_DWORD *)a3;
  HIDWORD(v28) = *(_DWORD *)(a3 + 12);
  (*(void (__fastcall **)(std::_Ref_count_base *, unsigned __int64 *, __int64))(*(_QWORD *)v22[0] + 48LL))(
    v22[0],
    &v28,
    1);
  (*(void (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v22[0] + 64LL))(v22[0], 1);
  v17 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v22[0] + 72LL))(v22[0]);
  if ( v17 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v17, v18, v19, v20);
  *a1 = v23[0];
  a1[1] = v23[1];
  *(_OWORD *)v23 = 0;
  if ( v22[1] )
    std::_Ref_count_base::_Decref(v22[1]);
  if ( v23[1] )
    std::_Ref_count_base::_Decref(v23[1]);
  return a1;
}

```

## disassembly

```asm
0x1800aa378  mov     [rsp-18h+arg_0], rbx
0x1800aa37d  push    rbp
0x1800aa37e  push    rsi
0x1800aa37f  push    rdi
0x1800aa380  mov     rbp, rsp
0x1800aa383  sub     rsp, 60h
0x1800aa387  mov     rsi, r8
0x1800aa38a  mov     rbx, rcx
0x1800aa38d  xorps   xmm0, xmm0
0x1800aa390  movdqu  xmmword ptr [rbp+var_28], xmm0
0x1800aa395  mov     dword ptr [rbp+arg_8], 0
0x1800aa39c  mov     rcx, [rdx+10h]
0x1800aa3a0  mov     rax, [rcx]
0x1800aa3a3  mov     [rbp+var_18], 0
0x1800aa3ab  lea     rdx, [rbp+arg_8]
0x1800aa3af  mov     [rbp+var_10], rdx
0x1800aa3b3  lea     rdx, [rbp+var_28]
0x1800aa3b7  mov     [rbp+var_8], rdx
0x1800aa3bb  lea     rdx, [rbp+var_18]
0x1800aa3bf  mov     rax, [rax+50h]
0x1800aa3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa3c8  mov     edi, eax
0x1800aa3ca  lea     rcx, [rbp+var_18]
0x1800aa3ce  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800aa3d3  mov     ecx, dword ptr [rbp+arg_8]; this
0x1800aa3d6  test    ecx, ecx
0x1800aa3d8  jns     short loc_1800AA3E0
0x1800aa3da  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800aa3e0  test    edi, edi
0x1800aa3e2  jns     short loc_1800AA3EC
0x1800aa3e4  mov     ecx, edi; this
0x1800aa3e6  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800aa3ec  xorps   xmm0, xmm0
0x1800aa3ef  movdqu  xmmword ptr [rbp+var_38], xmm0
0x1800aa3f4  mov     dword ptr [rbp+arg_8], 0
0x1800aa3fb  mov     rcx, [rbp+var_28]
0x1800aa3ff  mov     rax, [rcx]
0x1800aa402  mov     [rbp+var_18], 0
0x1800aa40a  lea     rdx, [rbp+arg_8]
0x1800aa40e  mov     [rbp+var_10], rdx
0x1800aa412  lea     rdx, [rbp+var_38]
0x1800aa416  mov     [rbp+var_8], rdx
0x1800aa41a  lea     rdx, [rbp+var_18]
0x1800aa41e  mov     rax, [rax+88h]
0x1800aa425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa42a  mov     edi, eax
0x1800aa42c  lea     rcx, [rbp+var_18]
0x1800aa430  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800aa435  mov     ecx, dword ptr [rbp+arg_8]; this
0x1800aa438  test    ecx, ecx
0x1800aa43a  jns     short loc_1800AA442
0x1800aa43c  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800aa442  test    edi, edi
0x1800aa444  jns     short loc_1800AA44E
0x1800aa446  mov     ecx, edi; this
0x1800aa448  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800aa44e  mov     rcx, [rbp+var_38]
0x1800aa452  mov     rax, [rcx]
0x1800aa455  mov     edi, 1
0x1800aa45a  mov     edx, edi
0x1800aa45c  mov     rax, [rax+18h]
0x1800aa460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa465  movss   xmm1, dword ptr [rsi]
0x1800aa469  movss   dword ptr [rbp+arg_18], xmm1
0x1800aa46e  movss   xmm0, dword ptr [rsi+4]
0x1800aa473  movss   dword ptr [rbp+arg_18+4], xmm0
0x1800aa478  mov     rcx, [rbp+var_38]
0x1800aa47c  mov     rax, [rcx]
0x1800aa47f  xor     r8d, r8d
0x1800aa482  unpcklps xmm1, xmm0
0x1800aa485  movsd   [rbp+arg_18], xmm1
0x1800aa48a  movq    rdx, xmm1
0x1800aa48f  mov     rax, [rax+28h]
0x1800aa493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa498  movss   xmm0, dword ptr [rsi+8]
0x1800aa49d  movss   dword ptr [rbp+arg_18], xmm0
0x1800aa4a2  movss   xmm1, dword ptr [rsi+4]
0x1800aa4a7  movss   dword ptr [rbp+arg_18+4], xmm1
0x1800aa4ac  mov     rcx, [rbp+var_38]
0x1800aa4b0  mov     rax, [rcx]
0x1800aa4b3  mov     r8d, edi
0x1800aa4b6  lea     rdx, [rbp+arg_18]
0x1800aa4ba  mov     rax, [rax+30h]
0x1800aa4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa4c3  movss   xmm0, dword ptr [rsi+8]
0x1800aa4c8  movss   dword ptr [rbp+arg_18], xmm0
0x1800aa4cd  movss   xmm1, dword ptr [rsi+0Ch]
0x1800aa4d2  movss   dword ptr [rbp+arg_18+4], xmm1
0x1800aa4d7  mov     rcx, [rbp+var_38]
0x1800aa4db  mov     rax, [rcx]
0x1800aa4de  mov     r8d, edi
0x1800aa4e1  lea     rdx, [rbp+arg_18]
0x1800aa4e5  mov     rax, [rax+30h]
0x1800aa4e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa4ee  movss   xmm0, dword ptr [rsi]
0x1800aa4f2  movss   dword ptr [rbp+arg_18], xmm0
0x1800aa4f7  movss   xmm1, dword ptr [rsi+0Ch]
0x1800aa4fc  movss   dword ptr [rbp+arg_18+4], xmm1
0x1800aa501  mov     rcx, [rbp+var_38]
0x1800aa505  mov     rax, [rcx]
0x1800aa508  mov     r8d, edi
0x1800aa50b  lea     rdx, [rbp+arg_18]
0x1800aa50f  mov     rax, [rax+30h]
0x1800aa513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa518  mov     rcx, [rbp+var_38]
0x1800aa51c  mov     rax, [rcx]
0x1800aa51f  mov     edx, edi
0x1800aa521  mov     rax, [rax+40h]
0x1800aa525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa52a  mov     rcx, [rbp+var_38]
0x1800aa52e  mov     rax, [rcx]
0x1800aa531  mov     rax, [rax+48h]
0x1800aa535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa53a  test    eax, eax
0x1800aa53c  jns     short loc_1800AA546
0x1800aa53e  mov     ecx, eax; this
0x1800aa540  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800aa546  mov     rax, [rbp+var_28]
0x1800aa54a  mov     [rbx], rax
0x1800aa54d  mov     rax, [rbp+var_28+8]
0x1800aa551  mov     [rbx+8], rax
0x1800aa555  xorps   xmm0, xmm0
0x1800aa558  movdqu  xmmword ptr [rbp+var_28], xmm0
0x1800aa55d  mov     rcx, [rbp+var_38+8]; this
0x1800aa561  test    rcx, rcx
0x1800aa564  jz      short loc_1800AA56C
0x1800aa566  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800aa56b  nop
0x1800aa56c  mov     rcx, [rbp+var_28+8]; this
0x1800aa570  test    rcx, rcx
0x1800aa573  jz      short loc_1800AA57A
0x1800aa575  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800aa57a  mov     rax, rbx
0x1800aa57d  mov     rbx, [rsp+60h+arg_0]
0x1800aa585  add     rsp, 60h
0x1800aa589  pop     rdi
0x1800aa58a  pop     rsi
0x1800aa58b  pop     rbp
0x1800aa58c  retn
```
