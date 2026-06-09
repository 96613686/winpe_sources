# LSA_SSPI_HANDLE_rundown

- ea: `0x180001bc0`
- end: `0x180001be5`
- name: `LSA_SSPI_HANDLE_rundown`
- size: `37`
- prototype: `__int64 (*())(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001b90`
- `0x180002330`

## callees

- `0x180001bc0`
- `0x180004010`

## pseudocode

```c
__int64 (*LSA_SSPI_HANDLE_rundown())(void)
{
  __int64 (*result)(void); // rax

  result = (__int64 (*)(void))gLsapSspiExtension;
  if ( gLsapSspiExtension )
  {
    result = *(__int64 (**)(void))(gLsapSspiExtension + 16);
    if ( result )
      return (__int64 (*)(void))result();
  }
  return result;
}

```

## disassembly

```asm
0x180001bc0  sub     rsp, 28h
0x180001bc4  mov     rax, cs:gLsapSspiExtension
0x180001bcb  test    rax, rax
0x180001bce  jz      short loc_180001BD9
0x180001bd0  mov     rax, [rax+10h]
0x180001bd4  test    rax, rax
0x180001bd7  jnz     short loc_180001BDE
0x180001bd9  add     rsp, 28h
0x180001bdd  retn
0x180001bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001be3  jmp     short loc_180001BD9
```
