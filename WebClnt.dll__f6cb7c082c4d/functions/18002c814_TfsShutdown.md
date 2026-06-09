# TfsShutdown

- ea: `0x18002c814`
- end: `0x18002c945`
- name: `TfsShutdown`
- size: `305`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fb90`
- `0x18002b8f8`

## callees

- `0x18000b7dc`
- `0x18002c814`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c8fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c918`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c8fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c918`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c85a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c85a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c839`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c839`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c8e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c8e9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c86a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c86a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c84d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c84d`

## pseudocode

```c
__int64 TfsShutdown()
{
  __int64 result; // rax
  DWORD v1; // eax
  DWORD v2; // ebx
  DWORD LastError; // eax

  if ( TfsInitialized != 1 )
    return 5023;
  EnterCriticalSection(&TfsGlobalLock);
  TfsShutdownInitiated = 1;
  SetEvent(TfsShutdownEvent);
  LeaveCriticalSection(&TfsGlobalLock);
  v1 = WaitForSingleObject(hTfsScavengerThread, 0xFFFFFFFF);
  v2 = v1;
  if ( v1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, v1);
    if ( v2 == -1 )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, LastError);
    }
    else
    {
      v2 = 0;
    }
  }
  DeleteCriticalSection(&TfsGlobalLock);
  if ( TfsShutdownEvent )
  {
    CloseHandle(TfsShutdownEvent);
    TfsShutdownEvent = 0;
  }
  if ( hTfsScavengerThread )
  {
    CloseHandle(hTfsScavengerThread);
    hTfsScavengerThread = 0;
  }
  TfsInitialized = 0;
  result = v2;
  TfsShutdownInitiated = 0;
  return result;
}

```

## disassembly

```asm
0x18002c814  mov     [rsp+arg_0], rbx
0x18002c819  push    r14
0x18002c81b  sub     rsp, 20h
0x18002c81f  cmp     cs:TfsInitialized, 1
0x18002c826  jz      short loc_18002C832
0x18002c828  mov     eax, 139Fh
0x18002c82d  jmp     loc_18002C939
0x18002c832  lea     rcx, TfsGlobalLock; lpCriticalSection
0x18002c839  call    cs:__imp_EnterCriticalSection
0x18002c83f  mov     rcx, cs:TfsShutdownEvent; hEvent
0x18002c846  mov     cs:TfsShutdownInitiated, 1
0x18002c84d  call    cs:__imp_SetEvent
0x18002c853  lea     rcx, TfsGlobalLock; lpCriticalSection
0x18002c85a  call    cs:__imp_LeaveCriticalSection
0x18002c860  mov     rcx, cs:hTfsScavengerThread; hHandle
0x18002c867  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002c86a  call    cs:__imp_WaitForSingleObject
0x18002c870  mov     ebx, eax
0x18002c872  test    eax, eax
0x18002c874  jz      short loc_18002C8E2
0x18002c876  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c87d  lea     r14, WPP_GLOBAL_Control
0x18002c884  cmp     rcx, r14
0x18002c887  jz      short loc_18002C8A7
0x18002c889  test    byte ptr [rcx+1Ch], 1
0x18002c88d  jz      short loc_18002C8A7
0x18002c88f  mov     rcx, [rcx+10h]
0x18002c893  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002c89a  mov     edx, 0Fh
0x18002c89f  mov     r9d, eax
0x18002c8a2  call    WPP_SF_d
0x18002c8a7  cmp     ebx, 0FFFFFFFFh
0x18002c8aa  jnz     short loc_18002C8E0
0x18002c8ac  call    cs:__imp_GetLastError
0x18002c8b2  mov     ebx, eax
0x18002c8b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c8bb  cmp     rcx, r14
0x18002c8be  jz      short loc_18002C8E2
0x18002c8c0  test    byte ptr [rcx+1Ch], 1
0x18002c8c4  jz      short loc_18002C8E2
0x18002c8c6  mov     rcx, [rcx+10h]
0x18002c8ca  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002c8d1  mov     edx, 10h
0x18002c8d6  mov     r9d, eax
0x18002c8d9  call    WPP_SF_d
0x18002c8de  jmp     short loc_18002C8E2
0x18002c8e0  xor     ebx, ebx
0x18002c8e2  lea     rcx, TfsGlobalLock; lpCriticalSection
0x18002c8e9  call    cs:__imp_DeleteCriticalSection
0x18002c8ef  mov     rcx, cs:TfsShutdownEvent; hObject
0x18002c8f6  test    rcx, rcx
0x18002c8f9  jz      short loc_18002C90C
0x18002c8fb  call    cs:__imp_CloseHandle
0x18002c901  mov     cs:TfsShutdownEvent, 0
0x18002c90c  mov     rcx, cs:hTfsScavengerThread; hObject
0x18002c913  test    rcx, rcx
0x18002c916  jz      short loc_18002C929
0x18002c918  call    cs:__imp_CloseHandle
0x18002c91e  mov     cs:hTfsScavengerThread, 0
0x18002c929  mov     cs:TfsInitialized, 0
0x18002c930  mov     eax, ebx
0x18002c932  mov     cs:TfsShutdownInitiated, 0
0x18002c939  mov     rbx, [rsp+28h+arg_0]
0x18002c93e  add     rsp, 20h
0x18002c942  pop     r14
0x18002c944  retn
```
