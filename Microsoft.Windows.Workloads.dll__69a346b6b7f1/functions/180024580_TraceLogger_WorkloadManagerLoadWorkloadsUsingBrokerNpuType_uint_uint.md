# TraceLogger::WorkloadManagerLoadWorkloadsUsingBrokerNpuType<uint>(uint &&)

- ea: `0x180024580`
- end: `0x180024668`
- name: `??$WorkloadManagerLoadWorkloadsUsingBrokerNpuType@I@TraceLogger@@SAX$$QEAI@Z`
- size: `232`
- prototype: `int __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x1800119b0`
- `0x180024580`
- `0x180034ef0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x18002464c`
- `ADVAPI32!EventWriteTransfer` at `0x18002464c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall TraceLogger::WorkloadManagerLoadWorkloadsUsingBrokerNpuType<unsigned int>(int *a1)
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
    v8 = byte_18004D911;
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
0x180024580  push    rbx
0x180024582  sub     rsp, 80h
0x180024589  mov     rax, cs:__security_cookie
0x180024590  xor     rax, rsp
0x180024593  mov     [rsp+88h+var_10], rax
0x180024598  mov     rbx, rcx
0x18002459b  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x1800245a0  mov     r10, rax
0x1800245a3  cmp     dword ptr [rax], 5
0x1800245a6  jbe     loc_180024652
0x1800245ac  mov     ecx, [rbx]
0x1800245ae  lea     rax, [rsp+88h+var_58]
0x1800245b3  mov     [rsp+88h+var_20], rax
0x1800245b8  lea     rdx, [rsp+88h+EventDescriptor]; EventDescriptor
0x1800245bd  movzx   eax, cs:word_18004D907
0x1800245c4  xor     r9d, r9d; RelatedActivityId
0x1800245c7  mov     dword ptr [rsp+88h+EventDescriptor.Level], eax
0x1800245cb  xor     r8d, r8d; ActivityId
0x1800245ce  mov     rax, [r10+8]
0x1800245d2  mov     [rsp+88h+var_40.Ptr], rax
0x1800245d7  mov     [rsp+88h+var_58], ecx
0x1800245db  xor     ecx, ecx
0x1800245dd  mov     [rsp+88h+EventDescriptor.Keyword], rcx
0x1800245e2  lea     rcx, _TraceLoggingMetadata
0x1800245e9  mov     [rsp+88h+var_18], 4
0x1800245f2  mov     dword ptr [rsp+88h+EventDescriptor.Id], 0B000000h
0x1800245fa  movzx   eax, word ptr [rax]
0x1800245fd  mov     [rsp+88h+var_40.Size], eax
0x180024601  lea     rax, byte_18004D911
0x180024608  mov     [rsp+88h+var_30], rax
0x18002460d  lea     rax, _TraceLoggingMetadataEnd
0x180024614  sub     eax, ecx
0x180024616  mov     dword ptr [rsp+88h+var_40.0Ch], 2
0x18002461e  mov     [rsp+88h+var_28], 3Bh ; ';'
0x180024626  mov     [rsp+88h+var_24], 1
0x18002462e  mov     [rsp+88h+var_54], eax
0x180024632  mov     eax, [rsp+88h+var_54]
0x180024636  mov     rcx, [r10+20h]; RegHandle
0x18002463a  lea     rax, [rsp+88h+var_40]
0x18002463f  mov     [rsp+88h+UserData], rax; UserData
0x180024644  mov     [rsp+88h+UserDataCount], 3; UserDataCount
0x18002464c  call    cs:__imp_EventWriteTransfer
0x180024652  mov     rcx, [rsp+88h+var_10]
0x180024657  xor     rcx, rsp; StackCookie
0x18002465a  call    __security_check_cookie
0x18002465f  add     rsp, 80h
0x180024666  pop     rbx
0x180024667  retn
```
