# CService::Stop(void)

- ea: `0x180003b60`
- end: `0x180003cbc`
- name: `?Stop@CService@@QEAAJXZ`
- size: `348`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800018c0`
- `0x180003ad0`

## callees

- `0x180003b60`
- `0x180003cd0`
- `0x180007790`
- `0x180007f28`
- `0x18000dfd4`
- `0x18000e3e4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003bf6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003bf6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003c15`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003c15`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003c08`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003c08`

## pseudocode

```c
__int64 __fastcall CService::Stop(CService *this)
{
  int v2; // edi

  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
      (unsigned int)g_RefCount);
  }
  _m_prefetchw((char *)this + 64);
  while ( (_InterlockedOr64((volatile signed __int64 *)this + 8, 2u) & 1) != 0 )
  {
    _mm_pause();
    _m_prefetchw((char *)this + 64);
  }
  if ( g_shutdownTimer )
  {
    SetThreadpoolTimer(g_shutdownTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(g_shutdownTimer, 1);
    CloseThreadpoolTimer(g_shutdownTimer);
    g_shutdownTimer = 0;
  }
  if ( g_PnPNotification )
  {
    v2 = CPnPNotification::Uninitialize(g_PnPNotification);
    if ( v2 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids);
      }
      v2 = 0;
    }
  }
  else
  {
    v2 = 0;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids);
  }
  if ( g_BthActiveConnector )
    CBthActiveConnector::Shutdown(g_BthActiveConnector);
  CService::Shutdown(this);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003b60  mov     [rsp+arg_0], rbx
0x180003b65  mov     [rsp+arg_8], rsi
0x180003b6a  push    rdi
0x180003b6b  sub     rsp, 20h
0x180003b6f  mov     rbx, rcx
0x180003b72  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b79  lea     rsi, WPP_GLOBAL_Control
0x180003b80  cmp     rcx, rsi
0x180003b83  jz      short loc_180003BAA
0x180003b85  test    dword ptr [rcx+1Ch], 200h
0x180003b8c  jz      short loc_180003BAA
0x180003b8e  mov     r9d, cs:?g_RefCount@@3JA; long g_RefCount
0x180003b95  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003b9c  mov     rcx, [rcx+10h]
0x180003ba0  mov     edx, 3Bh ; ';'
0x180003ba5  call    WPP_SF_d
0x180003baa  prefetchw byte ptr [rbx+40h]
0x180003bae  mov     rax, [rbx+40h]
0x180003bb2  mov     rcx, rax
0x180003bb5  or      rcx, 2
0x180003bb9  lock cmpxchg [rbx+40h], rcx
0x180003bbf  jnz     short loc_180003BB2
0x180003bc1  test    al, 1
0x180003bc3  jz      short loc_180003BE2
0x180003bc5  pause
0x180003bc7  prefetchw byte ptr [rbx+40h]
0x180003bcb  mov     rax, [rbx+40h]
0x180003bcf  mov     rcx, rax
0x180003bd2  or      rcx, 2
0x180003bd6  lock cmpxchg [rbx+40h], rcx
0x180003bdc  jnz     short loc_180003BCF
0x180003bde  test    al, 1
0x180003be0  jnz     short loc_180003BC5
0x180003be2  mov     rcx, cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA; pti
0x180003be9  test    rcx, rcx
0x180003bec  jz      short loc_180003C26
0x180003bee  xor     r9d, r9d; msWindowLength
0x180003bf1  xor     r8d, r8d; msPeriod
0x180003bf4  xor     edx, edx; pftDueTime
0x180003bf6  call    cs:__imp_SetThreadpoolTimer
0x180003bfc  mov     rcx, cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA; pti
0x180003c03  mov     edx, 1; fCancelPendingCallbacks
0x180003c08  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003c0e  mov     rcx, cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA; pti
0x180003c15  call    cs:__imp_CloseThreadpoolTimer
0x180003c1b  mov     cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * g_shutdownTimer
0x180003c26  mov     rcx, cs:?g_PnPNotification@@3PEAVCPnPNotification@@EA; this
0x180003c2d  test    rcx, rcx
0x180003c30  jz      short loc_180003C68
0x180003c32  call    ?Uninitialize@CPnPNotification@@QEAAJXZ; CPnPNotification::Uninitialize(void)
0x180003c37  mov     edi, eax
0x180003c39  test    eax, eax
0x180003c3b  jns     short loc_180003C91
0x180003c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c44  cmp     rcx, rsi
0x180003c47  jz      short loc_180003C64
0x180003c49  test    byte ptr [rcx+1Ch], 4
0x180003c4d  jz      short loc_180003C64
0x180003c4f  mov     rcx, [rcx+10h]
0x180003c53  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003c5a  mov     edx, 3Ch ; '<'
0x180003c5f  call    WPP_SF_
0x180003c64  xor     edi, edi
0x180003c66  jmp     short loc_180003C91
0x180003c68  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c6f  xor     edi, edi
0x180003c71  cmp     rcx, rsi
0x180003c74  jz      short loc_180003C91
0x180003c76  test    byte ptr [rcx+1Ch], 4
0x180003c7a  jz      short loc_180003C91
0x180003c7c  mov     rcx, [rcx+10h]
0x180003c80  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003c87  mov     edx, 3Dh ; '='
0x180003c8c  call    WPP_SF_
0x180003c91  mov     rcx, cs:?g_BthActiveConnector@@3PEAVCBthActiveConnector@@EA; this
0x180003c98  test    rcx, rcx
0x180003c9b  jz      short loc_180003CA2
0x180003c9d  call    ?Shutdown@CBthActiveConnector@@QEAAXXZ; CBthActiveConnector::Shutdown(void)
0x180003ca2  mov     rcx, rbx; this
0x180003ca5  call    ?Shutdown@CService@@QEAAXXZ; CService::Shutdown(void)
0x180003caa  mov     rbx, [rsp+28h+arg_0]
0x180003caf  mov     eax, edi
0x180003cb1  mov     rsi, [rsp+28h+arg_8]
0x180003cb6  add     rsp, 20h
0x180003cba  pop     rdi
0x180003cbb  retn
```
