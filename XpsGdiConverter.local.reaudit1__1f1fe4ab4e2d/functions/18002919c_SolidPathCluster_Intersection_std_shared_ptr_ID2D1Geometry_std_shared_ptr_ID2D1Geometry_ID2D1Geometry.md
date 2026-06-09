# SolidPathCluster::Intersection(std::shared_ptr<ID2D1Geometry>,std::shared_ptr<ID2D1Geometry>,ID2D1Geometry * *)

- ea: `0x18002919c`
- end: `0x18002932e`
- name: `?Intersection@SolidPathCluster@@AEAAJV?$shared_ptr@UID2D1Geometry@@@std@@0PEAPEAUID2D1Geometry@@@Z`
- size: `402`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180028810`
- `0x18002990c`

## callees

- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x18002919c`
- `0x180037278`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SolidPathCluster::Intersection(__int64 a1, _QWORD *a2, _QWORD *a3, _QWORD *a4)
{
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // ebx
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // ebx
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d
  __int64 v16; // rax
  int v17; // ebx
  int v18; // edx
  const char *v19; // r8
  int v20; // r9d
  __int64 v21; // rcx
  _QWORD v23[2]; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v25; // [rsp+60h] [rbp-20h] BYREF
  xpsrdr **v26; // [rsp+68h] [rbp-18h]
  _QWORD *v27; // [rsp+70h] [rbp-10h]
  xpsrdr *v28; // [rsp+C8h] [rbp+48h] BYREF

  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v24);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v23);
  if ( v8 )
  {
    LODWORD(v28) = 0;
    v10 = *(__int64 **)(*(_QWORD *)v7 + 16LL);
    v11 = *v10;
    v25 = 0;
    v26 = &v28;
    v27 = v23;
    v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v11 + 80))(v10, &v25);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v25);
    if ( (int)v28 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v28, v13, v14, v15);
    if ( v12 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v12, v13, v14, v15);
    LODWORD(v28) = 0;
    v16 = *(_QWORD *)v23[0];
    v25 = 0;
    v26 = &v28;
    v27 = v24;
    v17 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v16 + 136))(v23[0], &v25);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v25);
    if ( (int)v28 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v28, v18, v19, v20);
    if ( v17 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v17, v18, v19, v20);
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)*a2 + 88LL))(*a2, *a3, 1);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v24[0] + 72LL))(v24[0]);
      if ( v9 >= 0 )
      {
        v21 = v23[0];
        *a4 = v23[0];
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
  }
  else
  {
    v9 = -2147024809;
  }
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v23);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v24);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(a2);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(a3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002919c  mov     [rsp-28h+arg_10], r8
0x1800291a1  mov     [rsp-28h+arg_8], rdx
0x1800291a6  push    rbp
0x1800291a7  push    rbx
0x1800291a8  push    rsi
0x1800291a9  push    rdi
0x1800291aa  push    r14
0x1800291ac  mov     rbp, rsp
0x1800291af  sub     rsp, 80h
0x1800291b6  mov     r14, r9
0x1800291b9  mov     rdi, r8
0x1800291bc  mov     rsi, rdx
0x1800291bf  mov     rdx, rcx
0x1800291c2  lea     rcx, [rbp+var_30]
0x1800291c6  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800291cb  nop
0x1800291cc  lea     rcx, [rbp+var_40]
0x1800291d0  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800291d5  nop
0x1800291d6  test    r9, r9
0x1800291d9  jnz     short loc_1800291E5
0x1800291db  mov     ebx, 80070057h
0x1800291e0  jmp     loc_1800292F9
0x1800291e5  mov     dword ptr [rbp+arg_18], 0
0x1800291ec  mov     rax, [rdx]
0x1800291ef  mov     rcx, [rax+10h]
0x1800291f3  mov     rax, [rcx]
0x1800291f6  mov     [rbp+var_20], 0
0x1800291fe  lea     rdx, [rbp+arg_18]
0x180029202  mov     [rbp+var_18], rdx
0x180029206  lea     rdx, [rbp+var_40]
0x18002920a  mov     [rbp+var_10], rdx
0x18002920e  lea     rdx, [rbp+var_20]
0x180029212  mov     rax, [rax+50h]
0x180029216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002921b  mov     ebx, eax
0x18002921d  lea     rcx, [rbp+var_20]
0x180029221  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180029226  mov     ecx, dword ptr [rbp+arg_18]; this
0x180029229  test    ecx, ecx
0x18002922b  jns     short loc_180029233
0x18002922d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180029233  test    ebx, ebx
0x180029235  jns     short loc_18002923F
0x180029237  mov     ecx, ebx; this
0x180029239  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002923f  mov     dword ptr [rbp+arg_18], 0
0x180029246  mov     rcx, [rbp+var_40]
0x18002924a  mov     rax, [rcx]
0x18002924d  mov     [rbp+var_20], 0
0x180029255  lea     rdx, [rbp+arg_18]
0x180029259  mov     [rbp+var_18], rdx
0x18002925d  lea     rdx, [rbp+var_30]
0x180029261  mov     [rbp+var_10], rdx
0x180029265  lea     rdx, [rbp+var_20]
0x180029269  mov     rax, [rax+88h]
0x180029270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029275  mov     ebx, eax
0x180029277  lea     rcx, [rbp+var_20]
0x18002927b  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180029280  mov     ecx, dword ptr [rbp+arg_18]; this
0x180029283  test    ecx, ecx
0x180029285  jns     short loc_18002928D
0x180029287  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002928d  test    ebx, ebx
0x18002928f  jns     short loc_180029299
0x180029291  mov     ecx, ebx; this
0x180029293  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180029299  mov     rcx, [rsi]
0x18002929c  mov     rdx, [rbp+var_30]
0x1800292a0  mov     rax, [rcx]
0x1800292a3  mov     [rsp+80h+var_58], rdx
0x1800292a8  movss   xmm0, cs:__real@3d4ccccd
0x1800292b0  movss   [rsp+80h+var_60], xmm0
0x1800292b6  xor     r9d, r9d
0x1800292b9  lea     r8d, [r9+1]
0x1800292bd  mov     rdx, [rdi]
0x1800292c0  mov     rax, [rax+58h]
0x1800292c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292c9  mov     ebx, eax
0x1800292cb  test    eax, eax
0x1800292cd  js      short loc_1800292F9
0x1800292cf  mov     rcx, [rbp+var_30]
0x1800292d3  mov     rax, [rcx]
0x1800292d6  mov     rax, [rax+48h]
0x1800292da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292df  mov     ebx, eax
0x1800292e1  test    eax, eax
0x1800292e3  js      short loc_1800292F9
0x1800292e5  mov     rcx, [rbp+var_40]
0x1800292e9  mov     [r14], rcx
0x1800292ec  mov     rax, [rcx]
0x1800292ef  mov     rax, [rax+8]
0x1800292f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292f8  nop
0x1800292f9  lea     rcx, [rbp+var_40]
0x1800292fd  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180029302  nop
0x180029303  lea     rcx, [rbp+var_30]
0x180029307  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002930c  nop
0x18002930d  mov     rcx, rsi
0x180029310  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180029315  nop
0x180029316  mov     rcx, rdi
0x180029319  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002931e  mov     eax, ebx
0x180029320  add     rsp, 80h
0x180029327  pop     r14
0x180029329  pop     rdi
0x18002932a  pop     rsi
0x18002932b  pop     rbx
0x18002932c  pop     rbp
0x18002932d  retn
```
