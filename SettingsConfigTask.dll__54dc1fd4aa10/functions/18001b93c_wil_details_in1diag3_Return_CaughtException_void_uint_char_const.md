# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x18001b93c`
- end: `0x18001b961`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `37`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002268d`

## callees

- `0x18000d8a8`

## string_xrefs

- `0x18001b94a`: `pcshell\shell\settings\settingsconfigtask\lib\settingsconfigtaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_CaughtException(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  return wil::details::ReportFailure_CaughtException<1>(
           (_DWORD)this,
           200,
           (unsigned int)"pcshell\\shell\\settings\\settingsconfigtask\\lib\\settingsconfigtaskhandler.cpp",
           (_DWORD)a4);
}

```

## disassembly

```asm
0x18001b93c  sub     rsp, 48h
0x18001b940  mov     rax, [rsp+48h]
0x18001b945  mov     [rsp+48h+var_20], rax
0x18001b94a  lea     r8, aPcshellShellSe; "pcshell\\shell\\settings\\settingsconfi"...
0x18001b951  mov     edx, 0C8h
0x18001b956  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x18001b95b  nop
0x18001b95c  add     rsp, 48h
0x18001b960  retn
```
