# xpsrdr::VisualsRasterizer::CreateRenderTargets(uint,uint,std::shared_ptr<IWICBitmap>)

- ea: `0x1800ae4c8`
- end: `0x1800ae86f`
- name: `?CreateRenderTargets@VisualsRasterizer@xpsrdr@@AEAAXIIV?$shared_ptr@UIWICBitmap@@@std@@@Z`
- size: `935`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800af338`

## callees

- `0x180003180`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a96e4`
- `0x1800a9f6c`
- `0x1800ac7b8`
- `0x1800ae4c8`
- `0x1800b20e8`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall xpsrdr::VisualsRasterizer::CreateRenderTargets(
        std::_Ref_count_base **a1,
        int a2,
        enum DXGI_FORMAT *a3,
        _QWORD *a4)
{
  int v5; // r15d
  std::_Ref_count_base *v8; // rdi
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
  std::_Ref_count_base *v26; // rcx
  __int64 *v27; // rcx
  __int64 v28; // rax
  int v29; // edi
  int v30; // edx
  const char *v31; // r8
  int v32; // r9d
  std::_Ref_count_base *v33; // rcx
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
  std::_Ref_count_base **v44; // rcx
  std::_Ref_count_base *v45; // rcx
  __int64 *v46; // rcx
  __int64 v47; // rax
  int v48; // edi
  int v49; // edx
  const char *v50; // r8
  int v51; // r9d
  std::_Ref_count_base *v52; // rcx
  struct _GUID v53; // [rsp+30h] [rbp-79h] BYREF
  struct _GUID *v54; // [rsp+40h] [rbp-69h]
  std::_Ref_count_base **v55; // [rsp+48h] [rbp-61h]
  std::_Ref_count_base *v56[2]; // [rsp+50h] [rbp-59h] BYREF
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
  *(_OWORD *)v56 = *(_OWORD *)((char *)*a1 + 100);
  v9 = xpsrdr::ConvertWicToDxgiFormat((xpsrdr *)v56, &v53, a3);
  if ( v9 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v9, v10, v11, v12);
  if ( *((_DWORD *)v8 + 21) == 1 )
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
    v14 = (__int64 *)*((_QWORD *)v8 + 6);
    v15 = *v14;
    *(_QWORD *)v53.Data4 = 0;
    v54 = &v53;
    v55 = a1 + 5;
    v16 = (*(__int64 (__fastcall **)(__int64 *, _DWORD *, _QWORD, unsigned __int8 *))(v15 + 40))(v14, v63, 0, v53.Data4);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v53.Data4);
    if ( (v53.Data1 & 0x80000000) != 0 )
      xpsrdr::ThrowHRException((xpsrdr *)v53.Data1, v17, v18, v19);
    if ( v16 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v16, v17, v18, v19);
    LODWORD(v66) = 0x20000;
    v65 = 3;
    v53.Data1 = 0;
    v20 = (__int64 *)*((_QWORD *)*a1 + 6);
    v21 = *v20;
    *(_QWORD *)v53.Data4 = 0;
    v54 = &v53;
    v55 = a1 + 7;
    v22 = (*(__int64 (__fastcall **)(__int64 *, _DWORD *, _QWORD, unsigned __int8 *))(v21 + 40))(v20, v63, 0, v53.Data4);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v53.Data4);
    if ( (v53.Data1 & 0x80000000) != 0 )
      xpsrdr::ThrowHRException((xpsrdr *)v53.Data1, v23, v24, v25);
    if ( v22 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v22, v23, v24, v25);
    v26 = *a1;
    if ( !*((_BYTE *)*a1 + 481) )
    {
      v53.Data1 = 0;
      v27 = (__int64 *)*((_QWORD *)v26 + 6);
      v28 = *v27;
      *(_QWORD *)v53.Data4 = 0;
      v54 = &v53;
      v55 = a1 + 9;
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
    *(_OWORD *)v56 = 0;
    v53.Data1 = 0;
    v33 = a1[5];
    *(_QWORD *)v53.Data4 = 0;
    v54 = &v53;
    v55 = v56;
    v34 = (**(__int64 (__fastcall ***)(std::_Ref_count_base *, GUID *, unsigned __int8 *))v33)(
            v33,
            &GUID_cafcb56c_6ac3_4889_bf47_9e23bbd260ec,
            v53.Data4);
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
    v38 = (__int64 *)*((_QWORD *)*a1 + 2);
    v39 = *v38;
    *(_QWORD *)v53.Data4 = 0;
    v54 = &v53;
    v55 = a1 + 3;
    v40 = (*(__int64 (__fastcall **)(__int64 *, std::_Ref_count_base *, int *, unsigned __int8 *))(v39 + 120))(
            v38,
            v56[0],
            &v58,
            v53.Data4);
    detail::ComReset<ID2D1RenderTarget>::~ComReset<ID2D1RenderTarget>(v53.Data4);
    if ( (v53.Data1 & 0x80000000) != 0 )
      xpsrdr::ThrowHRException((xpsrdr *)v53.Data1, v41, v42, v43);
    if ( v40 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v40, v41, v42, v43);
    v44 = a1 + 9;
    if ( *((_BYTE *)*a1 + 481) )
      v44 = a1 + 7;
    v45 = *v44;
    a1[12] = a1[7];
    a1[11] = v45;
    if ( v56[1] )
      std::_Ref_count_base::_Decref(v56[1]);
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
    v46 = (__int64 *)*((_QWORD *)v8 + 2);
    v47 = *v46;
    *(_QWORD *)v53.Data4 = 0;
    v54 = &v53;
    v55 = a1 + 3;
    v48 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, int *, unsigned __int8 *))(v47 + 104))(
            v46,
            *a4,
            &v58,
            v53.Data4);
    detail::ComReset<ID2D1RenderTarget>::~ComReset<ID2D1RenderTarget>(v53.Data4);
    if ( (v53.Data1 & 0x80000000) != 0 )
      xpsrdr::ThrowHRException((xpsrdr *)v53.Data1, v49, v50, v51);
    if ( v48 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v48, v49, v50, v51);
    std::shared_ptr<ID3D11Texture2D>::reset(a1 + 5);
    std::shared_ptr<ID3D11Texture2D>::reset(a1 + 7);
    std::shared_ptr<ID3D11Texture2D>::reset(a1 + 9);
    a1[12] = 0;
    a1[11] = 0;
  }
  v52 = (std::_Ref_count_base *)a4[1];
  if ( v52 )
    std::_Ref_count_base::_Decref(v52);
}

