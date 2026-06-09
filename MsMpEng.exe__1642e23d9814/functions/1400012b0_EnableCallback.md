# EnableCallback

- ea: `0x1400012b0`
- end: `0x140001334`
- name: `EnableCallback`
- size: `132`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400012b0`
- `0x140029bd0`

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
0x1400012b0  mov     [rsp+arg_0], rbx
0x1400012b5  push    rdi
0x1400012b6  sub     rsp, 40h
0x1400012ba  mov     r10, [rsp+48h+CallbackContext]
0x1400012c2  mov     rdi, rcx
0x1400012c5  test    r10, r10
0x1400012c8  jz      short loc_140001329
0x1400012ca  mov     r11, [rsp+48h+MatchAllKeyword]
0x1400012cf  mov     eax, edx
0x1400012d1  test    edx, edx
0x1400012d3  jz      short loc_1400012F8
0x1400012d5  cmp     eax, 1
0x1400012d8  jnz     short loc_1400012FF
0x1400012da  movzx   eax, r8b
0x1400012de  mov     ecx, 100h
0x1400012e3  inc     eax
0x1400012e5  mov     [r10+10h], r9
0x1400012e9  test    r8b, r8b
0x1400012ec  mov     [r10+18h], r11
0x1400012f0  cmovnz  ecx, eax
0x1400012f3  mov     [r10], ecx
0x1400012f6  jmp     short loc_1400012FF
0x1400012f8  mov     dword ptr [r10], 0
0x1400012ff  mov     rax, [r10+28h]
0x140001303  test    rax, rax
0x140001306  jz      short loc_140001329
0x140001308  mov     rcx, [r10+30h]
0x14000130c  mov     [rsp+48h+var_18], rcx
0x140001311  mov     rcx, [rsp+48h+FilterData]
0x140001316  mov     [rsp+48h+var_20], rcx
0x14000131b  mov     rcx, rdi
0x14000131e  mov     [rsp+48h+var_28], r11
0x140001323  call    cs:__guard_dispatch_icall_fptr
0x140001329  mov     rbx, [rsp+48h+arg_0]
0x14000132e  add     rsp, 40h
0x140001332  pop     rdi
0x140001333  retn
```
