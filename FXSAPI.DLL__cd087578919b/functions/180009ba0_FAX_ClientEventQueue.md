# FAX_ClientEventQueue

- ea: `0x180009ba0`
- end: `0x180009dc6`
- name: `FAX_ClientEventQueue`
- size: `550`
- prototype: `__int64 __fastcall(struct _ASYNC_EVENT_INFO *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180008fd0`
- `0x180009ba0`
- `0x18000abe4`
- `0x18000ac14`
- `0x18002d0e4`
- `0x18003358c`

## import_xrefs

- `KERNEL32!PostQueuedCompletionStatus` at `0x180009d22`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180009d22`
- `KERNEL32!LocalFree` at `0x180009d51`
- `KERNEL32!LocalFree` at `0x180009d51`
- `KERNEL32!LocalAlloc` at `0x180009ce5`
- `KERNEL32!LocalAlloc` at `0x180009ce5`
- `KERNEL32!EnterCriticalSection` at `0x180009bf7`
- `KERNEL32!EnterCriticalSection` at `0x180009bf7`
- `KERNEL32!GetLastError` at `0x180009d32`
- `KERNEL32!GetLastError` at `0x180009d81`
- `KERNEL32!GetLastError` at `0x180009d32`
- `KERNEL32!GetLastError` at `0x180009d81`
- `KERNEL32!LeaveCriticalSection` at `0x180009da4`
- `KERNEL32!LeaveCriticalSection` at `0x180009da4`
- `USER32!PostMessageW` at `0x180009d71`
- `USER32!PostMessageW` at `0x180009d71`

## string_xrefs

- `0x180009d40`: `PostQueuedCompletionStatus failed, ec = %d\n`

## pseudocode

```c
__int64 __fastcall FAX_ClientEventQueue(struct _ASYNC_EVENT_INFO *a1, __int64 a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 LastError; // rbx
  unsigned int v7; // eax
  struct _OVERLAPPED *v8; // rax
  struct _OVERLAPPED *v9; // rsi
  void *v10; // xmm1_8

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_152912f6797533292abcfca723f93957_Traceguids);
  }
  EnterCriticalSection(&g_CsFaxAssyncInfo);
  if ( !(unsigned int)ValidAsyncInfoSignature(a1) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v5 = 51;
LABEL_10:
    WPP_SF_(v4[2], v5, &WPP_152912f6797533292abcfca723f93957_Traceguids);
LABEL_11:
    LODWORD(LastError) = 0;
    goto LABEL_29;
  }
  LODWORD(LastError) = 0;
  if ( *((_DWORD *)a1 + 14) )
  {
    v7 = IsLocalRPCConnectionIpTcp(*((RPC_BINDING_HANDLE *)a1 + 8));
    LODWORD(LastError) = v7;
    if ( !v7 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_11;
      }
      v5 = 53;
      goto LABEL_10;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_152912f6797533292abcfca723f93957_Traceguids, v7);
    }
  }
  else if ( *((_QWORD *)a1 + 3) )
  {
    v8 = (struct _OVERLAPPED *)LocalAlloc(0, 0x20u);
    v9 = v8;
    if ( v8 )
    {
      v10 = *(void **)(a2 + 16);
      *(_OWORD *)&v8->Internal = *(_OWORD *)a2;
      v8->Pointer = v10;
      if ( !PostQueuedCompletionStatus(*((HANDLE *)a1 + 3), 0x18u, *((_QWORD *)a1 + 4), v8) )
      {
        LastError = GetLastError();
        fax_dprintf(L"PostQueuedCompletionStatus failed, ec = %d\n", LastError);
        LocalFree(v9);
      }
    }
    else
    {
      LODWORD(LastError) = 8;
    }
  }
  else if ( !PostMessageW(
               *((HWND *)a1 + 5),
               *(_DWORD *)(a2 + 16) + *((_DWORD *)a1 + 12),
               *(unsigned int *)(a2 + 12),
               *(unsigned int *)(a2 + 20)) )
  {
    LastError = GetLastError();
    fax_dprintf(L"PostMessage failed, ec = %d\n", LastError);
  }
