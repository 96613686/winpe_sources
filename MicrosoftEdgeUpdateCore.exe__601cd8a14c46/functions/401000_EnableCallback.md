# EnableCallback

- ea: `0x401000`
- end: `0x401079`
- name: `EnableCallback`
- size: `121`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, int Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x401000`
- `0x402330`

## pseudocode

```c
void __stdcall EnableCallback(
        LPCGUID SourceId,
        ULONG IsEnabled,
        int Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        _QWORD *CallbackContext)
{
  int v7; // ecx
  int v8; // ecx
  void (__thiscall *v9)(_DWORD, LPCGUID, ULONG, int, _DWORD, int, _DWORD, _DWORD, PEVENT_FILTER_DESCRIPTOR, _DWORD); // esi

  if ( CallbackContext )
  {
    if ( IsEnabled )
    {
      if ( IsEnabled == 1 )
      {
        if ( (_BYTE)Level )
          v7 = (unsigned __int8)Level + 1;
        else
          v7 = 256;
        *(_DWORD *)CallbackContext = v7;
        CallbackContext[1] = MatchAnyKeyword;
        v8 = HIDWORD(MatchAnyKeyword);
        CallbackContext[2] = MatchAllKeyword;
        goto LABEL_10;
      }
    }
    else
    {
      *(_DWORD *)CallbackContext = 0;
    }
    v8 = HIDWORD(MatchAnyKeyword);
LABEL_10:
    v9 = (void (__thiscall *)(_DWORD, LPCGUID, ULONG, int, _DWORD, int, _DWORD, _DWORD, PEVENT_FILTER_DESCRIPTOR, _DWORD))*((_DWORD *)CallbackContext + 8);
    if ( v9 )
      v9(
        v9,
        SourceId,
        IsEnabled,
        Level,
        MatchAnyKeyword,
        v8,
        MatchAllKeyword,
        HIDWORD(MatchAllKeyword),
        FilterData,
        *((_DWORD *)CallbackContext + 9));
  }
}

```

## disassembly

```asm
0x401000  push    ebp
0x401001  mov     ebp, esp
0x401003  mov     eax, [ebp+CallbackContext]
0x401006  test    eax, eax
0x401008  jz      short loc_401075
0x40100a  mov     ecx, [ebp+IsEnabled]
0x40100d  mov     edx, [ebp+Level]
0x401010  push    ebx
0x401011  mov     ebx, dword ptr [ebp+MatchAllKeyword]
0x401014  push    edi
0x401015  mov     edi, dword ptr [ebp+MatchAllKeyword+4]
0x401018  sub     ecx, 0
0x40101b  jz      short loc_401047
0x40101d  sub     ecx, 1
0x401020  jnz     short loc_40104A
0x401022  test    dl, dl
0x401024  jz      short loc_40102C
0x401026  movzx   ecx, dl
0x401029  inc     ecx
0x40102a  jmp     short loc_401031
0x40102c  mov     ecx, 100h
0x401031  mov     [eax], ecx
0x401033  mov     ecx, dword ptr [ebp+MatchAnyKeyword]
0x401036  mov     [eax+8], ecx
0x401039  mov     ecx, dword ptr [ebp+MatchAnyKeyword+4]
0x40103c  mov     [eax+0Ch], ecx
0x40103f  mov     [eax+10h], ebx
0x401042  mov     [eax+14h], edi
0x401045  jmp     short loc_40104D
0x401047  and     dword ptr [eax], 0
0x40104a  mov     ecx, dword ptr [ebp+MatchAnyKeyword+4]
0x40104d  push    esi
0x40104e  mov     esi, [eax+20h]
0x401051  test    esi, esi
0x401053  jz      short loc_401072
0x401055  push    dword ptr [eax+24h]
0x401058  push    [ebp+FilterData]
0x40105b  push    edi
0x40105c  push    ebx
0x40105d  push    ecx
0x40105e  push    dword ptr [ebp+MatchAnyKeyword]
0x401061  mov     ecx, esi
0x401063  push    edx
0x401064  push    [ebp+IsEnabled]
0x401067  push    [ebp+SourceId]
0x40106a  call    ds:___guard_check_icall_fptr
0x401070  call    esi
0x401072  pop     esi
0x401073  pop     edi
0x401074  pop     ebx
0x401075  pop     ebp
0x401076  retn    24h ; '$'
```
