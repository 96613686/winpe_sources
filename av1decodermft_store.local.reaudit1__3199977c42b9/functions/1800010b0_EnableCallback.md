# EnableCallback

- ea: `0x1800010b0`
- end: `0x180001135`
- name: `EnableCallback`
- size: `133`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800010b0`
- `0x1801f9250`

## pseudocode

```c
void __fastcall EnableCallback(
        LPCGUID SourceId,
        __int64 IsEnabled,
        __int64 Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        _QWORD *CallbackContext)
{
  int v8; // ecx
  void (__fastcall *v9)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD); // rax

  if ( CallbackContext )
  {
    if ( (_DWORD)IsEnabled )
    {
      if ( (_DWORD)IsEnabled == 1 )
      {
        v8 = 256;
        CallbackContext[2] = MatchAnyKeyword;
        CallbackContext[3] = MatchAllKeyword;
        if ( (_BYTE)Level )
          v8 = (unsigned __int8)Level + 1;
        *(_DWORD *)CallbackContext = v8;
      }
    }
    else
    {
      *(_DWORD *)CallbackContext = 0;
    }
    v9 = (void (__fastcall *)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD))CallbackContext[5];
    if ( v9 )
      v9(SourceId, IsEnabled, Level, MatchAnyKeyword, MatchAllKeyword, FilterData, CallbackContext[6]);
  }
}

```

## disassembly

```asm
0x1800010b0  mov     [rsp+arg_0], rbx
0x1800010b5  push    rdi
0x1800010b6  sub     rsp, 40h
0x1800010ba  mov     r10, [rsp+48h+CallbackContext]
0x1800010c2  mov     rdi, rcx
0x1800010c5  test    r10, r10
0x1800010c8  jz      short loc_180001129
0x1800010ca  mov     r11, [rsp+48h+MatchAllKeyword]
0x1800010cf  mov     eax, edx
0x1800010d1  test    edx, edx
0x1800010d3  jz      short loc_1800010F8
0x1800010d5  cmp     eax, 1
0x1800010d8  jnz     short loc_1800010FF
0x1800010da  movzx   eax, r8b
0x1800010de  mov     ecx, 100h
0x1800010e3  inc     eax
0x1800010e5  mov     [r10+10h], r9
0x1800010e9  test    r8b, r8b
0x1800010ec  mov     [r10+18h], r11
0x1800010f0  cmovnz  ecx, eax
0x1800010f3  mov     [r10], ecx
0x1800010f6  jmp     short loc_1800010FF
0x1800010f8  mov     dword ptr [r10], 0
0x1800010ff  mov     rax, [r10+28h]
0x180001103  test    rax, rax
0x180001106  jz      short loc_180001129
0x180001108  mov     rcx, [r10+30h]
0x18000110c  mov     [rsp+48h+var_18], rcx
0x180001111  mov     rcx, [rsp+48h+FilterData]
0x180001116  mov     [rsp+48h+var_20], rcx
0x18000111b  mov     rcx, rdi
0x18000111e  mov     [rsp+48h+var_28], r11
0x180001123  call    cs:__guard_dispatch_icall_fptr
0x180001129  mov     rbx, [rsp+48h+arg_0]
0x18000112e  add     rsp, 40h
0x180001132  pop     rdi
0x180001133  retn
```
