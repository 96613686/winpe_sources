# WinSAT::OpMem1Thread::DoOperationThreadEntryPoint(void *)

- ea: `0x14005c150`
- end: `0x14005c1e8`
- name: `?DoOperationThreadEntryPoint@OpMem1Thread@WinSAT@@SAIPEAX@Z`
- size: `152`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140011f58`
- `0x14003ec14`
- `0x14004fe00`
- `0x140059ef4`
- `0x14005c150`

## import_xrefs

- `KERNEL32!GetThreadPriority` at `0x14005c162`
- `KERNEL32!GetThreadPriority` at `0x14005c162`
- `KERNEL32!GetCurrentThread` at `0x14005c159`
- `KERNEL32!GetCurrentThread` at `0x14005c159`
- `KERNEL32!SetLastError` at `0x14005c18f`
- `KERNEL32!SetLastError` at `0x14005c1d5`
- `KERNEL32!SetLastError` at `0x14005c18f`
- `KERNEL32!SetLastError` at `0x14005c1d5`

## string_xrefs

- `0x14005c168`: `DoOperationThreadEntryPoint Launched with priority %d`

## pseudocode

```c
__int64 __fastcall WinSAT::OpMem1Thread::DoOperationThreadEntryPoint(WinSAT::OpMem1Thread *a1)
{
  HANDLE CurrentThread; // rax
  int ThreadPriority; // eax
  unsigned __int16 v4; // r9
  const unsigned __int16 *v6; // rax

  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  Log_Text_F(
    "base\\winsat\\memory\\memat.cpp",
    1231,
    "DoOperationThreadEntryPoint Launched with priority %d",
    ThreadPriority);
  if ( a1 )
  {
    if ( *((_BYTE *)a1 + 116) )
    {
      v6 = mlib::MUIStr_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x4DD, 635, v4);
      WinSAT::OpStatus::SetResult((char *)a1 + 400, 5, v6, 0);
      SetLastError(5u);
    }
    return WinSAT::OpMem1Thread::DoOperation(a1);
  }
  else
  {
    SetLastError(0x57u);
    return 87;
  }
}

```

## disassembly

```asm
0x14005c150  push    rbx
0x14005c152  sub     rsp, 20h
0x14005c156  mov     rbx, rcx
0x14005c159  call    cs:__imp_GetCurrentThread
0x14005c15f  mov     rcx, rax; hThread
0x14005c162  call    cs:__imp_GetThreadPriority
0x14005c168  lea     r8, aDooperationthr; "DoOperationThreadEntryPoint Launched wi"...
0x14005c16f  mov     edx, 4CFh
0x14005c174  mov     r9d, eax
0x14005c177  lea     rcx, aBaseWinsatMemo; "base\\winsat\\memory\\memat.cpp"
0x14005c17e  call    Log_Text_F
0x14005c183  test    rbx, rbx
0x14005c186  jnz     short loc_14005C19D
0x14005c188  mov     ebx, 57h ; 'W'
0x14005c18d  mov     ecx, ebx; dwErrCode
0x14005c18f  call    cs:__imp_SetLastError
0x14005c195  mov     eax, ebx
0x14005c197  add     rsp, 20h
0x14005c19b  pop     rbx
0x14005c19c  retn
0x14005c19d  cmp     byte ptr [rbx+74h], 0
0x14005c1a1  jz      short loc_14005C1DB
0x14005c1a3  mov     edx, 4DDh; char *
0x14005c1a8  lea     rcx, aBaseWinsatMemo; "base\\winsat\\memory\\memat.cpp"
0x14005c1af  mov     r8d, 27Bh; int
0x14005c1b5  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14005c1ba  xor     r9d, r9d
0x14005c1bd  lea     rcx, [rbx+190h]
0x14005c1c4  mov     r8, rax
0x14005c1c7  lea     edx, [r9+5]
0x14005c1cb  call    ?SetResult@OpStatus@WinSAT@@QEAAXW4OpStatusCode@2@PEBGK@Z; WinSAT::OpStatus::SetResult(WinSAT::OpStatusCode,ushort const *,ulong)
0x14005c1d0  mov     ecx, 5; dwErrCode
0x14005c1d5  call    cs:__imp_SetLastError
0x14005c1db  mov     rcx, rbx; this
0x14005c1de  add     rsp, 20h
0x14005c1e2  pop     rbx
0x14005c1e3  jmp     ?DoOperation@OpMem1Thread@WinSAT@@QEAAKXZ; WinSAT::OpMem1Thread::DoOperation(void)
```
