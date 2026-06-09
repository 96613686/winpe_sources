# CWinTaskHandler::StopWorker(long *)

- ea: `0x180003734`
- end: `0x18000379d`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x1800037b0`

## callees

- `0x180003734`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003776`
- `KERNEL32!GetLastError` at `0x180003776`
- `KERNEL32!WaitForSingleObject` at `0x180003760`
- `KERNEL32!WaitForSingleObject` at `0x180003760`

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
0x180003734  mov     [rsp+arg_0], rbx
0x180003739  push    rdi
0x18000373a  sub     rsp, 20h
0x18000373e  cmp     qword ptr [rcx+28h], 0
0x180003743  mov     rdi, rcx
0x180003746  jnz     short loc_18000374F
0x180003748  mov     ebx, 80070057h
0x18000374d  jmp     short loc_18000378B
0x18000374f  mov     eax, 1
0x180003754  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003757  xchg    eax, [rcx+24h]
0x18000375a  mov     rcx, [rcx+28h]; hHandle
0x18000375e  xor     ebx, ebx
0x180003760  call    cs:__imp_WaitForSingleObject
0x180003766  test    eax, eax
0x180003768  jz      short loc_18000378B
0x18000376a  cmp     eax, 0FFFFFFFFh
0x18000376d  jz      short loc_180003776
0x18000376f  mov     ebx, 80004005h
0x180003774  jmp     short loc_18000378B
0x180003776  call    cs:__imp_GetLastError
0x18000377c  mov     ebx, eax
0x18000377e  test    eax, eax
0x180003780  jle     short loc_18000378B
0x180003782  movzx   ebx, ax
0x180003785  or      ebx, 80070000h
0x18000378b  xor     ecx, ecx
0x18000378d  mov     eax, ebx
0x18000378f  xchg    ecx, [rdi+24h]
0x180003792  mov     rbx, [rsp+28h+arg_0]
0x180003797  add     rsp, 20h
0x18000379b  pop     rdi
0x18000379c  retn
```
