# Windows::Internal::ComTaskPool::CTaskWrapper__lambda_44dec2ec29b2d12d628edc675583ab93___::Run

- ea: `0x18001aa70`
- end: `0x18001aaa8`
- name: `Windows::Internal::ComTaskPool::CTaskWrapper__lambda_44dec2ec29b2d12d628edc675583ab93___::Run`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001aa9d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001aa9d`

## string_xrefs

- `0x18001aa78`: `LastAccessTime`

## pseudocode

```c
LSTATUS __fastcall Windows::Internal::ComTaskPool::CTaskWrapper__lambda_44dec2ec29b2d12d628edc675583ab93___::Run(
        __int64 a1)
{
  return RegSetValueExW(*(HKEY *)(*(_QWORD *)(a1 + 32) + 48LL), L"LastAccessTime", 0, 0xBu, (const BYTE *)(a1 + 16), 8u);
}

```

## disassembly

```asm
0x18001aa70  sub     rsp, 38h
0x18001aa74  mov     rax, [rcx+20h]
0x18001aa78  lea     rdx, Value; "LastAccessTime"
0x18001aa7f  add     rcx, 10h
0x18001aa83  mov     [rsp+38h+cbData], 8; cbData
0x18001aa8b  mov     [rsp+38h+lpData], rcx; lpData
0x18001aa90  mov     r9d, 0Bh; dwType
0x18001aa96  xor     r8d, r8d; Reserved
0x18001aa99  mov     rcx, [rax+30h]; hKey
0x18001aa9d  call    cs:__imp_RegSetValueExW
0x18001aaa3  add     rsp, 38h
0x18001aaa7  retn
```
