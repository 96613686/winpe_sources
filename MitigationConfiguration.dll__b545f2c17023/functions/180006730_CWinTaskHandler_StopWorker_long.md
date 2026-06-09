# CWinTaskHandler::StopWorker(long *)

- ea: `0x180006730`
- end: `0x180006799`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180006730`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000675c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000675c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006772`

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
0x180006730  mov     [rsp+arg_0], rbx
0x180006735  push    rdi
0x180006736  sub     rsp, 20h
0x18000673a  cmp     qword ptr [rcx+28h], 0
0x18000673f  mov     rdi, rcx
0x180006742  jnz     short loc_18000674B
0x180006744  mov     ebx, 80070057h
0x180006749  jmp     short loc_180006787
0x18000674b  mov     eax, 1
0x180006750  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006753  xchg    eax, [rcx+24h]
0x180006756  mov     rcx, [rcx+28h]; hHandle
0x18000675a  xor     ebx, ebx
0x18000675c  call    cs:__imp_WaitForSingleObject
0x180006762  test    eax, eax
0x180006764  jz      short loc_180006787
0x180006766  cmp     eax, 0FFFFFFFFh
0x180006769  jz      short loc_180006772
0x18000676b  mov     ebx, 80004005h
0x180006770  jmp     short loc_180006787
0x180006772  call    cs:__imp_GetLastError
0x180006778  mov     ebx, eax
0x18000677a  test    eax, eax
0x18000677c  jle     short loc_180006787
0x18000677e  movzx   ebx, ax
0x180006781  or      ebx, 80070000h
0x180006787  xor     ecx, ecx
0x180006789  mov     eax, ebx
0x18000678b  xchg    ecx, [rdi+24h]
0x18000678e  mov     rbx, [rsp+28h+arg_0]
0x180006793  add     rsp, 20h
0x180006797  pop     rdi
0x180006798  retn
```
