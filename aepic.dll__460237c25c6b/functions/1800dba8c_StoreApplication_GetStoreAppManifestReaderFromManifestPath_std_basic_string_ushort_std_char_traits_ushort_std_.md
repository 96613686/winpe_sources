# StoreApplication::GetStoreAppManifestReaderFromManifestPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,IAppxManifestReader * *)

- ea: `0x1800dba8c`
- end: `0x1800dbc2d`
- name: `?GetStoreAppManifestReaderFromManifestPath@StoreApplication@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIAppxManifestReader@@@Z`
- size: `417`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d9dcc`
- `0x1800dc490`

## callees

- `0x18000a2d4`
- `0x1800c97f0`
- `0x1800dba8c`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dbacc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dbb14`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dbacc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dbb14`

## string_xrefs

- `0x1800dbadd`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dbb25`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dbb8e`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dbbc2`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
__int64 __fastcall StoreApplication::GetStoreAppManifestReaderFromManifestPath(_QWORD *a1, __int64 a2)
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
      (void *)0x613,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
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
      (void *)0x619,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
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
      (void *)0x620,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v8,
      128);
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v15 + 40LL))(v15, v17, a2);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x622,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
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
0x1800dba8c  mov     [rsp-18h+arg_0], rbx
0x1800dba91  mov     [rsp-18h+arg_8], rsi
0x1800dba96  push    rbp
0x1800dba97  push    rdi
0x1800dba98  push    r14
0x1800dba9a  mov     rbp, rsp
0x1800dba9d  sub     rsp, 50h
0x1800dbaa1  mov     r14, rdx
0x1800dbaa4  mov     rbx, rcx
0x1800dbaa7  mov     [rbp+var_10], 0
0x1800dbaaf  lea     rax, [rbp+var_10]
0x1800dbab3  mov     [rsp+50h+ppv], rax; int
0x1800dbab8  lea     r9, _GUID_beb94909_e451_438b_b5a7_d79e767b75d8; riid
0x1800dbabf  xor     edx, edx; pUnkOuter
0x1800dbac1  lea     r8d, [rdx+1]; dwClsContext
0x1800dbac5  lea     rcx, _GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781; rclsid
0x1800dbacc  call    cs:__imp_CoCreateInstance
0x1800dbad2  mov     rcx, [rbp+18h]; this
0x1800dbad6  test    eax, eax
0x1800dbad8  jns     short loc_1800DBAEF
0x1800dbada  mov     r9d, eax; char *
0x1800dbadd  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dbae4  mov     edx, 613h; void *
0x1800dbae9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dbaef  mov     [rbp+arg_18], 0
0x1800dbaf7  lea     rax, [rbp+arg_18]
0x1800dbafb  mov     [rsp+50h+ppv], rax; int
0x1800dbb00  lea     r9, _GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154; riid
0x1800dbb07  xor     edx, edx; pUnkOuter
0x1800dbb09  lea     r8d, [rdx+1]; dwClsContext
0x1800dbb0d  lea     rcx, _GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e; rclsid
0x1800dbb14  call    cs:__imp_CoCreateInstance
0x1800dbb1a  mov     rcx, [rbp+18h]; this
0x1800dbb1e  test    eax, eax
0x1800dbb20  jns     short loc_1800DBB37
0x1800dbb22  mov     r9d, eax; char *
0x1800dbb25  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dbb2c  mov     edx, 619h; void *
0x1800dbb31  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dbb37  mov     [rbp+arg_10], 0
0x1800dbb3f  mov     rdi, [rbp+arg_18]
0x1800dbb43  mov     rax, [rdi]
0x1800dbb46  mov     rsi, [rax+28h]
0x1800dbb4a  lea     rcx, [rbp+arg_10]
0x1800dbb4e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbb53  cmp     qword ptr [rbx+18h], 7
0x1800dbb58  jbe     short loc_1800DBB5D
0x1800dbb5a  mov     rbx, [rbx]
0x1800dbb5d  lea     rax, [rbp+arg_10]
0x1800dbb61  mov     [rsp+50h+var_28], rax
0x1800dbb66  mov     dword ptr [rsp+50h+ppv], 80h; int
0x1800dbb6e  xor     r9d, r9d
0x1800dbb71  lea     r8d, [r9+1]
0x1800dbb75  mov     rdx, rbx
0x1800dbb78  mov     rcx, rdi
0x1800dbb7b  mov     rax, rsi
0x1800dbb7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbb83  mov     rcx, [rbp+18h]; this
0x1800dbb87  test    eax, eax
0x1800dbb89  jns     short loc_1800DBBA0
0x1800dbb8b  mov     r9d, eax; char *
0x1800dbb8e  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dbb95  mov     edx, 620h; void *
0x1800dbb9a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dbba0  mov     rcx, [rbp+var_10]
0x1800dbba4  mov     rax, [rcx]
0x1800dbba7  mov     r8, r14
0x1800dbbaa  mov     rdx, [rbp+arg_10]
0x1800dbbae  mov     rax, [rax+28h]
0x1800dbbb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbbb7  mov     rcx, [rbp+18h]; this
0x1800dbbbb  test    eax, eax
0x1800dbbbd  jns     short loc_1800DBBD4
0x1800dbbbf  mov     r9d, eax; char *
0x1800dbbc2  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dbbc9  mov     edx, 622h; void *
0x1800dbbce  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dbbd4  lea     rcx, [rbp+arg_10]
0x1800dbbd8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbbdd  nop
0x1800dbbde  mov     rcx, [rbp+arg_18]
0x1800dbbe2  test    rcx, rcx
0x1800dbbe5  jz      short loc_1800DBBFC
0x1800dbbe7  mov     [rbp+arg_18], 0
0x1800dbbef  mov     rax, [rcx]
0x1800dbbf2  mov     rax, [rax+10h]
0x1800dbbf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbbfb  nop
0x1800dbbfc  mov     rcx, [rbp+var_10]
0x1800dbc00  test    rcx, rcx
0x1800dbc03  jz      short loc_1800DBC1A
0x1800dbc05  mov     [rbp+var_10], 0
0x1800dbc0d  mov     rax, [rcx]
0x1800dbc10  mov     rax, [rax+10h]
0x1800dbc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbc19  nop
0x1800dbc1a  mov     rbx, [rsp+50h+arg_0]
0x1800dbc1f  mov     rsi, [rsp+50h+arg_8]
0x1800dbc24  add     rsp, 50h
0x1800dbc28  pop     r14
0x1800dbc2a  pop     rdi
0x1800dbc2b  pop     rbp
0x1800dbc2c  retn
```