```

## disassembly

```asm
0x1800ae4c8  mov     [rsp-8+arg_18], r9
0x1800ae4cd  push    rbp
0x1800ae4ce  push    rbx
0x1800ae4cf  push    rsi
0x1800ae4d0  push    rdi
0x1800ae4d1  push    r12
0x1800ae4d3  push    r13
0x1800ae4d5  push    r14
0x1800ae4d7  push    r15
0x1800ae4d9  lea     rbp, [rsp-1Fh]
0x1800ae4de  sub     rsp, 0C8h
0x1800ae4e5  mov     rax, cs:__security_cookie
0x1800ae4ec  xor     rax, rsp
0x1800ae4ef  mov     [rbp+57h+var_48], rax
0x1800ae4f3  mov     r14, r9
0x1800ae4f6  mov     r15d, r8d
0x1800ae4f9  mov     esi, edx
0x1800ae4fb  mov     rbx, rcx
0x1800ae4fe  mov     [rbp+57h+var_A0], r9
0x1800ae502  xor     r13d, r13d
0x1800ae505  mov     [rbp+57h+var_D0.Data1], r13d
0x1800ae509  mov     rdi, [rcx]
0x1800ae50c  movups  xmm0, xmmword ptr [rdi+64h]
0x1800ae510  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x1800ae515  lea     rdx, [rbp+57h+var_D0]; struct _GUID
0x1800ae519  lea     rcx, [rbp+57h+var_B0]; this
0x1800ae51d  call    ?ConvertWicToDxgiFormat@xpsrdr@@YAJU_GUID@@PEAW4DXGI_FORMAT@@@Z; xpsrdr::ConvertWicToDxgiFormat(_GUID,DXGI_FORMAT *)
0x1800ae522  test    eax, eax
0x1800ae524  jns     short loc_1800AE52E
0x1800ae526  mov     ecx, eax; this
0x1800ae528  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae52e  mov     ecx, 1
0x1800ae533  lea     rdx, [rbp+57h+var_D0]
0x1800ae537  cmp     [rdi+54h], ecx
0x1800ae53a  jnz     loc_1800AE7A4
0x1800ae540  mov     [rbp+57h+var_64], rcx
0x1800ae544  mov     [rbp+57h+var_54], r13
0x1800ae548  mov     [rbp+57h+var_78], esi
0x1800ae54b  mov     [rbp+57h+var_74], r15d
0x1800ae54f  mov     [rbp+57h+var_70], ecx
0x1800ae552  mov     [rbp+57h+var_6C], ecx
0x1800ae555  mov     r12d, [rbp+57h+var_D0.Data1]
0x1800ae559  mov     [rbp+57h+var_68], r12d
0x1800ae55d  mov     dword ptr [rbp+57h+var_5C], r13d
0x1800ae561  mov     dword ptr [rbp+57h+var_5C+4], 20h ; ' '
0x1800ae568  mov     [rbp+57h+var_D0.Data1], r13d
0x1800ae56c  mov     rcx, [rdi+30h]
0x1800ae570  mov     rax, [rcx]
0x1800ae573  mov     qword ptr [rbp+57h+var_D0.Data4], r13
0x1800ae577  mov     [rbp+57h+var_C0], rdx
0x1800ae57b  lea     r15, [rbx+28h]
0x1800ae57f  mov     [rbp+57h+var_B8], r15
0x1800ae583  lea     r9, [rbp+57h+var_D0.Data4]
0x1800ae587  xor     r8d, r8d
0x1800ae58a  lea     rdx, [rbp+57h+var_78]
0x1800ae58e  mov     rax, [rax+28h]
0x1800ae592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae597  mov     edi, eax
0x1800ae599  lea     rcx, [rbp+57h+var_D0.Data4]
0x1800ae59d  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800ae5a2  mov     ecx, [rbp+57h+var_D0.Data1]; this
0x1800ae5a5  test    ecx, ecx
0x1800ae5a7  jns     short loc_1800AE5AF
0x1800ae5a9  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae5af  test    edi, edi
0x1800ae5b1  jns     short loc_1800AE5BB
0x1800ae5b3  mov     ecx, edi; this
0x1800ae5b5  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae5bb  mov     dword ptr [rbp+57h+var_54], 20000h
0x1800ae5c2  mov     [rbp+57h+var_5C], 3
0x1800ae5ca  mov     [rbp+57h+var_D0.Data1], r13d
0x1800ae5ce  mov     rax, [rbx]
0x1800ae5d1  mov     rcx, [rax+30h]
0x1800ae5d5  mov     rax, [rcx]
0x1800ae5d8  mov     qword ptr [rbp+57h+var_D0.Data4], r13
0x1800ae5dc  lea     rdx, [rbp+57h+var_D0]
0x1800ae5e0  mov     [rbp+57h+var_C0], rdx
0x1800ae5e4  lea     rsi, [rbx+38h]
0x1800ae5e8  mov     [rbp+57h+var_B8], rsi
0x1800ae5ec  lea     r9, [rbp+57h+var_D0.Data4]
0x1800ae5f0  xor     r8d, r8d
0x1800ae5f3  lea     rdx, [rbp+57h+var_78]
0x1800ae5f7  mov     rax, [rax+28h]
0x1800ae5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae600  mov     edi, eax
0x1800ae602  lea     rcx, [rbp+57h+var_D0.Data4]
0x1800ae606  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800ae60b  mov     ecx, [rbp+57h+var_D0.Data1]; this
0x1800ae60e  test    ecx, ecx
0x1800ae610  jns     short loc_1800AE618
0x1800ae612  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae618  test    edi, edi
0x1800ae61a  jns     short loc_1800AE624
0x1800ae61c  mov     ecx, edi; this
0x1800ae61e  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae624  mov     rcx, [rbx]
0x1800ae627  cmp     [rcx+1E1h], r13b
0x1800ae62e  jnz     short loc_1800AE687
0x1800ae630  mov     [rbp+57h+var_D0.Data1], r13d
0x1800ae634  mov     rcx, [rcx+30h]
0x1800ae638  mov     rax, [rcx]
0x1800ae63b  mov     qword ptr [rbp+57h+var_D0.Data4], r13
0x1800ae63f  lea     rdx, [rbp+57h+var_D0]
0x1800ae643  mov     [rbp+57h+var_C0], rdx
0x1800ae647  lea     rdx, [rbx+48h]
0x1800ae64b  mov     [rbp+57h+var_B8], rdx
0x1800ae64f  lea     r9, [rbp+57h+var_D0.Data4]
0x1800ae653  xor     r8d, r8d
0x1800ae656  lea     rdx, [rbp+57h+var_78]
0x1800ae65a  mov     rax, [rax+28h]
0x1800ae65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae663  mov     edi, eax
0x1800ae665  lea     rcx, [rbp+57h+var_D0.Data4]
0x1800ae669  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800ae66e  mov     ecx, [rbp+57h+var_D0.Data1]; this
0x1800ae671  test    ecx, ecx
0x1800ae673  jns     short loc_1800AE67B
0x1800ae675  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae67b  test    edi, edi
0x1800ae67d  jns     short loc_1800AE687
0x1800ae67f  mov     ecx, edi; this
0x1800ae681  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae687  xorps   xmm0, xmm0
0x1800ae68a  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x1800ae68f  mov     [rbp+57h+var_D0.Data1], r13d
0x1800ae693  mov     rcx, [r15]
0x1800ae696  mov     qword ptr [rbp+57h+var_D0.Data4], r13
0x1800ae69a  lea     rax, [rbp+57h+var_D0]
0x1800ae69e  mov     [rbp+57h+var_C0], rax
0x1800ae6a2  lea     rax, [rbp+57h+var_B0]
0x1800ae6a6  mov     [rbp+57h+var_B8], rax
0x1800ae6aa  mov     rax, [rcx]
0x1800ae6ad  lea     r8, [rbp+57h+var_D0.Data4]
0x1800ae6b1  lea     rdx, _GUID_cafcb56c_6ac3_4889_bf47_9e23bbd260ec
0x1800ae6b8  mov     rax, [rax]
0x1800ae6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae6c0  mov     edi, eax
0x1800ae6c2  lea     rcx, [rbp+57h+var_D0.Data4]
0x1800ae6c6  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800ae6cb  mov     ecx, [rbp+57h+var_D0.Data1]; this
0x1800ae6ce  test    ecx, ecx
0x1800ae6d0  jns     short loc_1800AE6D8
0x1800ae6d2  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae6d8  test    edi, edi
0x1800ae6da  jns     short loc_1800AE6E4
0x1800ae6dc  mov     ecx, edi; this
0x1800ae6de  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae6e4  mov     [rbp+57h+var_D0.Data1], r12d
0x1800ae6e8  mov     dword ptr [rbp+57h+var_D0.Data2], 1
0x1800ae6ef  mov     [rbp+57h+var_98], 2
0x1800ae6f6  mov     rax, qword ptr [rbp+57h+var_D0.Data1]
0x1800ae6fa  mov     [rbp+57h+var_94], rax
0x1800ae6fe  mov     [rbp+57h+var_8C], 42C00000h
0x1800ae705  mov     [rbp+57h+var_88], 42C00000h
0x1800ae70d  mov     [rbp+57h+var_80], r13d
0x1800ae711  mov     [rbp+57h+var_D0.Data1], r13d
0x1800ae715  mov     rax, [rbx]
0x1800ae718  mov     rcx, [rax+10h]
0x1800ae71c  mov     rax, [rcx]
0x1800ae71f  mov     qword ptr [rbp+57h+var_D0.Data4], r13
0x1800ae723  lea     rdx, [rbp+57h+var_D0]
0x1800ae727  mov     [rbp+57h+var_C0], rdx
0x1800ae72b  lea     rdx, [rbx+18h]
0x1800ae72f  mov     [rbp+57h+var_B8], rdx
0x1800ae733  lea     r9, [rbp+57h+var_D0.Data4]
0x1800ae737  lea     r8, [rbp+57h+var_98]
0x1800ae73b  mov     rdx, [rbp+57h+var_B0]
0x1800ae73f  mov     rax, [rax+78h]
0x1800ae743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae748  mov     edi, eax
0x1800ae74a  lea     rcx, [rbp+57h+var_D0.Data4]
0x1800ae74e  call    ??1?$ComReset@UID2D1RenderTarget@@@detail@@QEAA@XZ; detail::ComReset<ID2D1RenderTarget>::~ComReset<ID2D1RenderTarget>(void)
0x1800ae753  mov     ecx, [rbp+57h+var_D0.Data1]; this
0x1800ae756  test    ecx, ecx
0x1800ae758  jns     short loc_1800AE760
0x1800ae75a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae760  test    edi, edi
0x1800ae762  jns     short loc_1800AE76C
0x1800ae764  mov     ecx, edi; this
0x1800ae766  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae76c  mov     rax, [rbx]
0x1800ae76f  cmp     [rax+1E1h], r13b
0x1800ae776  lea     rcx, [rbx+48h]
0x1800ae77a  jz      short loc_1800AE77F
0x1800ae77c  mov     rcx, rsi
0x1800ae77f  mov     rcx, [rcx]
0x1800ae782  mov     rax, [rsi]
0x1800ae785  mov     [rbx+60h], rax
0x1800ae789  mov     [rbx+58h], rcx
0x1800ae78d  mov     rcx, [rbp+57h+var_B0+8]; this
0x1800ae791  test    rcx, rcx
0x1800ae794  jz      loc_1800AE841
0x1800ae79a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae79f  jmp     loc_1800AE841
0x1800ae7a4  mov     eax, [rbp+57h+var_D0.Data1]
0x1800ae7a7  mov     [rbp+57h+var_D0.Data1], eax
0x1800ae7aa  mov     dword ptr [rbp+57h+var_D0.Data2], ecx
0x1800ae7ad  mov     [rbp+57h+var_98], ecx
0x1800ae7b0  mov     rax, qword ptr [rbp+57h+var_D0.Data1]
0x1800ae7b4  mov     [rbp+57h+var_94], rax
0x1800ae7b8  mov     [rbp+57h+var_8C], 42C00000h
0x1800ae7bf  mov     [rbp+57h+var_88], 42C00000h
0x1800ae7c7  mov     [rbp+57h+var_80], r13d
0x1800ae7cb  mov     [rbp+57h+var_D0.Data1], r13d
0x1800ae7cf  mov     rcx, [rdi+10h]
0x1800ae7d3  mov     rax, [rcx]
0x1800ae7d6  mov     qword ptr [rbp+57h+var_D0.Data4], r13
0x1800ae7da  mov     [rbp+57h+var_C0], rdx
0x1800ae7de  lea     rdx, [rbx+18h]
0x1800ae7e2  mov     [rbp+57h+var_B8], rdx
0x1800ae7e6  lea     r9, [rbp+57h+var_D0.Data4]
0x1800ae7ea  lea     r8, [rbp+57h+var_98]
0x1800ae7ee  mov     rdx, [r14]
0x1800ae7f1  mov     rax, [rax+68h]
0x1800ae7f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae7fa  mov     edi, eax
0x1800ae7fc  lea     rcx, [rbp+57h+var_D0.Data4]
0x1800ae800  call    ??1?$ComReset@UID2D1RenderTarget@@@detail@@QEAA@XZ; detail::ComReset<ID2D1RenderTarget>::~ComReset<ID2D1RenderTarget>(void)
0x1800ae805  mov     ecx, [rbp+57h+var_D0.Data1]; this
0x1800ae808  test    ecx, ecx
0x1800ae80a  jns     short loc_1800AE812
0x1800ae80c  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae812  test    edi, edi
0x1800ae814  jns     short loc_1800AE81E
0x1800ae816  mov     ecx, edi; this
0x1800ae818  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ae81e  lea     rcx, [rbx+28h]
0x1800ae822  call    ?reset@?$shared_ptr@UID3D11Texture2D@@@std@@QEAAXXZ; std::shared_ptr<ID3D11Texture2D>::reset(void)
0x1800ae827  lea     rcx, [rbx+38h]
0x1800ae82b  call    ?reset@?$shared_ptr@UID3D11Texture2D@@@std@@QEAAXXZ; std::shared_ptr<ID3D11Texture2D>::reset(void)
0x1800ae830  lea     rcx, [rbx+48h]
0x1800ae834  call    ?reset@?$shared_ptr@UID3D11Texture2D@@@std@@QEAAXXZ; std::shared_ptr<ID3D11Texture2D>::reset(void)
0x1800ae839  mov     [rbx+60h], r13
0x1800ae83d  mov     [rbx+58h], r13
0x1800ae841  mov     rcx, [r14+8]; this
0x1800ae845  test    rcx, rcx
0x1800ae848  jz      short loc_1800AE84F
0x1800ae84a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae84f  mov     rcx, [rbp+57h+var_48]
0x1800ae853  xor     rcx, rsp; StackCookie
0x1800ae856  call    __security_check_cookie
0x1800ae85b  add     rsp, 0C8h
0x1800ae862  pop     r15
0x1800ae864  pop     r14
0x1800ae866  pop     r13
0x1800ae868  pop     r12
0x1800ae86a  pop     rdi
0x1800ae86b  pop     rsi
0x1800ae86c  pop     rbx
0x1800ae86d  pop     rbp
0x1800ae86e  retn
```
