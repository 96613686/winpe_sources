# CommonUtil::VerQueryValueWNotInitialized

- ea: `0x140010200`
- end: `0x140010216`
- name: `CommonUtil::VerQueryValueWNotInitialized`
- size: `22`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010209`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010209`

## pseudocode

```c
__int64 CommonUtil::VerQueryValueWNotInitialized()
{
  SetLastError(0x78u);
  return 0;
}

```

## disassembly

```asm
0x140010200  sub     rsp, 28h
0x140010204  mov     ecx, 78h ; 'x'; dwErrCode
0x140010209  call    cs:__imp_SetLastError
0x14001020f  xor     eax, eax
0x140010211  add     rsp, 28h
0x140010215  retn
```
