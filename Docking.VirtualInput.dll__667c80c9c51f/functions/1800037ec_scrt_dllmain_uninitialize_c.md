# __scrt_dllmain_uninitialize_c

- ea: `0x1800037ec`
- end: `0x18000381c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180003488`

## callees

- `0x1800037ec`
- `0x180003f08`
- `0x180003fa2`
- `0x180003fc6`
- `0x1800125a8`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>::invalid_value();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x1800037ec  sub     rsp, 28h
0x1800037f0  call    __scrt_is_ucrt_dll_in_use
0x1800037f5  test    eax, eax
0x1800037f7  jz      short loc_180003809
0x1800037f9  lea     rcx, Table; Table
0x180003800  add     rsp, 28h
0x180003804  jmp     _execute_onexit_table
0x180003809  call    ?invalid_value@?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@SAPEAXXZ; wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>::invalid_value(void)
0x18000380e  test    eax, eax
0x180003810  jnz     short loc_180003817
0x180003812  call    _o__cexit_0
0x180003817  add     rsp, 28h
0x18000381b  retn
```
