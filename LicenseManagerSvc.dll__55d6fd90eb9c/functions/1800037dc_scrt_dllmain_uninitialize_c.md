# __scrt_dllmain_uninitialize_c

- ea: `0x1800037dc`
- end: `0x18000380c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800031b8`

## callees

- `0x180001b50`
- `0x1800037dc`
- `0x180003f4c`
- `0x1800040d2`
- `0x1800040f6`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  HDC v0; // rdx
  WARBIRD_DELAY_LOAD *v1; // rcx
  int v2; // r8d
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = WARBIRD_DELAY_LOAD::SetBkMode(v1, v0, v2);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x1800037dc  sub     rsp, 28h
0x1800037e0  call    __scrt_is_ucrt_dll_in_use
0x1800037e5  test    eax, eax
0x1800037e7  jz      short loc_1800037F9
0x1800037e9  lea     rcx, Table; Table
0x1800037f0  add     rsp, 28h
0x1800037f4  jmp     _execute_onexit_table
0x1800037f9  call    ?SetBkMode@WARBIRD_DELAY_LOAD@@YAHPEAUHDC__@@H@Z; WARBIRD_DELAY_LOAD::SetBkMode(HDC__ *,int)
0x1800037fe  test    eax, eax
0x180003800  jnz     short loc_180003807
0x180003802  call    _o__cexit_0
0x180003807  add     rsp, 28h
0x18000380b  retn
```
