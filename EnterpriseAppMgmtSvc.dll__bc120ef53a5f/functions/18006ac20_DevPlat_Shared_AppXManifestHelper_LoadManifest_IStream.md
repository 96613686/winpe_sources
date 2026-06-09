# DevPlat::Shared::AppXManifestHelper::LoadManifest(IStream *)

- ea: `0x18006ac20`
- end: `0x18006b020`
- name: `?LoadManifest@AppXManifestHelper@Shared@DevPlat@@QEAAJPEAUIStream@@@Z`
- size: `1024`
- prototype: `__int64 __fastcall(DevPlat::Shared::AppXManifestHelper *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006a558`

## callees

- `0x1800072ac`
- `0x18006aaf8`
- `0x18006ac20`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006adfd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006adfd`
- `OLEAUT32!__imp_SysAllocString` at `0x18006ace8`
- `OLEAUT32!__imp_SysAllocString` at `0x18006ad11`
- `OLEAUT32!__imp_SysAllocString` at `0x18006ace8`
- `OLEAUT32!__imp_SysAllocString` at `0x18006ad11`
- `OLEAUT32!__imp_VariantInit` at `0x18006ac76`
- `OLEAUT32!__imp_VariantInit` at `0x18006ac86`
- `OLEAUT32!__imp_VariantInit` at `0x18006ac96`
- `OLEAUT32!__imp_VariantInit` at `0x18006aca6`
- `OLEAUT32!__imp_VariantInit` at `0x18006ac76`
- `OLEAUT32!__imp_VariantInit` at `0x18006ac86`
- `OLEAUT32!__imp_VariantInit` at `0x18006ac96`
- `OLEAUT32!__imp_VariantInit` at `0x18006aca6`
- `OLEAUT32!__imp_VariantClear` at `0x18006afc6`
- `OLEAUT32!__imp_VariantClear` at `0x18006afd6`
- `OLEAUT32!__imp_VariantClear` at `0x18006afe6`
- `OLEAUT32!__imp_VariantClear` at `0x18006aff6`
- `OLEAUT32!__imp_VariantClear` at `0x18006afc6`
- `OLEAUT32!__imp_VariantClear` at `0x18006afd6`
- `OLEAUT32!__imp_VariantClear` at `0x18006afe6`
- `OLEAUT32!__imp_VariantClear` at `0x18006aff6`

## string_xrefs

- `0x18006acd6`: `XPath`
- `0x18006ad32`: `http://schemas.microsoft.com/phone/2013/policy`
- `0x18006ad0a`: `xmlns:m="http://schemas.microsoft.com/appx/2010/manifest" xmlns:m2="http://schemas.microsoft.com/appx/2013/manifest" xmlns:mp="http://schemas.microsoft.com/appx/2014/phone/manifest"`

## pseudocode

