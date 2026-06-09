# xpsrdr::ColorContext::CreateFromProfile(xpsrdr::RenderState &,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800b96cc`
- end: `0x1800b984a`
- name: `?CreateFromProfile@ColorContext@xpsrdr@@SA?AV?$shared_ptr@UColorContext@xpsrdr@@@std@@AEAURenderState@2@AEBV?$vector@EV?$allocator@E@std@@@4@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800b9850`

## callees

- `0x18000358c`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800b20e8`
- `0x1800b8754`
- `0x1800b8a54`
- `0x1800b96cc`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall xpsrdr::ColorContext::CreateFromProfile(__int64 a1, __int64 **a2, __int64 a3)
{
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // ebx
  int v9; // edx
  const char *v10; // r8
  int v11; // r9d
  int v12; // eax
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d
  __int64 *v16; // rcx
  __int64 v17; // rax
  int v18; // ebx
  int v19; // edx
  const char *v20; // r8
  int v21; // r9d
  int v22; // eax
  int v23; // edx
  const char *v24; // r8
  int v25; // r9d
  __int64 v26; // rax
  std::_Ref_count_base *v28[2]; // [rsp+28h] [rbp-38h] BYREF
  std::_Ref_count_base *v29[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v30; // [rsp+48h] [rbp-18h] BYREF
  xpsrdr **v31; // [rsp+50h] [rbp-10h]
  std::_Ref_count_base **v32; // [rsp+58h] [rbp-8h]
  xpsrdr *v33; // [rsp+88h] [rbp+28h] BYREF

  *(_OWORD *)v29 = 0;
  *(_OWORD *)v28 = 0;
  LODWORD(v33) = 0;
  v6 = *a2;
  v7 = **a2;
  v30 = 0;
  v31 = &v33;
  v32 = v29;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v7 + 120))(v6, &v30);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v30);
  if ( (int)v33 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v33, v9, v10, v11);
  if ( v8 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v8, v9, v10, v11);
  v12 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, _QWORD))(*(_QWORD *)v29[0] + 32LL))(
          v29[0],
          *(_QWORD *)a3,
          (unsigned int)(*(_DWORD *)(a3 + 8) - *(_DWORD *)a3));
  if ( v12 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v12, v13, v14, v15);
  LODWORD(v33) = 0;
  v16 = *a2;
  v17 = **a2;
  v30 = 0;
  v31 = &v33;
  v32 = v28;
  v18 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v17 + 120))(v16, &v30);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v30);
  if ( (int)v33 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v33, v19, v20, v21);
  if ( v18 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v18, v19, v20, v21);
  v22 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v28[0] + 40LL))(v28[0], 1);
  if ( v22 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v22, v23, v24, v25);
  v33 = (xpsrdr *)operator new(0x68u);
  v26 = xpsrdr::ColorContext::ColorContext(v33, v29, v28);
  std::shared_ptr<xpsrdr::ColorContext>::shared_ptr<xpsrdr::ColorContext>(a1, v26);
  if ( v28[1] )
    std::_Ref_count_base::_Decref(v28[1]);
  if ( v29[1] )
    std::_Ref_count_base::_Decref(v29[1]);
  return a1;
}

```

## disassembly

