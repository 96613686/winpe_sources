# SyspartGetFirmwarePartition

- ea: `0x140013814`
- end: `0x140013893`
- name: `SyspartGetFirmwarePartition`
- size: `127`
- prototype: `__int64 __fastcall(void *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001c458`

## callees

- `0x140013628`
- `0x140013738`
- `0x140013814`
- `0x14001c844`

## string_xrefs

- `0x140013877`: `System Firmware Partition Path: %ws`
- `0x140013848`: `Firmware Partition Query failed. Will attempt Direct path. Status: %x`

## pseudocode

```c
__int64 __fastcall SyspartGetFirmwarePartition(void *a1, unsigned int a2, __int64 a3)
{
  int SystemInformationString; // eax
  int SystemDeviceName; // ebx

  SystemInformationString = SiQuerySystemInformationString(SystemWatchDogTimerInformation|0x80, a1);
  SystemDeviceName = SystemInformationString;
  if ( SystemInformationString >= 0
    || SystemInformationString != -1073741789
    && (SiLogMessage(
          3,
          L"Firmware Partition Query failed. Will attempt Direct path. Status: %x",
          (unsigned int)SystemInformationString),
        SystemDeviceName = SiGetSystemDeviceName(SiGetFirmwareSystemPartition, a1, a2, a3),
        SystemDeviceName >= 0) )
  {
    SiLogMessage(2, L"System Firmware Partition Path: %ws", a1);
  }
  return (unsigned int)SystemDeviceName;
}

```

## disassembly

```asm
0x140013814  push    rbx
0x140013816  push    rbp
0x140013817  push    rsi
0x140013818  push    rdi
0x140013819  sub     rsp, 28h
0x14001381d  mov     rsi, r8
0x140013820  mov     r9, r8
0x140013823  mov     r8d, edx
0x140013826  mov     ebp, edx
0x140013828  mov     rdx, rcx; void *
0x14001382b  mov     rdi, rcx
0x14001382e  mov     ecx, 0C8h; SystemInformationClass
0x140013833  call    SiQuerySystemInformationString
0x140013838  mov     ebx, eax
0x14001383a  test    eax, eax
0x14001383c  jns     short loc_140013874
0x14001383e  cmp     eax, 0C0000023h
0x140013843  jz      short loc_140013888
0x140013845  mov     r8d, eax
0x140013848  lea     rdx, aFirmwarePartit; "Firmware Partition Query failed. Will a"...
0x14001384f  mov     ecx, 3
0x140013854  call    SiLogMessage
0x140013859  mov     r9, rsi
0x14001385c  lea     rcx, SiGetFirmwareSystemPartition
0x140013863  mov     r8d, ebp
0x140013866  mov     rdx, rdi
0x140013869  call    SiGetSystemDeviceName
0x14001386e  mov     ebx, eax
0x140013870  test    eax, eax
0x140013872  js      short loc_140013888
0x140013874  mov     r8, rdi
0x140013877  lea     rdx, aSystemFirmware; "System Firmware Partition Path: %ws"
0x14001387e  mov     ecx, 2
0x140013883  call    SiLogMessage
0x140013888  mov     eax, ebx
0x14001388a  add     rsp, 28h
0x14001388e  pop     rdi
0x14001388f  pop     rsi
0x140013890  pop     rbp
0x140013891  pop     rbx
0x140013892  retn
```
