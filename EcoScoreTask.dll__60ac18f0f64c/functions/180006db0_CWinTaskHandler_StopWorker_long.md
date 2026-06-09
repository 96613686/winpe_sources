# CWinTaskHandler::StopWorker(long *)

- ea: `0x180006db0`
- end: `0x180006e19`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180006db0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006df2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006df2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006ddc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006ddc`

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
0x180006db0  mov     [rsp+arg_0], rbx
0x180006db5  push    rdi
0x180006db6  sub     rsp, 20h
0x180006dba  cmp     qword ptr [rcx+28h], 0
0x180006dbf  mov     rdi, rcx
0x180006dc2  jnz     short loc_180006DCB
0x180006dc4  mov     ebx, 80070057h
0x180006dc9  jmp     short loc_180006E07
0x180006dcb  mov     eax, 1
0x180006dd0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006dd3  xchg    eax, [rcx+24h]
0x180006dd6  mov     rcx, [rcx+28h]; hHandle
0x180006dda  xor     ebx, ebx
0x180006ddc  call    cs:__imp_WaitForSingleObject
0x180006de2  test    eax, eax
0x180006de4  jz      short loc_180006E07
0x180006de6  cmp     eax, 0FFFFFFFFh
0x180006de9  jz      short loc_180006DF2
0x180006deb  mov     ebx, 80004005h
0x180006df0  jmp     short loc_180006E07
0x180006df2  call    cs:__imp_GetLastError
0x180006df8  mov     ebx, eax
0x180006dfa  test    eax, eax
0x180006dfc  jle     short loc_180006E07
0x180006dfe  movzx   ebx, ax
0x180006e01  or      ebx, 80070000h
0x180006e07  xor     ecx, ecx
0x180006e09  mov     eax, ebx
0x180006e0b  xchg    ecx, [rdi+24h]
0x180006e0e  mov     rbx, [rsp+28h+arg_0]
0x180006e13  add     rsp, 20h
0x180006e17  pop     rdi
0x180006e18  retn
```
