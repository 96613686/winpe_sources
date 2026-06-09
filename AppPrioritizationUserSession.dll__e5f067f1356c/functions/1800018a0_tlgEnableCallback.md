# _tlgEnableCallback

- ea: `0x1800018a0`
- end: `0x180001916`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800018a0`
- `0x18000d010`

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
0x1800018a0  sub     rsp, 48h
0x1800018a4  mov     r11, rcx
0x1800018a7  mov     rcx, [rsp+48h+CallbackContext]
0x1800018af  test    rcx, rcx
0x1800018b2  jz      short loc_180001911
0x1800018b4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1800018b9  mov     eax, edx
0x1800018bb  test    edx, edx
0x1800018bd  jz      short loc_1800018E2
0x1800018bf  cmp     eax, 1
0x1800018c2  jnz     short loc_1800018E8
0x1800018c4  test    r8b, r8b
0x1800018c7  jz      short loc_1800018D1
0x1800018c9  movzx   eax, r8b
0x1800018cd  inc     eax
0x1800018cf  jmp     short loc_1800018D6
0x1800018d1  mov     eax, 100h
0x1800018d6  mov     [rcx], eax
0x1800018d8  mov     [rcx+10h], r9
0x1800018dc  mov     [rcx+18h], r10
0x1800018e0  jmp     short loc_1800018E8
0x1800018e2  mov     dword ptr [rcx], 0
0x1800018e8  mov     rax, [rcx+28h]
0x1800018ec  test    rax, rax
0x1800018ef  jz      short loc_180001911
0x1800018f1  mov     rcx, [rcx+30h]
0x1800018f5  mov     [rsp+48h+var_18], rcx
0x1800018fa  mov     rcx, [rsp+48h+FilterData]
0x1800018ff  mov     [rsp+48h+var_20], rcx
0x180001904  mov     rcx, r11
0x180001907  mov     [rsp+48h+var_28], r10
0x18000190c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001911  add     rsp, 48h
0x180001915  retn
```
