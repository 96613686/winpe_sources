# _tlgEnableCallback

- ea: `0x1800019d0`
- end: `0x180001a46`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800019d0`
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
0x1800019d0  sub     rsp, 48h
0x1800019d4  mov     r11, rcx
0x1800019d7  mov     rcx, [rsp+48h+CallbackContext]
0x1800019df  test    rcx, rcx
0x1800019e2  jz      short loc_180001A41
0x1800019e4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1800019e9  mov     eax, edx
0x1800019eb  test    edx, edx
0x1800019ed  jz      short loc_180001A12
0x1800019ef  cmp     eax, 1
0x1800019f2  jnz     short loc_180001A18
0x1800019f4  test    r8b, r8b
0x1800019f7  jz      short loc_180001A01
0x1800019f9  movzx   eax, r8b
0x1800019fd  inc     eax
0x1800019ff  jmp     short loc_180001A06
0x180001a01  mov     eax, 100h
0x180001a06  mov     [rcx], eax
0x180001a08  mov     [rcx+10h], r9
0x180001a0c  mov     [rcx+18h], r10
0x180001a10  jmp     short loc_180001A18
0x180001a12  mov     dword ptr [rcx], 0
0x180001a18  mov     rax, [rcx+28h]
0x180001a1c  test    rax, rax
0x180001a1f  jz      short loc_180001A41
0x180001a21  mov     rcx, [rcx+30h]
0x180001a25  mov     [rsp+48h+var_18], rcx
0x180001a2a  mov     rcx, [rsp+48h+FilterData]
0x180001a2f  mov     [rsp+48h+var_20], rcx
0x180001a34  mov     rcx, r11
0x180001a37  mov     [rsp+48h+var_28], r10
0x180001a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a41  add     rsp, 48h
0x180001a45  retn
```
