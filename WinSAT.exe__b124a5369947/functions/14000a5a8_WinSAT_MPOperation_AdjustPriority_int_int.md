# WinSAT::MPOperation::AdjustPriority(int,int)

- ea: `0x14000a5a8`
- end: `0x14000a65d`
- name: `?AdjustPriority@MPOperation@WinSAT@@AEAA_NHH@Z`
- size: `181`
- prototype: `bool __fastcall(WinSAT::MPOperation *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400120e0`

## callees

- `0x140004348`
- `0x14000a5a8`
- `0x140017af0`
- `0x1400530a8`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x14000a62a`
- `KERNEL32!GetCurrentThread` at `0x14000a62a`
- `KERNEL32!GetLastError` at `0x14000a5de`
- `KERNEL32!GetLastError` at `0x14000a5de`
- `KERNEL32!SetThreadPriority` at `0x14000a638`
- `KERNEL32!SetThreadPriority` at `0x14000a638`
- `KERNEL32!GetCurrentProcess` at `0x14000a5c6`
- `KERNEL32!GetCurrentProcess` at `0x14000a5c6`
- `KERNEL32!SetPriorityClass` at `0x14000a5d4`
- `KERNEL32!SetPriorityClass` at `0x14000a5d4`

## pseudocode

```c
char __fastcall WinSAT::MPOperation::AdjustPriority(WinSAT::MPOperation *this)
{
  HANDLE CurrentProcess; // rax
  __int64 v3; // rax
  HANDLE CurrentThread; // rax
  _QWORD Buffer[64]; // [rsp+20h] [rbp-228h] BYREF
  DWORD LastError; // [rsp+220h] [rbp-28h]
  char v8; // [rsp+224h] [rbp-24h]
  __int64 v9; // [rsp+228h] [rbp-20h]

  CurrentProcess = GetCurrentProcess();
  if ( SetPriorityClass(CurrentProcess, 0x80u) )
  {
    CurrentThread = GetCurrentThread();
    if ( SetThreadPriority(CurrentThread, 2) )
      return 0;
  }
  v8 = 1;
  LastError = GetLastError();
  v9 = 0;
  mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*((_QWORD *)this + 3) + 240LL, Buffer);
  std::endl(v3);
  return 1;
}

```

## disassembly

```asm
0x14000a5a8  push    rbx
0x14000a5aa  sub     rsp, 240h
0x14000a5b1  mov     rax, cs:__security_cookie
0x14000a5b8  xor     rax, rsp
0x14000a5bb  mov     [rsp+248h+var_18], rax
0x14000a5c3  mov     rbx, rcx
0x14000a5c6  call    cs:__imp_GetCurrentProcess
0x14000a5cc  mov     rcx, rax; hProcess
0x14000a5cf  mov     edx, 80h; dwPriorityClass
0x14000a5d4  call    cs:__imp_SetPriorityClass
0x14000a5da  test    eax, eax
0x14000a5dc  jnz     short loc_14000A62A
0x14000a5de  call    cs:__imp_GetLastError
0x14000a5e4  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x14000a5e9  mov     [rsp+248h+var_24], 1
0x14000a5f1  mov     [rsp+248h+var_28], eax
0x14000a5f8  mov     [rsp+248h+var_20], 0
0x14000a604  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14000a609  mov     rcx, [rbx+18h]
0x14000a60d  lea     rdx, [rsp+248h+Buffer]
0x14000a612  add     rcx, 0F0h
0x14000a619  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000a61e  mov     rcx, rax
0x14000a621  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14000a626  mov     al, 1
0x14000a628  jmp     short loc_14000A644
0x14000a62a  call    cs:__imp_GetCurrentThread
0x14000a630  mov     rcx, rax; hThread
0x14000a633  mov     edx, 2; nPriority
0x14000a638  call    cs:__imp_SetThreadPriority
0x14000a63e  test    eax, eax
0x14000a640  jz      short loc_14000A5DE
0x14000a642  xor     al, al
0x14000a644  mov     rcx, [rsp+248h+var_18]
0x14000a64c  xor     rcx, rsp; StackCookie
0x14000a64f  call    __security_check_cookie
0x14000a654  add     rsp, 240h
0x14000a65b  pop     rbx
0x14000a65c  retn
```
