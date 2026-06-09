# GDIHelpers::ColorizeBitmapFromResource(HINSTANCE__ *,ushort const *,ushort const *,bool,ulong,ulong,HBITMAP__ * *)

- ea: `0x1800072e0`
- end: `0x180007af9`
- name: `?ColorizeBitmapFromResource@GDIHelpers@@YAJPEAUHINSTANCE__@@PEBG1_NKKPEAPEAUHBITMAP__@@@Z`
- size: `2073`
- prototype: `__int64 __fastcall(GDIHelpers *__hidden this, HINSTANCE, const unsigned __int16 *, const unsigned __int16 *, bool, unsigned int, unsigned int, HBITMAP *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007100`
- `0x18005f3dc`

## callees

- `0x180004c98`
- `0x1800072e0`
- `0x180007b00`
- `0x18002c9f0`
- `0x180030aec`
- `0x180040270`
- `0x180043c30`
- `0x180046f62`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007380`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800078f1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007380`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800078f1`
- `SHCORE!__imp_SHCreateStreamOnModuleResourceW` at `0x18000733f`
- `SHCORE!__imp_SHCreateStreamOnModuleResourceW` at `0x18000733f`
- `GDI32!GetObjectW` at `0x1800076db`
- `GDI32!GetObjectW` at `0x1800076db`
- `GDI32!DeleteObject` at `0x180007765`
- `GDI32!DeleteObject` at `0x1800078bf`
- `GDI32!DeleteObject` at `0x180007765`
- `GDI32!DeleteObject` at `0x1800078bf`
- `GDI32!CreateDIBSection` at `0x180007611`
- `GDI32!CreateDIBSection` at `0x180007611`
- `USER32!CopyImage` at `0x1800076b4`
- `USER32!CopyImage` at `0x1800076b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall GDIHelpers::ColorizeBitmapFromResource(
        GDIHelpers *this,
        HINSTANCE a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        unsigned int a6,
        HBITMAP *a7)
{
  char v7; // r14
  int v10; // eax
  unsigned int v11; // ebx
  HRESULT Instance; // eax
  unsigned int v13; // ebx
  __int64 v14; // rsi
  void *v15; // rbx
  __int64 (__fastcall *v16)(void *, __int64, GUID *, _QWORD); // rdi
  HRESULT v17; // ebx
  struct IWICBitmapSource *v18; // rcx
  struct IWICBitmapSource *v19; // rcx
  HBITMAP v20; // rcx
  struct IWICImagingFactory *v21; // rsi
  struct IWICBitmapSource *v22; // rdi
  HBITMAP v23; // r14
  HRESULT (__stdcall *CreateFormatConverter)(IWICImagingFactory *, IWICFormatConverter **); // rbx
  struct IWICBitmapSource *v25; // rcx
  struct IWICBitmapSource *v26; // rdi
  HBITMAP v27; // rsi
  struct IWICBitmapSource *v28; // rcx
  HBITMAP v29; // rax
  HBITMAP v30; // rdi
  __int64 v31; // r11
  int v32; // ebx
  int v33; // eax
  int v34; // r8d
  unsigned int v35; // ecx
  int v36; // ebx
  unsigned int i; // r9d
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  struct IWICBitmapSource *v42; // rcx
  struct IWICImagingFactory *v43; // rcx
  __int64 v44; // rcx
  __int64 v46; // rdx
  struct IWICImagingFactory *v47; // rdi
  HRESULT (__stdcall *CreateBitmapFlipRotator)(IWICImagingFactory *, IWICBitmapFlipRotator **); // rbx
  __int64 v49; // rdx
  int ppv; // [rsp+20h] [rbp-C1h]
  int ppva; // [rsp+20h] [rbp-C1h]
  struct IWICBitmapSource **ppvb; // [rsp+20h] [rbp-C1h]
  struct IWICBitmapSource *v53; // [rsp+40h] [rbp-A1h] BYREF
  HBITMAP v54; // [rsp+48h] [rbp-99h] BYREF
  struct IWICImagingFactory *v55; // [rsp+50h] [rbp-91h] BYREF
  __int64 v56; // [rsp+58h] [rbp-89h] BYREF
  struct IWICBitmapSource *v57; // [rsp+60h] [rbp-81h] BYREF
  struct IWICBitmapSource *v58; // [rsp+68h] [rbp-79h] BYREF
  LONG v59[4]; // [rsp+70h] [rbp-71h] BYREF
  GUID Buf2; // [rsp+80h] [rbp-61h] BYREF
  __int128 Buf1; // [rsp+90h] [rbp-51h] BYREF
  __int128 v62; // [rsp+A0h] [rbp-41h]
  BITMAPINFO pbmi; // [rsp+B0h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v7 = (char)a4;
  *a7 = 0;
  v56 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v56);
  v10 = SHCreateStreamOnModuleResourceW(this, a2, L"IMAGE", &v56);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"desktop\\internal\\shell\\inc\\private\\GDIHelpers.h",
      (const char *)(unsigned int)v10,
      ppv);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v56);
    return v11;
  }
  v55 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
  Instance = CoCreateInstance(
               &CLSID_WICImagingFactory2,
               0,
               1u,
               &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
               (LPVOID *)&v55);
  v13 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"desktop\\internal\\shell\\inc\\private\\GDIHelpers.h",
      (const char *)(unsigned int)Instance,
      ppva);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v56);
    return v13;
  }
  v14 = v56;
  v15 = v55;
  v57 = 0;
  v54 = (HBITMAP)v55;
  if ( v55 )
  {
    ((void (__fastcall *)(struct IWICImagingFactory *))v55->lpVtbl->AddRef)(v55);
    v15 = v54;
  }
  if ( !v15 )
  {
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v54);
    v17 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, (LPVOID *)&v54);
    if ( v17 < 0 )
      goto LABEL_13;
    v15 = v54;
  }
  v53 = 0;
  v16 = *(__int64 (__fastcall **)(void *, __int64, GUID *, _QWORD))(*(_QWORD *)v15 + 32LL);
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v53);
  ppvb = &v53;
  v17 = v16(v15, v14, &GUID_VendorMicrosoftBuiltIn, 0);
  if ( v17 >= 0 )
  {
    v58 = 0;
    v17 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, _QWORD, struct IWICBitmapSource **))v53->lpVtbl[1].GetResolution)(
            v53,
            0,
            &v58);
    if ( v17 >= 0 )
      v17 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, GUID *, struct IWICBitmapSource **))v58->lpVtbl->QueryInterface)(
              v58,
              &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94,
              &v57);
    v18 = v58;
    if ( v58 )
    {
      v58 = 0;
      ((void (__fastcall *)(struct IWICBitmapSource *))v18->lpVtbl->Release)(v18);
    }
  }
  v19 = v53;
  if ( v53 )
  {
    v53 = 0;
    ((void (__fastcall *)(struct IWICBitmapSource *))v19->lpVtbl->Release)(v19);
  }
