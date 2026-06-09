# Common::Deployment::PackageHasAttributeForHeadless(Microsoft::WRL::ComPtr<IAppxManifestReader> const &,bool *)

- ea: `0x180046350`
- end: `0x1800466db`
- name: `?PackageHasAttributeForHeadless@Deployment@Common@@YAJAEBV?$ComPtr@UIAppxManifestReader@@@WRL@Microsoft@@PEA_N@Z`
- size: `907`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046128`

## callees

- `0x180018248`
- `0x18001a6a0`
- `0x18001ca24`
- `0x180045bbc`
- `0x180045e50`
- `0x180046350`
- `0x18004c9d0`
- `0x18004d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800464e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180046569`
- `OLEAUT32!__imp_SysFreeString` at `0x180046653`
- `OLEAUT32!__imp_SysFreeString` at `0x1800464e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180046569`
- `OLEAUT32!__imp_SysFreeString` at `0x180046653`

## string_xrefs

- `0x1800463b9`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x18004640b`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x1800464ca`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x18004653c`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x1800465b1`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x1800466a4`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x180046543`: `XPath %ws`

## pseudocode

```c
__int64 __fastcall Common::Deployment::PackageHasAttributeForHeadless(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        _BYTE *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, BSTR, __int64 *); // rdi
  OLECHAR *v13; // rbx
  int HasAttributeForHeadless; // edi
  int v15; // eax
  unsigned int v16; // r14d
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, _QWORD, BSTR *); // rdi
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h]
  char *v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+30h] [rbp-D0h]
  bool v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  char v30[16]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+90h] [rbp-70h]
  __int128 v33; // [rsp+A0h] [rbp-60h]
  __int128 v34; // [rsp+B0h] [rbp-50h]
  __int128 v35; // [rsp+C0h] [rbp-40h]
  __int128 v36; // [rsp+D0h] [rbp-30h]
  __int128 v37; // [rsp+E0h] [rbp-20h]
  __int128 v38; // [rsp+F0h] [rbp-10h]
  __int128 v39; // [rsp+100h] [rbp+0h]
  __int128 v40; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  *a2 = 0;
  v3 = *a1;
  v29 = 0;
  v4 = **v3;
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v29);
  v5 = v4(v3, &GUID_c0fc0853_18d7_43e8_afca_414a07af67a2, &v29);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = v29;
    v25 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 24LL);
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v25);
    v9 = v8(v7, &v25);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
        (const char *)(unsigned int)v9,
        v21);
LABEL_5:
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v25);
      goto LABEL_21;
    }
    *(_OWORD *)v30 = *(_OWORD *)L"/*[local-name()='Package']/*[local-name()='Applications']/*[local-name()='Application']";
    bstrString = 0;
    v32 = *(_OWORD *)L"'Package']/*[local-name()='Applications']/*[local-name()='Application']";
    v31 = *(_OWORD *)L"-name()='Package']/*[local-name()='Applications']/*[local-name()='Application']";
    v34 = *(_OWORD *)L"al-name()='Applications']/*[local-name()='Application']";
    v33 = *(_OWORD *)L"']/*[local-name()='Applications']/*[local-name()='Application']";
    v36 = *(_OWORD *)L"cations']/*[local-name()='Application']";
    v35 = *(_OWORD *)L")='Applications']/*[local-name()='Application']";
    v38 = *(_OWORD *)L"l-name()='Application']";
    v37 = *(_OWORD *)L"]/*[local-name()='Application']";
    v40 = *(_OWORD *)L"ation']";
    v39 = *(_OWORD *)L"='Application']";
    v10 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoBStrAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoBStrDeallocate(unsigned short *)>::CopyFromString(
            &bstrString,
            (const unsigned __int16 *)v30);
    v6 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
        (const char *)(unsigned int)v10,
        v21);
      SysFreeString(bstrString);
      goto LABEL_5;
    }
    v11 = v25;
    v27 = 0;
    v12 = *(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v25 + 288LL);
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v27);
    v13 = bstrString;
    HasAttributeForHeadless = v12(v11, bstrString, &v27);
    if ( HasAttributeForHeadless < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x7F,
        (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
        (const char *)(unsigned int)HasAttributeForHeadless,
        (int)"XPath %ws",
        v30);
LABEL_10:
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v27);
      SysFreeString(v13);
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v25);
      v6 = HasAttributeForHeadless;
      goto LABEL_21;
    }
    if ( v27 )
    {
      v26 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 64LL))(v27, &v26);
      HasAttributeForHeadless = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x84,
          (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
          (const char *)(unsigned int)v15,
          v21);
        goto LABEL_10;
      }
      v16 = 0;
      if ( v26 > 0 )
      {
        while ( 1 )
        {
          v17 = v27;
          bstrString = 0;
          v18 = *(__int64 (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)v27 + 56LL);
          Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&bstrString);
          HasAttributeForHeadless = v18(v17, v16, &bstrString);
          if ( HasAttributeForHeadless < 0 )
            break;
          v24 = 0;
          HasAttributeForHeadless = Common::Deployment::AppHasAttributeForHeadless(
                                      (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&bstrString,
                                      &v24);
          if ( HasAttributeForHeadless < 0 )
          {
            v20 = 142;
            goto LABEL_24;
          }
          Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&bstrString);
          if ( !v24 )
            goto LABEL_20;
          if ( (int)++v16 >= v26 )
            goto LABEL_19;
        }
        v20 = 137;
