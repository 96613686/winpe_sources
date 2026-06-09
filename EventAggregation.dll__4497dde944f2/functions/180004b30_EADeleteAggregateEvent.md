# EADeleteAggregateEvent

- ea: `0x180004b30`
- end: `0x180004cc7`
- name: `EADeleteAggregateEvent`
- size: `407`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800013a0`
- `0x180004b30`
- `0x1800072e0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180004ca5`
- `ntdll!RtlNtStatusToDosError` at `0x180004ca5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004be6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004c9d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004be6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004c9d`

## pseudocode

```c
ULONG __fastcall EADeleteAggregateEvent(__int64 a1)
{
  NTSTATUS v2; // eax
  NTSTATUS v3; // ebx
  _DWORD v5[2]; // [rsp+30h] [rbp-69h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-51h] BYREF
  char *v8; // [rsp+58h] [rbp-41h]
  int v9; // [rsp+60h] [rbp-39h]
  int v10; // [rsp+64h] [rbp-35h]
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+70h] [rbp-29h] BYREF
  __int16 *v12; // [rsp+80h] [rbp-19h]
  int v13; // [rsp+88h] [rbp-11h]
  int v14; // [rsp+8Ch] [rbp-Dh]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+90h] [rbp-9h]
  __int64 v16; // [rsp+98h] [rbp-1h]
  _DWORD *v17; // [rsp+A0h] [rbp+7h]
  __int64 v18; // [rsp+A8h] [rbp+Fh]

  if ( (unsigned int)dword_180012000 > 4 )
  {
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_180012008;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v8 = &byte_18000EF47;
    UserData.Reserved = 2;
    v9 = 26;
    v10 = 1;
    v5[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
  }
  v2 = EaDeleteAggregation(a1);
  v3 = v2;
  if ( (unsigned int)dword_180012000 > 4 )
  {
    *(_QWORD *)&EventDescriptor.Id = a1;
    p_EventDescriptor = &EventDescriptor;
    v16 = 8;
    v17 = v5;
    v11.Ptr = (ULONGLONG)off_180012008;
    v5[0] = v2;
    v18 = 4;
    UserData.Ptr = 0x2040B000000LL;
    *(_QWORD *)&UserData.Size = 0;
    v11.Size = *(unsigned __int16 *)off_180012008;
    v12 = &word_18000F1FE;
    v11.Reserved = 2;
    v13 = 48;
    v14 = 1;
    v5[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 4u, &v11);
  }
  return RtlNtStatusToDosError(v3);
}