LABEL_13:
  v20 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(HBITMAP))(*(_QWORD *)v20 + 16LL))(v20);
  }
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"desktop\\internal\\shell\\inc\\private\\GDIHelpers.h",
      (const char *)(unsigned int)v17,
      (int)ppvb);
LABEL_67:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v57);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v56);
    return (unsigned int)v17;
  }
  v54 = 0;
  if ( v7 )
  {
    v53 = 0;
    v47 = v55;
    CreateBitmapFlipRotator = v55->lpVtbl->CreateBitmapFlipRotator;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
    v17 = ((__int64 (__fastcall *)(struct IWICImagingFactory *, struct IWICBitmapSource **))CreateBitmapFlipRotator)(
            v47,
            &v53);
    if ( v17 < 0 )
    {
      v46 = 152;
    }
    else
    {
      v17 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct IWICBitmapSource *, __int64))v53->lpVtbl[1].QueryInterface)(
              v53,
              v57,
              8);
      if ( v17 >= 0 )
      {
        v17 = ConvertIWICBitmapSourceTo32bppHBITMAP(v53, v55, &v54);
        if ( v17 >= 0 )
        {
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
          v23 = v54;
          goto LABEL_31;
        }
        v46 = 154;
      }
      else
      {
        v46 = 153;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v46,
      (unsigned int)"desktop\\internal\\shell\\inc\\private\\GDIHelpers.h",
      (const char *)(unsigned int)v17,
      (int)ppvb);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
    goto LABEL_66;
  }
  v21 = v55;
  v22 = v57;
  v23 = 0;
  v54 = 0;
  Buf2 = GUID_WICPixelFormat32bppBGRA;
  v58 = 0;
  Buf1 = 0;
  v17 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int128 *))v57->lpVtbl->GetPixelFormat)(v57, &Buf1);
  if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
  {
    v58 = v22;
    ((void (__fastcall *)(struct IWICBitmapSource *))v22->lpVtbl->AddRef)(v22);
  }
  else
  {
    v53 = 0;
    CreateFormatConverter = v21->lpVtbl->CreateFormatConverter;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
    v17 = ((__int64 (__fastcall *)(struct IWICImagingFactory *, struct IWICBitmapSource **))CreateFormatConverter)(
            v21,
            &v53);
    if ( v17 >= 0
      && (LODWORD(ppvb) = 0,
          v17 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct IWICBitmapSource *, GUID *, _QWORD))v53->lpVtbl[1].QueryInterface)(
                  v53,
                  v22,
                  &Buf2,
                  0),
          v17 >= 0) )
    {
      v25 = 0;
      v58 = v53;
    }
    else
    {
      v25 = v53;
    }
    if ( v25 )
    {
      v53 = 0;
      ((void (__fastcall *)(struct IWICBitmapSource *))v25->lpVtbl->Release)(v25);
    }
  }
  if ( v17 >= 0 )
  {
    v26 = v58;
    v23 = 0;
    v54 = 0;
    v59[0] = 0;
    LODWORD(v53) = 0;
    v17 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, LONG *, struct IWICBitmapSource **))v58->lpVtbl->GetSize)(
            v58,
            v59,
            &v53);
    if ( v17 >= 0 )
    {
      memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
      pbmi.bmiHeader.biSize = 40;
      pbmi.bmiHeader.biWidth = v59[0];
      pbmi.bmiHeader.biHeight = -(int)v53;
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
      *(_QWORD *)&Buf2.Data1 = 0;
      v27 = CreateDIBSection(0, &pbmi, 0, (void **)&Buf2, 0, 0);
      if ( v27 )
      {
        *(_QWORD *)&Buf1 = 0;
        *((_QWORD *)&Buf1 + 1) = __PAIR64__((unsigned int)v53, v59[0]);
        LODWORD(ppvb) = Buf2.Data1;
        v17 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int128 *, _QWORD, _QWORD))v26->lpVtbl->CopyPixels)(
                v26,
                &Buf1,
                (unsigned int)(4 * v59[0]),
                (unsigned int)(4 * v59[0] * (_DWORD)v53));
        if ( v17 < 0 )
        {
          DeleteObject(v27);
        }
        else
        {
          v23 = v27;
          v54 = v27;
        }
      }
      else
      {
        v17 = -2147024882;
      }
    }
  }
  v28 = v58;
  if ( v58 )
  {
    v58 = 0;
    ((void (__fastcall *)(struct IWICBitmapSource *))v28->lpVtbl->Release)(v28);
  }
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"desktop\\internal\\shell\\inc\\private\\GDIHelpers.h",
      (const char *)(unsigned int)v17,
      (int)ppvb);
