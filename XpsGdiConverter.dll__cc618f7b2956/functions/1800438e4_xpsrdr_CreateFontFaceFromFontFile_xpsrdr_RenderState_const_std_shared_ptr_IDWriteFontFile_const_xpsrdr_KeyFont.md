# xpsrdr::CreateFontFaceFromFontFile(xpsrdr::RenderState const &,std::shared_ptr<IDWriteFontFile> const &,xpsrdr::KeyFontFace const &)

- ea: `0x1800438e4`
- end: `0x180043a41`
- name: `?CreateFontFaceFromFontFile@xpsrdr@@YA?AV?$shared_ptr@UIDWriteFontFace@@@std@@AEBURenderState@1@AEBV?$shared_ptr@UIDWriteFontFile@@@3@AEBUKeyFontFace@1@@Z`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800432dc`

## callees

- `0x18000e15c`
- `0x18000e4c4`
- `0x180037278`
- `0x1800372e4`
- `0x1800438e4`
- `0x180043a48`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall xpsrdr::CreateFontFaceFromFontFile(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  int v8; // eax
  const char *v9; // rdx
  xpsrdr *v10; // rcx
  const char *v11; // r8
  int v12; // r9d
  int v13; // r8d
  int v14; // eax
  __int64 v15; // r8
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64, _QWORD *, _DWORD, int, _QWORD *); // r10
  __int64 v17; // r11
  int v18; // ebx
  int v19; // edx
  const char *v20; // r8
  int v21; // r9d
  int v23; // [rsp+40h] [rbp-40h] BYREF
  int v24; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned int v25; // [rsp+48h] [rbp-38h] BYREF
  int v26; // [rsp+4Ch] [rbp-34h] BYREF
  int v27; // [rsp+50h] [rbp-30h]
  _QWORD v28[2]; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v29[3]; // [rsp+68h] [rbp-18h] BYREF
  int v30; // [rsp+B0h] [rbp+30h] BYREF

  v27 = 0;
  v30 = 0;
  v24 = 0;
  v25 = 0;
  v23 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, int *, int *, unsigned int *, int *))(*(_QWORD *)*a3 + 40LL))(
         *a3,
         &v30,
         &v24,
         &v25,
         &v23);
  if ( v8 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v8, (int)v9, v11, v12);
  if ( !v30 )
    xpsrdr::ThrowLogicException(v10, v9, (int)v11);
  if ( v23 <= *(__int16 *)(a4 + 36) )
    xpsrdr::ThrowLogicException(v10, v9, (int)v11);
  if ( v24 == 1 )
    ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 104LL);
  v28[0] = *a3;
  v28[1] = 0;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(a1);
  v27 = v13;
  v26 = 0;
  v29[0] = 0;
  v29[1] = &v26;
  v29[2] = a1;
  v14 = xpsrdr::DWriteFromXpsSimulations(*(unsigned int *)(a4 + 32));
  v18 = v16(v17, v25, v15, v28, *(__int16 *)(a4 + 36), v14, v29);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v29);
  if ( v26 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v26, v19, v20, v21);
  if ( v18 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v18, v19, v20, v21);
  return a1;
}

```

## disassembly

```asm
0x1800438e4  mov     r11, rsp
0x1800438e7  mov     [r11+10h], rbx
0x1800438eb  mov     [r11+20h], rsi
0x1800438ef  mov     [r11+8], rcx
0x1800438f3  push    rbp
0x1800438f4  push    rdi
0x1800438f5  push    r14
0x1800438f7  mov     rbp, rsp
0x1800438fa  sub     rsp, 80h
0x180043901  mov     rbx, r9
0x180043904  mov     r14, r8
0x180043907  mov     rsi, rdx
0x18004390a  mov     rdi, rcx
0x18004390d  mov     dword ptr [rbp+var_34+4], 0
0x180043914  mov     [rbp+arg_10], 0
0x18004391b  mov     [rbp+var_3C], 0
0x180043922  mov     [rbp+var_38], 0
0x180043929  mov     [rbp+var_40], 0
0x180043930  mov     rcx, [r8]
0x180043933  mov     rax, [rcx]
0x180043936  lea     rdx, [rbp+var_40]
0x18004393a  mov     [r11-78h], rdx
0x18004393e  lea     r9, [rbp+var_38]
0x180043942  lea     r8, [rbp+var_3C]
0x180043946  lea     rdx, [rbp+arg_10]
0x18004394a  mov     rax, [rax+28h]
0x18004394e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043953  test    eax, eax
0x180043955  jns     short loc_18004395F
0x180043957  mov     ecx, eax; this
0x180043959  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18004395f  cmp     [rbp+arg_10], 0
0x180043963  jnz     short loc_18004396B
0x180043965  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18004396b  movsx   eax, word ptr [rbx+24h]
0x18004396f  cmp     [rbp+var_40], eax
0x180043972  jg      short loc_18004397A
0x180043974  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18004397a  mov     r8d, 1
0x180043980  cmp     [rbp+var_3C], r8d
0x180043984  jnz     short loc_180043991
0x180043986  mov     rax, [rsi+220h]
0x18004398d  add     [rax+68h], r8d
0x180043991  mov     rax, [r14]
0x180043994  mov     [rbp+var_28], rax
0x180043998  mov     [rbp+var_20], 0
0x1800439a0  mov     rcx, rdi
0x1800439a3  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800439a8  mov     dword ptr [rbp+var_34+4], r8d
0x1800439ac  mov     dword ptr [rbp+var_34], 0
0x1800439b3  mov     r11, [rsi+20h]
0x1800439b7  mov     rax, [r11]
0x1800439ba  mov     r10, [rax+48h]
0x1800439be  mov     [rbp+var_18], 0
0x1800439c6  lea     rax, [rbp+var_34]
0x1800439ca  mov     [rbp+var_10], rax
0x1800439ce  mov     [rbp+var_8], rdi
0x1800439d2  mov     ecx, [rbx+20h]
0x1800439d5  call    ?DWriteFromXpsSimulations@xpsrdr@@YA?AW4DWRITE_FONT_SIMULATIONS@@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0004@@@Z; xpsrdr::DWriteFromXpsSimulations(__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0004)
0x1800439da  movsx   edx, word ptr [rbx+24h]
0x1800439de  lea     rcx, [rbp+var_18]
0x1800439e2  mov     [rsp+80h+var_50], rcx
0x1800439e7  mov     [rsp+80h+var_58], eax
0x1800439eb  mov     [rsp+80h+var_60], edx
0x1800439ef  lea     r9, [rbp+var_28]
0x1800439f3  mov     edx, [rbp+var_38]
0x1800439f6  mov     rcx, r11
0x1800439f9  mov     rax, r10
0x1800439fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a01  mov     ebx, eax
0x180043a03  lea     rcx, [rbp+var_18]
0x180043a07  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180043a0c  mov     ecx, dword ptr [rbp+var_34]; this
0x180043a0f  test    ecx, ecx
0x180043a11  jns     short loc_180043A19
0x180043a13  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180043a19  test    ebx, ebx
0x180043a1b  jns     short loc_180043A25
0x180043a1d  mov     ecx, ebx; this
0x180043a1f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180043a25  mov     rax, rdi
0x180043a28  lea     r11, [rsp+80h+var_s0]
0x180043a30  mov     rbx, [r11+28h]
0x180043a34  mov     rsi, [r11+38h]
0x180043a38  mov     rsp, r11
0x180043a3b  pop     r14
0x180043a3d  pop     rdi
0x180043a3e  pop     rbp
0x180043a3f  retn
```
