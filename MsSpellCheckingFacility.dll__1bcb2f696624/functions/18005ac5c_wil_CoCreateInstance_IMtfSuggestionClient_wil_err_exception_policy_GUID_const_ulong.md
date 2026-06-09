# wil::CoCreateInstance<IMtfSuggestionClient,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x18005ac5c`
- end: `0x18005acc5`
- name: `??$CoCreateInstance@UIMtfSuggestionClient@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIMtfSuggestionClient@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `105`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800405d4`

## callees

- `0x18005ac5c`
- `0x180070530`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005ac97`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005ac97`

## string_xrefs

- `0x18005aca9`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<IMtfSuggestionClient,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_b2445657_090d_11e4_aeda_b4b52fe06611,
               0,
               1u,
               &GUID_f7445657_fc22_11e3_a6ad_b4b52fe06611,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)Instance,
      v4);
  return a1;
}

```

## disassembly

```asm
0x18005ac5c  mov     rax, rsp
0x18005ac5f  mov     [rax+8], rcx
0x18005ac63  push    rbx
0x18005ac64  sub     rsp, 40h
0x18005ac68  mov     rbx, rcx
0x18005ac6b  mov     dword ptr [rax-18h], 0
0x18005ac72  mov     r8d, 1; dwClsContext
0x18005ac78  mov     [rax-18h], r8d
0x18005ac7c  mov     qword ptr [rcx], 0
0x18005ac83  mov     [rax-28h], rcx
0x18005ac87  lea     r9, _GUID_f7445657_fc22_11e3_a6ad_b4b52fe06611; riid
0x18005ac8e  xor     edx, edx; pUnkOuter
0x18005ac90  lea     rcx, _GUID_b2445657_090d_11e4_aeda_b4b52fe06611; rclsid
0x18005ac97  call    cs:__imp_CoCreateInstance
0x18005ac9d  test    eax, eax
0x18005ac9f  jns     short loc_18005ACBB
0x18005aca1  mov     rcx, [rsp+48h]; this
0x18005aca6  mov     r9d, eax; char *
0x18005aca9  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005acb0  mov     edx, 1CBEh; void *
0x18005acb5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005acbb  mov     rax, rbx
0x18005acbe  add     rsp, 40h
0x18005acc2  pop     rbx
0x18005acc3  retn
```
