# wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)

- ea: `0x18002e0a8`
- end: `0x18002e0c8`
- name: `?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002afc8`

## callees

- `0x180025b60`

## string_xrefs

- `0x18002e0b1`: `pcshell\shell\aix\shellconfigtask\lib\RecallTaskHandlerHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::in1diag3::_Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<0>(
    (int)this,
    569,
    (int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\RecallTaskHandlerHelpers.h",
    (int)a4,
    v4,
    retaddr);
}

```

## disassembly

```asm
0x18002e0a8  sub     rsp, 38h
0x18002e0ac  mov     rax, [rsp+38h]
0x18002e0b1  lea     r8, aPcshellShellAi_1; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002e0b8  mov     edx, 239h; int
0x18002e0bd  mov     [rsp+38h+var_10], rax; char *
0x18002e0c2  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
