# CWinTaskHandler::StopWorker(long *)

- ea: `0x180002b30`
- end: `0x180002b99`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b72`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002b5c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002b5c`

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
0x180002b30  mov     [rsp+arg_0], rbx
0x180002b35  push    rdi
0x180002b36  sub     rsp, 20h
0x180002b3a  cmp     qword ptr [rcx+28h], 0
0x180002b3f  mov     rdi, rcx
0x180002b42  jnz     short loc_180002B4B
0x180002b44  mov     ebx, 80070057h
0x180002b49  jmp     short loc_180002B87
0x180002b4b  mov     eax, 1
0x180002b50  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002b53  xchg    eax, [rcx+24h]
0x180002b56  mov     rcx, [rcx+28h]; hHandle
0x180002b5a  xor     ebx, ebx
0x180002b5c  call    cs:__imp_WaitForSingleObject
0x180002b62  test    eax, eax
0x180002b64  jz      short loc_180002B87
0x180002b66  cmp     eax, 0FFFFFFFFh
0x180002b69  jz      short loc_180002B72
0x180002b6b  mov     ebx, 80004005h
0x180002b70  jmp     short loc_180002B87
0x180002b72  call    cs:__imp_GetLastError
0x180002b78  mov     ebx, eax
0x180002b7a  test    eax, eax
0x180002b7c  jle     short loc_180002B87
0x180002b7e  movzx   ebx, ax
0x180002b81  or      ebx, 80070000h
0x180002b87  xor     ecx, ecx
0x180002b89  mov     eax, ebx
0x180002b8b  xchg    ecx, [rdi+24h]
0x180002b8e  mov     rbx, [rsp+28h+arg_0]
0x180002b93  add     rsp, 20h
0x180002b97  pop     rdi
0x180002b98  retn
```
