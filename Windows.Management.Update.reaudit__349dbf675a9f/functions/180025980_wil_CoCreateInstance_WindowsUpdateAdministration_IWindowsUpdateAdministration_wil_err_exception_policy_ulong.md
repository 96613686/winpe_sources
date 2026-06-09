# wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(ulong)

- ea: `0x180025980`
- end: `0x1800259ea`
- name: `??$CoCreateInstance@VWindowsUpdateAdministration@@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@0@K@Z`
- size: `106`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013000`
- `0x180015920`
- `0x180026068`
- `0x180026230`
- `0x18002648c`
- `0x18002664c`

## callees

- `0x18001d9e8`
- `0x180025980`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800259b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800259b6`

## string_xrefs

- `0x1800259d8`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(
        LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_a1365519_3256_41a0_bfd6_9fe9b4b0dc31,
               0,
               4u,
               &GUID_87486abe_0730_4285_abdb_74ba4e8793ed,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1C60,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)Instance,
      v4);
  return a1;
}

```

## disassembly

```asm
0x180025980  mov     rax, rsp
0x180025983  mov     [rax+8], rcx
0x180025987  push    rbx
0x180025988  sub     rsp, 40h
0x18002598c  mov     rbx, rcx
0x18002598f  and     dword ptr [rax-18h], 0
0x180025993  mov     dword ptr [rax-18h], 2
0x18002599a  and     qword ptr [rcx], 0
0x18002599e  mov     [rax-28h], rcx
0x1800259a2  lea     r9, _GUID_87486abe_0730_4285_abdb_74ba4e8793ed; riid
0x1800259a9  xor     edx, edx; pUnkOuter
0x1800259ab  lea     r8d, [rdx+4]; dwClsContext
0x1800259af  lea     rcx, _GUID_a1365519_3256_41a0_bfd6_9fe9b4b0dc31; rclsid
0x1800259b6  call    cs:__imp_CoCreateInstance
0x1800259bd  nop     dword ptr [rax+rax+00h]
0x1800259c2  mov     rcx, [rsp+48h]; this
0x1800259c7  test    eax, eax
0x1800259c9  js      short loc_1800259D5
0x1800259cb  mov     rax, rbx
0x1800259ce  add     rsp, 40h
0x1800259d2  pop     rbx
0x1800259d3  retn
0x1800259d5  mov     r9d, eax; char *
0x1800259d8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800259df  mov     edx, 1C60h; void *
0x1800259e4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
