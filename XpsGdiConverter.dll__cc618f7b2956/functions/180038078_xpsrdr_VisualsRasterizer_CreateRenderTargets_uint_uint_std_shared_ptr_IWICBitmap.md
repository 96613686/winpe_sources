# xpsrdr::VisualsRasterizer::CreateRenderTargets(uint,uint,std::shared_ptr<IWICBitmap>)

- ea: `0x180038078`
- end: `0x180038412`
- name: `?CreateRenderTargets@VisualsRasterizer@xpsrdr@@AEAAXIIV?$shared_ptr@UIWICBitmap@@@std@@@Z`
- size: `922`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180038e80`

## callees

- `0x180008830`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x180017a20`
- `0x18003365c`
- `0x180037278`
- `0x180038078`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
double __fastcall xpsrdr::VisualsRasterizer::CreateRenderTargets(_QWORD *a1, int a2, enum DXGI_FORMAT *a3, _QWORD *a4)
{
  int v5; // r15d
  __int64 v8; // rdi
  int v9; // eax
  int v10; // edx
  const char *v11; // r8
  int v12; // r9d
  unsigned int Data1; // r12d
  __int64 *v14; // rcx
  __int64 v15; // rax
  int v16; // edi
  int v17; // edx
  const char *v18; // r8
  int v19; // r9d
  __int64 *v20; // rcx
  __int64 v21; // rax
  int v22; // edi
  int v23; // edx
  const char *v24; // r8
  int v25; // r9d
  __int64 v26; // rcx
  __int64 *v27; // rcx
  __int64 v28; // rax
  int v29; // edi
  int v30; // edx
  const char *v31; // r8
  int v32; // r9d
  __int64 (__fastcall ***v33)(_QWORD, GUID *, unsigned __int8 *); // rcx
  int v34; // edi
  int v35; // edx
  const char *v36; // r8
  int v37; // r9d
  __int64 *v38; // rcx
  __int64 v39; // rax
  int v40; // edi
  int v41; // edx
  const char *v42; // r8
  int v43; // r9d
  __int64 *v44; // rcx
  __int64 v45; // rcx
  __int64 *v46; // rcx
  __int64 v47; // rax
  int v48; // edi
  int v49; // edx
  const char *v50; // r8
  int v51; // r9d
  struct _GUID v53; // [rsp+30h] [rbp-79h] BYREF
  struct _GUID *v54; // [rsp+40h] [rbp-69h]
  __int128 *v55; // [rsp+48h] [rbp-61h]
  __int128 v56; // [rsp+50h] [rbp-59h] BYREF
  _QWORD *v57; // [rsp+60h] [rbp-49h]
  int v58; // [rsp+68h] [rbp-41h] BYREF
  __int64 v59; // [rsp+6Ch] [rbp-3Dh]
  int v60; // [rsp+74h] [rbp-35h]
  __int64 v61; // [rsp+78h] [rbp-31h]
  int v62; // [rsp+80h] [rbp-29h]
  _DWORD v63[5]; // [rsp+88h] [rbp-21h] BYREF
  __int64 v64; // [rsp+9Ch] [rbp-Dh]
  __int64 v65; // [rsp+A4h] [rbp-5h]
  __int64 v66; // [rsp+ACh] [rbp+3h]

  v5 = (int)a3;
  v57 = a4;
  v53.Data1 = 0;
  v8 = *a1;
  v56 = *(_OWORD *)(*a1 + 100LL);
  v9 = xpsrdr::ConvertWicToDxgiFormat((xpsrdr *)&v56, &v53, a3);
  if ( v9 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v9, v10, v11, v12);
  if ( *(_DWORD *)(v8 + 84) == 1 )
  {
    v64 = 1;
    v66 = 0;
    v63[0] = a2;
    v63[1] = v5;
    v63[2] = 1;
    v63[3] = 1;
    Data1 = v53.Data1;
    v63[4] = v53.Data1;
    v65 = 0x2000000000LL;
    v53.Data1 = 0;
    v14 = *(__int64 **)(v8 + 48);
    v15 = *v14;
    *(_QWORD *)v53.Data4 = 0;
    v54 = &v53;
    v55 = (__int128 *)(a1 + 5);
    v16 = (*(__int64 (__fastcall **)(__int64 *, _DWORD *, _QWORD, unsigned __int8 *))(v15 + 40))(v14, v63, 0, v53.Data4);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v53.Data4);
    if ( (v53.Data1 & 0x80000000) != 0 )
      xpsrdr::ThrowHRException((xpsrdr *)v53.Data1, v17, v18, v19);
    if ( v16 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v16, v17, v18, v19);
    LODWORD(v66) = 0x20000;
    v65 = 3;
    v53.Data1 = 0;
    v20 = *(__int64 **)(*a1 + 48LL);
    v21 = *v20;
    *(_QWORD *)v53.Data4 = 0;
    v54 = &v53;
    v55 = (__int128 *)(a1 + 7);
    v22 = (*(__int64 (__fastcall **)(__int64 *, _DWORD *, _QWORD, unsigned __int8 *))(v21 + 40))(v20, v63, 0, v53.Data4);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v53.Data4);
    if ( (v53.Data1 & 0x80000000) != 0 )
      xpsrdr::ThrowHRException((xpsrdr *)v53.Data1, v23, v24, v25);
    if ( v22 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v22, v23, v24, v25);
    v26 = *a1;
    if ( !*(_BYTE *)(*a1 + 481LL) )
    {
      v53.Data1 = 0;
      v27 = *(__int64 **)(v26 + 48);
      v28 = *v27;
      *(_QWORD *)v53.Data4 = 0;
      v54 = &v53;
      v55 = (__int128 *)(a1 + 9);
      v29 = (*(__int64 (__fastcall **)(__int64 *, _DWORD *, _QWORD, unsigned __int8 *))(v28 + 40))(
              v27,
              v63,
              0,
              v53.Data4);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v53.Data4);
      if ( (v53.Data1 & 0x80000000) != 0 )
        xpsrdr::ThrowHRException((xpsrdr *)v53.Data1, v30, v31, v32);
      if ( v29 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v29, v30, v31, v32);
    }
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v56);
    v53.Data1 = 0;
    v33 = (__int64 (__fastcall ***)(_QWORD, GUID *, unsigned __int8 *))a1[5];
    *(_QWORD *)v53.Data4 = 0;
    v54 = &v53;
    v55 = &v56;
    v34 = (**v33)(v33, &GUID_cafcb56c_6ac3_4889_bf47_9e23bbd260ec, v53.Data4);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v53.Data4);
    if ( (v53.Data1 & 0x80000000) != 0 )
      xpsrdr::ThrowHRException((xpsrdr *)v53.Data1, v35, v36, v37);
    if ( v34 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v34, v35, v36, v37);
    *(_DWORD *)&v53.Data2 = 1;
    v58 = 2;
    v59 = Data1 | 0x100000000LL;
    v60 = 1119879168;
    v61 = 1119879168;
    v62 = 0;
    v53.Data1 = 0;
    v38 = *(__int64 **)(*a1 + 16LL);
    v39 = *v38;
    *(_QWORD *)v53.Data4 = 0;
    v54 = &v53;
    v55 = (__int128 *)(a1 + 3);
    v40 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, int *, unsigned __int8 *))(v39 + 120))(
            v38,
            v56,
            &v58,
            v53.Data4);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v53.Data4);
    if ( (v53.Data1 & 0x80000000) != 0 )
      xpsrdr::ThrowHRException((xpsrdr *)v53.Data1, v41, v42, v43);
    if ( v40 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v40, v41, v42, v43);
    v44 = a1 + 9;
    if ( *(_BYTE *)(*a1 + 481LL) )
      v44 = a1 + 7;
    v45 = *v44;
    a1[12] = a1[7];
    a1[11] = v45;
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v56);
  }
  else
  {
    *(_DWORD *)&v53.Data2 = 1;
    v58 = 1;
    v59 = *(_QWORD *)&v53.Data1;
    v60 = 1119879168;
    v61 = 1119879168;
    v62 = 0;
    v53.Data1 = 0;
    v46 = *(__int64 **)(v8 + 16);
    v47 = *v46;
    *(_QWORD *)v53.Data4 = 0;
    v54 = &v53;
    v55 = (__int128 *)(a1 + 3);
    v48 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, int *, unsigned __int8 *))(v47 + 104))(
            v46,
            *a4,
            &v58,
            v53.Data4);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v53.Data4);
    if ( (v53.Data1 & 0x80000000) != 0 )
      xpsrdr::ThrowHRException((xpsrdr *)v53.Data1, v49, v50, v51);
    if ( v48 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v48, v49, v50, v51);
    resetAddRef<IXpsRasterizerNotificationCallback>(a1 + 5);
    resetAddRef<IXpsRasterizerNotificationCallback>(a1 + 7);
    resetAddRef<IXpsRasterizerNotificationCallback>(a1 + 9);
    a1[12] = 0;
    a1[11] = 0;
  }
  return std::_Ptr_base<ID2D1RenderTarget>::_Decref(a4);
}

