# EnableCallback

- ea: `0x180001470`
- end: `0x1800014f2`
- name: `EnableCallback`
- size: `130`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001470`
- `0x180172640`

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
  void (__fastcall *v7)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD); // rax

  if ( CallbackContext )
  {
    if ( (_DWORD)IsEnabled )
    {
      if ( (_DWORD)IsEnabled == 1 )
      {
        CallbackContext[2] = MatchAnyKeyword;
        if ( (_BYTE)Level )
          *(_DWORD *)CallbackContext = (unsigned __int8)Level + 1;
        else
          *(_DWORD *)CallbackContext = 256;
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
0x180001470  sub     rsp, 48h
0x180001474  mov     r11, rcx
0x180001477  mov     rcx, [rsp+48h+CallbackContext]
0x18000147f  test    rcx, rcx
0x180001482  jz      short loc_1800014EC
0x180001484  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001489  mov     eax, edx
0x18000148b  test    edx, edx
0x18000148d  jz      short loc_1800014BC
0x18000148f  cmp     eax, 1
0x180001492  jnz     short loc_1800014C2
0x180001494  test    r8b, r8b
0x180001497  jz      short loc_1800014AB
0x180001499  movzx   eax, r8b
0x18000149d  inc     eax
0x18000149f  mov     [rcx+10h], r9
0x1800014a3  mov     [rcx], eax
0x1800014a5  mov     [rcx+18h], r10
0x1800014a9  jmp     short loc_1800014C2
0x1800014ab  mov     eax, 100h
0x1800014b0  mov     [rcx+10h], r9
0x1800014b4  mov     [rcx], eax
0x1800014b6  mov     [rcx+18h], r10
0x1800014ba  jmp     short loc_1800014C2
0x1800014bc  mov     dword ptr [rcx], 0
0x1800014c2  mov     rax, [rcx+28h]
0x1800014c6  test    rax, rax
0x1800014c9  jz      short loc_1800014EC
0x1800014cb  mov     rcx, [rcx+30h]
0x1800014cf  mov     [rsp+48h+var_18], rcx
0x1800014d4  mov     rcx, [rsp+48h+FilterData]
0x1800014d9  mov     [rsp+48h+var_20], rcx
0x1800014de  mov     rcx, r11
0x1800014e1  mov     [rsp+48h+var_28], r10
0x1800014e6  call    cs:__guard_dispatch_icall_fptr
0x1800014ec  add     rsp, 48h
0x1800014f0  retn
```
