# EnterpriseWorkerThread::InstallPreLoadedApp(_GUID)

- ea: `0x180015d78`
- end: `0x180016281`
- name: `?InstallPreLoadedApp@EnterpriseWorkerThread@@AEAAJU_GUID@@@Z`
- size: `1289`
- prototype: `__int64 __fastcall(EnterpriseWorkerThread *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016aa8`

## callees

- `0x180011f54`
- `0x180015d78`
- `0x180018518`
- `0x180018f48`
- `0x18001b210`
- `0x18001b2bc`
- `0x18001b4bc`
- `0x18001e394`
- `0x180029f88`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180015e38`
- `OLEAUT32!__imp_SysFreeString` at `0x180015ea6`
- `OLEAUT32!__imp_SysFreeString` at `0x180015efd`
- `OLEAUT32!__imp_SysFreeString` at `0x180015fa7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001606f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800160e6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800161a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800161fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180016241`
- `OLEAUT32!__imp_SysFreeString` at `0x180015e38`
- `OLEAUT32!__imp_SysFreeString` at `0x180015ea6`
- `OLEAUT32!__imp_SysFreeString` at `0x180015efd`
- `OLEAUT32!__imp_SysFreeString` at `0x180015fa7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001606f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800160e6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800161a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800161fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180016241`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015f65`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016039`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015f65`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016039`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015f97`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015f97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015f4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001604c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015f4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001604c`

## string_xrefs

- `0x180015f47`: `Windows.Foundation.Uri`
- `0x180016177`: `InstallPreLoadedApp Failed`
- `0x180015e81`: `PacMan BeginInstall Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseWorkerThread::InstallPreLoadedApp(EnterpriseWorkerThread *this, struct _GUID *a2)
{
  int ActivationFactory; // edi
  __int64 v5; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, PVOID, __int64 *); // r15
  __int64 v11; // rcx
  const WCHAR *v12; // rdi
  unsigned __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  PackageManagerWrapper *v20; // rax
  OLECHAR *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // [rsp+28h] [rbp-71h]
  __int64 v29; // [rsp+50h] [rbp-49h] BYREF
  __int64 v30; // [rsp+58h] [rbp-41h] BYREF
  BSTR bstrString[2]; // [rsp+60h] [rbp-39h] BYREF
  int v32; // [rsp+70h] [rbp-29h] BYREF
  BSTR v33; // [rsp+78h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-19h] BYREF
  __int128 v35; // [rsp+A0h] [rbp+7h] BYREF

  v33 = 0;
  v35 = 0;
  *(struct _GUID *)bstrString = *a2;
  ActivationFactory = EnrollmentManager::RetrieveGUID(1u, (__int64)bstrString, 13, &v35);
  if ( ActivationFactory < 0 )
    goto LABEL_5;
  *(struct _GUID *)bstrString = *a2;
  ActivationFactory = EnrollmentManager::RetrieveBSTR(1, bstrString, 6, &v33);
  if ( ActivationFactory < 0 )
    goto LABEL_5;
  v30 = 0;
  v29 = 0;
  bstrString[0] = 0;
  v32 = 0;
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = v35;
  ActivationFactory = ConvertGuidToBstr((GUID *)&hstringHeader, bstrString);
  if ( ActivationFactory < 0
    || (*(struct _GUID *)&hstringHeader.Reserved.Reserved1 = *a2,
        ActivationFactory = EnrollmentManager::RetrieveByte(v5, &hstringHeader, 22, &v32),
        ActivationFactory < 0) )
  {
    SysFreeString(bstrString[0]);
LABEL_5:
    *(struct _GUID *)&hstringHeader.Reserved.Reserved1 = *a2;
    EnterpriseWorkerThread::UpdateXAPRequestStatus(this, &hstringHeader, 6);
    goto LABEL_6;
  }
  if ( WindowsCreateStringReference(
         L"Windows.Foundation.Uri",
         0x16u,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(
                        hstringHeader.Reserved.Reserved1,
                        &GUID_44a9796f_723e_4fdf_a218_033e75b0c084,
                        &v29);
  if ( ActivationFactory < 0 )
  {
    SysFreeString(bstrString[0]);
    v7 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    v8 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    goto LABEL_5;
  }
  v9 = v29;
  v10 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v29 + 48LL);
  v11 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = v33;
  v13 = -1;
  do
    ++v13;
  while ( v33[v13] );
  if ( v13 > 0xFFFFFFFF )
  {
    LODWORD(v13) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(
    v12,
    v13,
    (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
    (HSTRING *)&hstringHeader);
  ActivationFactory = v10(v9, hstringHeader.Reserved.Reserved1, &v30);
  if ( ActivationFactory < 0 )
  {
    SysFreeString(bstrString[0]);
    v14 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    goto LABEL_5;
  }
  *(struct _GUID *)&hstringHeader.Reserved.Reserved1 = *a2;
  ActivationFactory = EnterpriseWorkerThread::UpdateXAPRequestStatus(this, &hstringHeader, 4);
  if ( ActivationFactory < 0 )
  {
    SysFreeString(bstrString[0]);
    v18 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    goto LABEL_5;
  }
  v20 = (PackageManagerWrapper *)tlx::_LazyImpl<PackageManagerWrapper,tlx::lazy_construct<PackageManagerWrapper>,tlx::static_lazy<PackageManagerWrapper,0,tlx::lazy_construct<PackageManagerWrapper>>>::get(
                                   v17,
                                   v16);
  LODWORD(v28) = 0;
  v21 = bstrString[0];
  ActivationFactory = PackageManagerWrapper::AddPackage(v20, bstrString[0], 0, v30, 0, v28, 0);
  if ( ActivationFactory >= 0 )
  {
    if ( !*(_QWORD *)utl::_Tree<_GUID,_GUID,memory_compare_less<_GUID>,utl::allocator<_GUID>,0>::insert(
                       (char *)this + 272,
                       &hstringHeader,
                       &v35) )
    {
      ActivationFactory = -2147024882;
      SysFreeString(v21);
      v24 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      v25 = v30;
      if ( v30 )
      {
        v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      goto LABEL_5;
    }
  }
  else
  {
    *(struct _GUID *)&hstringHeader.Reserved.Reserved1 = *a2;
    ActivationFactory = EnterpriseWorkerThread::UpdateXAPRequestStatus(this, &hstringHeader, 6);
    if ( ActivationFactory < 0 )
    {
      SysFreeString(v21);
      v22 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v23 = v30;
      if ( v30 )
      {
        v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      goto LABEL_5;
    }
  }
  SysFreeString(v21);
  v26 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
LABEL_6:
  SysFreeString(v33);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180015d78  mov     [rsp-8+arg_10], rbx
0x180015d7d  push    rbp
0x180015d7e  push    rsi
0x180015d7f  push    rdi
0x180015d80  push    r12
0x180015d82  push    r13
0x180015d84  push    r14
0x180015d86  push    r15
0x180015d88  lea     rbp, [rsp-27h]
0x180015d8d  sub     rsp, 0C0h
0x180015d94  mov     rax, cs:__security_cookie
0x180015d9b  xor     rax, rsp
0x180015d9e  mov     [rbp+57h+var_40], rax
0x180015da2  mov     r14, rdx
0x180015da5  mov     r13, rcx
0x180015da8  xor     r12d, r12d
0x180015dab  mov     [rbp+57h+var_78], r12
0x180015daf  xorps   xmm0, xmm0
0x180015db2  movups  [rbp+57h+var_50], xmm0
0x180015db6  movaps  xmm1, xmmword ptr [rdx]
0x180015db9  movdqa  xmmword ptr [rbp+57h+bstrString], xmm1
0x180015dbe  lea     r8d, [r12+0Dh]
0x180015dc3  lea     r9, [rbp+57h+var_50]
0x180015dc7  lea     rdx, [rbp+57h+bstrString]
0x180015dcb  lea     esi, [r12+1]
0x180015dd0  mov     ecx, esi
0x180015dd2  call    ?RetrieveGUID@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAU3@@Z; EnrollmentManager::RetrieveGUID(TABLEID,_GUID,ushort,_GUID *)
0x180015dd7  mov     edi, eax
0x180015dd9  test    eax, eax
0x180015ddb  js      loc_180015E73
0x180015de1  movaps  xmm0, xmmword ptr [r14]
0x180015de5  movdqa  xmmword ptr [rbp+57h+bstrString], xmm0
0x180015dea  lea     r8d, [r12+6]
0x180015def  lea     r9, [rbp+57h+var_78]
0x180015df3  lea     rdx, [rbp+57h+bstrString]
0x180015df7  mov     ecx, esi
0x180015df9  call    ?RetrieveBSTR@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAPEAG@Z; EnrollmentManager::RetrieveBSTR(TABLEID,_GUID,ushort,ushort * *)
0x180015dfe  mov     edi, eax
0x180015e00  test    eax, eax
0x180015e02  js      short loc_180015E73
0x180015e04  mov     [rbp+57h+var_98], r12
0x180015e08  mov     [rbp+57h+var_A0], r12
0x180015e0c  mov     [rbp+57h+bstrString], r12
0x180015e10  mov     [rbp+57h+var_80], r12d
0x180015e14  movaps  xmm0, [rbp+57h+var_50]
0x180015e18  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180015e1d  lea     rdx, [rbp+57h+bstrString]; unsigned __int16 **
0x180015e21  lea     rcx, [rbp+57h+hstringHeader]; rguid
0x180015e25  call    ?ConvertGuidToBstr@@YAJU_GUID@@PEAPEAG@Z; ConvertGuidToBstr(_GUID,ushort * *)
0x180015e2a  mov     edi, eax
0x180015e2c  test    eax, eax
0x180015e2e  jns     loc_180015ED5
0x180015e34  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180015e38  call    cs:__imp_SysFreeString
0x180015e3e  nop
0x180015e3f  mov     rcx, [rbp+57h+var_A0]
0x180015e43  test    rcx, rcx
0x180015e46  jz      short loc_180015E59
0x180015e48  mov     [rbp+57h+var_A0], r12
0x180015e4c  mov     rax, [rcx]
0x180015e4f  mov     rax, [rax+10h]
0x180015e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e58  nop
0x180015e59  mov     rcx, [rbp+57h+var_98]
0x180015e5d  test    rcx, rcx
0x180015e60  jz      short loc_180015E73
0x180015e62  mov     [rbp+57h+var_98], r12
0x180015e66  mov     rax, [rcx]
0x180015e69  mov     rax, [rax+10h]
0x180015e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e72  nop
0x180015e73  movaps  xmm0, xmmword ptr [r14]
0x180015e77  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180015e7c  mov     byte ptr [rsp+0F0h+var_C8], 64h ; 'd'
0x180015e81  lea     rax, aPacmanBeginins; "PacMan BeginInstall Failed"
0x180015e88  mov     [rsp+0F0h+var_D0], rax
0x180015e8d  mov     r9d, edi
0x180015e90  mov     r8d, 6
0x180015e96  lea     rdx, [rbp+57h+hstringHeader]
0x180015e9a  mov     rcx, r13
0x180015e9d  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x180015ea2  mov     rcx, [rbp+57h+var_78]; bstrString
0x180015ea6  call    cs:__imp_SysFreeString
0x180015eac  mov     eax, edi
0x180015eae  mov     rcx, [rbp+57h+var_40]
0x180015eb2  xor     rcx, rsp; StackCookie
0x180015eb5  call    __security_check_cookie
0x180015eba  mov     rbx, [rsp+0F0h+arg_10]
0x180015ec2  add     rsp, 0C0h
0x180015ec9  pop     r15
0x180015ecb  pop     r14
0x180015ecd  pop     r13
0x180015ecf  pop     r12
0x180015ed1  pop     rdi
0x180015ed2  pop     rsi
0x180015ed3  pop     rbp
0x180015ed4  retn
0x180015ed5  movaps  xmm0, xmmword ptr [r14]
0x180015ed9  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180015ede  mov     ebx, 16h
0x180015ee3  mov     r8d, ebx
0x180015ee6  lea     r9, [rbp+57h+var_80]
0x180015eea  lea     rdx, [rbp+57h+hstringHeader]
0x180015eee  call    ?RetrieveByte@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAE@Z; EnrollmentManager::RetrieveByte(TABLEID,_GUID,ushort,uchar *)
0x180015ef3  mov     edi, eax
0x180015ef5  test    eax, eax
0x180015ef7  jns     short loc_180015F3D
0x180015ef9  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180015efd  call    cs:__imp_SysFreeString
0x180015f03  nop
0x180015f04  mov     rcx, [rbp+57h+var_A0]
0x180015f08  test    rcx, rcx
0x180015f0b  jz      short loc_180015F1E
0x180015f0d  mov     [rbp+57h+var_A0], r12
0x180015f11  mov     rax, [rcx]
0x180015f14  mov     rax, [rax+10h]
0x180015f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f1d  nop
0x180015f1e  mov     rcx, [rbp+57h+var_98]
0x180015f22  test    rcx, rcx
0x180015f25  jz      short loc_180015F38
0x180015f27  mov     [rbp+57h+var_98], r12
0x180015f2b  mov     rax, [rcx]
0x180015f2e  mov     rax, [rax+10h]
0x180015f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f37  nop
0x180015f38  jmp     loc_180015E73
0x180015f3d  lea     r9, [rbp+57h+hstringHeader]; string
0x180015f41  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x180015f45  mov     edx, ebx; length
0x180015f47  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180015f4e  call    cs:__imp_WindowsCreateStringReference
0x180015f54  test    eax, eax
0x180015f56  jns     short loc_180015F6B
0x180015f58  xor     r9d, r9d; lpArguments
0x180015f5b  xor     r8d, r8d; nNumberOfArguments
0x180015f5e  mov     edx, esi; dwExceptionFlags
0x180015f60  mov     ecx, 0C000000Dh; dwExceptionCode
0x180015f65  call    cs:__imp_RaiseException
0x180015f6b  mov     rbx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180015f6f  mov     rcx, [rbp+57h+var_A0]
0x180015f73  test    rcx, rcx
0x180015f76  jz      short loc_180015F89
0x180015f78  mov     [rbp+57h+var_A0], r12
0x180015f7c  mov     rax, [rcx]
0x180015f7f  mov     rax, [rax+10h]
0x180015f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f88  nop
0x180015f89  lea     r8, [rbp+57h+var_A0]
0x180015f8d  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x180015f94  mov     rcx, rbx
0x180015f97  call    cs:__imp_RoGetActivationFactory
0x180015f9d  mov     edi, eax
0x180015f9f  test    eax, eax
0x180015fa1  jns     short loc_180015FE7
0x180015fa3  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180015fa7  call    cs:__imp_SysFreeString
0x180015fad  nop
0x180015fae  mov     rcx, [rbp+57h+var_A0]
0x180015fb2  test    rcx, rcx
0x180015fb5  jz      short loc_180015FC8
0x180015fb7  mov     [rbp+57h+var_A0], r12
0x180015fbb  mov     rax, [rcx]
0x180015fbe  mov     rax, [rax+10h]
0x180015fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fc7  nop
0x180015fc8  mov     rcx, [rbp+57h+var_98]
0x180015fcc  test    rcx, rcx
0x180015fcf  jz      short loc_180015FE2
0x180015fd1  mov     [rbp+57h+var_98], r12
0x180015fd5  mov     rax, [rcx]
0x180015fd8  mov     rax, [rax+10h]
0x180015fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fe1  nop
0x180015fe2  jmp     loc_180015E73
0x180015fe7  mov     rsi, [rbp+57h+var_A0]
0x180015feb  mov     rax, [rsi]
0x180015fee  mov     r15, [rax+30h]
0x180015ff2  mov     rcx, [rbp+57h+var_98]
0x180015ff6  test    rcx, rcx
0x180015ff9  jz      short loc_18001600C
0x180015ffb  mov     [rbp+57h+var_98], r12
0x180015fff  mov     rax, [rcx]
0x180016002  mov     rax, [rax+10h]
0x180016006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001600b  nop
0x18001600c  mov     rdi, [rbp+57h+var_78]
0x180016010  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016014  inc     rbx
0x180016017  cmp     [rdi+rbx*2], r12w
0x18001601c  jnz     short loc_180016014
0x18001601e  mov     eax, 0FFFFFFFFh
0x180016023  cmp     rbx, rax
0x180016026  jbe     short loc_18001603F
0x180016028  mov     ebx, eax
0x18001602a  xor     r9d, r9d; lpArguments
0x18001602d  xor     r8d, r8d; nNumberOfArguments
0x180016030  lea     edx, [r9+1]; dwExceptionFlags
0x180016034  mov     ecx, 0C000000Dh; dwExceptionCode
0x180016039  call    cs:__imp_RaiseException
0x18001603f  lea     r9, [rbp+57h+hstringHeader]; string
0x180016043  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x180016047  mov     edx, ebx; length
0x180016049  mov     rcx, rdi; sourceString
0x18001604c  call    cs:__imp_WindowsCreateStringReference
0x180016052  lea     r8, [rbp+57h+var_98]
0x180016056  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x18001605a  mov     rcx, rsi
0x18001605d  mov     rax, r15
0x180016060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016065  mov     edi, eax
0x180016067  test    eax, eax
0x180016069  jns     short loc_1800160AF
0x18001606b  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18001606f  call    cs:__imp_SysFreeString
0x180016075  nop
0x180016076  mov     rcx, [rbp+57h+var_A0]
0x18001607a  test    rcx, rcx
0x18001607d  jz      short loc_180016090
0x18001607f  mov     [rbp+57h+var_A0], r12
0x180016083  mov     rax, [rcx]
0x180016086  mov     rax, [rax+10h]
0x18001608a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001608f  nop
0x180016090  mov     rcx, [rbp+57h+var_98]
0x180016094  test    rcx, rcx
0x180016097  jz      short loc_1800160AA
0x180016099  mov     [rbp+57h+var_98], r12
0x18001609d  mov     rax, [rcx]
0x1800160a0  mov     rax, [rax+10h]
0x1800160a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160a9  nop
0x1800160aa  jmp     loc_180015E73
0x1800160af  movaps  xmm0, xmmword ptr [r14]
0x1800160b3  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x1800160b8  mov     byte ptr [rsp+0F0h+var_C8], 37h ; '7'
0x1800160bd  lea     rax, Src
0x1800160c4  mov     [rsp+0F0h+var_D0], rax
0x1800160c9  xor     r9d, r9d
0x1800160cc  lea     r8d, [r9+4]
0x1800160d0  lea     rdx, [rbp+57h+hstringHeader]
0x1800160d4  mov     rcx, r13
0x1800160d7  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x1800160dc  mov     edi, eax
0x1800160de  test    eax, eax
0x1800160e0  jns     short loc_180016126
0x1800160e2  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800160e6  call    cs:__imp_SysFreeString
0x1800160ec  nop
0x1800160ed  mov     rcx, [rbp+57h+var_A0]
0x1800160f1  test    rcx, rcx
0x1800160f4  jz      short loc_180016107
0x1800160f6  mov     [rbp+57h+var_A0], r12
0x1800160fa  mov     rax, [rcx]
0x1800160fd  mov     rax, [rax+10h]
0x180016101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016106  nop
0x180016107  mov     rcx, [rbp+57h+var_98]
0x18001610b  test    rcx, rcx
0x18001610e  jz      short loc_180016121
0x180016110  mov     [rbp+57h+var_98], r12
0x180016114  mov     rax, [rcx]
0x180016117  mov     rax, [rax+10h]
0x18001611b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016120  nop
0x180016121  jmp     loc_180015E73
0x180016126  call    ?get@?$_LazyImpl@VPackageManagerWrapper@@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@V?$static_lazy@VPackageManagerWrapper@@$0A@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@@3@@tlx@@QEAAAEAVPackageManagerWrapper@@XZ; tlx::_LazyImpl<PackageManagerWrapper,tlx::lazy_construct<PackageManagerWrapper>,tlx::static_lazy<PackageManagerWrapper,0,tlx::lazy_construct<PackageManagerWrapper>>>::get(void)
0x18001612b  mov     [rsp+0F0h+var_A8], r12
0x180016130  mov     [rsp+0F0h+var_B0], r12
0x180016135  mov     [rsp+0F0h+var_B8], r12b
0x18001613a  mov     [rsp+0F0h+var_C0], r12b
0x18001613f  mov     dword ptr [rsp+0F0h+var_C8], r12d
0x180016144  mov     [rsp+0F0h+var_D0], r12
0x180016149  mov     r9, [rbp+57h+var_98]
0x18001614d  xor     r8d, r8d
0x180016150  mov     rbx, [rbp+57h+bstrString]
0x180016154  mov     rdx, rbx
0x180016157  mov     rcx, rax
0x18001615a  call    ?AddPackage@PackageManagerWrapper@@QEAAJPEBG0PEAUIUriRuntimeClass@Foundation@Windows@@PEAV?$Vector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@U?$DefaultVectorOptions@PEAVUri@Foundation@Windows@@@5623@@Internal@Collections@34@W4DeploymentOptionsInternal@6Deployment@Management@4@_N4PEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@6734@2@Z; PackageManagerWrapper::AddPackage(ushort const *,ushort const *,Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *,Windows::Management::Deployment::Internal::DeploymentOptionsInternal,bool,bool,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *)
0x18001615f  mov     edi, eax
0x180016161  lea     rdx, [rbp+57h+hstringHeader]
0x180016165  test    eax, eax
0x180016167  jns     short loc_1800161E1
0x180016169  movaps  xmm0, xmmword ptr [r14]
0x18001616d  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180016172  mov     byte ptr [rsp+0F0h+var_C8], 64h ; 'd'
0x180016177  lea     rax, aInstallpreload; "InstallPreLoadedApp Failed"
0x18001617e  mov     [rsp+0F0h+var_D0], rax
0x180016183  mov     r9d, edi
0x180016186  mov     r8d, 6
0x18001618c  mov     rcx, r13
0x18001618f  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x180016194  mov     edi, eax
0x180016196  test    eax, eax
0x180016198  jns     loc_18001623E
0x18001619e  mov     rcx, rbx; bstrString
0x1800161a1  call    cs:__imp_SysFreeString
0x1800161a7  nop
0x1800161a8  mov     rcx, [rbp+57h+var_A0]
0x1800161ac  test    rcx, rcx
  ... truncated ...
```
