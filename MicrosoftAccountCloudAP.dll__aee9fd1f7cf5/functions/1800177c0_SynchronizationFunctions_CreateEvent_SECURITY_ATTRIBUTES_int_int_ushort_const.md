# SynchronizationFunctions::_CreateEvent(_SECURITY_ATTRIBUTES *,int,int,ushort const *)

- ea: `0x1800177c0`
- end: `0x1800177db`
- name: `?_CreateEvent@SynchronizationFunctions@@UEAAPEAXPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z`
- size: `27`
- prototype: `HANDLE __fastcall(SynchronizationFunctions *this, struct _SECURITY_ATTRIBUTES *, BOOL, BOOL, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800177d4`

## pseudocode

```c
HANDLE __fastcall SynchronizationFunctions::_CreateEvent(
        SynchronizationFunctions *this,
        struct _SECURITY_ATTRIBUTES *a2,
        BOOL a3,
        BOOL a4,
        const unsigned __int16 *a5)
{
  return CreateEventW(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1800177c0  mov     eax, r9d
0x1800177c3  mov     r10d, r8d
0x1800177c6  mov     r9, [rsp+arg_20]
0x1800177cb  mov     rcx, rdx
0x1800177ce  mov     r8d, eax
0x1800177d1  mov     edx, r10d
0x1800177d4  jmp     cs:__imp_CreateEventW
```
