# _tlgEnableCallback

- ea: `0x140001ad0`
- end: `0x140001b46`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001ad0`
- `0x140012010`

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
0x140001ad0  sub     rsp, 48h
0x140001ad4  mov     r11, rcx
0x140001ad7  mov     rcx, [rsp+48h+CallbackContext]
0x140001adf  test    rcx, rcx
0x140001ae2  jz      short loc_140001B41
0x140001ae4  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001ae9  mov     eax, edx
0x140001aeb  test    edx, edx
0x140001aed  jz      short loc_140001B12
0x140001aef  cmp     eax, 1
0x140001af2  jnz     short loc_140001B18
0x140001af4  test    r8b, r8b
0x140001af7  jz      short loc_140001B01
0x140001af9  movzx   eax, r8b
0x140001afd  inc     eax
0x140001aff  jmp     short loc_140001B06
0x140001b01  mov     eax, 100h
0x140001b06  mov     [rcx], eax
0x140001b08  mov     [rcx+10h], r9
0x140001b0c  mov     [rcx+18h], r10
0x140001b10  jmp     short loc_140001B18
0x140001b12  mov     dword ptr [rcx], 0
0x140001b18  mov     rax, [rcx+28h]
0x140001b1c  test    rax, rax
0x140001b1f  jz      short loc_140001B41
0x140001b21  mov     rcx, [rcx+30h]
0x140001b25  mov     [rsp+48h+var_18], rcx
0x140001b2a  mov     rcx, [rsp+48h+FilterData]
0x140001b2f  mov     [rsp+48h+var_20], rcx
0x140001b34  mov     rcx, r11
0x140001b37  mov     [rsp+48h+var_28], r10
0x140001b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001b41  add     rsp, 48h
0x140001b45  retn
```
