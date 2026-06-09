# wil::CoCreateInstance<IDsmControl,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x180010918`
- end: `0x180010981`
- name: `??$CoCreateInstance@UIDsmControl@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIDsmControl@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `105`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011ea8`

## callees

- `0x18000670c`
- `0x180010918`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010953`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010953`

## string_xrefs

- `0x180010965`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<IDsmControl,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_e4785230_0e43_47dc_826a_07dbc3aa63d8,
               0,
               1u,
               &GUID_46147e3d_0380_450d_b48e_cca7f77d1c69,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
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
0x180010918  mov     rax, rsp
0x18001091b  mov     [rax+8], rcx
0x18001091f  push    rbx
0x180010920  sub     rsp, 40h
0x180010924  mov     rbx, rcx
0x180010927  mov     dword ptr [rax-18h], 0
0x18001092e  mov     r8d, 1; dwClsContext
0x180010934  mov     [rax-18h], r8d
0x180010938  mov     qword ptr [rcx], 0
0x18001093f  mov     [rax-28h], rcx
0x180010943  lea     r9, _GUID_46147e3d_0380_450d_b48e_cca7f77d1c69; riid
0x18001094a  xor     edx, edx; pUnkOuter
0x18001094c  lea     rcx, _GUID_e4785230_0e43_47dc_826a_07dbc3aa63d8; rclsid
0x180010953  call    cs:__imp_CoCreateInstance
0x180010959  test    eax, eax
0x18001095b  jns     short loc_180010977
0x18001095d  mov     rcx, [rsp+48h]; this
0x180010962  mov     r9d, eax; char *
0x180010965  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001096c  mov     edx, 1CBEh; void *
0x180010971  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180010977  mov     rax, rbx
0x18001097a  add     rsp, 40h
0x18001097e  pop     rbx
0x18001097f  retn
```
