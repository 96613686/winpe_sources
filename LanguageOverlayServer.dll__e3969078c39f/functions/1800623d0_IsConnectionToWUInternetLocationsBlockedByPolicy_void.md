# _IsConnectionToWUInternetLocationsBlockedByPolicy(void)

- ea: `0x1800623d0`
- end: `0x180062535`
- name: `?_IsConnectionToWUInternetLocationsBlockedByPolicy@@YA_NXZ`
- size: `357`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061e88`
- `0x180062098`

## callees

- `0x180011318`
- `0x180012a98`
- `0x1800623d0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006240a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006240a`
- `OLEAUT32!__imp_VariantInit` at `0x18006244f`
- `OLEAUT32!__imp_VariantInit` at `0x18006244f`
- `OLEAUT32!__imp_VariantClear` at `0x1800624a2`
- `OLEAUT32!__imp_VariantClear` at `0x1800624cc`
- `OLEAUT32!__imp_VariantClear` at `0x1800624a2`
- `OLEAUT32!__imp_VariantClear` at `0x1800624cc`

## string_xrefs

- `0x1800624fb`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18006250d`: `onecore\base\languageoverlay\common\policyutils.cpp`
- `0x180062522`: `onecore\base\languageoverlay\common\policyutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool _IsConnectionToWUInternetLocationsBlockedByPolicy(void)
{
  HRESULT Instance; // eax
  const char *v1; // r9
  int v2; // eax
  bool result; // al
  int ppv; // [rsp+20h] [rbp-58h]
  __int128 v5; // [rsp+40h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  _QWORD *v8; // [rsp+88h] [rbp+10h] BYREF

  v8 = 0;
  Instance = CoCreateInstance(
               &GUID_07369a67_07a6_4608_abea_379491cb7c46,
               0,
               1u,
               &GUID_152807bd_4d18_46c5_ae31_dd8d597d0559,
               (LPVOID *)&v8);
  try
  {
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)Instance,
        ppv);
    if ( !v8 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
        v1);
    v5 = 0;
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v2 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int128 *))(*v8 + 24LL))(v8, 14, &v5);
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
        (const char *)(unsigned int)v2,
        ppv);
    if ( DWORD1(v5) == 1 && pvarg.lVal == 1 )
    {
      VariantClear(&pvarg);
      if ( v8 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v8 + 16LL))(v8, *v8);
      result = 1;
    }
    else
    {
      VariantClear(&pvarg);
      if ( v8 )
        (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
      result = 0;
    }
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800623d0  mov     rax, rsp
0x1800623d3  sub     rsp, 78h
0x1800623d7  mov     dword ptr [rax+8], 0
0x1800623de  mov     dword ptr [rax+8], 2
0x1800623e5  mov     qword ptr [rax+10h], 0
0x1800623ed  lea     rax, [rax+10h]
0x1800623f1  mov     qword ptr [rsp+78h+ppv], rax; int
0x1800623f6  lea     r9, _GUID_152807bd_4d18_46c5_ae31_dd8d597d0559; riid
0x1800623fd  xor     edx, edx; pUnkOuter
0x1800623ff  lea     r8d, [rdx+1]; dwClsContext
0x180062403  lea     rcx, _GUID_07369a67_07a6_4608_abea_379491cb7c46; rclsid
0x18006240a  call    cs:__imp_CoCreateInstance
0x180062410  mov     rcx, [rsp+78h]; this
0x180062415  test    eax, eax
0x180062417  js      loc_1800624F8
0x18006241d  cmp     [rsp+78h+arg_8], 0
0x180062426  setz    al
0x180062429  mov     rcx, [rsp+78h]; this
0x18006242e  test    al, al
0x180062430  jnz     loc_18006250D
0x180062436  xorps   xmm0, xmm0
0x180062439  xor     eax, eax
0x18006243b  movups  [rsp+78h+var_38], xmm0
0x180062440  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x180062445  mov     qword ptr [rsp+78h+pvarg+10h], rax
0x18006244a  lea     rcx, [rsp+78h+pvarg]; pvarg
0x18006244f  call    cs:__imp_VariantInit
0x180062455  lea     rax, [rsp+78h+var_38]
0x18006245a  mov     [rsp+78h+var_48], rax
0x18006245f  mov     [rsp+78h+var_40], 1
0x180062464  mov     rcx, [rsp+78h+arg_8]
0x18006246c  mov     rax, [rcx]
0x18006246f  lea     r8, [rsp+78h+var_38]
0x180062474  mov     edx, 0Eh
0x180062479  mov     rax, [rax+18h]
0x18006247d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062482  mov     rcx, [rsp+78h]; this
0x180062487  test    eax, eax
0x180062489  js      loc_18006251F
0x18006248f  cmp     dword ptr [rsp+78h+var_38+4], 1
0x180062494  jnz     short loc_1800624C7
0x180062496  cmp     dword ptr [rsp+78h+pvarg+8], 1
0x18006249b  jnz     short loc_1800624C7
0x18006249d  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1800624a2  call    cs:__imp_VariantClear
0x1800624a8  nop
0x1800624a9  mov     rcx, [rsp+78h+arg_8]
0x1800624b1  test    rcx, rcx
0x1800624b4  jz      short loc_1800624C3
0x1800624b6  mov     rdx, [rcx]
0x1800624b9  mov     rax, [rdx+10h]
0x1800624bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624c2  nop
0x1800624c3  mov     al, 1
0x1800624c5  jmp     short loc_1800624F3
0x1800624c7  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1800624cc  call    cs:__imp_VariantClear
0x1800624d2  nop
0x1800624d3  mov     rcx, [rsp+78h+arg_8]
0x1800624db  test    rcx, rcx
0x1800624de  jz      short loc_1800624ED
0x1800624e0  mov     rax, [rcx]
0x1800624e3  mov     rax, [rax+10h]
0x1800624e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624ec  nop
0x1800624ed  xor     al, al
0x1800624ef  jmp     short loc_1800624F3
0x1800624f1  xor     al, al
0x1800624f3  add     rsp, 78h
0x1800624f7  retn
0x1800624f8  mov     r9d, eax; char *
0x1800624fb  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180062502  mov     edx, 1CBEh; void *
0x180062507  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006250d  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x180062514  mov     edx, 87h; void *
0x180062519  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18006251f  mov     r9d, eax; char *
0x180062522  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x180062529  mov     edx, 90h; void *
0x18006252e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
