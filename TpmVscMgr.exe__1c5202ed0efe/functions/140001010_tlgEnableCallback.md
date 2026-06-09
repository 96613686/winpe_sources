# _tlgEnableCallback

- ea: `0x140001010`
- end: `0x140001086`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001010`
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
0x140001010  sub     rsp, 48h
0x140001014  mov     r11, rcx
0x140001017  mov     rcx, [rsp+48h+CallbackContext]
0x14000101f  test    rcx, rcx
0x140001022  jz      short loc_140001081
0x140001024  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001029  mov     eax, edx
0x14000102b  test    edx, edx
0x14000102d  jz      short loc_140001052
0x14000102f  cmp     eax, 1
0x140001032  jnz     short loc_140001058
0x140001034  test    r8b, r8b
0x140001037  jz      short loc_140001041
0x140001039  movzx   eax, r8b
0x14000103d  inc     eax
0x14000103f  jmp     short loc_140001046
0x140001041  mov     eax, 100h
0x140001046  mov     [rcx], eax
0x140001048  mov     [rcx+10h], r9
0x14000104c  mov     [rcx+18h], r10
0x140001050  jmp     short loc_140001058
0x140001052  mov     dword ptr [rcx], 0
0x140001058  mov     rax, [rcx+28h]
0x14000105c  test    rax, rax
0x14000105f  jz      short loc_140001081
0x140001061  mov     rcx, [rcx+30h]
0x140001065  mov     [rsp+48h+var_18], rcx
0x14000106a  mov     rcx, [rsp+48h+FilterData]
0x14000106f  mov     [rsp+48h+var_20], rcx
0x140001074  mov     rcx, r11
0x140001077  mov     [rsp+48h+var_28], r10
0x14000107c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001081  add     rsp, 48h
0x140001085  retn
```
