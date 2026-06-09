# wil::details::GetActivationFactory<Windows::Internal::Storage::Cloud::ICloudStoreFactory>(wchar_t const *)

- ea: `0x18000cac0`
- end: `0x18000cb87`
- name: `??$GetActivationFactory@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEB_W@Z`
- size: `199`
- prototype: `HSTRING __fastcall(HSTRING)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001f1f0`

## callees

- `0x180003560`
- `0x18000cac0`
- `0x180022b80`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000cb0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000cb0a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000cb4c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000cb4c`

## pseudocode

```c
HSTRING __fastcall wil::details::GetActivationFactory<Windows::Internal::Storage::Cloud::ICloudStoreFactory>(
        HSTRING a1)
{
  HRESULT v2; // eax
  int ActivationFactory; // eax
  HSTRING v5[2]; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER v6; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5[1] = a1;
  memset(&v6, 0, sizeof(v6));
  v5[0] = 0;
  v2 = WindowsCreateStringReference(L"Windows.Internal.Storage.Cloud.CloudStore", 0x29u, &v6, v5);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v2,
      0);
  *(_QWORD *)a1 = 0;
  ActivationFactory = RoGetActivationFactory(v5[0], &GUID_fc73907e_e219_4b15_9c14_90c3add7ad22, a1);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)ActivationFactory,
      1);
  return a1;
}

```

## disassembly

```asm
0x18000cac0  mov     r11, rsp
0x18000cac3  push    rbx
0x18000cac4  sub     rsp, 60h
0x18000cac8  mov     rax, cs:__security_cookie
0x18000cacf  xor     rax, rsp
0x18000cad2  mov     [rsp+68h+var_18], rax
0x18000cad7  mov     rbx, rcx
0x18000cada  mov     [r11-38h], rcx
0x18000cade  mov     [rsp+68h+var_48], 0; int
0x18000cae6  xorps   xmm0, xmm0
0x18000cae9  xor     eax, eax
0x18000caeb  movups  xmmword ptr [rsp+68h+var_30], xmm0
0x18000caf0  mov     [r11-20h], rax
0x18000caf4  mov     [r11-40h], rax
0x18000caf8  lea     r9, [r11-40h]; string
0x18000cafc  lea     r8, [r11-30h]; hstringHeader
0x18000cb00  lea     edx, [rax+29h]; length
0x18000cb03  lea     rcx, ?RuntimeClass_Windows_Internal_Storage_Cloud_CloudStore@@3QB_WB; "Windows.Internal.Storage.Cloud.CloudSto"...
0x18000cb0a  call    cs:__imp_WindowsCreateStringReference
0x18000cb10  mov     rcx, [rsp+68h]; this
0x18000cb15  test    eax, eax
0x18000cb17  jns     short loc_18000CB2E
0x18000cb19  mov     r9d, eax; char *
0x18000cb1c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18000cb23  mov     edx, 80h; void *
0x18000cb28  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000cb2e  mov     [rsp+68h+var_48], 1; int
0x18000cb36  mov     qword ptr [rbx], 0
0x18000cb3d  mov     r8, rbx
0x18000cb40  lea     rdx, _GUID_fc73907e_e219_4b15_9c14_90c3add7ad22
0x18000cb47  mov     rcx, [rsp+68h+var_40]
0x18000cb4c  call    cs:__imp_RoGetActivationFactory
0x18000cb52  test    eax, eax
0x18000cb54  jns     short loc_18000CB70
0x18000cb56  mov     rcx, [rsp+68h]; this
0x18000cb5b  mov     r9d, eax; char *
0x18000cb5e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18000cb65  mov     edx, 83h; void *
0x18000cb6a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000cb70  mov     rax, rbx
0x18000cb73  mov     rcx, [rsp+68h+var_18]
0x18000cb78  xor     rcx, rsp; StackCookie
0x18000cb7b  call    __security_check_cookie
0x18000cb80  add     rsp, 60h
0x18000cb84  pop     rbx
0x18000cb85  retn
```
