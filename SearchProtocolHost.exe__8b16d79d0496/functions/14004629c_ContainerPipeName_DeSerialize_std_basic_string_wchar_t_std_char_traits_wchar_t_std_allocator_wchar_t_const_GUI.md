# ContainerPipeName::DeSerialize(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_GUID &,_GUID &,_GUID &,_GUID &,_GUID &,_GUID &,_GUID &,_GUID &)

- ea: `0x14004629c`
- end: `0x14004663a`
- name: `?DeSerialize@ContainerPipeName@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@1111111@Z`
- size: `926`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002a090`
- `0x14002d394`
- `0x14003a8e8`

## callees

- `0x140005240`
- `0x14000cd28`
- `0x1400105c0`
- `0x1400317a8`
- `0x14003376c`
- `0x14004629c`
- `0x140046680`
- `0x140046698`

## string_xrefs

- `0x140046330`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x14004635d`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x14004638f`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x1400463bc`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x1400463ee`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x14004641b`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x14004644d`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x14004647a`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x1400464ac`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x1400464d9`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x14004650b`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x140046538`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x14004656a`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x140046597`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x1400465c9`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`
- `0x1400465f8`: `onecoreuap\base\appmodel\search\common\containerpipename\containerpipename.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ContainerPipeName::DeSerialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 result; // rax
  int v21[4]; // [rsp+20h] [rbp-88h] BYREF
  __int64 v22; // [rsp+30h] [rbp-78h]
  __int64 v23; // [rsp+38h] [rbp-70h]
  _BYTE v24[32]; // [rsp+40h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v23 = -2;
  v22 = a9;
  std::wstring::operator std::wstring_view(a1, v21);
  std::wstring::wstring(v24);
  try
  {
    if ( !(unsigned __int8)gettoken(v21, v24) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)0x80070057LL,
        v21[0]);
    v12 = ContainerPipeName::StringToGuid(v24, a2);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)(unsigned int)v12,
        v21[0]);
    if ( !(unsigned __int8)gettoken(v21, v24) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)0x80070057LL,
        v21[0]);
    v13 = ContainerPipeName::StringToGuid(v24, a3);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)(unsigned int)v13,
        v21[0]);
    if ( !(unsigned __int8)gettoken(v21, v24) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)0x80070057LL,
        v21[0]);
    v14 = ContainerPipeName::StringToGuid(v24, a4);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)(unsigned int)v14,
        v21[0]);
    if ( !(unsigned __int8)gettoken(v21, v24) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)0x80070057LL,
        v21[0]);
    v15 = ContainerPipeName::StringToGuid(v24, a5);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)(unsigned int)v15,
        v21[0]);
    if ( !(unsigned __int8)gettoken(v21, v24) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)0x80070057LL,
        v21[0]);
    v16 = ContainerPipeName::StringToGuid(v24, a6);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)(unsigned int)v16,
        v21[0]);
    if ( !(unsigned __int8)gettoken(v21, v24) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)0x80070057LL,
        v21[0]);
    v17 = ContainerPipeName::StringToGuid(v24, a7);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)(unsigned int)v17,
        v21[0]);
    if ( !(unsigned __int8)gettoken(v21, v24) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)0x80070057LL,
        v21[0]);
    v18 = ContainerPipeName::StringToGuid(v24, a8);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)(unsigned int)v18,
        v21[0]);
    if ( !(unsigned __int8)gettoken(v21, v24) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)0x80070057LL,
        v21[0]);
    v19 = ContainerPipeName::StringToGuid(v24, v22);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x76,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp",
        (const char *)(unsigned int)v19,
        v21[0]);
    std::wstring::_Tidy_deallocate(v24);
    result = 0;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      122,
      "onecoreuap\\base\\appmodel\\search\\common\\containerpipename\\containerpipename.cpp");
  }
  return result;
}

```

## disassembly

