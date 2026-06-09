# DispatchEvent(_ASYNC_EVENT_INFO const *,uchar * const,ulong)

- ea: `0x180003ffc`
- end: `0x180004106`
- name: `?DispatchEvent@@YAKPEBU_ASYNC_EVENT_INFO@@QEAEK@Z`
- size: `266`
- prototype: `__int64 __fastcall(const struct _ASYNC_EVENT_INFO *, struct _OVERLAPPED *, DWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006308`
- `0x180009dd0`

## callees

- `0x180003ffc`
- `0x18000abe4`
- `0x18000ac14`

## import_xrefs

- `KERNEL32!PostQueuedCompletionStatus` at `0x180004059`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180004059`
- `KERNEL32!GetLastError` at `0x18000406d`
- `KERNEL32!GetLastError` at `0x1800040b7`
- `KERNEL32!GetLastError` at `0x18000406d`
- `KERNEL32!GetLastError` at `0x1800040b7`
- `USER32!PostMessageW` at `0x1800040a7`
- `USER32!PostMessageW` at `0x1800040a7`

## pseudocode

```c
__int64 __fastcall DispatchEvent(const struct _ASYNC_EVENT_INFO *a1, struct _OVERLAPPED *a2, DWORD a3)
{
  DWORD v6; // ebx
  void *v7; // rcx
  DWORD LastError; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx

  v6 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_152912f6797533292abcfca723f93957_Traceguids);
  }
  v7 = (void *)*((_QWORD *)a1 + 3);
  if ( v7 )
  {
    if ( !PostQueuedCompletionStatus(v7, a3, *((_QWORD *)a1 + 4), a2) )
    {
      LastError = GetLastError();
      v6 = LastError;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 55;
LABEL_16:
        WPP_SF_d(v9[2], v10, &WPP_152912f6797533292abcfca723f93957_Traceguids, LastError);
      }
    }
  }
  else if ( !PostMessageW(*((HWND *)a1 + 5), *((_DWORD *)a1 + 12), 0, (LPARAM)a2) )
  {
    LastError = GetLastError();
    v6 = LastError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 56;
      goto LABEL_16;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180003ffc  push    rbx
0x180003ffe  push    rbp
0x180003fff  push    rsi
0x180004000  push    rdi
0x180004001  push    r15
0x180004003  sub     rsp, 20h
0x180004007  mov     ebp, r8d
0x18000400a  mov     rsi, rdx
0x18000400d  mov     rdi, rcx
0x180004010  xor     ebx, ebx
0x180004012  mov     rcx, cs:WPP_GLOBAL_Control
0x180004019  lea     r15, WPP_GLOBAL_Control
0x180004020  cmp     rcx, r15
0x180004023  jz      short loc_180004047
0x180004025  test    dword ptr [rcx+1Ch], 1000h
0x18000402c  jz      short loc_180004047
0x18000402e  cmp     byte ptr [rcx+19h], 5
0x180004032  jb      short loc_180004047
0x180004034  mov     rcx, [rcx+10h]
0x180004038  lea     edx, [rbx+36h]
0x18000403b  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x180004042  call    WPP_SF_
0x180004047  mov     rcx, [rdi+18h]; CompletionPort
0x18000404b  mov     r9, rsi; lParam
0x18000404e  test    rcx, rcx
0x180004051  jz      short loc_18000409D
0x180004053  mov     r8, [rdi+20h]; dwCompletionKey
0x180004057  mov     edx, ebp; dwNumberOfBytesTransferred
0x180004059  call    cs:__imp_PostQueuedCompletionStatus
0x180004060  nop     dword ptr [rax+rax+00h]
0x180004065  test    eax, eax
0x180004067  jnz     loc_1800040F8
0x18000406d  call    cs:__imp_GetLastError
0x180004074  nop     dword ptr [rax+rax+00h]
0x180004079  mov     ebx, eax
0x18000407b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004082  cmp     rcx, r15
0x180004085  jz      short loc_1800040F8
0x180004087  test    dword ptr [rcx+1Ch], 1000h
0x18000408e  jz      short loc_1800040F8
0x180004090  cmp     byte ptr [rcx+19h], 2
0x180004094  jb      short loc_1800040F8
0x180004096  mov     edx, 37h ; '7'
0x18000409b  jmp     short loc_1800040E5
0x18000409d  mov     edx, [rdi+30h]; Msg
0x1800040a0  xor     r8d, r8d; wParam
0x1800040a3  mov     rcx, [rdi+28h]; hWnd
0x1800040a7  call    cs:__imp_PostMessageW
0x1800040ae  nop     dword ptr [rax+rax+00h]
0x1800040b3  test    eax, eax
0x1800040b5  jnz     short loc_1800040F8
0x1800040b7  call    cs:__imp_GetLastError
0x1800040be  nop     dword ptr [rax+rax+00h]
0x1800040c3  mov     ebx, eax
0x1800040c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040cc  cmp     rcx, r15
0x1800040cf  jz      short loc_1800040F8
0x1800040d1  test    dword ptr [rcx+1Ch], 1000h
0x1800040d8  jz      short loc_1800040F8
0x1800040da  cmp     byte ptr [rcx+19h], 2
0x1800040de  jb      short loc_1800040F8
0x1800040e0  mov     edx, 38h ; '8'
0x1800040e5  mov     rcx, [rcx+10h]
0x1800040e9  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x1800040f0  mov     r9d, eax
0x1800040f3  call    WPP_SF_d
0x1800040f8  mov     eax, ebx
0x1800040fa  add     rsp, 20h
0x1800040fe  pop     r15
0x180004100  pop     rdi
0x180004101  pop     rsi
0x180004102  pop     rbp
0x180004103  pop     rbx
0x180004104  retn
```
