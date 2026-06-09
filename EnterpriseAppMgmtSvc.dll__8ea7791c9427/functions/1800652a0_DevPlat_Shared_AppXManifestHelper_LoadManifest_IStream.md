# DevPlat::Shared::AppXManifestHelper::LoadManifest(IStream *)

- ea: `0x1800652a0`
- end: `0x18006565d`
- name: `?LoadManifest@AppXManifestHelper@Shared@DevPlat@@QEAAJPEAUIStream@@@Z`
- size: `957`
- prototype: `__int64 __fastcall(DevPlat::Shared::AppXManifestHelper *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180064c4c`

## callees

- `0x18000702c`
- `0x180065190`
- `0x1800652a0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180065459`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180065459`
- `OLEAUT32!__imp_SysAllocString` at `0x180065350`
- `OLEAUT32!__imp_SysAllocString` at `0x180065373`
- `OLEAUT32!__imp_SysAllocString` at `0x180065350`
- `OLEAUT32!__imp_SysAllocString` at `0x180065373`
- `OLEAUT32!__imp_VariantInit` at `0x1800652f6`
- `OLEAUT32!__imp_VariantInit` at `0x180065300`
- `OLEAUT32!__imp_VariantInit` at `0x18006530a`
- `OLEAUT32!__imp_VariantInit` at `0x180065314`
- `OLEAUT32!__imp_VariantInit` at `0x1800652f6`
- `OLEAUT32!__imp_VariantInit` at `0x180065300`
- `OLEAUT32!__imp_VariantInit` at `0x18006530a`
- `OLEAUT32!__imp_VariantInit` at `0x180065314`
- `OLEAUT32!__imp_VariantClear` at `0x18006561c`
- `OLEAUT32!__imp_VariantClear` at `0x180065626`
- `OLEAUT32!__imp_VariantClear` at `0x180065630`
- `OLEAUT32!__imp_VariantClear` at `0x18006563a`
- `OLEAUT32!__imp_VariantClear` at `0x18006561c`
- `OLEAUT32!__imp_VariantClear` at `0x180065626`
- `OLEAUT32!__imp_VariantClear` at `0x180065630`
- `OLEAUT32!__imp_VariantClear` at `0x18006563a`

## string_xrefs

- `0x18006533e`: `XPath`
- `0x18006538e`: `http://schemas.microsoft.com/phone/2013/policy`
- `0x18006536c`: `xmlns:m="http://schemas.microsoft.com/appx/2010/manifest" xmlns:m2="http://schemas.microsoft.com/appx/2013/manifest" xmlns:mp="http://schemas.microsoft.com/appx/2014/phone/manifest"`

## pseudocode

