# DeInitializeTimers

- ea: `0x18000c0b0`
- end: `0x18000c1be`
- name: `DeInitializeTimers`
- size: `270`
- prototype: `__int64 __fastcall(HANDLE TimerQueue)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180008ff0`
- `0x180009130`
- `0x18000b6f4`
- `0x18000b734`
- `0x18000c0b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c131`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18000c127`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18000c127`

## pseudocode

```c
__int64 __fastcall DeInitializeTimers(HANDLE TimerQueue)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  DWORD LastError; // eax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( TimerQueue )
  {
    if ( DeleteTimerQueueEx(TimerQueue, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError )
      {
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v3;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_18;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, LastError);
        goto LABEL_17;
      }
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_18;
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, TimerQueue);
    goto LABEL_17;
  }
  v3 = 87;
  if ( v2 == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)v2 + 28) & 4) != 0 )
  {
    WPP_SF_(v2[2], 16, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
LABEL_17:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_18:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_L(v2[2], 19, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18000c0b0  push    rbx
0x18000c0b2  push    rbp
0x18000c0b3  push    rsi
0x18000c0b4  push    rdi
0x18000c0b5  sub     rsp, 28h
0x18000c0b9  mov     rdi, rcx
0x18000c0bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0c3  lea     rsi, WPP_GLOBAL_Control
0x18000c0ca  lea     rbp, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x18000c0d1  cmp     rcx, rsi
0x18000c0d4  jz      short loc_18000C0F4
0x18000c0d6  test    byte ptr [rcx+1Ch], 8
0x18000c0da  jz      short loc_18000C0F4
0x18000c0dc  mov     rcx, [rcx+10h]
0x18000c0e0  mov     edx, 0Fh
0x18000c0e5  mov     r8, rbp
0x18000c0e8  call    WPP_SF_
0x18000c0ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0f4  test    rdi, rdi
0x18000c0f7  jnz     short loc_18000C120
0x18000c0f9  lea     ebx, [rdi+57h]
0x18000c0fc  cmp     rcx, rsi
0x18000c0ff  jz      loc_18000C1B3
0x18000c105  test    byte ptr [rcx+1Ch], 4
0x18000c109  jz      loc_18000C194
0x18000c10f  mov     rcx, [rcx+10h]
0x18000c113  lea     edx, [rdi+10h]
0x18000c116  mov     r8, rbp
0x18000c119  call    WPP_SF_
0x18000c11e  jmp     short loc_18000C18D
0x18000c120  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000c124  mov     rcx, rdi; TimerQueue
0x18000c127  call    cs:__imp_DeleteTimerQueueEx
0x18000c12d  test    eax, eax
0x18000c12f  jnz     short loc_18000C165
0x18000c131  call    cs:__imp_GetLastError
0x18000c137  mov     ebx, eax
0x18000c139  test    eax, eax
0x18000c13b  jz      short loc_18000C167
0x18000c13d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c144  cmp     rcx, rsi
0x18000c147  jz      short loc_18000C1B3
0x18000c149  test    byte ptr [rcx+1Ch], 4
0x18000c14d  jz      short loc_18000C194
0x18000c14f  mov     rcx, [rcx+10h]
0x18000c153  mov     edx, 11h
0x18000c158  mov     r9d, eax
0x18000c15b  mov     r8, rbp
0x18000c15e  call    WPP_SF_d
0x18000c163  jmp     short loc_18000C18D
0x18000c165  xor     ebx, ebx
0x18000c167  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c16e  cmp     rcx, rsi
0x18000c171  jz      short loc_18000C1B3
0x18000c173  test    byte ptr [rcx+1Ch], 2
0x18000c177  jz      short loc_18000C194
0x18000c179  mov     rcx, [rcx+10h]
0x18000c17d  mov     edx, 12h
0x18000c182  mov     r9, rdi
0x18000c185  mov     r8, rbp
0x18000c188  call    WPP_SF_q
0x18000c18d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c194  cmp     rcx, rsi
0x18000c197  jz      short loc_18000C1B3
0x18000c199  test    byte ptr [rcx+1Ch], 8
0x18000c19d  jz      short loc_18000C1B3
0x18000c19f  mov     rcx, [rcx+10h]
0x18000c1a3  mov     edx, 13h
0x18000c1a8  mov     r9d, ebx
0x18000c1ab  mov     r8, rbp
0x18000c1ae  call    WPP_SF_L
0x18000c1b3  mov     eax, ebx
0x18000c1b5  add     rsp, 28h
0x18000c1b9  pop     rdi
0x18000c1ba  pop     rsi
0x18000c1bb  pop     rbp
0x18000c1bc  pop     rbx
0x18000c1bd  retn
```
