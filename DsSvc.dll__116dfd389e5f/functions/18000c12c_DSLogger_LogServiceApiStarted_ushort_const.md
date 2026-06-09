# DSLogger::LogServiceApiStarted(ushort const *)

- ea: `0x18000c12c`
- end: `0x18000c152`
- name: `?LogServiceApiStarted@DSLogger@@QEAAXPEBG@Z`
- size: `38`
- prototype: `void __fastcall(DSLogger *__hidden this, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800047f4`
- `0x180005508`
- `0x180007220`
- `0x180007300`
- `0x180007440`
- `0x180007530`
- `0x1800075e0`
- `0x1800076f0`
- `0x180007800`
- `0x180007870`
- `0x1800083c0`

## callees

- `0x18000c12c`
- `0x18000c3e4`

## pseudocode

```c
void __fastcall DSLogger::LogServiceApiStarted(DSLogger *this, const unsigned __int16 *a2)
{
  if ( *(_DWORD *)this )
  {
    if ( (Microsoft_WindowsPhone_DataSharingEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(this, DSServiceApiStartedEvent, a2);
  }
}

```

## disassembly

```asm
0x18000c12c  sub     rsp, 28h
0x18000c130  cmp     dword ptr [rcx], 0
0x18000c133  jz      short loc_18000C14D
0x18000c135  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 40h
0x18000c13c  jz      short loc_18000C14D
0x18000c13e  mov     r8, rdx
0x18000c141  lea     rdx, DSServiceApiStartedEvent
0x18000c148  call    McTemplateU0z_EventWriteTransfer
0x18000c14d  add     rsp, 28h
0x18000c151  retn
```
