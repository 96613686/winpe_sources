# CMetadataContainer::Initialize(IStream *,ulong,IWICBitmapDecoder *)

- ea: `0x180005360`
- end: `0x180005958`
- name: `?Initialize@CMetadataContainer@@QEAAJPEAUIStream@@KPEAUIWICBitmapDecoder@@@Z`
- size: `1528`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this, struct IStream *, unsigned int, struct IWICBitmapDecoder *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004f80`

## callees

- `0x180005360`
- `0x180005b48`
- `0x180016020`
- `0x1800169b8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005580`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005903`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005580`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005903`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005474`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005474`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMetadataContainer::Initialize(
        CMetadataContainer *this,
        struct IStream *a2,
        int a3,
        struct IWICBitmapDecoder *a4)
{
  struct IWICBitmapDecoder **v8; // r15
  unsigned int v9; // r12d
  HRESULT v10; // edi
  double v11; // r14
  LPVOID v12; // r13
  bool v13; // al
  __int64 v14; // r8
  double v15; // rbx
  int v16; // eax
  double v17; // xmm1_8
  double v18; // xmm3_8
  double v19; // xmm2_8
  double v20; // xmm4_8
  void (__fastcall *v22)(_QWORD); // rax
  void (__fastcall *v23)(_QWORD); // rax
  double v24; // rdx
  double v25; // [rsp+30h] [rbp-89h] BYREF
  double v26; // [rsp+38h] [rbp-81h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-79h] BYREF
  double v28; // [rsp+48h] [rbp-71h]
  double v29; // [rsp+50h] [rbp-69h] BYREF
  PROPVARIANT pvar; // [rsp+58h] [rbp-61h] BYREF
  _BYTE v31[16]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v32; // [rsp+80h] [rbp-39h]