```

## disassembly

```asm
0x180004b30  push    rbp
0x180004b32  push    rbx
0x180004b33  push    rsi
0x180004b34  push    rdi
0x180004b35  push    r14
0x180004b37  push    r15
0x180004b39  lea     rbp, [rsp-2Fh]
0x180004b3e  sub     rsp, 0C8h
0x180004b45  mov     rax, cs:__security_cookie
0x180004b4c  xor     rax, rsp
0x180004b4f  mov     [rbp+57h+var_40], rax
0x180004b53  mov     eax, cs:dword_180012000
0x180004b59  lea     rdi, _TraceLoggingMetadataEnd
0x180004b60  xor     r14d, r14d
0x180004b63  lea     r15, _TraceLoggingMetadata
0x180004b6a  mov     rsi, rcx
0x180004b6d  cmp     eax, 4
0x180004b70  jbe     short loc_180004BEC
0x180004b72  movzx   eax, cs:word_18000EF3D
0x180004b79  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180004b7d  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180004b80  xor     r9d, r9d; RelatedActivityId
0x180004b83  mov     rax, cs:off_180012008
0x180004b8a  xor     r8d, r8d; ActivityId
0x180004b8d  mov     [rbp+57h+var_A8.Ptr], rax
0x180004b91  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180004b98  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x180004b9c  movzx   eax, word ptr [rax]
0x180004b9f  mov     [rbp+57h+var_A8.Size], eax
0x180004ba2  lea     rax, byte_18000EF47
0x180004ba9  mov     [rbp+57h+var_98], rax
0x180004bad  mov     rax, rdi
0x180004bb0  sub     eax, r15d
0x180004bb3  mov     dword ptr [rbp+57h+var_A8.0Ch], 2
0x180004bba  mov     [rbp+57h+var_90], 1Ah
0x180004bc1  mov     [rbp+57h+var_8C], 1
0x180004bc8  mov     [rbp+57h+var_C0], eax
0x180004bcb  mov     eax, [rbp+57h+var_C0]
0x180004bce  mov     rcx, cs:RegHandle; RegHandle
0x180004bd5  lea     rax, [rbp+57h+var_A8]
0x180004bd9  mov     [rsp+0F0h+UserData], rax; UserData
0x180004bde  mov     [rsp+0F0h+UserDataCount], 2; UserDataCount
0x180004be6  call    cs:__imp_EventWriteTransfer
0x180004bec  mov     rcx, rsi
0x180004bef  call    EaDeleteAggregation
0x180004bf4  mov     ecx, cs:dword_180012000
0x180004bfa  mov     ebx, eax
0x180004bfc  cmp     ecx, 4
0x180004bff  jbe     loc_180004CA3
0x180004c05  mov     qword ptr [rbp+57h+EventDescriptor.Id], rsi
0x180004c09  lea     rax, [rbp+57h+EventDescriptor]
0x180004c0d  mov     [rbp+57h+var_60], rax
0x180004c11  lea     rdx, [rbp+57h+var_A8]; EventDescriptor
0x180004c15  lea     rax, [rbp+57h+var_C0]
0x180004c19  mov     [rbp+57h+var_58], 8
0x180004c21  mov     [rbp+57h+var_50], rax
0x180004c25  sub     edi, r15d
0x180004c28  movzx   eax, cs:word_18000F1F4
0x180004c2f  xor     r9d, r9d; RelatedActivityId
0x180004c32  mov     dword ptr [rbp+57h+var_A8.Ptr+4], eax
0x180004c35  xor     r8d, r8d; ActivityId
0x180004c38  mov     rax, cs:off_180012008
0x180004c3f  mov     [rbp+57h+var_80.Ptr], rax
0x180004c43  mov     [rbp+57h+var_C0], ebx
0x180004c46  mov     [rbp+57h+var_48], 4
0x180004c4e  mov     dword ptr [rbp+57h+var_A8.Ptr], 0B000000h
0x180004c55  mov     qword ptr [rbp+57h+var_A8.Size], r14
0x180004c59  movzx   eax, word ptr [rax]
0x180004c5c  mov     [rbp+57h+var_80.Size], eax
0x180004c5f  lea     rax, word_18000F1FE
0x180004c66  mov     [rbp+57h+var_70], rax
0x180004c6a  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x180004c71  mov     [rbp+57h+var_68], 30h ; '0'
0x180004c78  mov     [rbp+57h+var_64], 1
0x180004c7f  mov     [rbp+57h+var_BC], edi
0x180004c82  mov     eax, [rbp+57h+var_BC]
0x180004c85  mov     rcx, cs:RegHandle; RegHandle
0x180004c8c  lea     rax, [rbp+57h+var_80]
0x180004c90  mov     [rsp+0F0h+UserData], rax; UserData
0x180004c95  mov     [rsp+0F0h+UserDataCount], 4; UserDataCount
0x180004c9d  call    cs:__imp_EventWriteTransfer
0x180004ca3  mov     ecx, ebx; Status
0x180004ca5  call    cs:__imp_RtlNtStatusToDosError
0x180004cab  mov     rcx, [rbp+57h+var_40]
0x180004caf  xor     rcx, rsp; StackCookie
0x180004cb2  call    __security_check_cookie
0x180004cb7  add     rsp, 0C8h
0x180004cbe  pop     r15
0x180004cc0  pop     r14
0x180004cc2  pop     rdi
0x180004cc3  pop     rsi
0x180004cc4  pop     rbx
0x180004cc5  pop     rbp
0x180004cc6  retn
```
