# _tlgEnableCallback

- ea: `0x1400011e0`
- end: `0x140001256`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400011e0`
- `0x14003a010`

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
0x1400011e0  sub     rsp, 48h
0x1400011e4  mov     r11, rcx
0x1400011e7  mov     rcx, [rsp+48h+CallbackContext]
0x1400011ef  test    rcx, rcx
0x1400011f2  jz      short loc_140001251
0x1400011f4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1400011f9  mov     eax, edx
0x1400011fb  test    edx, edx
0x1400011fd  jz      short loc_140001222
0x1400011ff  cmp     eax, 1
0x140001202  jnz     short loc_140001228
0x140001204  test    r8b, r8b
0x140001207  jz      short loc_140001211
0x140001209  movzx   eax, r8b
0x14000120d  inc     eax
0x14000120f  jmp     short loc_140001216
0x140001211  mov     eax, 100h
0x140001216  mov     [rcx], eax
0x140001218  mov     [rcx+10h], r9
0x14000121c  mov     [rcx+18h], r10
0x140001220  jmp     short loc_140001228
0x140001222  mov     dword ptr [rcx], 0
0x140001228  mov     rax, [rcx+28h]
0x14000122c  test    rax, rax
0x14000122f  jz      short loc_140001251
0x140001231  mov     rcx, [rcx+30h]
0x140001235  mov     [rsp+48h+var_18], rcx
0x14000123a  mov     rcx, [rsp+48h+FilterData]
0x14000123f  mov     [rsp+48h+var_20], rcx
0x140001244  mov     rcx, r11
0x140001247  mov     [rsp+48h+var_28], r10
0x14000124c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001251  add     rsp, 48h
0x140001255  retn
```
