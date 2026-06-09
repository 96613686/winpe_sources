# StoreAppFinder::GetManifestReaderFromManifestPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,IAppxManifestReader * *)

- ea: `0x1800d7c74`
- end: `0x1800d7e15`
- name: `?GetManifestReaderFromManifestPath@StoreAppFinder@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIAppxManifestReader@@@Z`
- size: `417`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c8770`
- `0x1800d6c60`
- `0x1800d6e0c`
- `0x1800d6fec`

## callees

- `0x18000a2d4`
- `0x1800c97f0`
- `0x1800d7c74`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d7cb4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d7cfc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d7cb4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d7cfc`

## string_xrefs

- `0x1800d7cc5`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7d0d`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7d76`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7daa`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall StoreAppFinder::GetManifestReaderFromManifestPath(_QWORD *a1, __int64 a2)
{
  HRESULT v4; // eax
  HRESULT v5; // eax
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, _QWORD *, __int64); // rsi
  int v8; // eax
  int v9; // eax
  __int64 result; // rax
  LPVOID v11; // rcx
  LPVOID v12; // rcx
  int ppv; // [rsp+20h] [rbp-30h]
  int ppva; // [rsp+20h] [rbp-30h]
  LPVOID v15; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v17; // [rsp+80h] [rbp+30h] BYREF
  LPVOID v18; // [rsp+88h] [rbp+38h] BYREF

  v15 = 0;
  v4 = CoCreateInstance(
         &GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781,
         0,
         1u,
         &GUID_beb94909_e451_438b_b5a7_d79e767b75d8,
         &v15);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2F0,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  v18 = 0;
  v5 = CoCreateInstance(
         &GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e,
         0,
         1u,
         &GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154,
         &v18);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2F6,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v5,
      ppva);
  v17 = 0;
  v6 = v18;
  v7 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64))(*(_QWORD *)v18 + 40LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  v8 = v7(v6, a1, 1);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2FD,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v8,
      128);
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v15 + 40LL))(v15, v17, a2);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2FF,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v9,
      128);
  result = Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v11 = v18;
  if ( v18 )
  {
    v18 = 0;
    result = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = v15;
  if ( v15 )
  {
    v15 = 0;
    return (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800d7c74  mov     [rsp-18h+arg_0], rbx
0x1800d7c79  mov     [rsp-18h+arg_8], rsi
0x1800d7c7e  push    rbp
0x1800d7c7f  push    rdi
0x1800d7c80  push    r14
0x1800d7c82  mov     rbp, rsp
0x1800d7c85  sub     rsp, 50h
0x1800d7c89  mov     r14, rdx
0x1800d7c8c  mov     rbx, rcx
0x1800d7c8f  mov     [rbp+var_10], 0
0x1800d7c97  lea     rax, [rbp+var_10]
0x1800d7c9b  mov     [rsp+50h+ppv], rax; int
0x1800d7ca0  lea     r9, _GUID_beb94909_e451_438b_b5a7_d79e767b75d8; riid
0x1800d7ca7  xor     edx, edx; pUnkOuter
0x1800d7ca9  lea     r8d, [rdx+1]; dwClsContext
0x1800d7cad  lea     rcx, _GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781; rclsid
0x1800d7cb4  call    cs:__imp_CoCreateInstance
0x1800d7cba  mov     rcx, [rbp+18h]; this
0x1800d7cbe  test    eax, eax
0x1800d7cc0  jns     short loc_1800D7CD7
0x1800d7cc2  mov     r9d, eax; char *
0x1800d7cc5  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d7ccc  mov     edx, 2F0h; void *
0x1800d7cd1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d7cd7  mov     [rbp+arg_18], 0
0x1800d7cdf  lea     rax, [rbp+arg_18]
0x1800d7ce3  mov     [rsp+50h+ppv], rax; int
0x1800d7ce8  lea     r9, _GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154; riid
0x1800d7cef  xor     edx, edx; pUnkOuter
0x1800d7cf1  lea     r8d, [rdx+1]; dwClsContext
0x1800d7cf5  lea     rcx, _GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e; rclsid
0x1800d7cfc  call    cs:__imp_CoCreateInstance
0x1800d7d02  mov     rcx, [rbp+18h]; this
0x1800d7d06  test    eax, eax
0x1800d7d08  jns     short loc_1800D7D1F
0x1800d7d0a  mov     r9d, eax; char *
0x1800d7d0d  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d7d14  mov     edx, 2F6h; void *
0x1800d7d19  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d7d1f  mov     [rbp+arg_10], 0
0x1800d7d27  mov     rdi, [rbp+arg_18]
0x1800d7d2b  mov     rax, [rdi]
0x1800d7d2e  mov     rsi, [rax+28h]
0x1800d7d32  lea     rcx, [rbp+arg_10]
0x1800d7d36  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d7d3b  cmp     qword ptr [rbx+18h], 7
0x1800d7d40  jbe     short loc_1800D7D45
0x1800d7d42  mov     rbx, [rbx]
0x1800d7d45  lea     rax, [rbp+arg_10]
0x1800d7d49  mov     [rsp+50h+var_28], rax
0x1800d7d4e  mov     dword ptr [rsp+50h+ppv], 80h; int
0x1800d7d56  xor     r9d, r9d
0x1800d7d59  lea     r8d, [r9+1]
0x1800d7d5d  mov     rdx, rbx
0x1800d7d60  mov     rcx, rdi
0x1800d7d63  mov     rax, rsi
0x1800d7d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7d6b  mov     rcx, [rbp+18h]; this
0x1800d7d6f  test    eax, eax
0x1800d7d71  jns     short loc_1800D7D88
0x1800d7d73  mov     r9d, eax; char *
0x1800d7d76  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d7d7d  mov     edx, 2FDh; void *
0x1800d7d82  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d7d88  mov     rcx, [rbp+var_10]
0x1800d7d8c  mov     rax, [rcx]
0x1800d7d8f  mov     r8, r14
0x1800d7d92  mov     rdx, [rbp+arg_10]
0x1800d7d96  mov     rax, [rax+28h]
0x1800d7d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7d9f  mov     rcx, [rbp+18h]; this
0x1800d7da3  test    eax, eax
0x1800d7da5  jns     short loc_1800D7DBC
0x1800d7da7  mov     r9d, eax; char *
0x1800d7daa  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d7db1  mov     edx, 2FFh; void *
0x1800d7db6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d7dbc  lea     rcx, [rbp+arg_10]
0x1800d7dc0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d7dc5  nop
0x1800d7dc6  mov     rcx, [rbp+arg_18]
0x1800d7dca  test    rcx, rcx
0x1800d7dcd  jz      short loc_1800D7DE4
0x1800d7dcf  mov     [rbp+arg_18], 0
0x1800d7dd7  mov     rax, [rcx]
0x1800d7dda  mov     rax, [rax+10h]
0x1800d7dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7de3  nop
0x1800d7de4  mov     rcx, [rbp+var_10]
0x1800d7de8  test    rcx, rcx
0x1800d7deb  jz      short loc_1800D7E02
0x1800d7ded  mov     [rbp+var_10], 0
0x1800d7df5  mov     rax, [rcx]
0x1800d7df8  mov     rax, [rax+10h]
0x1800d7dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7e01  nop
0x1800d7e02  mov     rbx, [rsp+50h+arg_0]
0x1800d7e07  mov     rsi, [rsp+50h+arg_8]
0x1800d7e0c  add     rsp, 50h
0x1800d7e10  pop     r14
0x1800d7e12  pop     rdi
0x1800d7e13  pop     rbp
0x1800d7e14  retn
```
