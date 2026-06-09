# __scrt_dllmain_uninitialize_c

- ea: `0x180001c0c`
- end: `0x180001c3c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800018a8`

## callees

- `0x180001c0c`
- `0x180002378`
- `0x18000260a`
- `0x18000262e`
- `0x180009580`

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
0x180001c0c  sub     rsp, 28h
0x180001c10  call    __scrt_is_ucrt_dll_in_use
0x180001c15  test    eax, eax
0x180001c17  jz      short loc_180001C29
0x180001c19  lea     rcx, Table; Table
0x180001c20  add     rsp, 28h
0x180001c24  jmp     _execute_onexit_table
0x180001c29  call    ?SetBkMode@WARBIRD_DELAY_LOAD@@YAHPEAUHDC__@@H@Z; WARBIRD_DELAY_LOAD::SetBkMode(HDC__ *,int)
0x180001c2e  test    eax, eax
0x180001c30  jnz     short loc_180001C37
0x180001c32  call    _o__cexit_0
0x180001c37  add     rsp, 28h
0x180001c3b  retn
```
