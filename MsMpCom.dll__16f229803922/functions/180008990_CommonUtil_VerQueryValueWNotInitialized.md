# CommonUtil::VerQueryValueWNotInitialized

- ea: `0x180008990`
- end: `0x1800089a6`
- name: `CommonUtil::VerQueryValueWNotInitialized`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180008999`
- `KERNEL32!SetLastError` at `0x180008999`

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
0x180008990  sub     rsp, 28h
0x180008994  mov     ecx, 78h ; 'x'; dwErrCode
0x180008999  call    cs:__imp_SetLastError
0x18000899f  xor     eax, eax
0x1800089a1  add     rsp, 28h
0x1800089a5  retn
```
