# _GetDeviceFamily(ushort * *)

- ea: `0x18001e6bc`
- end: `0x18001e7e8`
- name: `?_GetDeviceFamily@@YAJPEAPEAG@Z`
- size: `300`
- prototype: `__int64 __fastcall(LPWSTR *ppwsz)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001ce10`

## callees

- `0x180002ce0`
- `0x18000a4d0`
- `0x18001bf70`
- `0x18001e6bc`
- `0x18002d010`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18001e7ab`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18001e7ab`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e720`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e720`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e776`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e7b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e776`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e7b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e79f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e79f`

## pseudocode

```c
__int64 __fastcall _GetDeviceFamily(LPWSTR *ppwsz)
{
  HSTRING_HEADER *v2; // rax
  HRESULT ActivationFactory; // ebx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, const WCHAR **); // rbx
  const WCHAR *v6; // rdi
  __int64 (__fastcall *v7)(const WCHAR *, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v10; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+28h] [rbp-40h] BYREF
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER v13; // [rsp+38h] [rbp-30h] BYREF

  *ppwsz = 0;
  v11 = 0;
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v11);
  v10 = L"Windows.System.Profile.AnalyticsInfo";
  v11 = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v13, &v10);
  ActivationFactory = RoGetActivationFactory(v2[1].Reserved.Reserved1, &GUID_1d5ee066_188d_5ba9_4387_acaeb0e7e305, &v11);
  if ( ActivationFactory >= 0 )
  {
    v10 = 0;
    v4 = v11;
    v5 = *(__int64 (__fastcall **)(__int64, const WCHAR **))(*(_QWORD *)v11 + 48LL);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v10);
    ActivationFactory = v5(v4, &v10);
    if ( ActivationFactory >= 0 )
    {
      string = 0;
      v6 = v10;
      v7 = *(__int64 (__fastcall **)(const WCHAR *, HSTRING *))(*(_QWORD *)v10 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      ActivationFactory = v7(v6, &string);
      if ( ActivationFactory >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        ActivationFactory = SHStrDupW(StringRawBuffer, ppwsz);
      }
      WindowsDeleteString(string);
    }
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v10);
  }
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v11);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001e6bc  push    rbp
0x18001e6be  push    rbx
0x18001e6bf  push    rsi
0x18001e6c0  push    rdi
0x18001e6c1  mov     rbp, rsp
0x18001e6c4  sub     rsp, 68h
0x18001e6c8  mov     rax, cs:__security_cookie
0x18001e6cf  xor     rax, rsp
0x18001e6d2  mov     [rbp+var_10], rax
0x18001e6d6  mov     rsi, rcx
0x18001e6d9  mov     qword ptr [rcx], 0
0x18001e6e0  mov     [rbp+var_40], 0
0x18001e6e8  lea     rcx, [rbp+var_40]
0x18001e6ec  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001e6f1  lea     rax, ?RuntimeClass_Windows_System_Profile_AnalyticsInfo@@3QBGB; "Windows.System.Profile.AnalyticsInfo"
0x18001e6f8  mov     [rbp+var_48], rax
0x18001e6fc  mov     [rbp+var_40], 0
0x18001e704  lea     rdx, [rbp+var_48]
0x18001e708  lea     rcx, [rbp+var_30]
0x18001e70c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e711  lea     r8, [rbp+var_40]
0x18001e715  lea     rdx, _GUID_1d5ee066_188d_5ba9_4387_acaeb0e7e305
0x18001e71c  mov     rcx, [rax+18h]
0x18001e720  call    cs:__imp_RoGetActivationFactory
0x18001e726  mov     ebx, eax
0x18001e728  test    eax, eax
0x18001e72a  js      loc_18001E7C8
0x18001e730  mov     [rbp+var_48], 0
0x18001e738  mov     rdi, [rbp+var_40]
0x18001e73c  mov     rax, [rdi]
0x18001e73f  mov     rbx, [rax+30h]
0x18001e743  lea     rcx, [rbp+var_48]
0x18001e747  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001e74c  lea     rdx, [rbp+var_48]
0x18001e750  mov     rcx, rdi
0x18001e753  mov     rax, rbx
0x18001e756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e75b  mov     ebx, eax
0x18001e75d  test    eax, eax
0x18001e75f  js      short loc_18001E7BE
0x18001e761  mov     [rbp+string], 0
0x18001e769  mov     rdi, [rbp+var_48]
0x18001e76d  mov     rax, [rdi]
0x18001e770  mov     rbx, [rax+30h]
0x18001e774  xor     ecx, ecx; string
0x18001e776  call    cs:__imp_WindowsDeleteString
0x18001e77c  mov     [rbp+string], 0
0x18001e784  lea     rdx, [rbp+string]
0x18001e788  mov     rcx, rdi
0x18001e78b  mov     rax, rbx
0x18001e78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e793  mov     ebx, eax
0x18001e795  test    eax, eax
0x18001e797  js      short loc_18001E7B3
0x18001e799  xor     edx, edx; length
0x18001e79b  mov     rcx, [rbp+string]; string
0x18001e79f  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e7a5  mov     rdx, rsi; ppwsz
0x18001e7a8  mov     rcx, rax; psz
0x18001e7ab  call    cs:__imp_SHStrDupW
0x18001e7b1  mov     ebx, eax
0x18001e7b3  mov     rcx, [rbp+string]; string
0x18001e7b7  call    cs:__imp_WindowsDeleteString
0x18001e7bd  nop
0x18001e7be  lea     rcx, [rbp+var_48]
0x18001e7c2  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001e7c7  nop
0x18001e7c8  lea     rcx, [rbp+var_40]
0x18001e7cc  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001e7d1  mov     eax, ebx
0x18001e7d3  mov     rcx, [rbp+var_10]
0x18001e7d7  xor     rcx, rsp; StackCookie
0x18001e7da  call    __security_check_cookie
0x18001e7df  add     rsp, 68h
0x18001e7e3  pop     rdi
0x18001e7e4  pop     rsi
0x18001e7e5  pop     rbx
0x18001e7e6  pop     rbp
0x18001e7e7  retn
```
