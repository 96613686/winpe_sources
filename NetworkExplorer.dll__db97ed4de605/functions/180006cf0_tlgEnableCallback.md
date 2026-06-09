# _tlgEnableCallback

- ea: `0x180006cf0`
- end: `0x180006d66`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006cf0`
- `0x180010010`

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
0x180006cf0  sub     rsp, 48h
0x180006cf4  mov     r11, rcx
0x180006cf7  mov     rcx, [rsp+48h+CallbackContext]
0x180006cff  test    rcx, rcx
0x180006d02  jz      short loc_180006D61
0x180006d04  mov     r10, [rsp+48h+MatchAllKeyword]
0x180006d09  mov     eax, edx
0x180006d0b  test    edx, edx
0x180006d0d  jz      short loc_180006D32
0x180006d0f  cmp     eax, 1
0x180006d12  jnz     short loc_180006D38
0x180006d14  test    r8b, r8b
0x180006d17  jz      short loc_180006D21
0x180006d19  movzx   eax, r8b
0x180006d1d  inc     eax
0x180006d1f  jmp     short loc_180006D26
0x180006d21  mov     eax, 100h
0x180006d26  mov     [rcx], eax
0x180006d28  mov     [rcx+10h], r9
0x180006d2c  mov     [rcx+18h], r10
0x180006d30  jmp     short loc_180006D38
0x180006d32  mov     dword ptr [rcx], 0
0x180006d38  mov     rax, [rcx+28h]
0x180006d3c  test    rax, rax
0x180006d3f  jz      short loc_180006D61
0x180006d41  mov     rcx, [rcx+30h]
0x180006d45  mov     [rsp+48h+var_18], rcx
0x180006d4a  mov     rcx, [rsp+48h+FilterData]
0x180006d4f  mov     [rsp+48h+var_20], rcx
0x180006d54  mov     rcx, r11
0x180006d57  mov     [rsp+48h+var_28], r10
0x180006d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d61  add     rsp, 48h
0x180006d65  retn
```
