# _tlgEnableCallback

- ea: `0x140002270`
- end: `0x1400022e6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002270`
- `0x14001a010`

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
0x140002270  sub     rsp, 48h
0x140002274  mov     r11, rcx
0x140002277  mov     rcx, [rsp+48h+CallbackContext]
0x14000227f  test    rcx, rcx
0x140002282  jz      short loc_1400022E1
0x140002284  mov     r10, [rsp+48h+MatchAllKeyword]
0x140002289  mov     eax, edx
0x14000228b  test    edx, edx
0x14000228d  jz      short loc_1400022B2
0x14000228f  cmp     eax, 1
0x140002292  jnz     short loc_1400022B8
0x140002294  test    r8b, r8b
0x140002297  jz      short loc_1400022A1
0x140002299  movzx   eax, r8b
0x14000229d  inc     eax
0x14000229f  jmp     short loc_1400022A6
0x1400022a1  mov     eax, 100h
0x1400022a6  mov     [rcx], eax
0x1400022a8  mov     [rcx+10h], r9
0x1400022ac  mov     [rcx+18h], r10
0x1400022b0  jmp     short loc_1400022B8
0x1400022b2  mov     dword ptr [rcx], 0
0x1400022b8  mov     rax, [rcx+28h]
0x1400022bc  test    rax, rax
0x1400022bf  jz      short loc_1400022E1
0x1400022c1  mov     rcx, [rcx+30h]
0x1400022c5  mov     [rsp+48h+var_18], rcx
0x1400022ca  mov     rcx, [rsp+48h+FilterData]
0x1400022cf  mov     [rsp+48h+var_20], rcx
0x1400022d4  mov     rcx, r11
0x1400022d7  mov     [rsp+48h+var_28], r10
0x1400022dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400022e1  add     rsp, 48h
0x1400022e5  retn
```
