# _tlgEnableCallback

- ea: `0x1800010f0`
- end: `0x180001170`
- name: `_tlgEnableCallback`
- size: `128`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800010f0`
- `0x180020010`

## pseudocode

```c
void __fastcall tlgEnableCallback(
        LPCGUID SourceId,
        __int64 IsEnabled,
        __int64 Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        _QWORD *CallbackContext)
{
  void (__fastcall *v7)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD); // rax

  if ( CallbackContext )
  {
    if ( (_DWORD)IsEnabled )
    {
      if ( (_DWORD)IsEnabled == 1 )
      {
        if ( (_BYTE)Level )
          *(_DWORD *)CallbackContext = (unsigned __int8)Level + 1;
        else
          *(_DWORD *)CallbackContext = 256;
        CallbackContext[2] = MatchAnyKeyword;
        CallbackContext[3] = MatchAllKeyword;
      }
    }
    else
    {
      *(_DWORD *)CallbackContext = 0;
    }
    v7 = (void (__fastcall *)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD))CallbackContext[5];
    if ( v7 )
      v7(SourceId, IsEnabled, Level, MatchAnyKeyword, MatchAllKeyword, FilterData, CallbackContext[6]);
  }
}

```

## disassembly

```asm
0x1800010f0  sub     rsp, 48h
0x1800010f4  mov     r11, rcx
0x1800010f7  mov     rcx, [rsp+48h+CallbackContext]
0x1800010ff  test    rcx, rcx
0x180001102  jz      short loc_18000116B
0x180001104  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001109  mov     eax, edx
0x18000110b  test    edx, edx
0x18000110d  jz      short loc_18000113C
0x18000110f  cmp     eax, 1
0x180001112  jnz     short loc_180001142
0x180001114  test    r8b, r8b
0x180001117  jz      short loc_18000112B
0x180001119  movzx   eax, r8b
0x18000111d  inc     eax
0x18000111f  mov     [rcx], eax
0x180001121  mov     [rcx+10h], r9
0x180001125  mov     [rcx+18h], r10
0x180001129  jmp     short loc_180001142
0x18000112b  mov     eax, 100h
0x180001130  mov     [rcx], eax
0x180001132  mov     [rcx+10h], r9
0x180001136  mov     [rcx+18h], r10
0x18000113a  jmp     short loc_180001142
0x18000113c  mov     dword ptr [rcx], 0
0x180001142  mov     rax, [rcx+28h]
0x180001146  test    rax, rax
0x180001149  jz      short loc_18000116B
0x18000114b  mov     rcx, [rcx+30h]
0x18000114f  mov     [rsp+48h+var_18], rcx
0x180001154  mov     rcx, [rsp+48h+FilterData]
0x180001159  mov     [rsp+48h+var_20], rcx
0x18000115e  mov     rcx, r11
0x180001161  mov     [rsp+48h+var_28], r10
0x180001166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000116b  add     rsp, 48h
0x18000116f  retn
```
