# CWaitProcThread::CreateDispatchThread(void)

- ea: `0x18003959c`
- end: `0x1800396ca`
- name: `?CreateDispatchThread@CWaitProcThread@@QEAAJXZ`
- size: `302`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18002c8cc`

## callees

- `0x18003959c`
- `0x180079728`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x180039650`
- `msvcrt!_beginthreadex` at `0x180039650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800395d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003965e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800395d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003965e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800395c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039605`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800395c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039605`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180039698`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180039698`

## pseudocode

```c
__int64 __fastcall CWaitProcThread::CreateDispatchThread(void **this)
{
  signed int v2; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v5; // rax
  signed int v6; // eax
  void *v7; // rax
  signed int v8; // eax
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( *this )
  {
    return 1;
  }
  else
  {
    v2 = 0;
    if ( this[2] )
      goto LABEL_22;
    EventW = CreateEventW(0, 1, 0, 0);
    this[2] = EventW;
    if ( EventW )
      goto LABEL_22;
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_22:
      if ( !this[5] )
      {
        v5 = CreateEventW(0, 1, 0, 0);
        this[5] = v5;
        if ( !v5 )
        {
          v6 = GetLastError();
          v2 = v6;
          if ( v6 > 0 )
            v2 = (unsigned __int16)v6 | 0x80070000;
        }
      }
      if ( v2 >= 0 )
      {
        v7 = (void *)_beginthreadex(0, 0, CWaitProcThread::DispatchThreadProc, this, 0, 0);
        *this = v7;
        if ( v7 )
          goto LABEL_16;
        v8 = GetLastError();
        v2 = v8;
        if ( v8 > 0 )
          v2 = (unsigned __int16)v8 | 0x80070000;
        if ( v2 >= 0 )
        {
LABEL_16:
          Handles[0] = this[2];
          Handles[1] = *this;
          if ( WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) )
          {
            SafeCloseHandle(this);
            *this = 0;
            return (unsigned int)-2147467259;
          }
        }
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003959c  mov     [rsp+arg_0], rbx
0x1800395a1  push    rdi
0x1800395a2  sub     rsp, 40h
0x1800395a6  cmp     qword ptr [rcx], 0
0x1800395aa  mov     rdi, rcx
0x1800395ad  jnz     loc_1800396B8
0x1800395b3  xor     ebx, ebx
0x1800395b5  cmp     [rcx+10h], rbx
0x1800395b9  jnz     short loc_1800395F2
0x1800395bb  xor     r9d, r9d; lpName
0x1800395be  lea     edx, [rbx+1]; bManualReset
0x1800395c1  xor     r8d, r8d; bInitialState
0x1800395c4  xor     ecx, ecx; lpEventAttributes
0x1800395c6  call    cs:__imp_CreateEventW
0x1800395cc  mov     [rdi+10h], rax
0x1800395d0  test    rax, rax
0x1800395d3  jnz     short loc_1800395F2
0x1800395d5  call    cs:__imp_GetLastError
0x1800395db  mov     ebx, eax
0x1800395dd  test    eax, eax
0x1800395df  jle     short loc_1800395EA
0x1800395e1  movzx   ebx, ax
0x1800395e4  or      ebx, 80070000h
0x1800395ea  test    ebx, ebx
0x1800395ec  js      loc_1800396BD
0x1800395f2  cmp     qword ptr [rdi+28h], 0
0x1800395f7  jnz     short loc_180039629
0x1800395f9  xor     r9d, r9d; lpName
0x1800395fc  xor     r8d, r8d; bInitialState
0x1800395ff  xor     ecx, ecx; lpEventAttributes
0x180039601  lea     edx, [r9+1]; bManualReset
0x180039605  call    cs:__imp_CreateEventW
0x18003960b  mov     [rdi+28h], rax
0x18003960f  test    rax, rax
0x180039612  jnz     short loc_180039629
0x180039614  call    cs:__imp_GetLastError
0x18003961a  mov     ebx, eax
0x18003961c  test    eax, eax
0x18003961e  jle     short loc_180039629
0x180039620  movzx   ebx, ax
0x180039623  or      ebx, 80070000h
0x180039629  test    ebx, ebx
0x18003962b  js      loc_1800396BD
0x180039631  mov     [rsp+48h+ThrdAddr], 0; ThrdAddr
0x18003963a  lea     r8, ?DispatchThreadProc@CWaitProcThread@@CAKPEAX@Z; StartAddress
0x180039641  mov     r9, rdi; ArgList
0x180039644  mov     [rsp+48h+InitFlag], 0; InitFlag
0x18003964c  xor     edx, edx; StackSize
0x18003964e  xor     ecx, ecx; Security
0x180039650  call    cs:__imp__beginthreadex
0x180039656  mov     [rdi], rax
0x180039659  test    rax, rax
0x18003965c  jnz     short loc_180039677
0x18003965e  call    cs:__imp_GetLastError
0x180039664  mov     ebx, eax
0x180039666  test    eax, eax
0x180039668  jle     short loc_180039673
0x18003966a  movzx   ebx, ax
0x18003966d  or      ebx, 80070000h
0x180039673  test    ebx, ebx
0x180039675  js      short loc_1800396BD
0x180039677  mov     rax, [rdi+10h]
0x18003967b  lea     rdx, [rsp+48h+Handles]; lpHandles
0x180039680  xor     r8d, r8d; bWaitAll
0x180039683  mov     [rsp+48h+Handles], rax
0x180039688  mov     rax, [rdi]
0x18003968b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18003968f  mov     [rsp+48h+var_10], rax
0x180039694  lea     ecx, [r8+2]; nCount
0x180039698  call    cs:__imp_WaitForMultipleObjects
0x18003969e  test    eax, eax
0x1800396a0  jz      short loc_1800396BD
0x1800396a2  mov     rcx, rdi; void **
0x1800396a5  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x1800396aa  mov     qword ptr [rdi], 0
0x1800396b1  mov     ebx, 80004005h
0x1800396b6  jmp     short loc_1800396BD
0x1800396b8  mov     ebx, 1
0x1800396bd  mov     eax, ebx
0x1800396bf  mov     rbx, [rsp+48h+arg_0]
0x1800396c4  add     rsp, 40h
0x1800396c8  pop     rdi
0x1800396c9  retn
```
