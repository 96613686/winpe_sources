# BackgroundThreadStartup(void)

- ea: `0x18009f9ac`
- end: `0x18009fa52`
- name: `?BackgroundThreadStartup@@YAHXZ`
- size: `166`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009e77c`
- `0x1801143b0`

## callees

- `0x18009f9ac`
- `0x18009fa58`
- `0x18009fb94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f9f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f9f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009fa0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009fa0c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f9c2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f9dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f9c2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f9dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009fa4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009fa4a`

## pseudocode

```c
__int64 BackgroundThreadStartup(void)
{
  HANDLE EventW; // rbx
  HANDLE v1; // rdi
  unsigned __int64 v2; // rdx
  struct _SECURITY_ATTRIBUTES *v3; // rcx
  unsigned int (*v4)(void *); // r8
  void *v5; // r9
  unsigned int v7; // [rsp+20h] [rbp-18h]
  unsigned int *v8; // [rsp+28h] [rbp-10h]

  EventW = CreateEventW(0, 1, 0, 0);
  if ( !EventW )
    goto LABEL_4;
  v1 = CreateEventW(0, 1, 0, 0);
  if ( !v1 )
  {
    CloseHandle(EventW);
    goto LABEL_4;
  }
  EnterCriticalSection(&BackgroundThreadCriticalSection::critSec);
  Globals::ThreadQuitEvent = EventW;
  Globals::ThreadNotify = v1;
  LeaveCriticalSection(&BackgroundThreadCriticalSection::critSec);
  Globals::BackgroundThreadHandle = CreateThreadAndAddRefDll(v3, v2, v4, v5, v7, v8);
  if ( !Globals::BackgroundThreadHandle )
  {
LABEL_4:
    BackgroundThreadShutdown();
    return 0;
  }
  Globals::HiddenWindowOwnerToken = 1;
  return 1;
}

```

## disassembly

```asm
0x18009f9ac  mov     [rsp+arg_0], rbx
0x18009f9b1  push    rdi
0x18009f9b2  sub     rsp, 30h
0x18009f9b6  xor     r9d, r9d; lpName
0x18009f9b9  xor     r8d, r8d; bInitialState
0x18009f9bc  xor     ecx, ecx; lpEventAttributes
0x18009f9be  lea     edx, [r9+1]; bManualReset
0x18009f9c2  call    cs:__imp_CreateEventW
0x18009f9c8  mov     rbx, rax
0x18009f9cb  test    rax, rax
0x18009f9ce  jz      short loc_18009FA23
0x18009f9d0  xor     r9d, r9d; lpName
0x18009f9d3  xor     r8d, r8d; bInitialState
0x18009f9d6  xor     ecx, ecx; lpEventAttributes
0x18009f9d8  lea     edx, [r9+1]; bManualReset
0x18009f9dc  call    cs:__imp_CreateEventW
0x18009f9e2  mov     rdi, rax
0x18009f9e5  test    rax, rax
0x18009f9e8  jz      short loc_18009FA47
0x18009f9ea  lea     rcx, ?critSec@BackgroundThreadCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009f9f1  call    cs:__imp_EnterCriticalSection
0x18009f9f7  lea     rcx, ?critSec@BackgroundThreadCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009f9fe  mov     cs:?ThreadQuitEvent@Globals@@3PEAXEA, rbx; void * Globals::ThreadQuitEvent
0x18009fa05  mov     cs:?ThreadNotify@Globals@@3PEAXEA, rdi; void * Globals::ThreadNotify
0x18009fa0c  call    cs:__imp_LeaveCriticalSection
0x18009fa12  call    ?CreateThreadAndAddRefDll@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@_KP6AKPEAX@Z2KPEAK@Z; CreateThreadAndAddRefDll(_SECURITY_ATTRIBUTES *,unsigned __int64,ulong (*)(void *),void *,ulong,ulong *)
0x18009fa17  mov     cs:?BackgroundThreadHandle@Globals@@3PEAXEA, rax; void * Globals::BackgroundThreadHandle
0x18009fa1e  test    rax, rax
0x18009fa21  jnz     short loc_18009FA35
0x18009fa23  call    ?BackgroundThreadShutdown@@YAPEAXXZ; BackgroundThreadShutdown(void)
0x18009fa28  xor     eax, eax
0x18009fa2a  mov     rbx, [rsp+38h+arg_0]
0x18009fa2f  add     rsp, 30h
0x18009fa33  pop     rdi
0x18009fa34  retn
0x18009fa35  mov     cs:?HiddenWindowOwnerToken@Globals@@3_KA, 1; unsigned __int64 Globals::HiddenWindowOwnerToken
0x18009fa40  mov     eax, 1
0x18009fa45  jmp     short loc_18009FA2A
0x18009fa47  mov     rcx, rbx; hObject
0x18009fa4a  call    cs:__imp_CloseHandle
0x18009fa50  jmp     short loc_18009FA23
```
