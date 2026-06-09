# TThread<CProtocolHandlerCreationThread>::StartThread(ulong)

- ea: `0x14002925c`
- end: `0x1400292bd`
- name: `?StartThread@?$TThread@VCProtocolHandlerCreationThread@@@@QEAAJK@Z`
- size: `97`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003a8e8`

## callees

- `0x14002925c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400292a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400292a1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140029292`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140029292`

## pseudocode

```c
signed int __fastcall TThread<CProtocolHandlerCreationThread>::StartThread(LPVOID lpParameter)
{
  HANDLE Thread; // rax
  signed int result; // eax

  if ( *((_QWORD *)lpParameter + 2) )
    return 0;
  *((_DWORD *)lpParameter + 10) = 0;
  Thread = CreateThread(0, 0, CProtocolHandlerCreationThread::Thread, lpParameter, 0, (LPDWORD)lpParameter + 12);
  *((_QWORD *)lpParameter + 2) = Thread;
  if ( Thread )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14002925c  push    rbx
0x14002925e  sub     rsp, 30h
0x140029262  cmp     qword ptr [rcx+10h], 0
0x140029267  mov     rbx, rcx
0x14002926a  jnz     short loc_1400292B5
0x14002926c  lea     rax, [rcx+30h]
0x140029270  mov     dword ptr [rcx+28h], 0
0x140029277  mov     r9, rcx; lpParameter
0x14002927a  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x14002927f  lea     r8, ?Thread@CProtocolHandlerCreationThread@@SAXPEAV1@@Z; lpStartAddress
0x140029286  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x14002928e  xor     edx, edx; dwStackSize
0x140029290  xor     ecx, ecx; lpThreadAttributes
0x140029292  call    cs:__imp_CreateThread
0x140029298  mov     [rbx+10h], rax
0x14002929c  test    rax, rax
0x14002929f  jnz     short loc_1400292B5
0x1400292a1  call    cs:__imp_GetLastError
0x1400292a7  test    eax, eax
0x1400292a9  jle     short loc_1400292B7
0x1400292ab  movzx   eax, ax
0x1400292ae  or      eax, 80070000h
0x1400292b3  jmp     short loc_1400292B7
0x1400292b5  xor     eax, eax
0x1400292b7  add     rsp, 30h
0x1400292bb  pop     rbx
0x1400292bc  retn
```