  if ( *(_QWORD *)this || *((_BYTE *)this + 28) )
    return 2147943647LL;
  if ( !a2 )
    return 2147500035LL;
  ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
  if ( *(_QWORD *)this )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
  *(_QWORD *)this = a2;
  *((_DWORD *)this + 6) = a3;
  v8 = (struct IWICBitmapDecoder **)((char *)this + 8);
  if ( *((struct IWICBitmapDecoder **)this + 1) != a4 )
  {
    if ( a4 )
      ((void (__fastcall *)(struct IWICBitmapDecoder *))a4->lpVtbl->AddRef)(a4);
    if ( *v8 )
      ((void (__fastcall *)(struct IWICBitmapDecoder *))(*v8)->lpVtbl->Release)(*v8);
    *v8 = a4;
  }
  memset_0(v31, 0, 0x50u);
  v9 = 1;
  if ( ((int (__fastcall *)(struct IStream *, _BYTE *, __int64))a2->lpVtbl->Stat)(a2, v31, 1) >= 0 && v32 )
    *((_QWORD *)this + 9) = v32;
  if ( !*((_QWORD *)this + 9) )
  {
    v26 = 0.0;
    v25 = 0.0;
    if ( ((int (__fastcall *)(struct IStream *, _QWORD, __int64, double *))a2->lpVtbl->Seek)(a2, 0, 1, &v25) < 0 )
      v25 = 0.0;
    if ( ((int (__fastcall *)(struct IStream *, _QWORD, __int64, char *))a2->lpVtbl->Seek)(a2, 0, 2, (char *)this + 72) >= 0 )
    {
      v24 = v25;
      if ( *(_QWORD *)&v25 > 0x7FFFFFFFFFFFFFFFuLL )
        v24 = 0.0;
      ((void (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Seek)(a2, *(_QWORD *)&v24, 0, 0);
    }
  }
  ppv = 0;
  v10 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv);
  if ( v10 >= 0 )
    v10 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, char *))ppv)(ppv, &IID_IWICComponentFactory, (char *)this + 16);
  if ( !*v8 )
  {
    v26 = 0.0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)this + 40LL))(
            *(_QWORD *)this,
            0,
            0,
            0);
    if ( v10 >= 0 )
      v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, char *))(*(_QWORD *)ppv + 32LL))(
              ppv,
              *(_QWORD *)this,
              0,
              0,
              (char *)this + 8);
  }
  if ( !*v8 )
  {
    if ( v10 >= 0 )
      v10 = -2147418113;
    goto LABEL_49;
  }
  v10 = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, char *))(*v8)->lpVtbl->GetContainerFormat)(
          *v8,
          (char *)this + 80);
  if ( v10 >= 0 )
  {
    v29 = 0.0;
    v10 = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, _QWORD, double *))(*v8)->lpVtbl->GetFrame)(*v8, 0, &v29);
    v11 = v29;
    if ( v10 < 0 || v29 == 0.0 )
    {
LABEL_45:
      if ( v11 != 0.0 )
        (*(void (__fastcall **)(double))(**(_QWORD **)&v11 + 16LL))(COERCE_DOUBLE(*(_QWORD *)&v11));
      if ( v10 >= 0 )
        *((_BYTE *)this + 28) = 1;
      goto LABEL_49;
    }
    v12 = ppv;
    v28 = 0.0;
    v13 = WICIsOrientationSupported(*v8);
    v14 = **(_QWORD **)&v11;
    if ( !v13 )
    {
      v22 = *(void (__fastcall **)(_QWORD))(v14 + 8);
      v15 = v11;
      v28 = v11;
      v22(*(_QWORD *)&v11);
      goto LABEL_32;
    }
    v26 = 0.0;
    if ( (*(int (__fastcall **)(double, double *))(v14 + 64))(COERCE_DOUBLE(*(_QWORD *)&v11), &v26) < 0 )
    {
      v23 = *(void (__fastcall **)(_QWORD))(**(_QWORD **)&v11 + 8LL);
      v15 = v11;
      v28 = v11;
      v23(*(_QWORD *)&v11);
      goto LABEL_32;
    }
    v15 = 0.0;
    v28 = 0.0;
    memset(&pvar, 0, sizeof(pvar));
    v16 = (*(__int64 (__fastcall **)(double, const wchar_t *, PROPVARIANT *))(**(_QWORD **)&v26 + 40LL))(
            COERCE_DOUBLE(*(_QWORD *)&v26),
            L"System.Photo.Orientation",
            &pvar);
    v10 = v16;
    if ( v16 == -2003292352 || pvar.vt != 18 )
    {
LABEL_26:
      v9 = 0;
    }
    else
    {
      if ( v16 < 0 )
      {
        PropVariantClear(&pvar);
        goto LABEL_31;
      }
      switch ( pvar.iVal )
      {
        case 2:
          v9 = 8;
          break;
        case 3:
          v9 = 2;
          break;
        case 4:
          v9 = 16;
          break;
        case 5:
          v9 = 17;
          break;
        case 6:
          break;
        case 7:
          v9 = 19;
          break;
        case 8:
          v9 = 3;
          break;
        default:
          goto LABEL_26;
      }
    }
    PropVariantClear(&pvar);
    v25 = 0.0;
    v10 = (*(__int64 (__fastcall **)(LPVOID, double *))(*(_QWORD *)v12 + 104LL))(v12, &v25);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(double, double, _QWORD))(**(_QWORD **)&v25 + 64LL))(
              COERCE_DOUBLE(*(_QWORD *)&v25),
              COERCE_DOUBLE(*(_QWORD *)&v11),
              v9);
      if ( v10 >= 0 )
      {
        v15 = v25;
        v28 = v25;
        (*(void (__fastcall **)(double))(**(_QWORD **)&v25 + 8LL))(COERCE_DOUBLE(*(_QWORD *)&v25));
      }
      (*(void (__fastcall **)(double))(**(_QWORD **)&v25 + 16LL))(COERCE_DOUBLE(*(_QWORD *)&v25));
    }
LABEL_31:
    (*(void (__fastcall **)(double))(**(_QWORD **)&v26 + 16LL))(COERCE_DOUBLE(*(_QWORD *)&v26));
    if ( v10 < 0 )
    {
LABEL_42:
      if ( v15 != 0.0 )
        (*(void (__fastcall **)(double))(**(_QWORD **)&v15 + 16LL))(COERCE_DOUBLE(*(_QWORD *)&v15));
      v11 = v29;
      goto LABEL_45;
    }
