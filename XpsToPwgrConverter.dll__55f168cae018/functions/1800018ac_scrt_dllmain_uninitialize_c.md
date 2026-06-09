# __scrt_dllmain_uninitialize_c

- ea: `0x1800018ac`
- end: `0x1800018dc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001548`

## callees

- `0x1800018ac`
- `0x180001ff8`
- `0x1800020e2`
- `0x180002106`
- `0x180009560`

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
0x1800018ac  sub     rsp, 28h
0x1800018b0  call    __scrt_is_ucrt_dll_in_use
0x1800018b5  test    eax, eax
0x1800018b7  jz      short loc_1800018C9
0x1800018b9  lea     rcx, Table; Table
0x1800018c0  add     rsp, 28h
0x1800018c4  jmp     _execute_onexit_table
0x1800018c9  call    ?GetTrustLevel@?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@impl@winrt@@MEBA?AW4TrustLevel@Foundation@Windows@3@XZ; winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::GetTrustLevel(void)
0x1800018ce  test    eax, eax
0x1800018d0  jnz     short loc_1800018D7
0x1800018d2  call    _o__cexit_0
0x1800018d7  add     rsp, 28h
0x1800018db  retn
```
