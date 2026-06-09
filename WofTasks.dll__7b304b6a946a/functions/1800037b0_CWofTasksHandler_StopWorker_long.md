# CWofTasksHandler::StopWorker(long *)

- ea: `0x1800037b0`
- end: `0x180003847`
- name: `?StopWorker@CWofTasksHandler@@UEAAJPEAJ@Z`
- size: `151`
- prototype: `__int64 __fastcall(CWofTasksHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003734`
- `0x1800037b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800037f1`
- `KERNEL32!GetLastError` at `0x1800037f1`
- `KERNEL32!CloseHandle` at `0x180003810`
- `KERNEL32!CloseHandle` at `0x180003828`
- `KERNEL32!CloseHandle` at `0x180003810`
- `KERNEL32!CloseHandle` at `0x180003828`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800037e7`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800037e7`

## pseudocode

```c
__int64 __fastcall CWofTasksHandler::StopWorker(CWofTasksHandler *this, int *a2)
{
  signed __int32 v4; // ebx
  unsigned int v5; // edi

  v4 = _InterlockedIncrement((volatile signed __int32 *)&HashValidationEvent);
  if ( v4 == 2 && !CancelIoEx(hObject, &Overlapped) )
    GetLastError();
  v5 = CWinTaskHandler::StopWorker(this, a2);
  if ( v4 == 2 )
  {
    CloseHandle(Overlapped.hEvent);
    Overlapped.hEvent = (HANDLE)-1LL;
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
  return v5;
}

```

## disassembly

```asm
0x1800037b0  mov     [rsp+arg_0], rbx
0x1800037b5  mov     [rsp+arg_8], rsi
0x1800037ba  push    rdi
0x1800037bb  sub     rsp, 20h
0x1800037bf  mov     rdi, rdx
0x1800037c2  mov     rsi, rcx
0x1800037c5  mov     ebx, 1
0x1800037ca  lock xadd cs:?HashValidationEvent@@3U_HASH_VALIDATION_EVENT@@A, ebx; _HASH_VALIDATION_EVENT HashValidationEvent
0x1800037d2  inc     ebx
0x1800037d4  cmp     ebx, 2
0x1800037d7  jnz     short loc_1800037F7
0x1800037d9  mov     rcx, cs:hObject; hFile
0x1800037e0  lea     rdx, Overlapped; lpOverlapped
0x1800037e7  call    cs:__imp_CancelIoEx
0x1800037ed  test    eax, eax
0x1800037ef  jnz     short loc_1800037F7
0x1800037f1  call    cs:__imp_GetLastError
0x1800037f7  mov     rdx, rdi; int *
0x1800037fa  mov     rcx, rsi; this
0x1800037fd  call    ?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z; CWinTaskHandler::StopWorker(long *)
0x180003802  mov     edi, eax
0x180003804  cmp     ebx, 2
0x180003807  jnz     short loc_180003835
0x180003809  mov     rcx, cs:Overlapped.hEvent; hObject
0x180003810  call    cs:__imp_CloseHandle
0x180003816  mov     rcx, cs:hObject; hObject
0x18000381d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003821  mov     cs:Overlapped.hEvent, rbx
0x180003828  call    cs:__imp_CloseHandle
0x18000382e  mov     cs:hObject, rbx
0x180003835  mov     rbx, [rsp+28h+arg_0]
0x18000383a  mov     eax, edi
0x18000383c  mov     rsi, [rsp+28h+arg_8]
0x180003841  add     rsp, 20h
0x180003845  pop     rdi
0x180003846  retn
```
