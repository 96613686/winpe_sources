# _tlgEnableCallback

- ea: `0x140001a10`
- end: `0x140001a86`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001a10`
- `0x140017010`

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
0x140001a10  sub     rsp, 48h
0x140001a14  mov     r11, rcx
0x140001a17  mov     rcx, [rsp+48h+CallbackContext]
0x140001a1f  test    rcx, rcx
0x140001a22  jz      short loc_140001A81
0x140001a24  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001a29  mov     eax, edx
0x140001a2b  test    edx, edx
0x140001a2d  jz      short loc_140001A52
0x140001a2f  cmp     eax, 1
0x140001a32  jnz     short loc_140001A58
0x140001a34  test    r8b, r8b
0x140001a37  jz      short loc_140001A41
0x140001a39  movzx   eax, r8b
0x140001a3d  inc     eax
0x140001a3f  jmp     short loc_140001A46
0x140001a41  mov     eax, 100h
0x140001a46  mov     [rcx], eax
0x140001a48  mov     [rcx+10h], r9
0x140001a4c  mov     [rcx+18h], r10
0x140001a50  jmp     short loc_140001A58
0x140001a52  mov     dword ptr [rcx], 0
0x140001a58  mov     rax, [rcx+28h]
0x140001a5c  test    rax, rax
0x140001a5f  jz      short loc_140001A81
0x140001a61  mov     rcx, [rcx+30h]
0x140001a65  mov     [rsp+48h+var_18], rcx
0x140001a6a  mov     rcx, [rsp+48h+FilterData]
0x140001a6f  mov     [rsp+48h+var_20], rcx
0x140001a74  mov     rcx, r11
0x140001a77  mov     [rsp+48h+var_28], r10
0x140001a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001a81  add     rsp, 48h
0x140001a85  retn
```
