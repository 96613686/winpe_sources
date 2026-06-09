# GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)

- ea: `0x1800135e0`
- end: `0x1800136df`
- name: `?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::ApplicationModel::Resources::Core::IResourceMap *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800136e8`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x18000c970`
- `0x1800135e0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001366e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800136aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001366e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800136aa`

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
0x1800135e0  mov     [rsp-18h+arg_18], rbx
0x1800135e5  push    rbp
0x1800135e6  push    rsi
0x1800135e7  push    rdi
0x1800135e8  mov     rbp, rsp
0x1800135eb  sub     rsp, 60h
0x1800135ef  mov     rax, cs:__security_cookie
0x1800135f6  xor     rax, rsp
0x1800135f9  mov     [rbp+var_8], rax
0x1800135fd  mov     rsi, r8
0x180013600  mov     rdi, rdx
0x180013603  mov     [rbp+string], rcx
0x180013607  mov     qword ptr [r8], 0
0x18001360e  mov     [rbp+var_30], 0
0x180013616  mov     rax, [rdx]
0x180013619  mov     rbx, [rax+38h]
0x18001361d  lea     rcx, [rbp+var_30]
0x180013621  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013626  lea     rdx, [rbp+string]
0x18001362a  lea     rcx, [rbp+var_28]
0x18001362e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180013633  nop
0x180013634  lea     r8, [rbp+var_30]
0x180013638  mov     rdx, [rax+18h]
0x18001363c  mov     rcx, rdi
0x18001363f  mov     rax, rbx
0x180013642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013647  mov     ebx, eax
0x180013649  test    eax, eax
0x18001364b  js      short loc_1800136B7
0x18001364d  mov     rbx, [rbp+var_30]
0x180013651  test    rbx, rbx
0x180013654  jnz     short loc_18001365D
0x180013656  mov     ebx, 80070003h
0x18001365b  jmp     short loc_1800136B7
0x18001365d  mov     [rbp+string], 0
0x180013665  mov     rax, [rbx]
0x180013668  mov     rdi, [rax+50h]
0x18001366c  xor     ecx, ecx; string
0x18001366e  call    cs:__imp_WindowsDeleteString
0x180013675  nop     dword ptr [rax+rax+00h]
0x18001367a  mov     [rbp+string], 0
0x180013682  lea     rdx, [rbp+string]
0x180013686  mov     rcx, rbx
0x180013689  mov     rax, rdi
0x18001368c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013691  mov     ebx, eax
0x180013693  test    eax, eax
0x180013695  js      short loc_1800136A6
0x180013697  mov     rax, [rbp+string]
0x18001369b  xor     ecx, ecx
0x18001369d  mov     [rbp+string], rcx
0x1800136a1  mov     [rsi], rax
0x1800136a4  jmp     short loc_1800136AA
0x1800136a6  mov     rcx, [rbp+string]; string
0x1800136aa  call    cs:__imp_WindowsDeleteString
0x1800136b1  nop     dword ptr [rax+rax+00h]
0x1800136b6  nop
0x1800136b7  lea     rcx, [rbp+var_30]
0x1800136bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800136c0  mov     eax, ebx
0x1800136c2  mov     rcx, [rbp+var_8]
0x1800136c6  xor     rcx, rsp; StackCookie
0x1800136c9  call    __security_check_cookie
0x1800136ce  mov     rbx, [rsp+60h+arg_18]
0x1800136d6  add     rsp, 60h
0x1800136da  pop     rdi
0x1800136db  pop     rsi
0x1800136dc  pop     rbp
0x1800136dd  retn
```