LABEL_66:
    CAutoHandle<HBITMAP__ *>::~CAutoHandle<HBITMAP__ *>(&v54);
    goto LABEL_67;
  }
LABEL_31:
  if ( !v23 )
  {
    v49 = 161;
LABEL_78:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v49,
      (unsigned int)"desktop\\internal\\shell\\inc\\private\\GDIHelpers.h",
      (const char *)0x8007000ELL,
      (int)ppvb);
    CAutoHandle<HBITMAP__ *>::~CAutoHandle<HBITMAP__ *>(&v54);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v57);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v56);
    return 2147942414LL;
  }
  v29 = (HBITMAP)CopyImage(v23, 0, 0, 0, 0x2000u);
  v30 = v29;
  if ( v29 )
  {
    Buf1 = 0;
    v62 = 0;
    if ( GetObjectW(v29, 32, &Buf1) )
    {
      v31 = *((_QWORD *)&v62 + 1);
      if ( *((_QWORD *)&v62 + 1) )
      {
        if ( WORD1(v62) == 32 )
        {
          v32 = DWORD2(Buf1);
          v33 = DWORD1(Buf1);
          v34 = DWORD1(Buf1) * DWORD2(Buf1);
          v35 = 0;
          if ( DWORD1(Buf1) * DWORD2(Buf1) > 0 )
          {
            do
            {
              if ( *(_BYTE *)(v31 + 4LL * v35 + 2) == (_BYTE)a5
                && *(_BYTE *)(v31 + 4LL * v35 + 1) == BYTE1(a5)
                && *(_BYTE *)(v31 + 4LL * v35) == BYTE2(a5) )
              {
                *(_BYTE *)(v31 + 4LL * v35 + 2) = a6;
                *(_BYTE *)(v31 + 4LL * v35 + 1) = BYTE1(a6);
                *(_BYTE *)(v31 + 4LL * v35) = BYTE2(a6);
              }
              ++v35;
            }
            while ( (int)v35 < v34 );
            v32 = DWORD2(Buf1);
            v33 = DWORD1(Buf1);
          }
          v36 = v33 * v32;
          for ( i = 0; (int)i < v36; ++i )
          {
            v38 = *(unsigned __int8 *)(v31 + 4LL * i + 3);
            if ( (_BYTE)v38 )
            {
              *(_BYTE *)(v31 + 4LL * i + 2) = (v38 * (unsigned int)*(unsigned __int8 *)(v31 + 4LL * i + 2) + 128) / 0xFF;
              *(_BYTE *)(v31 + 4LL * i + 1) = ((unsigned int)*(unsigned __int8 *)(v31 + 4LL * i + 1) * v38 + 128) / 0xFF;
              *(_BYTE *)(v31 + 4LL * i) = ((unsigned int)*(unsigned __int8 *)(v31 + 4LL * i) * v38 + 128) / 0xFF;
            }
            else
            {
              *(_DWORD *)(v31 + 4LL * i) = 0;
            }
          }
        }
      }
    }
  }
  DeleteObject(v23);
  v54 = v30;
  if ( !v30 )
  {
    v49 = 163;
    goto LABEL_78;
  }
  *a7 = v30;
  v42 = v57;
  if ( v57 )
  {
    v57 = 0;
    ((void (__fastcall *)(struct IWICBitmapSource *, __int64, __int64, __int64))v42->lpVtbl->Release)(
      v42,
      v39,
      v40,
      v41);
  }
  v43 = v55;
  if ( v55 )
  {
    v55 = 0;
    ((void (__fastcall *)(struct IWICImagingFactory *, __int64, __int64, __int64))v43->lpVtbl->Release)(
      v43,
      v39,
      v40,
      v41);
  }
  v44 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v44 + 16LL))(v44, v39, v40, v41);
  }
  return 0;
}

