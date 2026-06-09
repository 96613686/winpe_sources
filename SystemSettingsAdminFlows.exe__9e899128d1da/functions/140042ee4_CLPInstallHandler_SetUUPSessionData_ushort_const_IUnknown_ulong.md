# CLPInstallHandler::SetUUPSessionData(ushort const *,IUnknown *,ulong)

- ea: `0x140042ee4`
- end: `0x1400430b9`
- name: `?SetUUPSessionData@CLPInstallHandler@@AEAAJPEBGPEAUIUnknown@@K@Z`
- size: `469`
- prototype: `int(CLPInstallHandler *__hidden this, const unsigned __int16 *, struct IUnknown *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140041b08`

## callees

- `0x140005f30`
- `0x14000f164`
- `0x140026134`
- `0x140026a20`
- `0x14003aed0`
- `0x140041430`
- `0x140042ee4`
- `0x14007d010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x140042f87`
- `KERNEL32!RaiseException` at `0x140042f87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140042fc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140042fc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140042f9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140042f9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140042f49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140042f49`
- `OLEAUT32!__imp_SysFreeString` at `0x140043090`
- `OLEAUT32!__imp_SysFreeString` at `0x140043090`
- `OLEAUT32!__imp_VariantInit` at `0x140042f3c`
- `OLEAUT32!__imp_VariantInit` at `0x140042f3c`
- `Bcp47Langs!Bcp47GetMuiForm` at `0x140042fae`
- `Bcp47Langs!Bcp47GetMuiForm` at `0x140042fae`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLPInstallHandler::SetUUPSessionData(
        CLPInstallHandler *this,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        unsigned int a4)
{
  OLECHAR *v7; // rbx
  __int64 v8; // rsi
  unsigned __int64 v9; // rcx
  int MuiForm; // edi
  PCWSTR StringRawBuffer; // rax
  UINT32 length; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  LONGLONG v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v19[264]; // [rsp+80h] [rbp-80h] BYREF

  v7 = 0;
  v15 = 0;
  v16 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  WindowsDeleteString(0);
  string = 0;
  length = 0;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  if ( (int)ULongLongToUInt(v9, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(
    a2,
    length,
    (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
    (HSTRING *)&hstringHeader);
  MuiForm = Bcp47GetMuiForm(hstringHeader.Reserved.Reserved1, &string);
  if ( MuiForm >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    MuiForm = StringCchPrintfW(
                v19,
                0x104u,
                L"{\n"
                 " \"ModuleID\" : \"LangPack\",\n"
                 " \"Features\": [\n"
                 " { \"name\":\"Language.UI.Client\", \"language\":\"%s\" }\n"
                 " ]\n"
                 " }",
                StringRawBuffer);
    if ( MuiForm >= 0 )
    {
      do
        ++v8;
      while ( v19[v8] );
      MuiForm = ATL::CComBSTR::Append((ATL::CComBSTR *)&v15, v19, v8);
      v7 = (OLECHAR *)v15;
      if ( MuiForm >= 0 )
      {
        pvarg.vt = 8;
        pvarg.llVal = v15;
        MuiForm = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
                    a3,
                    &IID_IUpdateInternalConfiguration,
                    &v16);
        if ( MuiForm >= 0 )
        {
          hstringHeader = (HSTRING_HEADER)pvarg;
          MuiForm = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING_HEADER *))(*(_QWORD *)v16 + 32LL))(
                      v16,
                      a4,
                      &hstringHeader);
        }
      }
    }
  }
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v16);
  SysFreeString(v7);
  return (unsigned int)MuiForm;
}

