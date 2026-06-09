# _tlgEnableCallback

- ea: `0x1800015c0`
- end: `0x180001636`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800015c0`
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
0x1800015c0  sub     rsp, 48h
0x1800015c4  mov     r11, rcx
0x1800015c7  mov     rcx, [rsp+48h+CallbackContext]
0x1800015cf  test    rcx, rcx
0x1800015d2  jz      short loc_180001631
0x1800015d4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1800015d9  mov     eax, edx
0x1800015db  test    edx, edx
0x1800015dd  jz      short loc_180001602
0x1800015df  cmp     eax, 1
0x1800015e2  jnz     short loc_180001608
0x1800015e4  test    r8b, r8b
0x1800015e7  jz      short loc_1800015F1
0x1800015e9  movzx   eax, r8b
0x1800015ed  inc     eax
0x1800015ef  jmp     short loc_1800015F6
0x1800015f1  mov     eax, 100h
0x1800015f6  mov     [rcx], eax
0x1800015f8  mov     [rcx+10h], r9
0x1800015fc  mov     [rcx+18h], r10
0x180001600  jmp     short loc_180001608
0x180001602  mov     dword ptr [rcx], 0
0x180001608  mov     rax, [rcx+28h]
0x18000160c  test    rax, rax
0x18000160f  jz      short loc_180001631
0x180001611  mov     rcx, [rcx+30h]
0x180001615  mov     [rsp+48h+var_18], rcx
0x18000161a  mov     rcx, [rsp+48h+FilterData]
0x18000161f  mov     [rsp+48h+var_20], rcx
0x180001624  mov     rcx, r11
0x180001627  mov     [rsp+48h+var_28], r10
0x18000162c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001631  add     rsp, 48h
0x180001635  retn
```
