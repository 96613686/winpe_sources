# xpsrdr::GetMatchingSystemFont(std::shared_ptr<IDWriteFontFamily> const &,std::shared_ptr<IDWriteFont> const &,std::shared_ptr<IDWriteFont> &)

- ea: `0x180043d74`
- end: `0x180043fd7`
- name: `?GetMatchingSystemFont@xpsrdr@@YA_NAEBV?$shared_ptr@UIDWriteFontFamily@@@std@@AEBV?$shared_ptr@UIDWriteFont@@@3@AEAV43@@Z`
- size: `611`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180043fe0`

## callees

- `0x180008830`
- `0x1800093a0`
- `0x18000da08`
- `0x18000e0d8`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x180012088`
- `0x180043a74`
- `0x180043d74`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall xpsrdr::GetMatchingSystemFont(__int64 *a1, __int64 **a2, __int64 a3)
{
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // r14
  __int64 (__fastcall *v9)(__int64, _QWORD, _QWORD, _QWORD, __int128 *); // rsi
  unsigned int v10; // edi
  unsigned int v11; // eax
  __int64 *v12; // rdi
  int v13; // ebx
  __int64 *v14; // rdi
  int v15; // ebx
  __int64 *v16; // rdi
  int v17; // ebx
  __int64 *v18; // rsi
  unsigned int (__fastcall *v19)(__int64 *); // rdi
  int v20; // ebx
  __int64 *v22[2]; // [rsp+30h] [rbp-49h] BYREF
  int v23; // [rsp+40h] [rbp-39h] BYREF
  __int128 v24; // [rsp+48h] [rbp-31h] BYREF
  __int64 **v25; // [rsp+58h] [rbp-21h]
  __int128 Buf2; // [rsp+60h] [rbp-19h] BYREF
  int v27; // [rsp+70h] [rbp-9h]
  __int128 Buf1; // [rsp+78h] [rbp-1h] BYREF
  int v29; // [rsp+88h] [rbp+Fh]

  v23 = 0;
  v24 = 0;
  v6 = std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v24);
  std::shared_ptr<XgcSolidPath>::swap(v6, v7);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v24);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v22);
  v8 = *a1;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int128 *))(*(_QWORD *)*a1 + 56LL);
  *(_QWORD *)&v24 = 0;
  *((_QWORD *)&v24 + 1) = &v23;
  v25 = v22;
  v10 = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 48))(*a2);
  LODWORD(a1) = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 40))(*a2);
  v11 = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 32))(*a2);
  LODWORD(a1) = v9(v8, v11, (unsigned int)a1, v10, &v24);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v24);
  if ( (int)a1 < 0 )
    goto LABEL_9;
  v12 = v22[0];
  v13 = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 32))(*a2);
  if ( v13 != (*(unsigned int (__fastcall **)(__int64 *))(*v12 + 32))(v12) )
    goto LABEL_9;
  v14 = v22[0];
  v15 = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 40))(*a2);
  if ( v15 != (*(unsigned int (__fastcall **)(__int64 *))(*v14 + 40))(v14) )
    goto LABEL_9;
  v16 = v22[0];
  v17 = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 48))(*a2);
  if ( v17 != (*(unsigned int (__fastcall **)(__int64 *))(*v16 + 48))(v16) )
    goto LABEL_9;
  v18 = v22[0];
  v19 = *(unsigned int (__fastcall **)(__int64 *))(*v22[0] + 80);
  v20 = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 80))(*a2);
  if ( v20 != v19(v18) )
    goto LABEL_9;
  Buf2 = 0;
  v27 = 0;
  (*(void (__fastcall **)(__int64 *, __int128 *))(**a2 + 88))(*a2, &Buf2);
  Buf1 = 0;
  v29 = 0;
  (*(void (__fastcall **)(__int64 *, __int128 *))(*v22[0] + 88))(v22[0], &Buf1);
  if ( !memcmp_0(&Buf1, &Buf2, 0x14u) && xpsrdr::DoesInformationsMatch(a2, v22) )
  {
    std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(&v24);
    std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(&v24, v22);
    std::shared_ptr<XgcSolidPath>::swap(&v24, a3);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v24);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v22);
    return 1;
  }
  else
  {
LABEL_9:
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v22);
    return 0;
  }
}

