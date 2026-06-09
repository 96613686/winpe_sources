# _tlgEnableCallback

- ea: `0x140001950`
- end: `0x1400019c6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001950`
- `0x14000f010`

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
0x140001950  sub     rsp, 48h
0x140001954  mov     r11, rcx
0x140001957  mov     rcx, [rsp+48h+CallbackContext]
0x14000195f  test    rcx, rcx
0x140001962  jz      short loc_1400019C1
0x140001964  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001969  mov     eax, edx
0x14000196b  test    edx, edx
0x14000196d  jz      short loc_140001992
0x14000196f  cmp     eax, 1
0x140001972  jnz     short loc_140001998
0x140001974  test    r8b, r8b
0x140001977  jz      short loc_140001981
0x140001979  movzx   eax, r8b
0x14000197d  inc     eax
0x14000197f  jmp     short loc_140001986
0x140001981  mov     eax, 100h
0x140001986  mov     [rcx], eax
0x140001988  mov     [rcx+10h], r9
0x14000198c  mov     [rcx+18h], r10
0x140001990  jmp     short loc_140001998
0x140001992  mov     dword ptr [rcx], 0
0x140001998  mov     rax, [rcx+28h]
0x14000199c  test    rax, rax
0x14000199f  jz      short loc_1400019C1
0x1400019a1  mov     rcx, [rcx+30h]
0x1400019a5  mov     [rsp+48h+var_18], rcx
0x1400019aa  mov     rcx, [rsp+48h+FilterData]
0x1400019af  mov     [rsp+48h+var_20], rcx
0x1400019b4  mov     rcx, r11
0x1400019b7  mov     [rsp+48h+var_28], r10
0x1400019bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400019c1  add     rsp, 48h
0x1400019c5  retn
```
