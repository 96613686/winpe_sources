# Microsoft::WRL::Details::RaiseException(long,ulong)

- ea: `0x180007874`
- end: `0x18000788e`
- name: `?RaiseException@Details@WRL@Microsoft@@YAXJK@Z`
- size: `26`
- prototype: `void __fastcall(Microsoft::WRL::Details *__hidden this, int, unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180005918`
- `0x180005990`
- `0x180006860`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007882`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007882`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::RaiseException(Microsoft::WRL::Details *this)
{
  RaiseException((DWORD)this, 1u, 0, 0);
}

```

## disassembly

```asm
0x180007874  sub     rsp, 28h
0x180007878  xor     r9d, r9d; lpArguments
0x18000787b  xor     r8d, r8d; nNumberOfArguments
0x18000787e  lea     edx, [r9+1]; dwExceptionFlags
0x180007882  call    cs:__imp_RaiseException
0x180007888  nop
0x180007889  add     rsp, 28h
0x18000788d  retn
```
