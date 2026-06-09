# _Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey_::_1_::catch$0

- ea: `0x1800292bd`
- end: `0x1800292f3`
- name: `_Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x1800292ce`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`

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
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\directddsdownloadmanagerbase.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800292bd  mov     [rsp+arg_8], rdx
0x1800292c2  push    rbp
0x1800292c3  sub     rsp, 20h
0x1800292c7  mov     rbp, rdx
0x1800292ca  mov     rcx, [rbp+48h]; this
0x1800292ce  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800292d5  mov     edx, 95h; void *
0x1800292da  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800292df  mov     [rbp+50h], eax
0x1800292e2  mov     rax, 0
0x1800292ec  add     rsp, 20h
0x1800292f0  pop     rbp
0x1800292f1  retn
```
