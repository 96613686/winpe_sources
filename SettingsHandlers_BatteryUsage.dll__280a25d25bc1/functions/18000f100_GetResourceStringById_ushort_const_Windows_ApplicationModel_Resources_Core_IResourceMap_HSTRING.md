# GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)

- ea: `0x18000f100`
- end: `0x18000f1f2`
- name: `?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::ApplicationModel::Resources::Core::IResourceMap *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000f1f8`

## callees

- `0x1800028d0`
- `0x180004cfc`
- `0x18000c990`
- `0x18000f100`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f18e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f1c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f18e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f1c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetResourceStringById(
        const unsigned __int16 *a1,
        struct Windows::ApplicationModel::Resources::Core::IResourceMap *a2,
        HSTRING *a3)
{
  __int64 (__fastcall *v5)(struct Windows::ApplicationModel::Resources::Core::IResourceMap *, _QWORD, __int64 *); // rbx
  __int64 v6; // rax
  int v7; // ebx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rdi
  HSTRING v10; // rax
  HSTRING v11; // rcx
  HSTRING string[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v14; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v15[32]; // [rsp+38h] [rbp-28h] BYREF

  string[0] = (HSTRING)a1;
  *a3 = 0;
  v14 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::IResourceMap *, _QWORD, __int64 *))(*(_QWORD *)a2 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v15, string);
  v7 = v5(a2, *(_QWORD *)(v6 + 24), &v14);
  if ( v7 >= 0 )
  {
    v8 = v14;
    if ( v14 )
    {
      string[0] = 0;
      v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 80LL);
      WindowsDeleteString(0);
      string[0] = 0;
      v7 = v9(v8, string);
      if ( v7 < 0 )
      {
        v11 = string[0];
      }
      else
      {
        v10 = string[0];
        v11 = 0;
        string[0] = 0;
        *a3 = v10;
      }
      WindowsDeleteString(v11);
    }
    else
    {
      v7 = -2147024893;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000f100  mov     [rsp-18h+arg_18], rbx
0x18000f105  push    rbp
0x18000f106  push    rsi
0x18000f107  push    rdi
0x18000f108  mov     rbp, rsp
0x18000f10b  sub     rsp, 60h
0x18000f10f  mov     rax, cs:__security_cookie
0x18000f116  xor     rax, rsp
0x18000f119  mov     [rbp+var_8], rax
0x18000f11d  mov     rsi, r8
0x18000f120  mov     rdi, rdx
0x18000f123  mov     [rbp+string], rcx
0x18000f127  mov     qword ptr [r8], 0
0x18000f12e  mov     [rbp+var_30], 0
0x18000f136  mov     rax, [rdx]
0x18000f139  mov     rbx, [rax+38h]
0x18000f13d  lea     rcx, [rbp+var_30]
0x18000f141  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f146  lea     rdx, [rbp+string]
0x18000f14a  lea     rcx, [rbp+var_28]
0x18000f14e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000f153  nop
0x18000f154  lea     r8, [rbp+var_30]
0x18000f158  mov     rdx, [rax+18h]
0x18000f15c  mov     rcx, rdi
0x18000f15f  mov     rax, rbx
0x18000f162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f167  mov     ebx, eax
0x18000f169  test    eax, eax
0x18000f16b  js      short loc_18000F1CB
0x18000f16d  mov     rbx, [rbp+var_30]
0x18000f171  test    rbx, rbx
0x18000f174  jnz     short loc_18000F17D
0x18000f176  mov     ebx, 80070003h
0x18000f17b  jmp     short loc_18000F1CB
0x18000f17d  mov     [rbp+string], 0
0x18000f185  mov     rax, [rbx]
0x18000f188  mov     rdi, [rax+50h]
0x18000f18c  xor     ecx, ecx; string
0x18000f18e  call    cs:__imp_WindowsDeleteString
0x18000f194  mov     [rbp+string], 0
0x18000f19c  lea     rdx, [rbp+string]
0x18000f1a0  mov     rcx, rbx
0x18000f1a3  mov     rax, rdi
0x18000f1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1ab  mov     ebx, eax
0x18000f1ad  test    eax, eax
0x18000f1af  js      short loc_18000F1C0
0x18000f1b1  mov     rax, [rbp+string]
0x18000f1b5  xor     ecx, ecx
0x18000f1b7  mov     [rbp+string], rcx
0x18000f1bb  mov     [rsi], rax
0x18000f1be  jmp     short loc_18000F1C4
0x18000f1c0  mov     rcx, [rbp+string]; string
0x18000f1c4  call    cs:__imp_WindowsDeleteString
0x18000f1ca  nop
0x18000f1cb  lea     rcx, [rbp+var_30]
0x18000f1cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f1d4  mov     eax, ebx
0x18000f1d6  mov     rcx, [rbp+var_8]
0x18000f1da  xor     rcx, rsp; StackCookie
0x18000f1dd  call    __security_check_cookie
0x18000f1e2  mov     rbx, [rsp+60h+arg_18]
0x18000f1ea  add     rsp, 60h
0x18000f1ee  pop     rdi
0x18000f1ef  pop     rsi
0x18000f1f0  pop     rbp
0x18000f1f1  retn
```
