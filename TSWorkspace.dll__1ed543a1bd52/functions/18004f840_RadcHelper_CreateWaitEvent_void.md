# RadcHelper::CreateWaitEvent(void)

- ea: `0x18004f840`
- end: `0x18004f924`
- name: `?CreateWaitEvent@RadcHelper@@AEAAJXZ`
- size: `228`
- prototype: `__int64 __fastcall(RadcHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800504c4`

## callees

- `0x18000b1d8`
- `0x18000ec94`
- `0x18004f840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004f8a7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004f8a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f861`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f861`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f8b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f8b1`

## pseudocode

```c
__int64 __fastcall RadcHelper::CreateWaitEvent(RadcHelper *this)
{
  signed int LastError; // ebx
  void *v3; // rcx
  HANDLE EventW; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  bool v7; // sf

  LastError = 0;
  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    if ( ResetEvent(v3) )
      return (unsigned int)LastError;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 38;
    goto LABEL_12;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 4) = EventW;
  if ( EventW )
    return (unsigned int)LastError;
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 37;
LABEL_12:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      WPP_b74b712416693693af262b781bb28dc7_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
  }
LABEL_13:
  v7 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = LastError < 0;
  }
  if ( !v7 )
    return (unsigned int)-2147467259;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18004f840  mov     [rsp+arg_0], rbx
0x18004f845  push    rdi
0x18004f846  sub     rsp, 30h
0x18004f84a  mov     rdi, rcx
0x18004f84d  xor     ebx, ebx
0x18004f84f  mov     rcx, [rcx+20h]; hEvent
0x18004f853  test    rcx, rcx
0x18004f856  jnz     short loc_18004F8A7
0x18004f858  xor     r9d, r9d; lpName
0x18004f85b  lea     edx, [rbx+1]; bManualReset
0x18004f85e  xor     r8d, r8d; bInitialState
0x18004f861  call    cs:__imp_CreateEventW
0x18004f867  mov     [rdi+20h], rax
0x18004f86b  test    rax, rax
0x18004f86e  jnz     loc_18004F917
0x18004f874  call    cs:__imp_GetLastError
0x18004f87a  mov     ebx, eax
0x18004f87c  mov     rax, cs:WPP_GLOBAL_Control
0x18004f883  lea     rcx, WPP_GLOBAL_Control
0x18004f88a  cmp     rax, rcx
0x18004f88d  jz      short loc_18004F900
0x18004f88f  test    byte ptr [rax+1Ch], 8
0x18004f893  jz      short loc_18004F900
0x18004f895  cmp     byte ptr [rax+19h], 2
0x18004f899  jb      short loc_18004F900
0x18004f89b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004f8a0  mov     edx, 25h ; '%'
0x18004f8a5  jmp     short loc_18004F8E2
0x18004f8a7  call    cs:__imp_ResetEvent
0x18004f8ad  test    eax, eax
0x18004f8af  jnz     short loc_18004F917
0x18004f8b1  call    cs:__imp_GetLastError
0x18004f8b7  mov     ebx, eax
0x18004f8b9  mov     rax, cs:WPP_GLOBAL_Control
0x18004f8c0  lea     rcx, WPP_GLOBAL_Control
0x18004f8c7  cmp     rax, rcx
0x18004f8ca  jz      short loc_18004F900
0x18004f8cc  test    byte ptr [rax+1Ch], 8
0x18004f8d0  jz      short loc_18004F900
0x18004f8d2  cmp     byte ptr [rax+19h], 2
0x18004f8d6  jb      short loc_18004F900
0x18004f8d8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004f8dd  mov     edx, 26h ; '&'
0x18004f8e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f8e9  lea     r8, WPP_b74b712416693693af262b781bb28dc7_Traceguids
0x18004f8f0  mov     r9d, eax
0x18004f8f3  mov     [rsp+38h+var_18], ebx
0x18004f8f7  mov     rcx, [rcx+10h]
0x18004f8fb  call    WPP_SF_Dd
0x18004f900  test    ebx, ebx
0x18004f902  jle     short loc_18004F90F
0x18004f904  movzx   ebx, bx
0x18004f907  or      ebx, 80070000h
0x18004f90d  test    ebx, ebx
0x18004f90f  mov     eax, 80004005h
0x18004f914  cmovns  ebx, eax
0x18004f917  mov     eax, ebx
0x18004f919  mov     rbx, [rsp+38h+arg_0]
0x18004f91e  add     rsp, 30h
0x18004f922  pop     rdi
0x18004f923  retn
```
