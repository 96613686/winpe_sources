# EnableCallback

- ea: `0x180001000`
- end: `0x180001084`
- name: `EnableCallback`
- size: `132`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001000`
- `0x18002d040`

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
0x180001000  mov     [rsp+arg_0], rbx
0x180001005  push    rdi
0x180001006  sub     rsp, 40h
0x18000100a  mov     r10, [rsp+48h+CallbackContext]
0x180001012  mov     rdi, rcx
0x180001015  test    r10, r10
0x180001018  jz      short loc_180001079
0x18000101a  mov     r11, [rsp+48h+MatchAllKeyword]
0x18000101f  mov     eax, edx
0x180001021  test    edx, edx
0x180001023  jz      short loc_180001048
0x180001025  cmp     eax, 1
0x180001028  jnz     short loc_18000104F
0x18000102a  movzx   eax, r8b
0x18000102e  mov     ecx, 100h
0x180001033  inc     eax
0x180001035  mov     [r10+10h], r9
0x180001039  test    r8b, r8b
0x18000103c  mov     [r10+18h], r11
0x180001040  cmovnz  ecx, eax
0x180001043  mov     [r10], ecx
0x180001046  jmp     short loc_18000104F
0x180001048  mov     dword ptr [r10], 0
0x18000104f  mov     rax, [r10+28h]
0x180001053  test    rax, rax
0x180001056  jz      short loc_180001079
0x180001058  mov     rcx, [r10+30h]
0x18000105c  mov     [rsp+48h+var_18], rcx
0x180001061  mov     rcx, [rsp+48h+FilterData]
0x180001066  mov     [rsp+48h+var_20], rcx
0x18000106b  mov     rcx, rdi
0x18000106e  mov     [rsp+48h+var_28], r11
0x180001073  call    cs:__guard_dispatch_icall_fptr
0x180001079  mov     rbx, [rsp+48h+arg_0]
0x18000107e  add     rsp, 40h
0x180001082  pop     rdi
0x180001083  retn
```
