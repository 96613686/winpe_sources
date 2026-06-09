# _anonymous_namespace_::XmlParser

- ea: `0x140042224`
- end: `0x1400429a6`
- name: `_anonymous_namespace_::XmlParser`
- size: `1922`
- prototype: `__int64 __fastcall(void *, BYTE *pInit)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400420a0`

## callees

- `0x1400095b4`
- `0x140042104`
- `0x140042224`
- `0x14005d010`

## import_xrefs

- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x14004251d`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x14004251d`
- `XmlLite!CreateXmlReader` at `0x140042379`
- `XmlLite!CreateXmlReader` at `0x140042379`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x14004232b`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x14004232b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140042956`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140042956`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140042256`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140042256`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall anonymous_namespace_::XmlParser(void *a1, BYTE *pInit, __int64 a3)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  BYTE *v8; // rax
  unsigned __int64 v9; // r8
  IStream *v10; // rax
  IUnknown *v11; // rdi
  HRESULT v12; // eax
  IXmlReaderInput *v13; // rcx
  void *v14; // rcx
  int v15; // eax
  IXmlReaderInput *v16; // rcx
  void *v17; // rcx
  int v18; // eax
  IXmlReaderInput *v19; // rcx
  void *v20; // rcx
  IXmlReaderInput *v21; // rcx
  HRESULT v22; // eax
  IXmlReaderInput *v23; // rcx
  void *v24; // rcx
  int v25; // eax
  IXmlReaderInput *v26; // rcx
  void *v27; // rcx
  unsigned int v28; // eax
  int v29; // eax
  IXmlReaderInput *v30; // rcx
  void *v31; // rcx
  int v32; // eax
  IXmlReaderInput *v33; // rcx
  void *v34; // rcx
  int v35; // eax
  int v36; // eax
  IXmlReaderInput *v37; // rcx
  void *v38; // rcx
  IXmlReaderInput *v39; // rcx
  void *v40; // rcx
  IXmlReaderInput *v41; // rcx
  void *v42; // rcx
  int pwszBaseUri; // [rsp+20h] [rbp-40h]
  int pwszBaseUria; // [rsp+20h] [rbp-40h]
  void *ppvObject; // [rsp+30h] [rbp-30h] BYREF
  IXmlReaderInput *ppInput; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int16 *v48; // [rsp+40h] [rbp-20h] BYREF
  IUnknown *v49; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int v51; // [rsp+98h] [rbp+38h] BYREF
  __int64 v52; // [rsp+A0h] [rbp+40h] BYREF
  int v53; // [rsp+A8h] [rbp+48h]

  v52 = a3;
  if ( !pInit || !*(_WORD *)pInit )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)0x80070057LL,
      pwszBaseUri);
    return 2147942487LL;
  }
  v5 = CoInitializeEx(0, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)(unsigned int)v5,
      pwszBaseUri);
    return v6;
  }
  v53 = 1;
  ppvObject = 0;
  v49 = 0;
  ppInput = 0;
  v51 = 0;
  v48 = 0;
  LODWORD(v52) = 0;
  v7 = 0x7FFFFFFF;
  v8 = pInit;
  do
  {
    if ( !*(_WORD *)v8 )
      break;
    v8 += 2;
    --v7;
  }
  while ( v7 );
  v6 = v7 == 0 ? 0x80070057 : 0;
  v9 = (0x7FFFFFFF - v7) & -(__int64)(v7 != 0);
  if ( !v7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)v6,
      pwszBaseUri);
    goto LABEL_81;
  }
  if ( !is_mul_ok(v9, 2u) )
  {
    v6 = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)0x80070216LL,
      pwszBaseUri);
    goto LABEL_81;
  }
  v10 = SHCreateMemStream(pInit, 2 * (int)v9);
  v11 = (IUnknown *)v10;
  if ( !v10 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)0x8007000ELL,
      pwszBaseUri);
    goto LABEL_81;
  }
  (*(void (__fastcall **)(IStream *))(*(_QWORD *)v10 + 8LL))(v10);
  v49 = v11;
  v12 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v6 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)(unsigned int)v12,
      pwszBaseUri);
    v13 = ppInput;
    if ( ppInput )
    {
      ppInput = 0;
      ((void (__fastcall *)(IXmlReaderInput *))v13->lpVtbl->Release)(v13);
    }
    ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
    v14 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
    }
    goto LABEL_81;
  }
  v15 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 1);
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)(unsigned int)v15,
      pwszBaseUri);
    v16 = ppInput;
    if ( ppInput )
    {
      ppInput = 0;
      ((void (__fastcall *)(IXmlReaderInput *))v16->lpVtbl->Release)(v16);
    }
    ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
    v17 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
    }
    goto LABEL_81;
  }
  v18 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
  v6 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)(unsigned int)v18,
      pwszBaseUri);
    v19 = ppInput;
    if ( ppInput )
    {
      ppInput = 0;
      ((void (__fastcall *)(IXmlReaderInput *))v19->lpVtbl->Release)(v19);
    }
    ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
    v20 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    goto LABEL_81;
  }
  v21 = ppInput;
  if ( ppInput )
  {
    ppInput = 0;
    ((void (__fastcall *)(IXmlReaderInput *))v21->lpVtbl->Release)(v21);
  }
  v22 = CreateXmlReaderInputWithEncodingName(v11, 0, L"UTF-16", 0, 0, &ppInput);
  v6 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)(unsigned int)v22,
      pwszBaseUria);
    v23 = ppInput;
    if ( ppInput )
    {
      ppInput = 0;
      ((void (__fastcall *)(IXmlReaderInput *))v23->lpVtbl->Release)(v23);
    }
    ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
    v24 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
    }
    goto LABEL_81;
  }
  v25 = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppInput);
  v6 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)(unsigned int)v25,
      pwszBaseUria);
    v26 = ppInput;
    if ( ppInput )
    {
      ppInput = 0;
      ((void (__fastcall *)(IXmlReaderInput *))v26->lpVtbl->Release)(v26);
    }
    ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
    v27 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v27 + 16LL))(v27);
    }
    goto LABEL_81;
  }
  while ( 1 )
  {
    v28 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v51);
    if ( v28 )
      break;
    switch ( v51 )
    {
      case 1:
        if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) )
        {
          v29 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, __int64 *))(*(_QWORD *)ppvObject + 112LL))(
                  ppvObject,
                  &v48,
                  &v52);
          v6 = v29;
          if ( v29 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x86,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
              (const char *)(unsigned int)v29,
              pwszBaseUria);
            v30 = ppInput;
            if ( ppInput )
            {
              ppInput = 0;
              ((void (__fastcall *)(IXmlReaderInput *))v30->lpVtbl->Release)(v30);
            }
            ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
            v31 = ppvObject;
            if ( ppvObject )
            {
              ppvObject = 0;
              (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
            }
            goto LABEL_81;
          }
          goto LABEL_61;
        }
        break;
      case 3:
        v35 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, __int64 *))(*(_QWORD *)ppvObject + 128LL))(
                ppvObject,
                &v48,
                &v52);
        v6 = v35;
        if ( v35 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x90,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
            (const char *)(unsigned int)v35,
            pwszBaseUria);
          v39 = ppInput;
          if ( ppInput )
          {
            ppInput = 0;
            ((void (__fastcall *)(IXmlReaderInput *))v39->lpVtbl->Release)(v39);
          }
          ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
          v40 = ppvObject;
          if ( ppvObject )
          {
            ppvObject = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v40 + 16LL))(v40);
          }
          goto LABEL_81;
        }
LABEL_61:
        v36 = Dynamo::DpuResponseParser::ResponseParsingHandler(a1, v51, v48);
        v6 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9D,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
            (const char *)(unsigned int)v36,
            pwszBaseUria);
          v37 = ppInput;
          if ( ppInput )
          {
            ppInput = 0;
            ((void (__fastcall *)(IXmlReaderInput *))v37->lpVtbl->Release)(v37);
          }
          ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
          v38 = ppvObject;
          if ( ppvObject )
          {
            ppvObject = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v38 + 16LL))(v38);
          }
          goto LABEL_81;
        }
        break;
      case 15:
        v32 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, __int64 *))(*(_QWORD *)ppvObject + 112LL))(
                ppvObject,
                &v48,
                &v52);
        v6 = v32;
        if ( v32 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8B,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
            (const char *)(unsigned int)v32,
            pwszBaseUria);
          v33 = ppInput;
          if ( ppInput )
          {
            ppInput = 0;
            ((void (__fastcall *)(IXmlReaderInput *))v33->lpVtbl->Release)(v33);
          }
          ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
          v34 = ppvObject;
          if ( ppvObject )
          {
            ppvObject = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 16LL))(v34);
          }
          goto LABEL_81;
        }
        goto LABEL_61;
    }
  }
  v6 = 0;
  if ( v28 != 1 )
    v6 = v28;
  v41 = ppInput;
  if ( ppInput )
  {
    ppInput = 0;
    ((void (__fastcall *)(IXmlReaderInput *))v41->lpVtbl->Release)(v41);
  }
  ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
  v42 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v42 + 16LL))(v42);
  }
LABEL_81:
  CoUninitialize();
  return v6;
}

```

