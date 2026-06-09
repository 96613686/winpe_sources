# _tlgEnableCallback

- ea: `0x1400011d0`
- end: `0x140001251`
- name: `_tlgEnableCallback`
- size: `129`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400011d0`
- `0x14000b010`

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
0x1400011d0  sub     rsp, 48h
0x1400011d4  mov     r11, rcx
0x1400011d7  mov     rcx, [rsp+48h+CallbackContext]
0x1400011df  test    rcx, rcx
0x1400011e2  jz      short loc_14000124B
0x1400011e4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1400011e9  mov     eax, edx
0x1400011eb  test    edx, edx
0x1400011ed  jz      short loc_14000121C
0x1400011ef  cmp     eax, 1
0x1400011f2  jnz     short loc_140001222
0x1400011f4  test    r8b, r8b
0x1400011f7  jz      short loc_14000120B
0x1400011f9  movzx   eax, r8b
0x1400011fd  inc     eax
0x1400011ff  mov     [rcx], eax
0x140001201  mov     [rcx+10h], r9
0x140001205  mov     [rcx+18h], r10
0x140001209  jmp     short loc_140001222
0x14000120b  mov     eax, 100h
0x140001210  mov     [rcx], eax
0x140001212  mov     [rcx+10h], r9
0x140001216  mov     [rcx+18h], r10
0x14000121a  jmp     short loc_140001222
0x14000121c  mov     dword ptr [rcx], 0
0x140001222  mov     rax, [rcx+28h]
0x140001226  test    rax, rax
0x140001229  jz      short loc_14000124B
0x14000122b  mov     rcx, [rcx+30h]
0x14000122f  mov     [rsp+48h+var_18], rcx
0x140001234  mov     rcx, [rsp+48h+FilterData]
0x140001239  mov     [rsp+48h+var_20], rcx
0x14000123e  mov     rcx, r11
0x140001241  mov     [rsp+48h+var_28], r10
0x140001246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000124b  add     rsp, 48h
0x14000124f  retn
```
