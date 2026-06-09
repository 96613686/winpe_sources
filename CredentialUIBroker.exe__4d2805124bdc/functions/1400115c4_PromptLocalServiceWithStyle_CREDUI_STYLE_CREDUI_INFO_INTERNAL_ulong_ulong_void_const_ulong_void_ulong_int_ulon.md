# PromptLocalServiceWithStyle(CREDUI_STYLE,CREDUI_INFO_INTERNAL *,ulong,ulong *,void const *,ulong,void * *,ulong *,int *,ulong,unsigned __int64,ulong *)

- ea: `0x1400115c4`
- end: `0x140011a14`
- name: `?PromptLocalServiceWithStyle@@YAJW4CREDUI_STYLE@@PEAUCREDUI_INFO_INTERNAL@@KPEAKPEBXKPEAPEAX2PEAHK_K2@Z`
- size: `1104`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, void *Src, ULONG cElements, _QWORD *, _DWORD *, __int64, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400137d4`

## callees

- `0x140003620`
- `0x140006ee8`
- `0x140007b0c`
- `0x140008b98`
- `0x14000b47c`
- `0x14000e920`
- `0x1400115c4`
- `0x1400136fc`
- `0x140016a54`
- `0x14001e060`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140011927`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140011927`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140011695`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140011968`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1400119e5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140011695`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140011968`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1400119e5`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x140011882`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x140011882`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x140011895`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x140011895`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1400118fc`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1400118fc`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1400118af`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1400118af`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14001166b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140011914`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1400119b9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14001166b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140011914`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1400119b9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140011689`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001195e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400119dc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140011689`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14001195e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400119dc`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1400118d0`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1400118d0`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x14001162c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x14001162c`

## string_xrefs

- `0x1400116e3`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x1400116fb`: `shellcommon\internal\shell\inc\CredUIApiCommon.h`
- `0x140011764`: `shellcommon\internal\shell\inc\CredUIApiCommon.h`
- `0x1400117b5`: `shellcommon\internal\shell\inc\CredUIApiCommon.h`

## pseudocode

```c
__int64 __fastcall PromptLocalServiceWithStyle(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        void *Src,
        ULONG cElements,
        _QWORD *a7,
        _DWORD *a8,
        __int64 a9,
        int a10,
        __int64 a11,
        _DWORD *a12)
{
  __int64 v14; // rax
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64, _QWORD); // rbx
  int v20; // eax
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64 *); // rdi
  int v23; // eax
  int v25; // eax
  SIZE_T v26; // rcx
  void *v27; // rax
  __int64 v28; // rcx
  _BYTE *Reserved1; // rax
  __int64 v30; // rcx
  unsigned int *v31; // rdi
  SAFEARRAY **v32; // rbx
  __int64 v33; // rcx
  _BYTE *v34; // rax
  int v35; // [rsp+20h] [rbp-C9h]
  int v36; // [rsp+20h] [rbp-C9h]
  VARTYPE pvt; // [rsp+60h] [rbp-89h] BYREF
  __int64 v38; // [rsp+68h] [rbp-81h] BYREF
  SAFEARRAY *v39; // [rsp+70h] [rbp-79h] BYREF
  size_t Size; // [rsp+78h] [rbp-71h] BYREF
  SAFEARRAY *psa; // [rsp+80h] [rbp-69h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-61h] BYREF
  LONG plUbound[2]; // [rsp+90h] [rbp-59h] BYREF
  LONG plLbound; // [rsp+98h] [rbp-51h] BYREF
  __int64 v45; // [rsp+A0h] [rbp-49h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-41h]
  unsigned int *v47; // [rsp+B0h] [rbp-39h] BYREF
  SAFEARRAY **v48; // [rsp+B8h] [rbp-31h]
  char v49; // [rsp+C0h] [rbp-29h]
  HSTRING_HEADER ppvData; // [rsp+C8h] [rbp-21h] BYREF
  __int64 v51; // [rsp+E0h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+3Fh]

  *a12 = 1237;
  v46 = a4;
  LODWORD(Size) = cElements;
  *(_QWORD *)plUbound = a9;
  psa = SafeArrayCreateVector(0x11u, 0, cElements);
  v14 = lambda_987bc0ae049827ff44c300eba3d3b8aa_::_lambda_987bc0ae049827ff44c300eba3d3b8aa_(&ppvData, &Size, &psa);
  wil::ScopeExit__lambda_987bc0ae049827ff44c300eba3d3b8aa___(&v47, v14);
  if ( psa && (_DWORD)Size )
  {
    ppvData.Reserved.Reserved1 = 0;
    if ( SafeArrayAccessData(psa, &ppvData.Reserved.Reserved1) < 0 )
    {
      SafeArrayDestroy(psa);
      psa = 0;
    }
    else
    {
      memcpy_0(ppvData.Reserved.Reserved1, Src, (unsigned int)Size);
      SafeArrayUnaccessData(psa);
    }
  }
  v38 = 0;
  v51 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &ppvData,
    L"Windows.Internal.Shell.CredUXHostForHighIL",
    0x2Bu,
    0x2Au);
  v15 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
          v51,
          0,
          &GUID_acdccf87_b4d6_4f06_8168_a4d857e88e46,
          &v38);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x299,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v15,
      v35);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x164,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\CredUIApiCommon.h",
      (const char *)v16,
      v36);
    v17 = v38;
    if ( v38 )
    {
      v38 = 0;
LABEL_15:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  v42 = 0;
  v51 = 0;
  v18 = v38;
  v19 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v38 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  v20 = v19(v18, a11, &v42);
  v16 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x167,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\CredUIApiCommon.h",
      (const char *)(unsigned int)v20,
      v35);
    goto LABEL_13;
  }
  v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
  v45 = 0;
  v22 = **v42;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
  v23 = v22(v21, &GUID_c76cd2e4_1e90_440a_8e08_1cd1812d9bed, &v45);
  v16 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16A,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\CredUIApiCommon.h",
      (const char *)(unsigned int)v23,
      v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
