# wil::details::GetActivationFactory<Windows::Internal::Storage::Cloud::ICloudStoreFactory>(ushort const *)

- ea: `0x18001e1c0`
- end: `0x18001e287`
- name: `??$GetActivationFactory@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEBG@Z`
- size: `199`
- prototype: `HSTRING __fastcall(HSTRING)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d124`

## callees

- `0x18001e1c0`
- `0x18002a030`
- `0x18002e2d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e20a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e20a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e24c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e24c`

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
0x18001e1c0  mov     r11, rsp
0x18001e1c3  push    rbx
0x18001e1c4  sub     rsp, 60h
0x18001e1c8  mov     rax, cs:__security_cookie
0x18001e1cf  xor     rax, rsp
0x18001e1d2  mov     [rsp+68h+var_18], rax
0x18001e1d7  mov     rbx, rcx
0x18001e1da  mov     [r11-38h], rcx
0x18001e1de  mov     [rsp+68h+var_48], 0; int
0x18001e1e6  xorps   xmm0, xmm0
0x18001e1e9  xor     eax, eax
0x18001e1eb  movups  xmmword ptr [rsp+68h+var_30], xmm0
0x18001e1f0  mov     [r11-20h], rax
0x18001e1f4  mov     [r11-40h], rax
0x18001e1f8  lea     r9, [r11-40h]; string
0x18001e1fc  lea     r8, [r11-30h]; hstringHeader
0x18001e200  lea     edx, [rax+29h]; length
0x18001e203  lea     rcx, ?RuntimeClass_Windows_Internal_Storage_Cloud_CloudStore@@3QBGB; "Windows.Internal.Storage.Cloud.CloudSto"...
0x18001e20a  call    cs:__imp_WindowsCreateStringReference
0x18001e210  mov     rcx, [rsp+68h]; this
0x18001e215  test    eax, eax
0x18001e217  jns     short loc_18001E22E
0x18001e219  mov     r9d, eax; char *
0x18001e21c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18001e223  mov     edx, 80h; void *
0x18001e228  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e22e  mov     [rsp+68h+var_48], 1; int
0x18001e236  mov     qword ptr [rbx], 0
0x18001e23d  mov     r8, rbx
0x18001e240  lea     rdx, _GUID_fc73907e_e219_4b15_9c14_90c3add7ad22
0x18001e247  mov     rcx, [rsp+68h+var_40]
0x18001e24c  call    cs:__imp_RoGetActivationFactory
0x18001e252  test    eax, eax
0x18001e254  jns     short loc_18001E270
0x18001e256  mov     rcx, [rsp+68h]; this
0x18001e25b  mov     r9d, eax; char *
0x18001e25e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18001e265  mov     edx, 83h; void *
0x18001e26a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e270  mov     rax, rbx
0x18001e273  mov     rcx, [rsp+68h+var_18]
0x18001e278  xor     rcx, rsp; StackCookie
0x18001e27b  call    __security_check_cookie
0x18001e280  add     rsp, 60h
0x18001e284  pop     rbx
0x18001e285  retn
```
