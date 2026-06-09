# FaxSetJobA

- ea: `0x180020dd0`
- end: `0x180020e87`
- name: `FaxSetJobA`
- size: `183`
- prototype: `BOOL __stdcall(HANDLE FaxHandle, DWORD JobId, DWORD Command, const FAX_JOB_ENTRYA *JobEntry)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180020dd0`
- `0x180020e90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180020e48`
- `KERNEL32!GetLastError` at `0x180020e48`

## pseudocode

```c
BOOL __stdcall FaxSetJobA(HANDLE FaxHandle, DWORD JobId, DWORD Command, const FAX_JOB_ENTRYA *JobEntry)
{
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
  }
  if ( FaxSetJobW(FaxHandle, JobId, Command, 0) )
    return 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x180020dd0  push    rbx
0x180020dd2  push    rsi
0x180020dd3  push    rdi
0x180020dd4  push    r14
0x180020dd6  sub     rsp, 28h
0x180020dda  mov     ebx, r8d
0x180020ddd  mov     edi, edx
0x180020ddf  mov     rsi, rcx
0x180020de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180020de9  lea     r14, WPP_GLOBAL_Control
0x180020df0  cmp     rcx, r14
0x180020df3  jz      short loc_180020E19
0x180020df5  test    dword ptr [rcx+1Ch], 1000h
0x180020dfc  jz      short loc_180020E19
0x180020dfe  cmp     byte ptr [rcx+19h], 5
0x180020e02  jb      short loc_180020E19
0x180020e04  mov     rcx, [rcx+10h]
0x180020e08  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180020e0f  mov     edx, 60h ; '`'
0x180020e14  call    WPP_SF_
0x180020e19  xor     r9d, r9d; JobEntry
0x180020e1c  mov     r8d, ebx; Command
0x180020e1f  mov     edx, edi; JobId
0x180020e21  mov     rcx, rsi; FaxHandle
0x180020e24  call    FaxSetJobW
0x180020e29  test    eax, eax
0x180020e2b  jnz     short loc_180020E77
0x180020e2d  mov     rax, cs:WPP_GLOBAL_Control
0x180020e34  cmp     rax, r14
0x180020e37  jz      short loc_180020E73
0x180020e39  test    dword ptr [rax+1Ch], 1000h
0x180020e40  jz      short loc_180020E73
0x180020e42  cmp     byte ptr [rax+19h], 2
0x180020e46  jb      short loc_180020E73
0x180020e48  call    cs:__imp_GetLastError
0x180020e4f  nop     dword ptr [rax+rax+00h]
0x180020e54  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e5b  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180020e62  mov     edx, 61h ; 'a'
0x180020e67  mov     r9d, eax
0x180020e6a  mov     rcx, [rcx+10h]
0x180020e6e  call    WPP_SF_d
0x180020e73  xor     eax, eax
0x180020e75  jmp     short loc_180020E7C
0x180020e77  mov     eax, 1
0x180020e7c  add     rsp, 28h
0x180020e80  pop     r14
0x180020e82  pop     rdi
0x180020e83  pop     rsi
0x180020e84  pop     rbx
0x180020e85  retn
```
