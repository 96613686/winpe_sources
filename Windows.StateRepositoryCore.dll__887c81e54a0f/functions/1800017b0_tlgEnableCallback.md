# _tlgEnableCallback

- ea: `0x1800017b0`
- end: `0x180001826`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800017b0`
- `0x180011010`

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
0x1800017b0  sub     rsp, 48h
0x1800017b4  mov     r11, rcx
0x1800017b7  mov     rcx, [rsp+48h+CallbackContext]
0x1800017bf  test    rcx, rcx
0x1800017c2  jz      short loc_180001821
0x1800017c4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1800017c9  mov     eax, edx
0x1800017cb  test    edx, edx
0x1800017cd  jz      short loc_1800017F2
0x1800017cf  cmp     eax, 1
0x1800017d2  jnz     short loc_1800017F8
0x1800017d4  test    r8b, r8b
0x1800017d7  jz      short loc_1800017E1
0x1800017d9  movzx   eax, r8b
0x1800017dd  inc     eax
0x1800017df  jmp     short loc_1800017E6
0x1800017e1  mov     eax, 100h
0x1800017e6  mov     [rcx], eax
0x1800017e8  mov     [rcx+10h], r9
0x1800017ec  mov     [rcx+18h], r10
0x1800017f0  jmp     short loc_1800017F8
0x1800017f2  mov     dword ptr [rcx], 0
0x1800017f8  mov     rax, [rcx+28h]
0x1800017fc  test    rax, rax
0x1800017ff  jz      short loc_180001821
0x180001801  mov     rcx, [rcx+30h]
0x180001805  mov     [rsp+48h+var_18], rcx
0x18000180a  mov     rcx, [rsp+48h+FilterData]
0x18000180f  mov     [rsp+48h+var_20], rcx
0x180001814  mov     rcx, r11
0x180001817  mov     [rsp+48h+var_28], r10
0x18000181c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001821  add     rsp, 48h
0x180001825  retn
```
