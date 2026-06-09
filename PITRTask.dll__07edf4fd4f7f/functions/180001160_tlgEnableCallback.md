# _tlgEnableCallback

- ea: `0x180001160`
- end: `0x1800011d6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001160`
- `0x180012010`

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
0x180001160  sub     rsp, 48h
0x180001164  mov     r11, rcx
0x180001167  mov     rcx, [rsp+48h+CallbackContext]
0x18000116f  test    rcx, rcx
0x180001172  jz      short loc_1800011D1
0x180001174  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001179  mov     eax, edx
0x18000117b  test    edx, edx
0x18000117d  jz      short loc_1800011A2
0x18000117f  cmp     eax, 1
0x180001182  jnz     short loc_1800011A8
0x180001184  test    r8b, r8b
0x180001187  jz      short loc_180001191
0x180001189  movzx   eax, r8b
0x18000118d  inc     eax
0x18000118f  jmp     short loc_180001196
0x180001191  mov     eax, 100h
0x180001196  mov     [rcx], eax
0x180001198  mov     [rcx+10h], r9
0x18000119c  mov     [rcx+18h], r10
0x1800011a0  jmp     short loc_1800011A8
0x1800011a2  mov     dword ptr [rcx], 0
0x1800011a8  mov     rax, [rcx+28h]
0x1800011ac  test    rax, rax
0x1800011af  jz      short loc_1800011D1
0x1800011b1  mov     rcx, [rcx+30h]
0x1800011b5  mov     [rsp+48h+var_18], rcx
0x1800011ba  mov     rcx, [rsp+48h+FilterData]
0x1800011bf  mov     [rsp+48h+var_20], rcx
0x1800011c4  mov     rcx, r11
0x1800011c7  mov     [rsp+48h+var_28], r10
0x1800011cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011d1  add     rsp, 48h
0x1800011d5  retn
```
