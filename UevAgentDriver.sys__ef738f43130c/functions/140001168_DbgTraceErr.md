# DbgTraceErr

- ea: `0x140001168`
- end: `0x1400011a7`
- name: `DbgTraceErr`
- size: `63`
- prototype: `ULONG __fastcall(PCSTR Format, __int64, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400015c0`
- `0x14000164c`
- `0x1400016ac`
- `0x14000a3c4`
- `0x14000a660`
- `0x14000b160`
- `0x14000b76c`
- `0x14000b854`
- `0x14000b908`

## callees

- `0x140001168`
- `0x140001544`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140001194`
- `ntoskrnl!DbgPrintEx` at `0x140001194`

## pseudocode

```c
ULONG __fastcall DbgTraceErr(PCSTR Format, __int64 a2, __int64 a3)
{
  if ( (Microsoft_User_Experience_Virtualization_Agent_DriverEnableBits & 4) != 0 )
    McTemplateK0s_EtwWriteTransfer(Format, Trace_Error, a3, Format);
  return DbgPrintEx(0x4Du, 2u, Format);
}

```

## disassembly

```asm
0x140001168  push    rbx
0x14000116a  sub     rsp, 20h
0x14000116e  test    cs:Microsoft_User_Experience_Virtualization_Agent_DriverEnableBits, 4
0x140001175  mov     rbx, rcx
0x140001178  jz      short loc_140001189
0x14000117a  mov     r9, rcx
0x14000117d  lea     rdx, Trace_Error
0x140001184  call    McTemplateK0s_EtwWriteTransfer
0x140001189  mov     edx, 2; Level
0x14000118e  mov     r8, rbx; Format
0x140001191  lea     ecx, [rdx+4Bh]; ComponentId
0x140001194  call    cs:__imp_DbgPrintEx
0x14000119b  nop     dword ptr [rax+rax+00h]
0x1400011a0  add     rsp, 20h
0x1400011a4  pop     rbx
0x1400011a5  retn
```
