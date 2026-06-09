# EnterpriseXmlPolicyHelper::LoadPolicyXml(ushort const *,bool)

- ea: `0x180030fc4`
- end: `0x18003141d`
- name: `?LoadPolicyXml@EnterpriseXmlPolicyHelper@@IEAAJPEBG_N@Z`
- size: `1113`
- prototype: `__int64 __fastcall(EnterpriseXmlPolicyHelper *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f4dc`

## callees

- `0x18000702c`
- `0x180030c4c`
- `0x180030cbc`
- `0x180030d74`
- `0x180030e90`
- `0x180030f78`
- `0x180030fc4`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031154`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031181`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031154`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031181`
- `OLEAUT32!__imp_SysAllocString` at `0x18003109c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800310bf`
- `OLEAUT32!__imp_SysAllocString` at `0x18003109c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800310bf`
- `OLEAUT32!__imp_VariantInit` at `0x18003102b`
- `OLEAUT32!__imp_VariantInit` at `0x180031035`
- `OLEAUT32!__imp_VariantInit` at `0x18003103f`
- `OLEAUT32!__imp_VariantInit` at `0x180031049`
- `OLEAUT32!__imp_VariantInit` at `0x180031053`
- `OLEAUT32!__imp_VariantInit` at `0x18003105d`
- `OLEAUT32!__imp_VariantInit` at `0x18003102b`
- `OLEAUT32!__imp_VariantInit` at `0x180031035`
- `OLEAUT32!__imp_VariantInit` at `0x18003103f`
- `OLEAUT32!__imp_VariantInit` at `0x180031049`
- `OLEAUT32!__imp_VariantInit` at `0x180031053`
- `OLEAUT32!__imp_VariantInit` at `0x18003105d`
- `OLEAUT32!__imp_VariantClear` at `0x1800313cf`
- `OLEAUT32!__imp_VariantClear` at `0x1800313d9`
- `OLEAUT32!__imp_VariantClear` at `0x1800313e3`
- `OLEAUT32!__imp_VariantClear` at `0x1800313ed`
- `OLEAUT32!__imp_VariantClear` at `0x1800313f7`
- `OLEAUT32!__imp_VariantClear` at `0x180031401`
- `OLEAUT32!__imp_VariantClear` at `0x1800313cf`
- `OLEAUT32!__imp_VariantClear` at `0x1800313d9`
- `OLEAUT32!__imp_VariantClear` at `0x1800313e3`
- `OLEAUT32!__imp_VariantClear` at `0x1800313ed`
- `OLEAUT32!__imp_VariantClear` at `0x1800313f7`
- `OLEAUT32!__imp_VariantClear` at `0x180031401`

## string_xrefs

- `0x180031091`: `XPath`
- `0x1800310b8`: `xmlns:p="http://schemas.microsoft.com/phone/2013/policy"`

## pseudocode

