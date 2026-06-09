# _tlgEnableCallback

- ea: `0x180011580`
- end: `0x180011600`
- name: `_tlgEnableCallback`
- size: `128`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180011580`
- `0x18001c010`

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
0x180011580  sub     rsp, 48h
0x180011584  mov     r11, rcx
0x180011587  mov     rcx, [rsp+48h+CallbackContext]
0x18001158f  test    rcx, rcx
0x180011592  jz      short loc_1800115FB
0x180011594  mov     r10, [rsp+48h+MatchAllKeyword]
0x180011599  mov     eax, edx
0x18001159b  test    edx, edx
0x18001159d  jz      short loc_1800115CC
0x18001159f  cmp     eax, 1
0x1800115a2  jnz     short loc_1800115D2
0x1800115a4  test    r8b, r8b
0x1800115a7  jz      short loc_1800115BB
0x1800115a9  movzx   eax, r8b
0x1800115ad  inc     eax
0x1800115af  mov     [rcx], eax
0x1800115b1  mov     [rcx+10h], r9
0x1800115b5  mov     [rcx+18h], r10
0x1800115b9  jmp     short loc_1800115D2
0x1800115bb  mov     eax, 100h
0x1800115c0  mov     [rcx], eax
0x1800115c2  mov     [rcx+10h], r9
0x1800115c6  mov     [rcx+18h], r10
0x1800115ca  jmp     short loc_1800115D2
0x1800115cc  mov     dword ptr [rcx], 0
0x1800115d2  mov     rax, [rcx+28h]
0x1800115d6  test    rax, rax
0x1800115d9  jz      short loc_1800115FB
0x1800115db  mov     rcx, [rcx+30h]
0x1800115df  mov     [rsp+48h+var_18], rcx
0x1800115e4  mov     rcx, [rsp+48h+FilterData]
0x1800115e9  mov     [rsp+48h+var_20], rcx
0x1800115ee  mov     rcx, r11
0x1800115f1  mov     [rsp+48h+var_28], r10
0x1800115f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115fb  add     rsp, 48h
0x1800115ff  retn
```
