# _Windows::Settings::CacheSettings_::_1_::catch$86

- ea: `0x180060a79`
- end: `0x180060afa`
- name: `_Windows::Settings::CacheSettings_::_1_::catch$86`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x1800481c0`

## string_xrefs

- `0x180060ad7`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Settings.cpp`
- `0x180060ac5`: `Failed to convert setting from JSON: setting name %ws, json %ws`

## pseudocode

```c
__int64 __fastcall Windows::Settings::CacheSettings_::_1_::catch_86(__int64 a1, __int64 a2)
{
  __int64 v3; // rdx
  const char *v4; // rax

  v3 = a2 + 384;
  if ( *(_QWORD *)(a2 + 408) > 7u )
    v3 = *(_QWORD *)(a2 + 384);
  v4 = (const char *)(a2 + 352);
  if ( *(_QWORD *)(a2 + 376) > 7u )
    v4 = *(const char **)(a2 + 352);
  wil::details::in1diag3::Log_HrMsg(
    *(wil::details::in1diag3 **)(a2 + 840),
    (void *)0x190,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Settings.cpp",
    (const char *)0x8000FFFFLL,
    (int)"Failed to convert setting from JSON: setting name %ws, json %ws",
    v4,
    v3);
  return 0;
}

```

## disassembly

```asm
0x180060a79  mov     [rsp+arg_8], rdx
0x180060a7e  push    rbp
0x180060a7f  sub     rsp, 40h
0x180060a83  mov     rbp, rdx
0x180060a86  lea     rdx, [rbp+180h]
0x180060a8d  cmp     qword ptr [rbp+198h], 7
0x180060a95  cmova   rdx, [rbp+180h]
0x180060a9d  lea     rax, [rbp+160h]
0x180060aa4  cmp     qword ptr [rbp+178h], 7
0x180060aac  cmova   rax, [rbp+160h]
0x180060ab4  mov     rcx, [rbp+348h]; this
0x180060abb  mov     [rsp+48h+var_18], rdx
0x180060ac0  mov     [rsp+48h+var_20], rax; char *
0x180060ac5  lea     rax, aFailedToConver; "Failed to convert setting from JSON: se"...
0x180060acc  mov     qword ptr [rsp+48h+var_28], rax; int
0x180060ad1  mov     r9d, 8000FFFFh; char *
0x180060ad7  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180060ade  mov     edx, 190h; void *
0x180060ae3  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180060ae8  nop
0x180060ae9  mov     rax, 0
0x180060af3  add     rsp, 40h
0x180060af7  pop     rbp
0x180060af8  retn
```
