# _DeviceConfiguration::ConfigurationManager::_EnableWindowsProtectedPrint_::_1_::catch$7

- ea: `0x180017105`
- end: `0x180017141`
- name: `_DeviceConfiguration::ConfigurationManager::_EnableWindowsProtectedPrint_::_1_::catch$7`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180017119`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::_EnableWindowsProtectedPrint_::_1_::catch_7(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 160) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 152),
                            (void *)0x129,
                            (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180017105  mov     [rsp+arg_8], rdx
0x18001710a  push    rbp
0x18001710b  sub     rsp, 60h
0x18001710f  mov     rbp, rdx
0x180017112  mov     rcx, [rbp+98h]; this
0x180017119  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180017120  mov     edx, 129h; void *
0x180017125  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001712a  mov     [rbp+0A0h], eax
0x180017130  mov     rax, 0
0x18001713a  add     rsp, 60h
0x18001713e  pop     rbp
0x18001713f  retn
```
