# _Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls_::_1_::catch$12

- ea: `0x18002931d`
- end: `0x180029356`
- name: `_Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls_::_1_::catch$12`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x180029331`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

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
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002931d  mov     [rsp+arg_8], rdx
0x180029322  push    rbp
0x180029323  sub     rsp, 30h
0x180029327  mov     rbp, rdx
0x18002932a  mov     rcx, [rbp+0C8h]; this
0x180029331  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x180029338  mov     edx, 0A3h; void *
0x18002933d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029342  mov     [rbp+30h], eax
0x180029345  mov     rax, 0
0x18002934f  add     rsp, 30h
0x180029353  pop     rbp
0x180029354  retn
```
