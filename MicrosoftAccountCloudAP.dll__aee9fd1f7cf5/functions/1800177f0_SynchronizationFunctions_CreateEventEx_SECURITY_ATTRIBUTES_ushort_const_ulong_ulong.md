# SynchronizationFunctions::_CreateEventEx(_SECURITY_ATTRIBUTES *,ushort const *,ulong,ulong)

- ea: `0x1800177f0`
- end: `0x18001780b`
- name: `?_CreateEventEx@SynchronizationFunctions@@UEAAPEAXPEAU_SECURITY_ATTRIBUTES@@PEBGKK@Z`
- size: `27`
- prototype: `HANDLE __fastcall(SynchronizationFunctions *this, struct _SECURITY_ATTRIBUTES *, const unsigned __int16 *, DWORD, DWORD)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180017804`

## pseudocode

```c
HANDLE __fastcall SynchronizationFunctions::_CreateEventEx(
        SynchronizationFunctions *this,
        struct _SECURITY_ATTRIBUTES *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        DWORD a5)
{
  return CreateEventExW(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1800177f0  mov     eax, r9d
0x1800177f3  mov     r10, r8
0x1800177f6  mov     r9d, [rsp+arg_20]
0x1800177fb  mov     rcx, rdx
0x1800177fe  mov     r8d, eax
0x180017801  mov     rdx, r10
0x180017804  jmp     cs:__imp_CreateEventExW
```
