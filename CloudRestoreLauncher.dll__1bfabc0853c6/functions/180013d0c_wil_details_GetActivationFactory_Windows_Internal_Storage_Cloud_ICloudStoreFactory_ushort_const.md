# wil::details::GetActivationFactory<Windows::Internal::Storage::Cloud::ICloudStoreFactory>(ushort const *)

- ea: `0x180013d0c`
- end: `0x180013dd3`
- name: `??$GetActivationFactory@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEBG@Z`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001742c`

## callees

- `0x18000c6e0`
- `0x180013d0c`
- `0x18001cfa4`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013d98`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013d98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013d56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013d56`

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
0x180013d0c  mov     r11, rsp
0x180013d0f  push    rbx
0x180013d10  sub     rsp, 60h
0x180013d14  mov     rax, cs:__security_cookie
0x180013d1b  xor     rax, rsp
0x180013d1e  mov     [rsp+68h+var_18], rax
0x180013d23  mov     rbx, rcx
0x180013d26  mov     [r11-38h], rcx
0x180013d2a  mov     [rsp+68h+var_48], 0; int
0x180013d32  xorps   xmm0, xmm0
0x180013d35  xor     eax, eax
0x180013d37  movups  xmmword ptr [rsp+68h+var_30], xmm0
0x180013d3c  mov     [r11-20h], rax
0x180013d40  mov     [r11-40h], rax
0x180013d44  lea     r9, [r11-40h]; string
0x180013d48  lea     r8, [r11-30h]; hstringHeader
0x180013d4c  lea     edx, [rax+29h]; length
0x180013d4f  lea     rcx, ?RuntimeClass_Windows_Internal_Storage_Cloud_CloudStore@@3QBGB; "Windows.Internal.Storage.Cloud.CloudSto"...
0x180013d56  call    cs:__imp_WindowsCreateStringReference
0x180013d5c  mov     rcx, [rsp+68h]; this
0x180013d61  test    eax, eax
0x180013d63  jns     short loc_180013D7A
0x180013d65  mov     r9d, eax; char *
0x180013d68  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180013d6f  mov     edx, 80h; void *
0x180013d74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013d7a  mov     [rsp+68h+var_48], 1; int
0x180013d82  mov     qword ptr [rbx], 0
0x180013d89  mov     r8, rbx
0x180013d8c  lea     rdx, _GUID_fc73907e_e219_4b15_9c14_90c3add7ad22
0x180013d93  mov     rcx, [rsp+68h+var_40]
0x180013d98  call    cs:__imp_RoGetActivationFactory
0x180013d9e  test    eax, eax
0x180013da0  jns     short loc_180013DBC
0x180013da2  mov     rcx, [rsp+68h]; this
0x180013da7  mov     r9d, eax; char *
0x180013daa  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180013db1  mov     edx, 83h; void *
0x180013db6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013dbc  mov     rax, rbx
0x180013dbf  mov     rcx, [rsp+68h+var_18]
0x180013dc4  xor     rcx, rsp; StackCookie
0x180013dc7  call    __security_check_cookie
0x180013dcc  add     rsp, 60h
0x180013dd0  pop     rbx
0x180013dd1  retn
```
