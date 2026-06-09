# _tlgEnableCallback

- ea: `0x180005be0`
- end: `0x180005c56`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005be0`
- `0x180015010`

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
0x180005be0  sub     rsp, 48h
0x180005be4  mov     r11, rcx
0x180005be7  mov     rcx, [rsp+48h+CallbackContext]
0x180005bef  test    rcx, rcx
0x180005bf2  jz      short loc_180005C51
0x180005bf4  mov     r10, [rsp+48h+MatchAllKeyword]
0x180005bf9  mov     eax, edx
0x180005bfb  test    edx, edx
0x180005bfd  jz      short loc_180005C22
0x180005bff  cmp     eax, 1
0x180005c02  jnz     short loc_180005C28
0x180005c04  test    r8b, r8b
0x180005c07  jz      short loc_180005C11
0x180005c09  movzx   eax, r8b
0x180005c0d  inc     eax
0x180005c0f  jmp     short loc_180005C16
0x180005c11  mov     eax, 100h
0x180005c16  mov     [rcx], eax
0x180005c18  mov     [rcx+10h], r9
0x180005c1c  mov     [rcx+18h], r10
0x180005c20  jmp     short loc_180005C28
0x180005c22  mov     dword ptr [rcx], 0
0x180005c28  mov     rax, [rcx+28h]
0x180005c2c  test    rax, rax
0x180005c2f  jz      short loc_180005C51
0x180005c31  mov     rcx, [rcx+30h]
0x180005c35  mov     [rsp+48h+var_18], rcx
0x180005c3a  mov     rcx, [rsp+48h+FilterData]
0x180005c3f  mov     [rsp+48h+var_20], rcx
0x180005c44  mov     rcx, r11
0x180005c47  mov     [rsp+48h+var_28], r10
0x180005c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c51  add     rsp, 48h
0x180005c55  retn
```
