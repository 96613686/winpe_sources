# CWinTaskHandler::StopWorker(long *)

- ea: `0x180009360`
- end: `0x1800093c9`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180009360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000938c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000938c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093a2`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::StopWorker(CWinTaskHandler *this, int *a2)
{
  unsigned int v3; // ebx
  DWORD v4; // eax
  signed int LastError; // eax
  __int64 result; // rax

  if ( *((_QWORD *)this + 5) )
  {
    _InterlockedExchange((volatile __int32 *)this + 9, 1);
    v3 = 0;
    v4 = WaitForSingleObject(*((HANDLE *)this + 5), 0xFFFFFFFF);
    if ( v4 )
    {
      if ( v4 == -1 )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v3 = -2147467259;
      }
    }
  }
  else
  {
    v3 = -2147024809;
  }
  result = v3;
  _InterlockedExchange((volatile __int32 *)this + 9, 0);
  return result;
}

```

## disassembly

```asm
0x180009360  mov     [rsp+arg_0], rbx
0x180009365  push    rdi
0x180009366  sub     rsp, 20h
0x18000936a  cmp     qword ptr [rcx+28h], 0
0x18000936f  mov     rdi, rcx
0x180009372  jnz     short loc_18000937B
0x180009374  mov     ebx, 80070057h
0x180009379  jmp     short loc_1800093B7
0x18000937b  mov     eax, 1
0x180009380  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009383  xchg    eax, [rcx+24h]
0x180009386  mov     rcx, [rcx+28h]; hHandle
0x18000938a  xor     ebx, ebx
0x18000938c  call    cs:__imp_WaitForSingleObject
0x180009392  test    eax, eax
0x180009394  jz      short loc_1800093B7
0x180009396  cmp     eax, 0FFFFFFFFh
0x180009399  jz      short loc_1800093A2
0x18000939b  mov     ebx, 80004005h
0x1800093a0  jmp     short loc_1800093B7
0x1800093a2  call    cs:__imp_GetLastError
0x1800093a8  mov     ebx, eax
0x1800093aa  test    eax, eax
0x1800093ac  jle     short loc_1800093B7
0x1800093ae  movzx   ebx, ax
0x1800093b1  or      ebx, 80070000h
0x1800093b7  xor     ecx, ecx
0x1800093b9  mov     eax, ebx
0x1800093bb  xchg    ecx, [rdi+24h]
0x1800093be  mov     rbx, [rsp+28h+arg_0]
0x1800093c3  add     rsp, 20h
0x1800093c7  pop     rdi
0x1800093c8  retn
```
