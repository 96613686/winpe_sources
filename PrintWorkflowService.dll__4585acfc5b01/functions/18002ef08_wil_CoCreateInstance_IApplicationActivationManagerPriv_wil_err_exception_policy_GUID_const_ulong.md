# wil::CoCreateInstance<IApplicationActivationManagerPriv,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x18002ef08`
- end: `0x18002ef70`
- name: `??$CoCreateInstance@UIApplicationActivationManagerPriv@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIApplicationActivationManagerPriv@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `104`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180033f1c`

## callees

- `0x1800127a4`
- `0x18002ef08`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ef43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ef43`

## string_xrefs

- `0x18002ef5e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<IApplicationActivationManagerPriv,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &CLSID_ApplicationActivationManager,
               0,
               1u,
               &GUID_54e4c428_d1d4_47d4_ade6_46c829114a7d,
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
0x18002ef08  mov     rax, rsp
0x18002ef0b  mov     [rax+8], rcx
0x18002ef0f  push    rbx
0x18002ef10  sub     rsp, 40h
0x18002ef14  mov     rbx, rcx
0x18002ef17  mov     dword ptr [rax-18h], 0
0x18002ef1e  mov     r8d, 1; dwClsContext
0x18002ef24  mov     [rax-18h], r8d
0x18002ef28  mov     qword ptr [rcx], 0
0x18002ef2f  mov     [rax-28h], rcx
0x18002ef33  lea     r9, _GUID_54e4c428_d1d4_47d4_ade6_46c829114a7d; riid
0x18002ef3a  xor     edx, edx; pUnkOuter
0x18002ef3c  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x18002ef43  call    cs:__imp_CoCreateInstance
0x18002ef49  test    eax, eax
0x18002ef4b  js      short loc_18002EF56
0x18002ef4d  mov     rax, rbx
0x18002ef50  add     rsp, 40h
0x18002ef54  pop     rbx
0x18002ef55  retn
0x18002ef56  mov     rcx, [rsp+48h]; this
0x18002ef5b  mov     r9d, eax; char *
0x18002ef5e  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ef65  mov     edx, 1CBEh; void *
0x18002ef6a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
