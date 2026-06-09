# Windows::UI::Input::Inking::CInkStroke::PutInkStrokeDispDrawingAttributes(IInkStrokeDisp *,Windows::UI::Input::Inking::IInkDrawingAttributes *)

- ea: `0x180053e64`
- end: `0x1800545d5`
- name: `?PutInkStrokeDispDrawingAttributes@CInkStroke@Inking@Input@UI@Windows@@AEAAJPEAUIInkStrokeDisp@@PEAUIInkDrawingAttributes@2345@@Z`
- size: `1905`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::CInkStroke *__hidden this, struct IInkStrokeDisp *, struct IInkDrawingAttributes *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18004ccc0`

## callees

- `0x1800062a0`
- `0x1800101bc`
- `0x180019248`
- `0x18001ff5c`
- `0x18001ffac`
- `0x180048440`
- `0x18004a018`
- `0x180053e64`
- `0x180056724`
- `0x180058200`
- `0x1800fb010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005420d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005420d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180054165`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180054165`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800541bf`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800541bf`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180054148`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180054148`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::UI::Input::Inking::CInkStroke::PutInkStrokeDispDrawingAttributes(
        Windows::UI::Input::Inking::CInkStroke *this,
        struct IInkStrokeDisp *a2,
        struct IInkDrawingAttributes *a3)
{
  HRESULT (__stdcall *get_DrawingAttributes)(IInkStrokeDisp *, IInkDrawingAttributes **); // rbx
  HRESULT v6; // ebx
  unsigned __int16 v7; // si
  __int64 v8; // rdx
  const struct Windows::Foundation::Numerics::float3x2 *v9; // rdx
  struct IInkDrawingAttributes *v10; // r9
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v12; // rdi
  struct IInkDrawingAttributes *v13; // r9
  char v14; // al
  struct IInkDrawingAttributes *v15; // r9
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  struct IInkDrawingAttributes *v18; // r9
  struct IInkDrawingAttributes *v19; // r9
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rbx
  struct IInkDrawingAttributes *v22; // r9
  struct IInkDrawingAttributes *v23; // r9
  char v25; // [rsp+20h] [rbp-99h] BYREF
  char v26; // [rsp+21h] [rbp-98h] BYREF
  char v27; // [rsp+22h] [rbp-97h] BYREF
  char v28[5]; // [rsp+23h] [rbp-96h] BYREF
  unsigned __int16 *v29; // [rsp+28h] [rbp-91h] BYREF
  int v30; // [rsp+30h] [rbp-89h] BYREF
  __m128i v31; // [rsp+40h] [rbp-79h] BYREF
  __int64 v32; // [rsp+50h] [rbp-69h]
  void *ppvData; // [rsp+60h] [rbp-59h] BYREF
  struct IInkDrawingAttributes *v34; // [rsp+68h] [rbp-51h] BYREF
  __int64 v35; // [rsp+70h] [rbp-49h] BYREF
  int v36; // [rsp+78h] [rbp-41h] BYREF
  __int32 v37; // [rsp+7Ch] [rbp-3Dh] BYREF
  __int64 v38; // [rsp+80h] [rbp-39h] BYREF
  __int64 v39; // [rsp+88h] [rbp-31h] BYREF
  __int64 v40; // [rsp+90h] [rbp-29h] BYREF
  __int64 v41; // [rsp+98h] [rbp-21h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-9h] BYREF
  __m128i si128; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v46; // [rsp+C8h] [rbp+Fh]

