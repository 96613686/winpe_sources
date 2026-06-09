# _tlgWriteTransfer_BrowserWriteTransfer

- ea: `0x1800010c4`
- end: `0x1800011bc`
- name: `_tlgWriteTransfer_BrowserWriteTransfer`
- size: `248`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `19`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001010`
- `0x1800011c4`
- `0x180001284`
- `0x1800014ec`
- `0x18000159c`
- `0x180001680`
- `0x1800017a0`
- `0x18000187c`
- `0x1800019a8`
- `0x180001a58`
- `0x180001b78`
- `0x180001c64`
- `0x180001d04`
- `0x180001e20`
- `0x180001eec`
- `0x18000206c`
- `0x1800021b8`
- `0x1800022d0`
- `0x1800023bc`

## callees

- `0x1800010c4`
- `0x1800248f0`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000116a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000116a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x1800011ab`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x1800011ab`

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
  if ( !*(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL)
    && (!(unsigned __int8)IEConfiguration_GetBool(536870937) || IsTelemetryInPrivate()) )
  {
    v7 = 2;
  }
  return EventWriteEx(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, v7, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800010c4  push    rbx
0x1800010c6  push    rbp
0x1800010c7  push    rsi
0x1800010c8  push    rdi
0x1800010c9  push    r14
0x1800010cb  sub     rsp, 50h
0x1800010cf  movzx   eax, byte ptr [rdx]
0x1800010d2  mov     rsi, rcx
0x1800010d5  mov     rdi, [rsp+78h+arg_28]
0x1800010dd  xor     ebx, ebx
0x1800010df  shl     eax, 18h
0x1800010e2  mov     rbp, r9
0x1800010e5  mov     dword ptr [rsp+78h+EventDescriptor.Id], eax
0x1800010e9  mov     r14, r8
0x1800010ec  movzx   eax, word ptr [rdx+1]
0x1800010f0  mov     dword ptr [rsp+78h+EventDescriptor.Level], eax
0x1800010f4  mov     rax, [rdx+3]
0x1800010f8  add     rdx, 0Bh
0x1800010fc  mov     [rsp+78h+EventDescriptor.Keyword], rax
0x180001101  mov     rax, [rcx+8]
0x180001105  mov     [rdi], rax
0x180001108  mov     rax, [rcx+8]
0x18000110c  movzx   ecx, word ptr [rax]
0x18000110f  mov     [rdi+8], ecx
0x180001112  lea     rcx, _TraceLoggingMetadata
0x180001119  mov     [rdi+10h], rdx
0x18000111d  mov     dword ptr [rdi+0Ch], 2
0x180001124  movzx   eax, word ptr [rdx]
0x180001127  mov     [rdi+18h], eax
0x18000112a  lea     rax, _TraceLoggingMetadataEnd
0x180001131  sub     eax, ecx
0x180001133  mov     dword ptr [rdi+1Ch], 1
0x18000113a  mov     ecx, cs:_tls_index
0x180001140  mov     dword ptr [rsp+78h+arg_28], eax
0x180001147  mov     eax, dword ptr [rsp+78h+arg_28]
0x18000114e  mov     rax, gs:58h
0x180001157  mov     edx, 8
0x18000115c  mov     rax, [rax+rcx*8]
0x180001160  cmp     [rdx+rax], bl
0x180001163  jnz     short loc_180001182
0x180001165  mov     ecx, 20000019h
0x18000116a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180001170  test    al, al
0x180001172  jz      short loc_18000117D
0x180001174  call    ?IsTelemetryInPrivate@@YA_NXZ; IsTelemetryInPrivate(void)
0x180001179  test    al, al
0x18000117b  jz      short loc_180001182
0x18000117d  mov     ebx, 2
0x180001182  mov     eax, [rsp+78h+arg_20]
0x180001189  lea     rdx, [rsp+78h+EventDescriptor]; EventDescriptor
0x18000118e  mov     rcx, [rsi+20h]; RegHandle
0x180001192  mov     r9d, ebx; Flags
0x180001195  mov     [rsp+78h+UserData], rdi; UserData
0x18000119a  xor     r8d, r8d; Filter
0x18000119d  mov     [rsp+78h+UserDataCount], eax; UserDataCount
0x1800011a1  mov     [rsp+78h+RelatedActivityId], rbp; RelatedActivityId
0x1800011a6  mov     [rsp+78h+ActivityId], r14; ActivityId
0x1800011ab  call    cs:__imp_EventWriteEx
0x1800011b1  add     rsp, 50h
0x1800011b5  pop     r14
0x1800011b7  pop     rdi
0x1800011b8  pop     rsi
0x1800011b9  pop     rbp
0x1800011ba  pop     rbx
0x1800011bb  retn
```
