# TraceLogger::WorkloadManagerTryGetHardwareInfoFromBrokerFallback<long>(long &&)

- ea: `0x180024d50`
- end: `0x180024e38`
- name: `??$WorkloadManagerTryGetHardwareInfoFromBrokerFallback@J@TraceLogger@@SAX$$QEAJ@Z`
- size: `232`
- prototype: `int __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022260`

## callees

- `0x1800119b0`
- `0x180024d50`
- `0x180034ef0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180024e1c`
- `ADVAPI32!EventWriteTransfer` at `0x180024e1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall TraceLogger::WorkloadManagerTryGetHardwareInfoFromBrokerFallback<long>(int *a1)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // ecx
  _DWORD v5[2]; // [rsp+30h] [rbp-58h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-40h] BYREF
  __int16 *v8; // [rsp+58h] [rbp-30h]
  int v9; // [rsp+60h] [rbp-28h]
  int v10; // [rsp+64h] [rbp-24h]
  _DWORD *v11; // [rsp+68h] [rbp-20h]
  __int64 v12; // [rsp+70h] [rbp-18h]

  v2 = TraceLogger::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    v3 = *a1;
    v11 = v5;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = *((_QWORD *)v2 + 1);
    v5[0] = v3;
    EventDescriptor.Keyword = 0;
    v12 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v8 = word_18004D8CA;
    UserData.Reserved = 2;
    v9 = 59;
    v10 = 1;
    v5[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    LODWORD(v2) = EventWriteTransfer(*((_QWORD *)v2 + 4), &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (int)v2;
}

```

## disassembly

```asm
0x180024d50  push    rbx
0x180024d52  sub     rsp, 80h
0x180024d59  mov     rax, cs:__security_cookie
0x180024d60  xor     rax, rsp
0x180024d63  mov     [rsp+88h+var_10], rax
0x180024d68  mov     rbx, rcx
0x180024d6b  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x180024d70  mov     r10, rax
0x180024d73  cmp     dword ptr [rax], 5
0x180024d76  jbe     loc_180024E22
0x180024d7c  mov     ecx, [rbx]
0x180024d7e  lea     rax, [rsp+88h+var_58]
0x180024d83  mov     [rsp+88h+var_20], rax
0x180024d88  lea     rdx, [rsp+88h+EventDescriptor]; EventDescriptor
0x180024d8d  movzx   eax, cs:word_18004D8C0
0x180024d94  xor     r9d, r9d; RelatedActivityId
0x180024d97  mov     dword ptr [rsp+88h+EventDescriptor.Level], eax
0x180024d9b  xor     r8d, r8d; ActivityId
0x180024d9e  mov     rax, [r10+8]
0x180024da2  mov     [rsp+88h+var_40.Ptr], rax
0x180024da7  mov     [rsp+88h+var_58], ecx
0x180024dab  xor     ecx, ecx
0x180024dad  mov     [rsp+88h+EventDescriptor.Keyword], rcx
0x180024db2  lea     rcx, _TraceLoggingMetadata
0x180024db9  mov     [rsp+88h+var_18], 4
0x180024dc2  mov     dword ptr [rsp+88h+EventDescriptor.Id], 0B000000h
0x180024dca  movzx   eax, word ptr [rax]
0x180024dcd  mov     [rsp+88h+var_40.Size], eax
0x180024dd1  lea     rax, word_18004D8CA
0x180024dd8  mov     [rsp+88h+var_30], rax
0x180024ddd  lea     rax, _TraceLoggingMetadataEnd
0x180024de4  sub     eax, ecx
0x180024de6  mov     dword ptr [rsp+88h+var_40.0Ch], 2
0x180024dee  mov     [rsp+88h+var_28], 3Bh ; ';'
0x180024df6  mov     [rsp+88h+var_24], 1
0x180024dfe  mov     [rsp+88h+var_54], eax
0x180024e02  mov     eax, [rsp+88h+var_54]
0x180024e06  mov     rcx, [r10+20h]; RegHandle
0x180024e0a  lea     rax, [rsp+88h+var_40]
0x180024e0f  mov     [rsp+88h+UserData], rax; UserData
0x180024e14  mov     [rsp+88h+UserDataCount], 3; UserDataCount
0x180024e1c  call    cs:__imp_EventWriteTransfer
0x180024e22  mov     rcx, [rsp+88h+var_10]
0x180024e27  xor     rcx, rsp; StackCookie
0x180024e2a  call    __security_check_cookie
0x180024e2f  add     rsp, 80h
0x180024e36  pop     rbx
0x180024e37  retn
```
