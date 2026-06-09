# EnterpriseWorkerThread::InstallApplication(_GUID,_GUID,_GUID,ushort *)

- ea: `0x1800159a4`
- end: `0x180015d71`
- name: `?InstallApplication@EnterpriseWorkerThread@@AEAAJU_GUID@@00PEAG@Z`
- size: `973`
- prototype: `__int64 __fastcall(EnterpriseWorkerThread *__hidden this, struct _GUID *, struct _GUID *, struct _GUID *, PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016aa8`

## callees

- `0x180011f54`
- `0x1800159a4`
- `0x180018518`
- `0x180018f48`
- `0x18001e394`
- `0x180028284`
- `0x180029f88`
- `0x1800636a0`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180015cef`
- `OLEAUT32!__imp_SysFreeString` at `0x180015cef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015acf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015b97`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015acf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015b97`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015b01`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015b01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015ab8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015baa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015ab8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015baa`

## string_xrefs

- `0x180015ab1`: `Windows.Foundation.Uri`
- `0x180015c5d`: `PacMan BeginEnterpriseAppInstall Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall EnterpriseWorkerThread::InstallApplication(
        EnterpriseWorkerThread *this,
        struct _GUID *a2,
        struct _GUID *a3,
        struct _GUID *a4,
        PCWSTR sourceString)
{
  int updated; // edi
  WpCoreUtilHelper *v9; // rcx
  OLECHAR *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, PVOID, __int64 *); // rsi
  __int64 v15; // rcx
  unsigned __int64 v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  PackageManagerWrapper *v21; // rax
  BSTR v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // [rsp+28h] [rbp-69h]
  __int64 v31; // [rsp+50h] [rbp-41h] BYREF
  __int64 v32; // [rsp+58h] [rbp-39h] BYREF
  int v33; // [rsp+60h] [rbp-31h] BYREF
  _DWORD v34[3]; // [rsp+64h] [rbp-2Dh] BYREF
  BSTR bstrString[2]; // [rsp+70h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-11h] BYREF

  *(struct _GUID *)bstrString = *a2;
  updated = EnterpriseWorkerThread::UpdateXAPRequestStatus(this, bstrString, 4);
  if ( updated >= 0 )
  {
    bstrString[0] = 0;
    v33 = 0;
    v34[0] = 0;
    if ( (int)PlatformFuncHelper::CheckAndInit((PlatformFuncHelper *)&s_PlatformFuncHelper) >= 0
      && (!qword_180090CB0 || (int)qword_180090CB0(1, &v33) >= 0)
      && v33
      && (int)WpCoreUtilHelper::CheckAndInit(v9) >= 0
      && s_WpCoreUtilHelper )
    {
      ((void (__fastcall *)(__int64, _QWORD, __int64, _DWORD *, const WCHAR *, char))qword_180090D18)(
        1,
        0,
        2,
        v34,
        &Src,
        55);
    }
    *(struct _GUID *)&hstringHeader.Reserved.Reserved1 = *a3;
    updated = ConvertGuidToBstr((GUID *)&hstringHeader, bstrString);
    if ( updated < 0 )
      goto LABEL_10;
    v32 = 0;
    v31 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Foundation.Uri",
           0x16u,
           (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
           (HSTRING *)&hstringHeader) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    updated = RoGetActivationFactory(hstringHeader.Reserved.Reserved1, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v31);
    if ( updated < 0 )
    {
      v11 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      v12 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
LABEL_10:
      v10 = bstrString[0];
LABEL_44:
      SysFreeString(v10);
      return (unsigned int)updated;
    }
    v13 = v31;
    v14 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v31 + 48LL);
    v15 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = -1;
    do
      ++v16;
    while ( sourceString[v16] );
    if ( v16 > 0xFFFFFFFF )
    {
      LODWORD(v16) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(
      sourceString,
      v16,
      (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
      (HSTRING *)&hstringHeader);
    updated = v14(v13, hstringHeader.Reserved.Reserved1, &v32);
    if ( updated < 0 )
    {
      v19 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      v20 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      goto LABEL_10;
    }
    v21 = (PackageManagerWrapper *)tlx::_LazyImpl<PackageManagerWrapper,tlx::lazy_construct<PackageManagerWrapper>,tlx::static_lazy<PackageManagerWrapper,0,tlx::lazy_construct<PackageManagerWrapper>>>::get(
                                     v18,
                                     v17);
    LODWORD(v30) = 64;
    v22 = bstrString[0];
    updated = PackageManagerWrapper::AddPackage(v21, bstrString[0], 0, v32, 0, v30, 0);
    if ( updated >= 0 )
    {
      if ( !*(_QWORD *)utl::_Tree<_GUID,_GUID,memory_compare_less<_GUID>,utl::allocator<_GUID>,0>::insert(
                         (char *)this + 272,
                         &hstringHeader,
                         a3) )
      {
        updated = -2147024882;
        v28 = v31;
        if ( v31 )
        {
          v31 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        }
        v29 = v32;
        if ( v32 )
        {
          v32 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        goto LABEL_43;
      }
    }
    else
    {
      *(struct _GUID *)&hstringHeader.Reserved.Reserved1 = *a2;
      updated = EnterpriseWorkerThread::UpdateXAPRequestStatus(this, &hstringHeader, 6);
      if ( updated < 0 )
      {
        v23 = v31;
        if ( v31 )
        {
          v31 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        v24 = v32;
        if ( v32 )
        {
          v32 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
LABEL_43:
        v10 = v22;
        goto LABEL_44;
      }
      updated = 0;
    }
    v25 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    goto LABEL_43;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800159a4  mov     [rsp-8+arg_18], rbx
0x1800159a9  push    rbp
0x1800159aa  push    rsi
0x1800159ab  push    rdi
0x1800159ac  push    r12
0x1800159ae  push    r13
0x1800159b0  push    r14
0x1800159b2  push    r15
0x1800159b4  lea     rbp, [rsp-1Fh]
0x1800159b9  sub     rsp, 0B0h
0x1800159c0  mov     rax, cs:__security_cookie
0x1800159c7  xor     rax, rsp
0x1800159ca  mov     [rbp+4Fh+var_40], rax
0x1800159ce  mov     r15, r8
0x1800159d1  mov     r13, rdx
0x1800159d4  mov     r14, rcx
0x1800159d7  mov     r12, [rbp+4Fh+sourceString]
0x1800159db  movaps  xmm0, xmmword ptr [rdx]
0x1800159de  movdqa  xmmword ptr [rbp+4Fh+bstrString], xmm0
0x1800159e3  mov     byte ptr [rsp+0E0h+var_B8], 37h ; '7'
0x1800159e8  lea     rax, Src
0x1800159ef  mov     [rsp+0E0h+var_C0], rax
0x1800159f4  xor     r9d, r9d
0x1800159f7  lea     r8d, [r9+4]
0x1800159fb  lea     rdx, [rbp+4Fh+bstrString]
0x1800159ff  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x180015a04  mov     edi, eax
0x180015a06  xor     esi, esi
0x180015a08  test    eax, eax
0x180015a0a  js      loc_180015CF5
0x180015a10  mov     [rbp+4Fh+bstrString], rsi
0x180015a14  mov     [rbp+4Fh+var_80], esi
0x180015a17  mov     [rbp+4Fh+var_7C], esi
0x180015a1a  lea     rcx, ?s_PlatformFuncHelper@@3VPlatformFuncHelper@@A; this
0x180015a21  call    ?CheckAndInit@PlatformFuncHelper@@AEAAJXZ; PlatformFuncHelper::CheckAndInit(void)
0x180015a26  lea     ebx, [rsi+1]
0x180015a29  test    eax, eax
0x180015a2b  js      short loc_180015A77
0x180015a2d  mov     rax, cs:qword_180090CB0
0x180015a34  test    rax, rax
0x180015a37  jz      short loc_180015A48
0x180015a39  lea     rdx, [rbp+4Fh+var_80]
0x180015a3d  mov     ecx, ebx
0x180015a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a44  test    eax, eax
0x180015a46  js      short loc_180015A77
0x180015a48  cmp     [rbp+4Fh+var_80], ebx
0x180015a4b  jb      short loc_180015A77
0x180015a4d  call    ?CheckAndInit@WpCoreUtilHelper@@AEAAJXZ; WpCoreUtilHelper::CheckAndInit(void)
0x180015a52  test    eax, eax
0x180015a54  js      short loc_180015A77
0x180015a56  cmp     cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A, rsi; WpCoreUtilHelper s_WpCoreUtilHelper
0x180015a5d  jz      short loc_180015A77
0x180015a5f  lea     r9, [rbp+4Fh+var_7C]
0x180015a63  xor     edx, edx
0x180015a65  lea     r8d, [rdx+2]
0x180015a69  mov     ecx, ebx
0x180015a6b  mov     rax, cs:qword_180090D18
0x180015a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a77  movaps  xmm0, xmmword ptr [r15]
0x180015a7b  movdqa  xmmword ptr [rbp+4Fh+hstringHeader.Reserved], xmm0
0x180015a80  lea     rdx, [rbp+4Fh+bstrString]; unsigned __int16 **
0x180015a84  lea     rcx, [rbp+4Fh+hstringHeader]; rguid
0x180015a88  call    ?ConvertGuidToBstr@@YAJU_GUID@@PEAPEAG@Z; ConvertGuidToBstr(_GUID,ushort * *)
0x180015a8d  mov     edi, eax
0x180015a8f  test    eax, eax
0x180015a91  jns     short loc_180015A9C
0x180015a93  mov     rcx, [rbp+4Fh+bstrString]
0x180015a97  jmp     loc_180015CEF
0x180015a9c  mov     [rbp+4Fh+var_88], rsi
0x180015aa0  mov     [rbp+4Fh+var_90], rsi
0x180015aa4  lea     r9, [rbp+4Fh+hstringHeader]; string
0x180015aa8  lea     r8, [rbp+4Fh+hstringHeader.Reserved+8]; hstringHeader
0x180015aac  mov     edx, 16h; length
0x180015ab1  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180015ab8  call    cs:__imp_WindowsCreateStringReference
0x180015abe  test    eax, eax
0x180015ac0  jns     short loc_180015AD5
0x180015ac2  xor     r9d, r9d; lpArguments
0x180015ac5  xor     r8d, r8d; nNumberOfArguments
0x180015ac8  mov     edx, ebx; dwExceptionFlags
0x180015aca  mov     ecx, 0C000000Dh; dwExceptionCode
0x180015acf  call    cs:__imp_RaiseException
0x180015ad5  mov     rbx, qword ptr [rbp+4Fh+hstringHeader.Reserved]
0x180015ad9  mov     rcx, [rbp+4Fh+var_90]
0x180015add  test    rcx, rcx
0x180015ae0  jz      short loc_180015AF3
0x180015ae2  mov     [rbp+4Fh+var_90], rsi
0x180015ae6  mov     rax, [rcx]
0x180015ae9  mov     rax, [rax+10h]
0x180015aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015af2  nop
0x180015af3  lea     r8, [rbp+4Fh+var_90]
0x180015af7  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x180015afe  mov     rcx, rbx
0x180015b01  call    cs:__imp_RoGetActivationFactory
0x180015b07  mov     edi, eax
0x180015b09  test    eax, eax
0x180015b0b  jns     short loc_180015B46
0x180015b0d  mov     rcx, [rbp+4Fh+var_90]
0x180015b11  test    rcx, rcx
0x180015b14  jz      short loc_180015B27
0x180015b16  mov     [rbp+4Fh+var_90], rsi
0x180015b1a  mov     rax, [rcx]
0x180015b1d  mov     rax, [rax+10h]
0x180015b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b26  nop
0x180015b27  mov     rcx, [rbp+4Fh+var_88]
0x180015b2b  test    rcx, rcx
0x180015b2e  jz      short loc_180015B41
0x180015b30  mov     [rbp+4Fh+var_88], rsi
0x180015b34  mov     rax, [rcx]
0x180015b37  mov     rax, [rax+10h]
0x180015b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b40  nop
0x180015b41  jmp     loc_180015A93
0x180015b46  mov     rdi, [rbp+4Fh+var_90]
0x180015b4a  mov     rax, [rdi]
0x180015b4d  mov     rsi, [rax+30h]
0x180015b51  mov     rcx, [rbp+4Fh+var_88]
0x180015b55  xor     eax, eax
0x180015b57  test    rcx, rcx
0x180015b5a  jz      short loc_180015B6E
0x180015b5c  mov     [rbp+4Fh+var_88], rax
0x180015b60  mov     rax, [rcx]
0x180015b63  mov     rax, [rax+10h]
0x180015b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b6c  xor     eax, eax
0x180015b6e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015b72  inc     rbx
0x180015b75  cmp     [r12+rbx*2], ax
0x180015b7a  jnz     short loc_180015B72
0x180015b7c  mov     eax, 0FFFFFFFFh
0x180015b81  cmp     rbx, rax
0x180015b84  jbe     short loc_180015B9D
0x180015b86  mov     ebx, eax
0x180015b88  xor     r9d, r9d; lpArguments
0x180015b8b  xor     r8d, r8d; nNumberOfArguments
0x180015b8e  lea     edx, [r9+1]; dwExceptionFlags
0x180015b92  mov     ecx, 0C000000Dh; dwExceptionCode
0x180015b97  call    cs:__imp_RaiseException
0x180015b9d  lea     r9, [rbp+4Fh+hstringHeader]; string
0x180015ba1  lea     r8, [rbp+4Fh+hstringHeader.Reserved+8]; hstringHeader
0x180015ba5  mov     edx, ebx; length
0x180015ba7  mov     rcx, r12; sourceString
0x180015baa  call    cs:__imp_WindowsCreateStringReference
0x180015bb0  lea     r8, [rbp+4Fh+var_88]
0x180015bb4  mov     rdx, qword ptr [rbp+4Fh+hstringHeader.Reserved]
0x180015bb8  mov     rcx, rdi
0x180015bbb  mov     rax, rsi
0x180015bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bc3  mov     edi, eax
0x180015bc5  xor     esi, esi
0x180015bc7  test    eax, eax
0x180015bc9  jns     short loc_180015C04
0x180015bcb  mov     rcx, [rbp+4Fh+var_90]
0x180015bcf  test    rcx, rcx
0x180015bd2  jz      short loc_180015BE5
0x180015bd4  mov     [rbp+4Fh+var_90], rsi
0x180015bd8  mov     rax, [rcx]
0x180015bdb  mov     rax, [rax+10h]
0x180015bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015be4  nop
0x180015be5  mov     rcx, [rbp+4Fh+var_88]
0x180015be9  test    rcx, rcx
0x180015bec  jz      short loc_180015BFF
0x180015bee  mov     [rbp+4Fh+var_88], rsi
0x180015bf2  mov     rax, [rcx]
0x180015bf5  mov     rax, [rax+10h]
0x180015bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bfe  nop
0x180015bff  jmp     loc_180015A93
0x180015c04  call    ?get@?$_LazyImpl@VPackageManagerWrapper@@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@V?$static_lazy@VPackageManagerWrapper@@$0A@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@@3@@tlx@@QEAAAEAVPackageManagerWrapper@@XZ; tlx::_LazyImpl<PackageManagerWrapper,tlx::lazy_construct<PackageManagerWrapper>,tlx::static_lazy<PackageManagerWrapper,0,tlx::lazy_construct<PackageManagerWrapper>>>::get(void)
0x180015c09  mov     [rsp+0E0h+var_98], rsi
0x180015c0e  mov     [rsp+0E0h+var_A0], rsi
0x180015c13  mov     [rsp+0E0h+var_A8], sil
0x180015c18  mov     [rsp+0E0h+var_B0], sil
0x180015c1d  mov     dword ptr [rsp+0E0h+var_B8], 40h ; '@'
0x180015c25  mov     [rsp+0E0h+var_C0], rsi
0x180015c2a  mov     r9, [rbp+4Fh+var_88]
0x180015c2e  xor     r8d, r8d
0x180015c31  mov     rbx, [rbp+4Fh+bstrString]
0x180015c35  mov     rdx, rbx
0x180015c38  mov     rcx, rax
0x180015c3b  call    ?AddPackage@PackageManagerWrapper@@QEAAJPEBG0PEAUIUriRuntimeClass@Foundation@Windows@@PEAV?$Vector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@U?$DefaultVectorOptions@PEAVUri@Foundation@Windows@@@5623@@Internal@Collections@34@W4DeploymentOptionsInternal@6Deployment@Management@4@_N4PEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@6734@2@Z; PackageManagerWrapper::AddPackage(ushort const *,ushort const *,Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *,Windows::Management::Deployment::Internal::DeploymentOptionsInternal,bool,bool,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *)
0x180015c40  mov     edi, eax
0x180015c42  lea     rdx, [rbp+4Fh+hstringHeader]
0x180015c46  test    eax, eax
0x180015c48  jns     loc_180015D1E
0x180015c4e  movaps  xmm0, xmmword ptr [r13+0]
0x180015c53  movdqa  xmmword ptr [rbp+4Fh+hstringHeader.Reserved], xmm0
0x180015c58  mov     byte ptr [rsp+0E0h+var_B8], 64h ; 'd'
0x180015c5d  lea     rax, aPacmanBeginent; "PacMan BeginEnterpriseAppInstall Failed"
0x180015c64  mov     [rsp+0E0h+var_C0], rax
0x180015c69  mov     r9d, edi
0x180015c6c  mov     r8d, 6
0x180015c72  mov     rcx, r14
0x180015c75  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x180015c7a  mov     edi, eax
0x180015c7c  test    eax, eax
0x180015c7e  jns     short loc_180015CB6
0x180015c80  mov     rcx, [rbp+4Fh+var_90]
0x180015c84  test    rcx, rcx
0x180015c87  jz      short loc_180015C9A
0x180015c89  mov     [rbp+4Fh+var_90], rsi
0x180015c8d  mov     rax, [rcx]
0x180015c90  mov     rax, [rax+10h]
0x180015c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c99  nop
0x180015c9a  mov     rcx, [rbp+4Fh+var_88]
0x180015c9e  test    rcx, rcx
0x180015ca1  jz      short loc_180015CB4
0x180015ca3  mov     [rbp+4Fh+var_88], rsi
0x180015ca7  mov     rax, [rcx]
0x180015caa  mov     rax, [rax+10h]
0x180015cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cb3  nop
0x180015cb4  jmp     short loc_180015CEC
0x180015cb6  mov     edi, esi
0x180015cb8  mov     rcx, [rbp+4Fh+var_90]
0x180015cbc  test    rcx, rcx
0x180015cbf  jz      short loc_180015CD2
0x180015cc1  mov     [rbp+4Fh+var_90], rsi
0x180015cc5  mov     rax, [rcx]
0x180015cc8  mov     rax, [rax+10h]
0x180015ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cd1  nop
0x180015cd2  mov     rcx, [rbp+4Fh+var_88]
0x180015cd6  test    rcx, rcx
0x180015cd9  jz      short loc_180015CEC
0x180015cdb  mov     [rbp+4Fh+var_88], rsi
0x180015cdf  mov     rax, [rcx]
0x180015ce2  mov     rax, [rax+10h]
0x180015ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ceb  nop
0x180015cec  mov     rcx, rbx; bstrString
0x180015cef  call    cs:__imp_SysFreeString
0x180015cf5  mov     eax, edi
0x180015cf7  mov     rcx, [rbp+4Fh+var_40]
0x180015cfb  xor     rcx, rsp; StackCookie
0x180015cfe  call    __security_check_cookie
0x180015d03  mov     rbx, [rsp+0E0h+arg_18]
0x180015d0b  add     rsp, 0B0h
0x180015d12  pop     r15
0x180015d14  pop     r14
0x180015d16  pop     r13
0x180015d18  pop     r12
0x180015d1a  pop     rdi
0x180015d1b  pop     rsi
0x180015d1c  pop     rbp
0x180015d1d  retn
0x180015d1e  lea     rcx, [r14+110h]
0x180015d25  mov     r8, r15
0x180015d28  call    ?insert@?$_Tree@U_GUID@@U1@U?$memory_compare_less@U_GUID@@@@V?$allocator@U_GUID@@@utl@@$0A@@utl@@QEAA?AU?$pair@V?$_TreeConstIt@U_GUID@@@utl@@_N@2@AEBU_GUID@@@Z; utl::_Tree<_GUID,_GUID,memory_compare_less<_GUID>,utl::allocator<_GUID>,0>::insert(_GUID const &)
0x180015d2d  cmp     [rax], rsi
0x180015d30  jnz     short loc_180015CB8
0x180015d32  mov     edi, 8007000Eh
0x180015d37  mov     rcx, [rbp+4Fh+var_90]
0x180015d3b  test    rcx, rcx
0x180015d3e  jz      short loc_180015D51
0x180015d40  mov     [rbp+4Fh+var_90], rsi
0x180015d44  mov     rax, [rcx]
0x180015d47  mov     rax, [rax+10h]
0x180015d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d50  nop
0x180015d51  mov     rcx, [rbp+4Fh+var_88]
0x180015d55  test    rcx, rcx
0x180015d58  jz      short loc_180015D6B
0x180015d5a  mov     [rbp+4Fh+var_88], rsi
0x180015d5e  mov     rax, [rcx]
0x180015d61  mov     rax, [rax+10h]
0x180015d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d6a  nop
0x180015d6b  jmp     loc_180015CEC
```