```

## disassembly

```asm
0x140042ee4  push    rbp
0x140042ee6  push    rbx
0x140042ee7  push    rsi
0x140042ee8  push    rdi
0x140042ee9  push    r12
0x140042eeb  push    r14
0x140042eed  push    r15
0x140042eef  lea     rbp, [rsp-1A0h]
0x140042ef7  sub     rsp, 2A0h
0x140042efe  mov     rax, cs:__security_cookie
0x140042f05  xor     rax, rsp
0x140042f08  mov     [rbp+1D0h+var_40], rax
0x140042f0f  mov     r15d, r9d
0x140042f12  mov     r14, r8
0x140042f15  mov     rdi, rdx
0x140042f18  xor     r12d, r12d
0x140042f1b  mov     ebx, r12d
0x140042f1e  mov     [rsp+2D0h+var_2A0], rbx
0x140042f23  mov     [rsp+2D0h+var_298], r12
0x140042f28  xorps   xmm0, xmm0
0x140042f2b  xor     eax, eax
0x140042f2d  movups  xmmword ptr [rsp+2D0h+pvarg], xmm0
0x140042f32  mov     qword ptr [rsp+2D0h+pvarg+10h], rax
0x140042f37  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x140042f3c  call    cs:__imp_VariantInit
0x140042f42  mov     [rsp+2D0h+string], r12
0x140042f47  xor     ecx, ecx; string
0x140042f49  call    cs:__imp_WindowsDeleteString
0x140042f4f  mov     [rsp+2D0h+string], r12
0x140042f54  mov     [rsp+2D0h+length], r12d
0x140042f59  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140042f5d  mov     rcx, rsi
0x140042f60  inc     rcx; unsigned __int64
0x140042f63  cmp     [rdi+rcx*2], r12w
0x140042f68  jnz     short loc_140042F60
0x140042f6a  lea     rdx, [rsp+2D0h+length]; unsigned int *
0x140042f6f  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x140042f74  test    eax, eax
0x140042f76  jns     short loc_140042F8D
0x140042f78  xor     r9d, r9d; lpArguments
0x140042f7b  xor     r8d, r8d; nNumberOfArguments
0x140042f7e  lea     edx, [r9+1]; dwExceptionFlags
0x140042f82  mov     ecx, 0C000000Dh; dwExceptionCode
0x140042f87  call    cs:__imp_RaiseException
0x140042f8d  lea     r9, [rsp+2D0h+hstringHeader]; string
0x140042f92  lea     r8, [rsp+2D0h+hstringHeader.Reserved+8]; hstringHeader
0x140042f97  mov     edx, [rsp+2D0h+length]; length
0x140042f9b  mov     rcx, rdi; sourceString
0x140042f9e  call    cs:__imp_WindowsCreateStringReference
0x140042fa4  lea     rdx, [rsp+2D0h+string]
0x140042fa9  mov     rcx, qword ptr [rsp+2D0h+hstringHeader.Reserved]
0x140042fae  call    cs:__imp_Bcp47GetMuiForm
0x140042fb4  mov     edi, eax
0x140042fb6  test    eax, eax
0x140042fb8  js      loc_140043077
0x140042fbe  xor     edx, edx; length
0x140042fc0  mov     rcx, [rsp+2D0h+string]; string
0x140042fc5  call    cs:__imp_WindowsGetStringRawBuffer
0x140042fcb  mov     r9, rax
0x140042fce  lea     r8, aModuleidLangpa; "{\n \"ModuleID\" : \"LangPack\",\n \"Fe"...
0x140042fd5  mov     edx, 104h; unsigned __int64
0x140042fda  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x140042fde  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140042fe3  mov     edi, eax
0x140042fe5  test    eax, eax
0x140042fe7  js      loc_140043077
0x140042fed  lea     rax, [rbp+1D0h+var_250]
0x140042ff1  inc     rsi
0x140042ff4  cmp     [rax+rsi*2], r12w
0x140042ff9  jnz     short loc_140042FF1
0x140042ffb  mov     r8d, esi; int
0x140042ffe  lea     rdx, [rbp+1D0h+var_250]; unsigned __int16 *
0x140043002  lea     rcx, [rsp+2D0h+var_2A0]; this
0x140043007  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x14004300c  mov     edi, eax
0x14004300e  mov     rbx, [rsp+2D0h+var_2A0]
0x140043013  test    eax, eax
0x140043015  js      short loc_140043077
0x140043017  mov     eax, 8
0x14004301c  mov     word ptr [rsp+2D0h+pvarg], ax
0x140043021  mov     qword ptr [rsp+2D0h+pvarg+8], rbx
0x140043026  mov     rax, [r14]
0x140043029  lea     r8, [rsp+2D0h+var_298]
0x14004302e  lea     rdx, IID_IUpdateInternalConfiguration
0x140043035  mov     rcx, r14
0x140043038  mov     rax, [rax]
0x14004303b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043040  mov     edi, eax
0x140043042  test    eax, eax
0x140043044  js      short loc_140043077
0x140043046  mov     rcx, [rsp+2D0h+var_298]
0x14004304b  movups  xmm0, xmmword ptr [rsp+2D0h+pvarg]
0x140043050  movaps  xmmword ptr [rsp+2D0h+hstringHeader.Reserved], xmm0
0x140043055  movsd   xmm1, qword ptr [rsp+2D0h+pvarg+10h]
0x14004305b  movsd   qword ptr [rsp+2D0h+hstringHeader.Reserved+10h], xmm1
0x140043061  mov     rax, [rcx]
0x140043064  lea     r8, [rsp+2D0h+hstringHeader]
0x140043069  mov     edx, r15d
0x14004306c  mov     rax, [rax+20h]
0x140043070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043075  mov     edi, eax
0x140043077  lea     rcx, [rsp+2D0h+string]; this
0x14004307c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x140043081  nop
0x140043082  lea     rcx, [rsp+2D0h+var_298]
0x140043087  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14004308c  nop
0x14004308d  mov     rcx, rbx; bstrString
0x140043090  call    cs:__imp_SysFreeString
0x140043096  mov     eax, edi
0x140043098  mov     rcx, [rbp+1D0h+var_40]
0x14004309f  xor     rcx, rsp; StackCookie
0x1400430a2  call    __security_check_cookie
0x1400430a7  add     rsp, 2A0h
0x1400430ae  pop     r15
0x1400430b0  pop     r14
0x1400430b2  pop     r12
0x1400430b4  pop     rdi
0x1400430b5  pop     rsi
0x1400430b6  pop     rbx
0x1400430b7  pop     rbp
0x1400430b8  retn
```
