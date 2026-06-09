# _tlgEnableCallback

- ea: `0x180009b50`
- end: `0x180009bd0`
- name: `_tlgEnableCallback`
- size: `128`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009b50`
- `0x180029010`

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
  void (__fastcall *v7)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD); // rax

  if ( CallbackContext )
  {
    if ( (_DWORD)IsEnabled )
    {
      if ( (_DWORD)IsEnabled == 1 )
      {
        if ( (_BYTE)Level )
          *(_DWORD *)CallbackContext = (unsigned __int8)Level + 1;
        else
          *(_DWORD *)CallbackContext = 256;
        CallbackContext[2] = MatchAnyKeyword;
        CallbackContext[3] = MatchAllKeyword;
      }
    }
    else
    {
      *(_DWORD *)CallbackContext = 0;
    }
    v7 = (void (__fastcall *)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD))CallbackContext[5];
    if ( v7 )
      v7(SourceId, IsEnabled, Level, MatchAnyKeyword, MatchAllKeyword, FilterData, CallbackContext[6]);
  }
}

```

## disassembly

```asm
0x180009b50  sub     rsp, 48h
0x180009b54  mov     r11, rcx
0x180009b57  mov     rcx, [rsp+48h+CallbackContext]
0x180009b5f  test    rcx, rcx
0x180009b62  jz      short loc_180009BCB
0x180009b64  mov     r10, [rsp+48h+MatchAllKeyword]
0x180009b69  mov     eax, edx
0x180009b6b  test    edx, edx
0x180009b6d  jz      short loc_180009B9C
0x180009b6f  cmp     eax, 1
0x180009b72  jnz     short loc_180009BA2
0x180009b74  test    r8b, r8b
0x180009b77  jz      short loc_180009B8B
0x180009b79  movzx   eax, r8b
0x180009b7d  inc     eax
0x180009b7f  mov     [rcx], eax
0x180009b81  mov     [rcx+10h], r9
0x180009b85  mov     [rcx+18h], r10
0x180009b89  jmp     short loc_180009BA2
0x180009b8b  mov     eax, 100h
0x180009b90  mov     [rcx], eax
0x180009b92  mov     [rcx+10h], r9
0x180009b96  mov     [rcx+18h], r10
0x180009b9a  jmp     short loc_180009BA2
0x180009b9c  mov     dword ptr [rcx], 0
0x180009ba2  mov     rax, [rcx+28h]
0x180009ba6  test    rax, rax
0x180009ba9  jz      short loc_180009BCB
0x180009bab  mov     rcx, [rcx+30h]
0x180009baf  mov     [rsp+48h+var_18], rcx
0x180009bb4  mov     rcx, [rsp+48h+FilterData]
0x180009bb9  mov     [rsp+48h+var_20], rcx
0x180009bbe  mov     rcx, r11
0x180009bc1  mov     [rsp+48h+var_28], r10
0x180009bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bcb  add     rsp, 48h
0x180009bcf  retn
```
