# wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)

- ea: `0x18002a744`
- end: `0x18002a780`
- name: `?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z`
- size: `60`
- prototype: `int(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18002b274`

## callees

- `0x1800041d4`

## string_xrefs

- `0x18002a767`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  unsigned int v4; // ebx
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  v4 = (unsigned int)a4;
  LODWORD(v6) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    183,
    (int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
    0,
    0,
    retaddr,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18002a744  push    rbx
0x18002a746  sub     rsp, 40h
0x18002a74a  mov     ebx, r9d
0x18002a74d  mov     rax, [rsp+48h]
0x18002a752  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x18002a756  mov     [rsp+48h+var_20], rax; __int64
0x18002a75b  mov     [rsp+48h+var_28], 0; __int64
0x18002a764  xor     r9d, r9d; int
0x18002a767  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002a76e  mov     edx, 0B7h; int
0x18002a773  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002a778  mov     eax, ebx
0x18002a77a  add     rsp, 40h
0x18002a77e  pop     rbx
0x18002a77f  retn
```