LABEL_29:
  LeaveCriticalSection(&g_CsFaxAssyncInfo);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180009ba0  mov     [rsp+arg_8], rbx
0x180009ba5  mov     [rsp+arg_10], rbp
0x180009baa  push    rsi
0x180009bab  push    rdi
0x180009bac  push    r15
0x180009bae  sub     rsp, 20h
0x180009bb2  mov     rbp, rdx
0x180009bb5  mov     rdi, rcx
0x180009bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bbf  lea     r15, WPP_GLOBAL_Control
0x180009bc6  mov     esi, 1000h
0x180009bcb  cmp     rcx, r15
0x180009bce  jz      short loc_180009BF0
0x180009bd0  test    [rcx+1Ch], esi
0x180009bd3  jz      short loc_180009BF0
0x180009bd5  cmp     byte ptr [rcx+19h], 5
0x180009bd9  jb      short loc_180009BF0
0x180009bdb  mov     rcx, [rcx+10h]
0x180009bdf  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x180009be6  mov     edx, 32h ; '2'
0x180009beb  call    WPP_SF_
0x180009bf0  lea     rcx, ?g_CsFaxAssyncInfo@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180009bf7  call    cs:__imp_EnterCriticalSection
0x180009bfe  nop     dword ptr [rax+rax+00h]
0x180009c03  mov     rcx, rdi; struct _ASYNC_EVENT_INFO *
0x180009c06  call    ?ValidAsyncInfoSignature@@YAHPEAU_ASYNC_EVENT_INFO@@@Z; ValidAsyncInfoSignature(_ASYNC_EVENT_INFO *)
0x180009c0b  test    eax, eax
0x180009c0d  jnz     short loc_180009C40
0x180009c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c16  cmp     rcx, r15
0x180009c19  jz      short loc_180009C39
0x180009c1b  test    [rcx+1Ch], esi
0x180009c1e  jz      short loc_180009C39
0x180009c20  cmp     byte ptr [rcx+19h], 2
0x180009c24  jb      short loc_180009C39
0x180009c26  lea     edx, [rax+33h]
0x180009c29  mov     rcx, [rcx+10h]
0x180009c2d  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x180009c34  call    WPP_SF_
0x180009c39  xor     ebx, ebx
0x180009c3b  jmp     loc_180009D9D
0x180009c40  xor     ebx, ebx
0x180009c42  cmp     [rdi+38h], ebx
0x180009c45  jz      loc_180009CD3
0x180009c4b  mov     rcx, [rdi+40h]; ClientBinding
0x180009c4f  lea     rdx, [rsp+38h+arg_0]
0x180009c54  mov     [rsp+38h+arg_0], ebx
0x180009c58  call    IsLocalRPCConnectionIpTcp
0x180009c5d  mov     ebx, eax
0x180009c5f  test    eax, eax
0x180009c61  jz      short loc_180009CA3
0x180009c63  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c6a  cmp     rcx, r15
0x180009c6d  jz      loc_180009D9D
0x180009c73  test    [rcx+1Ch], esi
0x180009c76  jz      loc_180009D9D
0x180009c7c  cmp     byte ptr [rcx+19h], 2
0x180009c80  jb      loc_180009D9D
0x180009c86  mov     rcx, [rcx+10h]
0x180009c8a  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x180009c91  mov     edx, 34h ; '4'
0x180009c96  mov     r9d, eax
0x180009c99  call    WPP_SF_d
0x180009c9e  jmp     loc_180009D9D
0x180009ca3  cmp     [rsp+38h+arg_0], 0
0x180009ca8  jnz     short loc_180009CD3
0x180009caa  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cb1  cmp     rcx, r15
0x180009cb4  jz      short loc_180009C39
0x180009cb6  test    [rcx+1Ch], esi
0x180009cb9  jz      loc_180009C39
0x180009cbf  cmp     byte ptr [rcx+19h], 2
0x180009cc3  jb      loc_180009C39
0x180009cc9  mov     edx, 35h ; '5'
0x180009cce  jmp     loc_180009C29
0x180009cd3  cmp     qword ptr [rdi+18h], 0
0x180009cd8  jz      loc_180009D5F
0x180009cde  mov     edx, 20h ; ' '; uBytes
0x180009ce3  xor     ecx, ecx; uFlags
0x180009ce5  call    cs:__imp_LocalAlloc
0x180009cec  nop     dword ptr [rax+rax+00h]
0x180009cf1  mov     rsi, rax
0x180009cf4  test    rax, rax
0x180009cf7  jnz     short loc_180009D01
0x180009cf9  lea     ebx, [rax+8]
0x180009cfc  jmp     loc_180009D9D
0x180009d01  movups  xmm0, xmmword ptr [rbp+0]
0x180009d05  mov     r9, rsi; lpOverlapped
0x180009d08  mov     edx, 18h; dwNumberOfBytesTransferred
0x180009d0d  movsd   xmm1, qword ptr [rbp+10h]
0x180009d12  movups  xmmword ptr [rax], xmm0
0x180009d15  movsd   qword ptr [rax+10h], xmm1
0x180009d1a  mov     r8, [rdi+20h]; dwCompletionKey
0x180009d1e  mov     rcx, [rdi+18h]; CompletionPort
0x180009d22  call    cs:__imp_PostQueuedCompletionStatus
0x180009d29  nop     dword ptr [rax+rax+00h]
0x180009d2e  test    eax, eax
0x180009d30  jnz     short loc_180009D9D
0x180009d32  call    cs:__imp_GetLastError
0x180009d39  nop     dword ptr [rax+rax+00h]
0x180009d3e  mov     edx, eax
0x180009d40  lea     rcx, aPostqueuedcomp; "PostQueuedCompletionStatus failed, ec ="...
0x180009d47  mov     ebx, eax
0x180009d49  call    fax_dprintf
0x180009d4e  mov     rcx, rsi; hMem
0x180009d51  call    cs:__imp_LocalFree
0x180009d58  nop     dword ptr [rax+rax+00h]
0x180009d5d  jmp     short loc_180009D9D
0x180009d5f  mov     edx, [rdi+30h]
0x180009d62  add     edx, [rbp+10h]; Msg
0x180009d65  mov     r9d, [rbp+14h]; lParam
0x180009d69  mov     r8d, [rbp+0Ch]; wParam
0x180009d6d  mov     rcx, [rdi+28h]; hWnd
0x180009d71  call    cs:__imp_PostMessageW
0x180009d78  nop     dword ptr [rax+rax+00h]
0x180009d7d  test    eax, eax
0x180009d7f  jnz     short loc_180009D9D
0x180009d81  call    cs:__imp_GetLastError
0x180009d88  nop     dword ptr [rax+rax+00h]
0x180009d8d  mov     edx, eax
0x180009d8f  lea     rcx, aPostmessageFai; "PostMessage failed, ec = %d\n"
0x180009d96  mov     ebx, eax
0x180009d98  call    fax_dprintf
0x180009d9d  lea     rcx, ?g_CsFaxAssyncInfo@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180009da4  call    cs:__imp_LeaveCriticalSection
0x180009dab  nop     dword ptr [rax+rax+00h]
0x180009db0  mov     rbp, [rsp+38h+arg_10]
0x180009db5  mov     eax, ebx
0x180009db7  mov     rbx, [rsp+38h+arg_8]
0x180009dbc  add     rsp, 20h
0x180009dc0  pop     r15
0x180009dc2  pop     rdi
0x180009dc3  pop     rsi
0x180009dc4  retn
```
