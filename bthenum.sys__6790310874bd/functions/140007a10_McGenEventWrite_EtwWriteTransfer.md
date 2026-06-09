# McGenEventWrite_EtwWriteTransfer

- ea: `0x140007a10`
- end: `0x140007a70`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `96`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x140007a78`

## callees

- `0x140007a10`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140007a5e`
- `ntoskrnl!EtwWriteTransfer` at `0x140007a5e`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  unsigned int v6; // edx

  v5 = (unsigned __int16 *)qword_140015058;
  if ( qword_140015058 )
  {
    UserData->Ptr = qword_140015058;
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
  return EtwWriteTransfer(BTH_POLICY_PROVIDER_Context, &PolicyServiceBlockAudit, 0, 0, 6u, UserData);
}

```

## disassembly

```asm
0x140007a10  sub     rsp, 38h
0x140007a14  mov     rcx, cs:qword_140015058
0x140007a1b  mov     rax, [rsp+38h+arg_20]
0x140007a20  test    rcx, rcx
0x140007a23  jnz     short loc_140007A2C
0x140007a25  mov     [rax], rcx
0x140007a28  xor     edx, edx
0x140007a2a  jmp     short loc_140007A37
0x140007a2c  mov     [rax], rcx
0x140007a2f  mov     edx, 2
0x140007a34  movzx   ecx, word ptr [rcx]
0x140007a37  mov     [rax+8], ecx
0x140007a3a  xor     r9d, r9d; RelatedActivityId
0x140007a3d  mov     [rax+0Ch], edx
0x140007a40  xor     r8d, r8d; ActivityId
0x140007a43  mov     rcx, cs:BTH_POLICY_PROVIDER_Context; RegHandle
0x140007a4a  lea     rdx, _PolicyServiceBlockAudit; EventDescriptor
0x140007a51  mov     [rsp+38h+UserData], rax; UserData
0x140007a56  mov     [rsp+38h+UserDataCount], 6; UserDataCount
0x140007a5e  call    cs:__imp_EtwWriteTransfer
0x140007a65  nop     dword ptr [rax+rax+00h]
0x140007a6a  add     rsp, 38h
0x140007a6e  retn
```
