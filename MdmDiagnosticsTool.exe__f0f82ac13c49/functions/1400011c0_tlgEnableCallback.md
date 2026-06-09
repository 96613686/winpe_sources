# _tlgEnableCallback

- ea: `0x1400011c0`
- end: `0x140001240`
- name: `_tlgEnableCallback`
- size: `128`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400011c0`
- `0x14000a010`

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
0x1400011c0  sub     rsp, 48h
0x1400011c4  mov     r11, rcx
0x1400011c7  mov     rcx, [rsp+48h+CallbackContext]
0x1400011cf  test    rcx, rcx
0x1400011d2  jz      short loc_14000123B
0x1400011d4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1400011d9  mov     eax, edx
0x1400011db  test    edx, edx
0x1400011dd  jz      short loc_14000120C
0x1400011df  cmp     eax, 1
0x1400011e2  jnz     short loc_140001212
0x1400011e4  test    r8b, r8b
0x1400011e7  jz      short loc_1400011FB
0x1400011e9  movzx   eax, r8b
0x1400011ed  inc     eax
0x1400011ef  mov     [rcx], eax
0x1400011f1  mov     [rcx+10h], r9
0x1400011f5  mov     [rcx+18h], r10
0x1400011f9  jmp     short loc_140001212
0x1400011fb  mov     eax, 100h
0x140001200  mov     [rcx], eax
0x140001202  mov     [rcx+10h], r9
0x140001206  mov     [rcx+18h], r10
0x14000120a  jmp     short loc_140001212
0x14000120c  mov     dword ptr [rcx], 0
0x140001212  mov     rax, [rcx+28h]
0x140001216  test    rax, rax
0x140001219  jz      short loc_14000123B
0x14000121b  mov     rcx, [rcx+30h]
0x14000121f  mov     [rsp+48h+var_18], rcx
0x140001224  mov     rcx, [rsp+48h+FilterData]
0x140001229  mov     [rsp+48h+var_20], rcx
0x14000122e  mov     rcx, r11
0x140001231  mov     [rsp+48h+var_28], r10
0x140001236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000123b  add     rsp, 48h
0x14000123f  retn
```
