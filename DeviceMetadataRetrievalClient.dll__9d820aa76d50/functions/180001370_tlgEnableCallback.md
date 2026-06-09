# _tlgEnableCallback

- ea: `0x180001370`
- end: `0x1800013e6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001370`
- `0x180014010`

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
0x180001370  sub     rsp, 48h
0x180001374  mov     r11, rcx
0x180001377  mov     rcx, [rsp+48h+CallbackContext]
0x18000137f  test    rcx, rcx
0x180001382  jz      short loc_1800013E1
0x180001384  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001389  mov     eax, edx
0x18000138b  test    edx, edx
0x18000138d  jz      short loc_1800013B2
0x18000138f  cmp     eax, 1
0x180001392  jnz     short loc_1800013B8
0x180001394  test    r8b, r8b
0x180001397  jz      short loc_1800013A1
0x180001399  movzx   eax, r8b
0x18000139d  inc     eax
0x18000139f  jmp     short loc_1800013A6
0x1800013a1  mov     eax, 100h
0x1800013a6  mov     [rcx], eax
0x1800013a8  mov     [rcx+10h], r9
0x1800013ac  mov     [rcx+18h], r10
0x1800013b0  jmp     short loc_1800013B8
0x1800013b2  mov     dword ptr [rcx], 0
0x1800013b8  mov     rax, [rcx+28h]
0x1800013bc  test    rax, rax
0x1800013bf  jz      short loc_1800013E1
0x1800013c1  mov     rcx, [rcx+30h]
0x1800013c5  mov     [rsp+48h+var_18], rcx
0x1800013ca  mov     rcx, [rsp+48h+FilterData]
0x1800013cf  mov     [rsp+48h+var_20], rcx
0x1800013d4  mov     rcx, r11
0x1800013d7  mov     [rsp+48h+var_28], r10
0x1800013dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013e1  add     rsp, 48h
0x1800013e5  retn
```
