# xpsrdr::VisualsRasterizer::CopyToOutputBuffer(D2D_RECT_U &,std::shared_ptr<IWICBitmap> &)

- ea: `0x1800ae074`
- end: `0x1800ae26f`
- name: `?CopyToOutputBuffer@VisualsRasterizer@xpsrdr@@AEAAJAEAUD2D_RECT_U@@AEAV?$shared_ptr@UIWICBitmap@@@std@@@Z`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800aef08`

## callees

- `0x180003180`
- `0x1800a02eb`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a9cfc`
- `0x1800aa83c`
- `0x1800ae074`
- `0x1800b20e8`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall xpsrdr::VisualsRasterizer::CopyToOutputBuffer(_QWORD *a1, int *a2, __int64 **a3)
{
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // ebx
  int v7; // edx
  const char *v8; // r8
  int v9; // r9d
  int v10; // eax
  int v11; // edx
  const char *v12; // r8
  int v13; // r9d
  int v14; // eax
  int v15; // edx
  const char *v16; // r8
  int v17; // r9d
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  struct _GUID *v21; // rdx
  int v22; // r14d
  char *v23; // rbx
  char *v24; // rdi
  unsigned __int64 i; // rsi
  __int16 BytesPerPixel; // ax
  int v28; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-65h] BYREF
  int v30; // [rsp+48h] [rbp-61h] BYREF
  void *v31; // [rsp+50h] [rbp-59h] BYREF
  std::_Ref_count_base *v32[2]; // [rsp+58h] [rbp-51h] BYREF
  __int128 v33; // [rsp+70h] [rbp-39h] BYREF
  std::_Ref_count_base **v34; // [rsp+80h] [rbp-29h]
  __int128 v35; // [rsp+90h] [rbp-19h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-9h]
  void *Src; // [rsp+A8h] [rbp-1h] BYREF
  unsigned int v38; // [rsp+B0h] [rbp+7h]
  char v39; // [rsp+B8h] [rbp+Fh]
  int v40; // [rsp+C0h] [rbp+17h] BYREF
  int v41; // [rsp+C4h] [rbp+1Bh]
  int v42; // [rsp+C8h] [rbp+1Fh]
  unsigned int v43; // [rsp+CCh] [rbp+23h]

  v40 = *a2;
  v41 = a2[1];
  v42 = a2[2] - v40;
  v43 = a2[3] - v41;
  *(_OWORD *)v32 = 0;
  v28 = 0;
  v4 = *a3;
  v5 = **a3;
  *(_QWORD *)&v33 = 0;
  *((_QWORD *)&v33 + 1) = &v28;
  v34 = v32;
  v6 = (*(__int64 (__fastcall **)(__int64 *, int *, __int64, __int128 *))(v5 + 64))(v4, &v40, 2, &v33);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v33);
  if ( v28 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v28, v7, v8, v9);
  if ( v6 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v6, v7, v8, v9);
  v29 = 0;
  v10 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, unsigned int *))(*(_QWORD *)v32[0] + 32LL))(v32[0], &v29);
  if ( v10 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v10, v11, v12, v13);
  v31 = 0;
  v30 = 0;
  v14 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, int *, void **))(*(_QWORD *)v32[0] + 40LL))(
          v32[0],
          &v30,
          &v31);
  if ( v14 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v14, v15, v16, v17);
  v18 = a1[11];
  v19 = *a1;
  v35 = 0;
  v20 = *(_QWORD *)(v19 + 72);
  if ( v20 )
    _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
  v35 = *(_OWORD *)(v19 + 64);
  v36 = v18;
  v39 = 1;
  v22 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _DWORD, void **))(*(_QWORD *)v35 + 112LL))(
          v35,
          v18,
          0,
          1,
          0,
          &Src);
  if ( v22 >= 0 )
  {
    v23 = (char *)Src;
    v24 = (char *)v31;
    for ( i = 0; i < v43; ++i )
    {
      v33 = *(_OWORD *)(*a1 + 100LL);
      BytesPerPixel = xpsrdr::GetBytesPerPixel((xpsrdr *)&v33, v21);
      memcpy_0(v24, v23, v42 * BytesPerPixel);
      v23 += v38;
      v24 += v29;
    }
  }
  xpsrdr::D3D11TextureMapUnmapHelper::~D3D11TextureMapUnmapHelper((xpsrdr::D3D11TextureMapUnmapHelper *)&v35);
  if ( v32[1] )
    std::_Ref_count_base::_Decref(v32[1]);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1800ae074  mov     [rsp-8+arg_18], rbx
