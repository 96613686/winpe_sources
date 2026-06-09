# SyspartGetSystemPartition

- ea: `0x140013ac0`
- end: `0x140013b3f`
- name: `SyspartGetSystemPartition`
- size: `127`
- prototype: `__int64 __fastcall(void *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140002c14`

## callees

- `0x140013628`
- `0x140013738`
- `0x140013ac0`
- `0x14001c844`

## string_xrefs

- `0x140013af4`: `System Partition Query failed. Will attempt Direct path. Status: %x`
- `0x140013b23`: `System Partition Path: %ws`

## pseudocode

```c
__int64 __fastcall SyspartGetSystemPartition(void *a1, unsigned int a2, __int64 a3)
{
  int SystemInformationString; // eax
  int SystemDeviceName; // ebx

  SystemInformationString = SiQuerySystemInformationString(MaxSystemInfoClass, a1);
  SystemDeviceName = SystemInformationString;
  if ( SystemInformationString >= 0
    || SystemInformationString != -1073741789
    && (SiLogMessage(
          3,
          L"System Partition Query failed. Will attempt Direct path. Status: %x",
          (unsigned int)SystemInformationString),
        SystemDeviceName = SiGetSystemDeviceName(SiGetSystemPartition, a1, a2, a3),
        SystemDeviceName >= 0) )
  {
    SiLogMessage(2, L"System Partition Path: %ws", a1);
  }
  return (unsigned int)SystemDeviceName;
}

```

## disassembly

```asm
0x140013ac0  push    rbx
0x140013ac2  push    rbp
0x140013ac3  push    rsi
0x140013ac4  push    rdi
0x140013ac5  sub     rsp, 28h
0x140013ac9  mov     rsi, r8
0x140013acc  mov     r9, r8
0x140013acf  mov     r8d, edx
0x140013ad2  mov     ebp, edx
0x140013ad4  mov     rdx, rcx; void *
0x140013ad7  mov     rdi, rcx
0x140013ada  mov     ecx, 62h ; 'b'; SystemInformationClass
0x140013adf  call    SiQuerySystemInformationString
0x140013ae4  mov     ebx, eax
0x140013ae6  test    eax, eax
0x140013ae8  jns     short loc_140013B20
0x140013aea  cmp     eax, 0C0000023h
0x140013aef  jz      short loc_140013B34
0x140013af1  mov     r8d, eax
0x140013af4  lea     rdx, aSystemPartitio_1; "System Partition Query failed. Will att"...
0x140013afb  mov     ecx, 3
0x140013b00  call    SiLogMessage
0x140013b05  mov     r9, rsi
0x140013b08  lea     rcx, SiGetSystemPartition
0x140013b0f  mov     r8d, ebp
0x140013b12  mov     rdx, rdi
0x140013b15  call    SiGetSystemDeviceName
0x140013b1a  mov     ebx, eax
0x140013b1c  test    eax, eax
0x140013b1e  js      short loc_140013B34
0x140013b20  mov     r8, rdi
0x140013b23  lea     rdx, aSystemPartitio_0; "System Partition Path: %ws"
0x140013b2a  mov     ecx, 2
0x140013b2f  call    SiLogMessage
0x140013b34  mov     eax, ebx
0x140013b36  add     rsp, 28h
0x140013b3a  pop     rdi
0x140013b3b  pop     rsi
0x140013b3c  pop     rbp
0x140013b3d  pop     rbx
0x140013b3e  retn
```
