# _tlgEnableCallback

- ea: `0x1400010c0`
- end: `0x140001136`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400010c0`
- `0x140012010`

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
0x1400010c0  sub     rsp, 48h
0x1400010c4  mov     r11, rcx
0x1400010c7  mov     rcx, [rsp+48h+CallbackContext]
0x1400010cf  test    rcx, rcx
0x1400010d2  jz      short loc_140001131
0x1400010d4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1400010d9  mov     eax, edx
0x1400010db  test    edx, edx
0x1400010dd  jz      short loc_140001102
0x1400010df  cmp     eax, 1
0x1400010e2  jnz     short loc_140001108
0x1400010e4  test    r8b, r8b
0x1400010e7  jz      short loc_1400010F1
0x1400010e9  movzx   eax, r8b
0x1400010ed  inc     eax
0x1400010ef  jmp     short loc_1400010F6
0x1400010f1  mov     eax, 100h
0x1400010f6  mov     [rcx], eax
0x1400010f8  mov     [rcx+10h], r9
0x1400010fc  mov     [rcx+18h], r10
0x140001100  jmp     short loc_140001108
0x140001102  mov     dword ptr [rcx], 0
0x140001108  mov     rax, [rcx+28h]
0x14000110c  test    rax, rax
0x14000110f  jz      short loc_140001131
0x140001111  mov     rcx, [rcx+30h]
0x140001115  mov     [rsp+48h+var_18], rcx
0x14000111a  mov     rcx, [rsp+48h+FilterData]
0x14000111f  mov     [rsp+48h+var_20], rcx
0x140001124  mov     rcx, r11
0x140001127  mov     [rsp+48h+var_28], r10
0x14000112c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001131  add     rsp, 48h
0x140001135  retn
```
