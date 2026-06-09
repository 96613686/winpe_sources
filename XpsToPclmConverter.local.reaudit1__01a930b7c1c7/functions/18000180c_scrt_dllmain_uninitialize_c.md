# __scrt_dllmain_uninitialize_c

- ea: `0x18000180c`
- end: `0x18000183c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800013d8`

## callees

- `0x18000180c`
- `0x180001f58`
- `0x180002072`
- `0x180002096`
- `0x18000df00`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::GetTrustLevel();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x18000180c  sub     rsp, 28h
0x180001810  call    __scrt_is_ucrt_dll_in_use
0x180001815  test    eax, eax
0x180001817  jz      short loc_180001829
0x180001819  lea     rcx, Table; Table
0x180001820  add     rsp, 28h
0x180001824  jmp     _execute_onexit_table
0x180001829  call    ?GetTrustLevel@?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@impl@winrt@@MEBA?AW4TrustLevel@Foundation@Windows@3@XZ; winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::GetTrustLevel(void)
0x18000182e  test    eax, eax
0x180001830  jnz     short loc_180001837
0x180001832  call    _o__cexit_0
0x180001837  add     rsp, 28h
0x18000183b  retn
```
