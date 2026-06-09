# EnterpriseWorkerThread::InstallApplication(_GUID,_GUID,_GUID,ushort *)

- ea: `0x1800166d8`
- end: `0x180016a7a`
- name: `?InstallApplication@EnterpriseWorkerThread@@AEAAJU_GUID@@00PEAG@Z`
- size: `930`
- prototype: `__int64 __fastcall(EnterpriseWorkerThread *__hidden this, struct _GUID *, struct _GUID *, struct _GUID *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800177d0`

## callees

- `0x1800127c8`
- `0x1800147e0`
- `0x1800166d8`
- `0x180019384`
- `0x18001a18c`
- `0x18001f908`
- `0x18002a4b0`
- `0x18002c194`
- `0x180068de8`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800169fd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800169fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001680c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001680c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180016844`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180016844`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800167ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800167ef`

## string_xrefs

- `0x1800167e8`: `Windows.Foundation.Uri`
- `0x18001696a`: `PacMan BeginEnterpriseAppInstall Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall EnterpriseWorkerThread::InstallApplication(
        EnterpriseWorkerThread *this,
        struct _GUID *a2,
        struct _GUID *a3,
        struct _GUID *a4,
        unsigned __int16 *a5)
{
  int updated; // edi
  WpCoreUtilHelper *v9; // rcx
  OLECHAR *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rdi
  __int64 v15; // rcx
  _QWORD *v16; // rax
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
  __int64 v30; // [rsp+28h] [rbp-79h]
  __int64 v31; // [rsp+50h] [rbp-51h] BYREF
  __int64 v32; // [rsp+58h] [rbp-49h] BYREF
  int v33; // [rsp+60h] [rbp-41h] BYREF
  _DWORD v34[3]; // [rsp+64h] [rbp-3Dh] BYREF
  BSTR bstrString[2]; // [rsp+70h] [rbp-31h] BYREF
  unsigned __int16 *v36; // [rsp+80h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-11h] BYREF

  v36 = a5;
  *(struct _GUID *)bstrString = *a2;
  updated = EnterpriseWorkerThread::UpdateXAPRequestStatus(this, bstrString, 4);
  if ( updated >= 0 )
  {
    bstrString[0] = 0;
    v33 = 0;
    v34[0] = 0;
    if ( (int)PlatformFuncHelper::CheckAndInit((PlatformFuncHelper *)&s_PlatformFuncHelper) >= 0
      && (!qword_180096CB0 || (int)qword_180096CB0(1, &v33) >= 0)
      && v33
      && (int)WpCoreUtilHelper::CheckAndInit(v9) >= 0
      && s_WpCoreUtilHelper )
    {
      ((void (__fastcall *)(__int64, _QWORD, __int64, _DWORD *, const WCHAR *, char))qword_180096D18)(
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
LABEL_40:
      SysFreeString(v10);
      return (unsigned int)updated;
    }
    v13 = v31;
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 48LL);
    v15 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = (_QWORD *)Windows::Internal::StringReference::StringReference(&hstringHeader, &v36);
    updated = v14(v13, *v16, &v32);
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
        goto LABEL_39;
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
LABEL_39:
        v10 = v22;
        goto LABEL_40;
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
    goto LABEL_39;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800166d8  push    rbp
0x1800166da  push    rbx
0x1800166db  push    rsi
0x1800166dc  push    rdi
0x1800166dd  push    r12
0x1800166df  push    r14
0x1800166e1  push    r15
0x1800166e3  lea     rbp, [rsp-1Fh]
0x1800166e8  sub     rsp, 0C0h
0x1800166ef  mov     rax, cs:__security_cookie
0x1800166f6  xor     rax, rsp
0x1800166f9  mov     [rbp+4Fh+var_40], rax
0x1800166fd  mov     rsi, r8
0x180016700  mov     r15, rdx
0x180016703  mov     r14, rcx
0x180016706  mov     rax, [rbp+4Fh+arg_20]
0x18001670a  mov     [rbp+4Fh+var_70], rax
0x18001670e  movaps  xmm0, xmmword ptr [rdx]
0x180016711  movdqa  xmmword ptr [rbp+4Fh+bstrString], xmm0
0x180016716  mov     byte ptr [rsp+0F0h+var_C8], 37h ; '7'
0x18001671b  lea     rax, Src
0x180016722  mov     [rsp+0F0h+var_D0], rax
0x180016727  xor     r9d, r9d
0x18001672a  lea     r8d, [r9+4]
0x18001672e  lea     rdx, [rbp+4Fh+bstrString]
0x180016732  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x180016737  mov     edi, eax
0x180016739  xor     r12d, r12d
0x18001673c  test    eax, eax
0x18001673e  js      loc_180016A09
0x180016744  mov     [rbp+4Fh+bstrString], r12
0x180016748  mov     [rbp+4Fh+var_90], r12d
0x18001674c  mov     [rbp+4Fh+var_8C], r12d
0x180016750  lea     rcx, ?s_PlatformFuncHelper@@3VPlatformFuncHelper@@A; this
0x180016757  call    ?CheckAndInit@PlatformFuncHelper@@AEAAJXZ; PlatformFuncHelper::CheckAndInit(void)
0x18001675c  lea     ebx, [r12+1]
0x180016761  test    eax, eax
0x180016763  js      short loc_1800167AF
0x180016765  mov     rax, cs:qword_180096CB0
0x18001676c  test    rax, rax
0x18001676f  jz      short loc_180016780
0x180016771  lea     rdx, [rbp+4Fh+var_90]
0x180016775  mov     ecx, ebx
0x180016777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001677c  test    eax, eax
0x18001677e  js      short loc_1800167AF
0x180016780  cmp     [rbp+4Fh+var_90], ebx
0x180016783  jb      short loc_1800167AF
0x180016785  call    ?CheckAndInit@WpCoreUtilHelper@@AEAAJXZ; WpCoreUtilHelper::CheckAndInit(void)
0x18001678a  test    eax, eax
0x18001678c  js      short loc_1800167AF
0x18001678e  cmp     cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A, r12; WpCoreUtilHelper s_WpCoreUtilHelper
0x180016795  jz      short loc_1800167AF
0x180016797  lea     r9, [rbp+4Fh+var_8C]
0x18001679b  xor     edx, edx
0x18001679d  lea     r8d, [rdx+2]
0x1800167a1  mov     ecx, ebx
0x1800167a3  mov     rax, cs:qword_180096D18
0x1800167aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167af  movaps  xmm0, xmmword ptr [rsi]
0x1800167b2  movdqa  xmmword ptr [rbp+4Fh+hstringHeader.Reserved], xmm0
0x1800167b7  lea     rdx, [rbp+4Fh+bstrString]; unsigned __int16 **
0x1800167bb  lea     rcx, [rbp+4Fh+hstringHeader]; rguid
0x1800167bf  call    ?ConvertGuidToBstr@@YAJU_GUID@@PEAPEAG@Z; ConvertGuidToBstr(_GUID,ushort * *)
0x1800167c4  mov     edi, eax
0x1800167c6  test    eax, eax
0x1800167c8  jns     short loc_1800167D3
0x1800167ca  mov     rcx, [rbp+4Fh+bstrString]
0x1800167ce  jmp     loc_1800169FD
0x1800167d3  mov     [rbp+4Fh+var_98], r12
0x1800167d7  mov     [rbp+4Fh+var_A0], r12
0x1800167db  lea     r9, [rbp+4Fh+hstringHeader]; string
0x1800167df  lea     r8, [rbp+4Fh+hstringHeader.Reserved+8]; hstringHeader
0x1800167e3  mov     edx, 16h; length
0x1800167e8  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800167ef  call    cs:__imp_WindowsCreateStringReference
0x1800167f6  nop     dword ptr [rax+rax+00h]
0x1800167fb  test    eax, eax
0x1800167fd  jns     short loc_180016818
0x1800167ff  xor     r9d, r9d; lpArguments
0x180016802  xor     r8d, r8d; nNumberOfArguments
0x180016805  mov     edx, ebx; dwExceptionFlags
0x180016807  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001680c  call    cs:__imp_RaiseException
0x180016813  nop     dword ptr [rax+rax+00h]
0x180016818  mov     rbx, qword ptr [rbp+4Fh+hstringHeader.Reserved]
0x18001681c  mov     rcx, [rbp+4Fh+var_A0]
0x180016820  test    rcx, rcx
0x180016823  jz      short loc_180016836
0x180016825  mov     [rbp+4Fh+var_A0], r12
0x180016829  mov     rax, [rcx]
0x18001682c  mov     rax, [rax+10h]
0x180016830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016835  nop
0x180016836  lea     r8, [rbp+4Fh+var_A0]
0x18001683a  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x180016841  mov     rcx, rbx
0x180016844  call    cs:__imp_RoGetActivationFactory
0x18001684b  nop     dword ptr [rax+rax+00h]
0x180016850  mov     edi, eax
0x180016852  test    eax, eax
0x180016854  jns     short loc_18001688F
0x180016856  mov     rcx, [rbp+4Fh+var_A0]
0x18001685a  test    rcx, rcx
0x18001685d  jz      short loc_180016870
0x18001685f  mov     [rbp+4Fh+var_A0], r12
0x180016863  mov     rax, [rcx]
0x180016866  mov     rax, [rax+10h]
0x18001686a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001686f  nop
0x180016870  mov     rcx, [rbp+4Fh+var_98]
0x180016874  test    rcx, rcx
0x180016877  jz      short loc_18001688A
0x180016879  mov     [rbp+4Fh+var_98], r12
0x18001687d  mov     rax, [rcx]
0x180016880  mov     rax, [rax+10h]
0x180016884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016889  nop
0x18001688a  jmp     loc_1800167CA
0x18001688f  mov     rbx, [rbp+4Fh+var_A0]
0x180016893  mov     rax, [rbx]
0x180016896  mov     rdi, [rax+30h]
0x18001689a  mov     rcx, [rbp+4Fh+var_98]
0x18001689e  test    rcx, rcx
0x1800168a1  jz      short loc_1800168B4
0x1800168a3  mov     [rbp+4Fh+var_98], r12
0x1800168a7  mov     rax, [rcx]
0x1800168aa  mov     rax, [rax+10h]
0x1800168ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168b3  nop
0x1800168b4  lea     rdx, [rbp+4Fh+var_70]
0x1800168b8  lea     rcx, [rbp+4Fh+hstringHeader]
0x1800168bc  call    ??$?0PEAG@StringReference@Internal@Windows@@QEAA@AEBQEAGUdummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(ushort * const &,Windows::Internal::_StringDetail::dummy_t)
0x1800168c1  lea     r8, [rbp+4Fh+var_98]
0x1800168c5  mov     rdx, [rax]
0x1800168c8  mov     rcx, rbx
0x1800168cb  mov     rax, rdi
0x1800168ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168d3  mov     edi, eax
0x1800168d5  test    eax, eax
0x1800168d7  jns     short loc_180016912
0x1800168d9  mov     rcx, [rbp+4Fh+var_A0]
0x1800168dd  test    rcx, rcx
0x1800168e0  jz      short loc_1800168F3
0x1800168e2  mov     [rbp+4Fh+var_A0], r12
0x1800168e6  mov     rax, [rcx]
0x1800168e9  mov     rax, [rax+10h]
0x1800168ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168f2  nop
0x1800168f3  mov     rcx, [rbp+4Fh+var_98]
0x1800168f7  test    rcx, rcx
0x1800168fa  jz      short loc_18001690D
0x1800168fc  mov     [rbp+4Fh+var_98], r12
0x180016900  mov     rax, [rcx]
0x180016903  mov     rax, [rax+10h]
0x180016907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001690c  nop
0x18001690d  jmp     loc_1800167CA
0x180016912  call    ?get@?$_LazyImpl@VPackageManagerWrapper@@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@V?$static_lazy@VPackageManagerWrapper@@$0A@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@@3@@tlx@@QEAAAEAVPackageManagerWrapper@@XZ; tlx::_LazyImpl<PackageManagerWrapper,tlx::lazy_construct<PackageManagerWrapper>,tlx::static_lazy<PackageManagerWrapper,0,tlx::lazy_construct<PackageManagerWrapper>>>::get(void)
0x180016917  mov     [rsp+0F0h+var_A8], r12
0x18001691c  mov     [rsp+0F0h+var_B0], r12
0x180016921  mov     [rsp+0F0h+var_B8], r12b
0x180016926  mov     [rsp+0F0h+var_C0], r12b
0x18001692b  mov     dword ptr [rsp+0F0h+var_C8], 40h ; '@'
0x180016933  mov     [rsp+0F0h+var_D0], r12
0x180016938  mov     r9, [rbp+4Fh+var_98]
0x18001693c  xor     r8d, r8d
0x18001693f  mov     rbx, [rbp+4Fh+bstrString]
0x180016943  mov     rdx, rbx
0x180016946  mov     rcx, rax
0x180016949  call    ?AddPackage@PackageManagerWrapper@@QEAAJPEBG0PEAUIUriRuntimeClass@Foundation@Windows@@PEAV?$Vector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@U?$DefaultVectorOptions@PEAVUri@Foundation@Windows@@@5623@@Internal@Collections@34@W4DeploymentOptionsInternal@6Deployment@Management@4@_N4PEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@6734@2@Z; PackageManagerWrapper::AddPackage(ushort const *,ushort const *,Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *,Windows::Management::Deployment::Internal::DeploymentOptionsInternal,bool,bool,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *)
0x18001694e  mov     edi, eax
0x180016950  lea     rdx, [rbp+4Fh+hstringHeader]
0x180016954  test    eax, eax
0x180016956  jns     loc_180016A2A
0x18001695c  movaps  xmm0, xmmword ptr [r15]
0x180016960  movdqa  xmmword ptr [rbp+4Fh+hstringHeader.Reserved], xmm0
0x180016965  mov     byte ptr [rsp+0F0h+var_C8], 64h ; 'd'
0x18001696a  lea     rax, aPacmanBeginent; "PacMan BeginEnterpriseAppInstall Failed"
0x180016971  mov     [rsp+0F0h+var_D0], rax
0x180016976  mov     r9d, edi
0x180016979  mov     r8d, 6
0x18001697f  mov     rcx, r14
0x180016982  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x180016987  mov     edi, eax
0x180016989  test    eax, eax
0x18001698b  jns     short loc_1800169C3
0x18001698d  mov     rcx, [rbp+4Fh+var_A0]
0x180016991  test    rcx, rcx
0x180016994  jz      short loc_1800169A7
0x180016996  mov     [rbp+4Fh+var_A0], r12
0x18001699a  mov     rax, [rcx]
0x18001699d  mov     rax, [rax+10h]
0x1800169a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169a6  nop
0x1800169a7  mov     rcx, [rbp+4Fh+var_98]
0x1800169ab  test    rcx, rcx
0x1800169ae  jz      short loc_1800169C1
0x1800169b0  mov     [rbp+4Fh+var_98], r12
0x1800169b4  mov     rax, [rcx]
0x1800169b7  mov     rax, [rax+10h]
0x1800169bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169c0  nop
0x1800169c1  jmp     short loc_1800169FA
0x1800169c3  mov     edi, r12d
0x1800169c6  mov     rcx, [rbp+4Fh+var_A0]
0x1800169ca  test    rcx, rcx
0x1800169cd  jz      short loc_1800169E0
0x1800169cf  mov     [rbp+4Fh+var_A0], r12
0x1800169d3  mov     rax, [rcx]
0x1800169d6  mov     rax, [rax+10h]
0x1800169da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169df  nop
0x1800169e0  mov     rcx, [rbp+4Fh+var_98]
0x1800169e4  test    rcx, rcx
0x1800169e7  jz      short loc_1800169FA
0x1800169e9  mov     [rbp+4Fh+var_98], r12
0x1800169ed  mov     rax, [rcx]
0x1800169f0  mov     rax, [rax+10h]
0x1800169f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169f9  nop
0x1800169fa  mov     rcx, rbx; bstrString
0x1800169fd  call    cs:__imp_SysFreeString
0x180016a04  nop     dword ptr [rax+rax+00h]
0x180016a09  mov     eax, edi
0x180016a0b  mov     rcx, [rbp+4Fh+var_40]
0x180016a0f  xor     rcx, rsp; StackCookie
0x180016a12  call    __security_check_cookie
0x180016a17  add     rsp, 0C0h
0x180016a1e  pop     r15
0x180016a20  pop     r14
0x180016a22  pop     r12
0x180016a24  pop     rdi
0x180016a25  pop     rsi
0x180016a26  pop     rbx
0x180016a27  pop     rbp
0x180016a28  retn
0x180016a2a  lea     rcx, [r14+110h]
0x180016a31  mov     r8, rsi
0x180016a34  call    ?insert@?$_Tree@U_GUID@@U1@U?$memory_compare_less@U_GUID@@@@V?$allocator@U_GUID@@@utl@@$0A@@utl@@QEAA?AU?$pair@V?$_TreeConstIt@U_GUID@@@utl@@_N@2@AEBU_GUID@@@Z; utl::_Tree<_GUID,_GUID,memory_compare_less<_GUID>,utl::allocator<_GUID>,0>::insert(_GUID const &)
0x180016a39  cmp     [rax], r12
0x180016a3c  jnz     short loc_1800169C6
0x180016a3e  mov     edi, 8007000Eh
0x180016a43  mov     rcx, [rbp+4Fh+var_A0]
0x180016a47  test    rcx, rcx
0x180016a4a  jz      short loc_180016A5D
0x180016a4c  mov     [rbp+4Fh+var_A0], r12
0x180016a50  mov     rax, [rcx]
0x180016a53  mov     rax, [rax+10h]
0x180016a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a5c  nop
0x180016a5d  mov     rcx, [rbp+4Fh+var_98]
0x180016a61  test    rcx, rcx
0x180016a64  jz      short loc_180016A77
0x180016a66  mov     [rbp+4Fh+var_98], r12
0x180016a6a  mov     rax, [rcx]
0x180016a6d  mov     rax, [rax+10h]
0x180016a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a76  nop
0x180016a77  jmp     short loc_1800169FA
```
