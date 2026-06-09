# _tlgEnableCallback

- ea: `0x1800010e0`
- end: `0x180001156`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800010e0`
- `0x18000c010`

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
  int v7; // eax
  void (__fastcall *v8)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD); // rax

  if ( CallbackContext )
  {
    if ( (_DWORD)IsEnabled )
    {
      if ( (_DWORD)IsEnabled == 1 )
      {
        if ( (_BYTE)Level )
          v7 = (unsigned __int8)Level + 1;
        else
          v7 = 256;
        *(_DWORD *)CallbackContext = v7;
        CallbackContext[2] = MatchAnyKeyword;
        CallbackContext[3] = MatchAllKeyword;
      }
    }
    else
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
0x1800010e0  sub     rsp, 48h
0x1800010e4  mov     r11, rcx
0x1800010e7  mov     rcx, [rsp+48h+CallbackContext]
0x1800010ef  test    rcx, rcx
0x1800010f2  jz      short loc_180001151
0x1800010f4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1800010f9  mov     eax, edx
0x1800010fb  test    edx, edx
0x1800010fd  jz      short loc_180001122
0x1800010ff  cmp     eax, 1
0x180001102  jnz     short loc_180001128
0x180001104  test    r8b, r8b
0x180001107  jz      short loc_180001111
0x180001109  movzx   eax, r8b
0x18000110d  inc     eax
0x18000110f  jmp     short loc_180001116
0x180001111  mov     eax, 100h
0x180001116  mov     [rcx], eax
0x180001118  mov     [rcx+10h], r9
0x18000111c  mov     [rcx+18h], r10
0x180001120  jmp     short loc_180001128
0x180001122  mov     dword ptr [rcx], 0
0x180001128  mov     rax, [rcx+28h]
0x18000112c  test    rax, rax
0x18000112f  jz      short loc_180001151
0x180001131  mov     rcx, [rcx+30h]
0x180001135  mov     [rsp+48h+var_18], rcx
0x18000113a  mov     rcx, [rsp+48h+FilterData]
0x18000113f  mov     [rsp+48h+var_20], rcx
0x180001144  mov     rcx, r11
0x180001147  mov     [rsp+48h+var_28], r10
0x18000114c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001151  add     rsp, 48h
0x180001155  retn
```
