# GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)

- ea: `0x1800201b8`
- end: `0x1800202aa`
- name: `?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::ApplicationModel::Resources::Core::IResourceMap *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800202b0`

## callees

- `0x180009190`
- `0x18000cfa4`
- `0x1800149fc`
- `0x1800201b8`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002027c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002027c`

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
0x1800201b8  mov     [rsp-18h+arg_18], rbx
0x1800201bd  push    rbp
0x1800201be  push    rsi
0x1800201bf  push    rdi
0x1800201c0  mov     rbp, rsp
0x1800201c3  sub     rsp, 60h
0x1800201c7  mov     rax, cs:__security_cookie
0x1800201ce  xor     rax, rsp
0x1800201d1  mov     [rbp+var_8], rax
0x1800201d5  mov     rsi, r8
0x1800201d8  mov     rdi, rdx
0x1800201db  mov     [rbp+string], rcx
0x1800201df  mov     qword ptr [r8], 0
0x1800201e6  mov     [rbp+var_30], 0
0x1800201ee  mov     rax, [rdx]
0x1800201f1  mov     rbx, [rax+38h]
0x1800201f5  lea     rcx, [rbp+var_30]
0x1800201f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800201fe  lea     rdx, [rbp+string]
0x180020202  lea     rcx, [rbp+var_28]
0x180020206  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002020b  nop
0x18002020c  lea     r8, [rbp+var_30]
0x180020210  mov     rdx, [rax+18h]
0x180020214  mov     rcx, rdi
0x180020217  mov     rax, rbx
0x18002021a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002021f  mov     ebx, eax
0x180020221  test    eax, eax
0x180020223  js      short loc_180020283
0x180020225  mov     rbx, [rbp+var_30]
0x180020229  test    rbx, rbx
0x18002022c  jnz     short loc_180020235
0x18002022e  mov     ebx, 80070003h
0x180020233  jmp     short loc_180020283
0x180020235  mov     [rbp+string], 0
0x18002023d  mov     rax, [rbx]
0x180020240  mov     rdi, [rax+50h]
0x180020244  xor     ecx, ecx; string
0x180020246  call    cs:__imp_WindowsDeleteString
0x18002024c  mov     [rbp+string], 0
0x180020254  lea     rdx, [rbp+string]
0x180020258  mov     rcx, rbx
0x18002025b  mov     rax, rdi
0x18002025e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020263  mov     ebx, eax
0x180020265  test    eax, eax
0x180020267  js      short loc_180020278
0x180020269  mov     rax, [rbp+string]
0x18002026d  xor     ecx, ecx
0x18002026f  mov     [rbp+string], rcx
0x180020273  mov     [rsi], rax
0x180020276  jmp     short loc_18002027C
0x180020278  mov     rcx, [rbp+string]; string
0x18002027c  call    cs:__imp_WindowsDeleteString
0x180020282  nop
0x180020283  lea     rcx, [rbp+var_30]
0x180020287  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002028c  mov     eax, ebx
0x18002028e  mov     rcx, [rbp+var_8]
0x180020292  xor     rcx, rsp; StackCookie
0x180020295  call    __security_check_cookie
0x18002029a  mov     rbx, [rsp+60h+arg_18]
0x1800202a2  add     rsp, 60h
0x1800202a6  pop     rdi
0x1800202a7  pop     rsi
0x1800202a8  pop     rbp
0x1800202a9  retn
```
