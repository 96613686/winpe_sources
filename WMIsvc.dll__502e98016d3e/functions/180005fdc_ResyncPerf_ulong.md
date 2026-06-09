# ResyncPerf(ulong)

- ea: `0x180005fdc`
- end: `0x180006166`
- name: `?ResyncPerf@@YAKK@Z`
- size: `394`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800065e0`
- `0x180008840`
- `0x18000c974`
- `0x180016a70`
- `0x180016a80`

## callees

- `0x180005fdc`
- `0x18000616c`
- `0x18000618c`
- `0x18000b648`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006094`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006094`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006116`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006116`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800060ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800060ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000610c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000610c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006151`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180006143`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180006143`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005ffe`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005ffe`
- `wbemcomn!GetMemLogObject` at `0x180005ff2`
- `wbemcomn!GetMemLogObject` at `0x180005ff2`

## pseudocode

```c
DWORD __fastcall ResyncPerf(unsigned int a1)
{
  CMemoryLog *MemLogObject; // rax
  struct ResyncPerfTask *Available; // rbx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  int Data; // [rsp+78h] [rbp+28h] BYREF
  DWORD Type; // [rsp+80h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF

  if ( !(unsigned int)GLOB_IsResyncAllowed() )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -1);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids);
    }
    return 0;
  }
  Available = CMonitorEvents::GetAvailable((CMonitorEvents *)&dword_180032A88, a1);
  if ( !Available )
    return 170;
  if ( a1 == 2 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\PROVIDERS\\Performance", 0, 0x2001Fu, &hKey) )
    {
      Type = 0;
      Data = 0;
      cbData = 4;
      v4 = RegQueryValueExW(hKey, L"Performance Refresh", 0, &Type, (LPBYTE)&Data, &cbData);
      if ( !v4 )
      {
        if ( Type != 4 )
          goto LABEL_14;
        if ( !Data )
        {
LABEL_13:
          Data = 1;
          RegSetValueExW(hKey, L"Performance Refresh", 0, 4u, (const BYTE *)&Data, 4u);
          goto LABEL_14;
        }
      }
      if ( v4 == 2 )
        goto LABEL_13;
LABEL_14:
      RegCloseKey(hKey);
    }
  }
  if ( CreateTimerQueueTimer(
         (PHANDLE)Available + 2,
         0,
         CMonitorEvents::TimerCallBack,
         Available,
         *((_DWORD *)Available + 6),
         0,
         0x18u) )
  {
    return 0;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x180005fdc  push    rbp
0x180005fde  push    rbx
0x180005fdf  push    rdi
0x180005fe0  mov     rbp, rsp
0x180005fe3  sub     rsp, 50h
0x180005fe7  mov     edi, ecx
0x180005fe9  call    ?GLOB_IsResyncAllowed@@YAHXZ; GLOB_IsResyncAllowed(void)
0x180005fee  test    eax, eax
0x180005ff0  jnz     short loc_180006049
0x180005ff2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180005ff8  mov     rcx, rax
0x180005ffb  or      edx, 0FFFFFFFFh
0x180005ffe  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180006004  mov     rcx, cs:WPP_GLOBAL_Control
0x18000600b  lea     rax, WPP_GLOBAL_Control
0x180006012  cmp     rcx, rax
0x180006015  jz      loc_18000614D
0x18000601b  test    byte ptr [rcx+1Ch], 1
0x18000601f  jz      loc_18000614D
0x180006025  cmp     byte ptr [rcx+19h], 2
0x180006029  jb      loc_18000614D
0x18000602f  mov     rcx, [rcx+10h]
0x180006033  lea     r8, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids
0x18000603a  mov     edx, 19h
0x18000603f  call    WPP_SF_
0x180006044  jmp     loc_18000614D
0x180006049  mov     edx, edi; unsigned int
0x18000604b  lea     rcx, dword_180032A88; this
0x180006052  call    ?GetAvailable@CMonitorEvents@@QEAAPEAVResyncPerfTask@@K@Z; CMonitorEvents::GetAvailable(ulong)
0x180006057  mov     rbx, rax
0x18000605a  test    rax, rax
0x18000605d  jz      loc_180006159
0x180006063  cmp     edi, 2
0x180006066  jnz     loc_18000611C
0x18000606c  lea     rax, [rbp+hKey]
0x180006070  mov     [rbp+hKey], 0
0x180006078  mov     r9d, 2001Fh; samDesired
0x18000607e  mov     [rsp+50h+phkResult], rax; phkResult
0x180006083  xor     r8d, r8d; ulOptions
0x180006086  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\WBEM\\PROVIDERS\\P"...
0x18000608d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006094  call    cs:__imp_RegOpenKeyExW
0x18000609a  test    eax, eax
0x18000609c  jnz     short loc_18000611C
0x18000609e  mov     rcx, [rbp+hKey]; hKey
0x1800060a2  lea     edi, [rax+4]
0x1800060a5  mov     [rbp+Type], eax
0x1800060a8  lea     r9, [rbp+Type]; lpType
0x1800060ac  mov     [rbp+Data], eax
0x1800060af  lea     rdx, aPerformanceRef; "Performance Refresh"
0x1800060b6  lea     rax, [rbp+cbData]
0x1800060ba  mov     [rbp+cbData], edi
0x1800060bd  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800060c2  xor     r8d, r8d; lpReserved
0x1800060c5  lea     rax, [rbp+Data]
0x1800060c9  mov     [rsp+50h+phkResult], rax; lpData
0x1800060ce  call    cs:__imp_RegQueryValueExW
0x1800060d4  test    eax, eax
0x1800060d6  jnz     short loc_1800060E2
0x1800060d8  cmp     [rbp+Type], edi
0x1800060db  jnz     short loc_180006112
0x1800060dd  cmp     [rbp+Data], eax
0x1800060e0  jz      short loc_1800060E7
0x1800060e2  cmp     eax, 2
0x1800060e5  jnz     short loc_180006112
0x1800060e7  mov     rcx, [rbp+hKey]; hKey
0x1800060eb  lea     rax, [rbp+Data]
0x1800060ef  mov     dword ptr [rsp+50h+lpcbData], edi; cbData
0x1800060f3  lea     rdx, aPerformanceRef; "Performance Refresh"
0x1800060fa  mov     r9d, edi; dwType
0x1800060fd  mov     [rsp+50h+phkResult], rax; lpData
0x180006102  xor     r8d, r8d; Reserved
0x180006105  mov     [rbp+Data], 1
0x18000610c  call    cs:__imp_RegSetValueExW
0x180006112  mov     rcx, [rbp+hKey]; hKey
0x180006116  call    cs:__imp_RegCloseKey
0x18000611c  mov     eax, [rbx+18h]
0x18000611f  lea     rcx, [rbx+10h]; phNewTimer
0x180006123  mov     [rsp+50h+Flags], 18h; Flags
0x18000612b  lea     r8, ?TimerCallBack@CMonitorEvents@@SAXPEAXE@Z; Callback
0x180006132  mov     dword ptr [rsp+50h+lpcbData], 0; Period
0x18000613a  mov     r9, rbx; Parameter
0x18000613d  xor     edx, edx; TimerQueue
0x18000613f  mov     dword ptr [rsp+50h+phkResult], eax; DueTime
0x180006143  call    cs:__imp_CreateTimerQueueTimer
0x180006149  test    eax, eax
0x18000614b  jz      short loc_180006151
0x18000614d  xor     eax, eax
0x18000614f  jmp     short loc_18000615E
0x180006151  call    cs:__imp_GetLastError
0x180006157  jmp     short loc_18000615E
0x180006159  mov     eax, 0AAh
0x18000615e  add     rsp, 50h
0x180006162  pop     rdi
0x180006163  pop     rbx
0x180006164  pop     rbp
0x180006165  retn
```
