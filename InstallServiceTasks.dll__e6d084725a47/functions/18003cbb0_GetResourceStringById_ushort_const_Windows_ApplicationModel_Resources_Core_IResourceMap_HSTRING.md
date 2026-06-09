# GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)

- ea: `0x18003cbb0`
- end: `0x18003cca2`
- name: `?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::ApplicationModel::Resources::Core::IResourceMap *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003cca8`

## callees

- `0x180003450`
- `0x18000760c`
- `0x18000b48c`
- `0x18003cbb0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cc3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cc74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cc3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cc74`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetResourceStringById(
        const unsigned __int16 *a1,
        struct Windows::ApplicationModel::Resources::Core::IResourceMap *a2,
        HSTRING *a3)
{
  __int64 (__fastcall *v5)(struct Windows::ApplicationModel::Resources::Core::IResourceMap *, PVOID, __int64 *); // rbx
  char v6; // r8
  HSTRING_HEADER *v7; // rax
  int v8; // ebx
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rdi
  HSTRING v11; // rax
  HSTRING v12; // rcx
  HSTRING string[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v15; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER v16; // [rsp+38h] [rbp-28h] BYREF

  string[0] = (HSTRING)a1;
  *a3 = 0;
  v15 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::IResourceMap *, PVOID, __int64 *))(*(_QWORD *)a2 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v16, (const WCHAR **)string, v6);
  v8 = v5(a2, v7[1].Reserved.Reserved1, &v15);
  if ( v8 >= 0 )
  {
    v9 = v15;
    if ( v15 )
    {
      string[0] = 0;
      v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 80LL);
      WindowsDeleteString(0);
      string[0] = 0;
      v8 = v10(v9, string);
      if ( v8 < 0 )
      {
        v12 = string[0];
      }
      else
      {
        v11 = string[0];
        v12 = 0;
        string[0] = 0;
        *a3 = v11;
      }
      WindowsDeleteString(v12);
    }
    else
    {
      v8 = -2147024893;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003cbb0  mov     [rsp-18h+arg_18], rbx
0x18003cbb5  push    rbp
0x18003cbb6  push    rsi
0x18003cbb7  push    rdi
0x18003cbb8  mov     rbp, rsp
0x18003cbbb  sub     rsp, 60h
0x18003cbbf  mov     rax, cs:__security_cookie
0x18003cbc6  xor     rax, rsp
0x18003cbc9  mov     [rbp+var_8], rax
0x18003cbcd  mov     rsi, r8
0x18003cbd0  mov     rdi, rdx
0x18003cbd3  mov     [rbp+string], rcx
0x18003cbd7  mov     qword ptr [r8], 0
0x18003cbde  mov     [rbp+var_30], 0
0x18003cbe6  mov     rax, [rdx]
0x18003cbe9  mov     rbx, [rax+38h]
0x18003cbed  lea     rcx, [rbp+var_30]
0x18003cbf1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003cbf6  lea     rdx, [rbp+string]
0x18003cbfa  lea     rcx, [rbp+var_28]
0x18003cbfe  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003cc03  nop
0x18003cc04  lea     r8, [rbp+var_30]
0x18003cc08  mov     rdx, [rax+18h]
0x18003cc0c  mov     rcx, rdi
0x18003cc0f  mov     rax, rbx
0x18003cc12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc17  mov     ebx, eax
0x18003cc19  test    eax, eax
0x18003cc1b  js      short loc_18003CC7B
0x18003cc1d  mov     rbx, [rbp+var_30]
0x18003cc21  test    rbx, rbx
0x18003cc24  jnz     short loc_18003CC2D
0x18003cc26  mov     ebx, 80070003h
0x18003cc2b  jmp     short loc_18003CC7B
0x18003cc2d  mov     [rbp+string], 0
0x18003cc35  mov     rax, [rbx]
0x18003cc38  mov     rdi, [rax+50h]
0x18003cc3c  xor     ecx, ecx; string
0x18003cc3e  call    cs:__imp_WindowsDeleteString
0x18003cc44  mov     [rbp+string], 0
0x18003cc4c  lea     rdx, [rbp+string]
0x18003cc50  mov     rcx, rbx
0x18003cc53  mov     rax, rdi
0x18003cc56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc5b  mov     ebx, eax
0x18003cc5d  test    eax, eax
0x18003cc5f  js      short loc_18003CC70
0x18003cc61  mov     rax, [rbp+string]
0x18003cc65  xor     ecx, ecx
0x18003cc67  mov     [rbp+string], rcx
0x18003cc6b  mov     [rsi], rax
0x18003cc6e  jmp     short loc_18003CC74
0x18003cc70  mov     rcx, [rbp+string]; string
0x18003cc74  call    cs:__imp_WindowsDeleteString
0x18003cc7a  nop
0x18003cc7b  lea     rcx, [rbp+var_30]
0x18003cc7f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003cc84  mov     eax, ebx
0x18003cc86  mov     rcx, [rbp+var_8]
0x18003cc8a  xor     rcx, rsp; StackCookie
0x18003cc8d  call    __security_check_cookie
0x18003cc92  mov     rbx, [rsp+60h+arg_18]
0x18003cc9a  add     rsp, 60h
0x18003cc9e  pop     rdi
0x18003cc9f  pop     rsi
0x18003cca0  pop     rbp
0x18003cca1  retn
```
