# GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)

- ea: `0x14003c7a0`
- end: `0x14003c892`
- name: `?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::ApplicationModel::Resources::Core::IResourceMap *, HSTRING *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003c470`
- `0x14003c760`

## callees

- `0x140005f30`
- `0x140006d2c`
- `0x14001a2a0`
- `0x14003c7a0`
- `0x14007d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003c82e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003c864`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003c82e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003c864`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetResourceStringById(
        unsigned __int16 *a1,
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
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  __int64 v14; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v15[32]; // [rsp+30h] [rbp-30h] BYREF

  string = (HSTRING)a1;
  *a3 = 0;
  v14 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::IResourceMap *, _QWORD, __int64 *))(*(_QWORD *)a2 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v15, &string);
  v7 = v5(a2, *(_QWORD *)(v6 + 24), &v14);
  if ( v7 >= 0 )
  {
    v8 = v14;
    if ( v14 )
    {
      string = 0;
      v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 80LL);
      WindowsDeleteString(0);
      string = 0;
      v7 = v9(v8, &string);
      if ( v7 < 0 )
      {
        v11 = string;
      }
      else
      {
        v10 = string;
        v11 = 0;
        string = 0;
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
0x14003c7a0  mov     [rsp-18h+arg_18], rbx
0x14003c7a5  push    rbp
0x14003c7a6  push    rsi
0x14003c7a7  push    rdi
0x14003c7a8  mov     rbp, rsp
0x14003c7ab  sub     rsp, 60h
0x14003c7af  mov     rax, cs:__security_cookie
0x14003c7b6  xor     rax, rsp
0x14003c7b9  mov     [rbp+var_10], rax
0x14003c7bd  mov     rsi, r8
0x14003c7c0  mov     rdi, rdx
0x14003c7c3  mov     [rbp+string], rcx
0x14003c7c7  mov     qword ptr [r8], 0
0x14003c7ce  mov     [rbp+var_38], 0
0x14003c7d6  mov     rax, [rdx]
0x14003c7d9  mov     rbx, [rax+38h]
0x14003c7dd  lea     rcx, [rbp+var_38]
0x14003c7e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003c7e6  lea     rdx, [rbp+string]
0x14003c7ea  lea     rcx, [rbp+var_30]
0x14003c7ee  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14003c7f3  nop
0x14003c7f4  lea     r8, [rbp+var_38]
0x14003c7f8  mov     rdx, [rax+18h]
0x14003c7fc  mov     rcx, rdi
0x14003c7ff  mov     rax, rbx
0x14003c802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c807  mov     ebx, eax
0x14003c809  test    eax, eax
0x14003c80b  js      short loc_14003C86B
0x14003c80d  mov     rbx, [rbp+var_38]
0x14003c811  test    rbx, rbx
0x14003c814  jnz     short loc_14003C81D
0x14003c816  mov     ebx, 80070003h
0x14003c81b  jmp     short loc_14003C86B
0x14003c81d  mov     [rbp+string], 0
0x14003c825  mov     rax, [rbx]
0x14003c828  mov     rdi, [rax+50h]
0x14003c82c  xor     ecx, ecx; string
0x14003c82e  call    cs:__imp_WindowsDeleteString
0x14003c834  mov     [rbp+string], 0
0x14003c83c  lea     rdx, [rbp+string]
0x14003c840  mov     rcx, rbx
0x14003c843  mov     rax, rdi
0x14003c846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c84b  mov     ebx, eax
0x14003c84d  test    eax, eax
0x14003c84f  js      short loc_14003C860
0x14003c851  mov     rax, [rbp+string]
0x14003c855  xor     ecx, ecx
0x14003c857  mov     [rbp+string], rcx
0x14003c85b  mov     [rsi], rax
0x14003c85e  jmp     short loc_14003C864
0x14003c860  mov     rcx, [rbp+string]; string
0x14003c864  call    cs:__imp_WindowsDeleteString
0x14003c86a  nop
0x14003c86b  lea     rcx, [rbp+var_38]
0x14003c86f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003c874  mov     eax, ebx
0x14003c876  mov     rcx, [rbp+var_10]
0x14003c87a  xor     rcx, rsp; StackCookie
0x14003c87d  call    __security_check_cookie
0x14003c882  mov     rbx, [rsp+60h+arg_18]
0x14003c88a  add     rsp, 60h
0x14003c88e  pop     rdi
0x14003c88f  pop     rsi
0x14003c890  pop     rbp
0x14003c891  retn
```