## disassembly

```asm
0x140042224  mov     [rsp-28h+arg_10], r8
0x140042229  push    rbp
0x14004222a  push    rbx
0x14004222b  push    rsi
0x14004222c  push    rdi
0x14004222d  push    r14
0x14004222f  mov     rbp, rsp
0x140042232  sub     rsp, 60h
0x140042236  mov     rdi, rdx
0x140042239  mov     rsi, rcx
0x14004223c  xor     r14d, r14d
0x14004223f  test    rdx, rdx
0x140042242  jz      loc_14004297B
0x140042248  cmp     r14w, [rdx]
0x14004224c  jz      loc_14004297B
0x140042252  xor     edx, edx; dwCoInit
0x140042254  xor     ecx, ecx; pvReserved
0x140042256  call    cs:__imp_CoInitializeEx
0x14004225c  mov     ebx, eax
0x14004225e  test    eax, eax
0x140042260  js      loc_14004295E
0x140042266  mov     [rbp+arg_18], 1
0x14004226d  mov     [rbp+ppvObject], r14
0x140042271  mov     [rbp+var_18], r14
0x140042275  mov     [rbp+var_28], r14
0x140042279  mov     [rbp+arg_8], r14d
0x14004227d  mov     [rbp+var_20], r14
0x140042281  mov     dword ptr [rbp+arg_10], r14d
0x140042285  mov     edx, 7FFFFFFFh
0x14004228a  mov     ecx, edx
0x14004228c  mov     rax, rdi
0x14004228f  cmp     [rax], r14w
0x140042293  jz      short loc_14004229F
0x140042295  add     rax, 2
0x140042299  sub     rcx, 1
0x14004229d  jnz     short loc_14004228F
0x14004229f  mov     rax, rcx
0x1400422a2  neg     rax
0x1400422a5  sbb     ebx, ebx
0x1400422a7  not     ebx
0x1400422a9  and     ebx, 80070057h
0x1400422af  mov     rax, rcx
0x1400422b2  sub     rdx, rcx
0x1400422b5  neg     rax
0x1400422b8  sbb     r8, r8
0x1400422bb  and     r8, rdx
0x1400422be  test    rcx, rcx
0x1400422c1  jnz     short loc_140042315
0x1400422c3  mov     rcx, [rbp+28h]; this
0x1400422c7  mov     r9d, ebx; char *
0x1400422ca  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400422d1  mov     edx, 6Bh ; 'k'; void *
0x1400422d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400422db  nop
0x1400422dc  mov     rcx, [rbp+var_28]
0x1400422e0  test    rcx, rcx
0x1400422e3  jz      short loc_1400422F6
0x1400422e5  mov     [rbp+var_28], r14
0x1400422e9  mov     rax, [rcx]
0x1400422ec  mov     rax, [rax+10h]
0x1400422f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400422f5  nop
0x1400422f6  mov     rcx, [rbp+ppvObject]
0x1400422fa  test    rcx, rcx
0x1400422fd  jz      short loc_140042310
0x1400422ff  mov     [rbp+ppvObject], r14
0x140042303  mov     rax, [rcx]
0x140042306  mov     rax, [rax+10h]
0x14004230a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004230f  nop
0x140042310  jmp     loc_140042956
0x140042315  mov     eax, 2
0x14004231a  mul     r8
0x14004231d  test    rdx, rdx
0x140042320  jnz     loc_140042904
0x140042326  mov     edx, eax; cbInit
0x140042328  mov     rcx, rdi; pInit
0x14004232b  call    cs:__imp_SHCreateMemStream
0x140042331  mov     rdi, rax
0x140042334  test    rax, rax
0x140042337  jz      loc_1400428B0
0x14004233d  mov     rcx, [rax]
0x140042340  mov     rax, [rcx+8]
0x140042344  mov     rcx, rdi
0x140042347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004234c  nop
0x14004234d  mov     [rbp+var_18], rdi
0x140042351  mov     rcx, [rbp+ppvObject]
0x140042355  test    rcx, rcx
0x140042358  jz      short loc_14004236B
0x14004235a  mov     [rbp+ppvObject], r14
0x14004235e  mov     rax, [rcx]
0x140042361  mov     rax, [rax+10h]
0x140042365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004236a  nop
0x14004236b  xor     r8d, r8d; pMalloc
0x14004236e  lea     rdx, [rbp+ppvObject]; ppvObject
0x140042372  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x140042379  call    cs:__imp_CreateXmlReader
0x14004237f  mov     ebx, eax
0x140042381  test    eax, eax
0x140042383  jns     short loc_1400423E7
0x140042385  mov     rcx, [rbp+28h]; this
0x140042389  mov     r9d, eax; char *
0x14004238c  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140042393  mov     edx, 73h ; 's'; void *
0x140042398  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004239d  nop
0x14004239e  mov     rcx, [rbp+var_28]
0x1400423a2  test    rcx, rcx
0x1400423a5  jz      short loc_1400423B8
0x1400423a7  mov     [rbp+var_28], r14
0x1400423ab  mov     rax, [rcx]
0x1400423ae  mov     rax, [rax+10h]
0x1400423b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400423b7  nop
0x1400423b8  mov     rax, [rdi]
0x1400423bb  mov     rcx, rdi
0x1400423be  mov     rax, [rax+10h]
0x1400423c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400423c7  nop
0x1400423c8  mov     rcx, [rbp+ppvObject]
0x1400423cc  test    rcx, rcx
0x1400423cf  jz      short loc_1400423E2
0x1400423d1  mov     [rbp+ppvObject], r14
0x1400423d5  mov     rax, [rcx]
0x1400423d8  mov     rax, [rax+10h]
0x1400423dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400423e1  nop
0x1400423e2  jmp     loc_140042956
0x1400423e7  mov     rcx, [rbp+ppvObject]
0x1400423eb  mov     rax, [rcx]
0x1400423ee  mov     edx, 1
0x1400423f3  mov     r8d, edx
0x1400423f6  mov     rax, [rax+28h]
0x1400423fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400423ff  mov     ebx, eax
0x140042401  test    eax, eax
0x140042403  jns     short loc_140042467
0x140042405  mov     rcx, [rbp+28h]; this
0x140042409  mov     r9d, eax; char *
0x14004240c  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140042413  mov     edx, 74h ; 't'; void *
0x140042418  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004241d  nop
0x14004241e  mov     rcx, [rbp+var_28]
0x140042422  test    rcx, rcx
0x140042425  jz      short loc_140042438
0x140042427  mov     [rbp+var_28], r14
0x14004242b  mov     rax, [rcx]
0x14004242e  mov     rax, [rax+10h]
0x140042432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042437  nop
0x140042438  mov     rax, [rdi]
0x14004243b  mov     rcx, rdi
0x14004243e  mov     rax, [rax+10h]
0x140042442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042447  nop
0x140042448  mov     rcx, [rbp+ppvObject]
0x14004244c  test    rcx, rcx
0x14004244f  jz      short loc_140042462
0x140042451  mov     [rbp+ppvObject], r14
0x140042455  mov     rax, [rcx]
0x140042458  mov     rax, [rax+10h]
0x14004245c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042461  nop
0x140042462  jmp     loc_140042956
0x140042467  mov     rcx, [rbp+ppvObject]
0x14004246b  mov     rax, [rcx]
0x14004246e  xor     r8d, r8d
0x140042471  lea     edx, [r8+4]
0x140042475  mov     rax, [rax+28h]
0x140042479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004247e  mov     ebx, eax
0x140042480  test    eax, eax
0x140042482  jns     short loc_1400424E6
0x140042484  mov     rcx, [rbp+28h]; this
0x140042488  mov     r9d, eax; char *
0x14004248b  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140042492  mov     edx, 75h ; 'u'; void *
0x140042497  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004249c  nop
0x14004249d  mov     rcx, [rbp+var_28]
0x1400424a1  test    rcx, rcx
0x1400424a4  jz      short loc_1400424B7
0x1400424a6  mov     [rbp+var_28], r14
0x1400424aa  mov     rax, [rcx]
0x1400424ad  mov     rax, [rax+10h]
0x1400424b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400424b6  nop
0x1400424b7  mov     rax, [rdi]
0x1400424ba  mov     rcx, rdi
0x1400424bd  mov     rax, [rax+10h]
0x1400424c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400424c6  nop
0x1400424c7  mov     rcx, [rbp+ppvObject]
0x1400424cb  test    rcx, rcx
0x1400424ce  jz      short loc_1400424E1
0x1400424d0  mov     [rbp+ppvObject], r14
0x1400424d4  mov     rax, [rcx]
0x1400424d7  mov     rax, [rax+10h]
0x1400424db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400424e0  nop
0x1400424e1  jmp     loc_140042956
0x1400424e6  mov     rcx, [rbp+var_28]
0x1400424ea  test    rcx, rcx
0x1400424ed  jz      short loc_140042500
0x1400424ef  mov     [rbp+var_28], r14
0x1400424f3  mov     rax, [rcx]
0x1400424f6  mov     rax, [rax+10h]
0x1400424fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400424ff  nop
0x140042500  lea     rax, [rbp+var_28]
0x140042504  mov     [rsp+60h+ppInput], rax; ppInput
0x140042509  mov     [rsp+60h+pwszBaseUri], r14; int
0x14004250e  xor     r9d, r9d; fEncodingHint
0x140042511  lea     r8, pwszEncodingName; "UTF-16"
0x140042518  xor     edx, edx; pMalloc
0x14004251a  mov     rcx, rdi; pInputStream
0x14004251d  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x140042523  mov     ebx, eax
0x140042525  test    eax, eax
0x140042527  jns     short loc_14004258B
0x140042529  mov     rcx, [rbp+28h]; this
0x14004252d  mov     r9d, eax; char *
0x140042530  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140042537  mov     edx, 76h ; 'v'; void *
0x14004253c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140042541  nop
0x140042542  mov     rcx, [rbp+var_28]
0x140042546  test    rcx, rcx
0x140042549  jz      short loc_14004255C
0x14004254b  mov     [rbp+var_28], r14
0x14004254f  mov     rax, [rcx]
0x140042552  mov     rax, [rax+10h]
0x140042556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004255b  nop
0x14004255c  mov     rax, [rdi]
0x14004255f  mov     rcx, rdi
0x140042562  mov     rax, [rax+10h]
0x140042566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004256b  nop
0x14004256c  mov     rcx, [rbp+ppvObject]
0x140042570  test    rcx, rcx
0x140042573  jz      short loc_140042586
0x140042575  mov     [rbp+ppvObject], r14
0x140042579  mov     rax, [rcx]
0x14004257c  mov     rax, [rax+10h]
0x140042580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042585  nop
0x140042586  jmp     loc_140042956
0x14004258b  mov     rcx, [rbp+ppvObject]
0x14004258f  mov     rax, [rcx]
0x140042592  mov     rdx, [rbp+var_28]
0x140042596  mov     rax, [rax+18h]
0x14004259a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004259f  mov     ebx, eax
0x1400425a1  test    eax, eax
0x1400425a3  jns     short loc_140042607
0x1400425a5  mov     rcx, [rbp+28h]; this
0x1400425a9  mov     r9d, eax; char *
0x1400425ac  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400425b3  mov     edx, 77h ; 'w'; void *
0x1400425b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400425bd  nop
0x1400425be  mov     rcx, [rbp+var_28]
0x1400425c2  test    rcx, rcx
0x1400425c5  jz      short loc_1400425D8
0x1400425c7  mov     [rbp+var_28], r14
0x1400425cb  mov     rax, [rcx]
0x1400425ce  mov     rax, [rax+10h]
0x1400425d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400425d7  nop
0x1400425d8  mov     rax, [rdi]
0x1400425db  mov     rcx, rdi
0x1400425de  mov     rax, [rax+10h]
0x1400425e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400425e7  nop
0x1400425e8  mov     rcx, [rbp+ppvObject]
0x1400425ec  test    rcx, rcx
0x1400425ef  jz      short loc_140042602
0x1400425f1  mov     [rbp+ppvObject], r14
0x1400425f5  mov     rax, [rcx]
0x1400425f8  mov     rax, [rax+10h]
0x1400425fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042601  nop
0x140042602  jmp     loc_140042956
0x140042607  mov     rcx, [rbp+ppvObject]
0x14004260b  mov     rax, [rcx]
0x14004260e  lea     rdx, [rbp+arg_8]
0x140042612  mov     rax, [rax+30h]
0x140042616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004261b  test    eax, eax
0x14004261d  jnz     loc_14004285E
0x140042623  mov     ecx, [rbp+arg_8]
0x140042626  sub     ecx, 1
0x140042629  jnz     loc_1400426CA
0x14004262f  mov     rcx, [rbp+ppvObject]
0x140042633  mov     rax, [rcx]
0x140042636  mov     rax, [rax+0A0h]
  ... truncated ...
```
