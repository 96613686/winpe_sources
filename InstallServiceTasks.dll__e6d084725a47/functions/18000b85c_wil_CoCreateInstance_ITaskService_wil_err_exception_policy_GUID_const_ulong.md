# wil::CoCreateInstance<ITaskService,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x18000b85c`
- end: `0x18000b8c4`
- name: `??$CoCreateInstance@UITaskService@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `104`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800104b0`

## callees

- `0x18000b85c`
- `0x180010150`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b897`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b897`

## string_xrefs

- `0x18000b8b2`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPVOID *__fastcall wil::CoCreateInstance<ITaskService,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, a1);
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
0x18000b85c  mov     rax, rsp
0x18000b85f  mov     [rax+8], rcx
0x18000b863  push    rbx
0x18000b864  sub     rsp, 40h
0x18000b868  mov     rbx, rcx
0x18000b86b  mov     dword ptr [rax-18h], 0
0x18000b872  mov     r8d, 1; dwClsContext
0x18000b878  mov     [rax-18h], r8d
0x18000b87c  mov     qword ptr [rcx], 0
0x18000b883  mov     [rax-28h], rcx
0x18000b887  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18000b88e  xor     edx, edx; pUnkOuter
0x18000b890  lea     rcx, CLSID_TaskScheduler; rclsid
0x18000b897  call    cs:__imp_CoCreateInstance
0x18000b89d  test    eax, eax
0x18000b89f  js      short loc_18000B8AA
0x18000b8a1  mov     rax, rbx
0x18000b8a4  add     rsp, 40h
0x18000b8a8  pop     rbx
0x18000b8a9  retn
0x18000b8aa  mov     rcx, [rsp+48h]; this
0x18000b8af  mov     r9d, eax; char *
0x18000b8b2  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b8b9  mov     edx, 1CBEh; void *
0x18000b8be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
