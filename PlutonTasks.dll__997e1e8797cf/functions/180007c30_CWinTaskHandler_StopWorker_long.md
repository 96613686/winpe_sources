# CWinTaskHandler::StopWorker(long *)

- ea: `0x180007c30`
- end: `0x180007c99`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180007c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007c5c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c72`

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
0x180007c30  mov     [rsp+arg_0], rbx
0x180007c35  push    rdi
0x180007c36  sub     rsp, 20h
0x180007c3a  cmp     qword ptr [rcx+28h], 0
0x180007c3f  mov     rdi, rcx
0x180007c42  jnz     short loc_180007C4B
0x180007c44  mov     ebx, 80070057h
0x180007c49  jmp     short loc_180007C87
0x180007c4b  mov     eax, 1
0x180007c50  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007c53  xchg    eax, [rcx+24h]
0x180007c56  mov     rcx, [rcx+28h]; hHandle
0x180007c5a  xor     ebx, ebx
0x180007c5c  call    cs:__imp_WaitForSingleObject
0x180007c62  test    eax, eax
0x180007c64  jz      short loc_180007C87
0x180007c66  cmp     eax, 0FFFFFFFFh
0x180007c69  jz      short loc_180007C72
0x180007c6b  mov     ebx, 80004005h
0x180007c70  jmp     short loc_180007C87
0x180007c72  call    cs:__imp_GetLastError
0x180007c78  mov     ebx, eax
0x180007c7a  test    eax, eax
0x180007c7c  jle     short loc_180007C87
0x180007c7e  movzx   ebx, ax
0x180007c81  or      ebx, 80070000h
0x180007c87  xor     ecx, ecx
0x180007c89  mov     eax, ebx
0x180007c8b  xchg    ecx, [rdi+24h]
0x180007c8e  mov     rbx, [rsp+28h+arg_0]
0x180007c93  add     rsp, 20h
0x180007c97  pop     rdi
0x180007c98  retn
```