```

## disassembly

```asm
0x180038078  mov     [rsp-8+arg_18], r9
0x18003807d  push    rbp
0x18003807e  push    rbx
0x18003807f  push    rsi
0x180038080  push    rdi
0x180038081  push    r12
0x180038083  push    r13
0x180038085  push    r14
0x180038087  push    r15
0x180038089  lea     rbp, [rsp-1Fh]
0x18003808e  sub     rsp, 0C8h
0x180038095  mov     rax, cs:__security_cookie
0x18003809c  xor     rax, rsp
0x18003809f  mov     [rbp+57h+var_48], rax
0x1800380a3  mov     r14, r9
0x1800380a6  mov     r15d, r8d
0x1800380a9  mov     esi, edx
0x1800380ab  mov     rbx, rcx
0x1800380ae  mov     [rbp+57h+var_A0], r9
0x1800380b2  xor     r13d, r13d
0x1800380b5  mov     [rbp+57h+var_D0.Data1], r13d
0x1800380b9  mov     rdi, [rcx]
0x1800380bc  movups  xmm0, xmmword ptr [rdi+64h]
0x1800380c0  movdqu  [rbp+57h+var_B0], xmm0
0x1800380c5  lea     rdx, [rbp+57h+var_D0]; struct _GUID
0x1800380c9  lea     rcx, [rbp+57h+var_B0]; this
0x1800380cd  call    ?ConvertWicToDxgiFormat@xpsrdr@@YAJU_GUID@@PEAW4DXGI_FORMAT@@@Z; xpsrdr::ConvertWicToDxgiFormat(_GUID,DXGI_FORMAT *)
0x1800380d2  test    eax, eax
0x1800380d4  jns     short loc_1800380DE
0x1800380d6  mov     ecx, eax; this
0x1800380d8  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800380de  mov     ecx, 1
0x1800380e3  lea     rdx, [rbp+57h+var_D0]
0x1800380e7  cmp     [rdi+54h], ecx
0x1800380ea  jnz     loc_18003834D
0x1800380f0  mov     [rbp+57h+var_64], rcx
0x1800380f4  mov     [rbp+57h+var_54], r13
0x1800380f8  mov     [rbp+57h+var_78], esi
0x1800380fb  mov     [rbp+57h+var_74], r15d
0x1800380ff  mov     [rbp+57h+var_70], ecx
0x180038102  mov     [rbp+57h+var_6C], ecx
0x180038105  mov     r12d, [rbp+57h+var_D0.Data1]
0x180038109  mov     [rbp+57h+var_68], r12d
0x18003810d  mov     dword ptr [rbp+57h+var_5C], r13d
0x180038111  mov     dword ptr [rbp+57h+var_5C+4], 20h ; ' '
0x180038118  mov     [rbp+57h+var_D0.Data1], r13d
0x18003811c  mov     rcx, [rdi+30h]
0x180038120  mov     rax, [rcx]
0x180038123  mov     qword ptr [rbp+57h+var_D0.Data4], r13
0x180038127  mov     [rbp+57h+var_C0], rdx
0x18003812b  lea     r15, [rbx+28h]
0x18003812f  mov     [rbp+57h+var_B8], r15
0x180038133  lea     r9, [rbp+57h+var_D0.Data4]
0x180038137  xor     r8d, r8d
0x18003813a  lea     rdx, [rbp+57h+var_78]
0x18003813e  mov     rax, [rax+28h]
0x180038142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038147  mov     edi, eax
0x180038149  lea     rcx, [rbp+57h+var_D0.Data4]
0x18003814d  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180038152  mov     ecx, [rbp+57h+var_D0.Data1]; this
0x180038155  test    ecx, ecx
0x180038157  jns     short loc_18003815F
0x180038159  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003815f  test    edi, edi
0x180038161  jns     short loc_18003816B
0x180038163  mov     ecx, edi; this
0x180038165  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003816b  mov     dword ptr [rbp+57h+var_54], 20000h
0x180038172  mov     [rbp+57h+var_5C], 3
0x18003817a  mov     [rbp+57h+var_D0.Data1], r13d
0x18003817e  mov     rax, [rbx]
0x180038181  mov     rcx, [rax+30h]
0x180038185  mov     rax, [rcx]
0x180038188  mov     qword ptr [rbp+57h+var_D0.Data4], r13
0x18003818c  lea     rdx, [rbp+57h+var_D0]
0x180038190  mov     [rbp+57h+var_C0], rdx
0x180038194  lea     rsi, [rbx+38h]
0x180038198  mov     [rbp+57h+var_B8], rsi
0x18003819c  lea     r9, [rbp+57h+var_D0.Data4]
0x1800381a0  xor     r8d, r8d
0x1800381a3  lea     rdx, [rbp+57h+var_78]
0x1800381a7  mov     rax, [rax+28h]
0x1800381ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381b0  mov     edi, eax
0x1800381b2  lea     rcx, [rbp+57h+var_D0.Data4]
0x1800381b6  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800381bb  mov     ecx, [rbp+57h+var_D0.Data1]; this
0x1800381be  test    ecx, ecx
0x1800381c0  jns     short loc_1800381C8
0x1800381c2  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800381c8  test    edi, edi
0x1800381ca  jns     short loc_1800381D4
0x1800381cc  mov     ecx, edi; this
0x1800381ce  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800381d4  mov     rcx, [rbx]
0x1800381d7  cmp     [rcx+1E1h], r13b
0x1800381de  jnz     short loc_180038237
0x1800381e0  mov     [rbp+57h+var_D0.Data1], r13d
0x1800381e4  mov     rcx, [rcx+30h]
0x1800381e8  mov     rax, [rcx]
0x1800381eb  mov     qword ptr [rbp+57h+var_D0.Data4], r13
0x1800381ef  lea     rdx, [rbp+57h+var_D0]
0x1800381f3  mov     [rbp+57h+var_C0], rdx
0x1800381f7  lea     rdx, [rbx+48h]
0x1800381fb  mov     [rbp+57h+var_B8], rdx
0x1800381ff  lea     r9, [rbp+57h+var_D0.Data4]
0x180038203  xor     r8d, r8d
0x180038206  lea     rdx, [rbp+57h+var_78]
0x18003820a  mov     rax, [rax+28h]
0x18003820e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038213  mov     edi, eax
0x180038215  lea     rcx, [rbp+57h+var_D0.Data4]
0x180038219  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003821e  mov     ecx, [rbp+57h+var_D0.Data1]; this
0x180038221  test    ecx, ecx
0x180038223  jns     short loc_18003822B
0x180038225  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003822b  test    edi, edi
0x18003822d  jns     short loc_180038237
0x18003822f  mov     ecx, edi; this
0x180038231  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180038237  lea     rcx, [rbp+57h+var_B0]
0x18003823b  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180038240  nop
0x180038241  mov     [rbp+57h+var_D0.Data1], r13d
0x180038245  mov     rcx, [r15]
0x180038248  mov     qword ptr [rbp+57h+var_D0.Data4], r13
0x18003824c  lea     rax, [rbp+57h+var_D0]
0x180038250  mov     [rbp+57h+var_C0], rax
0x180038254  lea     rax, [rbp+57h+var_B0]
0x180038258  mov     [rbp+57h+var_B8], rax
0x18003825c  mov     rax, [rcx]
0x18003825f  lea     r8, [rbp+57h+var_D0.Data4]
0x180038263  lea     rdx, _GUID_cafcb56c_6ac3_4889_bf47_9e23bbd260ec
0x18003826a  mov     rax, [rax]
0x18003826d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038272  mov     edi, eax
0x180038274  lea     rcx, [rbp+57h+var_D0.Data4]
0x180038278  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003827d  mov     ecx, [rbp+57h+var_D0.Data1]; this
0x180038280  test    ecx, ecx
0x180038282  jns     short loc_18003828A
0x180038284  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003828a  test    edi, edi
0x18003828c  jns     short loc_180038296
0x18003828e  mov     ecx, edi; this
0x180038290  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180038296  mov     [rbp+57h+var_D0.Data1], r12d
0x18003829a  mov     dword ptr [rbp+57h+var_D0.Data2], 1
0x1800382a1  mov     [rbp+57h+var_98], 2
0x1800382a8  mov     rax, qword ptr [rbp+57h+var_D0.Data1]
0x1800382ac  mov     [rbp+57h+var_94], rax
0x1800382b0  mov     [rbp+57h+var_8C], 42C00000h
0x1800382b7  mov     [rbp+57h+var_88], 42C00000h
0x1800382bf  mov     [rbp+57h+var_80], r13d
0x1800382c3  mov     [rbp+57h+var_D0.Data1], r13d
0x1800382c7  mov     rax, [rbx]
0x1800382ca  mov     rcx, [rax+10h]
0x1800382ce  mov     rax, [rcx]
0x1800382d1  mov     qword ptr [rbp+57h+var_D0.Data4], r13
0x1800382d5  lea     rdx, [rbp+57h+var_D0]
0x1800382d9  mov     [rbp+57h+var_C0], rdx
0x1800382dd  lea     rdx, [rbx+18h]
0x1800382e1  mov     [rbp+57h+var_B8], rdx
0x1800382e5  lea     r9, [rbp+57h+var_D0.Data4]
0x1800382e9  lea     r8, [rbp+57h+var_98]
0x1800382ed  mov     rdx, qword ptr [rbp+57h+var_B0]
0x1800382f1  mov     rax, [rax+78h]
0x1800382f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382fa  mov     edi, eax
0x1800382fc  lea     rcx, [rbp+57h+var_D0.Data4]
0x180038300  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180038305  mov     ecx, [rbp+57h+var_D0.Data1]; this
0x180038308  test    ecx, ecx
0x18003830a  jns     short loc_180038312
0x18003830c  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180038312  test    edi, edi
0x180038314  jns     short loc_18003831E
0x180038316  mov     ecx, edi; this
0x180038318  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003831e  mov     rax, [rbx]
0x180038321  cmp     [rax+1E1h], r13b
0x180038328  lea     rcx, [rbx+48h]
0x18003832c  jz      short loc_180038331
0x18003832e  mov     rcx, rsi
0x180038331  mov     rcx, [rcx]
0x180038334  mov     rax, [rsi]
0x180038337  mov     [rbx+60h], rax
0x18003833b  mov     [rbx+58h], rcx
0x18003833f  lea     rcx, [rbp+57h+var_B0]
0x180038343  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180038348  jmp     loc_1800383EA
0x18003834d  mov     eax, [rbp+57h+var_D0.Data1]
0x180038350  mov     [rbp+57h+var_D0.Data1], eax
0x180038353  mov     dword ptr [rbp+57h+var_D0.Data2], ecx
0x180038356  mov     [rbp+57h+var_98], ecx
0x180038359  mov     rax, qword ptr [rbp+57h+var_D0.Data1]
0x18003835d  mov     [rbp+57h+var_94], rax
0x180038361  mov     [rbp+57h+var_8C], 42C00000h
0x180038368  mov     [rbp+57h+var_88], 42C00000h
0x180038370  mov     [rbp+57h+var_80], r13d
0x180038374  mov     [rbp+57h+var_D0.Data1], r13d
0x180038378  mov     rcx, [rdi+10h]
0x18003837c  mov     rax, [rcx]
0x18003837f  mov     qword ptr [rbp+57h+var_D0.Data4], r13
0x180038383  mov     [rbp+57h+var_C0], rdx
0x180038387  lea     rdx, [rbx+18h]
0x18003838b  mov     [rbp+57h+var_B8], rdx
0x18003838f  lea     r9, [rbp+57h+var_D0.Data4]
0x180038393  lea     r8, [rbp+57h+var_98]
0x180038397  mov     rdx, [r14]
0x18003839a  mov     rax, [rax+68h]
0x18003839e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383a3  mov     edi, eax
0x1800383a5  lea     rcx, [rbp+57h+var_D0.Data4]
0x1800383a9  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800383ae  mov     ecx, [rbp+57h+var_D0.Data1]; this
0x1800383b1  test    ecx, ecx
0x1800383b3  jns     short loc_1800383BB
0x1800383b5  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800383bb  test    edi, edi
0x1800383bd  jns     short loc_1800383C7
0x1800383bf  mov     ecx, edi; this
0x1800383c1  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800383c7  lea     rcx, [rbx+28h]
0x1800383cb  call    ??$resetAddRef@UIXpsRasterizerNotificationCallback@@@@YAXAEAV?$shared_ptr@UIXpsRasterizerNotificationCallback@@@std@@PEAUIXpsRasterizerNotificationCallback@@@Z; resetAddRef<IXpsRasterizerNotificationCallback>(std::shared_ptr<IXpsRasterizerNotificationCallback> &,IXpsRasterizerNotificationCallback *)
0x1800383d0  lea     rcx, [rbx+38h]
0x1800383d4  call    ??$resetAddRef@UIXpsRasterizerNotificationCallback@@@@YAXAEAV?$shared_ptr@UIXpsRasterizerNotificationCallback@@@std@@PEAUIXpsRasterizerNotificationCallback@@@Z; resetAddRef<IXpsRasterizerNotificationCallback>(std::shared_ptr<IXpsRasterizerNotificationCallback> &,IXpsRasterizerNotificationCallback *)
0x1800383d9  lea     rcx, [rbx+48h]
0x1800383dd  call    ??$resetAddRef@UIXpsRasterizerNotificationCallback@@@@YAXAEAV?$shared_ptr@UIXpsRasterizerNotificationCallback@@@std@@PEAUIXpsRasterizerNotificationCallback@@@Z; resetAddRef<IXpsRasterizerNotificationCallback>(std::shared_ptr<IXpsRasterizerNotificationCallback> &,IXpsRasterizerNotificationCallback *)
0x1800383e2  mov     [rbx+60h], r13
0x1800383e6  mov     [rbx+58h], r13
0x1800383ea  mov     rcx, r14
0x1800383ed  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800383f2  mov     rcx, [rbp+57h+var_48]
0x1800383f6  xor     rcx, rsp; StackCookie
0x1800383f9  call    __security_check_cookie
0x1800383fe  add     rsp, 0C8h
0x180038405  pop     r15
0x180038407  pop     r14
0x180038409  pop     r13
0x18003840b  pop     r12
0x18003840d  pop     rdi
0x18003840e  pop     rsi
0x18003840f  pop     rbx
0x180038410  pop     rbp
0x180038411  retn
```
