# Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)

- ea: `0x18000bdc0`
- end: `0x18000bdd8`
- name: `?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180006ab0`
- `0x180006cb4`
- `0x18000f060`
- `0x18000f7d0`
- `0x18000fdd0`
- `0x180010cc0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdc8`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(
        __int64 a1)
{
  return CloseHandle(*(HANDLE *)(a1 + 8));
}

```

## disassembly

```asm
0x18000bdc0  sub     rsp, 28h
0x18000bdc4  mov     rcx, [rcx+8]; hObject
0x18000bdc8  call    cs:__imp_CloseHandle
0x18000bdce  test    eax, eax
0x18000bdd0  setnz   al
0x18000bdd3  add     rsp, 28h
0x18000bdd7  retn
```
