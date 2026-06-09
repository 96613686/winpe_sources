# UtilElevatedManagerAutoElevated::IsNetworkRequiredForAutoPilot(uchar *)

- ea: `0x180049d10`
- end: `0x180049dbe`
- name: `?IsNetworkRequiredForAutoPilot@UtilElevatedManagerAutoElevated@@UEAAJPEAE@Z`
- size: `174`
- prototype: `__int64 __fastcall(UtilElevatedManagerAutoElevated *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000fa5c`
- `0x1800153f8`
- `0x18001a540`
- `0x180049d10`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180049d5d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180049d5d`

## string_xrefs

- `0x180049d71`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\utilelevatedmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilElevatedManagerAutoElevated::IsNetworkRequiredForAutoPilot(
        UtilElevatedManagerAutoElevated *this,
        unsigned __int8 *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int ppv; // [rsp+20h] [rbp-28h]
  LPVOID v7; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v7 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v7);
  v3 = CoCreateInstance(
         &GUID_3a965ed4_0e14_4a1b_a71e_972f1c1044f6,
         0,
         1u,
         &GUID_eb1c9fb1_d906_4559_b474_0de6d3ad9e7b,
         &v7);
  v4 = v3;
  if ( v3 >= 0 )
    v4 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int8 *))(*(_QWORD *)v7 + 72LL))(v7, a2);
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\utilelevatedmanager.cpp",
      (const char *)(unsigned int)v3,
      ppv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v7);
  return v4;
}

```

## disassembly

```asm
0x180049d10  mov     [rsp+arg_0], rbx
0x180049d15  push    rdi
0x180049d16  sub     rsp, 40h
0x180049d1a  mov     rax, cs:__security_cookie
0x180049d21  xor     rax, rsp
0x180049d24  mov     [rsp+48h+var_10], rax
0x180049d29  mov     rdi, rdx
0x180049d2c  mov     [rsp+48h+var_18], 0
0x180049d35  lea     rcx, [rsp+48h+var_18]
0x180049d3a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049d3f  lea     rax, [rsp+48h+var_18]
0x180049d44  mov     qword ptr [rsp+48h+ppv], rax; int
0x180049d49  lea     r9, _GUID_eb1c9fb1_d906_4559_b474_0de6d3ad9e7b; riid
0x180049d50  xor     edx, edx; pUnkOuter
0x180049d52  lea     r8d, [rdx+1]; dwClsContext
0x180049d56  lea     rcx, _GUID_3a965ed4_0e14_4a1b_a71e_972f1c1044f6; rclsid
0x180049d5d  call    cs:__imp_CoCreateInstance
0x180049d63  mov     ebx, eax
0x180049d65  test    eax, eax
0x180049d67  jns     short loc_180049D84
0x180049d69  mov     rcx, [rsp+48h]; this
0x180049d6e  mov     r9d, eax; char *
0x180049d71  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudexperiencehost"...
0x180049d78  mov     edx, 7Eh ; '~'; void *
0x180049d7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049d82  jmp     short loc_180049D9A
0x180049d84  mov     rcx, [rsp+48h+var_18]
0x180049d89  mov     rax, [rcx]
0x180049d8c  mov     rdx, rdi
0x180049d8f  mov     rax, [rax+48h]
0x180049d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d98  mov     ebx, eax
0x180049d9a  lea     rcx, [rsp+48h+var_18]
0x180049d9f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049da4  mov     eax, ebx
0x180049da6  mov     rcx, [rsp+48h+var_10]
0x180049dab  xor     rcx, rsp; StackCookie
0x180049dae  call    __security_check_cookie
0x180049db3  mov     rbx, [rsp+48h+arg_0]
0x180049db8  add     rsp, 40h
0x180049dbc  pop     rdi
0x180049dbd  retn
```
