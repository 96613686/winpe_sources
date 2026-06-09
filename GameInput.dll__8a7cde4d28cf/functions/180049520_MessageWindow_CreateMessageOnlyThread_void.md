# MessageWindow::CreateMessageOnlyThread(void)

- ea: `0x180049520`
- end: `0x1800495de`
- name: `?CreateMessageOnlyThread@MessageWindow@@AEAAJXZ`
- size: `190`
- prototype: `__int64 __fastcall(MessageWindow *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800495e4`
- `0x18004c42c`

## callees

- `0x180001304`
- `0x180049520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180049548`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180049548`

## pseudocode

```c
__int64 __fastcall MessageWindow::CreateMessageOnlyThread(MessageWindow *this)
{
  HANDLE Thread; // rax
  int v3; // r8d
  int v4; // r9d
  int v6; // [rsp+50h] [rbp+8h] BYREF
  int v7; // [rsp+58h] [rbp+10h] BYREF
  const char *v8; // [rsp+60h] [rbp+18h] BYREF

  Thread = CreateThread(0, 0, MessageWindow::WorkerThreadProcThunk, this, 0, 0);
  *(_QWORD *)this = Thread;
  if ( Thread )
    return 0;
  if ( (unsigned int)dword_180069000 > 2
    && (qword_180069010 & 0x400) != 0
    && (qword_180069018 & 0x400) == qword_180069018 )
  {
    v6 = -2147024882;
    v8 = "onecore\\xbox\\gameinput\\router\\MessageWindow.cpp";
    v7 = 74;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&v8,
      (unsigned int)&dword_180064504,
      v3,
      v4,
      (__int64)&v8,
      (__int64)&v7,
      (__int64)&v6);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180049520  push    rbx
0x180049522  sub     rsp, 40h
0x180049526  mov     rbx, rcx
0x180049529  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x180049532  mov     r9, rcx; lpParameter
0x180049535  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x18004953d  xor     ecx, ecx; lpThreadAttributes
0x18004953f  lea     r8, ?WorkerThreadProcThunk@MessageWindow@@CAKPEAX@Z; lpStartAddress
0x180049546  xor     edx, edx; dwStackSize
0x180049548  call    cs:__imp_CreateThread
0x18004954f  nop     dword ptr [rax+rax+00h]
0x180049554  mov     [rbx], rax
0x180049557  test    rax, rax
0x18004955a  jnz     short loc_1800495D5
0x18004955c  mov     eax, cs:dword_180069000
0x180049562  mov     ebx, 8007000Eh
0x180049567  cmp     eax, 2
0x18004956a  jbe     short loc_1800495D1
0x18004956c  mov     rcx, cs:qword_180069018
0x180049573  mov     edx, 400h
0x180049578  mov     rax, cs:qword_180069010
0x18004957f  test    rdx, rax
0x180049582  jz      short loc_1800495D1
0x180049584  mov     rax, rcx
0x180049587  and     rax, rdx
0x18004958a  cmp     rax, rcx
0x18004958d  jnz     short loc_1800495D1
0x18004958f  lea     rcx, aOnecoreXboxGam_40; "onecore\\xbox\\gameinput\\router\\Messa"...
0x180049596  mov     [rsp+48h+arg_0], ebx
0x18004959a  mov     [rsp+48h+arg_10], rcx
0x18004959f  lea     rdx, dword_180064504
0x1800495a6  lea     rcx, [rsp+48h+arg_0]
0x1800495ab  mov     [rsp+48h+arg_8], 4Ah ; 'J'
0x1800495b3  mov     [rsp+48h+var_18], rcx
0x1800495b8  lea     rcx, [rsp+48h+arg_8]
0x1800495bd  mov     [rsp+48h+lpThreadId], rcx
0x1800495c2  lea     rcx, [rsp+48h+arg_10]
0x1800495c7  mov     qword ptr [rsp+48h+dwCreationFlags], rcx
0x1800495cc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800495d1  mov     eax, ebx
0x1800495d3  jmp     short loc_1800495D7
0x1800495d5  xor     eax, eax
0x1800495d7  add     rsp, 40h
0x1800495db  pop     rbx
0x1800495dc  retn
```
