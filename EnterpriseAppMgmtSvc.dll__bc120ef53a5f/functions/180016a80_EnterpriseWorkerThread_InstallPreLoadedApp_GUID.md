# EnterpriseWorkerThread::InstallPreLoadedApp(_GUID)

- ea: `0x180016a80`
- end: `0x180016fde`
- name: `?InstallPreLoadedApp@EnterpriseWorkerThread@@AEAAJU_GUID@@@Z`
- size: `1374`
- prototype: `__int64 __fastcall(EnterpriseWorkerThread *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800177d0`

## callees

- `0x1800127c8`
- `0x180016a80`
- `0x180019384`
- `0x18001a18c`
- `0x18001c550`
- `0x18001c5fc`
- `0x18001c818`
- `0x18001f908`
- `0x18002c194`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180016b40`
- `OLEAUT32!__imp_SysFreeString` at `0x180016bb4`
- `OLEAUT32!__imp_SysFreeString` at `0x180016c12`
- `OLEAUT32!__imp_SysFreeString` at `0x180016cd4`
- `OLEAUT32!__imp_SysFreeString` at `0x180016dae`
- `OLEAUT32!__imp_SysFreeString` at `0x180016e2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180016eec`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f4f`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f98`
- `OLEAUT32!__imp_SysFreeString` at `0x180016b40`
- `OLEAUT32!__imp_SysFreeString` at `0x180016bb4`
- `OLEAUT32!__imp_SysFreeString` at `0x180016c12`
- `OLEAUT32!__imp_SysFreeString` at `0x180016cd4`
- `OLEAUT32!__imp_SysFreeString` at `0x180016dae`
- `OLEAUT32!__imp_SysFreeString` at `0x180016e2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180016eec`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f4f`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f98`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016c86`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016d6c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016c86`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016d6c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180016cbe`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180016cbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016c69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016d85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016c69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016d85`

## string_xrefs

- `0x180016c62`: `Windows.Foundation.Uri`
- `0x180016ec2`: `InstallPreLoadedApp Failed`
- `0x180016b8f`: `PacMan BeginInstall Failed`

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
  ActivationFactory = EnrollmentManager::RetrieveGUID(1, bstrString, 13, &v35);
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
0x180016a80  mov     [rsp-8+arg_10], rbx
0x180016a85  push    rbp
0x180016a86  push    rsi
0x180016a87  push    rdi
0x180016a88  push    r12
0x180016a8a  push    r13
0x180016a8c  push    r14
0x180016a8e  push    r15
0x180016a90  lea     rbp, [rsp-27h]
0x180016a95  sub     rsp, 0C0h
0x180016a9c  mov     rax, cs:__security_cookie
0x180016aa3  xor     rax, rsp
0x180016aa6  mov     [rbp+57h+var_40], rax
0x180016aaa  mov     r14, rdx
0x180016aad  mov     r13, rcx
0x180016ab0  xor     r12d, r12d
0x180016ab3  mov     [rbp+57h+var_78], r12
0x180016ab7  xorps   xmm0, xmm0
0x180016aba  movups  [rbp+57h+var_50], xmm0
0x180016abe  movaps  xmm1, xmmword ptr [rdx]
0x180016ac1  movdqa  xmmword ptr [rbp+57h+bstrString], xmm1
0x180016ac6  lea     r8d, [r12+0Dh]
0x180016acb  lea     r9, [rbp+57h+var_50]
0x180016acf  lea     rdx, [rbp+57h+bstrString]
0x180016ad3  lea     esi, [r12+1]
0x180016ad8  mov     ecx, esi
0x180016ada  call    ?RetrieveGUID@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAU3@@Z; EnrollmentManager::RetrieveGUID(TABLEID,_GUID,ushort,_GUID *)
0x180016adf  mov     edi, eax
0x180016ae1  test    eax, eax
0x180016ae3  js      loc_180016B81
0x180016ae9  movaps  xmm0, xmmword ptr [r14]
0x180016aed  movdqa  xmmword ptr [rbp+57h+bstrString], xmm0
0x180016af2  lea     r8d, [r12+6]
0x180016af7  lea     r9, [rbp+57h+var_78]
0x180016afb  lea     rdx, [rbp+57h+bstrString]
0x180016aff  mov     ecx, esi
0x180016b01  call    ?RetrieveBSTR@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAPEAG@Z; EnrollmentManager::RetrieveBSTR(TABLEID,_GUID,ushort,ushort * *)
0x180016b06  mov     edi, eax
0x180016b08  test    eax, eax
0x180016b0a  js      short loc_180016B81
0x180016b0c  mov     [rbp+57h+var_98], r12
0x180016b10  mov     [rbp+57h+var_A0], r12
0x180016b14  mov     [rbp+57h+bstrString], r12
0x180016b18  mov     [rbp+57h+var_80], r12d
0x180016b1c  movaps  xmm0, [rbp+57h+var_50]
0x180016b20  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180016b25  lea     rdx, [rbp+57h+bstrString]; unsigned __int16 **
0x180016b29  lea     rcx, [rbp+57h+hstringHeader]; rguid
0x180016b2d  call    ?ConvertGuidToBstr@@YAJU_GUID@@PEAPEAG@Z; ConvertGuidToBstr(_GUID,ushort * *)
0x180016b32  mov     edi, eax
0x180016b34  test    eax, eax
0x180016b36  jns     loc_180016BEA
0x180016b3c  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180016b40  call    cs:__imp_SysFreeString
0x180016b47  nop     dword ptr [rax+rax+00h]
0x180016b4c  nop
0x180016b4d  mov     rcx, [rbp+57h+var_A0]
0x180016b51  test    rcx, rcx
0x180016b54  jz      short loc_180016B67
0x180016b56  mov     [rbp+57h+var_A0], r12
0x180016b5a  mov     rax, [rcx]
0x180016b5d  mov     rax, [rax+10h]
0x180016b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b66  nop
0x180016b67  mov     rcx, [rbp+57h+var_98]
0x180016b6b  test    rcx, rcx
0x180016b6e  jz      short loc_180016B81
0x180016b70  mov     [rbp+57h+var_98], r12
0x180016b74  mov     rax, [rcx]
0x180016b77  mov     rax, [rax+10h]
0x180016b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b80  nop
0x180016b81  movaps  xmm0, xmmword ptr [r14]
0x180016b85  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180016b8a  mov     byte ptr [rsp+0F0h+var_C8], 64h ; 'd'
0x180016b8f  lea     rax, aPacmanBeginins; "PacMan BeginInstall Failed"
0x180016b96  mov     [rsp+0F0h+var_D0], rax
0x180016b9b  mov     r9d, edi
0x180016b9e  mov     r8d, 6
0x180016ba4  lea     rdx, [rbp+57h+hstringHeader]
0x180016ba8  mov     rcx, r13
0x180016bab  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x180016bb0  mov     rcx, [rbp+57h+var_78]; bstrString
0x180016bb4  call    cs:__imp_SysFreeString
0x180016bbb  nop     dword ptr [rax+rax+00h]
0x180016bc0  mov     eax, edi
0x180016bc2  mov     rcx, [rbp+57h+var_40]
0x180016bc6  xor     rcx, rsp; StackCookie
0x180016bc9  call    __security_check_cookie
0x180016bce  mov     rbx, [rsp+0F0h+arg_10]
0x180016bd6  add     rsp, 0C0h
0x180016bdd  pop     r15
0x180016bdf  pop     r14
0x180016be1  pop     r13
0x180016be3  pop     r12
0x180016be5  pop     rdi
0x180016be6  pop     rsi
0x180016be7  pop     rbp
0x180016be8  retn
0x180016bea  movaps  xmm0, xmmword ptr [r14]
0x180016bee  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180016bf3  mov     ebx, 16h
0x180016bf8  mov     r8d, ebx
0x180016bfb  lea     r9, [rbp+57h+var_80]
0x180016bff  lea     rdx, [rbp+57h+hstringHeader]
0x180016c03  call    ?RetrieveByte@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAE@Z; EnrollmentManager::RetrieveByte(TABLEID,_GUID,ushort,uchar *)
0x180016c08  mov     edi, eax
0x180016c0a  test    eax, eax
0x180016c0c  jns     short loc_180016C58
0x180016c0e  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180016c12  call    cs:__imp_SysFreeString
0x180016c19  nop     dword ptr [rax+rax+00h]
0x180016c1e  nop
0x180016c1f  mov     rcx, [rbp+57h+var_A0]
0x180016c23  test    rcx, rcx
0x180016c26  jz      short loc_180016C39
0x180016c28  mov     [rbp+57h+var_A0], r12
0x180016c2c  mov     rax, [rcx]
0x180016c2f  mov     rax, [rax+10h]
0x180016c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c38  nop
0x180016c39  mov     rcx, [rbp+57h+var_98]
0x180016c3d  test    rcx, rcx
0x180016c40  jz      short loc_180016C53
0x180016c42  mov     [rbp+57h+var_98], r12
0x180016c46  mov     rax, [rcx]
0x180016c49  mov     rax, [rax+10h]
0x180016c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c52  nop
0x180016c53  jmp     loc_180016B81
0x180016c58  lea     r9, [rbp+57h+hstringHeader]; string
0x180016c5c  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x180016c60  mov     edx, ebx; length
0x180016c62  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180016c69  call    cs:__imp_WindowsCreateStringReference
0x180016c70  nop     dword ptr [rax+rax+00h]
0x180016c75  test    eax, eax
0x180016c77  jns     short loc_180016C92
0x180016c79  xor     r9d, r9d; lpArguments
0x180016c7c  xor     r8d, r8d; nNumberOfArguments
0x180016c7f  mov     edx, esi; dwExceptionFlags
0x180016c81  mov     ecx, 0C000000Dh; dwExceptionCode
0x180016c86  call    cs:__imp_RaiseException
0x180016c8d  nop     dword ptr [rax+rax+00h]
0x180016c92  mov     rbx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180016c96  mov     rcx, [rbp+57h+var_A0]
0x180016c9a  test    rcx, rcx
0x180016c9d  jz      short loc_180016CB0
0x180016c9f  mov     [rbp+57h+var_A0], r12
0x180016ca3  mov     rax, [rcx]
0x180016ca6  mov     rax, [rax+10h]
0x180016caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016caf  nop
0x180016cb0  lea     r8, [rbp+57h+var_A0]
0x180016cb4  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x180016cbb  mov     rcx, rbx
0x180016cbe  call    cs:__imp_RoGetActivationFactory
0x180016cc5  nop     dword ptr [rax+rax+00h]
0x180016cca  mov     edi, eax
0x180016ccc  test    eax, eax
0x180016cce  jns     short loc_180016D1A
0x180016cd0  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180016cd4  call    cs:__imp_SysFreeString
0x180016cdb  nop     dword ptr [rax+rax+00h]
0x180016ce0  nop
0x180016ce1  mov     rcx, [rbp+57h+var_A0]
0x180016ce5  test    rcx, rcx
0x180016ce8  jz      short loc_180016CFB
0x180016cea  mov     [rbp+57h+var_A0], r12
0x180016cee  mov     rax, [rcx]
0x180016cf1  mov     rax, [rax+10h]
0x180016cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cfa  nop
0x180016cfb  mov     rcx, [rbp+57h+var_98]
0x180016cff  test    rcx, rcx
0x180016d02  jz      short loc_180016D15
0x180016d04  mov     [rbp+57h+var_98], r12
0x180016d08  mov     rax, [rcx]
0x180016d0b  mov     rax, [rax+10h]
0x180016d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d14  nop
0x180016d15  jmp     loc_180016B81
0x180016d1a  mov     rsi, [rbp+57h+var_A0]
0x180016d1e  mov     rax, [rsi]
0x180016d21  mov     r15, [rax+30h]
0x180016d25  mov     rcx, [rbp+57h+var_98]
0x180016d29  test    rcx, rcx
0x180016d2c  jz      short loc_180016D3F
0x180016d2e  mov     [rbp+57h+var_98], r12
0x180016d32  mov     rax, [rcx]
0x180016d35  mov     rax, [rax+10h]
0x180016d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d3e  nop
0x180016d3f  mov     rdi, [rbp+57h+var_78]
0x180016d43  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016d47  inc     rbx
0x180016d4a  cmp     [rdi+rbx*2], r12w
0x180016d4f  jnz     short loc_180016D47
0x180016d51  mov     eax, 0FFFFFFFFh
0x180016d56  cmp     rbx, rax
0x180016d59  jbe     short loc_180016D78
0x180016d5b  mov     ebx, eax
0x180016d5d  xor     r9d, r9d; lpArguments
0x180016d60  xor     r8d, r8d; nNumberOfArguments
0x180016d63  lea     edx, [r9+1]; dwExceptionFlags
0x180016d67  mov     ecx, 0C000000Dh; dwExceptionCode
0x180016d6c  call    cs:__imp_RaiseException
0x180016d73  nop     dword ptr [rax+rax+00h]
0x180016d78  lea     r9, [rbp+57h+hstringHeader]; string
0x180016d7c  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x180016d80  mov     edx, ebx; length
0x180016d82  mov     rcx, rdi; sourceString
0x180016d85  call    cs:__imp_WindowsCreateStringReference
0x180016d8c  nop     dword ptr [rax+rax+00h]
0x180016d91  lea     r8, [rbp+57h+var_98]
0x180016d95  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180016d99  mov     rcx, rsi
0x180016d9c  mov     rax, r15
0x180016d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016da4  mov     edi, eax
0x180016da6  test    eax, eax
0x180016da8  jns     short loc_180016DF4
0x180016daa  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180016dae  call    cs:__imp_SysFreeString
0x180016db5  nop     dword ptr [rax+rax+00h]
0x180016dba  nop
0x180016dbb  mov     rcx, [rbp+57h+var_A0]
0x180016dbf  test    rcx, rcx
0x180016dc2  jz      short loc_180016DD5
0x180016dc4  mov     [rbp+57h+var_A0], r12
0x180016dc8  mov     rax, [rcx]
0x180016dcb  mov     rax, [rax+10h]
0x180016dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dd4  nop
0x180016dd5  mov     rcx, [rbp+57h+var_98]
0x180016dd9  test    rcx, rcx
0x180016ddc  jz      short loc_180016DEF
0x180016dde  mov     [rbp+57h+var_98], r12
0x180016de2  mov     rax, [rcx]
0x180016de5  mov     rax, [rax+10h]
0x180016de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dee  nop
0x180016def  jmp     loc_180016B81
0x180016df4  movaps  xmm0, xmmword ptr [r14]
0x180016df8  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180016dfd  mov     byte ptr [rsp+0F0h+var_C8], 37h ; '7'
0x180016e02  lea     rax, Src
0x180016e09  mov     [rsp+0F0h+var_D0], rax
0x180016e0e  xor     r9d, r9d
0x180016e11  lea     r8d, [r9+4]
0x180016e15  lea     rdx, [rbp+57h+hstringHeader]
0x180016e19  mov     rcx, r13
0x180016e1c  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x180016e21  mov     edi, eax
0x180016e23  test    eax, eax
0x180016e25  jns     short loc_180016E71
0x180016e27  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180016e2b  call    cs:__imp_SysFreeString
0x180016e32  nop     dword ptr [rax+rax+00h]
0x180016e37  nop
0x180016e38  mov     rcx, [rbp+57h+var_A0]
0x180016e3c  test    rcx, rcx
0x180016e3f  jz      short loc_180016E52
0x180016e41  mov     [rbp+57h+var_A0], r12
0x180016e45  mov     rax, [rcx]
0x180016e48  mov     rax, [rax+10h]
0x180016e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e51  nop
0x180016e52  mov     rcx, [rbp+57h+var_98]
0x180016e56  test    rcx, rcx
0x180016e59  jz      short loc_180016E6C
0x180016e5b  mov     [rbp+57h+var_98], r12
0x180016e5f  mov     rax, [rcx]
0x180016e62  mov     rax, [rax+10h]
0x180016e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e6b  nop
0x180016e6c  jmp     loc_180016B81
0x180016e71  call    ?get@?$_LazyImpl@VPackageManagerWrapper@@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@V?$static_lazy@VPackageManagerWrapper@@$0A@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@@3@@tlx@@QEAAAEAVPackageManagerWrapper@@XZ; tlx::_LazyImpl<PackageManagerWrapper,tlx::lazy_construct<PackageManagerWrapper>,tlx::static_lazy<PackageManagerWrapper,0,tlx::lazy_construct<PackageManagerWrapper>>>::get(void)
0x180016e76  mov     [rsp+0F0h+var_A8], r12
0x180016e7b  mov     [rsp+0F0h+var_B0], r12
0x180016e80  mov     [rsp+0F0h+var_B8], r12b
0x180016e85  mov     [rsp+0F0h+var_C0], r12b
0x180016e8a  mov     dword ptr [rsp+0F0h+var_C8], r12d
0x180016e8f  mov     [rsp+0F0h+var_D0], r12
0x180016e94  mov     r9, [rbp+57h+var_98]
0x180016e98  xor     r8d, r8d
0x180016e9b  mov     rbx, [rbp+57h+bstrString]
0x180016e9f  mov     rdx, rbx
0x180016ea2  mov     rcx, rax
0x180016ea5  call    ?AddPackage@PackageManagerWrapper@@QEAAJPEBG0PEAUIUriRuntimeClass@Foundation@Windows@@PEAV?$Vector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@U?$DefaultVectorOptions@PEAVUri@Foundation@Windows@@@5623@@Internal@Collections@34@W4DeploymentOptionsInternal@6Deployment@Management@4@_N4PEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@6734@2@Z; PackageManagerWrapper::AddPackage(ushort const *,ushort const *,Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *,Windows::Management::Deployment::Internal::DeploymentOptionsInternal,bool,bool,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *)
0x180016eaa  mov     edi, eax
0x180016eac  lea     rdx, [rbp+57h+hstringHeader]
0x180016eb0  test    eax, eax
0x180016eb2  jns     short loc_180016F32
0x180016eb4  movaps  xmm0, xmmword ptr [r14]
0x180016eb8  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180016ebd  mov     byte ptr [rsp+0F0h+var_C8], 64h ; 'd'
0x180016ec2  lea     rax, aInstallpreload; "InstallPreLoadedApp Failed"
0x180016ec9  mov     [rsp+0F0h+var_D0], rax
0x180016ece  mov     r9d, edi
  ... truncated ...
```
