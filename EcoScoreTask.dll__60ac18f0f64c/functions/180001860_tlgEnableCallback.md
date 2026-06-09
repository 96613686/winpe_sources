# _tlgEnableCallback

- ea: `0x180001860`
- end: `0x1800018d6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001860`
- `0x180009010`

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
0x180001860  sub     rsp, 48h
0x180001864  mov     r11, rcx
0x180001867  mov     rcx, [rsp+48h+CallbackContext]
0x18000186f  test    rcx, rcx
0x180001872  jz      short loc_1800018D1
0x180001874  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001879  mov     eax, edx
0x18000187b  test    edx, edx
0x18000187d  jz      short loc_1800018A2
0x18000187f  cmp     eax, 1
0x180001882  jnz     short loc_1800018A8
0x180001884  test    r8b, r8b
0x180001887  jz      short loc_180001891
0x180001889  movzx   eax, r8b
0x18000188d  inc     eax
0x18000188f  jmp     short loc_180001896
0x180001891  mov     eax, 100h
0x180001896  mov     [rcx], eax
0x180001898  mov     [rcx+10h], r9
0x18000189c  mov     [rcx+18h], r10
0x1800018a0  jmp     short loc_1800018A8
0x1800018a2  mov     dword ptr [rcx], 0
0x1800018a8  mov     rax, [rcx+28h]
0x1800018ac  test    rax, rax
0x1800018af  jz      short loc_1800018D1
0x1800018b1  mov     rcx, [rcx+30h]
0x1800018b5  mov     [rsp+48h+var_18], rcx
0x1800018ba  mov     rcx, [rsp+48h+FilterData]
0x1800018bf  mov     [rsp+48h+var_20], rcx
0x1800018c4  mov     rcx, r11
0x1800018c7  mov     [rsp+48h+var_28], r10
0x1800018cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018d1  add     rsp, 48h
0x1800018d5  retn
```
