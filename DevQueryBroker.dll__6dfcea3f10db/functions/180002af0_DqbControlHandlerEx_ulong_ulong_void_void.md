# DqbControlHandlerEx(ulong,ulong,void *,void *)

- ea: `0x180002af0`
- end: `0x180002b95`
- name: `?DqbControlHandlerEx@@YAKKKPEAX0@Z`
- size: `165`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180002af0`
- `0x180002c20`
- `0x180002e18`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180002b75`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180002b75`

## pseudocode

```c
__int64 __fastcall DqbControlHandlerEx(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  unsigned int v4; // ebx
  DWORD v5; // ecx
  unsigned __int64 v6; // rcx
  int v7; // ecx

  _m_prefetchw((const void *)&g_dqbSeviceControlFlags);
  if ( (_InterlockedOr64((volatile signed __int64 *)&g_dqbSeviceControlFlags, 2u) & 1) != 0 )
  {
    v4 = 1115;
    goto LABEL_13;
  }
  v5 = dwControl - 1;
  if ( v5 )
  {
    v6 = v5 - 3;
    if ( !(_DWORD)v6 )
      goto LABEL_9;
    v7 = v6 - 1;
    if ( v7 )
    {
      v6 = (unsigned int)(v7 - 1);
      if ( (_DWORD)v6 )
      {
        v6 = (unsigned int)(v6 - 8);
        if ( (_DWORD)v6 == 18 )
        {
          v4 = 0;
          goto LABEL_13;
        }
      }
LABEL_9:
      v4 = 1052;
      DqbStatusUpdate((struct SERVICE_STATUS_HANDLE__ *)v6, g_dqbCurrentState, 0, 0x41Cu);
      goto LABEL_13;
    }
  }
  v4 = 0;
  if ( !_InterlockedExchange(&g_bDqbStopping, 1) && !TrySubmitThreadpoolCallback(DqbStopThreadProc, 0, 0) )
    DqbServiceStop();
LABEL_13:
  _InterlockedAnd64((volatile signed __int64 *)&g_dqbSeviceControlFlags, 0xFFFFFFFFFFFFFFFDuLL);
  return v4;
}

```

## disassembly

```asm
0x180002af0  push    rbx
0x180002af2  sub     rsp, 20h
0x180002af6  prefetchw byte ptr cs:?g_dqbSeviceControlFlags@@3_KC; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002afd  mov     rax, cs:?g_dqbSeviceControlFlags@@3_KC; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002b04  mov     rdx, rax
0x180002b07  or      rdx, 2
0x180002b0b  lock cmpxchg cs:?g_dqbSeviceControlFlags@@3_KC, rdx; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002b14  jnz     short loc_180002B04
0x180002b16  mov     edx, 1
0x180002b1b  test    dl, al
0x180002b1d  jz      short loc_180002B26
0x180002b1f  mov     ebx, 45Bh
0x180002b24  jmp     short loc_180002B84
0x180002b26  sub     ecx, edx
0x180002b28  jz      short loc_180002B5D
0x180002b2a  sub     ecx, 3; struct SERVICE_STATUS_HANDLE__ *
0x180002b2d  jz      short loc_180002B45
0x180002b2f  sub     ecx, edx
0x180002b31  jz      short loc_180002B5D
0x180002b33  sub     ecx, edx
0x180002b35  jz      short loc_180002B45
0x180002b37  sub     ecx, 8
0x180002b3a  jz      short loc_180002B45
0x180002b3c  cmp     ecx, 12h
0x180002b3f  jnz     short loc_180002B45
0x180002b41  xor     ebx, ebx
0x180002b43  jmp     short loc_180002B84
0x180002b45  mov     edx, cs:?g_dqbCurrentState@@3KA; unsigned int
0x180002b4b  mov     ebx, 41Ch
0x180002b50  mov     r9d, ebx; unsigned int
0x180002b53  xor     r8d, r8d; unsigned int
0x180002b56  call    ?DqbStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DqbStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180002b5b  jmp     short loc_180002B84
0x180002b5d  xchg    edx, cs:?g_bDqbStopping@@3JA; long g_bDqbStopping
0x180002b63  xor     ebx, ebx
0x180002b65  test    edx, edx
0x180002b67  jnz     short loc_180002B84
0x180002b69  xor     r8d, r8d; pcbe
0x180002b6c  lea     rcx, ?DqbStopThreadProc@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180002b73  xor     edx, edx; pv
0x180002b75  call    cs:__imp_TrySubmitThreadpoolCallback
0x180002b7b  test    eax, eax
0x180002b7d  jnz     short loc_180002B84
0x180002b7f  call    ?DqbServiceStop@@YAXXZ; DqbServiceStop(void)
0x180002b84  lock and cs:?g_dqbSeviceControlFlags@@3_KC, 0FFFFFFFFFFFFFFFDh; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002b8d  mov     eax, ebx
0x180002b8f  add     rsp, 20h
0x180002b93  pop     rbx
0x180002b94  retn
```
