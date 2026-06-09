# WindowsPerformanceRecorder::CControlManager::GetRunningSystemGroupMask(unsigned __int64,_PERFINFO_GROUPMASK &)

- ea: `0x1800385d4`
- end: `0x180038675`
- name: `?GetRunningSystemGroupMask@CControlManager@WindowsPerformanceRecorder@@AEAAJ_KAEAU_PERFINFO_GROUPMASK@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, unsigned __int64, struct _PERFINFO_GROUPMASK *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180023b34`
- `0x180058800`
- `0x18005ed4c`

## callees

- `0x18001e6e0`
- `0x1800385d4`
- `0x18003867c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003865d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003865d`

## string_xrefs

- `0x180038621`: `COMGUARD`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::GetRunningSystemGroupMask(
        WindowsPerformanceRecorder::CControlManager *this,
        const char *a2,
        struct _PERFINFO_GROUPMASK *a3)
{
  signed int EventTraceInformation; // eax
  _OWORD *v5; // rbx
  unsigned int v6; // edi
  void *Block; // [rsp+30h] [rbp-18h] BYREF
  int v10; // [rsp+50h] [rbp+8h] BYREF
  int v11; // [rsp+54h] [rbp+Ch]
  int v12; // [rsp+68h] [rbp+20h] BYREF

  v11 = HIDWORD(this);
  Block = 0;
  v12 = 48;
  v10 = 0;
  EventTraceInformation = WindowsPerformanceRecorder::CControlManager::GetEventTraceInformationT<_EVENT_TRACE_GROUPMASK_INFORMATION>(
                            this,
                            &Block,
                            &v12,
                            &v10);
  v5 = Block;
  v6 = EventTraceInformation;
  if ( EventTraceInformation >= 0 )
  {
    v6 = 0;
    *(_OWORD *)a3 = *((_OWORD *)Block + 1);
    *((_OWORD *)a3 + 1) = v5[2];
  }
  else
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "GetRunningSystemGroupMask",
      (const char *)0x1285,
      EventTraceInformation,
      "COMGUARD",
      a2);
  }
  free(v5);
  return v6;
}

```

## disassembly

```asm
0x1800385d4  mov     rax, rsp
0x1800385d7  mov     [rax+10h], rbx
0x1800385db  mov     [rax+18h], rsi
0x1800385df  mov     [rax+8], rcx
0x1800385e3  push    rdi
0x1800385e4  sub     rsp, 40h
0x1800385e8  mov     rsi, r8
0x1800385eb  mov     [rax-20h], rdx
0x1800385ef  lea     r8, [rax+20h]
0x1800385f3  mov     qword ptr [rax-18h], 0
0x1800385fb  lea     rdx, [rax-18h]
0x1800385ff  mov     dword ptr [rax+20h], 30h ; '0'
0x180038606  lea     r9, [rax+8]
0x18003860a  mov     dword ptr [rax+8], 0
0x180038611  call    ??$GetEventTraceInformationT@U_EVENT_TRACE_GROUPMASK_INFORMATION@@@CControlManager@WindowsPerformanceRecorder@@AEBAJAEAV?$CHeapPtr@U_EVENT_TRACE_GROUPMASK_INFORMATION@@VCCRTAllocator@ATL@@@ATL@@AEAK1W4_EVENT_TRACE_INFORMATION_CLASS@@_K@Z; WindowsPerformanceRecorder::CControlManager::GetEventTraceInformationT<_EVENT_TRACE_GROUPMASK_INFORMATION>(ATL::CHeapPtr<_EVENT_TRACE_GROUPMASK_INFORMATION,ATL::CCRTAllocator> &,ulong &,ulong &,_EVENT_TRACE_INFORMATION_CLASS,unsigned __int64)
0x180038616  mov     rbx, [rsp+48h+Block]
0x18003861b  mov     edi, eax
0x18003861d  test    eax, eax
0x18003861f  jns     short loc_180038649
0x180038621  lea     rax, aComguard; "COMGUARD"
0x180038628  mov     r9d, edi; unsigned int
0x18003862b  mov     r8d, 1285h; char *
0x180038631  mov     [rsp+48h+Format], rax; Format
0x180038636  lea     rdx, aGetrunningsyst; "GetRunningSystemGroupMask"
0x18003863d  mov     ecx, 2; this
0x180038642  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180038647  jmp     short loc_18003865A
0x180038649  movups  xmm0, xmmword ptr [rbx+10h]
0x18003864d  xor     edi, edi
0x18003864f  movups  xmmword ptr [rsi], xmm0
0x180038652  movups  xmm1, xmmword ptr [rbx+20h]
0x180038656  movups  xmmword ptr [rsi+10h], xmm1
0x18003865a  mov     rcx, rbx; Block
0x18003865d  call    cs:__imp_free
0x180038663  mov     rbx, [rsp+48h+arg_8]
0x180038668  mov     eax, edi
0x18003866a  mov     rsi, [rsp+48h+arg_10]
0x18003866f  add     rsp, 40h
0x180038673  pop     rdi
0x180038674  retn
```
