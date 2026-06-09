# Common::Deployment::GetPackagesInBundleByPath(ushort const *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)

- ea: `0x18001073c`
- end: `0x180010a28`
- name: `?GetPackagesInBundleByPath@Deployment@Common@@YAJPEBGAEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@2@@Z`
- size: `748`
- prototype: `__int64 __fastcall(Common::Deployment *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028d40`
- `0x180043b10`

## callees

- `0x180004920`
- `0x180008db0`
- `0x18001073c`
- `0x180018248`
- `0x1800198d4`
- `0x18001ca24`
- `0x18001f21c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800108f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010949`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800108f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010949`

## string_xrefs

- `0x180010759`: `onecore\admin\appmodel\common\bundleutilities.cpp`
- `0x1800107a0`: `onecore\admin\appmodel\common\bundleutilities.cpp`
- `0x1800107ee`: `onecore\admin\appmodel\common\bundleutilities.cpp`
- `0x18001092d`: `onecore\admin\appmodel\common\bundleutilities.cpp`
- `0x180010965`: `onecore\admin\appmodel\common\bundleutilities.cpp`
- `0x18001097f`: `onecore\admin\appmodel\common\bundleutilities.cpp`
- `0x180010999`: `onecore\admin\appmodel\common\bundleutilities.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::GetPackagesInBundleByPath(Common::Deployment *this, _QWORD *a2)
{
  unsigned int v4; // ebx
  struct IAppxBundleManifestReader **v6; // r8
  int AppxBundleManifestReaderByPath; // eax
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 *); // rbx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // [rsp+20h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-28h] BYREF
  unsigned __int16 v25[4]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v26; // [rsp+38h] [rbp-18h] BYREF
  int v27; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v29; // [rsp+80h] [rbp+30h] BYREF
  __int64 v30; // [rsp+90h] [rbp+40h] BYREF
  __int64 v31; // [rsp+98h] [rbp+48h] BYREF

  if ( !this )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\admin\\appmodel\\common\\bundleutilities.cpp",
      (const char *)0x80070057LL,
      v23);
    return v4;
  }
  *(_QWORD *)v25 = 0;
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(v25);
  AppxBundleManifestReaderByPath = Common::Deployment::GetAppxBundleManifestReaderByPath(this, v25, v6);
  v4 = AppxBundleManifestReaderByPath;
  if ( AppxBundleManifestReaderByPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecore\\admin\\appmodel\\common\\bundleutilities.cpp",
      (const char *)(unsigned int)AppxBundleManifestReaderByPath,
      v23);
LABEL_28:
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(v25);
    return v4;
  }
  v8 = *(_QWORD *)v25;
  v30 = 0;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)v25 + 32LL);
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v30);
  v10 = v9(v8, &v30);
  v4 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecore\\admin\\appmodel\\common\\bundleutilities.cpp",
      (const char *)(unsigned int)v10,
      v23);
LABEL_27:
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v30);
    goto LABEL_28;
  }
  v29 = 0;
  v31 = 0;
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 32LL))(v30, &v29);
  while ( v29 )
  {
    v11 = v30;
    v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 24LL);
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v31);
    v13 = v12(v11, &v31);
    v4 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecore\\admin\\appmodel\\common\\bundleutilities.cpp",
        (const char *)(unsigned int)v13,
        v23);
      goto LABEL_26;
    }
    v14 = v31;
    v23 = 0;
    v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 32LL);
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v23);
    v16 = v15(v14, &v23);
    v4 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecore\\admin\\appmodel\\common\\bundleutilities.cpp",
        (const char *)(unsigned int)v16,
        v23);
      goto LABEL_21;
    }
    pv = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v23 + 72LL))(v23, &pv);
    v4 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x84,
        (unsigned int)"onecore\\admin\\appmodel\\common\\bundleutilities.cpp",
        (const char *)(unsigned int)v17,
        v23);
      goto LABEL_20;
    }
    v26 = 0;
    v27 = 0;
    v18 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v26, (const unsigned __int16 *)pv);
    v4 = v18;
    if ( v18 < 0 )
    {
      v20 = 135;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\admin\\appmodel\\common\\bundleutilities.cpp",
        (const char *)(unsigned int)v18,
        v23);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v26);
LABEL_20:
      CoTaskMemFree(pv);
LABEL_21:
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v23);
LABEL_26:
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v31);
      goto LABEL_27;
    }
    v18 = Common::Array<unsigned short,Common::ContainerOperations<unsigned short,unsigned short>,Common::NoKey,Common::ContainerOperations<Common::NoKey,unsigned short>,Common::ArrayOperations<unsigned short,Common::NoKey>>::Add(
            a2,
            *((__int64 *)&v26 + 1));
    v4 = v18;
    if ( v18 < 0 )
    {
      v20 = 137;
      goto LABEL_19;
    }
    CoTaskMemFree(pv);
    v19 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 40LL))(v30, &v29);
  }
  v21 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return 0;
}