```c
__int64 __fastcall DevPlat::Shared::AppXManifestHelper::LoadManifest(__int64 **this, struct IStream *a2)
{
  int Instance; // ebx
  BSTR v5; // rax
  BSTR v6; // rax
  __int64 *v7; // rcx
  __int64 *v8; // rdx
  __int64 v9; // rax
  __int64 *v10; // rcx
  __int64 *v11; // rdx
  __int64 v12; // rax
  __int64 *v13; // rcx
  __int64 *v14; // rdx
  __int64 v15; // rax
  __int64 *v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  __int64 *v19; // rsi
  VARIANTARG v21; // [rsp+30h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-39h] BYREF
  VARIANTARG v23; // [rsp+68h] [rbp-21h] BYREF
  VARIANTARG v24; // [rsp+80h] [rbp-9h] BYREF
  VARIANTARG v25; // [rsp+98h] [rbp+Fh] BYREF
  __int16 v26; // [rsp+F8h] [rbp+6Fh] BYREF
  int v27; // [rsp+100h] [rbp+77h] BYREF

  v26 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v23, 0, sizeof(v23));
  memset(&v24, 0, sizeof(v24));
  memset(&v25, 0, sizeof(v25));
  VariantInit(&pvarg);
  VariantInit(&v23);
  VariantInit(&v24);
  VariantInit(&v25);
  if ( a2 )
  {
    if ( *((_BYTE *)this + 112) )
    {
      Instance = -2147467259;
    }
    else
    {
      pvarg.vt = 11;
      pvarg.iVal = -1;
      v5 = SysAllocString(L"XPath");
      if ( v5
        && (v23.llVal = (LONGLONG)v5,
            v23.vt = 8,
            (v6 = SysAllocString(
                    L"xmlns:m=\"http://schemas.microsoft.com/appx/2010/manifest\" xmlns:m2=\"http://schemas.microsoft.com/"
                     "appx/2013/manifest\" xmlns:mp=\"http://schemas.microsoft.com/appx/2014/phone/manifest\"")) != 0) )
      {
        v24.vt = 8;
        v24.llVal = (LONGLONG)v6;
        Instance = ATL::CComBSTR::Append((const void **)this + 6, L"http://schemas.microsoft.com/phone/2013/policy");
        if ( Instance >= 0 )
        {
          Instance = ATL::CComBSTR::Append((const void **)this + 3, L"NewParser");
          if ( Instance >= 0 )
          {
            Instance = ATL::CComBSTR::Append((const void **)this + 4, L"SelectionNamespaces");
            if ( Instance >= 0 )
            {
              Instance = ATL::CComBSTR::Append((const void **)this + 5, L"SelectionLanguage");
              if ( Instance >= 0 )
              {
                Instance = ATL::CComBSTR::Append(
                             (const void **)this + 7,
                             L"/*[local-name()='Package']/mp:PhoneIdentity");
                if ( Instance >= 0 )
                {
                  Instance = ATL::CComBSTR::Append((const void **)this + 8, L"PhoneProductId");
                  if ( Instance >= 0 )
                  {
                    Instance = ATL::CComBSTR::Append((const void **)this + 9, L"PhonePublisherId");
                    if ( Instance >= 0 )
                    {
                      Instance = CoCreateInstance(
                                   &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
                                   0,
                                   1u,
                                   &GUID_2933bf96_7b36_11d2_b20e_00c04f983e60,
                                   (LPVOID *)this);
                      if ( Instance >= 0 )
                      {
                        Instance = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(**this + 504))(*this, 0);
                        if ( Instance >= 0 )
                        {
                          v7 = *this;
                          v8 = this[3];
                          v9 = **this;
                          v21 = pvarg;
                          Instance = (*(__int64 (__fastcall **)(__int64 *, __int64 *, VARIANTARG *))(v9 + 640))(
                                       v7,
                                       v8,
                                       &v21);
                          if ( Instance >= 0 )
                          {
                            v10 = *this;
                            v11 = this[4];
                            v12 = **this;
                            v21 = v24;
                            Instance = (*(__int64 (__fastcall **)(__int64 *, __int64 *, VARIANTARG *))(v12 + 640))(
                                         v10,
                                         v11,
                                         &v21);
                            if ( Instance >= 0 )
                            {
                              v13 = *this;
                              v14 = this[5];
                              v15 = **this;
                              v21 = v23;
                              Instance = (*(__int64 (__fastcall **)(__int64 *, __int64 *, VARIANTARG *))(v15 + 640))(
                                           v13,
                                           v14,
                                           &v21);
                              if ( Instance >= 0 )
                              {
                                v25.llVal = (LONGLONG)a2;
                                v25.vt = 13;
                                (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)a2 + 8LL))(a2);
                                v16 = *this;
                                v17 = **this;
                                v21 = v25;
                                v18 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int16 *))(v17 + 464))(
                                        v16,
                                        &v21,
                                        &v26);
                                Instance = v18;
                                if ( v18 >= 0 )
                                {
                                  if ( v18 != 1 && v26 )
                                    goto LABEL_29;
                                  Instance = (*(__int64 (__fastcall **)(__int64 *, char *))(**this + 480))(
                                               *this,
                                               (char *)this + 8);
                                  if ( Instance >= 0 )
                                  {
                                    v19 = this[1];
                                    Instance = -2147467259;
                                    if ( v19 )
                                    {
                                      v27 = -2147467259;
                                      if ( this != (__int64 **)-16LL )
                                      {
                                        this[2] = 0;
                                        if ( (*(int (__fastcall **)(__int64 *, int *))(*v19 + 56))(v19, &v27) >= 0
                                          && v27 < 0 )
                                        {
                                          (*(void (__fastcall **)(__int64 *, char *))(*v19 + 72))(
                                            v19,
                                            (char *)this + 16);
                                        }
                                      }
                                      Instance = v27;
                                      if ( v27 >= 0 )
                                      {
LABEL_29:
                                        Instance = DevPlat::Shared::AppXManifestHelper::GetProductIdAndPublisherId(
                                                     (DevPlat::Shared::AppXManifestHelper *)this,
                                                     (struct _GUID *)this + 5,
                                                     (struct _GUID *)this + 6);
                                        if ( Instance >= 0 )
                                          *((_BYTE *)this + 112) = 1;
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
        }
      }
      else
      {
        Instance = -2147024882;
      }
    }
  }
  else
  {
    Instance = -2147024809;
  }
  VariantClear(&pvarg);
  VariantClear(&v23);
  VariantClear(&v24);
  VariantClear(&v25);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800652a0  mov     [rsp-8+arg_0], rbx
0x1800652a5  push    rbp
0x1800652a6  push    rsi
0x1800652a7  push    rdi
0x1800652a8  push    r12
0x1800652aa  push    r13
0x1800652ac  push    r14
0x1800652ae  push    r15
0x1800652b0  lea     rbp, [rsp-27h]
0x1800652b5  sub     rsp, 0B0h
0x1800652bc  xor     eax, eax
0x1800652be  xorps   xmm0, xmm0
0x1800652c1  xorps   xmm1, xmm1
0x1800652c4  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800652c8  mov     rdi, rcx
0x1800652cb  mov     qword ptr [rbp+57h+var_78+10h], rax
0x1800652cf  xor     r13d, r13d
0x1800652d2  mov     qword ptr [rbp+57h+var_60+10h], rax
0x1800652d6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800652da  mov     [rbp+57h+arg_8], r13w
0x1800652df  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800652e3  mov     qword ptr [rbp+57h+var_48+10h], rax
0x1800652e7  mov     r12, rdx
0x1800652ea  movups  xmmword ptr [rbp+57h+var_78], xmm1
0x1800652ee  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800652f2  movups  xmmword ptr [rbp+57h+var_48], xmm1
0x1800652f6  call    cs:__imp_VariantInit
0x1800652fc  lea     rcx, [rbp+57h+var_78]; pvarg
0x180065300  call    cs:__imp_VariantInit
0x180065306  lea     rcx, [rbp+57h+var_60]; pvarg
0x18006530a  call    cs:__imp_VariantInit
0x180065310  lea     rcx, [rbp+57h+var_48]; pvarg
0x180065314  call    cs:__imp_VariantInit
0x18006531a  test    r12, r12
0x18006531d  jnz     short loc_180065329
0x18006531f  mov     ebx, 80070057h
0x180065324  jmp     loc_180065618
0x180065329  cmp     [rdi+70h], r13b
0x18006532d  jz      short loc_180065339
0x18006532f  mov     ebx, 80004005h
0x180065334  jmp     loc_180065618
0x180065339  mov     eax, 0Bh
0x18006533e  lea     rcx, psz; "XPath"
0x180065345  mov     word ptr [rbp+57h+pvarg], ax
0x180065349  or      eax, 0FFFFFFFFh
0x18006534c  mov     word ptr [rbp+57h+pvarg+8], ax
0x180065350  call    cs:__imp_SysAllocString
0x180065356  test    rax, rax
0x180065359  jz      loc_180065613
0x18006535f  mov     ebx, 8
0x180065364  mov     qword ptr [rbp+57h+var_78+8], rax
0x180065368  mov     word ptr [rbp+57h+var_78], bx
0x18006536c  lea     rcx, aXmlnsMHttpSche; "xmlns:m=\"http://schemas.microsoft.com/"...
0x180065373  call    cs:__imp_SysAllocString
0x180065379  test    rax, rax
0x18006537c  jz      loc_180065613
0x180065382  mov     word ptr [rbp+57h+var_60], bx
0x180065386  mov     qword ptr [rbp+57h+var_60+8], rax
0x18006538a  lea     rcx, [rdi+30h]; this
0x18006538e  lea     rdx, aHttpSchemasMic; "http://schemas.microsoft.com/phone/2013"...
0x180065395  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18006539a  mov     ebx, eax
0x18006539c  test    eax, eax
0x18006539e  js      loc_180065618
0x1800653a4  lea     rdx, aNewparser; "NewParser"
0x1800653ab  lea     rcx, [rdi+18h]; this
0x1800653af  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800653b4  mov     ebx, eax
0x1800653b6  test    eax, eax
0x1800653b8  js      loc_180065618
0x1800653be  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x1800653c5  lea     rcx, [rdi+20h]; this
0x1800653c9  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800653ce  mov     ebx, eax
0x1800653d0  test    eax, eax
0x1800653d2  js      loc_180065618
0x1800653d8  lea     rdx, aSelectionlangu; "SelectionLanguage"
0x1800653df  lea     rcx, [rdi+28h]; this
0x1800653e3  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800653e8  mov     ebx, eax
0x1800653ea  test    eax, eax
0x1800653ec  js      loc_180065618
0x1800653f2  lea     rcx, [rdi+38h]; this
0x1800653f6  lea     rdx, aLocalNamePacka_2; "/*[local-name()='Package']/mp:PhoneIden"...
0x1800653fd  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180065402  mov     ebx, eax
0x180065404  test    eax, eax
0x180065406  js      loc_180065618
0x18006540c  lea     rcx, [rdi+40h]; this
0x180065410  lea     rdx, aPhoneproductid; "PhoneProductId"
0x180065417  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18006541c  mov     ebx, eax
0x18006541e  test    eax, eax
0x180065420  js      loc_180065618
0x180065426  lea     rcx, [rdi+48h]; this
0x18006542a  lea     rdx, aPhonepublisher; "PhonePublisherId"
0x180065431  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180065436  mov     ebx, eax
0x180065438  test    eax, eax
0x18006543a  js      loc_180065618
0x180065440  xor     edx, edx; pUnkOuter
0x180065442  mov     [rsp+0E0h+ppv], rdi; ppv
0x180065447  lea     r9, _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60; riid
0x18006544e  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180065455  lea     r8d, [rdx+1]; dwClsContext
0x180065459  call    cs:__imp_CoCreateInstance
0x18006545f  mov     ebx, eax
0x180065461  test    eax, eax
0x180065463  js      loc_180065618
0x180065469  mov     rcx, [rdi]
0x18006546c  xor     edx, edx
0x18006546e  mov     rax, [rcx]
0x180065471  mov     rax, [rax+1F8h]
0x180065478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006547d  mov     ebx, eax
0x18006547f  test    eax, eax
0x180065481  js      loc_180065618
0x180065487  mov     rcx, [rdi]
0x18006548a  lea     r8, [rbp+57h+var_B0]
0x18006548e  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180065492  mov     rdx, [rdi+18h]
0x180065496  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18006549b  mov     rax, [rcx]
0x18006549e  movaps  [rbp+57h+var_B0], xmm0
0x1800654a2  movsd   [rbp+57h+var_A0], xmm1
0x1800654a7  mov     rax, [rax+280h]
0x1800654ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800654b3  mov     ebx, eax
0x1800654b5  test    eax, eax
0x1800654b7  js      loc_180065618
0x1800654bd  mov     rcx, [rdi]
0x1800654c0  lea     r8, [rbp+57h+var_B0]
0x1800654c4  movups  xmm0, xmmword ptr [rbp+57h+var_60]
0x1800654c8  mov     rdx, [rdi+20h]
0x1800654cc  movsd   xmm1, qword ptr [rbp+57h+var_60+10h]
0x1800654d1  mov     rax, [rcx]
0x1800654d4  movaps  [rbp+57h+var_B0], xmm0
0x1800654d8  movsd   [rbp+57h+var_A0], xmm1
0x1800654dd  mov     rax, [rax+280h]
0x1800654e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800654e9  mov     ebx, eax
0x1800654eb  test    eax, eax
0x1800654ed  js      loc_180065618
0x1800654f3  mov     rcx, [rdi]
0x1800654f6  lea     r8, [rbp+57h+var_B0]
0x1800654fa  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x1800654fe  mov     rdx, [rdi+28h]
0x180065502  movsd   xmm1, qword ptr [rbp+57h+var_78+10h]
0x180065507  mov     rax, [rcx]
0x18006550a  movaps  [rbp+57h+var_B0], xmm0
0x18006550e  movsd   [rbp+57h+var_A0], xmm1
0x180065513  mov     rax, [rax+280h]
0x18006551a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006551f  mov     ebx, eax
0x180065521  test    eax, eax
0x180065523  js      loc_180065618
0x180065529  mov     eax, 0Dh
0x18006552e  mov     qword ptr [rbp+57h+var_48+8], r12
0x180065532  mov     word ptr [rbp+57h+var_48], ax
0x180065536  mov     rcx, r12
0x180065539  mov     rax, [r12]
0x18006553d  mov     rax, [rax+8]
0x180065541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065546  mov     rcx, [rdi]
0x180065549  lea     r8, [rbp+57h+arg_8]
0x18006554d  movups  xmm0, xmmword ptr [rbp+57h+var_48]
0x180065551  lea     rdx, [rbp+57h+var_B0]
0x180065555  movsd   xmm1, qword ptr [rbp+57h+var_48+10h]
0x18006555a  mov     rax, [rcx]
0x18006555d  movaps  [rbp+57h+var_B0], xmm0
0x180065561  movsd   [rbp+57h+var_A0], xmm1
0x180065566  mov     rax, [rax+1D0h]
0x18006556d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065572  mov     ebx, eax
0x180065574  test    eax, eax
0x180065576  js      loc_180065618
0x18006557c  cmp     eax, 1
0x18006557f  jz      short loc_180065588
0x180065581  cmp     [rbp+57h+arg_8], r13w
0x180065586  jnz     short loc_1800655F7
0x180065588  mov     rcx, [rdi]
0x18006558b  lea     rdx, [rdi+8]
0x18006558f  mov     rax, [rcx]
0x180065592  mov     rax, [rax+1E0h]
0x180065599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006559e  mov     ebx, eax
0x1800655a0  test    eax, eax
0x1800655a2  js      short loc_180065618
0x1800655a4  mov     rsi, [rdi+8]
0x1800655a8  mov     ebx, 80004005h
0x1800655ad  test    rsi, rsi
0x1800655b0  jz      short loc_180065618
0x1800655b2  mov     [rbp+57h+arg_10], ebx
0x1800655b5  lea     rbx, [rdi+10h]
0x1800655b9  test    rbx, rbx
0x1800655bc  jz      short loc_1800655F0
0x1800655be  mov     [rbx], r13
0x1800655c1  lea     rdx, [rbp+57h+arg_10]
0x1800655c5  mov     rax, [rsi]
0x1800655c8  mov     rcx, rsi
0x1800655cb  mov     rax, [rax+38h]
0x1800655cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800655d4  test    eax, eax
0x1800655d6  js      short loc_1800655F0
0x1800655d8  cmp     [rbp+57h+arg_10], r13d
0x1800655dc  jge     short loc_1800655F0
0x1800655de  mov     rax, [rsi]
0x1800655e1  mov     rdx, rbx
0x1800655e4  mov     rcx, rsi
0x1800655e7  mov     rax, [rax+48h]
0x1800655eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800655f0  mov     ebx, [rbp+57h+arg_10]
0x1800655f3  test    ebx, ebx
0x1800655f5  js      short loc_180065618
0x1800655f7  lea     r8, [rdi+60h]; struct _GUID *
0x1800655fb  mov     rcx, rdi; this
0x1800655fe  lea     rdx, [rdi+50h]; struct _GUID *
0x180065602  call    ?GetProductIdAndPublisherId@AppXManifestHelper@Shared@DevPlat@@IEBAJPEAU_GUID@@0@Z; DevPlat::Shared::AppXManifestHelper::GetProductIdAndPublisherId(_GUID *,_GUID *)
0x180065607  mov     ebx, eax
0x180065609  test    eax, eax
0x18006560b  js      short loc_180065618
0x18006560d  mov     byte ptr [rdi+70h], 1
0x180065611  jmp     short loc_180065618
0x180065613  mov     ebx, 8007000Eh
0x180065618  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18006561c  call    cs:__imp_VariantClear
0x180065622  lea     rcx, [rbp+57h+var_78]; pvarg
0x180065626  call    cs:__imp_VariantClear
0x18006562c  lea     rcx, [rbp+57h+var_60]; pvarg
0x180065630  call    cs:__imp_VariantClear
0x180065636  lea     rcx, [rbp+57h+var_48]; pvarg
0x18006563a  call    cs:__imp_VariantClear
0x180065640  mov     eax, ebx
0x180065642  mov     rbx, [rsp+0E0h+arg_0]
0x18006564a  add     rsp, 0B0h
0x180065651  pop     r15
0x180065653  pop     r14
0x180065655  pop     r13
0x180065657  pop     r12
0x180065659  pop     rdi
0x18006565a  pop     rsi
0x18006565b  pop     rbp
0x18006565c  retn
```