```

## disassembly

```asm
0x180043d74  push    rbp
0x180043d76  push    rbx
0x180043d77  push    rsi
0x180043d78  push    rdi
0x180043d79  push    r12
0x180043d7b  push    r14
0x180043d7d  push    r15
0x180043d7f  lea     rbp, [rsp-27h]
0x180043d84  sub     rsp, 0A0h
0x180043d8b  mov     rax, cs:__security_cookie
0x180043d92  xor     rax, rsp
0x180043d95  mov     [rbp+57h+var_40], rax
0x180043d99  mov     r12, r8
0x180043d9c  mov     r15, rdx
0x180043d9f  mov     rbx, rcx
0x180043da2  mov     [rbp+57h+var_90], 0
0x180043da9  xorps   xmm0, xmm0
0x180043dac  movups  [rbp+57h+var_88], xmm0
0x180043db0  lea     rcx, [rbp+57h+var_88]
0x180043db4  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180043db9  mov     rdx, r8
0x180043dbc  mov     rcx, rax
0x180043dbf  call    ?swap@?$shared_ptr@VXgcSolidPath@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<XgcSolidPath>::swap(std::shared_ptr<XgcSolidPath> &)
0x180043dc4  lea     rcx, [rbp+57h+var_88]
0x180043dc8  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180043dcd  lea     rcx, [rbp+57h+var_A0]
0x180043dd1  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180043dd6  nop
0x180043dd7  mov     r14, [rbx]
0x180043dda  mov     rax, [r14]
0x180043ddd  mov     rsi, [rax+38h]
0x180043de1  mov     qword ptr [rbp+57h+var_88], 0
0x180043de9  lea     rax, [rbp+57h+var_90]
0x180043ded  mov     qword ptr [rbp+57h+var_88+8], rax
0x180043df1  lea     rax, [rbp+57h+var_A0]
0x180043df5  mov     [rbp+57h+var_78], rax
0x180043df9  mov     rcx, [r15]
0x180043dfc  mov     rax, [rcx]
0x180043dff  mov     rax, [rax+30h]
0x180043e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e08  mov     edi, eax
0x180043e0a  mov     rcx, [r15]
0x180043e0d  mov     rdx, [rcx]
0x180043e10  mov     rax, [rdx+28h]
0x180043e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e19  mov     ebx, eax
0x180043e1b  mov     rcx, [r15]
0x180043e1e  mov     rdx, [rcx]
0x180043e21  mov     rax, [rdx+20h]
0x180043e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e2a  lea     rcx, [rbp+57h+var_88]
0x180043e2e  mov     [rsp+0D0h+var_B0], rcx
0x180043e33  mov     r9d, edi
0x180043e36  mov     r8d, ebx
0x180043e39  mov     edx, eax
0x180043e3b  mov     rcx, r14
0x180043e3e  mov     rax, rsi
0x180043e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e46  mov     ebx, eax
0x180043e48  lea     rcx, [rbp+57h+var_88]
0x180043e4c  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180043e51  shr     ebx, 1Fh
0x180043e54  test    bl, bl
0x180043e56  jnz     loc_180043FAE
0x180043e5c  mov     rcx, [r15]
0x180043e5f  mov     rdi, [rbp+57h+var_A0]
0x180043e63  mov     rax, [rcx]
0x180043e66  mov     rax, [rax+20h]
0x180043e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e6f  mov     ebx, eax
0x180043e71  mov     rdx, [rdi]
0x180043e74  mov     rcx, rdi
0x180043e77  mov     rax, [rdx+20h]
0x180043e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e80  cmp     ebx, eax
0x180043e82  jnz     loc_180043FAE
0x180043e88  mov     rcx, [r15]
0x180043e8b  mov     rdi, [rbp+57h+var_A0]
0x180043e8f  mov     rax, [rcx]
0x180043e92  mov     rax, [rax+28h]
0x180043e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e9b  mov     ebx, eax
0x180043e9d  mov     rdx, [rdi]
0x180043ea0  mov     rcx, rdi
0x180043ea3  mov     rax, [rdx+28h]
0x180043ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043eac  cmp     ebx, eax
0x180043eae  jnz     loc_180043FAE
0x180043eb4  mov     rcx, [r15]
0x180043eb7  mov     rdi, [rbp+57h+var_A0]
0x180043ebb  mov     rax, [rcx]
0x180043ebe  mov     rax, [rax+30h]
0x180043ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ec7  mov     ebx, eax
0x180043ec9  mov     rdx, [rdi]
0x180043ecc  mov     rcx, rdi
0x180043ecf  mov     rax, [rdx+30h]
0x180043ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ed8  cmp     ebx, eax
0x180043eda  jnz     loc_180043FAE
0x180043ee0  mov     rcx, [r15]
0x180043ee3  mov     rsi, [rbp+57h+var_A0]
0x180043ee7  mov     rax, [rsi]
0x180043eea  mov     rdi, [rax+50h]
0x180043eee  mov     rdx, [rcx]
0x180043ef1  mov     rax, [rdx+50h]
0x180043ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043efa  mov     ebx, eax
0x180043efc  mov     rcx, rsi
0x180043eff  mov     rax, rdi
0x180043f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f07  cmp     ebx, eax
0x180043f09  jnz     loc_180043FAE
0x180043f0f  xorps   xmm0, xmm0
0x180043f12  xor     eax, eax
0x180043f14  movups  [rbp+57h+Buf2], xmm0
0x180043f18  mov     [rbp+57h+var_60], eax
0x180043f1b  mov     rcx, [r15]
0x180043f1e  mov     rax, [rcx]
0x180043f21  lea     rdx, [rbp+57h+Buf2]
0x180043f25  mov     rax, [rax+58h]
0x180043f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f2e  xorps   xmm0, xmm0
0x180043f31  xor     eax, eax
0x180043f33  movups  [rbp+57h+Buf1], xmm0
0x180043f37  mov     [rbp+57h+var_48], eax
0x180043f3a  mov     rcx, [rbp+57h+var_A0]
0x180043f3e  mov     rax, [rcx]
0x180043f41  lea     rdx, [rbp+57h+Buf1]
0x180043f45  mov     rax, [rax+58h]
0x180043f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f4e  mov     r8d, 14h; Size
0x180043f54  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180043f58  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180043f5c  call    memcmp_0
0x180043f61  test    eax, eax
0x180043f63  jnz     short loc_180043FAE
0x180043f65  lea     rdx, [rbp+57h+var_A0]
0x180043f69  mov     rcx, r15
0x180043f6c  call    ?DoesInformationsMatch@xpsrdr@@YA_NAEBV?$shared_ptr@UIDWriteFont@@@std@@0@Z; xpsrdr::DoesInformationsMatch(std::shared_ptr<IDWriteFont> const &,std::shared_ptr<IDWriteFont> const &)
0x180043f71  test    al, al
0x180043f73  jz      short loc_180043FAE
0x180043f75  lea     rcx, [rbp+57h+var_88]
0x180043f79  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180043f7e  lea     rdx, [rbp+57h+var_A0]
0x180043f82  lea     rcx, [rbp+57h+var_88]
0x180043f86  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180043f8b  mov     rdx, r12
0x180043f8e  lea     rcx, [rbp+57h+var_88]
0x180043f92  call    ?swap@?$shared_ptr@VXgcSolidPath@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<XgcSolidPath>::swap(std::shared_ptr<XgcSolidPath> &)
0x180043f97  lea     rcx, [rbp+57h+var_88]
0x180043f9b  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180043fa0  nop
0x180043fa1  lea     rcx, [rbp+57h+var_A0]
0x180043fa5  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180043faa  mov     al, 1
0x180043fac  jmp     short loc_180043FB9
0x180043fae  lea     rcx, [rbp+57h+var_A0]
0x180043fb2  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180043fb7  xor     al, al
0x180043fb9  mov     rcx, [rbp+57h+var_40]
0x180043fbd  xor     rcx, rsp; StackCookie
0x180043fc0  call    __security_check_cookie
0x180043fc5  add     rsp, 0A0h
0x180043fcc  pop     r15
0x180043fce  pop     r14
0x180043fd0  pop     r12
0x180043fd2  pop     rdi
0x180043fd3  pop     rsi
0x180043fd4  pop     rbx
0x180043fd5  pop     rbp
0x180043fd6  retn
```
