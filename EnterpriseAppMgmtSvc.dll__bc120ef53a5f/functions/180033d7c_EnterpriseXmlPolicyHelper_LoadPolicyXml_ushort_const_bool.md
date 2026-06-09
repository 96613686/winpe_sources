# EnterpriseXmlPolicyHelper::LoadPolicyXml(ushort const *,bool)

- ea: `0x180033d7c`
- end: `0x180034236`
- name: `?LoadPolicyXml@EnterpriseXmlPolicyHelper@@IEAAJPEBG_N@Z`
- size: `1210`
- prototype: `__int64 __fastcall(EnterpriseXmlPolicyHelper *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003217c`

## callees

- `0x1800072ac`
- `0x1800339e0`
- `0x180033a50`
- `0x180033b08`
- `0x180033c40`
- `0x180033d2c`
- `0x180033d7c`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033f3c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033f6f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033f3c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033f6f`
- `OLEAUT32!__imp_SysAllocString` at `0x180033e78`
- `OLEAUT32!__imp_SysAllocString` at `0x180033ea1`
- `OLEAUT32!__imp_SysAllocString` at `0x180033e78`
- `OLEAUT32!__imp_SysAllocString` at `0x180033ea1`
- `OLEAUT32!__imp_VariantInit` at `0x180033de3`
- `OLEAUT32!__imp_VariantInit` at `0x180033df3`
- `OLEAUT32!__imp_VariantInit` at `0x180033e03`
- `OLEAUT32!__imp_VariantInit` at `0x180033e13`
- `OLEAUT32!__imp_VariantInit` at `0x180033e23`
- `OLEAUT32!__imp_VariantInit` at `0x180033e33`
- `OLEAUT32!__imp_VariantInit` at `0x180033de3`
- `OLEAUT32!__imp_VariantInit` at `0x180033df3`
- `OLEAUT32!__imp_VariantInit` at `0x180033e03`
- `OLEAUT32!__imp_VariantInit` at `0x180033e13`
- `OLEAUT32!__imp_VariantInit` at `0x180033e23`
- `OLEAUT32!__imp_VariantInit` at `0x180033e33`
- `OLEAUT32!__imp_VariantClear` at `0x1800341c3`
- `OLEAUT32!__imp_VariantClear` at `0x1800341d3`
- `OLEAUT32!__imp_VariantClear` at `0x1800341e3`
- `OLEAUT32!__imp_VariantClear` at `0x1800341f3`
- `OLEAUT32!__imp_VariantClear` at `0x180034203`
- `OLEAUT32!__imp_VariantClear` at `0x180034213`
- `OLEAUT32!__imp_VariantClear` at `0x1800341c3`
- `OLEAUT32!__imp_VariantClear` at `0x1800341d3`
- `OLEAUT32!__imp_VariantClear` at `0x1800341e3`
- `OLEAUT32!__imp_VariantClear` at `0x1800341f3`
- `OLEAUT32!__imp_VariantClear` at `0x180034203`
- `OLEAUT32!__imp_VariantClear` at `0x180034213`

## string_xrefs

- `0x180033e9a`: `xmlns:p="http://schemas.microsoft.com/phone/2013/policy"`
- `0x180033e6d`: `XPath`

## pseudocode

```c
__int64 __fastcall EnterpriseXmlPolicyHelper::LoadPolicyXml(
        EnterpriseXmlPolicyHelper *this,
        const unsigned __int16 *a2)
{
  HRESULT Instance; // ebx
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
    Instance = ATL::CComBSTR::Append((EnterpriseXmlPolicyHelper *)((char *)this + 16), a2);
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
0x180033d7c  mov     byte ptr [rsp-8+arg_10], r8b
0x180033d81  push    rbp
0x180033d82  push    rbx
0x180033d83  push    rsi
0x180033d84  push    rdi
0x180033d85  push    r12
0x180033d87  push    r13
0x180033d89  push    r14
0x180033d8b  push    r15
0x180033d8d  lea     rbp, [rsp-1Fh]
0x180033d92  sub     rsp, 0E8h
0x180033d99  xor     eax, eax
0x180033d9b  xorps   xmm0, xmm0
0x180033d9e  xorps   xmm1, xmm1
0x180033da1  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180033da5  mov     rdi, rcx
0x180033da8  mov     qword ptr [rbp+57h+var_B8+10h], rax
0x180033dac  xor     r13d, r13d
0x180033daf  mov     qword ptr [rbp+57h+var_A0+10h], rax
0x180033db3  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180033db7  mov     [rbp+57h+arg_10], r13w
0x180033dbc  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180033dc0  mov     qword ptr [rbp+57h+var_70+10h], rax
0x180033dc4  mov     rsi, rdx
0x180033dc7  movups  xmmword ptr [rbp+57h+var_B8], xmm1
0x180033dcb  mov     qword ptr [rbp+57h+var_58+10h], rax
0x180033dcf  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x180033dd3  mov     qword ptr [rbp+57h+var_88+10h], rax
0x180033dd7  movups  xmmword ptr [rbp+57h+var_70], xmm1
0x180033ddb  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180033ddf  movups  xmmword ptr [rbp+57h+var_88], xmm1
0x180033de3  call    cs:__imp_VariantInit
0x180033dea  nop     dword ptr [rax+rax+00h]
0x180033def  lea     rcx, [rbp+57h+var_B8]; pvarg
0x180033df3  call    cs:__imp_VariantInit
0x180033dfa  nop     dword ptr [rax+rax+00h]
0x180033dff  lea     rcx, [rbp+57h+var_A0]; pvarg
0x180033e03  call    cs:__imp_VariantInit
0x180033e0a  nop     dword ptr [rax+rax+00h]
0x180033e0f  lea     rcx, [rbp+57h+var_70]; pvarg
0x180033e13  call    cs:__imp_VariantInit
0x180033e1a  nop     dword ptr [rax+rax+00h]
0x180033e1f  lea     rcx, [rbp+57h+var_58]; pvarg
0x180033e23  call    cs:__imp_VariantInit
0x180033e2a  nop     dword ptr [rax+rax+00h]
0x180033e2f  lea     rcx, [rbp+57h+var_88]; pvarg
0x180033e33  call    cs:__imp_VariantInit
0x180033e3a  nop     dword ptr [rax+rax+00h]
0x180033e3f  test    rsi, rsi
0x180033e42  jnz     short loc_180033E4E
0x180033e44  mov     ebx, 80070057h
0x180033e49  jmp     loc_1800341BF
0x180033e4e  lea     r15, [rdi+0Ch]
0x180033e52  or      ecx, 0FFFFFFFFh
0x180033e55  cmp     [r15], ecx
0x180033e58  jz      short loc_180033E64
0x180033e5a  mov     ebx, 80004005h
0x180033e5f  jmp     loc_1800341BF
0x180033e64  mov     eax, 0Bh
0x180033e69  mov     word ptr [rbp+57h+pvarg+8], cx
0x180033e6d  lea     rcx, psz; "XPath"
0x180033e74  mov     word ptr [rbp+57h+pvarg], ax
0x180033e78  call    cs:__imp_SysAllocString
0x180033e7f  nop     dword ptr [rax+rax+00h]
0x180033e84  test    rax, rax
0x180033e87  jz      loc_1800341BA
0x180033e8d  mov     ebx, 8
0x180033e92  mov     qword ptr [rbp+57h+var_A0+8], rax
0x180033e96  mov     word ptr [rbp+57h+var_A0], bx
0x180033e9a  lea     rcx, aXmlnsPHttpSche; "xmlns:p=\"http://schemas.microsoft.com/"...
0x180033ea1  call    cs:__imp_SysAllocString
0x180033ea8  nop     dword ptr [rax+rax+00h]
0x180033ead  test    rax, rax
0x180033eb0  jz      loc_1800341BA
0x180033eb6  mov     word ptr [rbp+57h+var_88], bx
0x180033eba  mov     qword ptr [rbp+57h+var_88+8], rax
0x180033ebe  mov     rax, [rdi]
0x180033ec1  mov     rcx, rdi
0x180033ec4  mov     rax, [rax]
0x180033ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ecc  mov     rdx, rax; unsigned __int16 *
0x180033ecf  lea     r8, [rbp+57h+var_70]; struct tagVARIANT *
0x180033ed3  call    ?InitializeVariantFromString@EnterpriseXmlPolicyHelper@@IEAAJPEBGPEAUtagVARIANT@@@Z; EnterpriseXmlPolicyHelper::InitializeVariantFromString(ushort const *,tagVARIANT *)
0x180033ed8  mov     ebx, eax
0x180033eda  test    eax, eax
0x180033edc  js      loc_1800341BF
0x180033ee2  mov     rdx, rsi; unsigned __int16 *
0x180033ee5  lea     rcx, [rdi+10h]; this
0x180033ee9  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180033eee  mov     ebx, eax
0x180033ef0  test    eax, eax
0x180033ef2  js      loc_1800341BF
0x180033ef8  cmp     [rsi], r13w
0x180033efc  jnz     short loc_180033F0D
0x180033efe  mov     [rdi+8], r13d
0x180033f02  mov     ebx, r13d
0x180033f05  mov     [r15], r13d
0x180033f08  jmp     loc_1800341BF
0x180033f0d  mov     rcx, rdi; this
0x180033f10  call    ?InitializeStrings@EnterpriseXmlPolicyHelper@@IEAAJXZ; EnterpriseXmlPolicyHelper::InitializeStrings(void)
0x180033f15  mov     ebx, eax
0x180033f17  test    eax, eax
0x180033f19  js      loc_1800341BF
0x180033f1f  xor     edx, edx; pUnkOuter
0x180033f21  lea     rsi, [rdi+18h]
0x180033f25  lea     r9, _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60; riid
0x180033f2c  mov     [rsp+120h+ppv], rsi; ppv
0x180033f31  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180033f38  lea     r8d, [rdx+1]; dwClsContext
0x180033f3c  call    cs:__imp_CoCreateInstance
0x180033f43  nop     dword ptr [rax+rax+00h]
0x180033f48  mov     ebx, eax
0x180033f4a  test    eax, eax
0x180033f4c  js      loc_1800341BF
0x180033f52  xor     edx, edx; pUnkOuter
0x180033f54  lea     r14, [rdi+28h]
0x180033f58  lea     r9, _GUID_50ea08b0_dd1b_4664_9a50_c2f40f4bd79a; riid
0x180033f5f  mov     [rsp+120h+ppv], r14; ppv
0x180033f64  lea     rcx, _GUID_88d96a07_f192_11d4_a65f_0040963251e5; rclsid
0x180033f6b  lea     r8d, [rdx+1]; dwClsContext
0x180033f6f  call    cs:__imp_CoCreateInstance
0x180033f76  nop     dword ptr [rax+rax+00h]
0x180033f7b  mov     ebx, eax
0x180033f7d  test    eax, eax
0x180033f7f  js      loc_1800341BF
0x180033f85  mov     rcx, [rsi]
0x180033f88  xor     edx, edx
0x180033f8a  mov     rax, [rcx]
0x180033f8d  mov     rax, [rax+1F8h]
0x180033f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f99  mov     ebx, eax
0x180033f9b  test    eax, eax
0x180033f9d  js      loc_1800341BF
0x180033fa3  mov     rcx, [rsi]
0x180033fa6  lea     r8, [rsp+120h+var_F0]
0x180033fab  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180033faf  mov     rdx, [rdi+38h]
0x180033fb3  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180033fb8  mov     rax, [rcx]
0x180033fbb  movaps  [rsp+120h+var_F0], xmm0
0x180033fc0  movsd   [rsp+120h+var_E0], xmm1
0x180033fc6  mov     rax, [rax+280h]
0x180033fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033fd2  mov     ebx, eax
0x180033fd4  test    eax, eax
0x180033fd6  js      loc_1800341BF
0x180033fdc  mov     rcx, [rsi]
0x180033fdf  lea     r8, [rsp+120h+var_F0]
0x180033fe4  movups  xmm0, xmmword ptr [rbp+57h+var_88]
0x180033fe8  mov     rdx, [rdi+40h]
0x180033fec  movsd   xmm1, qword ptr [rbp+57h+var_88+10h]
0x180033ff1  mov     rax, [rcx]
0x180033ff4  movaps  [rsp+120h+var_F0], xmm0
0x180033ff9  movsd   [rsp+120h+var_E0], xmm1
0x180033fff  mov     rax, [rax+280h]
0x180034006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003400b  mov     ebx, eax
0x18003400d  test    eax, eax
0x18003400f  js      loc_1800341BF
0x180034015  mov     rcx, [rsi]
0x180034018  lea     r8, [rsp+120h+var_F0]
0x18003401d  movups  xmm0, xmmword ptr [rbp+57h+var_A0]
0x180034021  mov     rdx, [rdi+48h]
0x180034025  movsd   xmm1, qword ptr [rbp+57h+var_A0+10h]
0x18003402a  mov     rax, [rcx]
0x18003402d  movaps  [rsp+120h+var_F0], xmm0
0x180034032  movsd   [rsp+120h+var_E0], xmm1
0x180034038  mov     rax, [rax+280h]
0x18003403f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034044  mov     ebx, eax
0x180034046  test    eax, eax
0x180034048  js      loc_1800341BF
0x18003404e  mov     rcx, [r14]
0x180034051  mov     eax, 0Dh
0x180034056  mov     word ptr [rbp+57h+var_B8], ax
0x18003405a  mov     qword ptr [rbp+57h+var_B8+8], rcx
0x18003405e  mov     rax, [rcx]
0x180034061  mov     rax, [rax+8]
0x180034065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003406a  mov     rcx, [rsi]
0x18003406d  lea     rdx, [rsp+120h+var_F0]
0x180034072  movups  xmm0, xmmword ptr [rbp+57h+var_B8]
0x180034076  movsd   xmm1, qword ptr [rbp+57h+var_B8+10h]
0x18003407b  mov     rax, [rcx]
0x18003407e  movaps  [rsp+120h+var_F0], xmm0
0x180034083  movsd   [rsp+120h+var_E0], xmm1
0x180034089  mov     rax, [rax+270h]
0x180034090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034095  mov     ebx, eax
0x180034097  test    eax, eax
0x180034099  js      loc_1800341BF
0x18003409f  mov     rcx, [r14]
0x1800340a2  lea     r8, [rsp+120h+var_F0]
0x1800340a7  movups  xmm0, xmmword ptr [rbp+57h+var_70]
0x1800340ab  mov     rdx, [rdi+50h]
0x1800340af  movsd   xmm1, qword ptr [rbp+57h+var_70+10h]
0x1800340b4  mov     rax, [rcx]
0x1800340b7  movaps  [rsp+120h+var_F0], xmm0
0x1800340bc  movsd   [rsp+120h+var_E0], xmm1
0x1800340c2  mov     rax, [rax+38h]
0x1800340c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340cb  mov     ebx, eax
0x1800340cd  test    eax, eax
0x1800340cf  js      loc_1800341BF
0x1800340d5  mov     rcx, [r14]
0x1800340d8  or      edx, 0FFFFFFFFh
0x1800340db  mov     rax, [rcx]
0x1800340de  mov     rax, [rax+78h]
0x1800340e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340e7  mov     ebx, eax
0x1800340e9  test    eax, eax
0x1800340eb  js      loc_1800341BF
0x1800340f1  mov     rcx, [r14]
0x1800340f4  mov     rax, [rcx]
0x1800340f7  mov     rax, [rax+70h]
0x1800340fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034100  mov     ebx, eax
0x180034102  test    eax, eax
0x180034104  js      loc_1800341BF
0x18003410a  mov     rcx, [rsi]
0x18003410d  lea     r8, [rbp+57h+arg_10]
0x180034111  mov     rdx, [rdi+10h]
0x180034115  mov     rax, [rcx]
0x180034118  mov     rax, [rax+208h]
0x18003411f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034124  mov     ebx, eax
0x180034126  test    eax, eax
0x180034128  js      loc_1800341BF
0x18003412e  cmp     eax, 1
0x180034131  jz      short loc_180034161
0x180034133  cmp     [rbp+57h+arg_10], r13w
0x180034138  jz      short loc_180034161
0x18003413a  mov     rcx, [rsi]
0x18003413d  lea     rdx, [rdi+20h]
0x180034141  mov     rax, [rcx]
0x180034144  mov     rax, [rax+278h]
0x18003414b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034150  mov     ebx, eax
0x180034152  test    eax, eax
0x180034154  js      short loc_1800341BF
0x180034156  mov     rdx, [rdi+20h]
0x18003415a  test    rdx, rdx
0x18003415d  jz      short loc_180034199
0x18003415f  jmp     short loc_18003418A
0x180034161  mov     rcx, [rsi]
0x180034164  lea     rdx, [rdi+20h]
0x180034168  mov     rax, [rcx]
0x18003416b  mov     rax, [rax+1E0h]
0x180034172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034177  mov     ebx, eax
0x180034179  test    eax, eax
0x18003417b  js      short loc_1800341BF
0x18003417d  mov     rdx, [rdi+20h]; struct IXMLDOMParseError *
0x180034181  test    rdx, rdx
0x180034184  jz      loc_180033E5A
0x18003418a  lea     r8, [rdi+30h]; unsigned __int16 **
0x18003418e  call    ?GetParseError@EnterpriseXmlPolicyHelper@@IEAAJPEAUIXMLDOMParseError@@PEAPEAG@Z; EnterpriseXmlPolicyHelper::GetParseError(IXMLDOMParseError *,ushort * *)
0x180034193  mov     ebx, eax
0x180034195  test    eax, eax
0x180034197  js      short loc_1800341BF
0x180034199  lea     rdx, [rdi+8]; unsigned int *
0x18003419d  mov     rcx, rdi; this
0x1800341a0  call    ?GetVersion@EnterpriseXmlPolicyHelper@@IEBAJPEAK@Z; EnterpriseXmlPolicyHelper::GetVersion(ulong *)
0x1800341a5  mov     ebx, eax
0x1800341a7  test    eax, eax
0x1800341a9  js      short loc_1800341BF
0x1800341ab  mov     rdx, r15; enum PolicyType *
0x1800341ae  mov     rcx, rdi; this
0x1800341b1  call    ?GetPolicyType@EnterpriseXmlPolicyHelper@@IEBAJPEAW4PolicyType@@@Z; EnterpriseXmlPolicyHelper::GetPolicyType(PolicyType *)
0x1800341b6  mov     ebx, eax
0x1800341b8  jmp     short loc_1800341BF
0x1800341ba  mov     ebx, 8007000Eh
0x1800341bf  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800341c3  call    cs:__imp_VariantClear
0x1800341ca  nop     dword ptr [rax+rax+00h]
0x1800341cf  lea     rcx, [rbp+57h+var_B8]; pvarg
0x1800341d3  call    cs:__imp_VariantClear
0x1800341da  nop     dword ptr [rax+rax+00h]
0x1800341df  lea     rcx, [rbp+57h+var_A0]; pvarg
0x1800341e3  call    cs:__imp_VariantClear
0x1800341ea  nop     dword ptr [rax+rax+00h]
0x1800341ef  lea     rcx, [rbp+57h+var_70]; pvarg
0x1800341f3  call    cs:__imp_VariantClear
0x1800341fa  nop     dword ptr [rax+rax+00h]
0x1800341ff  lea     rcx, [rbp+57h+var_58]; pvarg
0x180034203  call    cs:__imp_VariantClear
0x18003420a  nop     dword ptr [rax+rax+00h]
0x18003420f  lea     rcx, [rbp+57h+var_88]; pvarg
0x180034213  call    cs:__imp_VariantClear
0x18003421a  nop     dword ptr [rax+rax+00h]
0x18003421f  mov     eax, ebx
0x180034221  add     rsp, 0E8h
0x180034228  pop     r15
0x18003422a  pop     r14
0x18003422c  pop     r13
0x18003422e  pop     r12
0x180034230  pop     rdi
0x180034231  pop     rsi
0x180034232  pop     rbx
0x180034233  pop     rbp
  ... truncated ...
```
