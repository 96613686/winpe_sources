# StoreApplication::GetStoreAppManifestReaderFromManifestPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,IAppxManifestReader * *)

- ea: `0x1800580fc`
- end: `0x1800582a6`
- name: `?GetStoreAppManifestReaderFromManifestPath@StoreApplication@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIAppxManifestReader@@@Z`
- size: `426`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004f010`
- `0x180057e28`

## callees

- `0x18000a39c`
- `0x1800580fc`
- `0x1800679f8`
- `0x180130010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180058145`
- `ole32!CoCreateInstance` at `0x18005818d`
- `ole32!CoCreateInstance` at `0x180058145`
- `ole32!CoCreateInstance` at `0x18005818d`

## string_xrefs

- `0x180058156`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18005819e`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180058207`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18005823b`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall StoreApplication::GetStoreAppManifestReaderFromManifestPath(_QWORD *a1, __int64 a2)
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
      (void *)0x613,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
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
      (void *)0x619,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
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
      (void *)0x620,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v8,
      128);
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v15[0] + 40LL))(v15[0], v17, a2);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x622,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
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
0x1800580fc  push    rbp
0x1800580fe  push    rdi
0x1800580ff  push    r14
0x180058101  mov     rbp, rsp
0x180058104  sub     rsp, 50h
0x180058108  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x180058110  mov     [rsp+50h+arg_0], rbx
0x180058115  mov     [rsp+50h+arg_8], rsi
0x18005811a  mov     r14, rdx
0x18005811d  mov     rbx, rcx
0x180058120  mov     [rbp+var_10], 0
0x180058128  lea     rax, [rbp+var_10]
0x18005812c  mov     [rsp+50h+ppv], rax; int
0x180058131  lea     r9, _GUID_beb94909_e451_438b_b5a7_d79e767b75d8; riid
0x180058138  xor     edx, edx; pUnkOuter
0x18005813a  lea     r8d, [rdx+1]; dwClsContext
0x18005813e  lea     rcx, _GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781; rclsid
0x180058145  call    cs:__imp_CoCreateInstance
0x18005814b  mov     rcx, [rbp+18h]; this
0x18005814f  test    eax, eax
0x180058151  jns     short loc_180058168
0x180058153  mov     r9d, eax; char *
0x180058156  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18005815d  mov     edx, 613h; void *
0x180058162  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180058168  mov     [rbp+arg_18], 0
0x180058170  lea     rax, [rbp+arg_18]
0x180058174  mov     [rsp+50h+ppv], rax; int
0x180058179  lea     r9, _GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154; riid
0x180058180  xor     edx, edx; pUnkOuter
0x180058182  lea     r8d, [rdx+1]; dwClsContext
0x180058186  lea     rcx, _GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e; rclsid
0x18005818d  call    cs:__imp_CoCreateInstance
0x180058193  mov     rcx, [rbp+18h]; this
0x180058197  test    eax, eax
0x180058199  jns     short loc_1800581B0
0x18005819b  mov     r9d, eax; char *
0x18005819e  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x1800581a5  mov     edx, 619h; void *
0x1800581aa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800581b0  mov     [rbp+arg_10], 0
0x1800581b8  mov     rdi, [rbp+arg_18]
0x1800581bc  mov     rax, [rdi]
0x1800581bf  mov     rsi, [rax+28h]
0x1800581c3  lea     rcx, [rbp+arg_10]
0x1800581c7  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800581cc  cmp     qword ptr [rbx+18h], 7
0x1800581d1  jbe     short loc_1800581D6
0x1800581d3  mov     rbx, [rbx]
0x1800581d6  lea     rax, [rbp+arg_10]
0x1800581da  mov     [rsp+50h+var_28], rax
0x1800581df  mov     dword ptr [rsp+50h+ppv], 80h; int
0x1800581e7  xor     r9d, r9d
0x1800581ea  lea     r8d, [r9+1]
0x1800581ee  mov     rdx, rbx
0x1800581f1  mov     rcx, rdi
0x1800581f4  mov     rax, rsi
0x1800581f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581fc  mov     rcx, [rbp+18h]; this
0x180058200  test    eax, eax
0x180058202  jns     short loc_180058219
0x180058204  mov     r9d, eax; char *
0x180058207  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18005820e  mov     edx, 620h; void *
0x180058213  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180058219  mov     rcx, [rbp+var_10]
0x18005821d  mov     rax, [rcx]
0x180058220  mov     r8, r14
0x180058223  mov     rdx, [rbp+arg_10]
0x180058227  mov     rax, [rax+28h]
0x18005822b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058230  mov     rcx, [rbp+18h]; this
0x180058234  test    eax, eax
0x180058236  jns     short loc_18005824D
0x180058238  mov     r9d, eax; char *
0x18005823b  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180058242  mov     edx, 622h; void *
0x180058247  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18005824d  lea     rcx, [rbp+arg_10]
0x180058251  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180058256  nop
0x180058257  mov     rcx, [rbp+arg_18]
0x18005825b  test    rcx, rcx
0x18005825e  jz      short loc_180058275
0x180058260  mov     [rbp+arg_18], 0
0x180058268  mov     rax, [rcx]
0x18005826b  mov     rax, [rax+10h]
0x18005826f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058274  nop
0x180058275  mov     rcx, [rbp+var_10]
0x180058279  test    rcx, rcx
0x18005827c  jz      short loc_180058293
0x18005827e  mov     [rbp+var_10], 0
0x180058286  mov     rax, [rcx]
0x180058289  mov     rax, [rax+10h]
0x18005828d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058292  nop
0x180058293  mov     rbx, [rsp+50h+arg_0]
0x180058298  mov     rsi, [rsp+50h+arg_8]
0x18005829d  add     rsp, 50h
0x1800582a1  pop     r14
0x1800582a3  pop     rdi
0x1800582a4  pop     rbp
0x1800582a5  retn
```