```c
__int64 __fastcall DevPlat::Shared::AppXManifestHelper::LoadManifest(__int64 **this, struct IStream *a2)
{
  HRESULT Instance; // ebx
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
        Instance = ATL::CComBSTR::Append((ATL::CComBSTR *)(this + 6), L"http://schemas.microsoft.com/phone/2013/policy");
        if ( Instance >= 0 )
        {
          Instance = ATL::CComBSTR::Append((ATL::CComBSTR *)(this + 3), L"NewParser");
          if ( Instance >= 0 )
          {
            Instance = ATL::CComBSTR::Append((ATL::CComBSTR *)(this + 4), L"SelectionNamespaces");
            if ( Instance >= 0 )
            {
              Instance = ATL::CComBSTR::Append((ATL::CComBSTR *)(this + 5), L"SelectionLanguage");
              if ( Instance >= 0 )
              {
                Instance = ATL::CComBSTR::Append(
                             (ATL::CComBSTR *)(this + 7),
                             L"/*[local-name()='Package']/mp:PhoneIdentity");
                if ( Instance >= 0 )
                {
                  Instance = ATL::CComBSTR::Append((ATL::CComBSTR *)(this + 8), L"PhoneProductId");
                  if ( Instance >= 0 )
                  {
                    Instance = ATL::CComBSTR::Append((ATL::CComBSTR *)(this + 9), L"PhonePublisherId");
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
0x18006ac20  mov     [rsp-8+arg_0], rbx
0x18006ac25  push    rbp
0x18006ac26  push    rsi
0x18006ac27  push    rdi
0x18006ac28  push    r12
0x18006ac2a  push    r13
0x18006ac2c  push    r14
0x18006ac2e  push    r15
0x18006ac30  lea     rbp, [rsp-27h]
0x18006ac35  sub     rsp, 0B0h
0x18006ac3c  xor     eax, eax
0x18006ac3e  xorps   xmm0, xmm0
0x18006ac41  xorps   xmm1, xmm1
0x18006ac44  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18006ac48  mov     rdi, rcx
0x18006ac4b  mov     qword ptr [rbp+57h+var_78+10h], rax
0x18006ac4f  xor     r13d, r13d
0x18006ac52  mov     qword ptr [rbp+57h+var_60+10h], rax
0x18006ac56  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18006ac5a  mov     [rbp+57h+arg_8], r13w
0x18006ac5f  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18006ac63  mov     qword ptr [rbp+57h+var_48+10h], rax
0x18006ac67  mov     r12, rdx
0x18006ac6a  movups  xmmword ptr [rbp+57h+var_78], xmm1
0x18006ac6e  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18006ac72  movups  xmmword ptr [rbp+57h+var_48], xmm1
0x18006ac76  call    cs:__imp_VariantInit
0x18006ac7d  nop     dword ptr [rax+rax+00h]
0x18006ac82  lea     rcx, [rbp+57h+var_78]; pvarg
0x18006ac86  call    cs:__imp_VariantInit
0x18006ac8d  nop     dword ptr [rax+rax+00h]
0x18006ac92  lea     rcx, [rbp+57h+var_60]; pvarg
0x18006ac96  call    cs:__imp_VariantInit
0x18006ac9d  nop     dword ptr [rax+rax+00h]
0x18006aca2  lea     rcx, [rbp+57h+var_48]; pvarg
0x18006aca6  call    cs:__imp_VariantInit
0x18006acad  nop     dword ptr [rax+rax+00h]
0x18006acb2  test    r12, r12
0x18006acb5  jnz     short loc_18006ACC1
0x18006acb7  mov     ebx, 80070057h
0x18006acbc  jmp     loc_18006AFC2
0x18006acc1  cmp     [rdi+70h], r13b
0x18006acc5  jz      short loc_18006ACD1
0x18006acc7  mov     ebx, 80004005h
0x18006accc  jmp     loc_18006AFC2
0x18006acd1  mov     eax, 0Bh
0x18006acd6  lea     rcx, psz; "XPath"
0x18006acdd  mov     word ptr [rbp+57h+pvarg], ax
0x18006ace1  or      eax, 0FFFFFFFFh
0x18006ace4  mov     word ptr [rbp+57h+pvarg+8], ax
0x18006ace8  call    cs:__imp_SysAllocString
0x18006acef  nop     dword ptr [rax+rax+00h]
0x18006acf4  test    rax, rax
0x18006acf7  jz      loc_18006AFBD
0x18006acfd  mov     ebx, 8
0x18006ad02  mov     qword ptr [rbp+57h+var_78+8], rax
0x18006ad06  mov     word ptr [rbp+57h+var_78], bx
0x18006ad0a  lea     rcx, aXmlnsMHttpSche; "xmlns:m=\"http://schemas.microsoft.com/"...
0x18006ad11  call    cs:__imp_SysAllocString
0x18006ad18  nop     dword ptr [rax+rax+00h]
0x18006ad1d  test    rax, rax
0x18006ad20  jz      loc_18006AFBD
0x18006ad26  mov     word ptr [rbp+57h+var_60], bx
0x18006ad2a  mov     qword ptr [rbp+57h+var_60+8], rax
0x18006ad2e  lea     rcx, [rdi+30h]; this
0x18006ad32  lea     rdx, aHttpSchemasMic; "http://schemas.microsoft.com/phone/2013"...
0x18006ad39  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18006ad3e  mov     ebx, eax
0x18006ad40  test    eax, eax
0x18006ad42  js      loc_18006AFC2
0x18006ad48  lea     rdx, aNewparser; "NewParser"
0x18006ad4f  lea     rcx, [rdi+18h]; this
0x18006ad53  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18006ad58  mov     ebx, eax
0x18006ad5a  test    eax, eax
0x18006ad5c  js      loc_18006AFC2
0x18006ad62  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18006ad69  lea     rcx, [rdi+20h]; this
0x18006ad6d  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18006ad72  mov     ebx, eax
0x18006ad74  test    eax, eax
0x18006ad76  js      loc_18006AFC2
0x18006ad7c  lea     rdx, aSelectionlangu; "SelectionLanguage"
0x18006ad83  lea     rcx, [rdi+28h]; this
0x18006ad87  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18006ad8c  mov     ebx, eax
0x18006ad8e  test    eax, eax
0x18006ad90  js      loc_18006AFC2
0x18006ad96  lea     rcx, [rdi+38h]; this
0x18006ad9a  lea     rdx, aLocalNamePacka_2; "/*[local-name()='Package']/mp:PhoneIden"...
0x18006ada1  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18006ada6  mov     ebx, eax
0x18006ada8  test    eax, eax
0x18006adaa  js      loc_18006AFC2
0x18006adb0  lea     rcx, [rdi+40h]; this
0x18006adb4  lea     rdx, aPhoneproductid; "PhoneProductId"
0x18006adbb  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18006adc0  mov     ebx, eax
0x18006adc2  test    eax, eax
0x18006adc4  js      loc_18006AFC2
0x18006adca  lea     rcx, [rdi+48h]; this
0x18006adce  lea     rdx, aPhonepublisher; "PhonePublisherId"
0x18006add5  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18006adda  mov     ebx, eax
0x18006addc  test    eax, eax
0x18006adde  js      loc_18006AFC2
0x18006ade4  xor     edx, edx; pUnkOuter
0x18006ade6  mov     [rsp+0E0h+ppv], rdi; ppv
0x18006adeb  lea     r9, _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60; riid
0x18006adf2  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18006adf9  lea     r8d, [rdx+1]; dwClsContext
0x18006adfd  call    cs:__imp_CoCreateInstance
0x18006ae04  nop     dword ptr [rax+rax+00h]
0x18006ae09  mov     ebx, eax
0x18006ae0b  test    eax, eax
0x18006ae0d  js      loc_18006AFC2
0x18006ae13  mov     rcx, [rdi]
0x18006ae16  xor     edx, edx
0x18006ae18  mov     rax, [rcx]
0x18006ae1b  mov     rax, [rax+1F8h]
0x18006ae22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae27  mov     ebx, eax
0x18006ae29  test    eax, eax
0x18006ae2b  js      loc_18006AFC2
0x18006ae31  mov     rcx, [rdi]
0x18006ae34  lea     r8, [rbp+57h+var_B0]
0x18006ae38  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18006ae3c  mov     rdx, [rdi+18h]
0x18006ae40  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18006ae45  mov     rax, [rcx]
0x18006ae48  movaps  [rbp+57h+var_B0], xmm0
0x18006ae4c  movsd   [rbp+57h+var_A0], xmm1
0x18006ae51  mov     rax, [rax+280h]
0x18006ae58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae5d  mov     ebx, eax
0x18006ae5f  test    eax, eax
0x18006ae61  js      loc_18006AFC2
0x18006ae67  mov     rcx, [rdi]
0x18006ae6a  lea     r8, [rbp+57h+var_B0]
0x18006ae6e  movups  xmm0, xmmword ptr [rbp+57h+var_60]
0x18006ae72  mov     rdx, [rdi+20h]
0x18006ae76  movsd   xmm1, qword ptr [rbp+57h+var_60+10h]
0x18006ae7b  mov     rax, [rcx]
0x18006ae7e  movaps  [rbp+57h+var_B0], xmm0
0x18006ae82  movsd   [rbp+57h+var_A0], xmm1
0x18006ae87  mov     rax, [rax+280h]
0x18006ae8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae93  mov     ebx, eax
0x18006ae95  test    eax, eax
0x18006ae97  js      loc_18006AFC2
0x18006ae9d  mov     rcx, [rdi]
0x18006aea0  lea     r8, [rbp+57h+var_B0]
0x18006aea4  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x18006aea8  mov     rdx, [rdi+28h]
0x18006aeac  movsd   xmm1, qword ptr [rbp+57h+var_78+10h]
0x18006aeb1  mov     rax, [rcx]
0x18006aeb4  movaps  [rbp+57h+var_B0], xmm0
0x18006aeb8  movsd   [rbp+57h+var_A0], xmm1
0x18006aebd  mov     rax, [rax+280h]
0x18006aec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aec9  mov     ebx, eax
0x18006aecb  test    eax, eax
0x18006aecd  js      loc_18006AFC2
0x18006aed3  mov     eax, 0Dh
0x18006aed8  mov     qword ptr [rbp+57h+var_48+8], r12
0x18006aedc  mov     word ptr [rbp+57h+var_48], ax
0x18006aee0  mov     rcx, r12
0x18006aee3  mov     rax, [r12]
0x18006aee7  mov     rax, [rax+8]
0x18006aeeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aef0  mov     rcx, [rdi]
0x18006aef3  lea     r8, [rbp+57h+arg_8]
0x18006aef7  movups  xmm0, xmmword ptr [rbp+57h+var_48]
0x18006aefb  lea     rdx, [rbp+57h+var_B0]
0x18006aeff  movsd   xmm1, qword ptr [rbp+57h+var_48+10h]
0x18006af04  mov     rax, [rcx]
0x18006af07  movaps  [rbp+57h+var_B0], xmm0
0x18006af0b  movsd   [rbp+57h+var_A0], xmm1
0x18006af10  mov     rax, [rax+1D0h]
0x18006af17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af1c  mov     ebx, eax
0x18006af1e  test    eax, eax
0x18006af20  js      loc_18006AFC2
0x18006af26  cmp     eax, 1
0x18006af29  jz      short loc_18006AF32
0x18006af2b  cmp     [rbp+57h+arg_8], r13w
0x18006af30  jnz     short loc_18006AFA1
0x18006af32  mov     rcx, [rdi]
0x18006af35  lea     rdx, [rdi+8]
0x18006af39  mov     rax, [rcx]
0x18006af3c  mov     rax, [rax+1E0h]
0x18006af43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af48  mov     ebx, eax
0x18006af4a  test    eax, eax
0x18006af4c  js      short loc_18006AFC2
0x18006af4e  mov     rsi, [rdi+8]
0x18006af52  mov     ebx, 80004005h
0x18006af57  test    rsi, rsi
0x18006af5a  jz      short loc_18006AFC2
0x18006af5c  mov     [rbp+57h+arg_10], ebx
0x18006af5f  lea     rbx, [rdi+10h]
0x18006af63  test    rbx, rbx
0x18006af66  jz      short loc_18006AF9A
0x18006af68  mov     [rbx], r13
0x18006af6b  lea     rdx, [rbp+57h+arg_10]
0x18006af6f  mov     rax, [rsi]
0x18006af72  mov     rcx, rsi
0x18006af75  mov     rax, [rax+38h]
0x18006af79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af7e  test    eax, eax
0x18006af80  js      short loc_18006AF9A
0x18006af82  cmp     [rbp+57h+arg_10], r13d
0x18006af86  jge     short loc_18006AF9A
0x18006af88  mov     rax, [rsi]
0x18006af8b  mov     rdx, rbx
0x18006af8e  mov     rcx, rsi
0x18006af91  mov     rax, [rax+48h]
0x18006af95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af9a  mov     ebx, [rbp+57h+arg_10]
0x18006af9d  test    ebx, ebx
0x18006af9f  js      short loc_18006AFC2
0x18006afa1  lea     r8, [rdi+60h]; struct _GUID *
0x18006afa5  mov     rcx, rdi; this
0x18006afa8  lea     rdx, [rdi+50h]; struct _GUID *
0x18006afac  call    ?GetProductIdAndPublisherId@AppXManifestHelper@Shared@DevPlat@@IEBAJPEAU_GUID@@0@Z; DevPlat::Shared::AppXManifestHelper::GetProductIdAndPublisherId(_GUID *,_GUID *)
0x18006afb1  mov     ebx, eax
0x18006afb3  test    eax, eax
0x18006afb5  js      short loc_18006AFC2
0x18006afb7  mov     byte ptr [rdi+70h], 1
0x18006afbb  jmp     short loc_18006AFC2
0x18006afbd  mov     ebx, 8007000Eh
0x18006afc2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18006afc6  call    cs:__imp_VariantClear
0x18006afcd  nop     dword ptr [rax+rax+00h]
0x18006afd2  lea     rcx, [rbp+57h+var_78]; pvarg
0x18006afd6  call    cs:__imp_VariantClear
0x18006afdd  nop     dword ptr [rax+rax+00h]
0x18006afe2  lea     rcx, [rbp+57h+var_60]; pvarg
0x18006afe6  call    cs:__imp_VariantClear
0x18006afed  nop     dword ptr [rax+rax+00h]
0x18006aff2  lea     rcx, [rbp+57h+var_48]; pvarg
0x18006aff6  call    cs:__imp_VariantClear
0x18006affd  nop     dword ptr [rax+rax+00h]
0x18006b002  mov     eax, ebx
0x18006b004  mov     rbx, [rsp+0E0h+arg_0]
0x18006b00c  add     rsp, 0B0h
0x18006b013  pop     r15
0x18006b015  pop     r14
0x18006b017  pop     r13
0x18006b019  pop     r12
0x18006b01b  pop     rdi
0x18006b01c  pop     rsi
0x18006b01d  pop     rbp
0x18006b01e  retn
```
