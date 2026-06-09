# LegacySystemLanguagePackResourceProvider::_CreateUpdateSession(void)

- ea: `0x1800486e0`
- end: `0x1800487cb`
- name: `?_CreateUpdateSession@LegacySystemLanguagePackResourceProvider@@CA?AV?$ComPtr@UIUpdateSession@@@WRL@Microsoft@@XZ`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800452d8`

## callees

- `0x180012a98`
- `0x180033c30`
- `0x1800486e0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048722`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048722`
- `OLEAUT32!__imp_SysAllocString` at `0x18004873e`
- `OLEAUT32!__imp_SysAllocString` at `0x18004873e`
- `OLEAUT32!__imp_SysFreeString` at `0x180048779`
- `OLEAUT32!__imp_SysFreeString` at `0x180048779`

## string_xrefs

- `0x1800487b9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800487a7`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.h`
- `0x180048792`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180048737`: `Language Overlay Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
LPVOID *__fastcall LegacySystemLanguagePackResourceProvider::_CreateUpdateSession(LPVOID *a1)
{
  HRESULT Instance; // eax
  LPVOID v3; // rsi
  __int64 v4; // rbp
  BSTR v5; // rax
  const char *v6; // r9
  OLECHAR *v7; // rdi
  int v8; // eax
  int v10; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe,
               0,
               0x17u,
               &GUID_816858a4_260d_4260_933a_2585f1abc76b,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.h",
      (const char *)(unsigned int)Instance,
      v10);
  v3 = *a1;
  v4 = *(_QWORD *)*a1;
  v5 = SysAllocString(L"Language Overlay Service");
  v7 = v5;
  if ( !v5 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v6);
  v8 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(v4 + 64))(v3, v5);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x36D,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v8,
      v10);
  SysFreeString(v7);
  return a1;
}

```

## disassembly

```asm
0x1800486e0  mov     rax, rsp
0x1800486e3  mov     [rax+18h], rbx
0x1800486e7  mov     [rax+8], rcx
0x1800486eb  push    rbp
0x1800486ec  push    rsi
0x1800486ed  push    rdi
0x1800486ee  sub     rsp, 40h
0x1800486f2  mov     rbx, rcx
0x1800486f5  mov     dword ptr [rax-28h], 0
0x1800486fc  mov     qword ptr [rcx], 0
0x180048703  mov     dword ptr [rax-28h], 2
0x18004870a  mov     [rax-38h], rcx
0x18004870e  lea     r9, _GUID_816858a4_260d_4260_933a_2585f1abc76b; riid
0x180048715  xor     edx, edx; pUnkOuter
0x180048717  lea     r8d, [rdx+17h]; dwClsContext
0x18004871b  lea     rcx, _GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe; rclsid
0x180048722  call    cs:__imp_CoCreateInstance
0x180048728  mov     rcx, [rsp+58h]; this
0x18004872d  test    eax, eax
0x18004872f  js      short loc_1800487A4
0x180048731  mov     rsi, [rbx]
0x180048734  mov     rbp, [rsi]
0x180048737  lea     rcx, sourceString; "Language Overlay Service"
0x18004873e  call    cs:__imp_SysAllocString
0x180048744  mov     rdi, rax
0x180048747  mov     [rsp+58h+arg_8], rax
0x18004874c  mov     [rsp+58h+var_28], 5
0x180048754  mov     rcx, [rsp+58h]; this
0x180048759  test    rax, rax
0x18004875c  jz      short loc_1800487B9
0x18004875e  mov     rdx, rax
0x180048761  mov     rcx, rsi
0x180048764  mov     rax, [rbp+40h]
0x180048768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004876d  mov     rcx, [rsp+58h]; this
0x180048772  test    eax, eax
0x180048774  js      short loc_18004878F
0x180048776  mov     rcx, rdi; bstrString
0x180048779  call    cs:__imp_SysFreeString
0x18004877f  mov     rax, rbx
0x180048782  mov     rbx, [rsp+58h+arg_10]
0x180048787  add     rsp, 40h
0x18004878b  pop     rdi
0x18004878c  pop     rsi
0x18004878d  pop     rbp
0x18004878e  retn
0x18004878f  mov     r9d, eax; char *
0x180048792  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180048799  mov     edx, 36Dh; void *
0x18004879e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800487a4  mov     r9d, eax; char *
0x1800487a7  lea     r8, aOnecoreBaseLan_22; "onecore\\base\\languageoverlay\\service"...
0x1800487ae  mov     edx, 0D9h; void *
0x1800487b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800487b9  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800487c0  mov     edx, 15F3h; void *
0x1800487c5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
