# CMetadataContainer::Initialize(IStream *,ulong,IWICBitmapDecoder *)

- ea: `0x180005470`
- end: `0x180005a80`
- name: `?Initialize@CMetadataContainer@@QEAAJPEAUIStream@@KPEAUIWICBitmapDecoder@@@Z`
- size: `1552`
- prototype: `__int64 __fastcall(CMetadataContainer *this, struct IStream *, int, struct IWICBitmapDecoder *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005080`

## callees

- `0x180005470`
- `0x180005c74`
- `0x180016a40`
- `0x180017408`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005696`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005a24`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005696`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005a24`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005584`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005584`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x180005470  mov     [rsp-8+arg_10], rbx
0x180005475  push    rbp
0x180005476  push    rsi
0x180005477  push    rdi
0x180005478  push    r12
0x18000547a  push    r13
0x18000547c  push    r14
0x18000547e  push    r15
0x180005480  lea     rbp, [rsp-27h]
0x180005485  sub     rsp, 0E0h
0x18000548c  movaps  [rsp+110h+var_40], xmm6
0x180005494  mov     rax, cs:__security_cookie
0x18000549b  xor     rax, rsp
0x18000549e  mov     [rbp+57h+var_50], rax
0x1800054a2  mov     rbx, r9
0x1800054a5  mov     r14d, r8d
0x1800054a8  mov     rdi, rdx
0x1800054ab  mov     rsi, rcx
0x1800054ae  cmp     qword ptr [rcx], 0
0x1800054b2  jnz     loc_180005858
0x1800054b8  cmp     byte ptr [rcx+1Ch], 0
0x1800054bc  jnz     loc_180005858
0x1800054c2  test    rdx, rdx
0x1800054c5  jz      loc_18000590E
0x1800054cb  mov     rax, [rdx]
0x1800054ce  mov     rcx, rdx
0x1800054d1  mov     rax, [rax+8]
0x1800054d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054da  mov     rcx, [rsi]
0x1800054dd  test    rcx, rcx
0x1800054e0  jnz     loc_1800058BA
0x1800054e6  mov     [rsi], rdi
0x1800054e9  mov     [rsi+18h], r14d
0x1800054ed  lea     r15, [rsi+8]
0x1800054f1  cmp     [r15], rbx
0x1800054f4  jz      short loc_180005519
0x1800054f6  test    rbx, rbx
0x1800054f9  jz      short loc_18000550A
0x1800054fb  mov     rax, [rbx]
0x1800054fe  mov     rcx, rbx
0x180005501  mov     rax, [rax+8]
0x180005505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000550a  mov     rcx, [r15]
0x18000550d  test    rcx, rcx
0x180005510  jnz     loc_1800058CB
0x180005516  mov     [r15], rbx
0x180005519  xor     edx, edx; Val
0x18000551b  mov     r8d, 50h ; 'P'; Size
0x180005521  lea     rcx, [rbp+57h+var_A0]; void *
0x180005525  call    memset_0
0x18000552a  mov     rax, [rdi]
0x18000552d  mov     r12d, 1
0x180005533  mov     r8d, r12d
0x180005536  lea     rdx, [rbp+57h+var_A0]
0x18000553a  mov     rcx, rdi
0x18000553d  mov     rax, [rax+60h]
0x180005541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005546  test    eax, eax
0x180005548  js      short loc_180005557
0x18000554a  mov     rax, [rbp+57h+var_90]
0x18000554e  test    rax, rax
0x180005551  jz      short loc_180005557
0x180005553  mov     [rsi+48h], rax
0x180005557  xor     r13d, r13d
0x18000555a  cmp     [rsi+48h], r13
0x18000555e  jz      loc_180005918
0x180005564  mov     [rbp+57h+var_D0], r13
0x180005568  lea     rax, [rbp+57h+var_D0]
0x18000556c  mov     [rsp+110h+ppv], rax; ppv
0x180005571  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180005578  mov     r8d, r12d; dwClsContext
0x18000557b  xor     edx, edx; pUnkOuter
0x18000557d  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180005584  call    cs:__imp_CoCreateInstance
0x18000558b  nop     dword ptr [rax+rax+00h]
0x180005590  mov     edi, eax
0x180005592  test    eax, eax
0x180005594  js      short loc_1800055B2
0x180005596  mov     rcx, [rbp+57h+var_D0]
0x18000559a  mov     rax, [rcx]
0x18000559d  lea     r8, [rsi+10h]
0x1800055a1  lea     rdx, IID_IWICComponentFactory
0x1800055a8  mov     rax, [rax]
0x1800055ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055b0  mov     edi, eax
0x1800055b2  cmp     qword ptr [r15], 0
0x1800055b6  jz      loc_18000599D
0x1800055bc  mov     rcx, [r15]
0x1800055bf  test    rcx, rcx
0x1800055c2  jz      loc_180005A4C
0x1800055c8  mov     rax, [rcx]
0x1800055cb  lea     rdx, [rsi+50h]
0x1800055cf  mov     rax, [rax+28h]
0x1800055d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055d8  mov     edi, eax
0x1800055da  test    eax, eax
0x1800055dc  js      loc_180005810
0x1800055e2  mov     [rbp+57h+var_C0], r13
0x1800055e6  mov     rcx, [r15]
0x1800055e9  mov     rax, [rcx]
0x1800055ec  lea     r8, [rbp+57h+var_C0]
0x1800055f0  xor     edx, edx
0x1800055f2  mov     rax, [rax+68h]
0x1800055f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055fb  mov     edi, eax
0x1800055fd  mov     r14, [rbp+57h+var_C0]
0x180005601  test    eax, eax
0x180005603  js      loc_1800057F3
0x180005609  test    r14, r14
0x18000560c  jz      loc_1800057F3
0x180005612  mov     r13, [rbp+57h+var_D0]
0x180005616  mov     [rbp+57h+var_C8], 0
0x18000561e  mov     rcx, [r15]; struct IWICBitmapDecoder *
0x180005621  call    ?WICIsOrientationSupported@@YA_NPEAUIWICBitmapDecoder@@@Z; WICIsOrientationSupported(IWICBitmapDecoder *)
0x180005626  mov     r8, [r14]
0x180005629  mov     rcx, r14
0x18000562c  test    al, al
0x18000562e  jz      loc_18000589A
0x180005634  xor     r15d, r15d
0x180005637  mov     [rsp+110h+var_D8], r15
0x18000563c  lea     rdx, [rsp+110h+var_D8]
0x180005641  mov     rax, [r8+40h]
0x180005645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000564a  test    eax, eax
0x18000564c  js      loc_1800058F3
0x180005652  mov     rcx, [rsp+110h+var_D8]
0x180005657  mov     ebx, r15d
0x18000565a  mov     [rbp+57h+var_C8], rbx
0x18000565e  xorps   xmm0, xmm0
0x180005661  xor     eax, eax
0x180005663  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180005667  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18000566b  mov     rax, [rcx]
0x18000566e  lea     r8, [rbp+57h+pvar]
0x180005672  lea     rdx, aSystemPhotoOri; "System.Photo.Orientation"
0x180005679  mov     rax, [rax+28h]
0x18000567d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005682  mov     edi, eax
0x180005684  cmp     eax, 88982F40h
0x180005689  jnz     loc_18000585F
0x18000568f  mov     r12d, r15d; jumptable 0000000180005894 default case, case 1
0x180005692  lea     rcx, [rbp+57h+pvar]; jumptable 0000000180005894 case 6
0x180005696  call    cs:__imp_PropVariantClear
0x18000569d  nop     dword ptr [rax+rax+00h]
0x1800056a2  mov     [rsp+110h+var_E0], r15
0x1800056a7  mov     rax, [r13+0]
0x1800056ab  lea     rdx, [rsp+110h+var_E0]
0x1800056b0  mov     rcx, r13
0x1800056b3  mov     rax, [rax+68h]
0x1800056b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056bc  mov     edi, eax
0x1800056be  test    eax, eax
0x1800056c0  js      short loc_180005708
0x1800056c2  mov     rcx, [rsp+110h+var_E0]
0x1800056c7  mov     rax, [rcx]
0x1800056ca  mov     r8d, r12d
0x1800056cd  mov     rdx, r14
0x1800056d0  mov     rax, [rax+40h]
0x1800056d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056d9  mov     edi, eax
0x1800056db  test    eax, eax
0x1800056dd  js      short loc_1800056F7
0x1800056df  mov     rbx, [rsp+110h+var_E0]
0x1800056e4  mov     [rbp+57h+var_C8], rbx
0x1800056e8  mov     rax, [rbx]
0x1800056eb  mov     rcx, rbx
0x1800056ee  mov     rax, [rax+8]
0x1800056f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056f7  mov     rcx, [rsp+110h+var_E0]
0x1800056fc  mov     rax, [rcx]
0x1800056ff  mov     rax, [rax+10h]
0x180005703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005708  mov     rcx, [rsp+110h+var_D8]
0x18000570d  mov     rax, [rcx]
0x180005710  mov     rax, [rax+10h]
0x180005714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005719  test    edi, edi
0x18000571b  js      loc_1800057DA
0x180005721  mov     rax, [rbx]
0x180005724  lea     r8, [rsi+24h]
0x180005728  lea     rdx, [rsi+20h]
0x18000572c  mov     rcx, rbx
0x18000572f  mov     rax, [rax+18h]
0x180005733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005738  mov     edi, eax
0x18000573a  test    eax, eax
0x18000573c  js      loc_1800057DA
0x180005742  xorps   xmm6, xmm6
0x180005745  movsd   [rsp+110h+var_E0], xmm6
0x18000574b  movsd   [rsp+110h+var_D8], xmm6
0x180005751  mov     rax, [rbx]
0x180005754  lea     r8, [rsp+110h+var_D8]
0x180005759  lea     rdx, [rsp+110h+var_E0]
0x18000575e  mov     rcx, rbx
0x180005761  mov     rax, [rax+28h]
0x180005765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000576a  test    eax, eax
0x18000576c  js      loc_1800058DC
0x180005772  movsd   xmm1, [rsp+110h+var_D8]
0x180005778  movsd   xmm3, [rsp+110h+var_E0]
0x18000577e  comisd  xmm6, xmm3
0x180005782  jnb     loc_1800058E7
0x180005788  comisd  xmm6, xmm1
0x18000578c  jnb     loc_180005A35
0x180005792  movaps  xmm2, xmm3
0x180005795  minsd   xmm2, xmm1
0x180005799  comisd  xmm2, xmm6
0x18000579d  jbe     short loc_1800057BB
0x18000579f  movaps  xmm4, xmm3
0x1800057a2  maxsd   xmm4, xmm1
0x1800057a6  movaps  xmm0, xmm4
0x1800057a9  divsd   xmm0, xmm2
0x1800057ad  comisd  xmm0, cs:__real@4010000000000000
0x1800057b5  ja      loc_180005A41
0x1800057bb  movsd   qword ptr [rsi+28h], xmm3
0x1800057c0  movsd   qword ptr [rsi+30h], xmm1
0x1800057c5  mov     rax, [rbx]
0x1800057c8  lea     rdx, [rsi+38h]
0x1800057cc  mov     rcx, rbx
0x1800057cf  mov     rax, [rax+20h]
0x1800057d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057d8  mov     edi, eax
0x1800057da  test    rbx, rbx
0x1800057dd  jz      short loc_1800057EF
0x1800057df  mov     rax, [rbx]
0x1800057e2  mov     rcx, rbx
0x1800057e5  mov     rax, [rax+10h]
0x1800057e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ee  nop
0x1800057ef  mov     r14, [rbp+57h+var_C0]
0x1800057f3  test    r14, r14
0x1800057f6  jz      short loc_180005808
0x1800057f8  mov     rax, [r14]
0x1800057fb  mov     rcx, r14
0x1800057fe  mov     rax, [rax+10h]
0x180005802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005807  nop
0x180005808  test    edi, edi
0x18000580a  js      short loc_180005810
0x18000580c  mov     byte ptr [rsi+1Ch], 1
0x180005810  mov     rcx, [rbp+57h+var_D0]
0x180005814  test    rcx, rcx
0x180005817  jz      short loc_180005826
0x180005819  mov     rax, [rcx]
0x18000581c  mov     rax, [rax+10h]
0x180005820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005825  nop
0x180005826  mov     eax, edi
0x180005828  mov     rcx, [rbp+57h+var_50]
0x18000582c  xor     rcx, rsp; StackCookie
0x18000582f  call    __security_check_cookie
0x180005834  mov     rbx, [rsp+110h+arg_10]
0x18000583c  movaps  xmm6, [rsp+110h+var_40]
0x180005844  add     rsp, 0E0h
0x18000584b  pop     r15
0x18000584d  pop     r14
0x18000584f  pop     r13
0x180005851  pop     r12
0x180005853  pop     rdi
0x180005854  pop     rsi
0x180005855  pop     rbp
0x180005856  retn
0x180005858  mov     eax, 800704DFh
0x18000585d  jmp     short loc_180005828
0x18000585f  cmp     word ptr [rbp+57h+pvar], 12h
0x180005864  jnz     def_180005894; jumptable 0000000180005894 default case, case 1
0x18000586a  test    eax, eax
0x18000586c  js      loc_180005A20
0x180005872  movzx   eax, word ptr [rbp+57h+pvar+8]
0x180005876  dec     eax; switch 8 cases
0x180005878  cmp     eax, 7
0x18000587b  ja      def_180005894; jumptable 0000000180005894 default case, case 1
0x180005881  cdqe
0x180005883  lea     rdx, __ImageBase
0x18000588a  mov     ecx, ds:(jpt_180005894 - 180000000h)[rdx+rax*4]
0x180005891  add     rcx, rdx
0x180005894  jmp     rcx; switch jump
0x18000589a  mov     rax, [r8+8]
0x18000589e  mov     rbx, r14
0x1800058a1  mov     [rbp+57h+var_C8], rbx
0x1800058a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058aa  jmp     loc_180005721
0x1800058af  mov     r12d, 3; jumptable 0000000180005894 case 8
0x1800058b5  jmp     loc_180005692; jumptable 0000000180005894 case 6
0x1800058ba  mov     rax, [rcx]
0x1800058bd  mov     rax, [rax+10h]
0x1800058c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058c6  jmp     loc_1800054E6
0x1800058cb  mov     rax, [rcx]
0x1800058ce  mov     rax, [rax+10h]
0x1800058d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058d7  jmp     loc_180005516
0x1800058dc  xorps   xmm1, xmm1
0x1800058df  xorps   xmm3, xmm3
0x1800058e2  jmp     loc_1800057BB
0x1800058e7  movaps  xmm3, xmm1
0x1800058ea  maxsd   xmm3, xmm6
0x1800058ee  jmp     loc_180005788
0x1800058f3  mov     rax, [r14]
0x1800058f6  mov     rcx, r14
  ... truncated ...
```