LABEL_24:
        v23 = v26;
        LODWORD(v22) = v16;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)v20,
          (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
          (const char *)(unsigned int)HasAttributeForHeadless,
          (int)"Item %d of %d",
          v22,
          v23);
        Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&bstrString);
        goto LABEL_10;
      }
LABEL_19:
      *a2 = 1;
    }
LABEL_20:
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v27);
    SysFreeString(v13);
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v25);
    v6 = 0;
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x72,
    (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
    (const char *)(unsigned int)v5,
    v21);
LABEL_21:
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v29);
  return v6;
}

```

## disassembly

```asm
0x180046350  mov     [rsp-8+arg_10], rbx
0x180046355  push    rbp
0x180046356  push    rsi
0x180046357  push    rdi
0x180046358  push    r14
0x18004635a  push    r15
0x18004635c  lea     rbp, [rsp-30h]
0x180046361  sub     rsp, 130h
0x180046368  mov     rax, cs:__security_cookie
0x18004636f  xor     rax, rsp
0x180046372  mov     [rbp+50h+var_30], rax
0x180046376  mov     byte ptr [rdx], 0
0x180046379  mov     r15, rdx
0x18004637c  mov     rdi, [rcx]
0x18004637f  lea     rcx, [rsp+150h+var_E8]
0x180046384  mov     [rsp+150h+var_E8], 0
0x18004638d  mov     rax, [rdi]
0x180046390  mov     rbx, [rax]
0x180046393  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180046398  lea     r8, [rsp+150h+var_E8]
0x18004639d  mov     rcx, rdi
0x1800463a0  lea     rdx, _GUID_c0fc0853_18d7_43e8_afca_414a07af67a2
0x1800463a7  mov     rax, rbx
0x1800463aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800463af  mov     ebx, eax
0x1800463b1  test    eax, eax
0x1800463b3  jns     short loc_1800463D2
0x1800463b5  mov     rcx, [rbp+58h]; this
0x1800463b9  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x1800463c0  mov     r9d, eax; char *
0x1800463c3  mov     edx, 72h ; 'r'; void *
0x1800463c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800463cd  jmp     loc_180046665
0x1800463d2  mov     rdi, [rsp+150h+var_E8]
0x1800463d7  lea     rcx, [rsp+150h+var_108]
0x1800463dc  mov     [rsp+150h+var_108], 0
0x1800463e5  mov     rax, [rdi]
0x1800463e8  mov     rbx, [rax+18h]
0x1800463ec  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x1800463f1  lea     rdx, [rsp+150h+var_108]
0x1800463f6  mov     rcx, rdi
0x1800463f9  mov     rax, rbx
0x1800463fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046401  mov     ebx, eax
0x180046403  test    eax, eax
0x180046405  jns     short loc_18004642E
0x180046407  mov     rcx, [rbp+58h]; this
0x18004640b  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x180046412  mov     r9d, eax; char *
0x180046415  mov     edx, 75h ; 'u'; void *
0x18004641a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004641f  lea     rcx, [rsp+150h+var_108]
0x180046424  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180046429  jmp     loc_180046665
0x18004642e  movaps  xmm0, xmmword ptr cs:aLocalNamePacka; "/*[local-name()='Package']/*[local-name"...
0x180046435  lea     rdx, [rsp+150h+var_E0]
0x18004643a  movaps  xmm1, xmmword ptr cs:aLocalNamePacka+10h; "-name()='Package']/*[local-name()='Appl"...
0x180046441  lea     rcx, [rsp+150h+bstrString]
0x180046446  movups  xmmword ptr [rsp+150h+var_E0], xmm0
0x18004644b  mov     [rsp+150h+bstrString], 0
0x180046454  movaps  xmm0, xmmword ptr cs:aLocalNamePacka+20h; "'Package']/*[local-name()='Applications"...
0x18004645b  movups  [rbp+50h+var_C0], xmm0
0x18004645f  movaps  xmm0, xmmword ptr cs:aLocalNamePacka+40h; "al-name()='Applications']/*[local-name("...
0x180046466  movups  [rbp+50h+var_D0], xmm1
0x18004646a  movaps  xmm1, xmmword ptr cs:aLocalNamePacka+30h; "']/*[local-name()='Applications']/*[loc"...
0x180046471  movups  [rbp+50h+var_A0], xmm0
0x180046475  movaps  xmm0, xmmword ptr cs:aLocalNamePacka+60h; "cations']/*[local-name()='Application']"
0x18004647c  movups  [rbp+50h+var_B0], xmm1
0x180046480  movaps  xmm1, xmmword ptr cs:aLocalNamePacka+50h; ")='Applications']/*[local-name()='Appli"...
0x180046487  movups  [rbp+50h+var_80], xmm0
0x18004648b  movaps  xmm0, xmmword ptr cs:aLocalNamePacka+80h; "l-name()='Application']"
0x180046492  movups  [rbp+50h+var_90], xmm1
0x180046496  movaps  xmm1, xmmword ptr cs:aLocalNamePacka+70h; "]/*[local-name()='Application']"
0x18004649d  movups  [rbp+50h+var_60], xmm0
0x1800464a1  movaps  xmm0, xmmword ptr cs:aLocalNamePacka+0A0h; "ation']"
0x1800464a8  movups  [rbp+50h+var_70], xmm1
0x1800464ac  movaps  xmm1, xmmword ptr cs:aLocalNamePacka+90h; "='Application']"
0x1800464b3  movups  [rbp+50h+var_40], xmm0
0x1800464b7  movups  [rbp+50h+var_50], xmm1
0x1800464bb  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoBStrAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoBStrDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoBStrAllocateAndCopy(ushort const *,uint),&Common::AutoBStrDeallocate(ushort *)>::CopyFromString(ushort const *)
0x1800464c0  mov     ebx, eax
0x1800464c2  test    eax, eax
0x1800464c4  jns     short loc_1800464EE
0x1800464c6  mov     rcx, [rbp+58h]; this
0x1800464ca  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x1800464d1  mov     r9d, eax; char *
0x1800464d4  mov     edx, 7Bh ; '{'; void *
0x1800464d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800464de  mov     rcx, [rsp+150h+bstrString]; bstrString
0x1800464e3  call    cs:__imp_SysFreeString
0x1800464e9  jmp     loc_18004641F
0x1800464ee  mov     rsi, [rsp+150h+var_108]
0x1800464f3  lea     rcx, [rsp+150h+var_F8]
0x1800464f8  mov     [rsp+150h+var_F8], 0
0x180046501  mov     rax, [rsi]
0x180046504  mov     rdi, [rax+120h]
0x18004650b  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180046510  mov     rbx, [rsp+150h+bstrString]
0x180046515  lea     r8, [rsp+150h+var_F8]
0x18004651a  mov     rdx, rbx
0x18004651d  mov     rcx, rsi
0x180046520  mov     rax, rdi
0x180046523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046528  mov     edi, eax
0x18004652a  test    eax, eax
0x18004652c  jns     short loc_180046580
0x18004652e  mov     rcx, [rbp+58h]; this
0x180046532  lea     rax, [rsp+150h+var_E0]
0x180046537  mov     [rsp+150h+var_128], rax; char *
0x18004653c  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x180046543  lea     rax, aXpathWs; "XPath %ws"
0x18004654a  mov     r9d, edi; char *
0x18004654d  mov     edx, 7Fh; void *
0x180046552  mov     qword ptr [rsp+150h+var_130], rax; int
0x180046557  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004655c  lea     rcx, [rsp+150h+var_F8]
0x180046561  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180046566  mov     rcx, rbx; bstrString
0x180046569  call    cs:__imp_SysFreeString
0x18004656f  lea     rcx, [rsp+150h+var_108]
0x180046574  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180046579  mov     ebx, edi
0x18004657b  jmp     loc_180046665
0x180046580  mov     rcx, [rsp+150h+var_F8]
0x180046585  test    rcx, rcx
0x180046588  jz      loc_180046646
0x18004658e  mov     [rsp+150h+var_100], 0
0x180046596  lea     rdx, [rsp+150h+var_100]
0x18004659b  mov     rax, [rcx]
0x18004659e  mov     rax, [rax+40h]
0x1800465a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465a7  mov     edi, eax
0x1800465a9  test    eax, eax
0x1800465ab  jns     short loc_1800465C7
0x1800465ad  mov     rcx, [rbp+58h]; this
0x1800465b1  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x1800465b8  mov     r9d, eax; char *
0x1800465bb  mov     edx, 84h; void *
0x1800465c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800465c5  jmp     short loc_18004655C
0x1800465c7  xor     r14d, r14d
0x1800465ca  cmp     [rsp+150h+var_100], r14d
0x1800465cf  jle     short loc_180046642
0x1800465d1  mov     rsi, [rsp+150h+var_F8]
0x1800465d6  lea     rcx, [rsp+150h+bstrString]
0x1800465db  mov     [rsp+150h+bstrString], 0
0x1800465e4  mov     rax, [rsi]
0x1800465e7  mov     rdi, [rax+38h]
0x1800465eb  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x1800465f0  lea     r8, [rsp+150h+bstrString]
0x1800465f5  mov     edx, r14d
0x1800465f8  mov     rcx, rsi
0x1800465fb  mov     rax, rdi
0x1800465fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046603  mov     edi, eax
0x180046605  test    eax, eax
0x180046607  js      loc_18004669B
0x18004660d  lea     rdx, [rsp+150h+var_110]
0x180046612  mov     [rsp+150h+var_110], 0
0x180046617  lea     rcx, [rsp+150h+bstrString]
0x18004661c  call    ?AppHasAttributeForHeadless@Deployment@Common@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEA_N@Z; Common::Deployment::AppHasAttributeForHeadless(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,bool *)
0x180046621  mov     edi, eax
0x180046623  test    eax, eax
0x180046625  js      short loc_180046694
0x180046627  lea     rcx, [rsp+150h+bstrString]
0x18004662c  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180046631  cmp     [rsp+150h+var_110], 0
0x180046636  jz      short loc_180046646
0x180046638  inc     r14d
0x18004663b  cmp     r14d, [rsp+150h+var_100]
0x180046640  jl      short loc_1800465D1
0x180046642  mov     byte ptr [r15], 1
0x180046646  lea     rcx, [rsp+150h+var_F8]
0x18004664b  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180046650  mov     rcx, rbx; bstrString
0x180046653  call    cs:__imp_SysFreeString
0x180046659  lea     rcx, [rsp+150h+var_108]
0x18004665e  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180046663  xor     ebx, ebx
0x180046665  lea     rcx, [rsp+150h+var_E8]
0x18004666a  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004666f  mov     eax, ebx
0x180046671  mov     rcx, [rbp+50h+var_30]
0x180046675  xor     rcx, rsp; StackCookie
0x180046678  call    __security_check_cookie
0x18004667d  mov     rbx, [rsp+150h+arg_10]
0x180046685  add     rsp, 130h
0x18004668c  pop     r15
0x18004668e  pop     r14
0x180046690  pop     rdi
0x180046691  pop     rsi
0x180046692  pop     rbp
0x180046693  retn
0x180046694  mov     edx, 8Eh
0x180046699  jmp     short loc_1800466A0
0x18004669b  mov     edx, 89h; void *
0x1800466a0  mov     eax, [rsp+150h+var_100]
0x1800466a4  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x1800466ab  mov     rcx, [rbp+58h]; this
0x1800466af  mov     r9d, edi; char *
0x1800466b2  mov     [rsp+150h+var_120], eax
0x1800466b6  lea     rax, aItemDOfD; "Item %d of %d"
0x1800466bd  mov     dword ptr [rsp+150h+var_128], r14d; char *
0x1800466c2  mov     qword ptr [rsp+150h+var_130], rax; int
0x1800466c7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800466cc  lea     rcx, [rsp+150h+bstrString]
0x1800466d1  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x1800466d6  jmp     loc_18004655C
```
