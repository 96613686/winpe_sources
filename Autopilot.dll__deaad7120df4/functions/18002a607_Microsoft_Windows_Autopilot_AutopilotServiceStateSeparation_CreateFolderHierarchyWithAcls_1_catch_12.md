# _Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls_::_1_::catch$12

- ea: `0x18002a607`
- end: `0x18002a640`
- name: `_Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls_::_1_::catch$12`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x18002a61b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls_::_1_::catch_12(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 200),
                           (void *)0xA3,
                           (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002a607  mov     [rsp+arg_8], rdx
0x18002a60c  push    rbp
0x18002a60d  sub     rsp, 30h
0x18002a611  mov     rbp, rdx
0x18002a614  mov     rcx, [rbp+0C8h]; this
0x18002a61b  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002a622  mov     edx, 0A3h; void *
0x18002a627  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a62c  mov     [rbp+30h], eax
0x18002a62f  mov     rax, 0
0x18002a639  add     rsp, 30h
0x18002a63d  pop     rbp
0x18002a63e  retn
```
