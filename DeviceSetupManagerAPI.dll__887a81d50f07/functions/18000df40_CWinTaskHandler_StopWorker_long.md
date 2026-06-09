# CWinTaskHandler::StopWorker(long *)

- ea: `0x18000df40`
- end: `0x18000dfa9`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000df40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000df6c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000df6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df82`

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
0x18000df40  mov     [rsp+arg_0], rbx
0x18000df45  push    rdi
0x18000df46  sub     rsp, 20h
0x18000df4a  cmp     qword ptr [rcx+28h], 0
0x18000df4f  mov     rdi, rcx
0x18000df52  jnz     short loc_18000DF5B
0x18000df54  mov     ebx, 80070057h
0x18000df59  jmp     short loc_18000DF97
0x18000df5b  mov     eax, 1
0x18000df60  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000df63  xchg    eax, [rcx+24h]
0x18000df66  mov     rcx, [rcx+28h]; hHandle
0x18000df6a  xor     ebx, ebx
0x18000df6c  call    cs:__imp_WaitForSingleObject
0x18000df72  test    eax, eax
0x18000df74  jz      short loc_18000DF97
0x18000df76  cmp     eax, 0FFFFFFFFh
0x18000df79  jz      short loc_18000DF82
0x18000df7b  mov     ebx, 80004005h
0x18000df80  jmp     short loc_18000DF97
0x18000df82  call    cs:__imp_GetLastError
0x18000df88  mov     ebx, eax
0x18000df8a  test    eax, eax
0x18000df8c  jle     short loc_18000DF97
0x18000df8e  movzx   ebx, ax
0x18000df91  or      ebx, 80070000h
0x18000df97  xor     ecx, ecx
0x18000df99  mov     eax, ebx
0x18000df9b  xchg    ecx, [rdi+24h]
0x18000df9e  mov     rbx, [rsp+28h+arg_0]
0x18000dfa3  add     rsp, 20h
0x18000dfa7  pop     rdi
0x18000dfa8  retn
```
