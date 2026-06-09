# Details::GetLauncherInternal(void)

- ea: `0x1800259a8`
- end: `0x180025ae7`
- name: `?GetLauncherInternal@Details@@YA?AV?$ComPtr@UILauncherStaticsInternal@Private@System@Windows@@@WRL@Microsoft@@XZ`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180027080`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x180017c58`
- `0x1800259a8`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025a14`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025a14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800259f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800259f2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025a3e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025a3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Details::GetLauncherInternal(_QWORD *a1)
{
  HSTRING v2; // rbx
  int ActivationFactory; // eax
  __int64 (__fastcall ***v4)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v5)(_QWORD, GUID *, _QWORD *); // rdi
  int v6; // eax
  __int64 (__fastcall ***v8)(_QWORD, GUID *, _QWORD *); // [rsp+20h] [rbp-48h] BYREF
  int v9; // [rsp+28h] [rbp-40h]
  _QWORD *v10; // [rsp+30h] [rbp-38h]
  HSTRING v11; // [rsp+38h] [rbp-30h] BYREF
  HSTRING_HEADER v12; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v10 = a1;
  v9 = 0;
  v8 = 0;
  if ( WindowsCreateStringReference(L"Windows.System.Launcher", 0x17u, &v12, &v11) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = v11;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_59ba2fbb_24cb_4c02_a4c4_8294569d54f1, &v8);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
      (const char *)(unsigned int)ActivationFactory,
      (int)v8);
  *a1 = 0;
  v9 = 1;
  v4 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v8;
  v5 = **v8;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
  v6 = v5(v4, &GUID_d906c164_6384_416f_b6d4_e9317ab95053, a1);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
      (const char *)(unsigned int)v6,
      (int)v8);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  return a1;
}

```

## disassembly

```asm
0x1800259a8  mov     r11, rsp
0x1800259ab  mov     [r11+10h], rbx
0x1800259af  mov     [r11+18h], rsi
0x1800259b3  push    rdi
0x1800259b4  sub     rsp, 60h
0x1800259b8  mov     rax, cs:__security_cookie
0x1800259bf  xor     rax, rsp
0x1800259c2  mov     [rsp+68h+var_10], rax
0x1800259c7  mov     rsi, rcx
0x1800259ca  mov     [r11-38h], rcx
0x1800259ce  mov     [rsp+68h+var_40], 0
0x1800259d6  mov     qword ptr [r11-48h], 0
0x1800259de  lea     r9, [r11-30h]; string
0x1800259e2  lea     r8, [r11-28h]; hstringHeader
0x1800259e6  mov     edx, 17h; length
0x1800259eb  lea     rcx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x1800259f2  call    cs:__imp_WindowsCreateStringReference
0x1800259f9  nop     dword ptr [rax+rax+00h]
0x1800259fe  mov     edi, 1
0x180025a03  test    eax, eax
0x180025a05  jns     short loc_180025A20
0x180025a07  xor     r9d, r9d; lpArguments
0x180025a0a  xor     r8d, r8d; nNumberOfArguments
0x180025a0d  mov     edx, edi; dwExceptionFlags
0x180025a0f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180025a14  call    cs:__imp_RaiseException
0x180025a1b  nop     dword ptr [rax+rax+00h]
0x180025a20  mov     rbx, [rsp+68h+var_30]
0x180025a25  lea     rcx, [rsp+68h+var_48]
0x180025a2a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a2f  lea     r8, [rsp+68h+var_48]
0x180025a34  lea     rdx, _GUID_59ba2fbb_24cb_4c02_a4c4_8294569d54f1
0x180025a3b  mov     rcx, rbx
0x180025a3e  call    cs:__imp_RoGetActivationFactory
0x180025a45  nop     dword ptr [rax+rax+00h]
0x180025a4a  mov     rcx, [rsp+68h]; this
0x180025a4f  test    eax, eax
0x180025a51  jns     short loc_180025A68
0x180025a53  mov     r9d, eax; char *
0x180025a56  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x180025a5d  mov     edx, 47h ; 'G'; void *
0x180025a62  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180025a68  mov     qword ptr [rsi], 0
0x180025a6f  mov     [rsp+68h+var_40], edi
0x180025a73  mov     rbx, [rsp+68h+var_48]
0x180025a78  mov     rax, [rbx]
0x180025a7b  mov     rdi, [rax]
0x180025a7e  mov     rcx, rsi
0x180025a81  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a86  mov     r8, rsi
0x180025a89  lea     rdx, _GUID_d906c164_6384_416f_b6d4_e9317ab95053
0x180025a90  mov     rcx, rbx
0x180025a93  mov     rax, rdi
0x180025a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a9b  nop
0x180025a9c  mov     rcx, [rsp+68h]; this
0x180025aa1  test    eax, eax
0x180025aa3  jns     short loc_180025ABA
0x180025aa5  mov     r9d, eax; char *
0x180025aa8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x180025aaf  mov     edx, 49h ; 'I'; void *
0x180025ab4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180025aba  lea     rcx, [rsp+68h+var_48]
0x180025abf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025ac4  mov     rax, rsi
0x180025ac7  mov     rcx, [rsp+68h+var_10]
0x180025acc  xor     rcx, rsp; StackCookie
0x180025acf  call    __security_check_cookie
0x180025ad4  lea     r11, [rsp+68h+var_8]
0x180025ad9  mov     rbx, [r11+18h]
0x180025add  mov     rsi, [r11+20h]
0x180025ae1  mov     rsp, r11
0x180025ae4  pop     rdi
0x180025ae5  retn
```
