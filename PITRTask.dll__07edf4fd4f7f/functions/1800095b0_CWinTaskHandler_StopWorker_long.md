# CWinTaskHandler::StopWorker(long *)

- ea: `0x1800095b0`
- end: `0x180009619`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800095b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800095dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800095dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095f2`

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
0x1800095b0  mov     [rsp+arg_0], rbx
0x1800095b5  push    rdi
0x1800095b6  sub     rsp, 20h
0x1800095ba  cmp     qword ptr [rcx+28h], 0
0x1800095bf  mov     rdi, rcx
0x1800095c2  jnz     short loc_1800095CB
0x1800095c4  mov     ebx, 80070057h
0x1800095c9  jmp     short loc_180009607
0x1800095cb  mov     eax, 1
0x1800095d0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800095d3  xchg    eax, [rcx+24h]
0x1800095d6  mov     rcx, [rcx+28h]; hHandle
0x1800095da  xor     ebx, ebx
0x1800095dc  call    cs:__imp_WaitForSingleObject
0x1800095e2  test    eax, eax
0x1800095e4  jz      short loc_180009607
0x1800095e6  cmp     eax, 0FFFFFFFFh
0x1800095e9  jz      short loc_1800095F2
0x1800095eb  mov     ebx, 80004005h
0x1800095f0  jmp     short loc_180009607
0x1800095f2  call    cs:__imp_GetLastError
0x1800095f8  mov     ebx, eax
0x1800095fa  test    eax, eax
0x1800095fc  jle     short loc_180009607
0x1800095fe  movzx   ebx, ax
0x180009601  or      ebx, 80070000h
0x180009607  xor     ecx, ecx
0x180009609  mov     eax, ebx
0x18000960b  xchg    ecx, [rdi+24h]
0x18000960e  mov     rbx, [rsp+28h+arg_0]
0x180009613  add     rsp, 20h
0x180009617  pop     rdi
0x180009618  retn
```