LABEL_13:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
    v17 = v38;
    if ( v38 )
    {
      v38 = 0;
      goto LABEL_15;
    }
LABEL_16:
    wil::details::ScopeExitFn__lambda_987bc0ae049827ff44c300eba3d3b8aa___::_ScopeExitFn__lambda_987bc0ae049827ff44c300eba3d3b8aa___(&v47);
    return v16;
  }
  v39 = 0;
  v25 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int, __int64, SAFEARRAY *, SAFEARRAY **, _QWORD, int, _DWORD *))(*(_QWORD *)v45 + 24LL))(
          v45,
          a2,
          0,
          0,
          a3,
          v46,
          psa,
          &v39,
          *(_QWORD *)plUbound,
          a10,
          a12);
  plLbound = 0;
  pvt = 0;
  if ( v25 >= 0
    && SafeArrayGetDim(v39) == 1
    && SafeArrayGetElemsize(v39) == 1
    && SafeArrayGetLBound(v39, 1u, &plLbound) >= 0
    && !plLbound
    && SafeArrayGetVartype(v39, &pvt) >= 0
    && pvt == 17 )
  {
    ppvData.Reserved.Reserved1 = 0;
    plUbound[0] = 0;
    if ( SafeArrayGetUBound(v39, 1u, plUbound) >= 0
      && plUbound[0] > 0
      && SafeArrayAccessData(v39, &ppvData.Reserved.Reserved1) >= 0 )
    {
      v26 = (unsigned int)(plUbound[0] + 1);
      *a8 = plUbound[0] + 1;
      v27 = CoTaskMemAlloc(v26);
      *a7 = v27;
      if ( v27 )
        memcpy_0(v27, ppvData.Reserved.Reserved1, (unsigned int)*a8);
      v28 = (unsigned int)*a8;
      Reserved1 = ppvData.Reserved.Reserved1;
      if ( *a8 )
      {
        do
        {
          *Reserved1++ = 0;
          --v28;
        }
        while ( v28 );
      }
      SafeArrayUnaccessData(v39);
    }
  }
  SafeArrayDestroy(v39);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  v30 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  if ( v49 )
  {
    v31 = v47;
    v32 = v48;
    if ( *v47 )
    {
      ppvData.Reserved.Reserved1 = 0;
      if ( SafeArrayAccessData(*v48, &ppvData.Reserved.Reserved1) >= 0 )
      {
        v33 = *v31;
        v34 = ppvData.Reserved.Reserved1;
        if ( *v31 )
        {
          do
          {
            *v34++ = 0;
            --v33;
          }
          while ( v33 );
        }
        SafeArrayUnaccessData(*v32);
      }
    }
    SafeArrayDestroy(*v32);
  }
  return 0;
}

