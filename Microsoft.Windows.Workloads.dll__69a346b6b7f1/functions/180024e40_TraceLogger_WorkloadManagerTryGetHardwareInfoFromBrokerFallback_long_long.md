# TraceLogger::WorkloadManagerTryGetHardwareInfoFromBrokerFallback<long &>(long &)

- ea: `0x180024e40`
- end: `0x180024f28`
- name: `??$WorkloadManagerTryGetHardwareInfoFromBrokerFallback@AEAJ@TraceLogger@@SAXAEAJ@Z`
- size: `232`
- prototype: `int __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022260`

## callees

- `0x1800119b0`
- `0x180024e40`
- `0x180034ef0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180024f0c`
- `ADVAPI32!EventWriteTransfer` at `0x180024f0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall TraceLogger::WorkloadManagerTryGetHardwareInfoFromBrokerFallback<long &>(int *a1)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // ecx
  _DWORD v5[2]; // [rsp+30h] [rbp-58h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-40h] BYREF
  char *v8; // [rsp+58h] [rbp-30h]
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
    v8 = byte_18004D883;
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
0x180024e40  push    rbx
0x180024e42  sub     rsp, 80h
0x180024e49  mov     rax, cs:__security_cookie
0x180024e50  xor     rax, rsp
0x180024e53  mov     [rsp+88h+var_10], rax
0x180024e58  mov     rbx, rcx
0x180024e5b  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x180024e60  mov     r10, rax
0x180024e63  cmp     dword ptr [rax], 5
0x180024e66  jbe     loc_180024F12
0x180024e6c  mov     ecx, [rbx]
0x180024e6e  lea     rax, [rsp+88h+var_58]
0x180024e73  mov     [rsp+88h+var_20], rax
0x180024e78  lea     rdx, [rsp+88h+EventDescriptor]; EventDescriptor
0x180024e7d  movzx   eax, cs:word_18004D879
0x180024e84  xor     r9d, r9d; RelatedActivityId
0x180024e87  mov     dword ptr [rsp+88h+EventDescriptor.Level], eax
0x180024e8b  xor     r8d, r8d; ActivityId
0x180024e8e  mov     rax, [r10+8]
0x180024e92  mov     [rsp+88h+var_40.Ptr], rax
0x180024e97  mov     [rsp+88h+var_58], ecx
0x180024e9b  xor     ecx, ecx
0x180024e9d  mov     [rsp+88h+EventDescriptor.Keyword], rcx
0x180024ea2  lea     rcx, _TraceLoggingMetadata
0x180024ea9  mov     [rsp+88h+var_18], 4
0x180024eb2  mov     dword ptr [rsp+88h+EventDescriptor.Id], 0B000000h
0x180024eba  movzx   eax, word ptr [rax]
0x180024ebd  mov     [rsp+88h+var_40.Size], eax
0x180024ec1  lea     rax, byte_18004D883
0x180024ec8  mov     [rsp+88h+var_30], rax
0x180024ecd  lea     rax, _TraceLoggingMetadataEnd
0x180024ed4  sub     eax, ecx
0x180024ed6  mov     dword ptr [rsp+88h+var_40.0Ch], 2
0x180024ede  mov     [rsp+88h+var_28], 3Bh ; ';'
0x180024ee6  mov     [rsp+88h+var_24], 1
0x180024eee  mov     [rsp+88h+var_54], eax
0x180024ef2  mov     eax, [rsp+88h+var_54]
0x180024ef6  mov     rcx, [r10+20h]; RegHandle
0x180024efa  lea     rax, [rsp+88h+var_40]
0x180024eff  mov     [rsp+88h+UserData], rax; UserData
0x180024f04  mov     [rsp+88h+UserDataCount], 3; UserDataCount
0x180024f0c  call    cs:__imp_EventWriteTransfer
0x180024f12  mov     rcx, [rsp+88h+var_10]
0x180024f17  xor     rcx, rsp; StackCookie
0x180024f1a  call    __security_check_cookie
0x180024f1f  add     rsp, 80h
0x180024f26  pop     rbx
0x180024f27  retn
```
