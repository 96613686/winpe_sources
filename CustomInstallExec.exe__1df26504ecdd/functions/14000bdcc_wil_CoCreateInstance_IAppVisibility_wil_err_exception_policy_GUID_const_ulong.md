# wil::CoCreateInstance<IAppVisibility,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x14000bdcc`
- end: `0x14000be35`
- name: `??$CoCreateInstance@UIAppVisibility@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIAppVisibility@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `105`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c9f4`

## callees

- `0x140007d78`
- `0x14000bdcc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000be07`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000be07`

## string_xrefs

- `0x14000be19`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<IAppVisibility,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_7e5fe3d9_985f_4908_91f9_ee19f9fd1514,
               0,
               1u,
               &GUID_2246ea2d_caea_4444_a3c4_6de827e44313,
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
0x14000bdcc  mov     rax, rsp
0x14000bdcf  mov     [rax+8], rcx
0x14000bdd3  push    rbx
0x14000bdd4  sub     rsp, 40h
0x14000bdd8  mov     rbx, rcx
0x14000bddb  mov     dword ptr [rax-18h], 0
0x14000bde2  mov     r8d, 1; dwClsContext
0x14000bde8  mov     [rax-18h], r8d
0x14000bdec  mov     qword ptr [rcx], 0
0x14000bdf3  mov     [rax-28h], rcx
0x14000bdf7  lea     r9, _GUID_2246ea2d_caea_4444_a3c4_6de827e44313; riid
0x14000bdfe  xor     edx, edx; pUnkOuter
0x14000be00  lea     rcx, _GUID_7e5fe3d9_985f_4908_91f9_ee19f9fd1514; rclsid
0x14000be07  call    cs:__imp_CoCreateInstance
0x14000be0d  test    eax, eax
0x14000be0f  jns     short loc_14000BE2B
0x14000be11  mov     rcx, [rsp+48h]; this
0x14000be16  mov     r9d, eax; char *
0x14000be19  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000be20  mov     edx, 1CBEh; void *
0x14000be25  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000be2b  mov     rax, rbx
0x14000be2e  add     rsp, 40h
0x14000be32  pop     rbx
0x14000be33  retn
```
