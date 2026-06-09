# _tlgEnableCallback

- ea: `0x1400019f0`
- end: `0x140001a66`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400019f0`
- `0x140018010`

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
0x1400019f0  sub     rsp, 48h
0x1400019f4  mov     r11, rcx
0x1400019f7  mov     rcx, [rsp+48h+CallbackContext]
0x1400019ff  test    rcx, rcx
0x140001a02  jz      short loc_140001A61
0x140001a04  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001a09  mov     eax, edx
0x140001a0b  test    edx, edx
0x140001a0d  jz      short loc_140001A32
0x140001a0f  cmp     eax, 1
0x140001a12  jnz     short loc_140001A38
0x140001a14  test    r8b, r8b
0x140001a17  jz      short loc_140001A21
0x140001a19  movzx   eax, r8b
0x140001a1d  inc     eax
0x140001a1f  jmp     short loc_140001A26
0x140001a21  mov     eax, 100h
0x140001a26  mov     [rcx], eax
0x140001a28  mov     [rcx+10h], r9
0x140001a2c  mov     [rcx+18h], r10
0x140001a30  jmp     short loc_140001A38
0x140001a32  mov     dword ptr [rcx], 0
0x140001a38  mov     rax, [rcx+28h]
0x140001a3c  test    rax, rax
0x140001a3f  jz      short loc_140001A61
0x140001a41  mov     rcx, [rcx+30h]
0x140001a45  mov     [rsp+48h+var_18], rcx
0x140001a4a  mov     rcx, [rsp+48h+FilterData]
0x140001a4f  mov     [rsp+48h+var_20], rcx
0x140001a54  mov     rcx, r11
0x140001a57  mov     [rsp+48h+var_28], r10
0x140001a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001a61  add     rsp, 48h
0x140001a65  retn
```
