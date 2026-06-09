# McGenEventWrite_EtwWriteTransfer

- ea: `0x140003608`
- end: `0x140003661`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003668`
- `0x140004964`
- `0x1400049ac`

## callees

- `0x140003608`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000364f`
- `ntoskrnl!EtwWriteTransfer` at `0x14000364f`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_14000B008;
  if ( qword_14000B008 )
  {
    UserData->Ptr = qword_14000B008;
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
  return EtwWriteTransfer(PROV_BINDFLT_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140003608  sub     rsp, 38h
0x14000360c  mov     rcx, cs:qword_14000B008
0x140003613  mov     rax, [rsp+38h+arg_20]
0x140003618  test    rcx, rcx
0x14000361b  jnz     short loc_140003625
0x14000361d  mov     [rax], rcx
0x140003620  xor     r8d, r8d
0x140003623  jmp     short loc_140003631
0x140003625  mov     [rax], rcx
0x140003628  mov     r8d, 2
0x14000362e  movzx   ecx, word ptr [rcx]
0x140003631  mov     [rax+8], ecx
0x140003634  mov     [rax+0Ch], r8d
0x140003638  xor     r8d, r8d; ActivityId
0x14000363b  mov     rcx, cs:PROV_BINDFLT_Context; RegHandle
0x140003642  mov     [rsp+38h+UserData], rax; UserData
0x140003647  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000364c  xor     r9d, r9d; RelatedActivityId
0x14000364f  call    cs:__imp_EtwWriteTransfer
0x140003656  nop     dword ptr [rax+rax+00h]
0x14000365b  add     rsp, 38h
0x14000365f  retn
```
