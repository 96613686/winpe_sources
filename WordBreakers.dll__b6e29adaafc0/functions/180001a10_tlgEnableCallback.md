# _tlgEnableCallback

- ea: `0x180001a10`
- end: `0x180001a86`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001a10`
- `0x18000c010`

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
0x180001a10  sub     rsp, 48h
0x180001a14  mov     r11, rcx
0x180001a17  mov     rcx, [rsp+48h+CallbackContext]
0x180001a1f  test    rcx, rcx
0x180001a22  jz      short loc_180001A81
0x180001a24  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001a29  mov     eax, edx
0x180001a2b  test    edx, edx
0x180001a2d  jz      short loc_180001A52
0x180001a2f  cmp     eax, 1
0x180001a32  jnz     short loc_180001A58
0x180001a34  test    r8b, r8b
0x180001a37  jz      short loc_180001A41
0x180001a39  movzx   eax, r8b
0x180001a3d  inc     eax
0x180001a3f  jmp     short loc_180001A46
0x180001a41  mov     eax, 100h
0x180001a46  mov     [rcx], eax
0x180001a48  mov     [rcx+10h], r9
0x180001a4c  mov     [rcx+18h], r10
0x180001a50  jmp     short loc_180001A58
0x180001a52  mov     dword ptr [rcx], 0
0x180001a58  mov     rax, [rcx+28h]
0x180001a5c  test    rax, rax
0x180001a5f  jz      short loc_180001A81
0x180001a61  mov     rcx, [rcx+30h]
0x180001a65  mov     [rsp+48h+var_18], rcx
0x180001a6a  mov     rcx, [rsp+48h+FilterData]
0x180001a6f  mov     [rsp+48h+var_20], rcx
0x180001a74  mov     rcx, r11
0x180001a77  mov     [rsp+48h+var_28], r10
0x180001a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a81  add     rsp, 48h
0x180001a85  retn
```