```c
__int64 __fastcall EnterpriseXmlPolicyHelper::LoadPolicyXml(
        EnterpriseXmlPolicyHelper *this,
        const unsigned __int16 *a2)
{
  int Instance; // ebx
  BSTR v5; // rax
  BSTR v6; // rax
  const unsigned __int16 *v7; // rax
  EnterpriseXmlPolicyHelper *v8; // rcx
  __int64 **v9; // rsi
  __int64 **v10; // r14
  __int64 *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 *v20; // rcx
  __int64 *v21; // rcx
  __int64 v22; // rax
  __int64 *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  EnterpriseXmlPolicyHelper *v27; // rcx
  struct IXMLDOMParseError *v28; // rdx
  VARIANTARG v30; // [rsp+30h] [rbp-99h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-79h] BYREF
  VARIANTARG v32; // [rsp+68h] [rbp-61h] BYREF
  VARIANTARG v33; // [rsp+80h] [rbp-49h] BYREF
  VARIANTARG v34; // [rsp+98h] [rbp-31h] BYREF
  VARIANTARG v35; // [rsp+B0h] [rbp-19h] BYREF
  VARIANTARG v36; // [rsp+C8h] [rbp-1h] BYREF
  __int16 v37; // [rsp+140h] [rbp+77h] BYREF

  v37 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v32, 0, sizeof(v32));
  memset(&v33, 0, sizeof(v33));
  memset(&v35, 0, sizeof(v35));
  memset(&v36, 0, sizeof(v36));
  memset(&v34, 0, sizeof(v34));
  VariantInit(&pvarg);
  VariantInit(&v32);
  VariantInit(&v33);
  VariantInit(&v35);
  VariantInit(&v36);
  VariantInit(&v34);
  if ( !a2 )
  {
    Instance = -2147024809;
    goto LABEL_34;
  }
  if ( *((_DWORD *)this + 3) != -1 )
  {
LABEL_4:
    Instance = -2147467259;
    goto LABEL_34;
  }
  pvarg.iVal = -1;
  pvarg.vt = 11;
  v5 = SysAllocString(L"XPath");
  if ( !v5
    || (v33.llVal = (LONGLONG)v5,
        v33.vt = 8,
        (v6 = SysAllocString(L"xmlns:p=\"http://schemas.microsoft.com/phone/2013/policy\"")) == 0) )
  {
    Instance = -2147024882;
    goto LABEL_34;
  }
  v34.vt = 8;
  v34.llVal = (LONGLONG)v6;
  v7 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(EnterpriseXmlPolicyHelper *))this)(this);
  Instance = EnterpriseXmlPolicyHelper::InitializeVariantFromString(v8, v7, &v35);
  if ( Instance >= 0 )
  {
    Instance = ATL::CComBSTR::Append((const void **)this + 2, a2);
    if ( Instance >= 0 )
    {
      if ( !*a2 )
      {
        *((_DWORD *)this + 2) = 0;
        Instance = 0;
        *((_DWORD *)this + 3) = 0;
        goto LABEL_34;
      }
      Instance = EnterpriseXmlPolicyHelper::InitializeStrings(this);
      if ( Instance >= 0 )
      {
        v9 = (__int64 **)((char *)this + 24);
        Instance = CoCreateInstance(
                     &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
                     0,
                     1u,
                     &GUID_2933bf96_7b36_11d2_b20e_00c04f983e60,
                     (LPVOID *)this + 3);
        if ( Instance >= 0 )
        {
          v10 = (__int64 **)((char *)this + 40);
          Instance = CoCreateInstance(
                       &GUID_88d96a07_f192_11d4_a65f_0040963251e5,
                       0,
                       1u,
                       &GUID_50ea08b0_dd1b_4664_9a50_c2f40f4bd79a,
                       (LPVOID *)this + 5);
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(**v9 + 504))(*v9, 0);
            if ( Instance >= 0 )
            {
              v11 = *v9;
              v12 = *((_QWORD *)this + 7);
              v13 = **v9;
              v30 = pvarg;
              Instance = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v13 + 640))(v11, v12, &v30);
              if ( Instance >= 0 )
              {
                v14 = *v9;
                v15 = *((_QWORD *)this + 8);
                v16 = **v9;
                v30 = v34;
                Instance = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v16 + 640))(v14, v15, &v30);
                if ( Instance >= 0 )
                {
                  v17 = *v9;
                  v18 = *((_QWORD *)this + 9);
                  v19 = **v9;
                  v30 = v33;
                  Instance = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v19 + 640))(v17, v18, &v30);
                  if ( Instance >= 0 )
                  {
                    v20 = *v10;
                    v32.vt = 13;
                    v32.llVal = (LONGLONG)v20;
                    (*(void (__fastcall **)(__int64 *))(*v20 + 8))(v20);
                    v21 = *v9;
                    v22 = **v9;
                    v30 = v32;
                    Instance = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *))(v22 + 624))(v21, &v30);
                    if ( Instance >= 0 )
                    {
                      v23 = *v10;
                      v24 = *((_QWORD *)this + 10);
                      v25 = **v10;
                      v30 = v35;
                      Instance = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v25 + 56))(
                                   v23,
                                   v24,
                                   &v30);
                      if ( Instance >= 0 )
                      {
                        Instance = (*(__int64 (__fastcall **)(__int64 *, __int64))(**v10 + 120))(*v10, 0xFFFFFFFFLL);
                        if ( Instance >= 0 )
                        {
                          Instance = (*(__int64 (__fastcall **)(__int64 *))(**v10 + 112))(*v10);
                          if ( Instance >= 0 )
                          {
                            v26 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int16 *))(**v9 + 520))(
                                    *v9,
                                    *((_QWORD *)this + 2),
                                    &v37);
                            Instance = v26;
                            if ( v26 >= 0 )
                            {
                              if ( v26 == 1 || !v37 )
                              {
                                Instance = (*(__int64 (__fastcall **)(__int64 *, char *))(**v9 + 480))(
                                             *v9,
                                             (char *)this + 32);
                                if ( Instance < 0 )
                                  goto LABEL_34;
                                v28 = (struct IXMLDOMParseError *)*((_QWORD *)this + 4);
                                if ( !v28 )
                                  goto LABEL_4;
                              }
                              else
                              {
                                Instance = (*(__int64 (__fastcall **)(__int64 *, char *))(**v9 + 632))(
                                             *v9,
                                             (char *)this + 32);
                                if ( Instance < 0 )
                                  goto LABEL_34;
                                v28 = (struct IXMLDOMParseError *)*((_QWORD *)this + 4);
                                if ( !v28 )
                                  goto LABEL_31;
                              }
                              Instance = EnterpriseXmlPolicyHelper::GetParseError(
                                           v27,
                                           v28,
                                           (unsigned __int16 **)this + 6);
                              if ( Instance < 0 )
                                goto LABEL_34;
LABEL_31:
                              Instance = EnterpriseXmlPolicyHelper::GetVersion(this, (unsigned int *)this + 2);
                              if ( Instance >= 0 )
                                Instance = EnterpriseXmlPolicyHelper::GetPolicyType(
                                             this,
                                             (EnterpriseXmlPolicyHelper *)((char *)this + 12));
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
LABEL_34:
  VariantClear(&pvarg);
  VariantClear(&v32);
  VariantClear(&v33);
  VariantClear(&v35);
  VariantClear(&v36);
  VariantClear(&v34);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180030fc4  mov     byte ptr [rsp-8+arg_10], r8b
0x180030fc9  push    rbp
0x180030fca  push    rbx
0x180030fcb  push    rsi
0x180030fcc  push    rdi
0x180030fcd  push    r12
0x180030fcf  push    r13
0x180030fd1  push    r14
0x180030fd3  push    r15
0x180030fd5  lea     rbp, [rsp-1Fh]
0x180030fda  sub     rsp, 0E8h
0x180030fe1  xor     eax, eax
0x180030fe3  xorps   xmm0, xmm0
0x180030fe6  xorps   xmm1, xmm1
0x180030fe9  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180030fed  mov     rdi, rcx
0x180030ff0  mov     qword ptr [rbp+57h+var_B8+10h], rax
0x180030ff4  xor     r13d, r13d
0x180030ff7  mov     qword ptr [rbp+57h+var_A0+10h], rax
0x180030ffb  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180030fff  mov     [rbp+57h+arg_10], r13w
0x180031004  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180031008  mov     qword ptr [rbp+57h+var_70+10h], rax
0x18003100c  mov     rsi, rdx
0x18003100f  movups  xmmword ptr [rbp+57h+var_B8], xmm1
0x180031013  mov     qword ptr [rbp+57h+var_58+10h], rax
0x180031017  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x18003101b  mov     qword ptr [rbp+57h+var_88+10h], rax
0x18003101f  movups  xmmword ptr [rbp+57h+var_70], xmm1
0x180031023  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180031027  movups  xmmword ptr [rbp+57h+var_88], xmm1
0x18003102b  call    cs:__imp_VariantInit
0x180031031  lea     rcx, [rbp+57h+var_B8]; pvarg
0x180031035  call    cs:__imp_VariantInit
0x18003103b  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18003103f  call    cs:__imp_VariantInit
0x180031045  lea     rcx, [rbp+57h+var_70]; pvarg
0x180031049  call    cs:__imp_VariantInit
0x18003104f  lea     rcx, [rbp+57h+var_58]; pvarg
0x180031053  call    cs:__imp_VariantInit
0x180031059  lea     rcx, [rbp+57h+var_88]; pvarg
0x18003105d  call    cs:__imp_VariantInit
0x180031063  test    rsi, rsi
0x180031066  jnz     short loc_180031072
0x180031068  mov     ebx, 80070057h
0x18003106d  jmp     loc_1800313CB
0x180031072  lea     r15, [rdi+0Ch]
0x180031076  or      ecx, 0FFFFFFFFh
0x180031079  cmp     [r15], ecx
0x18003107c  jz      short loc_180031088
0x18003107e  mov     ebx, 80004005h
0x180031083  jmp     loc_1800313CB
0x180031088  mov     eax, 0Bh
0x18003108d  mov     word ptr [rbp+57h+pvarg+8], cx
0x180031091  lea     rcx, psz; "XPath"
0x180031098  mov     word ptr [rbp+57h+pvarg], ax
0x18003109c  call    cs:__imp_SysAllocString
0x1800310a2  test    rax, rax
0x1800310a5  jz      loc_1800313C6
0x1800310ab  mov     ebx, 8
0x1800310b0  mov     qword ptr [rbp+57h+var_A0+8], rax
0x1800310b4  mov     word ptr [rbp+57h+var_A0], bx
0x1800310b8  lea     rcx, aXmlnsPHttpSche; "xmlns:p=\"http://schemas.microsoft.com/"...
0x1800310bf  call    cs:__imp_SysAllocString
0x1800310c5  test    rax, rax
0x1800310c8  jz      loc_1800313C6
0x1800310ce  mov     word ptr [rbp+57h+var_88], bx
0x1800310d2  mov     qword ptr [rbp+57h+var_88+8], rax
0x1800310d6  mov     rax, [rdi]
0x1800310d9  mov     rcx, rdi
0x1800310dc  mov     rax, [rax]
0x1800310df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310e4  mov     rdx, rax; unsigned __int16 *
0x1800310e7  lea     r8, [rbp+57h+var_70]; struct tagVARIANT *
0x1800310eb  call    ?InitializeVariantFromString@EnterpriseXmlPolicyHelper@@IEAAJPEBGPEAUtagVARIANT@@@Z; EnterpriseXmlPolicyHelper::InitializeVariantFromString(ushort const *,tagVARIANT *)
0x1800310f0  mov     ebx, eax
0x1800310f2  test    eax, eax
0x1800310f4  js      loc_1800313CB
0x1800310fa  mov     rdx, rsi; unsigned __int16 *
0x1800310fd  lea     rcx, [rdi+10h]; this
0x180031101  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180031106  mov     ebx, eax
0x180031108  test    eax, eax
0x18003110a  js      loc_1800313CB
0x180031110  cmp     [rsi], r13w
0x180031114  jnz     short loc_180031125
0x180031116  mov     [rdi+8], r13d
0x18003111a  mov     ebx, r13d
0x18003111d  mov     [r15], r13d
0x180031120  jmp     loc_1800313CB
0x180031125  mov     rcx, rdi; this
0x180031128  call    ?InitializeStrings@EnterpriseXmlPolicyHelper@@IEAAJXZ; EnterpriseXmlPolicyHelper::InitializeStrings(void)
0x18003112d  mov     ebx, eax
0x18003112f  test    eax, eax
0x180031131  js      loc_1800313CB
0x180031137  xor     edx, edx; pUnkOuter
0x180031139  lea     rsi, [rdi+18h]
0x18003113d  lea     r9, _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60; riid
0x180031144  mov     [rsp+120h+ppv], rsi; ppv
0x180031149  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180031150  lea     r8d, [rdx+1]; dwClsContext
0x180031154  call    cs:__imp_CoCreateInstance
0x18003115a  mov     ebx, eax
0x18003115c  test    eax, eax
0x18003115e  js      loc_1800313CB
0x180031164  xor     edx, edx; pUnkOuter
0x180031166  lea     r14, [rdi+28h]
0x18003116a  lea     r9, _GUID_50ea08b0_dd1b_4664_9a50_c2f40f4bd79a; riid
0x180031171  mov     [rsp+120h+ppv], r14; ppv
0x180031176  lea     rcx, _GUID_88d96a07_f192_11d4_a65f_0040963251e5; rclsid
0x18003117d  lea     r8d, [rdx+1]; dwClsContext
0x180031181  call    cs:__imp_CoCreateInstance
0x180031187  mov     ebx, eax
0x180031189  test    eax, eax
0x18003118b  js      loc_1800313CB
0x180031191  mov     rcx, [rsi]
0x180031194  xor     edx, edx
0x180031196  mov     rax, [rcx]
0x180031199  mov     rax, [rax+1F8h]
0x1800311a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311a5  mov     ebx, eax
0x1800311a7  test    eax, eax
0x1800311a9  js      loc_1800313CB
0x1800311af  mov     rcx, [rsi]
0x1800311b2  lea     r8, [rsp+120h+var_F0]
0x1800311b7  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800311bb  mov     rdx, [rdi+38h]
0x1800311bf  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800311c4  mov     rax, [rcx]
0x1800311c7  movaps  [rsp+120h+var_F0], xmm0
0x1800311cc  movsd   [rsp+120h+var_E0], xmm1
0x1800311d2  mov     rax, [rax+280h]
0x1800311d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311de  mov     ebx, eax
0x1800311e0  test    eax, eax
0x1800311e2  js      loc_1800313CB
0x1800311e8  mov     rcx, [rsi]
0x1800311eb  lea     r8, [rsp+120h+var_F0]
0x1800311f0  movups  xmm0, xmmword ptr [rbp+57h+var_88]
0x1800311f4  mov     rdx, [rdi+40h]
0x1800311f8  movsd   xmm1, qword ptr [rbp+57h+var_88+10h]
0x1800311fd  mov     rax, [rcx]
0x180031200  movaps  [rsp+120h+var_F0], xmm0
0x180031205  movsd   [rsp+120h+var_E0], xmm1
0x18003120b  mov     rax, [rax+280h]
0x180031212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031217  mov     ebx, eax
0x180031219  test    eax, eax
0x18003121b  js      loc_1800313CB
0x180031221  mov     rcx, [rsi]
0x180031224  lea     r8, [rsp+120h+var_F0]
0x180031229  movups  xmm0, xmmword ptr [rbp+57h+var_A0]
0x18003122d  mov     rdx, [rdi+48h]
0x180031231  movsd   xmm1, qword ptr [rbp+57h+var_A0+10h]
0x180031236  mov     rax, [rcx]
0x180031239  movaps  [rsp+120h+var_F0], xmm0
0x18003123e  movsd   [rsp+120h+var_E0], xmm1
0x180031244  mov     rax, [rax+280h]
0x18003124b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031250  mov     ebx, eax
0x180031252  test    eax, eax
0x180031254  js      loc_1800313CB
0x18003125a  mov     rcx, [r14]
0x18003125d  mov     eax, 0Dh
0x180031262  mov     word ptr [rbp+57h+var_B8], ax
0x180031266  mov     qword ptr [rbp+57h+var_B8+8], rcx
0x18003126a  mov     rax, [rcx]
0x18003126d  mov     rax, [rax+8]
0x180031271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031276  mov     rcx, [rsi]
0x180031279  lea     rdx, [rsp+120h+var_F0]
0x18003127e  movups  xmm0, xmmword ptr [rbp+57h+var_B8]
0x180031282  movsd   xmm1, qword ptr [rbp+57h+var_B8+10h]
0x180031287  mov     rax, [rcx]
0x18003128a  movaps  [rsp+120h+var_F0], xmm0
0x18003128f  movsd   [rsp+120h+var_E0], xmm1
0x180031295  mov     rax, [rax+270h]
0x18003129c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800312a1  mov     ebx, eax
0x1800312a3  test    eax, eax
0x1800312a5  js      loc_1800313CB
0x1800312ab  mov     rcx, [r14]
0x1800312ae  lea     r8, [rsp+120h+var_F0]
0x1800312b3  movups  xmm0, xmmword ptr [rbp+57h+var_70]
0x1800312b7  mov     rdx, [rdi+50h]
0x1800312bb  movsd   xmm1, qword ptr [rbp+57h+var_70+10h]
0x1800312c0  mov     rax, [rcx]
0x1800312c3  movaps  [rsp+120h+var_F0], xmm0
0x1800312c8  movsd   [rsp+120h+var_E0], xmm1
0x1800312ce  mov     rax, [rax+38h]
0x1800312d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800312d7  mov     ebx, eax
0x1800312d9  test    eax, eax
0x1800312db  js      loc_1800313CB
0x1800312e1  mov     rcx, [r14]
0x1800312e4  or      edx, 0FFFFFFFFh
0x1800312e7  mov     rax, [rcx]
0x1800312ea  mov     rax, [rax+78h]
0x1800312ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800312f3  mov     ebx, eax
0x1800312f5  test    eax, eax
0x1800312f7  js      loc_1800313CB
0x1800312fd  mov     rcx, [r14]
0x180031300  mov     rax, [rcx]
0x180031303  mov     rax, [rax+70h]
0x180031307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003130c  mov     ebx, eax
0x18003130e  test    eax, eax
0x180031310  js      loc_1800313CB
0x180031316  mov     rcx, [rsi]
0x180031319  lea     r8, [rbp+57h+arg_10]
0x18003131d  mov     rdx, [rdi+10h]
0x180031321  mov     rax, [rcx]
0x180031324  mov     rax, [rax+208h]
0x18003132b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031330  mov     ebx, eax
0x180031332  test    eax, eax
0x180031334  js      loc_1800313CB
0x18003133a  cmp     eax, 1
0x18003133d  jz      short loc_18003136D
0x18003133f  cmp     [rbp+57h+arg_10], r13w
0x180031344  jz      short loc_18003136D
0x180031346  mov     rcx, [rsi]
0x180031349  lea     rdx, [rdi+20h]
0x18003134d  mov     rax, [rcx]
0x180031350  mov     rax, [rax+278h]
0x180031357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003135c  mov     ebx, eax
0x18003135e  test    eax, eax
0x180031360  js      short loc_1800313CB
0x180031362  mov     rdx, [rdi+20h]
0x180031366  test    rdx, rdx
0x180031369  jz      short loc_1800313A5
0x18003136b  jmp     short loc_180031396
0x18003136d  mov     rcx, [rsi]
0x180031370  lea     rdx, [rdi+20h]
0x180031374  mov     rax, [rcx]
0x180031377  mov     rax, [rax+1E0h]
0x18003137e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031383  mov     ebx, eax
0x180031385  test    eax, eax
0x180031387  js      short loc_1800313CB
0x180031389  mov     rdx, [rdi+20h]; struct IXMLDOMParseError *
0x18003138d  test    rdx, rdx
0x180031390  jz      loc_18003107E
0x180031396  lea     r8, [rdi+30h]; unsigned __int16 **
0x18003139a  call    ?GetParseError@EnterpriseXmlPolicyHelper@@IEAAJPEAUIXMLDOMParseError@@PEAPEAG@Z; EnterpriseXmlPolicyHelper::GetParseError(IXMLDOMParseError *,ushort * *)
0x18003139f  mov     ebx, eax
0x1800313a1  test    eax, eax
0x1800313a3  js      short loc_1800313CB
0x1800313a5  lea     rdx, [rdi+8]; unsigned int *
0x1800313a9  mov     rcx, rdi; this
0x1800313ac  call    ?GetVersion@EnterpriseXmlPolicyHelper@@IEBAJPEAK@Z; EnterpriseXmlPolicyHelper::GetVersion(ulong *)
0x1800313b1  mov     ebx, eax
0x1800313b3  test    eax, eax
0x1800313b5  js      short loc_1800313CB
0x1800313b7  mov     rdx, r15; enum PolicyType *
0x1800313ba  mov     rcx, rdi; this
0x1800313bd  call    ?GetPolicyType@EnterpriseXmlPolicyHelper@@IEBAJPEAW4PolicyType@@@Z; EnterpriseXmlPolicyHelper::GetPolicyType(PolicyType *)
0x1800313c2  mov     ebx, eax
0x1800313c4  jmp     short loc_1800313CB
0x1800313c6  mov     ebx, 8007000Eh
0x1800313cb  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800313cf  call    cs:__imp_VariantClear
0x1800313d5  lea     rcx, [rbp+57h+var_B8]; pvarg
0x1800313d9  call    cs:__imp_VariantClear
0x1800313df  lea     rcx, [rbp+57h+var_A0]; pvarg
0x1800313e3  call    cs:__imp_VariantClear
0x1800313e9  lea     rcx, [rbp+57h+var_70]; pvarg
0x1800313ed  call    cs:__imp_VariantClear
0x1800313f3  lea     rcx, [rbp+57h+var_58]; pvarg
0x1800313f7  call    cs:__imp_VariantClear
0x1800313fd  lea     rcx, [rbp+57h+var_88]; pvarg
0x180031401  call    cs:__imp_VariantClear
0x180031407  mov     eax, ebx
0x180031409  add     rsp, 0E8h
0x180031410  pop     r15
0x180031412  pop     r14
0x180031414  pop     r13
0x180031416  pop     r12
0x180031418  pop     rdi
0x180031419  pop     rsi
0x18003141a  pop     rbx
0x18003141b  pop     rbp
0x18003141c  retn
```
