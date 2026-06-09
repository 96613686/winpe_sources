# wil::CoCreateInstance<ITaskService,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x18001ed50`
- end: `0x18001edb9`
- name: `??$CoCreateInstance@UITaskService@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180020578`

## callees

- `0x18001cfa4`
- `0x18001ed50`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x18001ed8b`
- `OLE32!CoCreateInstance` at `0x18001ed8b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18001ed50  mov     rax, rsp
0x18001ed53  mov     [rax+8], rcx
0x18001ed57  push    rbx
0x18001ed58  sub     rsp, 40h
0x18001ed5c  mov     rbx, rcx
0x18001ed5f  mov     dword ptr [rax-18h], 0
0x18001ed66  mov     r8d, 1; dwClsContext
0x18001ed6c  mov     [rax-18h], r8d
0x18001ed70  mov     qword ptr [rcx], 0
0x18001ed77  mov     [rax-28h], rcx
0x18001ed7b  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18001ed82  xor     edx, edx; pUnkOuter
0x18001ed84  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001ed8b  call    cs:__imp_CoCreateInstance
0x18001ed91  test    eax, eax
0x18001ed93  jns     short loc_18001EDAF
0x18001ed95  mov     rcx, [rsp+48h]; this
0x18001ed9a  mov     r9d, eax; char *
0x18001ed9d  lea     r8, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; unsigned int
0x18001eda4  mov     edx, 1CBEh; void *
0x18001eda9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001edaf  mov     rax, rbx
0x18001edb2  add     rsp, 40h
0x18001edb6  pop     rbx
0x18001edb7  retn
```
