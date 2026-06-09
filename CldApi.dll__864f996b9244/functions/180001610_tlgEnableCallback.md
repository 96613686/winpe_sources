# _tlgEnableCallback

- ea: `0x180001610`
- end: `0x180001686`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001610`
- `0x18001c010`

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
0x180001610  sub     rsp, 48h
0x180001614  mov     r11, rcx
0x180001617  mov     rcx, [rsp+48h+CallbackContext]
0x18000161f  test    rcx, rcx
0x180001622  jz      short loc_180001681
0x180001624  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001629  mov     eax, edx
0x18000162b  test    edx, edx
0x18000162d  jz      short loc_180001652
0x18000162f  cmp     eax, 1
0x180001632  jnz     short loc_180001658
0x180001634  test    r8b, r8b
0x180001637  jz      short loc_180001641
0x180001639  movzx   eax, r8b
0x18000163d  inc     eax
0x18000163f  jmp     short loc_180001646
0x180001641  mov     eax, 100h
0x180001646  mov     [rcx], eax
0x180001648  mov     [rcx+10h], r9
0x18000164c  mov     [rcx+18h], r10
0x180001650  jmp     short loc_180001658
0x180001652  mov     dword ptr [rcx], 0
0x180001658  mov     rax, [rcx+28h]
0x18000165c  test    rax, rax
0x18000165f  jz      short loc_180001681
0x180001661  mov     rcx, [rcx+30h]
0x180001665  mov     [rsp+48h+var_18], rcx
0x18000166a  mov     rcx, [rsp+48h+FilterData]
0x18000166f  mov     [rsp+48h+var_20], rcx
0x180001674  mov     rcx, r11
0x180001677  mov     [rsp+48h+var_28], r10
0x18000167c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001681  add     rsp, 48h
0x180001685  retn
```
