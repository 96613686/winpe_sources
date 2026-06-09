# __scrt_dllmain_uninitialize_c

- ea: `0x1800016e0`
- end: `0x180001710`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180001248`

## callees

- `0x1800016e0`
- `0x180001c40`
- `0x180001c92`
- `0x180001caa`
- `0x180003040`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  struct _GUID *v0; // rdx
  CAVIFile::CPersistFileImpl *v1; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = CAVIFile::CPersistFileImpl::GetClassID(v1, v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x1800016e0  sub     rsp, 28h
0x1800016e4  call    __scrt_is_ucrt_dll_in_use
0x1800016e9  test    eax, eax
0x1800016eb  jz      short loc_1800016FD
0x1800016ed  lea     rcx, Table; Table
0x1800016f4  add     rsp, 28h
0x1800016f8  jmp     _execute_onexit_table
0x1800016fd  call    ?GetClassID@CPersistFileImpl@CAVIFile@@UEAAJPEAU_GUID@@@Z; CAVIFile::CPersistFileImpl::GetClassID(_GUID *)
0x180001702  test    eax, eax
0x180001704  jnz     short loc_18000170B
0x180001706  call    _o__cexit_0
0x18000170b  add     rsp, 28h
0x18000170f  retn
```
