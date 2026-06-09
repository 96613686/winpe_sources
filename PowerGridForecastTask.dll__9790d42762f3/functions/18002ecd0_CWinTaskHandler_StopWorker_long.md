# CWinTaskHandler::StopWorker(long *)

- ea: `0x18002ecd0`
- end: `0x18002ed39`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18002ecd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ed12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ed12`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002ecfc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002ecfc`

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
0x18002ecd0  mov     [rsp+arg_0], rbx
0x18002ecd5  push    rdi
0x18002ecd6  sub     rsp, 20h
0x18002ecda  cmp     qword ptr [rcx+28h], 0
0x18002ecdf  mov     rdi, rcx
0x18002ece2  jnz     short loc_18002ECEB
0x18002ece4  mov     ebx, 80070057h
0x18002ece9  jmp     short loc_18002ED27
0x18002eceb  mov     eax, 1
0x18002ecf0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002ecf3  xchg    eax, [rcx+24h]
0x18002ecf6  mov     rcx, [rcx+28h]; hHandle
0x18002ecfa  xor     ebx, ebx
0x18002ecfc  call    cs:__imp_WaitForSingleObject
0x18002ed02  test    eax, eax
0x18002ed04  jz      short loc_18002ED27
0x18002ed06  cmp     eax, 0FFFFFFFFh
0x18002ed09  jz      short loc_18002ED12
0x18002ed0b  mov     ebx, 80004005h
0x18002ed10  jmp     short loc_18002ED27
0x18002ed12  call    cs:__imp_GetLastError
0x18002ed18  mov     ebx, eax
0x18002ed1a  test    eax, eax
0x18002ed1c  jle     short loc_18002ED27
0x18002ed1e  movzx   ebx, ax
0x18002ed21  or      ebx, 80070000h
0x18002ed27  xor     ecx, ecx
0x18002ed29  mov     eax, ebx
0x18002ed2b  xchg    ecx, [rdi+24h]
0x18002ed2e  mov     rbx, [rsp+28h+arg_0]
0x18002ed33  add     rsp, 20h
0x18002ed37  pop     rdi
0x18002ed38  retn
```
