# _tlgEnableCallback

- ea: `0x180001280`
- end: `0x1800012f6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001280`
- `0x180024010`

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
0x180001280  sub     rsp, 48h
0x180001284  mov     r11, rcx
0x180001287  mov     rcx, [rsp+48h+CallbackContext]
0x18000128f  test    rcx, rcx
0x180001292  jz      short loc_1800012F1
0x180001294  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001299  mov     eax, edx
0x18000129b  test    edx, edx
0x18000129d  jz      short loc_1800012C2
0x18000129f  cmp     eax, 1
0x1800012a2  jnz     short loc_1800012C8
0x1800012a4  test    r8b, r8b
0x1800012a7  jz      short loc_1800012B1
0x1800012a9  movzx   eax, r8b
0x1800012ad  inc     eax
0x1800012af  jmp     short loc_1800012B6
0x1800012b1  mov     eax, 100h
0x1800012b6  mov     [rcx], eax
0x1800012b8  mov     [rcx+10h], r9
0x1800012bc  mov     [rcx+18h], r10
0x1800012c0  jmp     short loc_1800012C8
0x1800012c2  mov     dword ptr [rcx], 0
0x1800012c8  mov     rax, [rcx+28h]
0x1800012cc  test    rax, rax
0x1800012cf  jz      short loc_1800012F1
0x1800012d1  mov     rcx, [rcx+30h]
0x1800012d5  mov     [rsp+48h+var_18], rcx
0x1800012da  mov     rcx, [rsp+48h+FilterData]
0x1800012df  mov     [rsp+48h+var_20], rcx
0x1800012e4  mov     rcx, r11
0x1800012e7  mov     [rsp+48h+var_28], r10
0x1800012ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012f1  add     rsp, 48h
0x1800012f5  retn
```
