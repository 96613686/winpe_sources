# _DeviceConfiguration::WNFListener::_CreateWorkForNotification_::_1_::catch$5

- ea: `0x180016b51`
- end: `0x180016b87`
- name: `_DeviceConfiguration::WNFListener::_CreateWorkForNotification_::_1_::catch$5`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180016b62`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\wnflistener.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::WNFListener::_CreateWorkForNotification_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0xDA,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180016b51  mov     [rsp+arg_8], rdx
0x180016b56  push    rbp
0x180016b57  sub     rsp, 20h
0x180016b5b  mov     rbp, rdx
0x180016b5e  mov     rcx, [rbp+28h]; this
0x180016b62  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\configuratio"...
0x180016b69  mov     edx, 0DAh; void *
0x180016b6e  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180016b73  mov     [rbp+30h], eax
0x180016b76  mov     rax, 0
0x180016b80  add     rsp, 20h
0x180016b84  pop     rbp
0x180016b85  retn
```
