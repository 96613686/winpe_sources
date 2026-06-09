# __scrt_dllmain_uninitialize_c

- ea: `0x1800016bc`
- end: `0x1800016ec`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001358`

## callees

- `0x1800016bc`
- `0x180001e78`
- `0x180001f42`
- `0x180001f66`
- `0x1800077d0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = winrt::impl::root_implements<winrt::Windows::Internal::WaasMedicDocked::implementation::WaaSAssessmentHelper,winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentHelper>::GetTrustLevel();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x1800016bc  sub     rsp, 28h
0x1800016c0  call    __scrt_is_ucrt_dll_in_use
0x1800016c5  test    eax, eax
0x1800016c7  jz      short loc_1800016D9
0x1800016c9  lea     rcx, Table; Table
0x1800016d0  add     rsp, 28h
0x1800016d4  jmp     _execute_onexit_table
0x1800016d9  call    ?GetTrustLevel@?$root_implements@VWaaSAssessmentHelper@implementation@WaasMedicDocked@Internal@Windows@winrt@@U13456@@impl@winrt@@MEBA?AW4TrustLevel@Foundation@Windows@3@XZ; winrt::impl::root_implements<winrt::Windows::Internal::WaasMedicDocked::implementation::WaaSAssessmentHelper,winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentHelper>::GetTrustLevel(void)
0x1800016de  test    eax, eax
0x1800016e0  jnz     short loc_1800016E7
0x1800016e2  call    _o__cexit_0
0x1800016e7  add     rsp, 28h
0x1800016eb  retn
```
