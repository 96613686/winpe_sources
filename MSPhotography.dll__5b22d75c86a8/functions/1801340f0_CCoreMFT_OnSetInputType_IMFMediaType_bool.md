# CCoreMFT::OnSetInputType(IMFMediaType *,bool)

- ea: `0x1801340f0`
- end: `0x180134439`
- name: `?OnSetInputType@CCoreMFT@@AEAAJPEAUIMFMediaType@@_N@Z`
- size: `841`
- prototype: `__int64 __fastcall(LONG *this, struct IMFMediaType *, char)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180134d20`

## callees

- `0x180002420`
- `0x180005660`
- `0x18000b490`
- `0x18000c0b8`
- `0x18000c0f8`
- `0x18001d784`
- `0x1801340f0`
- `0x180134440`
- `0x180142010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18013418f`
- `MFPlat!MFCreateMediaType` at `0x18013418f`
- `MFPlat!MFGetStrideForBitmapInfoHeader` at `0x1801342d9`
- `MFPlat!MFGetStrideForBitmapInfoHeader` at `0x1801342d9`

## pseudocode

```c
__int64 __fastcall CCoreMFT::OnSetInputType(LONG *this, struct IMFMediaType *a2, char a3)
{
  IMFMediaType **v3; // rsi
  char *v5; // rcx
  HRESULT v8; // ebx
  __int64 v9; // rdx
  IMFMediaType *v10; // rcx
  DWORD *v11; // r14
  int v12; // eax
  IMFMediaType *v13; // rcx
  IMFMediaType *v14; // rcx
  int v15; // ebx
  int v16; // esi
  int v18; // [rsp+30h] [rbp-40h] BYREF
  int v19; // [rsp+34h] [rbp-3Ch] BYREF
  int v20; // [rsp+38h] [rbp-38h] BYREF
  __int128 v21; // [rsp+40h] [rbp-30h] BYREF
  DWORD format[4]; // [rsp+50h] [rbp-20h] BYREF

  v3 = (IMFMediaType **)(this + 28);
  v5 = (char *)(this + 28);
  memset(format, 0, sizeof(format));
  if ( a2 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v5);
    v8 = MFCreateMediaType(v3);
    if ( v8 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_36;
      v9 = 135;
      goto LABEL_35;
    }
    v8 = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))a2->lpVtbl->CopyAllItems)(a2, *v3);
    if ( v8 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_36;
      v9 = 136;
      goto LABEL_35;
    }
  }
  else
  {
    v8 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v5);
  }
  if ( a3 )
  {
    v8 = CCoreMFT::OnSetOutputType((CCoreMFT *)this, 0);
    if ( v8 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_36;
      v9 = 137;
      goto LABEL_35;
    }
  }
  v10 = *v3;
  v11 = (DWORD *)(this + 20);
  this[20] = 0;
  this[21] = 0;
  *((_QWORD *)this + 12) = 0;
  if ( !v10 )
    goto LABEL_36;
  v20 = 0;
  v12 = ((__int64 (__fastcall *)(IMFMediaType *, __int64 *, int *))v10->lpVtbl->GetUINT32)(
          v10,
          MF_SD_VIDEO_SPHERICAL_FORMAT,
          &v20);
  v13 = *v3;
  *((_BYTE *)this + 104) = v12 >= 0;
  v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, DWORD *))v13->lpVtbl->GetGUID)(
         v13,
         &MF_MT_SUBTYPE,
         format);
  if ( v8 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_36;
    v9 = 138;
    goto LABEL_35;
  }
  v8 = MFGetAttribute2UINT32asUINT64(*v3, &MF_MT_FRAME_SIZE, this + 20, this + 21);
  if ( v8 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_36;
    v9 = 139;
    goto LABEL_35;
  }
  if ( !*v11 || !this[21] )
  {
    v8 = -1072875852;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_36;
    v9 = 140;
    goto LABEL_35;
  }
  if ( ((int (__fastcall *)(IMFMediaType *, const GUID *, char *))(*v3)->lpVtbl->GetUINT32)(
         *v3,
         &MF_MT_DEFAULT_STRIDE,
         (char *)this + 88) < 0 )
  {
    v8 = MFGetStrideForBitmapInfoHeader(format[0], *v11, this + 22);
    if ( v8 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_36;
      v9 = 141;
      goto LABEL_35;
    }
  }
  v14 = *v3;
  v18 = 0;
  v19 = 0;
  if ( (int)MFGetAttribute2UINT32asUINT64(v14, &MF_MT_FRAME_RATE, &v18, &v19) >= 0 )
  {
    v15 = v18;
    v16 = v19;
  }
  else
  {
    v15 = 30;
    v16 = 1;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 0x20u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this);
  }
  v21 = *(_OWORD *)format;
  *((_QWORD *)this + 12) = (unsigned int)(int)((float)((float)((float)v16 * 10000000.0) / (float)v15) + 0.5);
  v8 = (*(__int64 (__fastcall **)(LONG *, __int128 *))(*(_QWORD *)this + 72LL))(this, &v21);
  if ( v8 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v9 = 143;
LABEL_35:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v8);
  }
LABEL_36:
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1801340f0  mov     [rsp-28h+arg_10], rbx
0x1801340f5  mov     [rsp-28h+arg_18], rsi
0x1801340fa  push    rbp
0x1801340fb  push    rdi
0x1801340fc  push    r13
0x1801340fe  push    r14
0x180134100  push    r15
0x180134102  mov     rbp, rsp
0x180134105  sub     rsp, 70h
0x180134109  mov     rax, cs:__security_cookie
0x180134110  xor     rax, rsp
0x180134113  mov     [rbp+var_10], rax
0x180134117  movsd   xmm0, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data2
0x18013411f  lea     rsi, [rcx+70h]
0x180134123  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4+4
0x180134129  mov     rdi, rcx
0x18013412c  movsd   qword ptr [rbp+format+4], xmm0
0x180134131  mov     rcx, rsi
0x180134134  mov     [rbp+format], 0
0x18013413b  mov     r15b, r8b
0x18013413e  mov     [rbp+format+0Ch], eax
0x180134141  mov     r14, rdx
0x180134144  lea     r13, WPP_55bf114490c93d008a53f926557b4d05_Traceguids
0x18013414b  test    rdx, rdx
0x18013414e  jnz     short loc_180134187
0x180134150  xor     ebx, ebx
0x180134152  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180134157  test    r15b, r15b
0x18013415a  jz      loc_1801341E4
0x180134160  xor     edx, edx; struct IMFMediaType *
0x180134162  mov     rcx, rdi; this
0x180134165  call    ?OnSetOutputType@CCoreMFT@@AEAAJPEAUIMFMediaType@@@Z; CCoreMFT::OnSetOutputType(IMFMediaType *)
0x18013416a  mov     ebx, eax
0x18013416c  test    eax, eax
0x18013416e  jns     short loc_1801341E4
0x180134170  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180134175  cmp     al, 1
0x180134177  jb      loc_1801343EA
0x18013417d  mov     edx, 89h
0x180134182  jmp     loc_1801343D0
0x180134187  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18013418c  mov     rcx, rsi; ppMFType
0x18013418f  call    cs:__imp_MFCreateMediaType
0x180134195  mov     ebx, eax
0x180134197  test    eax, eax
0x180134199  jns     short loc_1801341B2
0x18013419b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801341a0  cmp     al, 1
0x1801341a2  jb      loc_1801343EA
0x1801341a8  mov     edx, 87h
0x1801341ad  jmp     loc_1801343D0
0x1801341b2  mov     rax, [r14]
0x1801341b5  mov     rcx, r14
0x1801341b8  mov     rdx, [rsi]
0x1801341bb  mov     rax, [rax+100h]
0x1801341c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801341c7  mov     ebx, eax
0x1801341c9  test    eax, eax
0x1801341cb  jns     short loc_180134157
0x1801341cd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801341d2  cmp     al, 1
0x1801341d4  jb      loc_1801343EA
0x1801341da  mov     edx, 88h
0x1801341df  jmp     loc_1801343D0
0x1801341e4  mov     rcx, [rsi]
0x1801341e7  lea     r14, [rdi+50h]
0x1801341eb  mov     dword ptr [r14], 0
0x1801341f2  lea     r15, [rdi+54h]
0x1801341f6  mov     dword ptr [r15], 0
0x1801341fd  mov     qword ptr [rdi+60h], 0
0x180134205  test    rcx, rcx
0x180134208  jz      loc_1801343EA
0x18013420e  mov     [rbp+var_38], 0
0x180134215  lea     r8, [rbp+var_38]
0x180134219  mov     rax, [rcx]
0x18013421c  lea     rdx, MF_SD_VIDEO_SPHERICAL_FORMAT
0x180134223  mov     rax, [rax+38h]
0x180134227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013422c  mov     rcx, [rsi]
0x18013422f  lea     r8, [rbp+format]
0x180134233  shr     eax, 1Fh
0x180134236  lea     rdx, MF_MT_SUBTYPE
0x18013423d  xor     al, 1
0x18013423f  mov     [rdi+68h], al
0x180134242  mov     rax, [rcx]
0x180134245  mov     rax, [rax+50h]
0x180134249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013424e  mov     ebx, eax
0x180134250  test    eax, eax
0x180134252  jns     short loc_18013426B
0x180134254  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180134259  cmp     al, 1
0x18013425b  jb      loc_1801343EA
0x180134261  mov     edx, 8Ah
0x180134266  jmp     loc_1801343D0
0x18013426b  mov     rcx, [rsi]
0x18013426e  lea     rdx, MF_MT_FRAME_SIZE
0x180134275  mov     r9, r15
0x180134278  mov     r8, r14
0x18013427b  call    MFGetAttribute2UINT32asUINT64
0x180134280  mov     ebx, eax
0x180134282  test    eax, eax
0x180134284  jns     short loc_18013429D
0x180134286  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18013428b  cmp     al, 1
0x18013428d  jb      loc_1801343EA
0x180134293  mov     edx, 8Bh
0x180134298  jmp     loc_1801343D0
0x18013429d  cmp     dword ptr [r14], 0
0x1801342a1  jz      loc_1801343BD
0x1801342a7  cmp     dword ptr [r15], 0
0x1801342ab  jz      loc_1801343BD
0x1801342b1  mov     rcx, [rsi]
0x1801342b4  lea     r8, [rdi+58h]
0x1801342b8  lea     rdx, MF_MT_DEFAULT_STRIDE
0x1801342bf  mov     rax, [rcx]
0x1801342c2  mov     rax, [rax+38h]
0x1801342c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801342cb  test    eax, eax
0x1801342cd  jns     short loc_1801342FC
0x1801342cf  mov     edx, [r14]; dwWidth
0x1801342d2  lea     r8, [rdi+58h]; pStride
0x1801342d6  mov     ecx, [rbp+format]; format
0x1801342d9  call    cs:__imp_MFGetStrideForBitmapInfoHeader
0x1801342df  mov     ebx, eax
0x1801342e1  test    eax, eax
0x1801342e3  jns     short loc_1801342FC
0x1801342e5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801342ea  cmp     al, 1
0x1801342ec  jb      loc_1801343EA
0x1801342f2  mov     edx, 8Dh
0x1801342f7  jmp     loc_1801343D0
0x1801342fc  mov     rcx, [rsi]
0x1801342ff  lea     r9, [rbp+var_3C]
0x180134303  lea     r8, [rbp+var_40]
0x180134307  mov     [rbp+var_40], 0
0x18013430e  lea     rdx, MF_MT_FRAME_RATE
0x180134315  mov     [rbp+var_3C], 0
0x18013431c  call    MFGetAttribute2UINT32asUINT64
0x180134321  test    eax, eax
0x180134323  jns     short loc_180134351
0x180134325  mov     ebx, 1Eh
0x18013432a  lea     esi, [rbx-1Dh]
0x18013432d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180134332  cmp     al, 20h ; ' '
0x180134334  jb      short loc_180134357
0x180134336  mov     rcx, cs:WPP_GLOBAL_Control
0x18013433d  lea     edx, [rbx+70h]
0x180134340  mov     r9, rdi
0x180134343  mov     r8, r13
0x180134346  mov     rcx, [rcx+10h]
0x18013434a  call    WPP_SF_q
0x18013434f  jmp     short loc_180134357
0x180134351  mov     ebx, [rbp+var_40]
0x180134354  mov     esi, [rbp+var_3C]
0x180134357  xorps   xmm1, xmm1
0x18013435a  mov     eax, esi
0x18013435c  xorps   xmm0, xmm0
0x18013435f  lea     rdx, [rbp+var_30]
0x180134363  mov     rcx, rdi
0x180134366  cvtsi2ss xmm1, rax
0x18013436b  mov     eax, ebx
0x18013436d  cvtsi2ss xmm0, rax
0x180134372  mulss   xmm1, cs:__real@4b189680
0x18013437a  divss   xmm1, xmm0
0x18013437e  movaps  xmm0, xmmword ptr [rbp+format]
0x180134382  cvtps2pd xmm1, xmm1
0x180134385  movdqa  [rbp+var_30], xmm0
0x18013438a  addsd   xmm1, cs:__real@3fe0000000000000
0x180134392  cvttsd2si rax, xmm1
0x180134397  mov     [rdi+60h], rax
0x18013439b  mov     rax, [rdi]
0x18013439e  mov     rax, [rax+48h]
0x1801343a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801343a7  mov     ebx, eax
0x1801343a9  test    eax, eax
0x1801343ab  jns     short loc_1801343EA
0x1801343ad  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801343b2  cmp     al, 1
0x1801343b4  jb      short loc_1801343EA
0x1801343b6  mov     edx, 8Fh
0x1801343bb  jmp     short loc_1801343D0
0x1801343bd  mov     ebx, 0C00D36B4h
0x1801343c2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801343c7  cmp     al, 1
0x1801343c9  jb      short loc_1801343EA
0x1801343cb  mov     edx, 8Ch
0x1801343d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801343d7  mov     r9, rdi
0x1801343da  mov     r8, r13
0x1801343dd  mov     [rsp+70h+var_50], ebx
0x1801343e1  mov     rcx, [rcx+10h]
0x1801343e5  call    WPP_SF_qD
0x1801343ea  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801343ef  cmp     al, 20h ; ' '
0x1801343f1  jb      short loc_180134412
0x1801343f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801343fa  mov     edx, 90h
0x1801343ff  mov     r9, rdi
0x180134402  mov     [rsp+70h+var_50], ebx
0x180134406  mov     r8, r13
0x180134409  mov     rcx, [rcx+10h]
0x18013440d  call    WPP_SF_qD
0x180134412  mov     eax, ebx
0x180134414  mov     rcx, [rbp+var_10]
0x180134418  xor     rcx, rsp; StackCookie
0x18013441b  call    __security_check_cookie
0x180134420  lea     r11, [rsp+70h+var_s0]
0x180134425  mov     rbx, [r11+40h]
0x180134429  mov     rsi, [r11+48h]
0x18013442d  mov     rsp, r11
0x180134430  pop     r15
0x180134432  pop     r14
0x180134434  pop     r13
0x180134436  pop     rdi
0x180134437  pop     rbp
0x180134438  retn
```