LABEL_32:
    v10 = (*(__int64 (__fastcall **)(double, char *, char *))(**(_QWORD **)&v15 + 24LL))(
            COERCE_DOUBLE(*(_QWORD *)&v15),
            (char *)this + 32,
            (char *)this + 36);
    if ( v10 >= 0 )
    {
      v25 = 0.0;
      v26 = 0.0;
      if ( (*(int (__fastcall **)(double, double *, double *))(**(_QWORD **)&v15 + 40LL))(
             COERCE_DOUBLE(*(_QWORD *)&v15),
             &v25,
             &v26) < 0 )
      {
        v17 = 0.0;
        v18 = 0.0;
      }
      else
      {
        v17 = v26;
        v18 = v25;
        if ( v25 <= 0.0 )
          v18 = fmax(v26, 0.0);
        if ( v26 <= 0.0 )
          v17 = fmax(v18, 0.0);
        v19 = fmin(v18, v17);
        if ( v19 > 0.0 )
        {
          v20 = fmax(v18, v17);
          if ( v20 / v19 > 4.0 )
          {
            v17 = v20;
            v18 = v20;
          }
        }
      }
      *((double *)this + 5) = v18;
      *((double *)this + 6) = v17;
      v10 = (*(__int64 (__fastcall **)(double, char *))(**(_QWORD **)&v15 + 32LL))(
              COERCE_DOUBLE(*(_QWORD *)&v15),
              (char *)this + 56);
    }
    goto LABEL_42;
  }
