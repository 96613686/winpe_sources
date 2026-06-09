# _tlgEnableCallback

- ea: `0x180001730`
- end: `0x1800017a6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001730`
- `0x180086010`

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
0x180001730  sub     rsp, 48h
0x180001734  mov     r11, rcx
0x180001737  mov     rcx, [rsp+48h+CallbackContext]
0x18000173f  test    rcx, rcx
0x180001742  jz      short loc_1800017A1
0x180001744  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001749  mov     eax, edx
0x18000174b  test    edx, edx
0x18000174d  jz      short loc_180001772
0x18000174f  cmp     eax, 1
0x180001752  jnz     short loc_180001778
0x180001754  test    r8b, r8b
0x180001757  jz      short loc_180001761
0x180001759  movzx   eax, r8b
0x18000175d  inc     eax
0x18000175f  jmp     short loc_180001766
0x180001761  mov     eax, 100h
0x180001766  mov     [rcx], eax
0x180001768  mov     [rcx+10h], r9
0x18000176c  mov     [rcx+18h], r10
0x180001770  jmp     short loc_180001778
0x180001772  mov     dword ptr [rcx], 0
0x180001778  mov     rax, [rcx+28h]
0x18000177c  test    rax, rax
0x18000177f  jz      short loc_1800017A1
0x180001781  mov     rcx, [rcx+30h]
0x180001785  mov     [rsp+48h+var_18], rcx
0x18000178a  mov     rcx, [rsp+48h+FilterData]
0x18000178f  mov     [rsp+48h+var_20], rcx
0x180001794  mov     rcx, r11
0x180001797  mov     [rsp+48h+var_28], r10
0x18000179c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017a1  add     rsp, 48h
0x1800017a5  retn
```
