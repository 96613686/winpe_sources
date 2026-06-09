# ServiceManager::InitODML(void)

- ea: `0x180016d3c`
- end: `0x180016e72`
- name: `?InitODML@ServiceManager@@AEAAJXZ`
- size: `310`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x1800142c4`
- `0x180015898`

## callees

- `0x180016d3c`
- `0x18001edb0`
- `0x18001eec4`
- `0x180020978`
- `0x1800226dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180016df5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180016df5`
- `MapsStore!MapsStore_LoadCatalogAsync` at `0x180016e1d`
- `MapsStore!MapsStore_LoadCatalogAsync` at `0x180016e1d`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180016e3c`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180016e3c`

## string_xrefs

- `0x180016d7d`: `LastMapUpdateDate`
- `0x180016da7`: `LastMapUpdateCheck`
- `0x180016e33`: `ServiceManager::InitODML`

## pseudocode

```c
__int64 __fastcall ServiceManager::InitODML(ServiceManager *this)
{
  int v1; // ebp
  char v3; // si
  int MapsPersistedRegQword; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  int v7; // r8d
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // edi
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+10h] BYREF

  v1 = *((_DWORD *)this + 882);
  v12 = 0;
  v3 = 0;
  MapsPersistedRegQword = TimerQueue::Initialize((ServiceManager *)((char *)this + 4280));
  if ( MapsPersistedRegQword >= 0 )
  {
    MapsPersistedRegQword = RegUtils::GetMapsPersistedRegQword(v5, L"LastMapUpdateDate", v6, &v12);
    if ( MapsPersistedRegQword >= 0 )
    {
      *((_QWORD *)this + 445) = v12;
      MapsPersistedRegQword = RegUtils::GetMapsPersistedRegQword(v8, L"LastMapUpdateCheck", v9, &v12);
      if ( MapsPersistedRegQword >= 0 )
      {
        *((_QWORD *)this + 444) = v12;
        *((_DWORD *)this + 882) = 3;
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        MapsPersistedRegQword = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))ServiceWatchdog::Start)(
                                  (char *)this + 3944,
                                  1,
                                  SystemTimeAsFileTime);
        if ( MapsPersistedRegQword >= 0 )
        {
          MapsPersistedRegQword = MapsStore_LoadCatalogAsync();
          if ( MapsPersistedRegQword >= 0 )
            return 0;
          v3 = 1;
          v7 = 1860;
        }
        else
        {
          v7 = 1856;
        }
      }
      else
      {
        v7 = 1845;
      }
    }
    else
    {
      v7 = 1841;
    }
  }
  else
  {
    v7 = 1839;
  }
  v10 = ZTraceReportPropagation(MapsPersistedRegQword, "ServiceManager::InitODML", v7, this);
  if ( v10 < 0 )
  {
    if ( v3 )
      ServiceWatchdog::Stop((ServiceManager *)((char *)this + 3944));
    *((_DWORD *)this + 882) = v1;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180016d3c  mov     [rsp+arg_10], rbx
0x180016d41  push    rbp
0x180016d42  push    rsi
0x180016d43  push    rdi
0x180016d44  sub     rsp, 20h
0x180016d48  mov     ebp, [rcx+0DC8h]
0x180016d4e  mov     rbx, rcx
0x180016d51  add     rcx, 10B8h; this
0x180016d58  mov     [rsp+38h+arg_0], 0
0x180016d61  xor     sil, sil
0x180016d64  call    ?Initialize@TimerQueue@@QEAAJXZ; TimerQueue::Initialize(void)
0x180016d69  test    eax, eax
0x180016d6b  jns     short loc_180016D78
0x180016d6d  mov     r8d, 72Fh
0x180016d73  jmp     loc_180016E30
0x180016d78  lea     r9, [rsp+38h+arg_0]
0x180016d7d  lea     rdx, aLastmapupdated; "LastMapUpdateDate"
0x180016d84  call    ?GetMapsPersistedRegQword@RegUtils@@SAJW4MapsRegKeys@@PEBG_KPEA_K@Z; RegUtils::GetMapsPersistedRegQword(MapsRegKeys,ushort const *,unsigned __int64,unsigned __int64 *)
0x180016d89  test    eax, eax
0x180016d8b  jns     short loc_180016D98
0x180016d8d  mov     r8d, 731h
0x180016d93  jmp     loc_180016E30
0x180016d98  mov     eax, dword ptr [rsp+38h+arg_0]
0x180016d9c  lea     r9, [rsp+38h+arg_0]
0x180016da1  mov     [rbx+0DE8h], eax
0x180016da7  lea     rdx, aLastmapupdatec; "LastMapUpdateCheck"
0x180016dae  mov     eax, dword ptr [rsp+38h+arg_0+4]
0x180016db2  mov     [rbx+0DECh], eax
0x180016db8  call    ?GetMapsPersistedRegQword@RegUtils@@SAJW4MapsRegKeys@@PEBG_KPEA_K@Z; RegUtils::GetMapsPersistedRegQword(MapsRegKeys,ushort const *,unsigned __int64,unsigned __int64 *)
0x180016dbd  test    eax, eax
0x180016dbf  jns     short loc_180016DC9
0x180016dc1  mov     r8d, 735h
0x180016dc7  jmp     short loc_180016E30
0x180016dc9  mov     eax, dword ptr [rsp+38h+arg_0]
0x180016dcd  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180016dd2  mov     [rbx+0DE0h], eax
0x180016dd8  mov     eax, dword ptr [rsp+38h+arg_0+4]
0x180016ddc  mov     [rbx+0DE4h], eax
0x180016de2  mov     dword ptr [rbx+0DC8h], 3
0x180016dec  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180016df5  call    cs:__imp_GetSystemTimeAsFileTime
0x180016dfb  mov     r8, qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime]
0x180016e00  lea     rcx, [rbx+0F68h]
0x180016e07  mov     edx, 1
0x180016e0c  call    ?Start@ServiceWatchdog@@QEAAJW4StartReason@1@U_FILETIME@@@Z; ServiceWatchdog::Start(ServiceWatchdog::StartReason,_FILETIME)
0x180016e11  test    eax, eax
0x180016e13  jns     short loc_180016E1D
0x180016e15  mov     r8d, 740h
0x180016e1b  jmp     short loc_180016E30
0x180016e1d  call    cs:__imp_?MapsStore_LoadCatalogAsync@@YAJXZ; MapsStore_LoadCatalogAsync(void)
0x180016e23  test    eax, eax
0x180016e25  jns     short loc_180016E61
0x180016e27  mov     sil, 1
0x180016e2a  mov     r8d, 744h
0x180016e30  mov     r9, rbx
0x180016e33  lea     rdx, aServicemanager_18; "ServiceManager::InitODML"
0x180016e3a  mov     ecx, eax
0x180016e3c  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180016e42  mov     edi, eax
0x180016e44  test    eax, eax
0x180016e46  jns     short loc_180016E63
0x180016e48  test    sil, sil
0x180016e4b  jz      short loc_180016E59
0x180016e4d  lea     rcx, [rbx+0F68h]; this
0x180016e54  call    ?Stop@ServiceWatchdog@@QEAAXXZ; ServiceWatchdog::Stop(void)
0x180016e59  mov     [rbx+0DC8h], ebp
0x180016e5f  jmp     short loc_180016E63
0x180016e61  xor     edi, edi
0x180016e63  mov     rbx, [rsp+38h+arg_10]
0x180016e68  mov     eax, edi
0x180016e6a  add     rsp, 20h
0x180016e6e  pop     rdi
0x180016e6f  pop     rsi
0x180016e70  pop     rbp
0x180016e71  retn
```