```asm
0x1800b96cc  mov     [rsp-18h+arg_0], rbx
0x1800b96d1  mov     [rsp-18h+arg_10], rsi
0x1800b96d6  push    rbp
0x1800b96d7  push    rdi
0x1800b96d8  push    r14
0x1800b96da  mov     rbp, rsp
0x1800b96dd  sub     rsp, 60h
0x1800b96e1  mov     rsi, r8
0x1800b96e4  mov     r14, rdx
0x1800b96e7  mov     rdi, rcx
0x1800b96ea  xorps   xmm0, xmm0
0x1800b96ed  movdqu  xmmword ptr [rbp+var_28], xmm0
0x1800b96f2  movdqu  xmmword ptr [rbp+var_38], xmm0
0x1800b96f7  mov     dword ptr [rbp+arg_8], 0
0x1800b96fe  mov     rcx, [rdx]
0x1800b9701  mov     rax, [rcx]
0x1800b9704  mov     [rbp+var_18], 0
0x1800b970c  lea     rdx, [rbp+arg_8]
0x1800b9710  mov     [rbp+var_10], rdx
0x1800b9714  lea     rdx, [rbp+var_28]
0x1800b9718  mov     [rbp+var_8], rdx
0x1800b971c  lea     rdx, [rbp+var_18]
0x1800b9720  mov     rax, [rax+78h]
0x1800b9724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9729  mov     ebx, eax
0x1800b972b  lea     rcx, [rbp+var_18]
0x1800b972f  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b9734  mov     ecx, dword ptr [rbp+arg_8]; this
0x1800b9737  test    ecx, ecx
0x1800b9739  jns     short loc_1800B9741
0x1800b973b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b9741  test    ebx, ebx
0x1800b9743  jns     short loc_1800B974D
0x1800b9745  mov     ecx, ebx; this
0x1800b9747  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b974d  mov     rcx, [rbp+var_28]
0x1800b9751  mov     rax, [rcx]
0x1800b9754  mov     r8d, [rsi+8]
0x1800b9758  sub     r8d, [rsi]
0x1800b975b  mov     rdx, [rsi]
0x1800b975e  mov     rax, [rax+20h]
0x1800b9762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9767  test    eax, eax
0x1800b9769  jns     short loc_1800B9773
0x1800b976b  mov     ecx, eax; this
0x1800b976d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b9773  mov     dword ptr [rbp+arg_8], 0
0x1800b977a  mov     rcx, [r14]
0x1800b977d  mov     rax, [rcx]
0x1800b9780  mov     [rbp+var_18], 0
0x1800b9788  lea     rdx, [rbp+arg_8]
0x1800b978c  mov     [rbp+var_10], rdx
0x1800b9790  lea     rdx, [rbp+var_38]
0x1800b9794  mov     [rbp+var_8], rdx
0x1800b9798  lea     rdx, [rbp+var_18]
0x1800b979c  mov     rax, [rax+78h]
0x1800b97a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b97a5  mov     ebx, eax
0x1800b97a7  lea     rcx, [rbp+var_18]
0x1800b97ab  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b97b0  mov     ecx, dword ptr [rbp+arg_8]; this
0x1800b97b3  test    ecx, ecx
0x1800b97b5  jns     short loc_1800B97BD
0x1800b97b7  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b97bd  test    ebx, ebx
0x1800b97bf  jns     short loc_1800B97C9
0x1800b97c1  mov     ecx, ebx; this
0x1800b97c3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b97c9  mov     rcx, [rbp+var_38]
0x1800b97cd  mov     rax, [rcx]
0x1800b97d0  mov     edx, 1
0x1800b97d5  mov     rax, [rax+28h]
0x1800b97d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b97de  test    eax, eax
0x1800b97e0  jns     short loc_1800B97EA
0x1800b97e2  mov     ecx, eax; this
0x1800b97e4  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b97ea  mov     ecx, 68h ; 'h'; Size
0x1800b97ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b97f4  mov     [rbp+arg_8], rax
0x1800b97f8  lea     r8, [rbp+var_38]
0x1800b97fc  lea     rdx, [rbp+var_28]
0x1800b9800  mov     rcx, rax
0x1800b9803  call    ??0ColorContext@xpsrdr@@QEAA@AEBV?$shared_ptr@UIWICColorContext@@@std@@0@Z; xpsrdr::ColorContext::ColorContext(std::shared_ptr<IWICColorContext> const &,std::shared_ptr<IWICColorContext> const &)
0x1800b9808  nop
0x1800b9809  mov     rdx, rax
0x1800b980c  mov     rcx, rdi
0x1800b980f  call    ??$?0UColorContext@xpsrdr@@$0A@@?$shared_ptr@UColorContext@xpsrdr@@@std@@QEAA@PEAUColorContext@xpsrdr@@@Z; std::shared_ptr<xpsrdr::ColorContext>::shared_ptr<xpsrdr::ColorContext>(xpsrdr::ColorContext *)
0x1800b9814  nop
0x1800b9815  mov     rcx, [rbp+var_38+8]; this
0x1800b9819  test    rcx, rcx
0x1800b981c  jz      short loc_1800B9824
0x1800b981e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b9823  nop
0x1800b9824  mov     rcx, [rbp+var_28+8]; this
0x1800b9828  test    rcx, rcx
0x1800b982b  jz      short loc_1800B9832
0x1800b982d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b9832  mov     rax, rdi
0x1800b9835  lea     r11, [rsp+60h+var_s0]
0x1800b983a  mov     rbx, [r11+20h]
0x1800b983e  mov     rsi, [r11+30h]
0x1800b9842  mov     rsp, r11
0x1800b9845  pop     r14
0x1800b9847  pop     rdi
0x1800b9848  pop     rbp
0x1800b9849  retn
```