  v29 = 0;
  get_DrawingAttributes = a2->lpVtbl->get_DrawingAttributes;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  v6 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, unsigned __int16 **))get_DrawingAttributes)(a2, &v29);
  if ( v6 < 0 )
    goto LABEL_64;
  v7 = -1;
  v6 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64))(*(_QWORD *)v29 + 144LL))(v29, 0xFFFFFFFFLL);
  v30 = 0;
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(struct IInkDrawingAttributes *, int *))a3->lpVtbl->Invoke)(a3, &v30);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD))(*(_QWORD *)v29 + 64LL))(
             v29,
             BYTE1(v30) | (HIBYTE(v30) << 16) | (BYTE2(v30) << 8));
      if ( v6 >= 0 )
        v6 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD))(*(_QWORD *)v29 + 160LL))(
               v29,
               255 - (unsigned int)(unsigned __int8)v30);
    }
  }
  v36 = 0;
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(struct IInkDrawingAttributes *, int *))a3->lpVtbl->put_Color)(a3, &v36);
    if ( v6 >= 0 )
      v6 = (*(__int64 (__fastcall **)(unsigned __int16 *, bool))(*(_QWORD *)v29 + 192LL))(v29, v36 != 0);
  }
  v39 = 0;
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(struct IInkDrawingAttributes *, __int64 *))a3->lpVtbl->put_Width)(a3, &v39);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v29 + 80LL))(v29);
      if ( v6 >= 0 )
        v6 = (*(__int64 (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v29 + 96LL))(v29);
    }
  }
  v26 = 0;
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(struct IInkDrawingAttributes *, char *))a3->lpVtbl->put_Height)(a3, &v26);
    if ( v6 >= 0 )
    {
      v8 = 0xFFFFFFFFLL;
      if ( !v26 )
        v8 = 0;
      v6 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64))(*(_QWORD *)v29 + 128LL))(v29, v8);
    }
  }
  v27 = 1;
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(struct IInkDrawingAttributes *, char *))a3->lpVtbl->put_FitToCurve)(a3, &v27);
    if ( v6 >= 0 )
    {
      if ( !v27 )
        v7 = 0;
      v6 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD))(*(_QWORD *)v29 + 112LL))(v29, v7);
    }
  }
  v34 = a3;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(&v34);
  v42 = 0;
  v25 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v46 = 0;
  if ( v6 >= 0 )
  {
    if ( (int)Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::IInkDrawingAttributes>::As<Windows::UI::Input::Inking::IInkDrawingAttributes2>(
                &v34,
                &v42) < 0 )
    {
      v6 = 0;
    }
    else
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __m128i *))(*(_QWORD *)v42 + 48LL))(v42, &si128);
      if ( v6 < 0 )
        goto LABEL_40;
      v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v42 + 64LL))(v42, &v25);
    }
    if ( v6 >= 0 )
    {
      v31 = si128;
      v32 = v46;
      if ( Windows::Foundation::Numerics::is_identity((Windows::Foundation::Numerics *)&v31, v9) )
      {
LABEL_36:
        v14 = v25;
        if ( v25 )
        {
          v6 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64))(*(_QWORD *)v29 + 176LL))(v29, 9);
          v14 = v25;
        }
        if ( v6 >= 0 )
        {
          v31 = 0;
          v31.m128i_i16[0] = 17;
          v31.m128i_i8[8] = v14 != 0;
          v32 = 0;
          v6 = Windows::UI::Input::Inking::PutInkDrawingAttributesExtendedProperty(
                 (Windows::UI::Input::Inking *)&v31,
                 (struct tagVARIANT *)&stru_180117280,
                 v29,
                 v10);
        }
        goto LABEL_40;
      }
      Vector = SafeArrayCreateVector(4u, 0, 6u);
      v12 = Vector;
      if ( !Vector )
      {
        v6 = -2147024882;
        goto LABEL_40;
      }
      ppvData = 0;
      v6 = SafeArrayAccessData(Vector, &ppvData);
      if ( v6 < 0 )
      {
        SafeArrayDestroy(v12);
      }
      else
      {
        *(__m128i *)ppvData = si128;
        *((_DWORD *)ppvData + 5) = 0;
        *((_DWORD *)ppvData + 4) = 0;
        v6 = SafeArrayUnaccessData(v12);
        if ( v6 < 0 )
          goto LABEL_40;
        v31.m128i_i64[0] = 8196;
        v31.m128i_i64[1] = (__int64)v12;
        v32 = 0;
        v6 = Windows::UI::Input::Inking::PutInkDrawingAttributesExtendedProperty(
               (Windows::UI::Input::Inking *)&v31,
               (struct tagVARIANT *)&stru_180117230,
               v29,
               v13);
      }
      if ( v6 >= 0 )
        goto LABEL_36;
    }
  }