```asm
0x14004629c  push    rbx
0x14004629e  push    rsi
0x14004629f  push    rdi
0x1400462a0  push    r12
0x1400462a2  push    r13
0x1400462a4  push    r14
0x1400462a6  push    r15
0x1400462a8  sub     rsp, 70h
0x1400462ac  mov     [rsp+0A8h+var_70], 0FFFFFFFFFFFFFFFEh
0x1400462b5  mov     rax, cs:__security_cookie
0x1400462bc  xor     rax, rsp
0x1400462bf  mov     [rsp+0A8h+var_48], rax
0x1400462c4  mov     rsi, r9
0x1400462c7  mov     rdi, r8
0x1400462ca  mov     rbx, rdx
0x1400462cd  mov     r14, [rsp+0A8h+arg_20]
0x1400462d5  mov     r15, [rsp+0A8h+arg_28]
0x1400462dd  mov     r12, [rsp+0A8h+arg_30]
0x1400462e5  mov     r13, [rsp+0A8h+arg_38]
0x1400462ed  mov     rax, [rsp+0A8h+arg_40]
0x1400462f5  mov     [rsp+0A8h+var_78], rax
0x1400462fa  lea     rdx, [rsp+0A8h+var_88]
0x1400462ff  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x140046304  lea     rcx, [rsp+0A8h+var_68]
0x140046309  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14004630e  nop
0x14004630f  lea     rdx, [rsp+0A8h+var_68]
0x140046314  lea     rcx, [rsp+0A8h+var_88]
0x140046319  call    ?gettoken@@YA_NAEAV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@_W@Z; gettoken(std::wstring_view &,std::wstring &,wchar_t)
0x14004631e  mov     rcx, [rsp+0A8h]; this
0x140046326  test    al, al
0x140046328  jnz     short loc_140046341
0x14004632a  mov     r9d, 80070057h; char *
0x140046330  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x140046337  mov     edx, 67h ; 'g'; void *
0x14004633c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140046341  mov     rdx, rbx
0x140046344  lea     rcx, [rsp+0A8h+var_68]
0x140046349  call    ?StringToGuid@ContainerPipeName@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; ContainerPipeName::StringToGuid(std::wstring const &,_GUID &)
0x14004634e  mov     rcx, [rsp+0A8h]; this
0x140046356  test    eax, eax
0x140046358  jns     short loc_14004636E
0x14004635a  mov     r9d, eax; char *
0x14004635d  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x140046364  mov     edx, 68h ; 'h'; void *
0x140046369  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004636e  lea     rdx, [rsp+0A8h+var_68]
0x140046373  lea     rcx, [rsp+0A8h+var_88]
0x140046378  call    ?gettoken@@YA_NAEAV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@_W@Z; gettoken(std::wstring_view &,std::wstring &,wchar_t)
0x14004637d  mov     rcx, [rsp+0A8h]; this
0x140046385  test    al, al
0x140046387  jnz     short loc_1400463A0
0x140046389  mov     r9d, 80070057h; char *
0x14004638f  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x140046396  mov     edx, 69h ; 'i'; void *
0x14004639b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400463a0  mov     rdx, rdi
0x1400463a3  lea     rcx, [rsp+0A8h+var_68]
0x1400463a8  call    ?StringToGuid@ContainerPipeName@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; ContainerPipeName::StringToGuid(std::wstring const &,_GUID &)
0x1400463ad  mov     rcx, [rsp+0A8h]; this
0x1400463b5  test    eax, eax
0x1400463b7  jns     short loc_1400463CD
0x1400463b9  mov     r9d, eax; char *
0x1400463bc  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400463c3  mov     edx, 6Ah ; 'j'; void *
0x1400463c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400463cd  lea     rdx, [rsp+0A8h+var_68]
0x1400463d2  lea     rcx, [rsp+0A8h+var_88]
0x1400463d7  call    ?gettoken@@YA_NAEAV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@_W@Z; gettoken(std::wstring_view &,std::wstring &,wchar_t)
0x1400463dc  mov     rcx, [rsp+0A8h]; this
0x1400463e4  test    al, al
0x1400463e6  jnz     short loc_1400463FF
0x1400463e8  mov     r9d, 80070057h; char *
0x1400463ee  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400463f5  mov     edx, 6Bh ; 'k'; void *
0x1400463fa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400463ff  mov     rdx, rsi
0x140046402  lea     rcx, [rsp+0A8h+var_68]
0x140046407  call    ?StringToGuid@ContainerPipeName@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; ContainerPipeName::StringToGuid(std::wstring const &,_GUID &)
0x14004640c  mov     rcx, [rsp+0A8h]; this
0x140046414  test    eax, eax
0x140046416  jns     short loc_14004642C
0x140046418  mov     r9d, eax; char *
0x14004641b  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x140046422  mov     edx, 6Ch ; 'l'; void *
0x140046427  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004642c  lea     rdx, [rsp+0A8h+var_68]
0x140046431  lea     rcx, [rsp+0A8h+var_88]
0x140046436  call    ?gettoken@@YA_NAEAV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@_W@Z; gettoken(std::wstring_view &,std::wstring &,wchar_t)
0x14004643b  mov     rcx, [rsp+0A8h]; this
0x140046443  test    al, al
0x140046445  jnz     short loc_14004645E
0x140046447  mov     r9d, 80070057h; char *
0x14004644d  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x140046454  mov     edx, 6Dh ; 'm'; void *
0x140046459  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004645e  mov     rdx, r14
0x140046461  lea     rcx, [rsp+0A8h+var_68]
0x140046466  call    ?StringToGuid@ContainerPipeName@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; ContainerPipeName::StringToGuid(std::wstring const &,_GUID &)
0x14004646b  mov     rcx, [rsp+0A8h]; this
0x140046473  test    eax, eax
0x140046475  jns     short loc_14004648B
0x140046477  mov     r9d, eax; char *
0x14004647a  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x140046481  mov     edx, 6Eh ; 'n'; void *
0x140046486  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004648b  lea     rdx, [rsp+0A8h+var_68]
0x140046490  lea     rcx, [rsp+0A8h+var_88]
0x140046495  call    ?gettoken@@YA_NAEAV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@_W@Z; gettoken(std::wstring_view &,std::wstring &,wchar_t)
0x14004649a  mov     rcx, [rsp+0A8h]; this
0x1400464a2  test    al, al
0x1400464a4  jnz     short loc_1400464BD
0x1400464a6  mov     r9d, 80070057h; char *
0x1400464ac  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400464b3  mov     edx, 6Fh ; 'o'; void *
0x1400464b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400464bd  mov     rdx, r15
0x1400464c0  lea     rcx, [rsp+0A8h+var_68]
0x1400464c5  call    ?StringToGuid@ContainerPipeName@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; ContainerPipeName::StringToGuid(std::wstring const &,_GUID &)
0x1400464ca  mov     rcx, [rsp+0A8h]; this
0x1400464d2  test    eax, eax
0x1400464d4  jns     short loc_1400464EA
0x1400464d6  mov     r9d, eax; char *
0x1400464d9  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400464e0  mov     edx, 70h ; 'p'; void *
0x1400464e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400464ea  lea     rdx, [rsp+0A8h+var_68]
0x1400464ef  lea     rcx, [rsp+0A8h+var_88]
0x1400464f4  call    ?gettoken@@YA_NAEAV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@_W@Z; gettoken(std::wstring_view &,std::wstring &,wchar_t)
0x1400464f9  mov     rcx, [rsp+0A8h]; this
0x140046501  test    al, al
0x140046503  jnz     short loc_14004651C
0x140046505  mov     r9d, 80070057h; char *
0x14004650b  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x140046512  mov     edx, 71h ; 'q'; void *
0x140046517  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004651c  mov     rdx, r12
0x14004651f  lea     rcx, [rsp+0A8h+var_68]
0x140046524  call    ?StringToGuid@ContainerPipeName@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; ContainerPipeName::StringToGuid(std::wstring const &,_GUID &)
0x140046529  mov     rcx, [rsp+0A8h]; this
0x140046531  test    eax, eax
0x140046533  jns     short loc_140046549
0x140046535  mov     r9d, eax; char *
0x140046538  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x14004653f  mov     edx, 72h ; 'r'; void *
0x140046544  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140046549  lea     rdx, [rsp+0A8h+var_68]
0x14004654e  lea     rcx, [rsp+0A8h+var_88]
0x140046553  call    ?gettoken@@YA_NAEAV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@_W@Z; gettoken(std::wstring_view &,std::wstring &,wchar_t)
0x140046558  mov     rcx, [rsp+0A8h]; this
0x140046560  test    al, al
0x140046562  jnz     short loc_14004657B
0x140046564  mov     r9d, 80070057h; char *
0x14004656a  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x140046571  mov     edx, 73h ; 's'; void *
0x140046576  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004657b  mov     rdx, r13
0x14004657e  lea     rcx, [rsp+0A8h+var_68]
0x140046583  call    ?StringToGuid@ContainerPipeName@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; ContainerPipeName::StringToGuid(std::wstring const &,_GUID &)
0x140046588  mov     rcx, [rsp+0A8h]; this
0x140046590  test    eax, eax
0x140046592  jns     short loc_1400465A8
0x140046594  mov     r9d, eax; char *
0x140046597  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x14004659e  mov     edx, 74h ; 't'; void *
0x1400465a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400465a8  lea     rdx, [rsp+0A8h+var_68]
0x1400465ad  lea     rcx, [rsp+0A8h+var_88]
0x1400465b2  call    ?gettoken@@YA_NAEAV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@_W@Z; gettoken(std::wstring_view &,std::wstring &,wchar_t)
0x1400465b7  mov     rcx, [rsp+0A8h]; this
0x1400465bf  test    al, al
0x1400465c1  jnz     short loc_1400465DA
0x1400465c3  mov     r9d, 80070057h; char *
0x1400465c9  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400465d0  mov     edx, 75h ; 'u'; void *
0x1400465d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400465da  mov     rdx, [rsp+0A8h+var_78]
0x1400465df  lea     rcx, [rsp+0A8h+var_68]
0x1400465e4  call    ?StringToGuid@ContainerPipeName@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; ContainerPipeName::StringToGuid(std::wstring const &,_GUID &)
0x1400465e9  mov     rcx, [rsp+0A8h]; this
0x1400465f1  test    eax, eax
0x1400465f3  jns     short loc_14004660A
0x1400465f5  mov     r9d, eax; char *
0x1400465f8  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400465ff  mov     edx, 76h ; 'v'; void *
0x140046604  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004660a  lea     rcx, [rsp+0A8h+var_68]
0x14004660f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140046614  xor     eax, eax
0x140046616  jmp     short loc_14004661C
0x140046618  mov     eax, dword ptr [rsp+0A8h+var_78]
0x14004661c  mov     rcx, [rsp+0A8h+var_48]
0x140046621  xor     rcx, rsp; StackCookie
0x140046624  call    __security_check_cookie
0x140046629  add     rsp, 70h
0x14004662d  pop     r15
0x14004662f  pop     r14
0x140046631  pop     r13
0x140046633  pop     r12
0x140046635  pop     rdi
0x140046636  pop     rsi
0x140046637  pop     rbx
0x140046638  retn
```
