# Wallet::Utils::D2DBitmapToIWICBitmap(ID2D1Bitmap1 *,ID2D1DeviceContext *,IWICBitmap * *,int,int)

- ea: `0x1800377e4`
- end: `0x180037bd2`
- name: `?D2DBitmapToIWICBitmap@Utils@Wallet@@YAJPEAUID2D1Bitmap1@@PEAUID2D1DeviceContext@@PEAPEAUIWICBitmap@@HH@Z`
- size: `1006`
- prototype: `__int64 __fastcall(Wallet::Utils *this, struct ID2D1Bitmap1 *, struct ID2D1DeviceContext *, struct IWICBitmap **, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003cb40`

## callees

- `0x18002d048`
- `0x1800377e4`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180037ab6`
- `msvcrt!memcpy_s` at `0x180037ab6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003786d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003786d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18003794f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18003794f`

## pseudocode

```c
__int64 __fastcall Wallet::Utils::D2DBitmapToIWICBitmap(
        Wallet::Utils *this,
        struct ID2D1Bitmap1 *a2,
        struct ID2D1DeviceContext *a3,
        struct IWICBitmap **a4,
        unsigned int a5)
{
  unsigned int v5; // r14d
  HRESULT v9; // ebx
  _QWORD *v10; // rax
  char *v11; // rsi
  unsigned int v12; // ebx
  rsize_t v13; // r14
  unsigned int v14; // eax
  char *v15; // rcx
  __int64 v16; // rax
  rsize_t DestinationSize; // [rsp+40h] [rbp-91h] BYREF
  __int64 v19; // [rsp+48h] [rbp-89h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-81h] BYREF
  __int64 v21; // [rsp+58h] [rbp-79h] BYREF
  __int64 v22; // [rsp+60h] [rbp-71h] BYREF
  __int64 v23; // [rsp+68h] [rbp-69h] BYREF
  void *Destination; // [rsp+70h] [rbp-61h] BYREF
  __int64 v25; // [rsp+78h] [rbp-59h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp-51h] BYREF
  LPSTREAM ppstm; // [rsp+88h] [rbp-49h] BYREF
  __int64 v28; // [rsp+90h] [rbp-41h] BYREF
  float v29; // [rsp+98h] [rbp-39h]
  float v30; // [rsp+9Ch] [rbp-35h]
  __int64 v31; // [rsp+A0h] [rbp-31h]
  __int64 v32; // [rsp+A8h] [rbp-29h]
  void *Source[2]; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-11h] BYREF
  int v35; // [rsp+C8h] [rbp-9h]
  unsigned int v36; // [rsp+CCh] [rbp-5h]

  v5 = (unsigned int)a4;
  ppv = 0;
  v23 = 0;
  ppstm = 0;
  v22 = 0;
  v21 = 0;
  v25 = 0;
  LODWORD(DestinationSize) = 0;
  Destination = 0;
  *(_OWORD *)Source = 0;
  v34 = 0;
  v35 = (int)a4;
  v36 = a5;
  v9 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv);
  if ( v9 >= 0 )
  {
    v10 = (_QWORD *)(*(__int64 (__fastcall **)(Wallet::Utils *, __int64 *))(*(_QWORD *)this + 40LL))(this, &v19);
    v28 = 0x100000057LL;
    v29 = FLOAT_96_0;
    v30 = FLOAT_96_0;
    v31 = 6;
    v32 = 0;
    v9 = (*(__int64 (__fastcall **)(struct ID2D1Bitmap1 *, _QWORD, _QWORD, _QWORD, __int64 *, __int64 *))(*(_QWORD *)a2 + 456LL))(
           a2,
           *v10,
           0,
           0,
           &v28,
           &v25);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, Wallet::Utils *, _QWORD))(*(_QWORD *)v25 + 64LL))(
             v25,
             0,
             this,
             0);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, __int64, void **))(*(_QWORD *)v25 + 112LL))(v25, 1, Source);
        if ( v9 >= 0 )
        {
          v9 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(LPVOID, GUID *, _QWORD, __int64 *))(*(_QWORD *)ppv + 64LL))(
                   ppv,
                   &GUID_ContainerFormatJpeg,
                   0,
                   &v23);
            if ( v9 >= 0 )
            {
              v9 = (*(__int64 (__fastcall **)(__int64, LPSTREAM, __int64))(*(_QWORD *)v23 + 24LL))(v23, ppstm, 2);
              if ( v9 >= 0 )
              {
                v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v23 + 80LL))(v23, &v22, 0);
                if ( v9 >= 0 )
                {
                  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 24LL))(v22, 0);
                  if ( v9 >= 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, GUID *, int, __int64 *))(*(_QWORD *)ppv + 136LL))(
                           ppv,
                           v5,
                           a5,
                           &GUID_WICPixelFormat32bppBGRA,
                           1,
                           &v21);
                    if ( v9 >= 0 )
                    {
                      v19 = 0;
                      v20 = 0;
                      v11 = (char *)Source[1];
                      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64, __int64 *))(*(_QWORD *)v21 + 64LL))(
                             v21,
                             &v34,
                             2,
                             &v19);
                      if ( v9 < 0
                        || (v9 = (*(__int64 (__fastcall **)(__int64, rsize_t *, void **))(*(_QWORD *)v19 + 40LL))(
                                   v19,
                                   &DestinationSize,
                                   &Destination),
                            v9 < 0)
                        || (v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 32LL))(v19, &v20),
                            v9 < 0) )
                      {
                        ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v19);
                      }
                      else
                      {
                        v12 = 0;
                        if ( a5 )
                        {
                          v13 = 4 * v5;
                          v14 = DestinationSize;
                          v15 = (char *)Destination;
                          do
                          {
                            memcpy_s(v15, v14, v11, v13);
                            v11 += LODWORD(Source[0]);
                            v15 = (char *)Destination + v20;
                            Destination = v15;
                            v14 = DestinationSize - v20;
                            LODWORD(DestinationSize) = DestinationSize - v20;
                            ++v12;
                          }
                          while ( v12 < a5 );
                        }
                        ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v19);
                        v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 80LL))(v21);
                        if ( v9 >= 0 )
                        {
                          v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v22 + 88LL))(
                                 v22,
                                 v21,
                                 &v34);
                          if ( v9 >= 0 )
                          {
                            v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 96LL))(v22);
                            if ( v9 >= 0 )
                            {
                              v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 88LL))(v23);
                              if ( v9 >= 0 )
                              {
                                v9 = 0;
                                v16 = v21;
                                v21 = 0;
                                *(_QWORD *)a3 = v16;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v25);
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v21);
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v22);
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>((__int64 *)&ppstm);
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v23);
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>((__int64 *)&ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800377e4  push    rbp
0x1800377e6  push    rbx
0x1800377e7  push    rsi
0x1800377e8  push    rdi
0x1800377e9  push    r12
0x1800377eb  push    r13
0x1800377ed  push    r14
0x1800377ef  push    r15
0x1800377f1  lea     rbp, [rsp-17h]
0x1800377f6  sub     rsp, 0E8h
0x1800377fd  mov     rax, cs:__security_cookie
0x180037804  xor     rax, rsp
0x180037807  mov     [rbp+4Fh+var_50], rax
0x18003780b  mov     r14d, r9d
0x18003780e  mov     r12, r8
0x180037811  mov     r15, rdx
0x180037814  mov     rsi, rcx
0x180037817  xor     r13d, r13d
0x18003781a  mov     [rbp+4Fh+var_A0], r13
0x18003781e  mov     [rbp+4Fh+var_B8], r13
0x180037822  mov     [rbp+4Fh+ppstm], r13
0x180037826  mov     [rbp+4Fh+var_C0], r13
0x18003782a  mov     [rbp+4Fh+var_C8], r13
0x18003782e  mov     [rbp+4Fh+var_A8], r13
0x180037832  mov     dword ptr [rsp+120h+DestinationSize], r13d
0x180037837  mov     [rbp+4Fh+Destination], r13
0x18003783b  xorps   xmm0, xmm0
0x18003783e  movups  xmmword ptr [rbp+4Fh+Source], xmm0
0x180037842  mov     [rbp+4Fh+var_60], r13
0x180037846  mov     [rbp+4Fh+var_58], r9d
0x18003784a  mov     edi, [rbp+4Fh+arg_20]
0x18003784d  mov     [rbp+4Fh+var_54], edi
0x180037850  lea     rax, [rbp+4Fh+var_A0]
0x180037854  mov     [rsp+120h+ppv], rax; ppv
0x180037859  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180037860  xor     edx, edx; pUnkOuter
0x180037862  lea     r8d, [r13+1]; dwClsContext
0x180037866  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18003786d  call    cs:__imp_CoCreateInstance
0x180037873  mov     ebx, eax
0x180037875  test    eax, eax
0x180037877  js      loc_180037B75
0x18003787d  mov     rax, [rsi]
0x180037880  lea     rdx, [rsp+120h+var_D8]
0x180037885  mov     rcx, rsi
0x180037888  mov     rax, [rax+28h]
0x18003788c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037891  mov     dword ptr [rbp+4Fh+var_90], 57h ; 'W'
0x180037898  mov     dword ptr [rbp+4Fh+var_90+4], 1
0x18003789f  movss   xmm0, cs:__real@42c00000
0x1800378a7  mov     rcx, [rbp+4Fh+var_90]
0x1800378ab  mov     [rbp+4Fh+var_90], rcx
0x1800378af  movss   [rbp+4Fh+var_88], xmm0
0x1800378b4  movss   [rbp+4Fh+var_84], xmm0
0x1800378b9  mov     [rbp+4Fh+var_80], 6
0x1800378c1  mov     [rbp+4Fh+var_78], r13
0x1800378c5  mov     rdx, [r15]
0x1800378c8  mov     r10, [rdx+1C8h]
0x1800378cf  lea     rcx, [rbp+4Fh+var_A8]
0x1800378d3  mov     [rsp+120h+var_F8], rcx
0x1800378d8  lea     rcx, [rbp+4Fh+var_90]
0x1800378dc  mov     [rsp+120h+ppv], rcx
0x1800378e1  xor     r9d, r9d
0x1800378e4  xor     r8d, r8d
0x1800378e7  mov     rdx, [rax]
0x1800378ea  mov     rcx, r15
0x1800378ed  mov     rax, r10
0x1800378f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378f5  mov     ebx, eax
0x1800378f7  test    eax, eax
0x1800378f9  js      loc_180037B75
0x1800378ff  mov     rcx, [rbp+4Fh+var_A8]
0x180037903  mov     rax, [rcx]
0x180037906  xor     r9d, r9d
0x180037909  mov     r8, rsi
0x18003790c  xor     edx, edx
0x18003790e  mov     rax, [rax+40h]
0x180037912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037917  mov     ebx, eax
0x180037919  test    eax, eax
0x18003791b  js      loc_180037B75
0x180037921  mov     rcx, [rbp+4Fh+var_A8]
0x180037925  mov     rax, [rcx]
0x180037928  lea     r8, [rbp+4Fh+Source]
0x18003792c  lea     r15d, [r13+1]
0x180037930  mov     edx, r15d
0x180037933  mov     rax, [rax+70h]
0x180037937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003793c  mov     ebx, eax
0x18003793e  test    eax, eax
0x180037940  js      loc_180037B75
0x180037946  lea     r8, [rbp+4Fh+ppstm]; ppstm
0x18003794a  mov     edx, r15d; fDeleteOnRelease
0x18003794d  xor     ecx, ecx; hGlobal
0x18003794f  call    cs:__imp_CreateStreamOnHGlobal
0x180037955  mov     ebx, eax
0x180037957  test    eax, eax
0x180037959  js      loc_180037B75
0x18003795f  mov     rcx, [rbp+4Fh+var_A0]
0x180037963  mov     rax, [rcx]
0x180037966  lea     r9, [rbp+4Fh+var_B8]
0x18003796a  xor     r8d, r8d
0x18003796d  lea     rdx, GUID_ContainerFormatJpeg
0x180037974  mov     rax, [rax+40h]
0x180037978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003797d  mov     ebx, eax
0x18003797f  test    eax, eax
0x180037981  js      loc_180037B75
0x180037987  mov     rcx, [rbp+4Fh+var_B8]
0x18003798b  mov     rax, [rcx]
0x18003798e  lea     r8d, [r13+2]
0x180037992  mov     rdx, [rbp+4Fh+ppstm]
0x180037996  mov     rax, [rax+18h]
0x18003799a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003799f  mov     ebx, eax
0x1800379a1  test    eax, eax
0x1800379a3  js      loc_180037B75
0x1800379a9  mov     rcx, [rbp+4Fh+var_B8]
0x1800379ad  mov     rax, [rcx]
0x1800379b0  xor     r8d, r8d
0x1800379b3  lea     rdx, [rbp+4Fh+var_C0]
0x1800379b7  mov     rax, [rax+50h]
0x1800379bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379c0  mov     ebx, eax
0x1800379c2  test    eax, eax
0x1800379c4  js      loc_180037B75
0x1800379ca  mov     rcx, [rbp+4Fh+var_C0]
0x1800379ce  mov     rax, [rcx]
0x1800379d1  xor     edx, edx
0x1800379d3  mov     rax, [rax+18h]
0x1800379d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379dc  mov     ebx, eax
0x1800379de  test    eax, eax
0x1800379e0  js      loc_180037B75
0x1800379e6  mov     rcx, [rbp+4Fh+var_A0]
0x1800379ea  mov     rax, [rcx]
0x1800379ed  lea     rdx, [rbp+4Fh+var_C8]
0x1800379f1  mov     [rsp+120h+var_F8], rdx
0x1800379f6  mov     dword ptr [rsp+120h+ppv], r15d
0x1800379fb  lea     r9, GUID_WICPixelFormat32bppBGRA
0x180037a02  mov     r8d, edi
0x180037a05  mov     edx, r14d
0x180037a08  mov     rax, [rax+88h]
0x180037a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a14  mov     ebx, eax
0x180037a16  test    eax, eax
0x180037a18  js      loc_180037B75
0x180037a1e  mov     [rsp+120h+var_D8], r13
0x180037a23  mov     [rsp+120h+var_D0], r13d
0x180037a28  mov     rsi, [rbp+4Fh+Source+8]
0x180037a2c  mov     rcx, [rbp+4Fh+var_C8]
0x180037a30  mov     rax, [rcx]
0x180037a33  lea     r9, [rsp+120h+var_D8]
0x180037a38  lea     r8d, [r13+2]
0x180037a3c  lea     rdx, [rbp+4Fh+var_60]
0x180037a40  mov     rax, [rax+40h]
0x180037a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a49  mov     ebx, eax
0x180037a4b  test    eax, eax
0x180037a4d  js      loc_180037B6A
0x180037a53  mov     rcx, [rsp+120h+var_D8]
0x180037a58  mov     rax, [rcx]
0x180037a5b  lea     r8, [rbp+4Fh+Destination]
0x180037a5f  lea     rdx, [rsp+120h+DestinationSize]
0x180037a64  mov     rax, [rax+28h]
0x180037a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a6d  mov     ebx, eax
0x180037a6f  test    eax, eax
0x180037a71  js      loc_180037B6A
0x180037a77  mov     rcx, [rsp+120h+var_D8]
0x180037a7c  mov     rax, [rcx]
0x180037a7f  lea     rdx, [rsp+120h+var_D0]
0x180037a84  mov     rax, [rax+20h]
0x180037a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a8d  mov     ebx, eax
0x180037a8f  test    eax, eax
0x180037a91  js      loc_180037B6A
0x180037a97  mov     ebx, r13d
0x180037a9a  test    edi, edi
0x180037a9c  jz      short loc_180037AE4
0x180037a9e  lea     r14d, ds:0[r14*4]
0x180037aa6  mov     eax, dword ptr [rsp+120h+DestinationSize]
0x180037aaa  mov     rcx, [rbp+4Fh+Destination]; Destination
0x180037aae  mov     edx, eax; DestinationSize
0x180037ab0  mov     r9, r14; SourceSize
0x180037ab3  mov     r8, rsi; Source
0x180037ab6  call    cs:__imp_memcpy_s
0x180037abc  mov     eax, dword ptr [rbp+4Fh+Source]
0x180037abf  add     rsi, rax
0x180037ac2  mov     eax, [rsp+120h+var_D0]
0x180037ac6  mov     rcx, [rbp+4Fh+Destination]
0x180037aca  add     rcx, rax
0x180037acd  mov     [rbp+4Fh+Destination], rcx
0x180037ad1  mov     eax, dword ptr [rsp+120h+DestinationSize]
0x180037ad5  sub     eax, [rsp+120h+var_D0]
0x180037ad9  mov     dword ptr [rsp+120h+DestinationSize], eax
0x180037add  add     ebx, r15d
0x180037ae0  cmp     ebx, edi
0x180037ae2  jb      short loc_180037AAE
0x180037ae4  lea     rcx, [rsp+120h+var_D8]
0x180037ae9  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x180037aee  mov     rcx, [rbp+4Fh+var_C8]
0x180037af2  mov     rax, [rcx]
0x180037af5  movsd   xmm1, cs:__real@4058000000000000
0x180037afd  movaps  xmm2, xmm1
0x180037b00  mov     rax, [rax+50h]
0x180037b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b09  mov     ebx, eax
0x180037b0b  test    eax, eax
0x180037b0d  js      short loc_180037B75
0x180037b0f  mov     rcx, [rbp+4Fh+var_C0]
0x180037b13  mov     rax, [rcx]
0x180037b16  lea     r8, [rbp+4Fh+var_60]
0x180037b1a  mov     rdx, [rbp+4Fh+var_C8]
0x180037b1e  mov     rax, [rax+58h]
0x180037b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b27  mov     ebx, eax
0x180037b29  test    eax, eax
0x180037b2b  js      short loc_180037B75
0x180037b2d  mov     rcx, [rbp+4Fh+var_C0]
0x180037b31  mov     rax, [rcx]
0x180037b34  mov     rax, [rax+60h]
0x180037b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b3d  mov     ebx, eax
0x180037b3f  test    eax, eax
0x180037b41  js      short loc_180037B75
0x180037b43  mov     rcx, [rbp+4Fh+var_B8]
0x180037b47  mov     rax, [rcx]
0x180037b4a  mov     rax, [rax+58h]
0x180037b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b53  mov     ebx, eax
0x180037b55  test    eax, eax
0x180037b57  js      short loc_180037B75
0x180037b59  mov     ebx, r13d
0x180037b5c  mov     rax, [rbp+4Fh+var_C8]
0x180037b60  mov     [rbp+4Fh+var_C8], r13
0x180037b64  mov     [r12], rax
0x180037b68  jmp     short loc_180037B75
0x180037b6a  lea     rcx, [rsp+120h+var_D8]
0x180037b6f  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x180037b74  nop
0x180037b75  lea     rcx, [rbp+4Fh+var_A8]
0x180037b79  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x180037b7e  nop
0x180037b7f  lea     rcx, [rbp+4Fh+var_C8]
0x180037b83  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x180037b88  nop
0x180037b89  lea     rcx, [rbp+4Fh+var_C0]
0x180037b8d  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x180037b92  nop
0x180037b93  lea     rcx, [rbp+4Fh+ppstm]
0x180037b97  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x180037b9c  nop
0x180037b9d  lea     rcx, [rbp+4Fh+var_B8]
0x180037ba1  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x180037ba6  nop
0x180037ba7  lea     rcx, [rbp+4Fh+var_A0]
0x180037bab  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x180037bb0  mov     eax, ebx
0x180037bb2  mov     rcx, [rbp+4Fh+var_50]
0x180037bb6  xor     rcx, rsp; StackCookie
0x180037bb9  call    __security_check_cookie
0x180037bbe  add     rsp, 0E8h
0x180037bc5  pop     r15
0x180037bc7  pop     r14
0x180037bc9  pop     r13
0x180037bcb  pop     r12
0x180037bcd  pop     rdi
0x180037bce  pop     rsi
0x180037bcf  pop     rbx
0x180037bd0  pop     rbp
0x180037bd1  retn
```
