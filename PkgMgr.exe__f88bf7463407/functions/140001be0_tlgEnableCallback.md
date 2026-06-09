# _tlgEnableCallback

- ea: `0x140001be0`
- end: `0x140001c56`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001be0`
- `0x14002a010`

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
0x140001be0  sub     rsp, 48h
0x140001be4  mov     r11, rcx
0x140001be7  mov     rcx, [rsp+48h+CallbackContext]
0x140001bef  test    rcx, rcx
0x140001bf2  jz      short loc_140001C51
0x140001bf4  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001bf9  mov     eax, edx
0x140001bfb  test    edx, edx
0x140001bfd  jz      short loc_140001C22
0x140001bff  cmp     eax, 1
0x140001c02  jnz     short loc_140001C28
0x140001c04  test    r8b, r8b
0x140001c07  jz      short loc_140001C11
0x140001c09  movzx   eax, r8b
0x140001c0d  inc     eax
0x140001c0f  jmp     short loc_140001C16
0x140001c11  mov     eax, 100h
0x140001c16  mov     [rcx], eax
0x140001c18  mov     [rcx+10h], r9
0x140001c1c  mov     [rcx+18h], r10
0x140001c20  jmp     short loc_140001C28
0x140001c22  mov     dword ptr [rcx], 0
0x140001c28  mov     rax, [rcx+28h]
0x140001c2c  test    rax, rax
0x140001c2f  jz      short loc_140001C51
0x140001c31  mov     rcx, [rcx+30h]
0x140001c35  mov     [rsp+48h+var_18], rcx
0x140001c3a  mov     rcx, [rsp+48h+FilterData]
0x140001c3f  mov     [rsp+48h+var_20], rcx
0x140001c44  mov     rcx, r11
0x140001c47  mov     [rsp+48h+var_28], r10
0x140001c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001c51  add     rsp, 48h
0x140001c55  retn
```
