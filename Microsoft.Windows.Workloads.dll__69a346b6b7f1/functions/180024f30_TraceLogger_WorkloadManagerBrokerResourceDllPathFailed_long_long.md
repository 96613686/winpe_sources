# TraceLogger::WorkloadManagerBrokerResourceDllPathFailed<long &>(long &)

- ea: `0x180024f30`
- end: `0x180025018`
- name: `??$WorkloadManagerBrokerResourceDllPathFailed@AEAJ@TraceLogger@@SAXAEAJ@Z`
- size: `232`
- prototype: `int __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022260`

## callees

- `0x1800119b0`
- `0x180024f30`
- `0x180034ef0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180024ffc`
- `ADVAPI32!EventWriteTransfer` at `0x180024ffc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall TraceLogger::WorkloadManagerBrokerResourceDllPathFailed<long &>(int *a1)
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
    v8 = word_18004D7A2;
    UserData.Reserved = 2;
    v9 = 50;
    v10 = 1;
    v5[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    LODWORD(v2) = EventWriteTransfer(*((_QWORD *)v2 + 4), &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (int)v2;
}

```

## disassembly

```asm
0x180024f30  push    rbx
0x180024f32  sub     rsp, 80h
0x180024f39  mov     rax, cs:__security_cookie
0x180024f40  xor     rax, rsp
0x180024f43  mov     [rsp+88h+var_10], rax
0x180024f48  mov     rbx, rcx
0x180024f4b  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x180024f50  mov     r10, rax
0x180024f53  cmp     dword ptr [rax], 5
0x180024f56  jbe     loc_180025002
0x180024f5c  mov     ecx, [rbx]
0x180024f5e  lea     rax, [rsp+88h+var_58]
0x180024f63  mov     [rsp+88h+var_20], rax
0x180024f68  lea     rdx, [rsp+88h+EventDescriptor]; EventDescriptor
0x180024f6d  movzx   eax, cs:word_18004D798
0x180024f74  xor     r9d, r9d; RelatedActivityId
0x180024f77  mov     dword ptr [rsp+88h+EventDescriptor.Level], eax
0x180024f7b  xor     r8d, r8d; ActivityId
0x180024f7e  mov     rax, [r10+8]
0x180024f82  mov     [rsp+88h+var_40.Ptr], rax
0x180024f87  mov     [rsp+88h+var_58], ecx
0x180024f8b  xor     ecx, ecx
0x180024f8d  mov     [rsp+88h+EventDescriptor.Keyword], rcx
0x180024f92  lea     rcx, _TraceLoggingMetadata
0x180024f99  mov     [rsp+88h+var_18], 4
0x180024fa2  mov     dword ptr [rsp+88h+EventDescriptor.Id], 0B000000h
0x180024faa  movzx   eax, word ptr [rax]
0x180024fad  mov     [rsp+88h+var_40.Size], eax
0x180024fb1  lea     rax, word_18004D7A2
0x180024fb8  mov     [rsp+88h+var_30], rax
0x180024fbd  lea     rax, _TraceLoggingMetadataEnd
0x180024fc4  sub     eax, ecx
0x180024fc6  mov     dword ptr [rsp+88h+var_40.0Ch], 2
0x180024fce  mov     [rsp+88h+var_28], 32h ; '2'
0x180024fd6  mov     [rsp+88h+var_24], 1
0x180024fde  mov     [rsp+88h+var_54], eax
0x180024fe2  mov     eax, [rsp+88h+var_54]
0x180024fe6  mov     rcx, [r10+20h]; RegHandle
0x180024fea  lea     rax, [rsp+88h+var_40]
0x180024fef  mov     [rsp+88h+UserData], rax; UserData
0x180024ff4  mov     [rsp+88h+UserDataCount], 3; UserDataCount
0x180024ffc  call    cs:__imp_EventWriteTransfer
0x180025002  mov     rcx, [rsp+88h+var_10]
0x180025007  xor     rcx, rsp; StackCookie
0x18002500a  call    __security_check_cookie
0x18002500f  add     rsp, 80h
0x180025016  pop     rbx
0x180025017  retn
```
