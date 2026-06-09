# _tlgEnableCallback

- ea: `0x180001d20`
- end: `0x180001d96`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001d20`
- `0x180012010`

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
0x180001d20  sub     rsp, 48h
0x180001d24  mov     r11, rcx
0x180001d27  mov     rcx, [rsp+48h+CallbackContext]
0x180001d2f  test    rcx, rcx
0x180001d32  jz      short loc_180001D91
0x180001d34  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001d39  mov     eax, edx
0x180001d3b  test    edx, edx
0x180001d3d  jz      short loc_180001D62
0x180001d3f  cmp     eax, 1
0x180001d42  jnz     short loc_180001D68
0x180001d44  test    r8b, r8b
0x180001d47  jz      short loc_180001D51
0x180001d49  movzx   eax, r8b
0x180001d4d  inc     eax
0x180001d4f  jmp     short loc_180001D56
0x180001d51  mov     eax, 100h
0x180001d56  mov     [rcx], eax
0x180001d58  mov     [rcx+10h], r9
0x180001d5c  mov     [rcx+18h], r10
0x180001d60  jmp     short loc_180001D68
0x180001d62  mov     dword ptr [rcx], 0
0x180001d68  mov     rax, [rcx+28h]
0x180001d6c  test    rax, rax
0x180001d6f  jz      short loc_180001D91
0x180001d71  mov     rcx, [rcx+30h]
0x180001d75  mov     [rsp+48h+var_18], rcx
0x180001d7a  mov     rcx, [rsp+48h+FilterData]
0x180001d7f  mov     [rsp+48h+var_20], rcx
0x180001d84  mov     rcx, r11
0x180001d87  mov     [rsp+48h+var_28], r10
0x180001d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d91  add     rsp, 48h
0x180001d95  retn
```
