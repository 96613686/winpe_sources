# StoreAppFinder::GetManifestReaderFromManifestPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,IAppxManifestReader * *)

- ea: `0x18003dacc`
- end: `0x18003dc76`
- name: `?GetManifestReaderFromManifestPath@StoreAppFinder@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIAppxManifestReader@@@Z`
- size: `426`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d72c`
- `0x18003d918`
- `0x18003e66c`

## callees

- `0x18000a39c`
- `0x18003dacc`
- `0x1800679f8`
- `0x180130010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003db15`
- `ole32!CoCreateInstance` at `0x18003db5d`
- `ole32!CoCreateInstance` at `0x18003db15`
- `ole32!CoCreateInstance` at `0x18003db5d`

## string_xrefs

- `0x18003db26`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003db6e`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003dbd7`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x18003dc0b`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall StoreAppFinder::GetManifestReaderFromManifestPath(_QWORD *a1, __int64 a2)
{
  HRESULT Instance; // eax
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
  LPVOID v15[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v17; // [rsp+80h] [rbp+30h] BYREF
  LPVOID v18; // [rsp+88h] [rbp+38h] BYREF

  v15[1] = (LPVOID)-2LL;
  v15[0] = 0;
  Instance = CoCreateInstance(
               &GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781,
               0,
               1u,
               &GUID_beb94909_e451_438b_b5a7_d79e767b75d8,
               v15);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2F0,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
      (const char *)(unsigned int)Instance,
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
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
      (const char *)(unsigned int)v5,
      ppva);
  v17 = 0;
  v6 = v18;
  v7 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64))(*(_QWORD *)v18 + 40LL);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v17);
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  v8 = v7(v6, a1, 1);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2FD,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
      (const char *)(unsigned int)v8,
      128);
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v15[0] + 40LL))(v15[0], v17, a2);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2FF,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
      (const char *)(unsigned int)v9,
      128);
  result = Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v17);
  v11 = v18;
  if ( v18 )
  {
    v18 = 0;
    result = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = v15[0];
  if ( v15[0] )
  {
    v15[0] = 0;
    return (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return result;
}

```

## disassembly

```asm
0x18003dacc  push    rbp
0x18003dace  push    rdi
0x18003dacf  push    r14
0x18003dad1  mov     rbp, rsp
0x18003dad4  sub     rsp, 50h
0x18003dad8  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x18003dae0  mov     [rsp+50h+arg_0], rbx
0x18003dae5  mov     [rsp+50h+arg_8], rsi
0x18003daea  mov     r14, rdx
0x18003daed  mov     rbx, rcx
0x18003daf0  mov     [rbp+var_10], 0
0x18003daf8  lea     rax, [rbp+var_10]
0x18003dafc  mov     [rsp+50h+ppv], rax; int
0x18003db01  lea     r9, _GUID_beb94909_e451_438b_b5a7_d79e767b75d8; riid
0x18003db08  xor     edx, edx; pUnkOuter
0x18003db0a  lea     r8d, [rdx+1]; dwClsContext
0x18003db0e  lea     rcx, _GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781; rclsid
0x18003db15  call    cs:__imp_CoCreateInstance
0x18003db1b  mov     rcx, [rbp+18h]; this
0x18003db1f  test    eax, eax
0x18003db21  jns     short loc_18003DB38
0x18003db23  mov     r9d, eax; char *
0x18003db26  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18003db2d  mov     edx, 2F0h; void *
0x18003db32  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003db38  mov     [rbp+arg_18], 0
0x18003db40  lea     rax, [rbp+arg_18]
0x18003db44  mov     [rsp+50h+ppv], rax; int
0x18003db49  lea     r9, _GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154; riid
0x18003db50  xor     edx, edx; pUnkOuter
0x18003db52  lea     r8d, [rdx+1]; dwClsContext
0x18003db56  lea     rcx, _GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e; rclsid
0x18003db5d  call    cs:__imp_CoCreateInstance
0x18003db63  mov     rcx, [rbp+18h]; this
0x18003db67  test    eax, eax
0x18003db69  jns     short loc_18003DB80
0x18003db6b  mov     r9d, eax; char *
0x18003db6e  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18003db75  mov     edx, 2F6h; void *
0x18003db7a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003db80  mov     [rbp+arg_10], 0
0x18003db88  mov     rdi, [rbp+arg_18]
0x18003db8c  mov     rax, [rdi]
0x18003db8f  mov     rsi, [rax+28h]
0x18003db93  lea     rcx, [rbp+arg_10]
0x18003db97  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18003db9c  cmp     qword ptr [rbx+18h], 7
0x18003dba1  jbe     short loc_18003DBA6
0x18003dba3  mov     rbx, [rbx]
0x18003dba6  lea     rax, [rbp+arg_10]
0x18003dbaa  mov     [rsp+50h+var_28], rax
0x18003dbaf  mov     dword ptr [rsp+50h+ppv], 80h; int
0x18003dbb7  xor     r9d, r9d
0x18003dbba  lea     r8d, [r9+1]
0x18003dbbe  mov     rdx, rbx
0x18003dbc1  mov     rcx, rdi
0x18003dbc4  mov     rax, rsi
0x18003dbc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbcc  mov     rcx, [rbp+18h]; this
0x18003dbd0  test    eax, eax
0x18003dbd2  jns     short loc_18003DBE9
0x18003dbd4  mov     r9d, eax; char *
0x18003dbd7  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18003dbde  mov     edx, 2FDh; void *
0x18003dbe3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003dbe9  mov     rcx, [rbp+var_10]
0x18003dbed  mov     rax, [rcx]
0x18003dbf0  mov     r8, r14
0x18003dbf3  mov     rdx, [rbp+arg_10]
0x18003dbf7  mov     rax, [rax+28h]
0x18003dbfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc00  mov     rcx, [rbp+18h]; this
0x18003dc04  test    eax, eax
0x18003dc06  jns     short loc_18003DC1D
0x18003dc08  mov     r9d, eax; char *
0x18003dc0b  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18003dc12  mov     edx, 2FFh; void *
0x18003dc17  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003dc1d  lea     rcx, [rbp+arg_10]
0x18003dc21  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18003dc26  nop
0x18003dc27  mov     rcx, [rbp+arg_18]
0x18003dc2b  test    rcx, rcx
0x18003dc2e  jz      short loc_18003DC45
0x18003dc30  mov     [rbp+arg_18], 0
0x18003dc38  mov     rax, [rcx]
0x18003dc3b  mov     rax, [rax+10h]
0x18003dc3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc44  nop
0x18003dc45  mov     rcx, [rbp+var_10]
0x18003dc49  test    rcx, rcx
0x18003dc4c  jz      short loc_18003DC63
0x18003dc4e  mov     [rbp+var_10], 0
0x18003dc56  mov     rax, [rcx]
0x18003dc59  mov     rax, [rax+10h]
0x18003dc5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc62  nop
0x18003dc63  mov     rbx, [rsp+50h+arg_0]
0x18003dc68  mov     rsi, [rsp+50h+arg_8]
0x18003dc6d  add     rsp, 50h
0x18003dc71  pop     r14
0x18003dc73  pop     rdi
0x18003dc74  pop     rbp
0x18003dc75  retn
```