0x1800ae079  push    rbp
0x1800ae07a  push    rsi
0x1800ae07b  push    rdi
0x1800ae07c  push    r14
0x1800ae07e  push    r15
0x1800ae080  lea     rbp, [rsp-37h]
0x1800ae085  sub     rsp, 0E0h
0x1800ae08c  mov     rax, cs:__security_cookie
0x1800ae093  xor     rax, rsp
0x1800ae096  mov     [rbp+57h+var_30], rax
0x1800ae09a  mov     r15, rcx
0x1800ae09d  mov     r9d, [rdx]
0x1800ae0a0  mov     [rbp+57h+var_40], r9d
0x1800ae0a4  mov     r10d, [rdx+4]
0x1800ae0a8  mov     [rbp+57h+var_3C], r10d
0x1800ae0ac  mov     eax, [rdx+8]
0x1800ae0af  sub     eax, r9d
0x1800ae0b2  mov     [rbp+57h+var_38], eax
0x1800ae0b5  mov     eax, [rdx+0Ch]
0x1800ae0b8  sub     eax, r10d
0x1800ae0bb  mov     [rbp+57h+var_34], eax
0x1800ae0be  xorps   xmm0, xmm0
0x1800ae0c1  movdqu  xmmword ptr [rbp+57h+var_A8], xmm0
0x1800ae0c6  mov     dword ptr [rbp+57h+var_C0], 0
0x1800ae0cd  mov     rcx, [r8]
0x1800ae0d0  mov     rax, [rcx]
0x1800ae0d3  mov     qword ptr [rbp+57h+var_90], 0
0x1800ae0db  lea     rdx, [rbp+57h+var_C0]
0x1800ae0df  mov     qword ptr [rbp+57h+var_90+8], rdx
0x1800ae0e3  lea     rdx, [rbp+57h+var_A8]
0x1800ae0e7  mov     [rbp+57h+var_80], rdx
0x1800ae0eb  lea     r9, [rbp+57h+var_90]
0x1800ae0ef  mov     r8d, 2
0x1800ae0f5  lea     rdx, [rbp+57h+var_40]
0x1800ae0f9  mov     rax, [rax+40h]
0x1800ae0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae102  mov     ebx, eax
0x1800ae104  lea     rcx, [rbp+57h+var_90]
0x1800ae108  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800ae10d  mov     ecx, dword ptr [rbp+57h+var_C0]; this
0x1800ae110  test    ecx, ecx
0x1800ae112  jns     short loc_1800AE11A
0x1800ae114  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae11a  test    ebx, ebx
0x1800ae11c  jns     short loc_1800AE126
0x1800ae11e  mov     ecx, ebx; this
0x1800ae120  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae126  mov     dword ptr [rbp+57h+var_C0+4], 0
0x1800ae12d  mov     rcx, [rbp+57h+var_A8]
0x1800ae131  mov     rax, [rcx]
0x1800ae134  lea     rdx, [rbp+57h+var_C0+4]
0x1800ae138  mov     rax, [rax+20h]
0x1800ae13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae141  test    eax, eax
0x1800ae143  jns     short loc_1800AE14D
0x1800ae145  mov     ecx, eax; this
0x1800ae147  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae14d  mov     [rbp+57h+var_B0], 0
0x1800ae155  mov     [rbp+57h+var_B8], 0
0x1800ae15c  mov     rcx, [rbp+57h+var_A8]
0x1800ae160  mov     rax, [rcx]
0x1800ae163  lea     r8, [rbp+57h+var_B0]
0x1800ae167  lea     rdx, [rbp+57h+var_B8]
0x1800ae16b  mov     rax, [rax+28h]
0x1800ae16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae174  test    eax, eax
0x1800ae176  jns     short loc_1800AE180
0x1800ae178  mov     ecx, eax; this
0x1800ae17a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae180  mov     rdx, [r15+58h]
0x1800ae184  mov     r8, [r15]
0x1800ae187  xorps   xmm0, xmm0
0x1800ae18a  movdqu  [rbp+57h+var_70], xmm0
0x1800ae18f  mov     rax, [r8+48h]
0x1800ae193  test    rax, rax
0x1800ae196  jz      short loc_1800AE19C
0x1800ae198  lock inc dword ptr [rax+8]
0x1800ae19c  mov     rcx, [r8+40h]
0x1800ae1a0  mov     qword ptr [rbp+57h+var_70], rcx
0x1800ae1a4  mov     rax, [r8+48h]
0x1800ae1a8  mov     qword ptr [rbp+57h+var_70+8], rax
0x1800ae1ac  mov     [rbp+57h+var_60], rdx
0x1800ae1b0  mov     [rbp+57h+var_48], 1
0x1800ae1b4  mov     rax, [rcx]
0x1800ae1b7  lea     r8, [rbp+57h+Src]
0x1800ae1bb  mov     [rsp+100h+var_D8], r8
0x1800ae1c0  mov     [rsp+100h+var_E0], 0
0x1800ae1c8  mov     r9d, 1
0x1800ae1ce  xor     r8d, r8d
0x1800ae1d1  mov     rax, [rax+70h]
0x1800ae1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae1da  mov     r14d, eax
0x1800ae1dd  test    eax, eax
0x1800ae1df  js      short loc_1800AE231
0x1800ae1e1  mov     rbx, [rbp+57h+Src]
0x1800ae1e5  mov     rdi, [rbp+57h+var_B0]
0x1800ae1e9  xor     esi, esi
0x1800ae1eb  cmp     [rbp+57h+var_34], esi
0x1800ae1ee  jbe     short loc_1800AE231
0x1800ae1f0  mov     rcx, [r15]
0x1800ae1f3  movups  xmm0, xmmword ptr [rcx+64h]
0x1800ae1f7  movdqu  [rbp+57h+var_90], xmm0
0x1800ae1fc  lea     rcx, [rbp+57h+var_90]; this
0x1800ae200  call    ?GetBytesPerPixel@xpsrdr@@YAFU_GUID@@@Z; xpsrdr::GetBytesPerPixel(_GUID)
0x1800ae205  movsx   ecx, ax
0x1800ae208  imul    ecx, [rbp+57h+var_38]
0x1800ae20c  movsxd  r8, ecx; Size
0x1800ae20f  mov     rdx, rbx; Src
0x1800ae212  mov     rcx, rdi; void *
0x1800ae215  call    memcpy_0
0x1800ae21a  mov     eax, [rbp+57h+var_50]
0x1800ae21d  add     rbx, rax
0x1800ae220  mov     eax, dword ptr [rbp+57h+var_C0+4]
0x1800ae223  add     rdi, rax
0x1800ae226  inc     rsi
0x1800ae229  mov     eax, [rbp+57h+var_34]
0x1800ae22c  cmp     rsi, rax
0x1800ae22f  jb      short loc_1800AE1F0
0x1800ae231  lea     rcx, [rbp+57h+var_70]; this
0x1800ae235  call    ??1D3D11TextureMapUnmapHelper@xpsrdr@@QEAA@XZ; xpsrdr::D3D11TextureMapUnmapHelper::~D3D11TextureMapUnmapHelper(void)
0x1800ae23a  nop
0x1800ae23b  mov     rcx, [rbp+57h+var_A8+8]; this
0x1800ae23f  test    rcx, rcx
0x1800ae242  jz      short loc_1800AE249
0x1800ae244  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae249  mov     eax, r14d
0x1800ae24c  mov     rcx, [rbp+57h+var_30]
0x1800ae250  xor     rcx, rsp; StackCookie
0x1800ae253  call    __security_check_cookie
0x1800ae258  mov     rbx, [rsp+100h+arg_18]
0x1800ae260  add     rsp, 0E0h
0x1800ae267  pop     r15
0x1800ae269  pop     r14
0x1800ae26b  pop     rdi
0x1800ae26c  pop     rsi
0x1800ae26d  pop     rbp
0x1800ae26e  retn
```
