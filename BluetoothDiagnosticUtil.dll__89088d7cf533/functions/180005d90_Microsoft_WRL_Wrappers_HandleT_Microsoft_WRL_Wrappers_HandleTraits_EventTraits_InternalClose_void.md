# Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)

- ea: `0x180005d90`
- end: `0x180005daf`
- name: `?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ`
- size: `31`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000378c`
- `0x1800087a0`
- `0x180008f80`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180005d98`
- `KERNEL32!CloseHandle` at `0x180005d98`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(
        __int64 a1)
{
  return CloseHandle(*(HANDLE *)(a1 + 8));
}

```

## disassembly

```asm
0x180005d90  sub     rsp, 28h
0x180005d94  mov     rcx, [rcx+8]; hObject
0x180005d98  call    cs:__imp_CloseHandle
0x180005d9f  nop     dword ptr [rax+rax+00h]
0x180005da4  test    eax, eax
0x180005da6  setnz   al
0x180005da9  add     rsp, 28h
0x180005dad  retn
```
