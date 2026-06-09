# CWinTaskHandler::StopWorker(long *)

- ea: `0x180002dc0`
- end: `0x180002e29`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e02`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002dec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002dec`

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
0x180002dc0  mov     [rsp+arg_0], rbx
0x180002dc5  push    rdi
0x180002dc6  sub     rsp, 20h
0x180002dca  cmp     qword ptr [rcx+28h], 0
0x180002dcf  mov     rdi, rcx
0x180002dd2  jnz     short loc_180002DDB
0x180002dd4  mov     ebx, 80070057h
0x180002dd9  jmp     short loc_180002E17
0x180002ddb  mov     eax, 1
0x180002de0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002de3  xchg    eax, [rcx+24h]
0x180002de6  mov     rcx, [rcx+28h]; hHandle
0x180002dea  xor     ebx, ebx
0x180002dec  call    cs:__imp_WaitForSingleObject
0x180002df2  test    eax, eax
0x180002df4  jz      short loc_180002E17
0x180002df6  cmp     eax, 0FFFFFFFFh
0x180002df9  jz      short loc_180002E02
0x180002dfb  mov     ebx, 80004005h
0x180002e00  jmp     short loc_180002E17
0x180002e02  call    cs:__imp_GetLastError
0x180002e08  mov     ebx, eax
0x180002e0a  test    eax, eax
0x180002e0c  jle     short loc_180002E17
0x180002e0e  movzx   ebx, ax
0x180002e11  or      ebx, 80070000h
0x180002e17  xor     ecx, ecx
0x180002e19  mov     eax, ebx
0x180002e1b  xchg    ecx, [rdi+24h]
0x180002e1e  mov     rbx, [rsp+28h+arg_0]
0x180002e23  add     rsp, 20h
0x180002e27  pop     rdi
0x180002e28  retn
```
