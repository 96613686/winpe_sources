# InitHiddenCharacter(void)

- ea: `0x1800ff854`
- end: `0x1800ff91e`
- name: `?InitHiddenCharacter@@YAXXZ`
- size: `202`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004b710`

## callees

- `0x180048d5c`
- `0x1800ff854`
- `0x18013bad0`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ff917`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ff917`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800ff8b7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800ff8b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ff88f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ff88f`

## string_xrefs

- `0x1800ff888`: `Windows.UI.Text.Core.CoreTextServicesConstants`

## pseudocode

```c
void InitHiddenCharacter(void)
{
  HRESULT v0; // eax
  HSTRING v1; // rbx
  __int64 v2; // rcx
  __int64 v3; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER v4; // [rsp+28h] [rbp-30h] BYREF
  HSTRING v5; // [rsp+40h] [rbp-18h] BYREF

  v3 = 0;
  v5 = 0;
  v0 = WindowsCreateStringReference(L"Windows.UI.Text.Core.CoreTextServicesConstants", 0x2Eu, &v4, &v5);
  if ( v0 < 0 )
  {
    RaiseException(v0, 1u, 0, 0);
    JUMPOUT(0x1800FF91DLL);
  }
  v1 = v5;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v3);
  if ( (int)RoGetActivationFactory(v1, &GUID_91859a46_eccf_47a4_8ae7_098a9c6fbb15, &v3) >= 0 )
    (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v3 + 48LL))(v3, &wchTSF30Hidden);
  v2 = v3;
  if ( v3 )
  {
    v3 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
}

```

## disassembly

```asm
0x1800ff854  mov     r11, rsp
0x1800ff857  push    rbx
0x1800ff858  sub     rsp, 50h
0x1800ff85c  mov     rax, cs:__security_cookie
0x1800ff863  xor     rax, rsp
0x1800ff866  mov     [rsp+58h+var_10], rax
0x1800ff86b  lea     r9, [r11-18h]; string
0x1800ff86f  mov     qword ptr [r11-38h], 0
0x1800ff877  lea     r8, [r11-30h]; hstringHeader
0x1800ff87b  mov     qword ptr [r11-18h], 0
0x1800ff883  mov     edx, 2Eh ; '.'; length
0x1800ff888  lea     rcx, ?RuntimeClass_Windows_UI_Text_Core_CoreTextServicesConstants@@3QBGB; "Windows.UI.Text.Core.CoreTextServicesCo"...
0x1800ff88f  call    cs:__imp_WindowsCreateStringReference
0x1800ff895  test    eax, eax
0x1800ff897  js      short loc_1800FF90B
0x1800ff899  mov     rbx, [rsp+58h+var_18]
0x1800ff89e  lea     rcx, [rsp+58h+var_38]
0x1800ff8a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ff8a8  lea     r8, [rsp+58h+var_38]
0x1800ff8ad  mov     rcx, rbx
0x1800ff8b0  lea     rdx, _GUID_91859a46_eccf_47a4_8ae7_098a9c6fbb15
0x1800ff8b7  call    cs:__imp_RoGetActivationFactory
0x1800ff8bd  test    eax, eax
0x1800ff8bf  js      short loc_1800FF8D9
0x1800ff8c1  mov     rcx, [rsp+58h+var_38]
0x1800ff8c6  lea     rdx, ?wchTSF30Hidden@@3GA; ushort wchTSF30Hidden
0x1800ff8cd  mov     rax, [rcx]
0x1800ff8d0  mov     rax, [rax+30h]
0x1800ff8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff8d9  mov     rcx, [rsp+58h+var_38]
0x1800ff8de  test    rcx, rcx
0x1800ff8e1  jz      short loc_1800FF8F8
0x1800ff8e3  mov     [rsp+58h+var_38], 0
0x1800ff8ec  mov     rax, [rcx]
0x1800ff8ef  mov     rax, [rax+10h]
0x1800ff8f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff8f8  mov     rcx, [rsp+58h+var_10]
0x1800ff8fd  xor     rcx, rsp; StackCookie
0x1800ff900  call    __security_check_cookie
0x1800ff905  add     rsp, 50h
0x1800ff909  pop     rbx
0x1800ff90a  retn
0x1800ff90b  xor     r9d, r9d; lpArguments
0x1800ff90e  xor     r8d, r8d; nNumberOfArguments
0x1800ff911  mov     ecx, eax; dwExceptionCode
0x1800ff913  lea     edx, [r9+1]; dwExceptionFlags
0x1800ff917  call    cs:__imp_RaiseException
```
