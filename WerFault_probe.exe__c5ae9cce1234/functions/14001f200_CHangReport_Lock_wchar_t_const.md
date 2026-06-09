# CHangReport::Lock(wchar_t const *)

- ea: `0x14001f200`
- end: `0x14001f292`
- name: `?Lock@CHangReport@@IEAA?AV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEB_W@Z`
- size: `146`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x14001d800`
- `0x14001dd84`
- `0x14001f870`
- `0x14001fb18`
- `0x14001ff40`
- `0x140022b50`
- `0x140023560`
- `0x1400243b0`

## callees

- `0x140014678`
- `0x14001f200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001f273`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001f273`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x14001f220`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x14001f220`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001f27d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001f27d`

## pseudocode

```c
__int64 __fastcall CHangReport::Lock(__int64 a1, __int64 a2, int a3)
{
  _BYTE *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rcx

  v4 = (_BYTE *)(a2 + 8);
  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  *(_BYTE *)(a2 + 8) = 0;
  *(_QWORD *)a2 = v5;
  if ( !TryEnterCriticalSection(v5) )
  {
    *v4 = 0;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        (unsigned int)&WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
        a3,
        *(_DWORD *)(a1 + 56));
    }
    if ( !*(_QWORD *)a2 || *v4 )
      __int2c();
    EnterCriticalSection(*(LPCRITICAL_SECTION *)a2);
  }
  *v4 = 1;
  *(_DWORD *)(a1 + 56) = GetCurrentThreadId();
  return a2;
}

```

## disassembly

```asm
0x14001f200  push    rbx
0x14001f202  push    rbp
0x14001f203  push    rsi
0x14001f204  push    rdi
0x14001f205  sub     rsp, 38h
0x14001f209  mov     rsi, rcx
0x14001f20c  lea     rbx, [rdx+8]
0x14001f210  add     rcx, 10h; lpCriticalSection
0x14001f214  mov     byte ptr [rbx], 0
0x14001f217  mov     [rdx], rcx
0x14001f21a  mov     rbp, r8
0x14001f21d  mov     rdi, rdx
0x14001f220  call    cs:__imp_TryEnterCriticalSection
0x14001f226  test    eax, eax
0x14001f228  jnz     short loc_14001F279
0x14001f22a  mov     [rbx], al
0x14001f22c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f233  lea     rax, WPP_GLOBAL_Control
0x14001f23a  cmp     rcx, rax
0x14001f23d  jz      short loc_14001F264
0x14001f23f  test    byte ptr [rcx+1Ch], 4
0x14001f243  jz      short loc_14001F264
0x14001f245  mov     eax, [rsi+38h]
0x14001f248  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x14001f24f  mov     rcx, [rcx+10h]
0x14001f253  mov     edx, 4Fh ; 'O'
0x14001f258  mov     r9, rbp
0x14001f25b  mov     [rsp+58h+var_38], eax
0x14001f25f  call    WPP_SF_Sd
0x14001f264  mov     rcx, [rdi]; lpCriticalSection
0x14001f267  test    rcx, rcx
0x14001f26a  jz      short loc_14001F271
0x14001f26c  cmp     byte ptr [rbx], 0
0x14001f26f  jz      short loc_14001F273
0x14001f271  int     2Ch; Windows NT - assertion failure
0x14001f273  call    cs:__imp_EnterCriticalSection
0x14001f279  mov     al, 1
0x14001f27b  mov     [rbx], al
0x14001f27d  call    cs:__imp_GetCurrentThreadId
0x14001f283  mov     [rsi+38h], eax
0x14001f286  mov     rax, rdi
0x14001f289  add     rsp, 38h
0x14001f28d  pop     rdi
0x14001f28e  pop     rsi
0x14001f28f  pop     rbp
0x14001f290  pop     rbx
0x14001f291  retn
```
