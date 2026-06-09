# std::_Construct_in_place<Microsoft::Bluetooth::Foundation::Details::ComDisconnectableContextImpl,>(Microsoft::Bluetooth::Foundation::Details::ComDisconnectableContextImpl &)

- ea: `0x18000aa78`
- end: `0x18000aae3`
- name: `??$_Construct_in_place@VComDisconnectableContextImpl@Details@Foundation@Bluetooth@Microsoft@@$$V@std@@YAXAEAVComDisconnectableContextImpl@Details@Foundation@Bluetooth@Microsoft@@@Z`
- size: `107`
- prototype: `HRESULT __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000cc28`

## callees

- `0x18000aa78`
- `0x18000d0c0`
- `0x18000e0c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aab9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aab9`

## string_xrefs

- `0x18000aad1`: `onecore\drivers\bluetooth\foundation\lib\ComDisconnectableContext.h`

## pseudocode

```c
HRESULT __fastcall std::_Construct_in_place<Microsoft::Bluetooth::Foundation::Details::ComDisconnectableContextImpl,>(
        _QWORD *a1)
{
  LPVOID *v1; // rbx
  HRESULT result; // eax
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = &Microsoft::Bluetooth::Foundation::Details::ComDisconnectableContextImpl::`vftable';
  v1 = (LPVOID *)(a1 + 1);
  a1[1] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 1);
  result = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, v1);
  if ( result < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ComDisconnectableContext.h",
      (const char *)(unsigned int)result,
      ppv);
  return result;
}

```

## disassembly

```asm
0x18000aa78  push    rbx
0x18000aa7a  sub     rsp, 30h
0x18000aa7e  mov     [rsp+38h+arg_0], rcx
0x18000aa83  lea     rax, ??_7ComDisconnectableContextImpl@Details@Foundation@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::Foundation::Details::ComDisconnectableContextImpl::`vftable'
0x18000aa8a  mov     [rcx], rax
0x18000aa8d  lea     rbx, [rcx+8]
0x18000aa91  mov     qword ptr [rbx], 0
0x18000aa98  mov     rcx, rbx
0x18000aa9b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000aaa0  mov     qword ptr [rsp+38h+ppv], rbx; int
0x18000aaa5  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18000aaac  xor     edx, edx; pUnkOuter
0x18000aaae  lea     r8d, [rdx+1]; dwClsContext
0x18000aab2  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18000aab9  call    cs:__imp_CoCreateInstance
0x18000aabf  mov     rcx, [rsp+38h]; this
0x18000aac4  test    eax, eax
0x18000aac6  js      short loc_18000AACE
0x18000aac8  add     rsp, 30h
0x18000aacc  pop     rbx
0x18000aacd  retn
0x18000aace  mov     r9d, eax; char *
0x18000aad1  lea     r8, aOnecoreDrivers_42; "onecore\\drivers\\bluetooth\\foundation"...
0x18000aad8  mov     edx, 94h; void *
0x18000aadd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
