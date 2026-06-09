# SharedSocket::CreateRetryTriggerMonitor(_SOCKET_BROKER_TRIGGER_REASON)

- ea: `0x180027c50`
- end: `0x180027d69`
- name: `?CreateRetryTriggerMonitor@SharedSocket@@IEAAKW4_SOCKET_BROKER_TRIGGER_REASON@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026fc8`
- `0x1800278e0`
- `0x180027e68`
- `0x180027fa0`

## callees

- `0x1800025c0`
- `0x18000a0a0`
- `0x180027c50`
- `0x18002a22c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ce9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027c6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027c6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027d51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027d51`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180027cd7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180027cd7`

## string_xrefs

- `0x180027caf`: `SharedSocket::CreateRetryTriggerMonitor execcded retry limit Closing socket`
- `0x180027cfd`: `SharedSocket::CreateRetryTriggerMonitor CreateThreadpoolWork failed`

## pseudocode

```c
__int64 __fastcall SharedSocket::CreateRetryTriggerMonitor(__int64 a1, int a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int WakeTimer; // edi
  __int64 v7; // r9
  const wchar_t *v8; // r8
  PTP_WORK ThreadpoolWork; // rax
  DWORD LastError; // eax
  __int64 v11; // rdx
  unsigned int v12; // ecx

  SharedSocket::DeleteRetryTriggerTimer((SharedSocket *)a1);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  if ( !*(_QWORD *)(a1 + 80) || *(_BYTE *)(a1 + 208) )
  {
    WakeTimer = 5023;
    goto LABEL_13;
  }
  if ( ++*(_DWORD *)(a1 + 240) <= 2u )
  {
    if ( *(_QWORD *)(a1 + 256)
      || (ThreadpoolWork = CreateThreadpoolWork(SharedSocket::HandleRetryTriggerWork, (PVOID)a1, 0),
          (*(_QWORD *)(a1 + 256) = ThreadpoolWork) != 0) )
    {
      v11 = *(_QWORD *)(a1 + 80);
      v12 = 1000 * *(_DWORD *)(a1 + 244);
      *(_DWORD *)(a1 + 116) = a2;
      WakeTimer = WakeTimer::CreateWakeTimer(
                    v12,
                    *(unsigned __int16 **)(v11 + 48),
                    (void *)a1,
                    (void (__high *)(void *, struct _CBROKERED_EVENT_ID, void *, void *, unsigned int, unsigned int, enum _BI_ACTIVATION_STATUS *))&SharedSocket::HandleRetryTriggerCallback,
                    (void **)(a1 + 232));
      *(_DWORD *)(a1 + 244) *= 2;
      goto LABEL_13;
    }
    LastError = GetLastError();
    WakeTimer = LastError;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      v7 = LastError;
      v8 = L"SharedSocket::CreateRetryTriggerMonitor CreateThreadpoolWork failed";
      goto LABEL_6;
    }
  }
  else
  {
    WakeTimer = 5023;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      v7 = 5023;
      v8 = L"SharedSocket::CreateRetryTriggerMonitor execcded retry limit Closing socket";
LABEL_6:
      McTemplateU0zq_EventWriteTransfer(v5, v4, v8, v7);
    }
  }
LABEL_13:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  return WakeTimer;
}

```

## disassembly

```asm
0x180027c50  mov     [rsp+arg_0], rbx
0x180027c55  mov     [rsp+arg_8], rsi
0x180027c5a  push    rdi
0x180027c5b  sub     rsp, 30h
0x180027c5f  mov     edi, edx
0x180027c61  mov     rbx, rcx
0x180027c64  call    ?DeleteRetryTriggerTimer@SharedSocket@@AEAAXXZ; SharedSocket::DeleteRetryTriggerTimer(void)
0x180027c69  lea     rcx, [rbx+28h]; lpCriticalSection
0x180027c6d  call    cs:__imp_EnterCriticalSection
0x180027c73  cmp     qword ptr [rbx+50h], 0
0x180027c78  jz      loc_180027D48
0x180027c7e  cmp     byte ptr [rbx+0D0h], 0
0x180027c85  jnz     loc_180027D48
0x180027c8b  inc     dword ptr [rbx+0F0h]
0x180027c91  cmp     dword ptr [rbx+0F0h], 2
0x180027c98  jbe     short loc_180027CC0
0x180027c9a  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027ca1  mov     edi, 139Fh
0x180027ca6  jz      loc_180027D4D
0x180027cac  mov     r9d, edi
0x180027caf  lea     r8, aSharedsocketCr; "SharedSocket::CreateRetryTriggerMonitor"...
0x180027cb6  call    McTemplateU0zq_EventWriteTransfer
0x180027cbb  jmp     loc_180027D4D
0x180027cc0  cmp     qword ptr [rbx+100h], 0
0x180027cc8  jnz     short loc_180027D06
0x180027cca  xor     r8d, r8d; pcbe
0x180027ccd  lea     rcx, ?HandleRetryTriggerWork@SharedSocket@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180027cd4  mov     rdx, rbx; pv
0x180027cd7  call    cs:__imp_CreateThreadpoolWork
0x180027cdd  mov     [rbx+100h], rax
0x180027ce4  test    rax, rax
0x180027ce7  jnz     short loc_180027D06
0x180027ce9  call    cs:__imp_GetLastError
0x180027cef  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027cf6  mov     edi, eax
0x180027cf8  jz      short loc_180027D4D
0x180027cfa  mov     r9d, eax
0x180027cfd  lea     r8, aSharedsocketCr_0; "SharedSocket::CreateRetryTriggerMonitor"...
0x180027d04  jmp     short loc_180027CB6
0x180027d06  mov     rdx, [rbx+50h]
0x180027d0a  lea     rax, [rbx+0E8h]
0x180027d11  imul    ecx, [rbx+0F4h], 3E8h; unsigned int
0x180027d1b  lea     r9, ?HandleRetryTriggerCallback@SharedSocket@@CAXPEAXU_CBROKERED_EVENT_ID@@00KKPEAW4_BI_ACTIVATION_STATUS@@@Z; void (__high *)(void *, struct _CBROKERED_EVENT_ID, void *, void *, unsigned int, unsigned int, enum _BI_ACTIVATION_STATUS *)
0x180027d22  mov     [rbx+74h], edi
0x180027d25  mov     r8, rbx; void *
0x180027d28  mov     [rsp+38h+var_18], rax; void **
0x180027d2d  mov     rdx, [rdx+30h]; unsigned __int16 *
0x180027d31  call    ?CreateWakeTimer@WakeTimer@@SAKKPEAGPEAXP6AX1U_CBROKERED_EVENT_ID@@11KKPEAW4_BI_ACTIVATION_STATUS@@@ZPEAPEAX@Z; WakeTimer::CreateWakeTimer(ulong,ushort *,void *,void (*)(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *),void * *)
0x180027d36  mov     edi, eax
0x180027d38  mov     eax, [rbx+0F4h]
0x180027d3e  add     eax, eax
0x180027d40  mov     [rbx+0F4h], eax
0x180027d46  jmp     short loc_180027D4D
0x180027d48  mov     edi, 139Fh
0x180027d4d  lea     rcx, [rbx+28h]; lpCriticalSection
0x180027d51  call    cs:__imp_LeaveCriticalSection
0x180027d57  mov     rbx, [rsp+38h+arg_0]
0x180027d5c  mov     eax, edi
0x180027d5e  mov     rsi, [rsp+38h+arg_8]
0x180027d63  add     rsp, 30h
0x180027d67  pop     rdi
0x180027d68  retn
```
