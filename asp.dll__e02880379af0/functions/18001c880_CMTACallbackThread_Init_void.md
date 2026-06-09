# CMTACallbackThread::Init(void)

- ea: `0x18001c880`
- end: `0x18001c990`
- name: `?Init@CMTACallbackThread@@QEAAJXZ`
- size: `272`
- prototype: `__int64 __fastcall(CMTACallbackThread *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a64`

## callees

- `0x18001c880`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x18001c958`
- `msvcrt!_beginthreadex` at `0x18001c958`
- `KERNEL32!CreateEventA` at `0x18001c8f3`
- `KERNEL32!CreateEventA` at `0x18001c919`
- `KERNEL32!CreateEventA` at `0x18001c8f3`
- `KERNEL32!CreateEventA` at `0x18001c919`
- `KERNEL32!GetLastError` at `0x18001c8a2`
- `KERNEL32!GetLastError` at `0x18001c8a2`
- `iisutil!IISInitializeCriticalSection` at `0x18001c898`
- `iisutil!IISInitializeCriticalSection` at `0x18001c898`

## pseudocode

```c
__int64 __fastcall CMTACallbackThread::Init(CMTACallbackThread *this)
{
  signed int v1; // ebx
  signed int LastError; // eax
  int v3; // ecx
  void *v4; // rax
  CMTACallbackThread *ThrdAddr; // [rsp+50h] [rbp+8h] BYREF

  ThrdAddr = this;
  v1 = 0;
  if ( !(unsigned int)IISInitializeCriticalSection(&stru_18007A188) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
  }
  v3 = 0;
  if ( v1 >= 0 )
    v3 = 2;
  dword_18007A180 = v3 | dword_18007A180 & 0xFFFFFFFD;
  if ( v1 >= 0 )
  {
    qword_18007A1B0 = CreateEventA(0, 0, 0, 0);
    if ( !qword_18007A1B0 )
      v1 = -2147024882;
  }
  if ( v1 >= 0 )
  {
    pHandles = CreateEventA(0, 0, 0, 0);
    if ( !pHandles )
      v1 = -2147024882;
  }
  LODWORD(ThrdAddr) = 0;
  v4 = (void *)_beginthreadex(0, 0, CMTACallbackThread::Thread, &dword_18007A180, 0, (unsigned int *)&ThrdAddr);
  if ( v4 == (void *)0xFFFFFFFFLL || !v4 )
    v1 = -2147024882;
  else
    hHandle = v4;
  if ( v1 >= 0 )
    dword_18007A180 |= 1u;
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001c880  mov     [rsp+arg_8], rbx
0x18001c885  mov     [rsp+arg_0], rcx
0x18001c88a  push    rdi
0x18001c88b  sub     rsp, 40h
0x18001c88f  xor     ebx, ebx
0x18001c891  lea     rcx, stru_18007A188
0x18001c898  call    cs:__imp_IISInitializeCriticalSection
0x18001c89e  test    eax, eax
0x18001c8a0  jnz     short loc_18001C8BB
0x18001c8a2  call    cs:__imp_GetLastError
0x18001c8a8  mov     ebx, eax
0x18001c8aa  test    eax, eax
0x18001c8ac  jle     short loc_18001C8B7
0x18001c8ae  movzx   ebx, ax
0x18001c8b1  or      ebx, 80070000h
0x18001c8b7  mov     [rsp+48h+var_18], ebx
0x18001c8bb  jmp     short loc_18001C8C6
0x18001c8bd  mov     ebx, 8000FFFFh
0x18001c8c2  mov     [rsp+48h+var_18], ebx
0x18001c8c6  xor     ecx, ecx
0x18001c8c8  lea     eax, [rcx+2]
0x18001c8cb  test    ebx, ebx
0x18001c8cd  cmovns  ecx, eax
0x18001c8d0  mov     eax, cs:dword_18007A180
0x18001c8d6  and     eax, 0FFFFFFFDh
0x18001c8d9  or      eax, ecx
0x18001c8db  mov     cs:dword_18007A180, eax
0x18001c8e1  test    ebx, ebx
0x18001c8e3  js      loc_18002FBFE
0x18001c8e9  xor     r9d, r9d; lpName
0x18001c8ec  xor     r8d, r8d; bInitialState
0x18001c8ef  xor     edx, edx; bManualReset
0x18001c8f1  xor     ecx, ecx; lpEventAttributes
0x18001c8f3  call    cs:__imp_CreateEventA
0x18001c8f9  mov     cs:qword_18007A1B0, rax
0x18001c900  mov     edi, 8007000Eh
0x18001c905  test    rax, rax
0x18001c908  cmovz   ebx, edi
0x18001c90b  test    ebx, ebx
0x18001c90d  js      short loc_18001C92C
0x18001c90f  xor     r9d, r9d; lpName
0x18001c912  xor     r8d, r8d; bInitialState
0x18001c915  xor     edx, edx; bManualReset
0x18001c917  xor     ecx, ecx; lpEventAttributes
0x18001c919  call    cs:__imp_CreateEventA
0x18001c91f  mov     cs:pHandles, rax
0x18001c926  test    rax, rax
0x18001c929  cmovz   ebx, edi
0x18001c92c  mov     dword ptr [rsp+48h+arg_0], 0
0x18001c934  lea     rax, [rsp+48h+arg_0]
0x18001c939  mov     [rsp+48h+ThrdAddr], rax; ThrdAddr
0x18001c93e  mov     [rsp+48h+InitFlag], 0; InitFlag
0x18001c946  lea     r9, dword_18007A180; ArgList
0x18001c94d  lea     r8, ?Thread@CMTACallbackThread@@CAIPEAX@Z; StartAddress
0x18001c954  xor     edx, edx; StackSize
0x18001c956  xor     ecx, ecx; Security
0x18001c958  call    cs:__imp__beginthreadex
0x18001c95e  mov     ecx, 0FFFFFFFFh
0x18001c963  cmp     rax, rcx
0x18001c966  jz      short loc_18001C98C
0x18001c968  test    rax, rax
0x18001c96b  jz      short loc_18001C98C
0x18001c96d  mov     cs:hHandle, rax
0x18001c974  test    ebx, ebx
0x18001c976  js      short loc_18001C97F
0x18001c978  or      cs:dword_18007A180, 1
0x18001c97f  mov     eax, ebx
0x18001c981  mov     rbx, [rsp+48h+arg_8]
0x18001c986  add     rsp, 40h
0x18001c98a  pop     rdi
0x18001c98b  retn
0x18001c98c  mov     ebx, edi
0x18001c98e  jmp     short loc_18001C974
0x18002fbfe  mov     edi, 8007000Eh
0x18002fc03  jmp     loc_18001C90B
```
