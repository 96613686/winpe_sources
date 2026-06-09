# _tlgEnableCallback

- ea: `0x140002510`
- end: `0x140002586`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002510`
- `0x14000f010`

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
0x140002510  sub     rsp, 48h
0x140002514  mov     r11, rcx
0x140002517  mov     rcx, [rsp+48h+CallbackContext]
0x14000251f  test    rcx, rcx
0x140002522  jz      short loc_140002581
0x140002524  mov     r10, [rsp+48h+MatchAllKeyword]
0x140002529  mov     eax, edx
0x14000252b  test    edx, edx
0x14000252d  jz      short loc_140002552
0x14000252f  cmp     eax, 1
0x140002532  jnz     short loc_140002558
0x140002534  test    r8b, r8b
0x140002537  jz      short loc_140002541
0x140002539  movzx   eax, r8b
0x14000253d  inc     eax
0x14000253f  jmp     short loc_140002546
0x140002541  mov     eax, 100h
0x140002546  mov     [rcx], eax
0x140002548  mov     [rcx+10h], r9
0x14000254c  mov     [rcx+18h], r10
0x140002550  jmp     short loc_140002558
0x140002552  mov     dword ptr [rcx], 0
0x140002558  mov     rax, [rcx+28h]
0x14000255c  test    rax, rax
0x14000255f  jz      short loc_140002581
0x140002561  mov     rcx, [rcx+30h]
0x140002565  mov     [rsp+48h+var_18], rcx
0x14000256a  mov     rcx, [rsp+48h+FilterData]
0x14000256f  mov     [rsp+48h+var_20], rcx
0x140002574  mov     rcx, r11
0x140002577  mov     [rsp+48h+var_28], r10
0x14000257c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002581  add     rsp, 48h
0x140002585  retn
```
