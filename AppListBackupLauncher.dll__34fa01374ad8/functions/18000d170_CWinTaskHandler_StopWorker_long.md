# CWinTaskHandler::StopWorker(long *)

- ea: `0x18000d170`
- end: `0x18000d1d9`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000d170`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d19c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d19c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1b2`

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
0x18000d170  mov     [rsp+arg_0], rbx
0x18000d175  push    rdi
0x18000d176  sub     rsp, 20h
0x18000d17a  cmp     qword ptr [rcx+28h], 0
0x18000d17f  mov     rdi, rcx
0x18000d182  jnz     short loc_18000D18B
0x18000d184  mov     ebx, 80070057h
0x18000d189  jmp     short loc_18000D1C7
0x18000d18b  mov     eax, 1
0x18000d190  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d193  xchg    eax, [rcx+24h]
0x18000d196  mov     rcx, [rcx+28h]; hHandle
0x18000d19a  xor     ebx, ebx
0x18000d19c  call    cs:__imp_WaitForSingleObject
0x18000d1a2  test    eax, eax
0x18000d1a4  jz      short loc_18000D1C7
0x18000d1a6  cmp     eax, 0FFFFFFFFh
0x18000d1a9  jz      short loc_18000D1B2
0x18000d1ab  mov     ebx, 80004005h
0x18000d1b0  jmp     short loc_18000D1C7
0x18000d1b2  call    cs:__imp_GetLastError
0x18000d1b8  mov     ebx, eax
0x18000d1ba  test    eax, eax
0x18000d1bc  jle     short loc_18000D1C7
0x18000d1be  movzx   ebx, ax
0x18000d1c1  or      ebx, 80070000h
0x18000d1c7  xor     ecx, ecx
0x18000d1c9  mov     eax, ebx
0x18000d1cb  xchg    ecx, [rdi+24h]
0x18000d1ce  mov     rbx, [rsp+28h+arg_0]
0x18000d1d3  add     rsp, 20h
0x18000d1d7  pop     rdi
0x18000d1d8  retn
```
