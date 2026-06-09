# _tlgEnableCallback

- ea: `0x180001190`
- end: `0x180001206`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001190`
- `0x18001e010`

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
0x180001190  sub     rsp, 48h
0x180001194  mov     r11, rcx
0x180001197  mov     rcx, [rsp+48h+CallbackContext]
0x18000119f  test    rcx, rcx
0x1800011a2  jz      short loc_180001201
0x1800011a4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1800011a9  mov     eax, edx
0x1800011ab  test    edx, edx
0x1800011ad  jz      short loc_1800011D2
0x1800011af  cmp     eax, 1
0x1800011b2  jnz     short loc_1800011D8
0x1800011b4  test    r8b, r8b
0x1800011b7  jz      short loc_1800011C1
0x1800011b9  movzx   eax, r8b
0x1800011bd  inc     eax
0x1800011bf  jmp     short loc_1800011C6
0x1800011c1  mov     eax, 100h
0x1800011c6  mov     [rcx], eax
0x1800011c8  mov     [rcx+10h], r9
0x1800011cc  mov     [rcx+18h], r10
0x1800011d0  jmp     short loc_1800011D8
0x1800011d2  mov     dword ptr [rcx], 0
0x1800011d8  mov     rax, [rcx+28h]
0x1800011dc  test    rax, rax
0x1800011df  jz      short loc_180001201
0x1800011e1  mov     rcx, [rcx+30h]
0x1800011e5  mov     [rsp+48h+var_18], rcx
0x1800011ea  mov     rcx, [rsp+48h+FilterData]
0x1800011ef  mov     [rsp+48h+var_20], rcx
0x1800011f4  mov     rcx, r11
0x1800011f7  mov     [rsp+48h+var_28], r10
0x1800011fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001201  add     rsp, 48h
0x180001205  retn
```
