# RPC_FAX_HANDLE_rundown

- ea: `0x18000aa00`
- end: `0x18000abdc`
- name: `RPC_FAX_HANDLE_rundown`
- size: `476`
- prototype: `__int64 __fastcall(struct _ASYNC_EVENT_INFO *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180004c3c`
- `0x180006308`
- `0x180008fd0`
- `0x18000aa00`
- `0x18000abe4`
- `0x18000ac14`
- `0x18002bb58`
- `0x18003d4ca`

## import_xrefs

- `KERNEL32!PostQueuedCompletionStatus` at `0x18000ab1a`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18000ab1a`
- `KERNEL32!LocalFree` at `0x18000ab6c`
- `KERNEL32!LocalFree` at `0x18000ab6c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000aaef`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000aaef`
- `KERNEL32!LocalAlloc` at `0x18000aacd`
- `KERNEL32!LocalAlloc` at `0x18000aacd`
- `KERNEL32!EnterCriticalSection` at `0x18000aa51`
- `KERNEL32!EnterCriticalSection` at `0x18000aa51`
- `KERNEL32!GetLastError` at `0x18000ab2a`
- `KERNEL32!GetLastError` at `0x18000ab2a`
- `KERNEL32!LeaveCriticalSection` at `0x18000abd0`
- `USER32!PostMessageW` at `0x18000ab8f`
- `USER32!PostMessageW` at `0x18000ab8f`

## pseudocode

```c
void __fastcall RPC_FAX_HANDLE_rundown(struct _ASYNC_EVENT_INFO *a1)
{
  struct _LIST_ENTRY *v2; // rcx
  char *v3; // rax
  char *v4; // rdi
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_152912f6797533292abcfca723f93957_Traceguids);
  }
  EnterCriticalSection(&g_CsFaxAssyncInfo);
  if ( ValidAsyncInfoSignature((const wchar_t *)a1) )
  {
    if ( *((_DWORD *)a1 + 13) == 1 )
    {
      PostRundownEventEx(a1);
LABEL_22:
      FindAndRemoveContext(v2, a1);
      memset_0(a1, 0, 0x58u);
      pMemFree(a1);
      goto LABEL_23;
    }
    if ( *((_QWORD *)a1 + 3) )
    {
      v3 = (char *)LocalAlloc(0, 0x20u);
      v4 = v3;
      if ( !v3 )
        goto LABEL_22;
      *(_DWORD *)v3 = 88;
      GetSystemTimeAsFileTime((LPFILETIME)(v3 + 4));
      *((_DWORD *)v4 + 3) = 0;
      *((_QWORD *)v4 + 2) = 20;
      if ( !PostQueuedCompletionStatus(*((HANDLE *)a1 + 3), 0x18u, *((_QWORD *)a1 + 4), (LPOVERLAPPED)v4) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_152912f6797533292abcfca723f93957_Traceguids, LastError);
        }
        LocalFree(v4);
        goto LABEL_22;
      }
    }
    v2 = (struct _LIST_ENTRY *)*((_QWORD *)a1 + 5);
    if ( v2 )
      PostMessageW((HWND)v2, *((_DWORD *)a1 + 12) + 20, 0, 0);
    goto LABEL_22;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_152912f6797533292abcfca723f93957_Traceguids);
  }
LABEL_23:
  LeaveCriticalSection(&g_CsFaxAssyncInfo);
}

```

## disassembly

