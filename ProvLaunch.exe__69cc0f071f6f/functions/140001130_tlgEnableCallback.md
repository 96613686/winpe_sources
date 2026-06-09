# _tlgEnableCallback

- ea: `0x140001130`
- end: `0x1400011a6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001130`
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
0x140001130  sub     rsp, 48h
0x140001134  mov     r11, rcx
0x140001137  mov     rcx, [rsp+48h+CallbackContext]
0x14000113f  test    rcx, rcx
0x140001142  jz      short loc_1400011A1
0x140001144  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001149  mov     eax, edx
0x14000114b  test    edx, edx
0x14000114d  jz      short loc_140001172
0x14000114f  cmp     eax, 1
0x140001152  jnz     short loc_140001178
0x140001154  test    r8b, r8b
0x140001157  jz      short loc_140001161
0x140001159  movzx   eax, r8b
0x14000115d  inc     eax
0x14000115f  jmp     short loc_140001166
0x140001161  mov     eax, 100h
0x140001166  mov     [rcx], eax
0x140001168  mov     [rcx+10h], r9
0x14000116c  mov     [rcx+18h], r10
0x140001170  jmp     short loc_140001178
0x140001172  mov     dword ptr [rcx], 0
0x140001178  mov     rax, [rcx+28h]
0x14000117c  test    rax, rax
0x14000117f  jz      short loc_1400011A1
0x140001181  mov     rcx, [rcx+30h]
0x140001185  mov     [rsp+48h+var_18], rcx
0x14000118a  mov     rcx, [rsp+48h+FilterData]
0x14000118f  mov     [rsp+48h+var_20], rcx
0x140001194  mov     rcx, r11
0x140001197  mov     [rsp+48h+var_28], r10
0x14000119c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400011a1  add     rsp, 48h
0x1400011a5  retn
```
