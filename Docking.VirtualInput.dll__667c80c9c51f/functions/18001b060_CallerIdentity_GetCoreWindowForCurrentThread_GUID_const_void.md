# CallerIdentity::GetCoreWindowForCurrentThread(_GUID const &,void * *)

- ea: `0x18001b060`
- end: `0x18001b161`
- name: `?GetCoreWindowForCurrentThread@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `257`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001b168`

## callees

- `0x1800036a0`
- `0x18001b060`
- `0x18001b270`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b0b9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b0b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b0a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b0a0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001b0da`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001b0da`

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
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v10);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1, &v10);
  if ( ActivationFactory >= 0 )
  {
    v6 = v10;
    v9 = 0;
    v7 = *(void (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, const struct _GUID *)))(*(_QWORD *)v10 + 48LL);
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v9);
    v7(v6, &v9);
    if ( v9 )
      ActivationFactory = (**v9)(v9, &GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f, a2);
    else
      ActivationFactory = -2147023728;
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v9);
  }
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v10);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001b060  push    rbp
0x18001b062  push    rbx
0x18001b063  push    rsi
0x18001b064  push    rdi
0x18001b065  mov     rbp, rsp
0x18001b068  sub     rsp, 68h
0x18001b06c  mov     rax, cs:__security_cookie
0x18001b073  xor     rax, rsp
0x18001b076  mov     [rbp+var_18], rax
0x18001b07a  mov     rsi, rdx
0x18001b07d  mov     qword ptr [rdx], 0
0x18001b084  mov     edx, 1Ah; length
0x18001b089  mov     [rbp+var_40], 0
0x18001b091  lea     r9, [rbp+string]; string
0x18001b095  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001b099  lea     rcx, ?RuntimeClass_Windows_UI_Core_CoreWindow@@3QBGB; "Windows.UI.Core.CoreWindow"
0x18001b0a0  call    cs:__imp_WindowsCreateStringReference
0x18001b0a6  test    eax, eax
0x18001b0a8  jns     short loc_18001B0BF
0x18001b0aa  xor     r9d, r9d; lpArguments
0x18001b0ad  xor     r8d, r8d; nNumberOfArguments
0x18001b0b0  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001b0b5  lea     edx, [r9+1]; dwExceptionFlags
0x18001b0b9  call    cs:__imp_RaiseException
0x18001b0bf  mov     rbx, [rbp+string]
0x18001b0c3  lea     rcx, [rbp+var_40]
0x18001b0c7  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18001b0cc  lea     r8, [rbp+var_40]
0x18001b0d0  mov     rcx, rbx
0x18001b0d3  lea     rdx, _GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1
0x18001b0da  call    cs:__imp_RoGetActivationFactory
0x18001b0e0  mov     ebx, eax
0x18001b0e2  test    eax, eax
0x18001b0e4  js      short loc_18001B141
0x18001b0e6  mov     rdi, [rbp+var_40]
0x18001b0ea  lea     rcx, [rbp+var_48]
0x18001b0ee  mov     [rbp+var_48], 0
0x18001b0f6  mov     rax, [rdi]
0x18001b0f9  mov     rbx, [rax+30h]
0x18001b0fd  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18001b102  lea     rdx, [rbp+var_48]
0x18001b106  mov     rcx, rdi
0x18001b109  mov     rax, rbx
0x18001b10c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b111  mov     rcx, [rbp+var_48]
0x18001b115  test    rcx, rcx
0x18001b118  jnz     short loc_18001B121
0x18001b11a  mov     ebx, 80070490h
0x18001b11f  jmp     short loc_18001B138
0x18001b121  mov     rax, [rcx]
0x18001b124  lea     rdx, _GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f
0x18001b12b  mov     r8, rsi
0x18001b12e  mov     rax, [rax]
0x18001b131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b136  mov     ebx, eax
0x18001b138  lea     rcx, [rbp+var_48]
0x18001b13c  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18001b141  lea     rcx, [rbp+var_40]
0x18001b145  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18001b14a  mov     eax, ebx
0x18001b14c  mov     rcx, [rbp+var_18]
0x18001b150  xor     rcx, rsp; StackCookie
0x18001b153  call    __security_check_cookie
0x18001b158  add     rsp, 68h
0x18001b15c  pop     rdi
0x18001b15d  pop     rsi
0x18001b15e  pop     rbx
0x18001b15f  pop     rbp
0x18001b160  retn
```
