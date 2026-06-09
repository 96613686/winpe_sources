# __scrt_dllmain_uninitialize_c

- ea: `0x180002a3c`
- end: `0x180002a6c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800026d8`

## callees

- `0x180002a3c`
- `0x18000327c`
- `0x18000334a`
- `0x18000336e`
- `0x1800143d0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo,winrt::Windows::Management::Update::WindowsSoftwareUpdateApprovalInfo>::GetTrustLevel();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180002a3c  sub     rsp, 28h
0x180002a40  call    __scrt_is_ucrt_dll_in_use
0x180002a45  test    eax, eax
0x180002a47  jz      short loc_180002A59
0x180002a49  lea     rcx, Table; Table
0x180002a50  add     rsp, 28h
0x180002a54  jmp     _execute_onexit_table
0x180002a59  call    ?GetTrustLevel@?$root_implements@UWindowsSoftwareUpdateApprovalInfo@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@MEBA?AW4TrustLevel@Foundation@Windows@3@XZ; winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo,winrt::Windows::Management::Update::WindowsSoftwareUpdateApprovalInfo>::GetTrustLevel(void)
0x180002a5e  test    eax, eax
0x180002a60  jnz     short loc_180002A67
0x180002a62  call    _o__cexit_0
0x180002a67  add     rsp, 28h
0x180002a6b  retn
```
