# ServiceManager::AddCumulativeOperationTime(void)

- ea: `0x180012828`
- end: `0x1800128c4`
- name: `?AddCumulativeOperationTime@ServiceManager@@AEAAXXZ`
- size: `156`
- prototype: `void __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800142c4`

## callees

- `0x180012828`
- `0x18002110c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012849`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18001283f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18001283f`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180012876`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800128b8`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180012876`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800128b8`

## string_xrefs

- `0x180012867`: `ServiceManager::AddCumulativeOperationTime`
- `0x1800128a9`: `ServiceManager::AddCumulativeOperationTime`

## pseudocode

```c
void __fastcall ServiceManager::AddCumulativeOperationTime(ServiceManager *this)
{
  __int64 v2; // rcx
  signed int LastError; // eax
  int v4; // eax
  unsigned __int64 UnbiasedTime; // [rsp+30h] [rbp+8h] BYREF

  UnbiasedTime = 0;
  if ( !QueryUnbiasedInterruptTime(&UnbiasedTime) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    ZTraceReportIgnore(LastError, "ServiceManager::AddCumulativeOperationTime", 684, this);
  }
  *((_QWORD *)this + 543) += UnbiasedTime - *((_QWORD *)this + 544);
  v4 = RegUtils::SetMapsPersistedRegQword(v2, L"CurrentOperationActiveTime", *((_QWORD *)this + 543));
  if ( v4 < 0 )
    ZTraceReportIgnore(v4, "ServiceManager::AddCumulativeOperationTime", 688, this);
}

```

## disassembly

```asm
0x180012828  push    rbx
0x18001282a  sub     rsp, 20h
0x18001282e  mov     rbx, rcx
0x180012831  mov     [rsp+28h+UnbiasedTime], 0
0x18001283a  lea     rcx, [rsp+28h+UnbiasedTime]; UnbiasedTime
0x18001283f  call    cs:__imp_QueryUnbiasedInterruptTime
0x180012845  test    eax, eax
0x180012847  jnz     short loc_18001287C
0x180012849  call    cs:__imp_GetLastError
0x18001284f  test    eax, eax
0x180012851  jz      short loc_18001285F
0x180012853  jle     short loc_180012864
0x180012855  movzx   eax, ax
0x180012858  or      eax, 80070000h
0x18001285d  jmp     short loc_180012864
0x18001285f  mov     eax, 80390004h
0x180012864  mov     r9, rbx
0x180012867  lea     rdx, aServicemanager_68; "ServiceManager::AddCumulativeOperationT"...
0x18001286e  mov     r8d, 2ACh
0x180012874  mov     ecx, eax
0x180012876  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001287c  mov     rax, [rsp+28h+UnbiasedTime]
0x180012881  lea     rdx, aCurrentoperati; "CurrentOperationActiveTime"
0x180012888  sub     rax, [rbx+1100h]
0x18001288f  add     [rbx+10F8h], rax
0x180012896  mov     r8, [rbx+10F8h]
0x18001289d  call    ?SetMapsPersistedRegQword@RegUtils@@SAJW4MapsRegKeys@@PEBG_K@Z; RegUtils::SetMapsPersistedRegQword(MapsRegKeys,ushort const *,unsigned __int64)
0x1800128a2  test    eax, eax
0x1800128a4  jns     short loc_1800128BE
0x1800128a6  mov     r9, rbx
0x1800128a9  lea     rdx, aServicemanager_68; "ServiceManager::AddCumulativeOperationT"...
0x1800128b0  mov     r8d, 2B0h
0x1800128b6  mov     ecx, eax
0x1800128b8  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800128be  add     rsp, 20h
0x1800128c2  pop     rbx
0x1800128c3  retn
```