```

## disassembly

```asm
0x1800072e0  mov     [rsp-8+arg_10], rbx
0x1800072e5  push    rbp
0x1800072e6  push    rsi
0x1800072e7  push    rdi
0x1800072e8  push    r12
0x1800072ea  push    r13
0x1800072ec  push    r14
0x1800072ee  push    r15
0x1800072f0  lea     rbp, [rsp-0Fh]
0x1800072f5  sub     rsp, 0F0h
0x1800072fc  mov     rax, cs:__security_cookie
0x180007303  xor     rax, rsp
0x180007306  mov     [rbp+3Fh+var_40], rax
0x18000730a  movzx   r14d, r9b
0x18000730e  mov     rdi, rdx
0x180007311  mov     rbx, rcx
0x180007314  mov     r15, qword ptr [rbp+3Fh+arg_30]
0x180007318  xor     r12d, r12d
0x18000731b  mov     [r15], r12
0x18000731e  mov     [rsp+120h+var_C8], r12
0x180007323  lea     rcx, [rsp+120h+var_C8]
0x180007328  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000732d  lea     r9, [rsp+120h+var_C8]
0x180007332  lea     r8, aImage; "IMAGE"
0x180007339  mov     rdx, rdi
0x18000733c  mov     rcx, rbx
0x18000733f  call    cs:__imp_SHCreateStreamOnModuleResourceW
0x180007345  mov     ebx, eax
0x180007347  test    eax, eax
0x180007349  js      loc_18000790B
0x18000734f  mov     [rsp+120h+var_D0], r12
0x180007354  lea     rcx, [rsp+120h+var_D0]
0x180007359  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000735e  lea     rax, [rsp+120h+var_D0]
0x180007363  mov     [rsp+120h+ppv], rax; int
0x180007368  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18000736f  mov     edi, 1
0x180007374  mov     r8d, edi; dwClsContext
0x180007377  xor     edx, edx; pUnkOuter
0x180007379  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180007380  call    cs:__imp_CoCreateInstance
0x180007386  mov     ebx, eax
0x180007388  test    eax, eax
0x18000738a  js      loc_180007935
0x180007390  mov     rsi, [rsp+120h+var_C8]
0x180007395  mov     rbx, [rsp+120h+var_D0]
0x18000739a  mov     [rsp+120h+var_C0], r12
0x18000739f  mov     [rsp+120h+var_D8], rbx
0x1800073a4  test    rbx, rbx
0x1800073a7  jz      short loc_1800073BD
0x1800073a9  mov     rax, [rbx]
0x1800073ac  mov     rcx, rbx
0x1800073af  mov     rax, [rax+8]
0x1800073b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073b8  mov     rbx, [rsp+120h+var_D8]
0x1800073bd  test    rbx, rbx
0x1800073c0  jz      loc_1800078CA
0x1800073c6  mov     [rsp+120h+var_E0], r12
0x1800073cb  mov     rax, [rbx]
0x1800073ce  mov     rdi, [rax+20h]
0x1800073d2  lea     rcx, [rsp+120h+var_E0]
0x1800073d7  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1800073dc  lea     rax, [rsp+120h+var_E0]
0x1800073e1  mov     [rsp+120h+ppv], rax; int
0x1800073e6  xor     r9d, r9d
0x1800073e9  lea     r8, GUID_VendorMicrosoftBuiltIn
0x1800073f0  mov     rdx, rsi
0x1800073f3  mov     rcx, rbx
0x1800073f6  mov     rax, rdi
0x1800073f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073fe  mov     ebx, eax
0x180007400  test    eax, eax
0x180007402  js      short loc_18000745C
0x180007404  mov     [rbp+3Fh+var_B8], r12
0x180007408  mov     rcx, [rsp+120h+var_E0]
0x18000740d  mov     rax, [rcx]
0x180007410  lea     r8, [rbp+3Fh+var_B8]
0x180007414  xor     edx, edx
0x180007416  mov     rax, [rax+68h]
0x18000741a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000741f  mov     ebx, eax
0x180007421  test    eax, eax
0x180007423  js      short loc_180007442
0x180007425  mov     rcx, [rbp+3Fh+var_B8]
0x180007429  mov     rax, [rcx]
0x18000742c  lea     r8, [rsp+120h+var_C0]
0x180007431  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x180007438  mov     rax, [rax]
0x18000743b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007440  mov     ebx, eax
0x180007442  mov     rcx, [rbp+3Fh+var_B8]
0x180007446  test    rcx, rcx
0x180007449  jz      short loc_18000745C
0x18000744b  mov     [rbp+3Fh+var_B8], r12
0x18000744f  mov     rax, [rcx]
0x180007452  mov     rax, [rax+10h]
0x180007456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000745b  nop
0x18000745c  mov     rcx, [rsp+120h+var_E0]
0x180007461  test    rcx, rcx
0x180007464  jz      short loc_180007478
0x180007466  mov     [rsp+120h+var_E0], r12
0x18000746b  mov     rax, [rcx]
0x18000746e  mov     rax, [rax+10h]
0x180007472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007477  nop
0x180007478  mov     rcx, [rsp+120h+var_D8]
0x18000747d  test    rcx, rcx
0x180007480  jz      short loc_180007494
0x180007482  mov     [rsp+120h+var_D8], r12
0x180007487  mov     rax, [rcx]
0x18000748a  mov     rax, [rax+10h]
0x18000748e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007493  nop
0x180007494  test    ebx, ebx
0x180007496  js      loc_18000796A
0x18000749c  mov     [rsp+120h+var_D8], r12
0x1800074a1  mov     r13d, 20h ; ' '
0x1800074a7  test    r14b, r14b
0x1800074aa  jnz     loc_1800079DA
0x1800074b0  mov     rsi, [rsp+120h+var_D0]
0x1800074b5  mov     rdi, [rsp+120h+var_C0]
0x1800074ba  mov     r14, r12
0x1800074bd  mov     [rsp+120h+var_D8], r12
0x1800074c2  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x1800074c9  movaps  [rbp+3Fh+Buf2], xmm0
0x1800074cd  mov     [rbp+3Fh+var_B8], r12
0x1800074d1  xorps   xmm0, xmm0
0x1800074d4  movups  [rbp+3Fh+Buf1], xmm0
0x1800074d8  mov     rax, [rdi]
0x1800074db  lea     rdx, [rbp+3Fh+Buf1]
0x1800074df  mov     rcx, rdi
0x1800074e2  mov     rax, [rax+20h]
0x1800074e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074eb  mov     ebx, eax
0x1800074ed  mov     r8d, 10h; Size
0x1800074f3  lea     rdx, [rbp+3Fh+Buf2]; Buf2
0x1800074f7  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x1800074fb  call    memcmp_0
0x180007500  test    eax, eax
0x180007502  jz      loc_18000789A
0x180007508  mov     [rsp+120h+var_E0], r12
0x18000750d  mov     rax, [rsi]
0x180007510  mov     rbx, [rax+50h]
0x180007514  lea     rcx, [rsp+120h+var_E0]
0x180007519  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000751e  lea     rdx, [rsp+120h+var_E0]
0x180007523  mov     rcx, rsi
0x180007526  mov     rax, rbx
0x180007529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000752e  mov     ebx, eax
0x180007530  test    eax, eax
0x180007532  js      short loc_18000756C
0x180007534  mov     rcx, [rsp+120h+var_E0]
0x180007539  mov     rax, [rcx]
0x18000753c  mov     [rsp+120h+var_F0], r12d
0x180007541  xorps   xmm0, xmm0
0x180007544  movsd   qword ptr [rsp+120h+offset], xmm0
0x18000754a  mov     [rsp+120h+ppv], r12
0x18000754f  xor     r9d, r9d
0x180007552  lea     r8, [rbp+3Fh+Buf2]
0x180007556  mov     rdx, rdi
0x180007559  mov     rax, [rax+40h]
0x18000755d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007562  mov     ebx, eax
0x180007564  test    eax, eax
0x180007566  jns     loc_180007A73
0x18000756c  mov     rcx, [rsp+120h+var_E0]
0x180007571  test    rcx, rcx
0x180007574  jz      short loc_180007588
0x180007576  mov     [rsp+120h+var_E0], r12
0x18000757b  mov     rax, [rcx]
0x18000757e  mov     rax, [rax+10h]
0x180007582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007587  nop
0x180007588  test    ebx, ebx
0x18000758a  js      loc_180007676
0x180007590  mov     rdi, [rbp+3Fh+var_B8]
0x180007594  mov     r14, r12
0x180007597  mov     [rsp+120h+var_D8], r12
0x18000759c  mov     [rbp+3Fh+var_B0], r12d
0x1800075a0  mov     dword ptr [rsp+120h+var_E0], r12d
0x1800075a5  mov     rax, [rdi]
0x1800075a8  lea     r8, [rsp+120h+var_E0]
0x1800075ad  lea     rdx, [rbp+3Fh+var_B0]
0x1800075b1  mov     rcx, rdi
0x1800075b4  mov     rax, [rax+18h]
0x1800075b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075bd  mov     ebx, eax
0x1800075bf  test    eax, eax
0x1800075c1  js      loc_180007676
0x1800075c7  xorps   xmm0, xmm0
0x1800075ca  xor     eax, eax
0x1800075cc  movups  xmmword ptr [rbp+3Fh+pbmi.bmiHeader.biWidth], xmm0
0x1800075d0  movups  xmmword ptr [rbp+3Fh+pbmi.bmiHeader.biSizeImage], xmm0
0x1800075d4  mov     qword ptr [rbp+3Fh+pbmi.bmiHeader.biClrImportant], rax
0x1800075d8  mov     [rbp+3Fh+pbmi.bmiHeader.biSize], 28h ; '('
0x1800075df  mov     eax, [rbp+3Fh+var_B0]
0x1800075e2  mov     [rbp+3Fh+pbmi.bmiHeader.biWidth], eax
0x1800075e5  mov     eax, dword ptr [rsp+120h+var_E0]
0x1800075e9  neg     eax
0x1800075eb  mov     [rbp+3Fh+pbmi.bmiHeader.biHeight], eax
0x1800075ee  mov     qword ptr [rbp+3Fh+pbmi.bmiHeader.biPlanes], 200001h
0x1800075f6  mov     qword ptr [rbp+3Fh+Buf2], r12
0x1800075fa  mov     [rsp+120h+offset], r12d; offset
0x1800075ff  mov     [rsp+120h+ppv], r12; hSection
0x180007604  lea     r9, [rbp+3Fh+Buf2]; ppvBits
0x180007608  xor     r8d, r8d; usage
0x18000760b  lea     rdx, [rbp+3Fh+pbmi]; pbmi
0x18000760f  xor     ecx, ecx; hdc
0x180007611  call    cs:__imp_CreateDIBSection
0x180007617  mov     rsi, rax
0x18000761a  test    rax, rax
0x18000761d  jz      loc_1800078B2
0x180007623  mov     qword ptr [rbp+3Fh+Buf1], r12
0x180007627  mov     r8d, [rbp+3Fh+var_B0]
0x18000762b  mov     dword ptr [rbp+3Fh+Buf1+8], r8d
0x18000762f  mov     r9d, dword ptr [rsp+120h+var_E0]
0x180007634  mov     dword ptr [rbp+3Fh+Buf1+0Ch], r9d
0x180007638  mov     rdx, [rdi]
0x18000763b  imul    r9d, r8d
0x18000763f  shl     r9d, 2
0x180007643  lea     r8d, ds:0[r8*4]
0x18000764b  mov     rax, [rdx+38h]
0x18000764f  mov     rdx, qword ptr [rbp+3Fh+Buf2]
0x180007653  mov     [rsp+120h+ppv], rdx; int
0x180007658  lea     rdx, [rbp+3Fh+Buf1]
0x18000765c  mov     rcx, rdi
0x18000765f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007664  mov     ebx, eax
0x180007666  test    eax, eax
0x180007668  js      loc_1800078BC
0x18000766e  mov     r14, rsi
0x180007671  mov     [rsp+120h+var_D8], rsi
0x180007676  mov     rcx, [rbp+3Fh+var_B8]
0x18000767a  test    rcx, rcx
0x18000767d  jz      short loc_180007690
0x18000767f  mov     [rbp+3Fh+var_B8], r12
0x180007683  mov     rax, [rcx]
0x180007686  mov     rax, [rax+10h]
0x18000768a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000768f  nop
0x180007690  test    ebx, ebx
0x180007692  js      loc_180007A84
0x180007698  test    r14, r14
0x18000769b  jz      loc_180007AA1
0x1800076a1  mov     dword ptr [rsp+120h+ppv], 2000h; int
0x1800076a9  xor     r9d, r9d; cy
0x1800076ac  xor     r8d, r8d; cx
0x1800076af  xor     edx, edx; type
0x1800076b1  mov     rcx, r14; h
0x1800076b4  call    cs:__imp_CopyImage
0x1800076ba  mov     rdi, rax
0x1800076bd  test    rax, rax
0x1800076c0  jz      loc_18000775D
0x1800076c6  xorps   xmm0, xmm0
0x1800076c9  movups  [rbp+3Fh+Buf1], xmm0
0x1800076cd  movups  [rbp+3Fh+var_80], xmm0
0x1800076d1  lea     r8, [rbp+3Fh+Buf1]; pv
0x1800076d5  mov     edx, r13d; c
0x1800076d8  mov     rcx, rax; h
0x1800076db  call    cs:__imp_GetObjectW
0x1800076e1  test    eax, eax
0x1800076e3  jz      short loc_18000775D
0x1800076e5  mov     r11, qword ptr [rbp+3Fh+var_80+8]
0x1800076e9  test    r11, r11
0x1800076ec  jz      short loc_18000775D
0x1800076ee  cmp     r13w, word ptr [rbp+3Fh+var_80+2]
0x1800076f3  jnz     short loc_18000775D
0x1800076f5  mov     r9d, dword ptr [rbp+3Fh+arg_20]
0x1800076f9  mov     ebx, dword ptr [rbp+3Fh+Buf1+8]
0x1800076fc  mov     r8d, ebx
0x1800076ff  mov     eax, dword ptr [rbp+3Fh+Buf1+4]
0x180007702  imul    r8d, eax
0x180007706  mov     ecx, r12d
0x180007709  test    r8d, r8d
0x18000770c  jle     short loc_18000772C
0x18000770e  mov     r10d, [rbp+3Fh+arg_28]
0x180007712  mov     edx, ecx
0x180007714  cmp     [r11+rdx*4+2], r9b
0x180007719  jz      loc_180007856
0x18000771f  inc     ecx
0x180007721  cmp     ecx, r8d
0x180007724  jl      short loc_180007712
0x180007726  mov     ebx, dword ptr [rbp+3Fh+Buf1+8]
0x180007729  mov     eax, dword ptr [rbp+3Fh+Buf1+4]
0x18000772c  imul    ebx, eax
0x18000772f  mov     r9d, r12d
0x180007732  test    ebx, ebx
0x180007734  jle     short loc_18000775D
0x180007736  nop     word ptr [rax+rax+00000000h]
0x180007740  mov     r10d, r9d
0x180007743  movzx   eax, byte ptr [r11+r10*4+3]
0x180007749  test    al, al
0x18000774b  jnz     loc_1800077F9
0x180007751  mov     [r11+r10*4], r12d
0x180007755  inc     r9d
0x180007758  cmp     r9d, ebx
0x18000775b  jl      short loc_180007740
0x18000775d  test    r14, r14
  ... truncated ...
```
