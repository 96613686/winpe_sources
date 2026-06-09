# wil::details::GetActivationFactory<Windows::Internal::Storage::Cloud::ICloudStoreFactory>(ushort const *)

- ea: `0x18003f620`
- end: `0x18003f6e7`
- name: `??$GetActivationFactory@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEBG@Z`
- size: `199`
- prototype: `HSTRING __fastcall(HSTRING)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004fa30`

## callees

- `0x18003f620`
- `0x180061320`
- `0x180070530`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003f66a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003f66a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003f6ac`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003f6ac`

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
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v2,
      0);
  *(_QWORD *)a1 = 0;
  ActivationFactory = RoGetActivationFactory(v5[0], &GUID_fc73907e_e219_4b15_9c14_90c3add7ad22, a1);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
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
0x18003f620  mov     r11, rsp
0x18003f623  push    rbx
0x18003f624  sub     rsp, 60h
0x18003f628  mov     rax, cs:__security_cookie
0x18003f62f  xor     rax, rsp
0x18003f632  mov     [rsp+68h+var_18], rax
0x18003f637  mov     rbx, rcx
0x18003f63a  mov     [r11-38h], rcx
0x18003f63e  mov     [rsp+68h+var_48], 0; int
0x18003f646  xorps   xmm0, xmm0
0x18003f649  xor     eax, eax
0x18003f64b  movups  xmmword ptr [rsp+68h+var_30], xmm0
0x18003f650  mov     [r11-20h], rax
0x18003f654  mov     [r11-40h], rax
0x18003f658  lea     r9, [r11-40h]; string
0x18003f65c  lea     r8, [r11-30h]; hstringHeader
0x18003f660  lea     edx, [rax+29h]; length
0x18003f663  lea     rcx, ?RuntimeClass_Windows_Internal_Storage_Cloud_CloudStore@@3QBGB; "Windows.Internal.Storage.Cloud.CloudSto"...
0x18003f66a  call    cs:__imp_WindowsCreateStringReference
0x18003f670  mov     rcx, [rsp+68h]; this
0x18003f675  test    eax, eax
0x18003f677  jns     short loc_18003F68E
0x18003f679  mov     r9d, eax; char *
0x18003f67c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18003f683  mov     edx, 80h; void *
0x18003f688  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003f68e  mov     [rsp+68h+var_48], 1; int
0x18003f696  mov     qword ptr [rbx], 0
0x18003f69d  mov     r8, rbx
0x18003f6a0  lea     rdx, _GUID_fc73907e_e219_4b15_9c14_90c3add7ad22
0x18003f6a7  mov     rcx, [rsp+68h+var_40]
0x18003f6ac  call    cs:__imp_RoGetActivationFactory
0x18003f6b2  test    eax, eax
0x18003f6b4  jns     short loc_18003F6D0
0x18003f6b6  mov     rcx, [rsp+68h]; this
0x18003f6bb  mov     r9d, eax; char *
0x18003f6be  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18003f6c5  mov     edx, 83h; void *
0x18003f6ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003f6d0  mov     rax, rbx
0x18003f6d3  mov     rcx, [rsp+68h+var_18]
0x18003f6d8  xor     rcx, rsp; StackCookie
0x18003f6db  call    __security_check_cookie
0x18003f6e0  add     rsp, 60h
0x18003f6e4  pop     rbx
0x18003f6e5  retn
```
