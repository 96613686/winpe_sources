# wil::details::GetActivationFactory<Windows::Internal::Storage::Cloud::ICloudStoreFactory>(ushort const *)

- ea: `0x1800085b8`
- end: `0x18000867f`
- name: `??$GetActivationFactory@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEBG@Z`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800097ec`

## callees

- `0x180003980`
- `0x1800085b8`
- `0x18000cf94`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008602`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180008644`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180008644`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800085b8  mov     r11, rsp
0x1800085bb  push    rbx
0x1800085bc  sub     rsp, 60h
0x1800085c0  mov     rax, cs:__security_cookie
0x1800085c7  xor     rax, rsp
0x1800085ca  mov     [rsp+68h+var_18], rax
0x1800085cf  mov     rbx, rcx
0x1800085d2  mov     [r11-38h], rcx
0x1800085d6  mov     [rsp+68h+var_48], 0; int
0x1800085de  xorps   xmm0, xmm0
0x1800085e1  xor     eax, eax
0x1800085e3  movups  xmmword ptr [rsp+68h+var_30], xmm0
0x1800085e8  mov     [r11-20h], rax
0x1800085ec  mov     [r11-40h], rax
0x1800085f0  lea     r9, [r11-40h]; string
0x1800085f4  lea     r8, [r11-30h]; hstringHeader
0x1800085f8  lea     edx, [rax+29h]; length
0x1800085fb  lea     rcx, ?RuntimeClass_Windows_Internal_Storage_Cloud_CloudStore@@3QBGB; "Windows.Internal.Storage.Cloud.CloudSto"...
0x180008602  call    cs:__imp_WindowsCreateStringReference
0x180008608  mov     rcx, [rsp+68h]; this
0x18000860d  test    eax, eax
0x18000860f  jns     short loc_180008626
0x180008611  mov     r9d, eax; char *
0x180008614  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18000861b  mov     edx, 80h; void *
0x180008620  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180008626  mov     [rsp+68h+var_48], 1; int
0x18000862e  mov     qword ptr [rbx], 0
0x180008635  mov     r8, rbx
0x180008638  lea     rdx, _GUID_fc73907e_e219_4b15_9c14_90c3add7ad22
0x18000863f  mov     rcx, [rsp+68h+var_40]
0x180008644  call    cs:__imp_RoGetActivationFactory
0x18000864a  test    eax, eax
0x18000864c  jns     short loc_180008668
0x18000864e  mov     rcx, [rsp+68h]; this
0x180008653  mov     r9d, eax; char *
0x180008656  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18000865d  mov     edx, 83h; void *
0x180008662  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180008668  mov     rax, rbx
0x18000866b  mov     rcx, [rsp+68h+var_18]
0x180008670  xor     rcx, rsp; StackCookie
0x180008673  call    __security_check_cookie
0x180008678  add     rsp, 60h
0x18000867c  pop     rbx
0x18000867d  retn
```
