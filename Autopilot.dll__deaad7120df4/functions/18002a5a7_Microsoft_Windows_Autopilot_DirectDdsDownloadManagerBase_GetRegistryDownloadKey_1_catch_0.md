# _Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey_::_1_::catch$0

- ea: `0x18002a5a7`
- end: `0x18002a5dd`
- name: `_Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x18002a5b8`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x95,
                           (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\directddsdownloadmanagerbase.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002a5a7  mov     [rsp+arg_8], rdx
0x18002a5ac  push    rbp
0x18002a5ad  sub     rsp, 20h
0x18002a5b1  mov     rbp, rdx
0x18002a5b4  mov     rcx, [rbp+48h]; this
0x18002a5b8  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002a5bf  mov     edx, 95h; void *
0x18002a5c4  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a5c9  mov     [rbp+50h], eax
0x18002a5cc  mov     rax, 0
0x18002a5d6  add     rsp, 20h
0x18002a5da  pop     rbp
0x18002a5db  retn
```
