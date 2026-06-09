# InitializeTimers

- ea: `0x180008930`
- end: `0x180008a66`
- name: `InitializeTimers`
- size: `310`
- prototype: `DWORD __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180008930`
- `0x180008ff0`
- `0x180009130`
- `0x18000b6f4`
- `0x18000b734`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089c0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800089b2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800089b2`

## pseudocode

```c
DWORD __fastcall InitializeTimers(_QWORD *a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // esi
  HANDLE TimerQueue; // rdi
  DWORD result; // eax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v3 = 0;
    TimerQueue = CreateTimerQueue();
    if ( TimerQueue || (result = GetLastError(), (v3 = result) == 0) )
    {
      *a1 = TimerQueue;
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v3;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_17;
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, TimerQueue);
    }
    else
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return result;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_17;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, result);
    }
LABEL_16:
    v2 = (PVOID *)WPP_GLOBAL_Control;
LABEL_17:
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      WPP_SF_L(v2[2], 14, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, v3);
    return v3;
  }
  v3 = 87;
  if ( v2 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v2 + 28) & 4) == 0 )
      goto LABEL_17;
    WPP_SF_(v2[2], 11, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
    goto LABEL_16;
  }
  return v3;
}

```

## disassembly

```asm
0x180008930  mov     [rsp+arg_10], rbx
0x180008935  push    rbp
0x180008936  sub     rsp, 20h
0x18000893a  mov     rbx, rcx
0x18000893d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008944  lea     rbp, WPP_GLOBAL_Control
0x18000894b  cmp     rcx, rbp
0x18000894e  jz      short loc_180008972
0x180008950  test    byte ptr [rcx+1Ch], 8
0x180008954  jz      short loc_180008972
0x180008956  mov     rcx, [rcx+10h]
0x18000895a  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x180008961  mov     edx, 0Ah
0x180008966  call    WPP_SF_
0x18000896b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008972  mov     [rsp+28h+arg_0], rsi
0x180008977  mov     [rsp+28h+arg_8], rdi
0x18000897c  test    rbx, rbx
0x18000897f  jnz     short loc_1800089B0
0x180008981  mov     esi, 57h ; 'W'
0x180008986  cmp     rcx, rbp
0x180008989  jz      loc_180008A4F
0x18000898f  test    byte ptr [rcx+1Ch], 4
0x180008993  jz      loc_180008A2C
0x180008999  mov     rcx, [rcx+10h]
0x18000899d  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x1800089a4  mov     edx, 0Bh
0x1800089a9  call    WPP_SF_
0x1800089ae  jmp     short loc_180008A25
0x1800089b0  xor     esi, esi
0x1800089b2  call    cs:__imp_CreateTimerQueue
0x1800089b8  mov     rdi, rax
0x1800089bb  test    rax, rax
0x1800089be  jnz     short loc_1800089F8
0x1800089c0  call    cs:__imp_GetLastError
0x1800089c6  mov     esi, eax
0x1800089c8  test    eax, eax
0x1800089ca  jz      short loc_1800089F8
0x1800089cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089d3  cmp     rcx, rbp
0x1800089d6  jz      short loc_180008A51
0x1800089d8  test    byte ptr [rcx+1Ch], 4
0x1800089dc  jz      short loc_180008A2C
0x1800089de  mov     rcx, [rcx+10h]
0x1800089e2  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x1800089e9  mov     edx, 0Ch
0x1800089ee  mov     r9d, eax
0x1800089f1  call    WPP_SF_d
0x1800089f6  jmp     short loc_180008A25
0x1800089f8  mov     [rbx], rdi
0x1800089fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a02  cmp     rcx, rbp
0x180008a05  jz      short loc_180008A4F
0x180008a07  test    byte ptr [rcx+1Ch], 2
0x180008a0b  jz      short loc_180008A2C
0x180008a0d  mov     rcx, [rcx+10h]
0x180008a11  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x180008a18  mov     edx, 0Dh
0x180008a1d  mov     r9, rdi
0x180008a20  call    WPP_SF_q
0x180008a25  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a2c  cmp     rcx, rbp
0x180008a2f  jz      short loc_180008A4F
0x180008a31  test    byte ptr [rcx+1Ch], 8
0x180008a35  jz      short loc_180008A4F
0x180008a37  mov     rcx, [rcx+10h]
0x180008a3b  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x180008a42  mov     edx, 0Eh
0x180008a47  mov     r9d, esi
0x180008a4a  call    WPP_SF_L
0x180008a4f  mov     eax, esi
0x180008a51  mov     rdi, [rsp+28h+arg_8]
0x180008a56  mov     rsi, [rsp+28h+arg_0]
0x180008a5b  mov     rbx, [rsp+28h+arg_10]
0x180008a60  add     rsp, 20h
0x180008a64  pop     rbp
0x180008a65  retn
```
