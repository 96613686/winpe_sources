# DMCSP_DevDetail_GetDeviceName

- ea: `0x1800085a0`
- end: `0x1800085b9`
- name: `DMCSP_DevDetail_GetDeviceName`
- size: `25`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800080f8`

## string_xrefs

- `0x1800085a6`: `ComputerName`
- `0x1800085ad`: `SYSTEM\CurrentControlSet\Control\ComputerName\ComputerName`

## pseudocode

```c
__int64 __fastcall DMCSP_DevDetail_GetDeviceName(unsigned int a1, unsigned __int16 *a2)
{
  return RegLookupHelper(L"SYSTEM\\CurrentControlSet\\Control\\ComputerName\\ComputerName", L"ComputerName", a1, a2);
}

```

## disassembly

```asm
0x1800085a0  mov     r9, rdx; unsigned __int16 *
0x1800085a3  mov     r8d, ecx; unsigned int
0x1800085a6  lea     rdx, aComputername; "ComputerName"
0x1800085ad  lea     rcx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Com"...
0x1800085b4  jmp     ?RegLookupHelper@@YAJPEBG0KPEAG@Z; RegLookupHelper(ushort const *,ushort const *,ulong,ushort *)
```
