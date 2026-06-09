# HttpCreateRequestQueue

- ea: `0x1800082a0`
- end: `0x1800082c9`
- name: `HttpCreateRequestQueue`
- size: `41`
- prototype: `ULONG __stdcall(HTTPAPI_VERSION Version, PCWSTR Name, PSECURITY_ATTRIBUTES SecurityAttributes, ULONG Flags, PHANDLE RequestQueueHandle)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003e20`

## pseudocode

```c
ULONG __stdcall HttpCreateRequestQueue(
        HTTPAPI_VERSION Version,
        PCWSTR Name,
        PSECURITY_ATTRIBUTES SecurityAttributes,
        ULONG Flags,
        PHANDLE RequestQueueHandle)
{
  return HttpCreateRequestQueueEx(
           *(_DWORD *)&Version,
           Name,
           (__int64)SecurityAttributes,
           Flags,
           0,
           0,
           RequestQueueHandle);
}

```

## disassembly

```asm
0x1800082a0  sub     rsp, 48h
0x1800082a4  mov     rax, [rsp+48h+RequestQueueHandle]
0x1800082a9  mov     [rsp+48h+var_18], rax; __int64
0x1800082ae  mov     [rsp+48h+var_20], 0; __int64
0x1800082b7  mov     [rsp+48h+var_28], 0; int
0x1800082bf  call    HttpCreateRequestQueueEx
0x1800082c4  add     rsp, 48h
0x1800082c8  retn
```
