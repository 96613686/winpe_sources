# _tlgWriteTransfer_BrowserWriteTransfer

- ea: `0x18000113c`
- end: `0x180001234`
- name: `_tlgWriteTransfer_BrowserWriteTransfer`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000448c`

## callees

- `0x18000113c`
- `0x180004778`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180001223`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180001223`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800011e2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800011e2`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_BrowserWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONG v7; // ebx
  ULONGLONG v10; // rax
  unsigned __int16 *v11; // rdx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-38h] BYREF

  v7 = 0;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v10 = *(_QWORD *)(a2 + 3);
  v11 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v10;
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData[1].Ptr = (ULONGLONG)v11;
  UserData->Reserved = 2;
  UserData[1].Size = *v11;
  UserData[1].Reserved = 1;
  if ( !*(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 1LL)
    && (!(unsigned __int8)IEConfiguration_GetBool(536870937) || IsTelemetryInPrivate()) )
  {
    v7 = 2;
  }
  return EventWriteEx(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, v7, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000113c  push    rbx
0x18000113e  push    rbp
0x18000113f  push    rsi
0x180001140  push    rdi
0x180001141  push    r14
0x180001143  sub     rsp, 50h
0x180001147  movzx   eax, byte ptr [rdx]
0x18000114a  mov     rsi, rcx
0x18000114d  mov     rdi, [rsp+78h+arg_28]
0x180001155  xor     ebx, ebx
0x180001157  shl     eax, 18h
0x18000115a  mov     rbp, r9
0x18000115d  mov     dword ptr [rsp+78h+EventDescriptor.Id], eax
0x180001161  mov     r14, r8
0x180001164  movzx   eax, word ptr [rdx+1]
0x180001168  mov     dword ptr [rsp+78h+EventDescriptor.Level], eax
0x18000116c  mov     rax, [rdx+3]
0x180001170  add     rdx, 0Bh
0x180001174  mov     [rsp+78h+EventDescriptor.Keyword], rax
0x180001179  mov     rax, [rcx+8]
0x18000117d  mov     [rdi], rax
0x180001180  mov     rax, [rcx+8]
0x180001184  movzx   ecx, word ptr [rax]
0x180001187  mov     [rdi+8], ecx
0x18000118a  lea     rcx, _TraceLoggingMetadata
0x180001191  mov     [rdi+10h], rdx
0x180001195  mov     dword ptr [rdi+0Ch], 2
0x18000119c  movzx   eax, word ptr [rdx]
0x18000119f  mov     [rdi+18h], eax
0x1800011a2  lea     rax, _TraceLoggingMetadataEnd
0x1800011a9  sub     eax, ecx
0x1800011ab  mov     dword ptr [rdi+1Ch], 1
0x1800011b2  mov     ecx, cs:_tls_index
0x1800011b8  mov     dword ptr [rsp+78h+arg_28], eax
0x1800011bf  mov     eax, dword ptr [rsp+78h+arg_28]
0x1800011c6  mov     rax, gs:58h
0x1800011cf  mov     edx, 1
0x1800011d4  mov     rax, [rax+rcx*8]
0x1800011d8  cmp     [rdx+rax], bl
0x1800011db  jnz     short loc_1800011FA
0x1800011dd  mov     ecx, 20000019h
0x1800011e2  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800011e8  test    al, al
0x1800011ea  jz      short loc_1800011F5
0x1800011ec  call    ?IsTelemetryInPrivate@@YA_NXZ; IsTelemetryInPrivate(void)
0x1800011f1  test    al, al
0x1800011f3  jz      short loc_1800011FA
0x1800011f5  mov     ebx, 2
0x1800011fa  mov     eax, [rsp+78h+arg_20]
0x180001201  lea     rdx, [rsp+78h+EventDescriptor]; EventDescriptor
0x180001206  mov     rcx, [rsi+20h]; RegHandle
0x18000120a  mov     r9d, ebx; Flags
0x18000120d  mov     [rsp+78h+UserData], rdi; UserData
0x180001212  xor     r8d, r8d; Filter
0x180001215  mov     [rsp+78h+UserDataCount], eax; UserDataCount
0x180001219  mov     [rsp+78h+RelatedActivityId], rbp; RelatedActivityId
0x18000121e  mov     [rsp+78h+ActivityId], r14; ActivityId
0x180001223  call    cs:__imp_EventWriteEx
0x180001229  add     rsp, 50h
0x18000122d  pop     r14
0x18000122f  pop     rdi
0x180001230  pop     rsi
0x180001231  pop     rbp
0x180001232  pop     rbx
0x180001233  retn
```