LABEL_40:
  v41 = 0;
  v37 = 0;
  v40 = 0;
  if ( v6 >= 0 )
  {
    if ( (int)Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::IInkDrawingAttributes>::As<Windows::UI::Input::Inking::IInkDrawingAttributes3>(
                &v34,
                &v41) < 0 )
    {
      v6 = 0;
    }
    else
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int32 *))(*(_QWORD *)v41 + 48LL))(v41, &v37);
      if ( v6 >= 0 )
      {
        v31 = 0;
        v31.m128i_i16[0] = 19;
        v31.m128i_i32[2] = v37;
        v32 = 0;
        v6 = Windows::UI::Input::Inking::PutInkDrawingAttributesExtendedProperty(
               (Windows::UI::Input::Inking *)&v31,
               (struct tagVARIANT *)&stru_180117320,
               v29,
               v15);
        if ( v6 >= 0 )
        {
          v16 = v41;
          v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 56LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
          v6 = v17(v16, &v40);
          if ( v6 >= 0 )
          {
            if ( v40 )
            {
              v35 = 0;
              v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 48LL))(v40, &v35);
              if ( v6 >= 0 )
              {
                v31.m128i_i64[0] = 5;
                v31.m128i_i64[1] = v35;
                v32 = 0;
                v6 = Windows::UI::Input::Inking::PutInkDrawingAttributesExtendedProperty(
                       (Windows::UI::Input::Inking *)&v31,
                       (struct tagVARIANT *)&stru_1801172D0,
                       v29,
                       v18);
              }
            }
          }
        }
      }
    }
  }
  v43 = 0;
  v28[0] = 1;
  if ( v6 >= 0 )
  {
    if ( (int)Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::IInkDrawingAttributes>::As<Windows::UI::Input::Inking::IInkDrawingAttributes4>(
                &v34,
                &v43) < 0
      || (v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v43 + 48LL))(v43, v28), v6 >= 0)
      && (v31 = 0,
          v31.m128i_i16[0] = 17,
          v31.m128i_i8[8] = v28[0] != 0,
          v32 = 0,
          v6 = Windows::UI::Input::Inking::PutInkDrawingAttributesExtendedProperty(
                 (Windows::UI::Input::Inking *)&v31,
                 (struct tagVARIANT *)&stru_1801173C0,
                 v29,
                 v19),
          v6 >= 0) )
    {
      v35 = 0;
      v6 = Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::IInkDrawingAttributes>::As<Windows::UI::Input::Inking::IInkDrawingAttributes5>(
             &v34,
             &v35);
      if ( v6 >= 0 )
      {
        v38 = 0;
        v20 = v35;
        v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
        v6 = v21(v20, &v38);
        if ( v6 >= 0 )
        {
          LODWORD(ppvData) = 0;
          v6 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v38 + 64LL))(v38, &ppvData);
          if ( v6 >= 0 )
          {
            v44 = 0;
            v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 48LL))(v38, &v44);
            if ( v6 >= 0 )
            {
              v31 = 0;
              v31.m128i_i16[0] = 4;
              v31.m128i_i32[2] = (int)ppvData;
              v32 = 0;
              v6 = Windows::UI::Input::Inking::PutInkDrawingAttributesExtendedProperty(
                     (Windows::UI::Input::Inking *)&v31,
                     (struct tagVARIANT *)&stru_180117370,
                     v29,
                     v22);
              if ( v6 >= 0 )
              {
                v31 = 0;
                v31.m128i_i16[0] = 19;
                v31.m128i_i32[2] = (int)v44 / 10;
                v32 = 0;
                v6 = Windows::UI::Input::Inking::PutInkDrawingAttributesExtendedProperty(
                       (Windows::UI::Input::Inking *)&v31,
                       (struct tagVARIANT *)&stru_180117410,
                       v29,
                       v23);
              }
            }
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      if ( v6 >= 0 )
        v6 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, unsigned __int16 *))a2->lpVtbl->putref_DrawingAttributes)(
               a2,
               v29);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
