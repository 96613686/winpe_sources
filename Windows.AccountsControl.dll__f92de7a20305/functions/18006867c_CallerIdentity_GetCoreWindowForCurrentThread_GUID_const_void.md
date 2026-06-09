# CallerIdentity::GetCoreWindowForCurrentThread(_GUID const &,void * *)

- ea: `0x18006867c`
- end: `0x18006877d`
- name: `?GetCoreWindowForCurrentThread@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `257`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180068784`

## callees

- `0x18000634c`
- `0x180011ffc`
- `0x18006867c`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800686d5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800686d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800686bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800686bc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800686f6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800686f6`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCoreWindowForCurrentThread(
        CallerIdentity *this,
        const struct _GUID *a2,
        void **a3)
{
  HSTRING v4; // rbx
  int ActivationFactory; // ebx
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, const struct _GUID *)); // rbx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, const struct _GUID *); // [rsp+20h] [rbp-48h] BYREF
  __int64 v10; // [rsp+28h] [rbp-40h] BYREF
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF

  *(_QWORD *)&a2->Data1 = 0;
  v10 = 0;
  if ( WindowsCreateStringReference(L"Windows.UI.Core.CoreWindow", 0x1Au, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1, &v10);
  if ( ActivationFactory >= 0 )
  {
    v6 = v10;
    v9 = 0;
    v7 = *(void (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, const struct _GUID *)))(*(_QWORD *)v10 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
    v7(v6, &v9);
    if ( v9 )
      ActivationFactory = (**v9)(v9, &GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f, a2);
    else
      ActivationFactory = -2147023728;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18006867c  push    rbp
0x18006867e  push    rbx
0x18006867f  push    rsi
0x180068680  push    rdi
0x180068681  mov     rbp, rsp
0x180068684  sub     rsp, 68h
0x180068688  mov     rax, cs:__security_cookie
0x18006868f  xor     rax, rsp
0x180068692  mov     [rbp+var_18], rax
0x180068696  mov     rsi, rdx
0x180068699  mov     qword ptr [rdx], 0
0x1800686a0  mov     edx, 1Ah; length
0x1800686a5  mov     [rbp+var_40], 0
0x1800686ad  lea     r9, [rbp+string]; string
0x1800686b1  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800686b5  lea     rcx, ?RuntimeClass_Windows_UI_Core_CoreWindow@@3QBGB; "Windows.UI.Core.CoreWindow"
0x1800686bc  call    cs:__imp_WindowsCreateStringReference
0x1800686c2  test    eax, eax
0x1800686c4  jns     short loc_1800686DB
0x1800686c6  xor     r9d, r9d; lpArguments
0x1800686c9  xor     r8d, r8d; nNumberOfArguments
0x1800686cc  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800686d1  lea     edx, [r9+1]; dwExceptionFlags
0x1800686d5  call    cs:__imp_RaiseException
0x1800686db  mov     rbx, [rbp+string]
0x1800686df  lea     rcx, [rbp+var_40]
0x1800686e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800686e8  lea     r8, [rbp+var_40]
0x1800686ec  mov     rcx, rbx
0x1800686ef  lea     rdx, _GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1
0x1800686f6  call    cs:__imp_RoGetActivationFactory
0x1800686fc  mov     ebx, eax
0x1800686fe  test    eax, eax
0x180068700  js      short loc_18006875D
0x180068702  mov     rdi, [rbp+var_40]
0x180068706  lea     rcx, [rbp+var_48]
0x18006870a  mov     [rbp+var_48], 0
0x180068712  mov     rax, [rdi]
0x180068715  mov     rbx, [rax+30h]
0x180068719  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006871e  lea     rdx, [rbp+var_48]
0x180068722  mov     rcx, rdi
0x180068725  mov     rax, rbx
0x180068728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006872d  mov     rcx, [rbp+var_48]
0x180068731  test    rcx, rcx
0x180068734  jnz     short loc_18006873D
0x180068736  mov     ebx, 80070490h
0x18006873b  jmp     short loc_180068754
0x18006873d  mov     rax, [rcx]
0x180068740  lea     rdx, _GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f
0x180068747  mov     r8, rsi
0x18006874a  mov     rax, [rax]
0x18006874d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068752  mov     ebx, eax
0x180068754  lea     rcx, [rbp+var_48]
0x180068758  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006875d  lea     rcx, [rbp+var_40]
0x180068761  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180068766  mov     eax, ebx
0x180068768  mov     rcx, [rbp+var_18]
0x18006876c  xor     rcx, rsp; StackCookie
0x18006876f  call    __security_check_cookie
0x180068774  add     rsp, 68h
0x180068778  pop     rdi
0x180068779  pop     rsi
0x18006877a  pop     rbx
0x18006877b  pop     rbp
0x18006877c  retn
```
