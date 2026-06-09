# wil::CoCreateInstance<ITaskService,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x180021d38`
- end: `0x180021da0`
- name: `??$CoCreateInstance@UITaskService@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `104`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022408`

## callees

- `0x18002008c`
- `0x180021d38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021d73`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021d73`

## string_xrefs

- `0x180021d8e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LPVOID *__fastcall wil::CoCreateInstance<ITaskService,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
               0,
               1u,
               &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
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
0x180021d38  mov     rax, rsp
0x180021d3b  mov     [rax+8], rcx
0x180021d3f  push    rbx
0x180021d40  sub     rsp, 40h
0x180021d44  mov     rbx, rcx
0x180021d47  mov     dword ptr [rax-18h], 0
0x180021d4e  mov     r8d, 1; dwClsContext
0x180021d54  mov     [rax-18h], r8d
0x180021d58  mov     qword ptr [rcx], 0
0x180021d5f  mov     [rax-28h], rcx
0x180021d63  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180021d6a  xor     edx, edx; pUnkOuter
0x180021d6c  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x180021d73  call    cs:__imp_CoCreateInstance
0x180021d79  test    eax, eax
0x180021d7b  js      short loc_180021D86
0x180021d7d  mov     rax, rbx
0x180021d80  add     rsp, 40h
0x180021d84  pop     rbx
0x180021d85  retn
0x180021d86  mov     rcx, [rsp+48h]; this
0x180021d8b  mov     r9d, eax; char *
0x180021d8e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021d95  mov     edx, 1CBEh; void *
0x180021d9a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
