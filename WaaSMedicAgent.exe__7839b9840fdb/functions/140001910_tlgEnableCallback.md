# _tlgEnableCallback

- ea: `0x140001910`
- end: `0x140001986`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001910`
- `0x140013010`

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
0x140001910  sub     rsp, 48h
0x140001914  mov     r11, rcx
0x140001917  mov     rcx, [rsp+48h+CallbackContext]
0x14000191f  test    rcx, rcx
0x140001922  jz      short loc_140001981
0x140001924  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001929  mov     eax, edx
0x14000192b  test    edx, edx
0x14000192d  jz      short loc_140001952
0x14000192f  cmp     eax, 1
0x140001932  jnz     short loc_140001958
0x140001934  test    r8b, r8b
0x140001937  jz      short loc_140001941
0x140001939  movzx   eax, r8b
0x14000193d  inc     eax
0x14000193f  jmp     short loc_140001946
0x140001941  mov     eax, 100h
0x140001946  mov     [rcx], eax
0x140001948  mov     [rcx+10h], r9
0x14000194c  mov     [rcx+18h], r10
0x140001950  jmp     short loc_140001958
0x140001952  mov     dword ptr [rcx], 0
0x140001958  mov     rax, [rcx+28h]
0x14000195c  test    rax, rax
0x14000195f  jz      short loc_140001981
0x140001961  mov     rcx, [rcx+30h]
0x140001965  mov     [rsp+48h+var_18], rcx
0x14000196a  mov     rcx, [rsp+48h+FilterData]
0x14000196f  mov     [rsp+48h+var_20], rcx
0x140001974  mov     rcx, r11
0x140001977  mov     [rsp+48h+var_28], r10
0x14000197c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001981  add     rsp, 48h
0x140001985  retn
```
