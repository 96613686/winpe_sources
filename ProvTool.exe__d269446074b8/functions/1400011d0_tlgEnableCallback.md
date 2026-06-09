# _tlgEnableCallback

- ea: `0x1400011d0`
- end: `0x140001246`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400011d0`
- `0x140010010`

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
0x1400011d0  sub     rsp, 48h
0x1400011d4  mov     r11, rcx
0x1400011d7  mov     rcx, [rsp+48h+CallbackContext]
0x1400011df  test    rcx, rcx
0x1400011e2  jz      short loc_140001241
0x1400011e4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1400011e9  mov     eax, edx
0x1400011eb  test    edx, edx
0x1400011ed  jz      short loc_140001212
0x1400011ef  cmp     eax, 1
0x1400011f2  jnz     short loc_140001218
0x1400011f4  test    r8b, r8b
0x1400011f7  jz      short loc_140001201
0x1400011f9  movzx   eax, r8b
0x1400011fd  inc     eax
0x1400011ff  jmp     short loc_140001206
0x140001201  mov     eax, 100h
0x140001206  mov     [rcx], eax
0x140001208  mov     [rcx+10h], r9
0x14000120c  mov     [rcx+18h], r10
0x140001210  jmp     short loc_140001218
0x140001212  mov     dword ptr [rcx], 0
0x140001218  mov     rax, [rcx+28h]
0x14000121c  test    rax, rax
0x14000121f  jz      short loc_140001241
0x140001221  mov     rcx, [rcx+30h]
0x140001225  mov     [rsp+48h+var_18], rcx
0x14000122a  mov     rcx, [rsp+48h+FilterData]
0x14000122f  mov     [rsp+48h+var_20], rcx
0x140001234  mov     rcx, r11
0x140001237  mov     [rsp+48h+var_28], r10
0x14000123c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001241  add     rsp, 48h
0x140001245  retn
```