LABEL_49:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180005360  mov     [rsp-8+arg_10], rbx
0x180005365  push    rbp
0x180005366  push    rsi
0x180005367  push    rdi
0x180005368  push    r12
0x18000536a  push    r13
0x18000536c  push    r14
0x18000536e  push    r15
0x180005370  lea     rbp, [rsp-27h]
0x180005375  sub     rsp, 0E0h
0x18000537c  movaps  [rsp+110h+var_40], xmm6
0x180005384  mov     rax, cs:__security_cookie
0x18000538b  xor     rax, rsp
0x18000538e  mov     [rbp+57h+var_50], rax
0x180005392  mov     rbx, r9
0x180005395  mov     r14d, r8d
0x180005398  mov     rdi, rdx
0x18000539b  mov     rsi, rcx
0x18000539e  cmp     qword ptr [rcx], 0
0x1800053a2  jnz     loc_18000573B
0x1800053a8  cmp     byte ptr [rcx+1Ch], 0
0x1800053ac  jnz     loc_18000573B
0x1800053b2  test    rdx, rdx
0x1800053b5  jz      loc_1800057ED
0x1800053bb  mov     rax, [rdx]
0x1800053be  mov     rcx, rdx
0x1800053c1  mov     rax, [rax+8]
0x1800053c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053ca  mov     rcx, [rsi]
0x1800053cd  test    rcx, rcx
0x1800053d0  jnz     loc_180005799
0x1800053d6  mov     [rsi], rdi
0x1800053d9  mov     [rsi+18h], r14d
0x1800053dd  lea     r15, [rsi+8]
0x1800053e1  cmp     [r15], rbx
0x1800053e4  jz      short loc_180005409
0x1800053e6  test    rbx, rbx
0x1800053e9  jz      short loc_1800053FA
0x1800053eb  mov     rax, [rbx]
0x1800053ee  mov     rcx, rbx
0x1800053f1  mov     rax, [rax+8]
0x1800053f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053fa  mov     rcx, [r15]
0x1800053fd  test    rcx, rcx
0x180005400  jnz     loc_1800057AA
0x180005406  mov     [r15], rbx
0x180005409  xor     edx, edx; Val
0x18000540b  mov     r8d, 50h ; 'P'; Size
0x180005411  lea     rcx, [rbp+57h+var_A0]; void *
0x180005415  call    memset_0
0x18000541a  mov     rax, [rdi]
0x18000541d  mov     r12d, 1
0x180005423  mov     r8d, r12d
0x180005426  lea     rdx, [rbp+57h+var_A0]
0x18000542a  mov     rcx, rdi
0x18000542d  mov     rax, [rax+60h]
0x180005431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005436  test    eax, eax
0x180005438  js      short loc_180005447
0x18000543a  mov     rax, [rbp+57h+var_90]
0x18000543e  test    rax, rax
0x180005441  jz      short loc_180005447
0x180005443  mov     [rsi+48h], rax
0x180005447  xor     r13d, r13d
0x18000544a  cmp     [rsi+48h], r13
0x18000544e  jz      loc_1800057F7
0x180005454  mov     [rbp+57h+var_D0], r13
0x180005458  lea     rax, [rbp+57h+var_D0]
0x18000545c  mov     [rsp+110h+ppv], rax; ppv
0x180005461  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180005468  mov     r8d, r12d; dwClsContext
0x18000546b  xor     edx, edx; pUnkOuter
0x18000546d  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180005474  call    cs:__imp_CoCreateInstance
0x18000547a  mov     edi, eax
0x18000547c  test    eax, eax
0x18000547e  js      short loc_18000549C
0x180005480  mov     rcx, [rbp+57h+var_D0]
0x180005484  mov     rax, [rcx]
0x180005487  lea     r8, [rsi+10h]
0x18000548b  lea     rdx, IID_IWICComponentFactory
0x180005492  mov     rax, [rax]
0x180005495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000549a  mov     edi, eax
0x18000549c  cmp     qword ptr [r15], 0
0x1800054a0  jz      loc_18000587C
0x1800054a6  mov     rcx, [r15]
0x1800054a9  test    rcx, rcx
0x1800054ac  jz      loc_180005925
0x1800054b2  mov     rax, [rcx]
0x1800054b5  lea     rdx, [rsi+50h]
0x1800054b9  mov     rax, [rax+28h]
0x1800054bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054c2  mov     edi, eax
0x1800054c4  test    eax, eax
0x1800054c6  js      loc_1800056F4
0x1800054cc  mov     [rbp+57h+var_C0], r13
0x1800054d0  mov     rcx, [r15]
0x1800054d3  mov     rax, [rcx]
0x1800054d6  lea     r8, [rbp+57h+var_C0]
0x1800054da  xor     edx, edx
0x1800054dc  mov     rax, [rax+68h]
0x1800054e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054e5  mov     edi, eax
0x1800054e7  mov     r14, [rbp+57h+var_C0]
0x1800054eb  test    eax, eax
0x1800054ed  js      loc_1800056D7
0x1800054f3  test    r14, r14
0x1800054f6  jz      loc_1800056D7
0x1800054fc  mov     r13, [rbp+57h+var_D0]
0x180005500  mov     [rbp+57h+var_C8], 0
0x180005508  mov     rcx, [r15]; struct IWICBitmapDecoder *
0x18000550b  call    ?WICIsOrientationSupported@@YA_NPEAUIWICBitmapDecoder@@@Z; WICIsOrientationSupported(IWICBitmapDecoder *)
0x180005510  mov     r8, [r14]
0x180005513  mov     rcx, r14
0x180005516  test    al, al
0x180005518  jz      loc_180005779
0x18000551e  xor     r15d, r15d
0x180005521  mov     [rsp+110h+var_D8], r15
0x180005526  lea     rdx, [rsp+110h+var_D8]
0x18000552b  mov     rax, [r8+40h]
0x18000552f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005534  test    eax, eax
0x180005536  js      loc_1800057D2
0x18000553c  mov     rcx, [rsp+110h+var_D8]
0x180005541  mov     ebx, r15d
0x180005544  mov     [rbp+57h+var_C8], rbx
0x180005548  xorps   xmm0, xmm0
0x18000554b  xor     eax, eax
0x18000554d  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180005551  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180005555  mov     rax, [rcx]
0x180005558  lea     r8, [rbp+57h+pvar]
0x18000555c  lea     rdx, aSystemPhotoOri; "System.Photo.Orientation"
0x180005563  mov     rax, [rax+28h]
0x180005567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000556c  mov     edi, eax
0x18000556e  cmp     eax, 88982F40h
0x180005573  jnz     loc_180005742
0x180005579  mov     r12d, r15d; jumptable 0000000180005777 default case, case 1
0x18000557c  lea     rcx, [rbp+57h+pvar]; jumptable 0000000180005777 case 6
0x180005580  call    cs:__imp_PropVariantClear
0x180005586  mov     [rsp+110h+var_E0], r15
0x18000558b  mov     rax, [r13+0]
0x18000558f  lea     rdx, [rsp+110h+var_E0]
0x180005594  mov     rcx, r13
0x180005597  mov     rax, [rax+68h]
0x18000559b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a0  mov     edi, eax
0x1800055a2  test    eax, eax
0x1800055a4  js      short loc_1800055EC
0x1800055a6  mov     rcx, [rsp+110h+var_E0]
0x1800055ab  mov     rax, [rcx]
0x1800055ae  mov     r8d, r12d
0x1800055b1  mov     rdx, r14
0x1800055b4  mov     rax, [rax+40h]
0x1800055b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055bd  mov     edi, eax
0x1800055bf  test    eax, eax
0x1800055c1  js      short loc_1800055DB
0x1800055c3  mov     rbx, [rsp+110h+var_E0]
0x1800055c8  mov     [rbp+57h+var_C8], rbx
0x1800055cc  mov     rax, [rbx]
0x1800055cf  mov     rcx, rbx
0x1800055d2  mov     rax, [rax+8]
0x1800055d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055db  mov     rcx, [rsp+110h+var_E0]
0x1800055e0  mov     rax, [rcx]
0x1800055e3  mov     rax, [rax+10h]
0x1800055e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ec  mov     rcx, [rsp+110h+var_D8]
0x1800055f1  mov     rax, [rcx]
0x1800055f4  mov     rax, [rax+10h]
0x1800055f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055fd  test    edi, edi
0x1800055ff  js      loc_1800056BE
0x180005605  mov     rax, [rbx]
0x180005608  lea     r8, [rsi+24h]
0x18000560c  lea     rdx, [rsi+20h]
0x180005610  mov     rcx, rbx
0x180005613  mov     rax, [rax+18h]
0x180005617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000561c  mov     edi, eax
0x18000561e  test    eax, eax
0x180005620  js      loc_1800056BE
0x180005626  xorps   xmm6, xmm6
0x180005629  movsd   [rsp+110h+var_E0], xmm6
0x18000562f  movsd   [rsp+110h+var_D8], xmm6
0x180005635  mov     rax, [rbx]
0x180005638  lea     r8, [rsp+110h+var_D8]
0x18000563d  lea     rdx, [rsp+110h+var_E0]
0x180005642  mov     rcx, rbx
0x180005645  mov     rax, [rax+28h]
0x180005649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000564e  test    eax, eax
0x180005650  js      loc_1800057BB
0x180005656  movsd   xmm1, [rsp+110h+var_D8]
0x18000565c  movsd   xmm3, [rsp+110h+var_E0]
0x180005662  comisd  xmm6, xmm3
0x180005666  jnb     loc_1800057C6
0x18000566c  comisd  xmm6, xmm1
0x180005670  jnb     loc_18000590E
0x180005676  movaps  xmm2, xmm3
0x180005679  minsd   xmm2, xmm1
0x18000567d  comisd  xmm2, xmm6
0x180005681  jbe     short loc_18000569F
0x180005683  movaps  xmm4, xmm3
0x180005686  maxsd   xmm4, xmm1
0x18000568a  movaps  xmm0, xmm4
0x18000568d  divsd   xmm0, xmm2
0x180005691  comisd  xmm0, cs:__real@4010000000000000
0x180005699  ja      loc_18000591A
0x18000569f  movsd   qword ptr [rsi+28h], xmm3
0x1800056a4  movsd   qword ptr [rsi+30h], xmm1
0x1800056a9  mov     rax, [rbx]
0x1800056ac  lea     rdx, [rsi+38h]
0x1800056b0  mov     rcx, rbx
0x1800056b3  mov     rax, [rax+20h]
0x1800056b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056bc  mov     edi, eax
0x1800056be  test    rbx, rbx
0x1800056c1  jz      short loc_1800056D3
0x1800056c3  mov     rax, [rbx]
0x1800056c6  mov     rcx, rbx
0x1800056c9  mov     rax, [rax+10h]
0x1800056cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056d2  nop
0x1800056d3  mov     r14, [rbp+57h+var_C0]
0x1800056d7  test    r14, r14
0x1800056da  jz      short loc_1800056EC
0x1800056dc  mov     rax, [r14]
0x1800056df  mov     rcx, r14
0x1800056e2  mov     rax, [rax+10h]
0x1800056e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056eb  nop
0x1800056ec  test    edi, edi
0x1800056ee  js      short loc_1800056F4
0x1800056f0  mov     byte ptr [rsi+1Ch], 1
0x1800056f4  mov     rcx, [rbp+57h+var_D0]
0x1800056f8  test    rcx, rcx
0x1800056fb  jz      short loc_18000570A
0x1800056fd  mov     rax, [rcx]
0x180005700  mov     rax, [rax+10h]
0x180005704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005709  nop
0x18000570a  mov     eax, edi
0x18000570c  mov     rcx, [rbp+57h+var_50]
0x180005710  xor     rcx, rsp; StackCookie
0x180005713  call    __security_check_cookie
0x180005718  mov     rbx, [rsp+110h+arg_10]
0x180005720  movaps  xmm6, [rsp+110h+var_40]
0x180005728  add     rsp, 0E0h
0x18000572f  pop     r15
0x180005731  pop     r14
0x180005733  pop     r13
0x180005735  pop     r12
0x180005737  pop     rdi
0x180005738  pop     rsi
0x180005739  pop     rbp
0x18000573a  retn
0x18000573b  mov     eax, 800704DFh
0x180005740  jmp     short loc_18000570C
0x180005742  cmp     word ptr [rbp+57h+pvar], 12h
0x180005747  jnz     def_180005777; jumptable 0000000180005777 default case, case 1
0x18000574d  test    eax, eax
0x18000574f  js      loc_1800058FF
0x180005755  movzx   eax, word ptr [rbp+57h+pvar+8]
0x180005759  dec     eax; switch 8 cases
0x18000575b  cmp     eax, 7
0x18000575e  ja      def_180005777; jumptable 0000000180005777 default case, case 1
0x180005764  cdqe
0x180005766  lea     rdx, __ImageBase
0x18000576d  mov     ecx, ds:(jpt_180005777 - 180000000h)[rdx+rax*4]
0x180005774  add     rcx, rdx
0x180005777  jmp     rcx; switch jump
0x180005779  mov     rax, [r8+8]
0x18000577d  mov     rbx, r14
0x180005780  mov     [rbp+57h+var_C8], rbx
0x180005784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005789  jmp     loc_180005605
0x18000578e  mov     r12d, 3; jumptable 0000000180005777 case 8
0x180005794  jmp     loc_18000557C; jumptable 0000000180005777 case 6
0x180005799  mov     rax, [rcx]
0x18000579c  mov     rax, [rax+10h]
0x1800057a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057a5  jmp     loc_1800053D6
0x1800057aa  mov     rax, [rcx]
0x1800057ad  mov     rax, [rax+10h]
0x1800057b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b6  jmp     loc_180005406
0x1800057bb  xorps   xmm1, xmm1
0x1800057be  xorps   xmm3, xmm3
0x1800057c1  jmp     loc_18000569F
0x1800057c6  movaps  xmm3, xmm1
0x1800057c9  maxsd   xmm3, xmm6
0x1800057cd  jmp     loc_18000566C
0x1800057d2  mov     rax, [r14]
0x1800057d5  mov     rcx, r14
0x1800057d8  mov     rax, [rax+8]
0x1800057dc  mov     rbx, r14
  ... truncated ...
```
