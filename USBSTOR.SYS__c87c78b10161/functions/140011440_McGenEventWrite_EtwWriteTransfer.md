# McGenEventWrite_EtwWriteTransfer

- ea: `0x140011440`
- end: `0x14001149d`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `93`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400114a4`

## callees

- `0x140011440`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14001148b`
- `ntoskrnl!EtwWriteTransfer` at `0x14001148b`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        const GUID *a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // edx

  v5 = (unsigned __int16 *)qword_14001A028;
  if ( qword_14001A028 )
  {
    UserData->Ptr = qword_14001A028;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EtwWriteTransfer(USBSTOR_DIAG_TRACE_PROVIDER_Context, &EventLogoPerformanceMeasurement, a3, 0, 0xBu, UserData);
}

```

## disassembly

```asm
0x140011440  sub     rsp, 38h
0x140011444  mov     rcx, cs:qword_14001A028
0x14001144b  mov     rax, [rsp+38h+arg_20]
0x140011450  test    rcx, rcx
0x140011453  jnz     short loc_14001145C
0x140011455  mov     [rax], rcx
0x140011458  xor     edx, edx
0x14001145a  jmp     short loc_140011467
0x14001145c  mov     [rax], rcx
0x14001145f  mov     edx, 2
0x140011464  movzx   ecx, word ptr [rcx]
0x140011467  mov     [rax+8], ecx
0x14001146a  xor     r9d, r9d; RelatedActivityId
0x14001146d  mov     [rax+0Ch], edx
0x140011470  lea     rdx, EventLogoPerformanceMeasurement; EventDescriptor
0x140011477  mov     rcx, cs:USBSTOR_DIAG_TRACE_PROVIDER_Context; RegHandle
0x14001147e  mov     [rsp+38h+UserData], rax; UserData
0x140011483  mov     [rsp+38h+UserDataCount], 0Bh; UserDataCount
0x14001148b  call    cs:__imp_EtwWriteTransfer
0x140011492  nop     dword ptr [rax+rax+00h]
0x140011497  add     rsp, 38h
0x14001149b  retn
```
