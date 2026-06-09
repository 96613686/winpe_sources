# LegacySystemLanguagePackResourceProvider::_CreateCbsSession(void)

- ea: `0x180047d40`
- end: `0x180047e40`
- name: `?_CreateCbsSession@LegacySystemLanguagePackResourceProvider@@CA?AV?$ComPtr@UICbsSession9@@@WRL@Microsoft@@XZ`
- size: `256`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180045d10`
- `0x180046040`
- `0x180048b9c`
- `0x180049c04`

## callees

- `0x180012a98`
- `0x180047d40`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047d7c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047d7c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180047db4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180047db4`

## string_xrefs

- `0x180047dfa`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180047e14`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180047e2e`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180047dd0`: `Language Overlay Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID *__fastcall LegacySystemLanguagePackResourceProvider::_CreateCbsSession(LPVOID *a1)
{
  HRESULT Instance; // eax
  HRESULT v3; // eax
  int v4; // eax
  int dwAuthnLevel; // [rsp+20h] [rbp-38h]
  int dwAuthnLevela; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed,
               0,
               0x15u,
               &GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3F1,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)Instance,
      dwAuthnLevel);
  v3 = CoSetProxyBlanket((IUnknown *)*a1, 0xFFFFFFFF, 0xFFFFFFFF, 0, 3u, 3u, 0, 0);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3FB,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v3,
      dwAuthnLevela);
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, const OLECHAR *, _QWORD))(*(_QWORD *)*a1 + 24LL))(
         *a1,
         1073741872,
         L"Language Overlay Service",
         0);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3FD,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v4,
      0);
  return a1;
}

```

## disassembly

```asm
0x180047d40  mov     rax, rsp
0x180047d43  mov     [rax+8], rcx
0x180047d47  push    rbx
0x180047d48  sub     rsp, 50h
0x180047d4c  mov     rbx, rcx
0x180047d4f  mov     dword ptr [rax-18h], 0
0x180047d56  mov     qword ptr [rcx], 0
0x180047d5d  mov     dword ptr [rax-18h], 1
0x180047d64  mov     [rax-38h], rcx
0x180047d68  lea     r9, _GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22; riid
0x180047d6f  xor     edx, edx; pUnkOuter
0x180047d71  lea     r8d, [rdx+15h]; dwClsContext
0x180047d75  lea     rcx, _GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed; rclsid
0x180047d7c  call    cs:__imp_CoCreateInstance
0x180047d82  test    eax, eax
0x180047d84  js      loc_180047E0C
0x180047d8a  mov     [rsp+58h+dwCapabilities], 0; dwCapabilities
0x180047d92  mov     [rsp+58h+pAuthInfo], 0; pAuthInfo
0x180047d9b  mov     eax, 3
0x180047da0  mov     [rsp+58h+dwImpLevel], eax; dwImpLevel
0x180047da4  mov     [rsp+58h+dwAuthnLevel], eax; int
0x180047da8  xor     r9d, r9d; pServerPrincName
0x180047dab  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180047dae  mov     r8d, edx; dwAuthzSvc
0x180047db1  mov     rcx, [rbx]; pProxy
0x180047db4  call    cs:__imp_CoSetProxyBlanket
0x180047dba  test    eax, eax
0x180047dbc  js      short loc_180047E26
0x180047dbe  mov     rcx, [rbx]
0x180047dc1  mov     rax, [rcx]
0x180047dc4  mov     qword ptr [rsp+58h+dwAuthnLevel], 0; int
0x180047dcd  xor     r9d, r9d
0x180047dd0  lea     r8, sourceString; "Language Overlay Service"
0x180047dd7  mov     edx, 40000030h
0x180047ddc  mov     rax, [rax+18h]
0x180047de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047de5  test    eax, eax
0x180047de7  js      short loc_180047DF2
0x180047de9  mov     rax, rbx
0x180047dec  add     rsp, 50h
0x180047df0  pop     rbx
0x180047df1  retn
0x180047df2  mov     rcx, [rsp+58h]; this
0x180047df7  mov     r9d, eax; char *
0x180047dfa  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180047e01  mov     edx, 3FDh; void *
0x180047e06  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180047e0c  mov     rcx, [rsp+58h]; this
0x180047e11  mov     r9d, eax; char *
0x180047e14  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180047e1b  mov     edx, 3F1h; void *
0x180047e20  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180047e26  mov     rcx, [rsp+58h]; this
0x180047e2b  mov     r9d, eax; char *
0x180047e2e  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180047e35  mov     edx, 3FBh; void *
0x180047e3a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