```

## disassembly

```asm
0x18001073c  push    rbp
0x18001073e  push    rbx
0x18001073f  push    rsi
0x180010740  push    rdi
0x180010741  push    r14
0x180010743  mov     rbp, rsp
0x180010746  sub     rsp, 50h
0x18001074a  mov     r14, rdx
0x18001074d  mov     rbx, rcx
0x180010750  test    rcx, rcx
0x180010753  jnz     short loc_180010779
0x180010755  mov     rcx, [rbp+28h]; this
0x180010759  lea     r8, aOnecoreAdminAp_28
0x180010760  mov     ebx, 80070057h
0x180010765  mov     edx, 72h ; 'r'; void *
0x18001076a  mov     r9d, ebx; char *
0x18001076d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180010772  mov     eax, ebx
0x180010774  jmp     loc_180010A1D
0x180010779  lea     rcx, [rbp+var_20]
0x18001077d  mov     qword ptr [rbp+var_20], 0
0x180010785  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ
0x18001078a  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x18001078e  mov     rcx, rbx; this
0x180010791  call    ?GetAppxBundleManifestReaderByPath@Deployment@Common@@YAJPEBGPEAPEAUIAppxBundleManifestReader@@@Z
0x180010796  mov     ebx, eax
0x180010798  test    eax, eax
0x18001079a  jns     short loc_1800107B9
0x18001079c  mov     rcx, [rbp+28h]; this
0x1800107a0  lea     r8, aOnecoreAdminAp_28
0x1800107a7  mov     r9d, eax; char *
0x1800107aa  mov     edx, 75h ; 'u'; void *
0x1800107af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800107b4  jmp     loc_1800109BF
0x1800107b9  mov     rsi, qword ptr [rbp+var_20]
0x1800107bd  lea     rcx, [rbp+arg_10]
0x1800107c1  mov     [rbp+arg_10], 0
0x1800107c9  mov     rax, [rsi]
0x1800107cc  mov     rbx, [rax+20h]
0x1800107d0  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ
0x1800107d5  lea     rdx, [rbp+arg_10]
0x1800107d9  mov     rcx, rsi
0x1800107dc  mov     rax, rbx
0x1800107df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107e4  mov     ebx, eax
0x1800107e6  test    eax, eax
0x1800107e8  jns     short loc_180010807
0x1800107ea  mov     rcx, [rbp+28h]; this
0x1800107ee  lea     r8, aOnecoreAdminAp_28
0x1800107f5  mov     r9d, eax; char *
0x1800107f8  mov     edx, 78h ; 'x'; void *
0x1800107fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180010802  jmp     loc_1800109B6
0x180010807  mov     rcx, [rbp+arg_10]
0x18001080b  mov     [rbp+arg_0], 0
0x180010812  mov     [rbp+arg_18], 0
0x18001081a  mov     rax, [rcx]
0x18001081d  mov     rax, [rax+20h]
0x180010821  lea     rdx, [rbp+arg_0]
0x180010825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001082a  cmp     [rbp+arg_0], 0
0x18001082e  jz      loc_1800109CD
0x180010834  mov     rdi, [rbp+arg_10]
0x180010838  lea     rcx, [rbp+arg_18]
0x18001083c  mov     rax, [rdi]
0x18001083f  mov     rbx, [rax+18h]
0x180010843  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ
0x180010848  lea     rdx, [rbp+arg_18]
0x18001084c  mov     rcx, rdi
0x18001084f  mov     rax, rbx
0x180010852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010857  mov     ebx, eax
0x180010859  test    eax, eax
0x18001085b  js      loc_180010995
0x180010861  mov     rdi, [rbp+arg_18]
0x180010865  lea     rcx, [rbp+var_30]
0x180010869  mov     [rbp+var_30], 0
0x180010871  mov     rax, [rdi]
0x180010874  mov     rbx, [rax+20h]
0x180010878  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ
0x18001087d  lea     rdx, [rbp+var_30]
0x180010881  mov     rcx, rdi
0x180010884  mov     rax, rbx
0x180010887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001088c  mov     ebx, eax
0x18001088e  test    eax, eax
0x180010890  js      loc_18001097B
0x180010896  mov     rcx, [rbp+var_30]
0x18001089a  lea     rdx, [rbp+pv]
0x18001089e  mov     [rbp+pv], 0
0x1800108a6  mov     rax, [rcx]
0x1800108a9  mov     rax, [rax+48h]
0x1800108ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108b2  mov     ebx, eax
0x1800108b4  test    eax, eax
0x1800108b6  js      loc_180010961
0x1800108bc  mov     rdx, [rbp+pv]; Src
0x1800108c0  lea     rcx, [rbp+var_18]; this
0x1800108c4  xor     eax, eax
0x1800108c6  xorps   xmm0, xmm0
0x1800108c9  movups  [rbp+var_18], xmm0
0x1800108cd  mov     [rbp+var_8], eax
0x1800108d0  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z
0x1800108d5  mov     ebx, eax
0x1800108d7  test    eax, eax
0x1800108d9  js      short loc_18001095A
0x1800108db  mov     rdx, qword ptr [rbp+var_18+8]
0x1800108df  mov     rcx, r14
0x1800108e2  call    ?Add@?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@QEAAJPEAG@Z
0x1800108e7  mov     ebx, eax
0x1800108e9  test    eax, eax
0x1800108eb  js      short loc_180010924
0x1800108ed  mov     rcx, [rbp+pv]; pv
0x1800108f1  call    cs:__imp_CoTaskMemFree
0x1800108f7  mov     rcx, [rbp+var_30]
0x1800108fb  test    rcx, rcx
0x1800108fe  jz      short loc_180010914
0x180010900  mov     [rbp+var_30], 0
0x180010908  mov     rax, [rcx]
0x18001090b  mov     rax, [rax+10h]
0x18001090f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010914  mov     rcx, [rbp+arg_10]
0x180010918  mov     rax, [rcx]
0x18001091b  mov     rax, [rax+28h]
0x18001091f  jmp     loc_180010821
0x180010924  mov     edx, 89h; void *
0x180010929  mov     rcx, [rbp+28h]; this
0x18001092d  lea     r8, aOnecoreAdminAp_28
0x180010934  mov     r9d, eax; char *
0x180010937  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18001093c  lea     rcx, [rbp+var_18]; this
0x180010940  call    ??1StringBuffer@Common@@QEAA@XZ
0x180010945  mov     rcx, [rbp+pv]; pv
0x180010949  call    cs:__imp_CoTaskMemFree
0x18001094f  lea     rcx, [rbp+var_30]
0x180010953  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ
0x180010958  jmp     short loc_1800109AD
0x18001095a  mov     edx, 87h
0x18001095f  jmp     short loc_180010929
0x180010961  mov     rcx, [rbp+28h]; this
0x180010965  lea     r8, aOnecoreAdminAp_28
0x18001096c  mov     r9d, eax; char *
0x18001096f  mov     edx, 84h; void *
0x180010974  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180010979  jmp     short loc_180010945
0x18001097b  mov     rcx, [rbp+28h]; this
0x18001097f  lea     r8, aOnecoreAdminAp_28
0x180010986  mov     r9d, eax; char *
0x180010989  mov     edx, 81h; void *
0x18001098e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180010993  jmp     short loc_18001094F
0x180010995  mov     rcx, [rbp+28h]; this
0x180010999  lea     r8, aOnecoreAdminAp_28
0x1800109a0  mov     r9d, eax; char *
0x1800109a3  mov     edx, 7Eh ; '~'; void *
0x1800109a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800109ad  lea     rcx, [rbp+arg_18]
0x1800109b1  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ
0x1800109b6  lea     rcx, [rbp+arg_10]
0x1800109ba  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ
0x1800109bf  lea     rcx, [rbp+var_20]
0x1800109c3  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ
0x1800109c8  jmp     loc_180010772
0x1800109cd  mov     rcx, [rbp+arg_18]
0x1800109d1  test    rcx, rcx
0x1800109d4  jz      short loc_1800109EA
0x1800109d6  mov     [rbp+arg_18], 0
0x1800109de  mov     rax, [rcx]
0x1800109e1  mov     rax, [rax+10h]
0x1800109e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ea  mov     rcx, [rbp+arg_10]
0x1800109ee  test    rcx, rcx
0x1800109f1  jz      short loc_180010A07
0x1800109f3  mov     [rbp+arg_10], 0
0x1800109fb  mov     rax, [rcx]
0x1800109fe  mov     rax, [rax+10h]
0x180010a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a07  test    rsi, rsi
0x180010a0a  jz      short loc_180010A1B
0x180010a0c  mov     rax, [rsi]
0x180010a0f  mov     rcx, rsi
0x180010a12  mov     rax, [rax+10h]
0x180010a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a1b  xor     eax, eax
0x180010a1d  add     rsp, 50h
0x180010a21  pop     r14
0x180010a23  pop     rdi
0x180010a24  pop     rsi
0x180010a25  pop     rbx
0x180010a26  pop     rbp
0x180010a27  retn
```
