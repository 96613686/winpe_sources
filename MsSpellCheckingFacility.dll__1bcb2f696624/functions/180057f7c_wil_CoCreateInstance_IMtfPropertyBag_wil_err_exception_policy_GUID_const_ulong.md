# wil::CoCreateInstance<IMtfPropertyBag,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x180057f7c`
- end: `0x180057fe5`
- name: `??$CoCreateInstance@UIMtfPropertyBag@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIMtfPropertyBag@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `105`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800405d4`

## callees

- `0x180057f7c`
- `0x180070530`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180057fb7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180057fb7`

## string_xrefs

- `0x180057fc9`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<IMtfPropertyBag,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_26445657_50e1_4c9f_8378_ff028fd26816,
               0,
               1u,
               &GUID_47445657_8d68_4b3b_b716_b0debdd9b3f5,
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
0x180057f7c  mov     rax, rsp
0x180057f7f  mov     [rax+8], rcx
0x180057f83  push    rbx
0x180057f84  sub     rsp, 40h
0x180057f88  mov     rbx, rcx
0x180057f8b  mov     dword ptr [rax-18h], 0
0x180057f92  mov     r8d, 1; dwClsContext
0x180057f98  mov     [rax-18h], r8d
0x180057f9c  mov     qword ptr [rcx], 0
0x180057fa3  mov     [rax-28h], rcx
0x180057fa7  lea     r9, _GUID_47445657_8d68_4b3b_b716_b0debdd9b3f5; riid
0x180057fae  xor     edx, edx; pUnkOuter
0x180057fb0  lea     rcx, _GUID_26445657_50e1_4c9f_8378_ff028fd26816; rclsid
0x180057fb7  call    cs:__imp_CoCreateInstance
0x180057fbd  test    eax, eax
0x180057fbf  jns     short loc_180057FDB
0x180057fc1  mov     rcx, [rsp+48h]; this
0x180057fc6  mov     r9d, eax; char *
0x180057fc9  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180057fd0  mov     edx, 1CBEh; void *
0x180057fd5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180057fdb  mov     rax, rbx
0x180057fde  add     rsp, 40h
0x180057fe2  pop     rbx
0x180057fe3  retn
```