LABEL_64:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180053e64  mov     [rsp-8+arg_0], rbx
0x180053e69  push    rbp
0x180053e6a  push    rsi
0x180053e6b  push    rdi
0x180053e6c  push    r12
0x180053e6e  push    r13
0x180053e70  push    r14
0x180053e72  push    r15
0x180053e74  lea     rbp, [rsp-27h]
0x180053e79  sub     rsp, 0E0h
0x180053e80  mov     rax, cs:__security_cookie
0x180053e87  xor     rax, rsp
0x180053e8a  mov     [rbp+57h+var_40], rax
0x180053e8e  mov     rdi, r8
0x180053e91  mov     r14, rdx
0x180053e94  xor     r15d, r15d
0x180053e97  mov     [rsp+110h+var_E8], r15
0x180053e9c  mov     rax, [rdx]
0x180053e9f  mov     rbx, [rax+48h]
0x180053ea3  lea     rcx, [rsp+110h+var_E8]
0x180053ea8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180053ead  lea     rdx, [rsp+110h+var_E8]
0x180053eb2  mov     rcx, r14
0x180053eb5  mov     rax, rbx
0x180053eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ebd  mov     ebx, eax
0x180053ebf  test    eax, eax
0x180053ec1  js      loc_1800545A2
0x180053ec7  mov     rcx, [rsp+110h+var_E8]
0x180053ecc  mov     rax, [rcx]
0x180053ecf  or      esi, 0FFFFFFFFh
0x180053ed2  mov     edx, esi
0x180053ed4  mov     rax, [rax+90h]
0x180053edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ee0  mov     ebx, eax
0x180053ee2  mov     [rsp+110h+var_E0], r15d
0x180053ee7  test    eax, eax
0x180053ee9  js      short loc_180053F5A
0x180053eeb  mov     rax, [rdi]
0x180053eee  lea     rdx, [rsp+110h+var_E0]
0x180053ef3  mov     rcx, rdi
0x180053ef6  mov     rax, [rax+30h]
0x180053efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053eff  mov     ebx, eax
0x180053f01  test    eax, eax
0x180053f03  js      short loc_180053F5A
0x180053f05  mov     rcx, [rsp+110h+var_E8]
0x180053f0a  mov     r8, [rcx]
0x180053f0d  movzx   edx, byte ptr [rsp+110h+var_E0+2]
0x180053f12  shl     edx, 8
0x180053f15  movzx   eax, byte ptr [rsp+110h+var_E0+3]
0x180053f1a  shl     eax, 10h
0x180053f1d  or      edx, eax
0x180053f1f  movzx   eax, byte ptr [rsp+110h+var_E0+1]
0x180053f24  or      edx, eax
0x180053f26  mov     rax, [r8+40h]
0x180053f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f2f  mov     ebx, eax
0x180053f31  test    eax, eax
0x180053f33  js      short loc_180053F5A
0x180053f35  mov     r8, [rsp+110h+var_E8]
0x180053f3a  mov     rcx, [r8]
0x180053f3d  movzx   eax, byte ptr [rsp+110h+var_E0]
0x180053f42  mov     edx, 0FFh
0x180053f47  sub     edx, eax
0x180053f49  mov     rax, [rcx+0A0h]
0x180053f50  mov     rcx, r8
0x180053f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f58  mov     ebx, eax
0x180053f5a  mov     [rbp+57h+var_98], r15d
0x180053f5e  test    ebx, ebx
0x180053f60  js      short loc_180053F9B
0x180053f62  mov     rax, [rdi]
0x180053f65  lea     rdx, [rbp+57h+var_98]
0x180053f69  mov     rcx, rdi
0x180053f6c  mov     rax, [rax+40h]
0x180053f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f75  mov     ebx, eax
0x180053f77  test    eax, eax
0x180053f79  js      short loc_180053F9B
0x180053f7b  mov     rcx, [rsp+110h+var_E8]
0x180053f80  mov     rax, [rcx]
0x180053f83  mov     edx, r15d
0x180053f86  cmp     [rbp+57h+var_98], r15d
0x180053f8a  setnz   dl
0x180053f8d  mov     rax, [rax+0C0h]
0x180053f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f99  mov     ebx, eax
0x180053f9b  mov     [rbp+57h+var_88], 0
0x180053fa3  test    ebx, ebx
0x180053fa5  js      short loc_180054004
0x180053fa7  mov     rax, [rdi]
0x180053faa  lea     rdx, [rbp+57h+var_88]
0x180053fae  mov     rcx, rdi
0x180053fb1  mov     rax, [rax+50h]
0x180053fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fba  mov     ebx, eax
0x180053fbc  test    eax, eax
0x180053fbe  js      short loc_180054004
0x180053fc0  mov     rcx, [rsp+110h+var_E8]
0x180053fc5  mov     rax, [rcx]
0x180053fc8  movss   xmm1, dword ptr [rbp+57h+var_88]
0x180053fcd  mulss   xmm1, cs:__real@41d00000
0x180053fd5  mov     rax, [rax+50h]
0x180053fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fde  mov     ebx, eax
0x180053fe0  test    eax, eax
0x180053fe2  js      short loc_180054004
0x180053fe4  mov     rcx, [rsp+110h+var_E8]
0x180053fe9  mov     rax, [rcx]
0x180053fec  movss   xmm1, dword ptr [rbp+57h+var_88+4]
0x180053ff1  mulss   xmm1, cs:__real@41d00000
0x180053ff9  mov     rax, [rax+60h]
0x180053ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054002  mov     ebx, eax
0x180054004  mov     [rsp+110h+var_EF], r15b
0x180054009  test    ebx, ebx
0x18005400b  js      short loc_180054049
0x18005400d  mov     rax, [rdi]
0x180054010  lea     rdx, [rsp+110h+var_EF]
0x180054015  mov     rcx, rdi
0x180054018  mov     rax, [rax+60h]
0x18005401c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054021  mov     ebx, eax
0x180054023  test    eax, eax
0x180054025  js      short loc_180054049
0x180054027  mov     rcx, [rsp+110h+var_E8]
0x18005402c  mov     rax, [rcx]
0x18005402f  cmp     [rsp+110h+var_EF], r15b
0x180054034  mov     edx, esi
0x180054036  jnz     short loc_18005403B
0x180054038  mov     edx, r15d
0x18005403b  mov     rax, [rax+80h]
0x180054042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054047  mov     ebx, eax
0x180054049  mov     [rsp+110h+var_EE], 1
0x18005404e  test    ebx, ebx
0x180054050  js      short loc_18005408C
0x180054052  mov     rax, [rdi]
0x180054055  lea     rdx, [rsp+110h+var_EE]
0x18005405a  mov     rcx, rdi
0x18005405d  mov     rax, [rax+70h]
0x180054061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054066  mov     ebx, eax
0x180054068  test    eax, eax
0x18005406a  js      short loc_18005408C
0x18005406c  mov     rcx, [rsp+110h+var_E8]
0x180054071  mov     rax, [rcx]
0x180054074  cmp     [rsp+110h+var_EE], r15b
0x180054079  jnz     short loc_18005407E
0x18005407b  mov     esi, r15d
0x18005407e  movzx   edx, si
0x180054081  mov     rax, [rax+70h]
0x180054085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005408a  mov     ebx, eax
0x18005408c  mov     [rbp+57h+var_A8], rdi
0x180054090  lea     rcx, [rbp+57h+var_A8]
0x180054094  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAVInkStroke@Inking@Input@UI@Windows@@UEventRegistrationToken@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(void)
0x180054099  nop
0x18005409a  mov     [rbp+57h+var_70], r15
0x18005409e  mov     [rsp+110h+var_F0], r15b
0x1800540a3  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x1800540ab  movups  [rbp+57h+var_58], xmm0
0x1800540af  mov     [rbp+57h+var_48], 0
0x1800540b7  mov     r13d, 11h
0x1800540bd  lea     r12d, [r13-0Dh]
0x1800540c1  test    ebx, ebx
0x1800540c3  js      loc_180054279
0x1800540c9  lea     rdx, [rbp+57h+var_70]
0x1800540cd  lea     rcx, [rbp+57h+var_A8]
0x1800540d1  call    ??$As@UIInkDrawingAttributes2@Inking@Input@UI@Windows@@@?$ComPtr@UIInkDrawingAttributes@Inking@Input@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInkDrawingAttributes2@Inking@Input@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::IInkDrawingAttributes>::As<Windows::UI::Input::Inking::IInkDrawingAttributes2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::IInkDrawingAttributes2>>)
0x1800540d6  test    eax, eax
0x1800540d8  js      short loc_180054111
0x1800540da  mov     rcx, [rbp+57h+var_70]
0x1800540de  mov     rax, [rcx]
0x1800540e1  lea     rdx, [rbp+57h+var_58]
0x1800540e5  mov     rax, [rax+30h]
0x1800540e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540ee  mov     ebx, eax
0x1800540f0  test    eax, eax
0x1800540f2  js      loc_180054279
0x1800540f8  mov     rcx, [rbp+57h+var_70]
0x1800540fc  mov     rax, [rcx]
0x1800540ff  lea     rdx, [rsp+110h+var_F0]
0x180054104  mov     rax, [rax+40h]
0x180054108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005410d  mov     ebx, eax
0x18005410f  jmp     short loc_180054114
0x180054111  mov     ebx, r15d
0x180054114  test    ebx, ebx
0x180054116  js      loc_180054279
0x18005411c  movups  xmm0, [rbp+57h+var_58]
0x180054120  movups  [rbp+57h+var_D0], xmm0
0x180054124  movsd   xmm1, [rbp+57h+var_48]
0x180054129  movsd   [rbp+57h+var_C0], xmm1
0x18005412e  lea     rcx, [rbp+57h+var_D0]; this
0x180054132  call    ?is_identity@Numerics@Foundation@Windows@@YA_NAEBUfloat3x2@123@@Z; Windows::Foundation::Numerics::is_identity(Windows::Foundation::Numerics::float3x2 const &)
0x180054137  test    al, al
0x180054139  jnz     loc_180054217
0x18005413f  mov     ecx, r12d; vt
0x180054142  xor     edx, edx; lLbound
0x180054144  lea     r8d, [rdx+6]; cElements
0x180054148  call    cs:__imp_SafeArrayCreateVector
0x18005414e  mov     rdi, rax
0x180054151  test    rax, rax
0x180054154  jz      loc_180054392
0x18005415a  mov     [rbp+57h+ppvData], r15
0x18005415e  lea     rdx, [rbp+57h+ppvData]; ppvData
0x180054162  mov     rcx, rax; psa
0x180054165  call    cs:__imp_SafeArrayAccessData
0x18005416b  mov     ebx, eax
0x18005416d  test    eax, eax
0x18005416f  js      loc_18005420A
0x180054175  mov     rcx, [rbp+57h+ppvData]
0x180054179  movss   xmm0, dword ptr [rbp+57h+var_58]
0x18005417e  movss   dword ptr [rcx], xmm0
0x180054182  mov     rax, [rbp+57h+ppvData]
0x180054186  movss   xmm1, dword ptr [rbp+57h+var_58+4]
0x18005418b  movss   dword ptr [rax+4], xmm1
0x180054190  mov     rax, [rbp+57h+ppvData]
0x180054194  movss   xmm0, dword ptr [rbp+57h+var_58+8]
0x180054199  movss   dword ptr [rax+8], xmm0
0x18005419e  mov     rax, [rbp+57h+ppvData]
0x1800541a2  movss   xmm1, dword ptr [rbp+57h+var_58+0Ch]
0x1800541a7  movss   dword ptr [rax+0Ch], xmm1
0x1800541ac  mov     rax, [rbp+57h+ppvData]
0x1800541b0  mov     [rax+14h], r15d
0x1800541b4  mov     rax, [rbp+57h+ppvData]
0x1800541b8  mov     [rax+10h], r15d
0x1800541bc  mov     rcx, rdi; psa
0x1800541bf  call    cs:__imp_SafeArrayUnaccessData
0x1800541c5  mov     ebx, eax
0x1800541c7  test    eax, eax
0x1800541c9  js      loc_180054279
0x1800541cf  xorps   xmm0, xmm0
0x1800541d2  xor     ecx, ecx
0x1800541d4  movups  [rbp+57h+var_D0], xmm0
0x1800541d8  mov     eax, 2004h
0x1800541dd  mov     word ptr [rbp+57h+var_D0], ax
0x1800541e1  mov     qword ptr [rbp+57h+var_D0+8], rdi
0x1800541e5  movups  xmm0, [rbp+57h+var_D0]
0x1800541e9  movaps  [rbp+57h+var_D0], xmm0
0x1800541ed  mov     [rbp+57h+var_C0], rcx
0x1800541f1  mov     r8, [rsp+110h+var_E8]; unsigned __int16 *
0x1800541f6  lea     rdx, stru_180117230; struct tagVARIANT
0x1800541fd  lea     rcx, [rbp+57h+var_D0]; this
0x180054201  call    ?PutInkDrawingAttributesExtendedProperty@Inking@Input@UI@Windows@@YAJUtagVARIANT@@PEAGPEAUIInkDrawingAttributes@@@Z; Windows::UI::Input::Inking::PutInkDrawingAttributesExtendedProperty(tagVARIANT,ushort *,IInkDrawingAttributes *)
0x180054206  mov     ebx, eax
0x180054208  jmp     short loc_180054213
0x18005420a  mov     rcx, rdi; psa
0x18005420d  call    cs:__imp_SafeArrayDestroy
0x180054213  test    ebx, ebx
0x180054215  js      short loc_180054279
0x180054217  mov     al, [rsp+110h+var_F0]
0x18005421b  test    al, al
0x18005421d  jz      short loc_18005423E
0x18005421f  mov     rcx, [rsp+110h+var_E8]
0x180054224  mov     rax, [rcx]
0x180054227  mov     edx, 9
0x18005422c  mov     rax, [rax+0B0h]
0x180054233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054238  mov     ebx, eax
0x18005423a  mov     al, [rsp+110h+var_F0]
0x18005423e  test    ebx, ebx
0x180054240  js      short loc_180054279
0x180054242  xorps   xmm0, xmm0
0x180054245  xor     ecx, ecx
0x180054247  movups  [rbp+57h+var_D0], xmm0
0x18005424b  mov     word ptr [rbp+57h+var_D0], r13w
0x180054250  test    al, al
0x180054252  setnz   byte ptr [rbp+57h+var_D0+8]
0x180054256  movups  xmm0, [rbp+57h+var_D0]
0x18005425a  movaps  [rbp+57h+var_D0], xmm0
0x18005425e  mov     [rbp+57h+var_C0], rcx
0x180054262  mov     r8, [rsp+110h+var_E8]; unsigned __int16 *
0x180054267  lea     rdx, stru_180117280; struct tagVARIANT
0x18005426e  lea     rcx, [rbp+57h+var_D0]; this
0x180054272  call    ?PutInkDrawingAttributesExtendedProperty@Inking@Input@UI@Windows@@YAJUtagVARIANT@@PEAGPEAUIInkDrawingAttributes@@@Z; Windows::UI::Input::Inking::PutInkDrawingAttributesExtendedProperty(tagVARIANT,ushort *,IInkDrawingAttributes *)
0x180054277  mov     ebx, eax
0x180054279  mov     [rbp+57h+var_78], r15
0x18005427d  mov     [rbp+57h+var_94], r15d
0x180054281  mov     [rbp+57h+var_80], r15
0x180054285  mov     esi, 13h
0x18005428a  test    ebx, ebx
0x18005428c  js      loc_18005439F
0x180054292  lea     rdx, [rbp+57h+var_78]
0x180054296  lea     rcx, [rbp+57h+var_A8]
0x18005429a  call    ??$As@UIInkDrawingAttributes3@Inking@Input@UI@Windows@@@?$ComPtr@UIInkDrawingAttributes@Inking@Input@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInkDrawingAttributes3@Inking@Input@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::IInkDrawingAttributes>::As<Windows::UI::Input::Inking::IInkDrawingAttributes3>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::IInkDrawingAttributes3>>)
0x18005429f  test    eax, eax
0x1800542a1  js      loc_18005439C
0x1800542a7  mov     rcx, [rbp+57h+var_78]
0x1800542ab  mov     rax, [rcx]
0x1800542ae  lea     rdx, [rbp+57h+var_94]
0x1800542b2  mov     rax, [rax+30h]
0x1800542b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800542bb  mov     ebx, eax
0x1800542bd  test    eax, eax
0x1800542bf  js      loc_18005439F
0x1800542c5  xorps   xmm0, xmm0
0x1800542c8  xor     ecx, ecx
  ... truncated ...
```
