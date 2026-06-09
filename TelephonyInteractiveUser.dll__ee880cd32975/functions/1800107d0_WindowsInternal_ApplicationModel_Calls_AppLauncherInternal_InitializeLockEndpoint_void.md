# WindowsInternal::ApplicationModel::Calls::AppLauncherInternal::_InitializeLockEndpoint(void)

- ea: `0x1800107d0`
- end: `0x180010985`
- name: `?_InitializeLockEndpoint@AppLauncherInternal@Calls@ApplicationModel@WindowsInternal@@MEAAJXZ`
- size: `437`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001dc0`
- `0x18000cf2c`
- `0x1800107d0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001081a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001081a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010838`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010838`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001084d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001084d`

## string_xrefs

- `0x1800107f6`: `lockframework.LockAppBroker`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::AppLauncherInternal::_InitializeLockEndpoint(
        WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *this)
{
  int ActivationFactory; // ebx
  HSTRING string; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-40h] BYREF
  __int64 v6; // [rsp+50h] [rbp-28h] BYREF
  __int64 v7; // [rsp+58h] [rbp-20h] BYREF
  __int64 v8; // [rsp+60h] [rbp-18h] BYREF

  v8 = 0;
  v7 = 0;
  v6 = 0;
  if ( WindowsCreateStringReference(L"lockframework.LockAppBroker", 0x1Bu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_fcc7498e_d8cf_4993_a9ae_804193af19d7, &v8);
  if ( ActivationFactory < 0
    || (ActivationFactory = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v8)(
                              v8,
                              &GUID_91398107_1c08_44be_8b18_79322a23a71d,
                              &v7),
        ActivationFactory < 0)
    || (ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 24LL))(v7, &v6),
        ActivationFactory < 0)
    || (ActivationFactory = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v6)(
                              v6,
                              &GUID_f2f2e6cf_4806_4728_954a_ef83a6301791,
                              (char *)this + 56),
        ActivationFactory < 0) )
  {
    Log_HREvent_0(
      (unsigned int)ActivationFactory,
      1,
      "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\applauncher.cpp");
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    return (unsigned int)ActivationFactory;
  }
  else
  {
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    return 0;
  }
}

```

## disassembly