```asm
0x18000aa00  mov     [rsp+arg_0], rbx
0x18000aa05  mov     [rsp+arg_8], rdi
0x18000aa0a  push    r14
0x18000aa0c  sub     rsp, 20h
0x18000aa10  mov     rbx, rcx
0x18000aa13  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa1a  lea     r14, WPP_GLOBAL_Control
0x18000aa21  cmp     rcx, r14
0x18000aa24  jz      short loc_18000AA4A
0x18000aa26  test    dword ptr [rcx+1Ch], 1000h
0x18000aa2d  jz      short loc_18000AA4A
0x18000aa2f  cmp     byte ptr [rcx+19h], 5
0x18000aa33  jb      short loc_18000AA4A
0x18000aa35  mov     rcx, [rcx+10h]
0x18000aa39  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x18000aa40  mov     edx, 3Dh ; '='
0x18000aa45  call    WPP_SF_
0x18000aa4a  lea     rcx, ?g_CsFaxAssyncInfo@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000aa51  call    cs:__imp_EnterCriticalSection
0x18000aa58  nop     dword ptr [rax+rax+00h]
0x18000aa5d  mov     rcx, rbx; struct _ASYNC_EVENT_INFO *
0x18000aa60  call    ?ValidAsyncInfoSignature@@YAHPEAU_ASYNC_EVENT_INFO@@@Z; ValidAsyncInfoSignature(_ASYNC_EVENT_INFO *)
0x18000aa65  test    eax, eax
0x18000aa67  jnz     short loc_18000AAA8
0x18000aa69  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa70  cmp     rcx, r14
0x18000aa73  jz      loc_18000ABB9
0x18000aa79  test    dword ptr [rcx+1Ch], 1000h
0x18000aa80  jz      loc_18000ABB9
0x18000aa86  cmp     byte ptr [rcx+19h], 2
0x18000aa8a  jb      loc_18000ABB9
0x18000aa90  mov     rcx, [rcx+10h]
0x18000aa94  lea     edx, [rax+3Eh]
0x18000aa97  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x18000aa9e  call    WPP_SF_
0x18000aaa3  jmp     loc_18000ABB9
0x18000aaa8  cmp     dword ptr [rbx+34h], 1
0x18000aaac  jnz     short loc_18000AABB
0x18000aaae  mov     rcx, rbx; struct _ASYNC_EVENT_INFO *
0x18000aab1  call    ?PostRundownEventEx@@YAXPEAU_ASYNC_EVENT_INFO@@@Z; PostRundownEventEx(_ASYNC_EVENT_INFO *)
0x18000aab6  jmp     loc_18000AB9B
0x18000aabb  cmp     qword ptr [rbx+18h], 0
0x18000aac0  jz      loc_18000AB7A
0x18000aac6  mov     edx, 20h ; ' '; uBytes
0x18000aacb  xor     ecx, ecx; uFlags
0x18000aacd  call    cs:__imp_LocalAlloc
0x18000aad4  nop     dword ptr [rax+rax+00h]
0x18000aad9  mov     rdi, rax
0x18000aadc  test    rax, rax
0x18000aadf  jz      loc_18000AB9B
0x18000aae5  lea     rcx, [rax+4]; lpSystemTimeAsFileTime
0x18000aae9  mov     dword ptr [rax], 58h ; 'X'
0x18000aaef  call    cs:__imp_GetSystemTimeAsFileTime
0x18000aaf6  nop     dword ptr [rax+rax+00h]
0x18000aafb  mov     dword ptr [rdi+0Ch], 0
0x18000ab02  mov     r9, rdi; lpOverlapped
0x18000ab05  mov     qword ptr [rdi+10h], 14h
0x18000ab0d  mov     edx, 18h; dwNumberOfBytesTransferred
0x18000ab12  mov     r8, [rbx+20h]; dwCompletionKey
0x18000ab16  mov     rcx, [rbx+18h]; CompletionPort
0x18000ab1a  call    cs:__imp_PostQueuedCompletionStatus
0x18000ab21  nop     dword ptr [rax+rax+00h]
0x18000ab26  test    eax, eax
0x18000ab28  jnz     short loc_18000AB7A
0x18000ab2a  call    cs:__imp_GetLastError
0x18000ab31  nop     dword ptr [rax+rax+00h]
0x18000ab36  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab3d  cmp     rcx, r14
0x18000ab40  jz      short loc_18000AB69
0x18000ab42  test    dword ptr [rcx+1Ch], 1000h
0x18000ab49  jz      short loc_18000AB69
0x18000ab4b  cmp     byte ptr [rcx+19h], 2
0x18000ab4f  jb      short loc_18000AB69
0x18000ab51  mov     rcx, [rcx+10h]
0x18000ab55  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x18000ab5c  mov     edx, 3Fh ; '?'
0x18000ab61  mov     r9d, eax
0x18000ab64  call    WPP_SF_d
0x18000ab69  mov     rcx, rdi; hMem
0x18000ab6c  call    cs:__imp_LocalFree
0x18000ab73  nop     dword ptr [rax+rax+00h]
0x18000ab78  jmp     short loc_18000AB9B
0x18000ab7a  mov     rcx, [rbx+28h]; hWnd
0x18000ab7e  test    rcx, rcx
0x18000ab81  jz      short loc_18000AB9B
0x18000ab83  mov     edx, [rbx+30h]
0x18000ab86  xor     r9d, r9d; lParam
0x18000ab89  add     edx, 14h; Msg
0x18000ab8c  xor     r8d, r8d; wParam
0x18000ab8f  call    cs:__imp_PostMessageW
0x18000ab96  nop     dword ptr [rax+rax+00h]
0x18000ab9b  mov     rdx, rbx; struct _ASYNC_EVENT_INFO *
0x18000ab9e  call    ?FindAndRemoveContext@@YAXPEAU_LIST_ENTRY@@PEAU_ASYNC_EVENT_INFO@@@Z; FindAndRemoveContext(_LIST_ENTRY *,_ASYNC_EVENT_INFO *)
0x18000aba3  xor     edx, edx; Val
0x18000aba5  mov     rcx, rbx; void *
0x18000aba8  lea     r8d, [rdx+58h]; Size
0x18000abac  call    memset_0
0x18000abb1  mov     rcx, rbx; lpMem
0x18000abb4  call    pMemFree
0x18000abb9  lea     rcx, ?g_CsFaxAssyncInfo@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CsFaxAssyncInfo
0x18000abc0  mov     rbx, [rsp+28h+arg_0]
0x18000abc5  mov     rdi, [rsp+28h+arg_8]
0x18000abca  add     rsp, 20h
0x18000abce  pop     r14
0x18000abd0  jmp     cs:__imp_LeaveCriticalSection
```
