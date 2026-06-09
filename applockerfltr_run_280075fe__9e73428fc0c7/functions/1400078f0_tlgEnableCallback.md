# _tlgEnableCallback

- ea: `0x1400078f0`
- end: `0x140007967`
- name: `_tlgEnableCallback`
- size: `119`
- prototype: `ETWENABLECALLBACK`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001860`
- `0x1400078f0`

## pseudocode

```c
void __fastcall tlgEnableCallback(
        LPCGUID SourceId,
        __int64 ControlCode,
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
    if ( (_DWORD)ControlCode )
    {
      if ( (_DWORD)ControlCode == 1 )
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
      v8(SourceId, ControlCode, Level, MatchAnyKeyword, MatchAllKeyword, FilterData, CallbackContext[6]);
  }
}

```

## disassembly

```asm
0x1400078f0  sub     rsp, 48h
0x1400078f4  mov     r11, rcx
0x1400078f7  mov     rcx, [rsp+48h+CallbackContext]
0x1400078ff  test    rcx, rcx
0x140007902  jz      short loc_140007961
0x140007904  mov     r10, [rsp+48h+MatchAllKeyword]
0x140007909  mov     eax, edx
0x14000790b  test    edx, edx
0x14000790d  jz      short loc_140007932
0x14000790f  cmp     eax, 1
0x140007912  jnz     short loc_140007938
0x140007914  test    r8b, r8b
0x140007917  jz      short loc_140007921
0x140007919  movzx   eax, r8b
0x14000791d  inc     eax
0x14000791f  jmp     short loc_140007926
0x140007921  mov     eax, 100h
0x140007926  mov     [rcx], eax
0x140007928  mov     [rcx+10h], r9
0x14000792c  mov     [rcx+18h], r10
0x140007930  jmp     short loc_140007938
0x140007932  mov     dword ptr [rcx], 0
0x140007938  mov     rax, [rcx+28h]
0x14000793c  test    rax, rax
0x14000793f  jz      short loc_140007961
0x140007941  mov     rcx, [rcx+30h]
0x140007945  mov     [rsp+48h+var_18], rcx
0x14000794a  mov     rcx, [rsp+48h+FilterData]
0x14000794f  mov     [rsp+48h+var_20], rcx
0x140007954  mov     rcx, r11
0x140007957  mov     [rsp+48h+var_28], r10
0x14000795c  call    _guard_dispatch_icall
0x140007961  add     rsp, 48h
0x140007965  retn
```