```asm
0x1800107d0  push    rbp
0x1800107d2  push    rbx
0x1800107d3  push    rdi
0x1800107d4  push    r14
0x1800107d6  mov     rbp, rsp
0x1800107d9  sub     rsp, 78h
0x1800107dd  mov     rax, cs:__security_cookie
0x1800107e4  xor     rax, rsp
0x1800107e7  mov     [rbp+var_10], rax
0x1800107eb  mov     rdi, rcx
0x1800107ee  mov     [rbp+var_18], 0
0x1800107f6  lea     rcx, ?RuntimeClass_lockframework_LockAppBroker@@3QBGB; "lockframework.LockAppBroker"
0x1800107fd  mov     [rbp+var_20], 0
0x180010805  lea     r9, [rbp+string]; string
0x180010809  mov     [rbp+var_28], 0
0x180010811  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180010815  mov     edx, 1Bh; length
0x18001081a  call    cs:__imp_WindowsCreateStringReference
0x180010820  mov     r14d, 1
0x180010826  test    eax, eax
0x180010828  jns     short loc_18001083E
0x18001082a  xor     r9d, r9d; lpArguments
0x18001082d  xor     r8d, r8d; nNumberOfArguments
0x180010830  mov     edx, r14d; dwExceptionFlags
0x180010833  mov     ecx, 0C000000Dh; dwExceptionCode
0x180010838  call    cs:__imp_RaiseException
0x18001083e  mov     rcx, [rbp+string]
0x180010842  lea     r8, [rbp+var_18]
0x180010846  lea     rdx, _GUID_fcc7498e_d8cf_4993_a9ae_804193af19d7
0x18001084d  call    cs:__imp_RoGetActivationFactory
0x180010853  mov     ebx, eax
0x180010855  test    eax, eax
0x180010857  jns     short loc_1800108B6
0x180010859  mov     r9d, 1AAh
0x18001085f  lea     r8, aOnecoreuapNetP_3; "onecoreuap\\net\\phone\\telephonyintera"...
0x180010866  mov     edx, r14d
0x180010869  mov     ecx, ebx
0x18001086b  call    Log_HREvent_0
0x180010870  mov     rcx, [rbp+var_28]
0x180010874  test    rcx, rcx
0x180010877  jz      short loc_180010885
0x180010879  mov     rdx, [rcx]
0x18001087c  mov     rax, [rdx+10h]
0x180010880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010885  mov     rcx, [rbp+var_20]
0x180010889  test    rcx, rcx
0x18001088c  jz      short loc_18001089A
0x18001088e  mov     rax, [rcx]
0x180010891  mov     rax, [rax+10h]
0x180010895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001089a  mov     rcx, [rbp+var_18]
0x18001089e  test    rcx, rcx
0x1800108a1  jz      short loc_1800108AF
0x1800108a3  mov     rax, [rcx]
0x1800108a6  mov     rax, [rax+10h]
0x1800108aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108af  mov     eax, ebx
0x1800108b1  jmp     loc_18001096F
0x1800108b6  mov     rcx, [rbp+var_18]
0x1800108ba  lea     r8, [rbp+var_20]
0x1800108be  lea     rdx, _GUID_91398107_1c08_44be_8b18_79322a23a71d
0x1800108c5  mov     rax, [rcx]
0x1800108c8  mov     rax, [rax]
0x1800108cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108d0  mov     ebx, eax
0x1800108d2  test    eax, eax
0x1800108d4  jns     short loc_1800108DE
0x1800108d6  mov     r9d, 1ABh
0x1800108dc  jmp     short loc_18001085F
0x1800108de  mov     rcx, [rbp+var_20]
0x1800108e2  lea     rdx, [rbp+var_28]
0x1800108e6  mov     rax, [rcx]
0x1800108e9  mov     rax, [rax+18h]
0x1800108ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108f2  mov     ebx, eax
0x1800108f4  test    eax, eax
0x1800108f6  jns     short loc_180010903
0x1800108f8  mov     r9d, 1ACh
0x1800108fe  jmp     loc_18001085F
0x180010903  mov     rcx, [rbp+var_28]
0x180010907  lea     r8, [rdi+38h]
0x18001090b  lea     rdx, _GUID_f2f2e6cf_4806_4728_954a_ef83a6301791
0x180010912  mov     rax, [rcx]
0x180010915  mov     rax, [rax]
0x180010918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001091d  mov     ebx, eax
0x18001091f  test    eax, eax
0x180010921  jns     short loc_18001092E
0x180010923  mov     r9d, 1ADh
0x180010929  jmp     loc_18001085F
0x18001092e  mov     rcx, [rbp+var_28]
0x180010932  test    rcx, rcx
0x180010935  jz      short loc_180010943
0x180010937  mov     rax, [rcx]
0x18001093a  mov     rax, [rax+10h]
0x18001093e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010943  mov     rcx, [rbp+var_20]
0x180010947  test    rcx, rcx
0x18001094a  jz      short loc_180010958
0x18001094c  mov     rax, [rcx]
0x18001094f  mov     rax, [rax+10h]
0x180010953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010958  mov     rcx, [rbp+var_18]
0x18001095c  test    rcx, rcx
0x18001095f  jz      short loc_18001096D
0x180010961  mov     rax, [rcx]
0x180010964  mov     rax, [rax+10h]
0x180010968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001096d  xor     eax, eax
0x18001096f  mov     rcx, [rbp+var_10]
0x180010973  xor     rcx, rsp; StackCookie
0x180010976  call    __security_check_cookie
0x18001097b  add     rsp, 78h
0x18001097f  pop     r14
0x180010981  pop     rdi
0x180010982  pop     rbx
0x180010983  pop     rbp
0x180010984  retn
```
