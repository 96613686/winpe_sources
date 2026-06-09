# CWinTaskHandler::StopWorker(long *)

- ea: `0x1800020d0`
- end: `0x180002139`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800020d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800020fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800020fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002112`

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
0x1800020d0  mov     [rsp+arg_0], rbx
0x1800020d5  push    rdi
0x1800020d6  sub     rsp, 20h
0x1800020da  cmp     qword ptr [rcx+28h], 0
0x1800020df  mov     rdi, rcx
0x1800020e2  jnz     short loc_1800020EB
0x1800020e4  mov     ebx, 80070057h
0x1800020e9  jmp     short loc_180002127
0x1800020eb  mov     eax, 1
0x1800020f0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800020f3  xchg    eax, [rcx+24h]
0x1800020f6  mov     rcx, [rcx+28h]; hHandle
0x1800020fa  xor     ebx, ebx
0x1800020fc  call    cs:__imp_WaitForSingleObject
0x180002102  test    eax, eax
0x180002104  jz      short loc_180002127
0x180002106  cmp     eax, 0FFFFFFFFh
0x180002109  jz      short loc_180002112
0x18000210b  mov     ebx, 80004005h
0x180002110  jmp     short loc_180002127
0x180002112  call    cs:__imp_GetLastError
0x180002118  mov     ebx, eax
0x18000211a  test    eax, eax
0x18000211c  jle     short loc_180002127
0x18000211e  movzx   ebx, ax
0x180002121  or      ebx, 80070000h
0x180002127  xor     ecx, ecx
0x180002129  mov     eax, ebx
0x18000212b  xchg    ecx, [rdi+24h]
0x18000212e  mov     rbx, [rsp+28h+arg_0]
0x180002133  add     rsp, 20h
0x180002137  pop     rdi
0x180002138  retn
```
