# ClientUpdatePnpInfo

- ea: `0x1800065d0`
- end: `0x18000675b`
- name: `ClientUpdatePnpInfo`
- size: `395`
- prototype: `void()`
- caller_count: `77`
- callee_count: `13`
- tags: `service_task, installer_update`

## callers

- `0x180004610`
- `0x1800048e0`
- `0x180004da0`
- `0x180005030`
- `0x1800055b0`
- `0x180005930`
- `0x180005c40`
- `0x180005fb0`
- `0x180006300`
- `0x180006ba0`
- `0x180007020`
- `0x1800073a0`
- `0x180007420`
- `0x180007640`
- `0x1800084d0`
- `0x180008530`
- `0x180009160`
- `0x180009250`
- `0x1800096f0`
- `0x180009760`
- `0x180009a8c`
- `0x180009de0`
- `0x18000a790`
- `0x18000a960`
- `0x18000af80`
- `0x18000b090`
- `0x18000b800`
- `0x18000bee0`
- `0x18000c6a0`
- `0x18000e000`
- `0x18000e860`
- `0x18000ec90`
- `0x18000ed70`
- `0x18000eff0`
- `0x18000f9e0`
- `0x18000fa30`
- `0x18000fa80`
- `0x180010220`
- `0x180017100`
- `0x180017280`
- `0x180017310`
- `0x180017350`
- `0x1800173c0`
- `0x180017490`
- `0x180018a10`
- `0x180018bb0`
- `0x180018e40`
- `0x180019000`
- `0x180019060`
- `0x1800190b0`

## callees

- `0x18000132c`
- `0x180001660`
- `0x1800065d0`
- `0x180006770`
- `0x180006800`
- `0x180006e54`
- `0x180006ec0`
- `0x1800072fc`
- `0x180008834`
- `0x18000c784`
- `0x18000ea20`
- `0x18000fefc`
- `0x180012d08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000670a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000670a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006698`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006698`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800065fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800065fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000660b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000660b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000666b`
- `MMDevAPI!__imp_InitializeDeviceAPI` at `0x180006686`
- `MMDevAPI!__imp_InitializeDeviceAPI` at `0x180006686`

## pseudocode

```c
void ClientUpdatePnpInfo()
{
  __int32 v0; // ebx
  int v1; // esi
  __int32 NewPnpEvents; // edi
  CWinmmNotificationClient *v3; // rcx
  int Endpoints; // eax
  int v5; // edx
  void *v6; // rbp
  LPVOID lpMem; // [rsp+30h] [rbp+8h] BYREF

  v0 = _InterlockedExchange(&dword_18002C254, 0);
  if ( v0 )
  {
    if ( IsRunningInVM() )
    {
      g_fIsRunningInVM = 1;
      CWinmmNotificationClient::winmmStartEndpointListener(v3);
    }
    else
    {
      winmmWaitForService();
      AudioSrvBinding();
    }
    InitializeDeviceAPI();
    InitDevices();
    SetEvent(hEventApiInit);
  }
  else
  {
    WaitForSingleObjectEx(hEventApiInit, 0xFFFFFFFF, 0);
  }
  EnterCriticalSection(&NumDevsCritSec);
  if ( !_InterlockedExchange(&dword_18002D408, 1) )
  {
    v1 = 0;
    if ( g_fIsRunningInVM )
      NewPnpEvents = _InterlockedExchange(&dword_18002D308, 0);
    else
      NewPnpEvents = winmmGetNewPnpEvents();
    if ( NewPnpEvents )
    {
      lpMem = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids);
      }
      Endpoints = winmmGetEndpoints((struct _MMPNPINFO **)&lpMem);
      v6 = lpMem;
      if ( Endpoints >= 0 )
        v1 = ClientPnpChange((struct _MMPNPINFO *)lpMem, v5);
      if ( v6 )
        HeapFree(hHeap, 0, v6);
      if ( v1 )
        InvalidatePreferredDevices();
    }
    if ( v0 || NewPnpEvents )
      RefreshPreferredDevices();
    if ( v1 )
      KickMappers();
    _InterlockedExchange(&dword_18002D408, 0);
  }
  LeaveCriticalSection(&NumDevsCritSec);
}

```

## disassembly

