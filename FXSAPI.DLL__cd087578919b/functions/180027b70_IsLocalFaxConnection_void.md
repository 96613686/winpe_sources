# IsLocalFaxConnection(void *)

- ea: `0x180027b70`
- end: `0x180027c15`
- name: `?IsLocalFaxConnection@@YAHPEAX@Z`
- size: `165`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bd30`
- `0x180011470`
- `0x18001ad28`
- `0x180028ef0`
- `0x180029e10`

## callees

- `0x18000abe4`
- `0x180027b70`
- `0x18002c1e0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180027bec`
- `KERNEL32!SetLastError` at `0x180027bec`

## pseudocode

```c
_BOOL8 __fastcall IsLocalFaxConnection(_QWORD *a1)
{
  _UNKNOWN **v2; // rcx

  v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xEu, (const GUID *)WPP_a4158162aa603b3b4cac811f54679e94_Traceguids);
    v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( a1 )
    return IsLocalMachineNameW(*(wchar_t **)(a1[4] + 72LL));
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x1000) != 0 && *((_BYTE *)v2 + 25) >= 2u )
    WPP_SF_((TRACEHANDLE)v2[2], 0xFu, (const GUID *)WPP_a4158162aa603b3b4cac811f54679e94_Traceguids);
  SetLastError(6u);
  return 0;
}

```

## disassembly

```asm
0x180027b70  mov     [rsp+arg_0], rbx
0x180027b75  push    rsi
0x180027b76  sub     rsp, 20h
0x180027b7a  mov     rbx, rcx
0x180027b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b84  lea     rsi, WPP_GLOBAL_Control
0x180027b8b  cmp     rcx, rsi
0x180027b8e  jz      short loc_180027BBB
0x180027b90  test    dword ptr [rcx+1Ch], 1000h
0x180027b97  jz      short loc_180027BBB
0x180027b99  cmp     byte ptr [rcx+19h], 5
0x180027b9d  jb      short loc_180027BBB
0x180027b9f  mov     rcx, [rcx+10h]
0x180027ba3  lea     r8, WPP_a4158162aa603b3b4cac811f54679e94_Traceguids
0x180027baa  mov     edx, 0Eh
0x180027baf  call    WPP_SF_
0x180027bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180027bbb  test    rbx, rbx
0x180027bbe  jnz     short loc_180027BFC
0x180027bc0  cmp     rcx, rsi
0x180027bc3  jz      short loc_180027BE7
0x180027bc5  test    dword ptr [rcx+1Ch], 1000h
0x180027bcc  jz      short loc_180027BE7
0x180027bce  cmp     byte ptr [rcx+19h], 2
0x180027bd2  jb      short loc_180027BE7
0x180027bd4  mov     rcx, [rcx+10h]
0x180027bd8  lea     edx, [rbx+0Fh]
0x180027bdb  lea     r8, WPP_a4158162aa603b3b4cac811f54679e94_Traceguids
0x180027be2  call    WPP_SF_
0x180027be7  mov     ecx, 6; dwErrCode
0x180027bec  call    cs:__imp_SetLastError
0x180027bf3  nop     dword ptr [rax+rax+00h]
0x180027bf8  xor     eax, eax
0x180027bfa  jmp     short loc_180027C09
0x180027bfc  mov     rcx, [rbx+20h]
0x180027c00  mov     rcx, [rcx+48h]; String2
0x180027c04  call    IsLocalMachineNameW
0x180027c09  mov     rbx, [rsp+28h+arg_0]
0x180027c0e  add     rsp, 20h
0x180027c12  pop     rsi
0x180027c13  retn
```
