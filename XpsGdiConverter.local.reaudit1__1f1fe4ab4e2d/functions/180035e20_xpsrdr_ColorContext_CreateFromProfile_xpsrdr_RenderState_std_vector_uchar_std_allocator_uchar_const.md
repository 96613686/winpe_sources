# xpsrdr::ColorContext::CreateFromProfile(xpsrdr::RenderState &,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180035e20`
- end: `0x180035f9b`
- name: `?CreateFromProfile@ColorContext@xpsrdr@@SA?AV?$shared_ptr@UColorContext@xpsrdr@@@std@@AEAURenderState@2@AEBV?$vector@EV?$allocator@E@std@@@4@@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180035fa4`

## callees

- `0x180008854`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x180034f7c`
- `0x1800350fc`
- `0x180035e20`
- `0x180037278`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall xpsrdr::ColorContext::CreateFromProfile(__int64 a1, __int64 **a2, __int64 a3)
{
  __int64 **v6; // rdx
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // ebx
  int v10; // edx
  const char *v11; // r8
  int v12; // r9d
  int v13; // eax
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // ebx
  int v20; // edx
  const char *v21; // r8
  int v22; // r9d
  int v23; // eax
  int v24; // edx
  const char *v25; // r8
  int v26; // r9d
  __int64 v27; // rax
  _QWORD v29[2]; // [rsp+28h] [rbp-38h] BYREF
  _QWORD v30[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v31; // [rsp+48h] [rbp-18h] BYREF
  xpsrdr **v32; // [rsp+50h] [rbp-10h]
  _QWORD *v33; // [rsp+58h] [rbp-8h]
  xpsrdr *v34; // [rsp+88h] [rbp+28h] BYREF

  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v30);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v29);
  LODWORD(v34) = 0;
  v7 = *v6;
  v8 = **v6;
  v31 = 0;
  v32 = &v34;
  v33 = v30;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v8 + 120))(v7, &v31);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v31);
  if ( (int)v34 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v34, v10, v11, v12);
  if ( v9 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v9, v10, v11, v12);
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v30[0] + 32LL))(
          v30[0],
          *(_QWORD *)a3,
          (unsigned int)(*(_DWORD *)(a3 + 8) - *(_DWORD *)a3));
  if ( v13 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v13, v14, v15, v16);
  LODWORD(v34) = 0;
  v17 = *a2;
  v18 = **a2;
  v31 = 0;
  v32 = &v34;
  v33 = v29;
  v19 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v18 + 120))(v17, &v31);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v31);
  if ( (int)v34 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v34, v20, v21, v22);
  if ( v19 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v19, v20, v21, v22);
  v23 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v29[0] + 40LL))(v29[0], 1);
  if ( v23 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v23, v24, v25, v26);
  v34 = (xpsrdr *)operator new(0x68u);
  v27 = xpsrdr::ColorContext::ColorContext(v34, v30, v29);
  std::shared_ptr<xpsrdr::ColorContext>::shared_ptr<xpsrdr::ColorContext>(a1, v27);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v29);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v30);
  return a1;
}

```

## disassembly