```asm
0x1800065d0  mov     [rsp+arg_18], rbx
0x1800065d5  push    rdi
0x1800065d6  sub     rsp, 20h
0x1800065da  xor     ebx, ebx
0x1800065dc  mov     edi, 1
0x1800065e1  xchg    ebx, cs:dword_18002C254
0x1800065e7  test    ebx, ebx
0x1800065e9  jnz     loc_180006672
0x1800065ef  mov     rcx, cs:hEventApiInit; hHandle
0x1800065f6  xor     r8d, r8d; bAlertable
0x1800065f9  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800065fe  call    cs:__imp_WaitForSingleObjectEx
0x180006604  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000660b  call    cs:__imp_EnterCriticalSection
0x180006611  xchg    edi, cs:dword_18002D408
0x180006617  test    edi, edi
0x180006619  jnz     short loc_18000665A
0x18000661b  mov     [rsp+28h+arg_10], rsi
0x180006620  xor     esi, esi
0x180006622  cmp     cs:?g_fIsRunningInVM@@3HA, esi; int g_fIsRunningInVM
0x180006628  jnz     loc_180006731
0x18000662e  call    winmmGetNewPnpEvents
0x180006633  mov     edi, eax
0x180006635  test    edi, edi
0x180006637  jnz     short loc_1800066B6
0x180006639  test    ebx, ebx
0x18000663b  jnz     loc_180006727
0x180006641  test    edi, edi
0x180006643  jnz     loc_180006727
0x180006649  test    esi, esi
0x18000664b  mov     rsi, [rsp+28h+arg_10]
0x180006650  jnz     short loc_1800066AF
0x180006652  xor     eax, eax
0x180006654  xchg    eax, cs:dword_18002D408
0x18000665a  lea     rcx, NumDevsCritSec
0x180006661  mov     rbx, [rsp+28h+arg_18]
0x180006666  add     rsp, 20h
0x18000666a  pop     rdi
0x18000666b  jmp     cs:__imp_LeaveCriticalSection
0x180006672  call    ?IsRunningInVM@@YA_NXZ; IsRunningInVM(void)
0x180006677  test    al, al
0x180006679  jz      short loc_1800066A3
0x18000667b  mov     cs:?g_fIsRunningInVM@@3HA, edi; int g_fIsRunningInVM
0x180006681  call    ?winmmStartEndpointListener@CWinmmNotificationClient@@QEAAXXZ; CWinmmNotificationClient::winmmStartEndpointListener(void)
0x180006686  call    cs:__imp_InitializeDeviceAPI
0x18000668c  call    ?InitDevices@@YAXXZ; InitDevices(void)
0x180006691  mov     rcx, cs:hEventApiInit; hEvent
0x180006698  call    cs:__imp_SetEvent
0x18000669e  jmp     loc_180006604
0x1800066a3  call    winmmWaitForService
0x1800066a8  call    AudioSrvBinding
0x1800066ad  jmp     short loc_180006686
0x1800066af  call    ?KickMappers@@YAXXZ; KickMappers(void)
0x1800066b4  jmp     short loc_180006652
0x1800066b6  mov     [rsp+28h+arg_8], rbp
0x1800066bb  mov     [rsp+28h+lpMem], rsi
0x1800066c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066c7  lea     rax, WPP_GLOBAL_Control
0x1800066ce  cmp     rcx, rax
0x1800066d1  jz      short loc_1800066DC
0x1800066d3  test    dword ptr [rcx+1Ch], 400000h
0x1800066da  jnz     short loc_18000673E
0x1800066dc  lea     rcx, [rsp+28h+lpMem]; struct _MMPNPINFO **
0x1800066e1  call    ?winmmGetEndpoints@@YAJPEAPEAU_MMPNPINFO@@@Z; winmmGetEndpoints(_MMPNPINFO * *)
0x1800066e6  mov     rbp, [rsp+28h+lpMem]
0x1800066eb  test    eax, eax
0x1800066ed  js      short loc_1800066F9
0x1800066ef  mov     rcx, rbp; struct _MMPNPINFO *
0x1800066f2  call    ?ClientPnpChange@@YAHPEAU_MMPNPINFO@@J@Z; ClientPnpChange(_MMPNPINFO *,long)
0x1800066f7  mov     esi, eax
0x1800066f9  test    rbp, rbp
0x1800066fc  jz      short loc_180006710
0x1800066fe  mov     rcx, cs:hHeap; hHeap
0x180006705  mov     r8, rbp; lpMem
0x180006708  xor     edx, edx; dwFlags
0x18000670a  call    cs:__imp_HeapFree
0x180006710  mov     rbp, [rsp+28h+arg_8]
0x180006715  test    esi, esi
0x180006717  jz      loc_180006639
0x18000671d  call    InvalidatePreferredDevices
0x180006722  jmp     loc_180006639
0x180006727  call    RefreshPreferredDevices
0x18000672c  jmp     loc_180006649
0x180006731  xor     edi, edi
0x180006733  xchg    edi, cs:dword_18002D308
0x180006739  jmp     loc_180006635
0x18000673e  cmp     byte ptr [rcx+19h], 4
0x180006742  jb      short loc_1800066DC
0x180006744  mov     rcx, [rcx+10h]
0x180006748  lea     r8, WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids
0x18000674f  mov     edx, 19h
0x180006754  call    WPP_SF_
0x180006759  jmp     short loc_1800066DC
```
