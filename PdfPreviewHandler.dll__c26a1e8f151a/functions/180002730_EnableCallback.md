# EnableCallback

- ea: `0x180002730`
- end: `0x1800027a3`
- name: `EnableCallback`
- size: `115`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002730`
- `0x180011c50`

## pseudocode

```c
void __fastcall EnableCallback(
        LPCGUID SourceId,
        __int64 IsEnabled,
        __int64 Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        _QWORD *CallbackContext)
{
  int v7; // eax
  void (__fastcall *v8)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD); // rax

  if ( CallbackContext )
  {
    if ( (_DWORD)IsEnabled == 1 )
    {
      v7 = 256;
      if ( (_BYTE)Level )
        v7 = (unsigned __int8)Level + 1;
      *(_DWORD *)CallbackContext = v7;
      CallbackContext[2] = MatchAnyKeyword;
      CallbackContext[3] = MatchAllKeyword;
    }
    else if ( !(_DWORD)IsEnabled )
    {
      *(_DWORD *)CallbackContext = 0;
    }
    v8 = (void (__fastcall *)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD))CallbackContext[5];
    if ( v8 )
      v8(SourceId, IsEnabled, Level, MatchAnyKeyword, MatchAllKeyword, FilterData, CallbackContext[6]);
  }
}

```

## disassembly

```asm
0x180002730  push    rsi
0x180002731  sub     rsp, 40h
0x180002735  mov     r11, [rsp+48h+CallbackContext]
0x18000273d  test    r11, r11
0x180002740  jz      short loc_18000279D
0x180002742  mov     r10, [rsp+48h+MatchAllKeyword]
0x180002747  cmp     edx, 1
0x18000274a  jz      short loc_180002759
0x18000274c  test    edx, edx
0x18000274e  jnz     short loc_180002775
0x180002750  mov     dword ptr [r11], 0
0x180002757  jmp     short loc_180002775
0x180002759  movzx   eax, r8b
0x18000275d  lea     esi, [rax+1]
0x180002760  test    al, al
0x180002762  mov     eax, 100h
0x180002767  cmovnz  eax, esi
0x18000276a  mov     [r11], eax
0x18000276d  mov     [r11+10h], r9
0x180002771  mov     [r11+18h], r10
0x180002775  mov     rax, [r11+28h]
0x180002779  test    rax, rax
0x18000277c  jz      short loc_18000279D
0x18000277e  mov     rsi, [rsp+48h+FilterData]
0x180002783  mov     r11, [r11+30h]
0x180002787  mov     [rsp+48h+var_18], r11
0x18000278c  mov     [rsp+48h+var_20], rsi
0x180002791  mov     [rsp+48h+var_28], r10
0x180002796  call    cs:__guard_dispatch_icall_fptr
0x18000279c  nop
0x18000279d  add     rsp, 40h
0x1800027a1  pop     rsi
0x1800027a2  retn
```
