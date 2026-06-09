# EnableCallback

- ea: `0x1800030f0`
- end: `0x180003167`
- name: `EnableCallback`
- size: `119`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800030f0`
- `0x180068420`

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
0x1800030f0  sub     rsp, 48h
0x1800030f4  mov     r11, rcx
0x1800030f7  mov     rcx, [rsp+48h+CallbackContext]
0x1800030ff  test    rcx, rcx
0x180003102  jz      short loc_180003162
0x180003104  mov     r10, [rsp+48h+MatchAllKeyword]
0x180003109  mov     eax, edx
0x18000310b  test    edx, edx
0x18000310d  jz      short loc_180003132
0x18000310f  cmp     eax, 1
0x180003112  jnz     short loc_180003138
0x180003114  test    r8b, r8b
0x180003117  jz      short loc_180003121
0x180003119  movzx   eax, r8b
0x18000311d  inc     eax
0x18000311f  jmp     short loc_180003126
0x180003121  mov     eax, 100h
0x180003126  mov     [rcx], eax
0x180003128  mov     [rcx+10h], r9
0x18000312c  mov     [rcx+18h], r10
0x180003130  jmp     short loc_180003138
0x180003132  mov     dword ptr [rcx], 0
0x180003138  mov     rax, [rcx+28h]
0x18000313c  test    rax, rax
0x18000313f  jz      short loc_180003162
0x180003141  mov     rcx, [rcx+30h]
0x180003145  mov     [rsp+48h+var_18], rcx
0x18000314a  mov     rcx, [rsp+48h+FilterData]
0x18000314f  mov     [rsp+48h+var_20], rcx
0x180003154  mov     rcx, r11
0x180003157  mov     [rsp+48h+var_28], r10
0x18000315c  call    cs:__guard_dispatch_icall_fptr
0x180003162  add     rsp, 48h
0x180003166  retn
```