```asm
0x180035e20  mov     [rsp-18h+arg_0], rbx
0x180035e25  mov     [rsp-18h+arg_10], rsi
0x180035e2a  push    rbp
0x180035e2b  push    rdi
0x180035e2c  push    r14
0x180035e2e  mov     rbp, rsp
0x180035e31  sub     rsp, 60h
0x180035e35  mov     rdi, r8
0x180035e38  mov     r14, rdx
0x180035e3b  mov     rsi, rcx
0x180035e3e  lea     rcx, [rbp+var_28]
0x180035e42  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180035e47  nop
0x180035e48  lea     rcx, [rbp+var_38]
0x180035e4c  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180035e51  nop
0x180035e52  mov     dword ptr [rbp+arg_8], 0
0x180035e59  mov     rcx, [rdx]
0x180035e5c  mov     rax, [rcx]
0x180035e5f  mov     [rbp+var_18], 0
0x180035e67  lea     rdx, [rbp+arg_8]
0x180035e6b  mov     [rbp+var_10], rdx
0x180035e6f  lea     rdx, [rbp+var_28]
0x180035e73  mov     [rbp+var_8], rdx
0x180035e77  lea     rdx, [rbp+var_18]
0x180035e7b  mov     rax, [rax+78h]
0x180035e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e84  mov     ebx, eax
0x180035e86  lea     rcx, [rbp+var_18]
0x180035e8a  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180035e8f  mov     ecx, dword ptr [rbp+arg_8]; this
0x180035e92  test    ecx, ecx
0x180035e94  jns     short loc_180035E9C
0x180035e96  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180035e9c  test    ebx, ebx
0x180035e9e  jns     short loc_180035EA8
0x180035ea0  mov     ecx, ebx; this
0x180035ea2  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180035ea8  mov     rcx, [rbp+var_28]
0x180035eac  mov     rax, [rcx]
0x180035eaf  mov     r8d, [rdi+8]
0x180035eb3  sub     r8d, [rdi]
0x180035eb6  mov     rdx, [rdi]
0x180035eb9  mov     rax, [rax+20h]
0x180035ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ec2  test    eax, eax
0x180035ec4  jns     short loc_180035ECE
0x180035ec6  mov     ecx, eax; this
0x180035ec8  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180035ece  mov     dword ptr [rbp+arg_8], 0
0x180035ed5  mov     rcx, [r14]
0x180035ed8  mov     rax, [rcx]
0x180035edb  mov     [rbp+var_18], 0
0x180035ee3  lea     rdx, [rbp+arg_8]
0x180035ee7  mov     [rbp+var_10], rdx
0x180035eeb  lea     rdx, [rbp+var_38]
0x180035eef  mov     [rbp+var_8], rdx
0x180035ef3  lea     rdx, [rbp+var_18]
0x180035ef7  mov     rax, [rax+78h]
0x180035efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f00  mov     ebx, eax
0x180035f02  lea     rcx, [rbp+var_18]
0x180035f06  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180035f0b  mov     ecx, dword ptr [rbp+arg_8]; this
0x180035f0e  test    ecx, ecx
0x180035f10  jns     short loc_180035F18
0x180035f12  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180035f18  test    ebx, ebx
0x180035f1a  jns     short loc_180035F24
0x180035f1c  mov     ecx, ebx; this
0x180035f1e  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180035f24  mov     rcx, [rbp+var_38]
0x180035f28  mov     rax, [rcx]
0x180035f2b  mov     edx, 1
0x180035f30  mov     rax, [rax+28h]
0x180035f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f39  test    eax, eax
0x180035f3b  jns     short loc_180035F45
0x180035f3d  mov     ecx, eax; this
0x180035f3f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180035f45  mov     ecx, 68h ; 'h'; Size
0x180035f4a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035f4f  mov     [rbp+arg_8], rax
0x180035f53  lea     r8, [rbp+var_38]
0x180035f57  lea     rdx, [rbp+var_28]
0x180035f5b  mov     rcx, rax
0x180035f5e  call    ??0ColorContext@xpsrdr@@QEAA@AEBV?$shared_ptr@UIWICColorContext@@@std@@0@Z; xpsrdr::ColorContext::ColorContext(std::shared_ptr<IWICColorContext> const &,std::shared_ptr<IWICColorContext> const &)
0x180035f63  nop
0x180035f64  mov     rdx, rax
0x180035f67  mov     rcx, rsi
0x180035f6a  call    ??$?0UColorContext@xpsrdr@@$0A@@?$shared_ptr@UColorContext@xpsrdr@@@std@@QEAA@PEAUColorContext@xpsrdr@@@Z; std::shared_ptr<xpsrdr::ColorContext>::shared_ptr<xpsrdr::ColorContext>(xpsrdr::ColorContext *)
0x180035f6f  nop
0x180035f70  lea     rcx, [rbp+var_38]
0x180035f74  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180035f79  nop
0x180035f7a  lea     rcx, [rbp+var_28]
0x180035f7e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180035f83  mov     rax, rsi
0x180035f86  lea     r11, [rsp+60h+var_s0]
0x180035f8b  mov     rbx, [r11+20h]
0x180035f8f  mov     rsi, [r11+30h]
0x180035f93  mov     rsp, r11
0x180035f96  pop     r14
0x180035f98  pop     rdi
0x180035f99  pop     rbp
0x180035f9a  retn
```