```

## disassembly

```asm
0x1400115c4  mov     [rsp-8+arg_0], rbx
0x1400115c9  push    rbp
0x1400115ca  push    rsi
0x1400115cb  push    rdi
0x1400115cc  push    r12
0x1400115ce  push    r13
0x1400115d0  push    r14
0x1400115d2  push    r15
0x1400115d4  lea     rbp, [rsp-7]
0x1400115d9  sub     rsp, 0F0h
0x1400115e0  mov     rax, cs:__security_cookie
0x1400115e7  xor     rax, rsp
0x1400115ea  mov     [rbp+37h+var_38], rax
0x1400115ee  mov     rax, [rbp+37h+arg_40]
0x1400115f5  mov     r13d, r8d
0x1400115f8  mov     r8d, [rbp+37h+cElements]; cElements
0x1400115fc  mov     r12, rdx
0x1400115ff  mov     r15, [rbp+37h+arg_58]
0x140011606  mov     ecx, 11h; vt
0x14001160b  mov     rbx, [rbp+37h+Src]
0x14001160f  xor     edx, edx; lLbound
0x140011611  mov     r14, [rbp+37h+arg_30]
0x140011615  mov     rsi, [rbp+37h+arg_38]
0x140011619  mov     dword ptr [r15], 4D5h
0x140011620  mov     [rbp+37h+var_78], r9
0x140011624  mov     dword ptr [rbp+37h+Size], r8d
0x140011628  mov     qword ptr [rbp+37h+plUbound], rax
0x14001162c  call    cs:__imp_SafeArrayCreateVector
0x140011632  lea     r8, [rbp+37h+psa]
0x140011636  mov     [rbp+37h+psa], rax
0x14001163a  lea     rdx, [rbp+37h+Size]
0x14001163e  lea     rcx, [rbp+37h+ppvData]
0x140011642  call    _lambda_987bc0ae049827ff44c300eba3d3b8aa____lambda_987bc0ae049827ff44c300eba3d3b8aa_
0x140011647  mov     rdx, rax
0x14001164a  lea     rcx, [rbp+37h+var_70]
0x14001164e  call    wil__ScopeExit__lambda_987bc0ae049827ff44c300eba3d3b8aa___
0x140011653  mov     rcx, [rbp+37h+psa]; psa
0x140011657  xor     edi, edi
0x140011659  test    rcx, rcx
0x14001165c  jz      short loc_14001169F
0x14001165e  cmp     dword ptr [rbp+37h+Size], edi
0x140011661  jbe     short loc_14001169F
0x140011663  lea     rdx, [rbp+37h+ppvData]; ppvData
0x140011667  mov     qword ptr [rbp+37h+ppvData], rdi
0x14001166b  call    cs:__imp_SafeArrayAccessData
0x140011671  test    eax, eax
0x140011673  js      short loc_140011691
0x140011675  mov     r8d, dword ptr [rbp+37h+Size]; Size
0x140011679  mov     rdx, rbx; Src
0x14001167c  mov     rcx, qword ptr [rbp+37h+ppvData]; void *
0x140011680  call    memcpy_0
0x140011685  mov     rcx, [rbp+37h+psa]; psa
0x140011689  call    cs:__imp_SafeArrayUnaccessData
0x14001168f  jmp     short loc_14001169F
0x140011691  mov     rcx, [rbp+37h+psa]; psa
0x140011695  call    cs:__imp_SafeArrayDestroy
0x14001169b  mov     [rbp+37h+psa], rdi
0x14001169f  mov     r9d, 2Ah ; '*'; unsigned int
0x1400116a5  mov     [rsp+120h+var_B8], rdi
0x1400116aa  lea     rdx, sourceString; "Windows.Internal.Shell.CredUXHostForHig"...
0x1400116b1  mov     [rbp+37h+var_40], rdi
0x1400116b5  lea     rcx, [rbp+37h+ppvData]; hstringHeader
0x1400116b9  lea     r8d, [r9+1]; unsigned int
0x1400116bd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400116c2  mov     rcx, [rbp+37h+var_40]
0x1400116c6  lea     r9, [rsp+120h+var_B8]
0x1400116cb  lea     r8, _GUID_acdccf87_b4d6_4f06_8168_a4d857e88e46
0x1400116d2  mov     edx, edi
0x1400116d4  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x1400116d9  mov     ebx, eax
0x1400116db  test    eax, eax
0x1400116dd  jns     short loc_140011727
0x1400116df  mov     rcx, [rbp+3Fh]; this
0x1400116e3  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1400116ea  mov     r9d, eax; char *
0x1400116ed  mov     edx, 299h; void *
0x1400116f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400116f7  mov     rcx, [rbp+3Fh]; this
0x1400116fb  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Cred"...
0x140011702  mov     r9d, ebx; char *
0x140011705  mov     edx, 164h; void *
0x14001170a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001170f  mov     rcx, [rsp+120h+var_B8]
0x140011714  test    rcx, rcx
0x140011717  jz      loc_1400117FA
0x14001171d  mov     [rsp+120h+var_B8], rdi
0x140011722  jmp     loc_1400117EE
0x140011727  mov     [rbp+37h+var_98], rdi
0x14001172b  lea     rcx, [rbp+37h+var_98]
0x14001172f  mov     [rbp+37h+var_40], rdi
0x140011733  mov     rdi, [rsp+120h+var_B8]
0x140011738  mov     rax, [rdi]
0x14001173b  mov     rbx, [rax+30h]
0x14001173f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011744  mov     rdx, [rbp+37h+arg_50]
0x14001174b  lea     r8, [rbp+37h+var_98]
0x14001174f  mov     rcx, rdi
0x140011752  mov     rax, rbx
0x140011755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001175a  mov     ebx, eax
0x14001175c  test    eax, eax
0x14001175e  jns     short loc_14001177A
0x140011760  mov     rcx, [rbp+3Fh]; this
0x140011764  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Cred"...
0x14001176b  mov     r9d, eax; char *
0x14001176e  mov     edx, 167h; void *
0x140011773  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011778  jmp     short loc_1400117D2
0x14001177a  mov     rbx, [rbp+37h+var_98]
0x14001177e  lea     rcx, [rbp+37h+var_80]
0x140011782  mov     [rbp+37h+var_80], 0
0x14001178a  mov     rax, [rbx]
0x14001178d  mov     rdi, [rax]
0x140011790  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011795  lea     r8, [rbp+37h+var_80]
0x140011799  mov     rcx, rbx
0x14001179c  lea     rdx, _GUID_c76cd2e4_1e90_440a_8e08_1cd1812d9bed
0x1400117a3  mov     rax, rdi
0x1400117a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400117ab  mov     ebx, eax
0x1400117ad  test    eax, eax
0x1400117af  jns     short loc_14001180A
0x1400117b1  mov     rcx, [rbp+3Fh]; this
0x1400117b5  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Cred"...
0x1400117bc  mov     r9d, eax; char *
0x1400117bf  mov     edx, 16Ah; void *
0x1400117c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400117c9  lea     rcx, [rbp+37h+var_80]
0x1400117cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400117d2  lea     rcx, [rbp+37h+var_98]
0x1400117d6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400117db  mov     rcx, [rsp+120h+var_B8]
0x1400117e0  test    rcx, rcx
0x1400117e3  jz      short loc_1400117FA
0x1400117e5  mov     [rsp+120h+var_B8], 0
0x1400117ee  mov     rax, [rcx]
0x1400117f1  mov     rax, [rax+10h]
0x1400117f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400117fa  lea     rcx, [rbp+37h+var_70]
0x1400117fe  call    wil__details__ScopeExitFn__lambda_987bc0ae049827ff44c300eba3d3b8aa______ScopeExitFn__lambda_987bc0ae049827ff44c300eba3d3b8aa___
0x140011803  mov     eax, ebx
0x140011805  jmp     loc_1400119ED
0x14001180a  mov     r9, [rbp+37h+psa]
0x14001180e  mov     rcx, [rbp+37h+var_80]
0x140011812  mov     r8d, [rbp+37h+arg_48]
0x140011819  mov     rdx, qword ptr [rbp+37h+plUbound]
0x14001181d  mov     [rsp+120h+var_D0], r15
0x140011822  mov     [rsp+120h+var_D8], r8d
0x140011827  xor     r8d, r8d
0x14001182a  mov     [rsp+120h+var_E0], rdx
0x14001182f  lea     rdx, [rbp+37h+var_B0]
0x140011833  mov     [rsp+120h+var_E8], rdx
0x140011838  mov     rdx, [rbp+37h+var_78]
0x14001183c  mov     [rsp+120h+var_F0], r9
0x140011841  xor     r9d, r9d
0x140011844  mov     [rsp+120h+var_F8], rdx
0x140011849  mov     rdx, r12
0x14001184c  mov     [rbp+37h+var_B0], 0
0x140011854  mov     rax, [rcx]
0x140011857  mov     [rsp+120h+var_100], r13d
0x14001185c  mov     rax, [rax+18h]
0x140011860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011865  xor     r15d, r15d
0x140011868  mov     [rbp+37h+plLbound], r15d
0x14001186c  mov     [rsp+120h+pvt], r15w
0x140011872  lea     r12d, [r15+1]
0x140011876  test    eax, eax
0x140011878  js      loc_140011964
0x14001187e  mov     rcx, [rbp+37h+var_B0]; psa
0x140011882  call    cs:__imp_SafeArrayGetDim
0x140011888  cmp     eax, r12d
0x14001188b  jnz     loc_140011964
0x140011891  mov     rcx, [rbp+37h+var_B0]; psa
0x140011895  call    cs:__imp_SafeArrayGetElemsize
0x14001189b  cmp     eax, r12d
0x14001189e  jnz     loc_140011964
0x1400118a4  mov     rcx, [rbp+37h+var_B0]; psa
0x1400118a8  lea     r8, [rbp+37h+plLbound]; plLbound
0x1400118ac  mov     edx, r12d; nDim
0x1400118af  call    cs:__imp_SafeArrayGetLBound
0x1400118b5  test    eax, eax
0x1400118b7  js      loc_140011964
0x1400118bd  cmp     [rbp+37h+plLbound], r15d
0x1400118c1  jnz     loc_140011964
0x1400118c7  mov     rcx, [rbp+37h+var_B0]; psa
0x1400118cb  lea     rdx, [rsp+120h+pvt]; pvt
0x1400118d0  call    cs:__imp_SafeArrayGetVartype
0x1400118d6  test    eax, eax
0x1400118d8  js      loc_140011964
0x1400118de  lea     eax, [r15+11h]
0x1400118e2  cmp     [rsp+120h+pvt], ax
0x1400118e7  jnz     short loc_140011964
0x1400118e9  mov     rcx, [rbp+37h+var_B0]; psa
0x1400118ed  lea     r8, [rbp+37h+plUbound]; plUbound
0x1400118f1  mov     edx, r12d; nDim
0x1400118f4  mov     qword ptr [rbp+37h+ppvData], r15
0x1400118f8  mov     [rbp+37h+plUbound], r15d
0x1400118fc  call    cs:__imp_SafeArrayGetUBound
0x140011902  test    eax, eax
0x140011904  js      short loc_140011964
0x140011906  cmp     [rbp+37h+plUbound], r15d
0x14001190a  jle     short loc_140011964
0x14001190c  mov     rcx, [rbp+37h+var_B0]; psa
0x140011910  lea     rdx, [rbp+37h+ppvData]; ppvData
0x140011914  call    cs:__imp_SafeArrayAccessData
0x14001191a  test    eax, eax
0x14001191c  js      short loc_140011964
0x14001191e  mov     eax, [rbp+37h+plUbound]
0x140011921  inc     eax
0x140011923  mov     ecx, eax; cb
0x140011925  mov     [rsi], eax
0x140011927  call    cs:__imp_CoTaskMemAlloc
0x14001192d  mov     [r14], rax
0x140011930  test    rax, rax
0x140011933  jz      short loc_140011944
0x140011935  mov     r8d, [rsi]; Size
0x140011938  mov     rcx, rax; void *
0x14001193b  mov     rdx, qword ptr [rbp+37h+ppvData]; Src
0x14001193f  call    memcpy_0
0x140011944  mov     ecx, [rsi]
0x140011946  mov     rax, qword ptr [rbp+37h+ppvData]
0x14001194a  test    rcx, rcx
0x14001194d  jz      short loc_14001195A
0x14001194f  mov     [rax], r15b
0x140011952  add     rax, r12
0x140011955  sub     rcx, r12
0x140011958  jnz     short loc_14001194F
0x14001195a  mov     rcx, [rbp+37h+var_B0]; psa
0x14001195e  call    cs:__imp_SafeArrayUnaccessData
0x140011964  mov     rcx, [rbp+37h+var_B0]; psa
0x140011968  call    cs:__imp_SafeArrayDestroy
0x14001196e  lea     rcx, [rbp+37h+var_80]
0x140011972  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011977  lea     rcx, [rbp+37h+var_98]
0x14001197b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011980  mov     rcx, [rsp+120h+var_B8]
0x140011985  test    rcx, rcx
0x140011988  jz      short loc_14001199B
0x14001198a  mov     [rsp+120h+var_B8], r15
0x14001198f  mov     rax, [rcx]
0x140011992  mov     rax, [rax+10h]
0x140011996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001199b  cmp     [rbp+37h+var_60], r15b
0x14001199f  jz      short loc_1400119EB
0x1400119a1  mov     rdi, [rbp+37h+var_70]
0x1400119a5  mov     rbx, [rbp+37h+var_68]
0x1400119a9  cmp     [rdi], r15d
0x1400119ac  jbe     short loc_1400119E2
0x1400119ae  mov     qword ptr [rbp+37h+ppvData], r15
0x1400119b2  lea     rdx, [rbp+37h+ppvData]; ppvData
0x1400119b6  mov     rcx, [rbx]; psa
0x1400119b9  call    cs:__imp_SafeArrayAccessData
0x1400119bf  test    eax, eax
0x1400119c1  js      short loc_1400119E2
0x1400119c3  mov     ecx, [rdi]
0x1400119c5  mov     rax, qword ptr [rbp+37h+ppvData]
0x1400119c9  test    rcx, rcx
0x1400119cc  jz      short loc_1400119D9
0x1400119ce  mov     [rax], r15b
0x1400119d1  add     rax, r12
0x1400119d4  sub     rcx, r12
0x1400119d7  jnz     short loc_1400119CE
0x1400119d9  mov     rcx, [rbx]; psa
0x1400119dc  call    cs:__imp_SafeArrayUnaccessData
0x1400119e2  mov     rcx, [rbx]; psa
0x1400119e5  call    cs:__imp_SafeArrayDestroy
0x1400119eb  xor     eax, eax
0x1400119ed  mov     rcx, [rbp+37h+var_38]
0x1400119f1  xor     rcx, rsp; StackCookie
0x1400119f4  call    __security_check_cookie
0x1400119f9  mov     rbx, [rsp+120h+arg_0]
0x140011a01  add     rsp, 0F0h
0x140011a08  pop     r15
0x140011a0a  pop     r14
0x140011a0c  pop     r13
0x140011a0e  pop     r12
0x140011a10  pop     rdi
0x140011a11  pop     rsi
0x140011a12  pop     rbp
0x140011a13  retn
```
