# _tlgEnableCallback

- ea: `0x140001ae0`
- end: `0x140001b56`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001ae0`
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
0x140001ae0  sub     rsp, 48h
0x140001ae4  mov     r11, rcx
0x140001ae7  mov     rcx, [rsp+48h+CallbackContext]
0x140001aef  test    rcx, rcx
0x140001af2  jz      short loc_140001B51
0x140001af4  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001af9  mov     eax, edx
0x140001afb  test    edx, edx
0x140001afd  jz      short loc_140001B22
0x140001aff  cmp     eax, 1
0x140001b02  jnz     short loc_140001B28
0x140001b04  test    r8b, r8b
0x140001b07  jz      short loc_140001B11
0x140001b09  movzx   eax, r8b
0x140001b0d  inc     eax
0x140001b0f  jmp     short loc_140001B16
0x140001b11  mov     eax, 100h
0x140001b16  mov     [rcx], eax
0x140001b18  mov     [rcx+10h], r9
0x140001b1c  mov     [rcx+18h], r10
0x140001b20  jmp     short loc_140001B28
0x140001b22  mov     dword ptr [rcx], 0
0x140001b28  mov     rax, [rcx+28h]
0x140001b2c  test    rax, rax
0x140001b2f  jz      short loc_140001B51
0x140001b31  mov     rcx, [rcx+30h]
0x140001b35  mov     [rsp+48h+var_18], rcx
0x140001b3a  mov     rcx, [rsp+48h+FilterData]
0x140001b3f  mov     [rsp+48h+var_20], rcx
0x140001b44  mov     rcx, r11
0x140001b47  mov     [rsp+48h+var_28], r10
0x140001b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001b51  add     rsp, 48h
0x140001b55  retn
```
