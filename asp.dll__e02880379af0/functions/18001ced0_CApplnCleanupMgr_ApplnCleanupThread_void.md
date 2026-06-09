# CApplnCleanupMgr::ApplnCleanupThread(void *)

- ea: `0x18001ced0`
- end: `0x18001cf04`
- name: `?ApplnCleanupThread@CApplnCleanupMgr@@CAKPEAX@Z`
- size: `52`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001ced0`
- `0x1800310b0`
- `0x180031b60`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002ff69`
- `KERNEL32!LeaveCriticalSection` at `0x18002ffbd`
- `KERNEL32!LeaveCriticalSection` at `0x18002ff69`
- `KERNEL32!LeaveCriticalSection` at `0x18002ffbd`
- `KERNEL32!WaitForMultipleObjects` at `0x18002ff8e`
- `KERNEL32!WaitForMultipleObjects` at `0x18002ffec`
- `KERNEL32!WaitForMultipleObjects` at `0x18002ff8e`
- `KERNEL32!WaitForMultipleObjects` at `0x18002ffec`
- `KERNEL32!WaitForSingleObject` at `0x18001cef8`
- `KERNEL32!WaitForSingleObject` at `0x18001cef8`
- `KERNEL32!CloseHandle` at `0x180030087`
- `KERNEL32!CloseHandle` at `0x1800300ae`
- `KERNEL32!CloseHandle` at `0x180030087`
- `KERNEL32!CloseHandle` at `0x1800300ae`
- `KERNEL32!CreateThread` at `0x180030052`
- `KERNEL32!CreateThread` at `0x180030052`
- `KERNEL32!EnterCriticalSection` at `0x18002ff46`
- `KERNEL32!EnterCriticalSection` at `0x18002ff46`
- `iisutil!PuDbgPrint` at `0x18003002d`
- `iisutil!PuDbgPrint` at `0x18003002d`

## string_xrefs

- `0x180030021`: `[CApplnCleanupMgr] Cleanup Thread working on (%S)\n`

## pseudocode

```c
__int64 __fastcall CApplnCleanupMgr::ApplnCleanupThread(CApplnCleanupMgr *lpThreadParameter)
{
  CApplnCleanupMgr *v1; // rcx
  CApplnCleanupMgr *v2; // rcx
  CApplnCleanupMgr *v3; // rcx
  const wchar_t **v4; // rbx
  struct CAppln *v5; // rax
  DWORD v6; // edi
  HANDLE Thread; // rsi
  __int64 v8; // rbx
  DWORD v9; // eax

  while ( 1 )
  {
    if ( (g_ApplnCleanupMgr & 1) != 0 )
LABEL_2:
      WaitForSingleObject(qword_180079CB0, 0xFFFFFFFF);
    if ( !CApplnCleanupMgr::Head(lpThreadParameter) && (g_ApplnCleanupMgr & 1) != 0 )
      goto LABEL_2;
    if ( !CApplnCleanupMgr::Head(v1) )
      goto LABEL_9;
    EnterCriticalSection(&stru_180079B80);
    v4 = (const wchar_t **)CApplnCleanupMgr::Head(v2);
    if ( !v4 && (g_ApplnCleanupMgr & 1) == 0 )
      break;
    v5 = CApplnCleanupMgr::Head(v3);
    *(_QWORD *)(*((_QWORD *)v5 + 7) + 32LL) = *((_QWORD *)v5 + 8);
    *(_QWORD *)(*((_QWORD *)v5 + 8) + 24LL) = *((_QWORD *)v5 + 7);
    LeaveCriticalSection(&stru_180079B80);
    v6 = nCount;
    if ( nCount >= 4 && (!g_fShutDownInProgress || nCount >= 0x20) )
      v6 = WaitForMultipleObjects(nCount, &Handles, 0, 0xFFFFFFFF);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
        3544,
        "CApplnCleanupMgr::ApplnCleanupDoWork",
        "[CApplnCleanupMgr] Cleanup Thread working on (%S)\n",
        v4[15]);
    Thread = CreateThread(0, 0, CAppln::ApplnCleanupProc, v4, 0, 0);
    if ( Thread )
    {
      v8 = 8LL * v6;
      if ( v6 >= nCount )
        ++nCount;
      else
        CloseHandle(*(HANDLE *)((char *)&g_ApplnCleanupMgr + v8 + 56));
      *(_QWORD *)((char *)&g_ApplnCleanupMgr + v8 + 56) = Thread;
    }
    else
    {
      CAppln::ApplnCleanupProc(v4);
    }
  }
  LeaveCriticalSection(&stru_180079B80);
LABEL_9:
  if ( nCount )
  {
    WaitForMultipleObjects(nCount, &Handles, 1, 0xFFFFFFFF);
    while ( 1 )
    {
      v9 = nCount;
      if ( !nCount )
        break;
      --nCount;
      CloseHandle(*((HANDLE *)&g_ApplnCleanupMgr + v9 + 6));
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001ced0  push    rbx
0x18001ced2  push    rsi
0x18001ced3  push    rdi
0x18001ced4  push    r13
0x18001ced6  sub     rsp, 38h
0x18001ceda  lea     r13, ?g_ApplnCleanupMgr@@3VCApplnCleanupMgr@@A; CApplnCleanupMgr g_ApplnCleanupMgr
0x18001cee1  test    byte ptr cs:?g_ApplnCleanupMgr@@3VCApplnCleanupMgr@@A, 1; CApplnCleanupMgr g_ApplnCleanupMgr
0x18001cee8  jz      loc_18002FF1E
0x18001ceee  mov     rcx, cs:qword_180079CB0; hHandle
0x18001cef5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001cef8  call    cs:__imp_WaitForSingleObject
0x18001cefe  nop
0x18001ceff  jmp     loc_18002FF1E
0x18002ff1e  call    ?Head@CApplnCleanupMgr@@AEAAPEAVCAppln@@XZ; CApplnCleanupMgr::Head(void)
0x18002ff23  test    rax, rax
0x18002ff26  jnz     short loc_18002FF35
0x18002ff28  test    byte ptr cs:?g_ApplnCleanupMgr@@3VCApplnCleanupMgr@@A, 1; CApplnCleanupMgr g_ApplnCleanupMgr
0x18002ff2f  jnz     loc_18001CEEE
0x18002ff35  call    ?Head@CApplnCleanupMgr@@AEAAPEAVCAppln@@XZ; CApplnCleanupMgr::Head(void)
0x18002ff3a  test    rax, rax
0x18002ff3d  jz      short loc_18002FF6F
0x18002ff3f  lea     rcx, stru_180079B80; lpCriticalSection
0x18002ff46  call    cs:__imp_EnterCriticalSection
0x18002ff4c  call    ?Head@CApplnCleanupMgr@@AEAAPEAVCAppln@@XZ; CApplnCleanupMgr::Head(void)
0x18002ff51  mov     rbx, rax
0x18002ff54  test    rax, rax
0x18002ff57  jnz     short loc_18002FF99
0x18002ff59  test    byte ptr cs:?g_ApplnCleanupMgr@@3VCApplnCleanupMgr@@A, 1; CApplnCleanupMgr g_ApplnCleanupMgr
0x18002ff60  jnz     short loc_18002FF99
0x18002ff62  lea     rcx, stru_180079B80; lpCriticalSection
0x18002ff69  call    cs:__imp_LeaveCriticalSection
0x18002ff6f  mov     ecx, cs:nCount; nCount
0x18002ff75  test    ecx, ecx
0x18002ff77  jz      loc_1800300BE
0x18002ff7d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002ff81  lea     rdx, Handles; lpHandles
0x18002ff88  mov     r8d, 1; bWaitAll
0x18002ff8e  call    cs:__imp_WaitForMultipleObjects
0x18002ff94  jmp     loc_1800300B4
0x18002ff99  call    ?Head@CApplnCleanupMgr@@AEAAPEAVCAppln@@XZ; CApplnCleanupMgr::Head(void)
0x18002ff9e  mov     rcx, [rax+40h]
0x18002ffa2  mov     rdx, [rax+38h]
0x18002ffa6  mov     [rdx+20h], rcx
0x18002ffaa  mov     rcx, [rax+40h]
0x18002ffae  mov     rax, [rax+38h]
0x18002ffb2  mov     [rcx+18h], rax
0x18002ffb6  lea     rcx, stru_180079B80; lpCriticalSection
0x18002ffbd  call    cs:__imp_LeaveCriticalSection
0x18002ffc3  mov     edi, cs:nCount
0x18002ffc9  cmp     edi, 4
0x18002ffcc  jb      short loc_18002FFF4
0x18002ffce  cmp     cs:?g_fShutDownInProgress@@3HA, 0; int g_fShutDownInProgress
0x18002ffd5  jz      short loc_18002FFDC
0x18002ffd7  cmp     edi, 20h ; ' '
0x18002ffda  jb      short loc_18002FFF4
0x18002ffdc  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002ffe0  lea     rdx, Handles; lpHandles
0x18002ffe7  xor     r8d, r8d; bWaitAll
0x18002ffea  mov     ecx, edi; nCount
0x18002ffec  call    cs:__imp_WaitForMultipleObjects
0x18002fff2  mov     edi, eax
0x18002fff4  test    byte ptr cs:g_dwDebugFlags, 3
0x18002fffb  jz      short loc_180030033
0x18002fffd  mov     rax, [rbx+78h]
0x180030001  lea     r9, aCapplncleanupm_0; "CApplnCleanupMgr::ApplnCleanupDoWork"
0x180030008  mov     rcx, cs:g_pDebug
0x18003000f  lea     rdx, aInetsrvIisSvcs_7; "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.c"...
0x180030016  mov     [rsp+58h+lpThreadId], rax
0x18003001b  mov     r8d, 0DD8h
0x180030021  lea     rax, aCapplncleanupm_2; "[CApplnCleanupMgr] Cleanup Thread worki"...
0x180030028  mov     qword ptr [rsp+58h+dwCreationFlags], rax
0x18003002d  call    cs:__imp_PuDbgPrint
0x180030033  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18003003c  lea     r8, ?ApplnCleanupProc@CAppln@@CAKPEAX@Z; lpStartAddress
0x180030043  mov     r9, rbx; lpParameter
0x180030046  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18003004e  xor     edx, edx; dwStackSize
0x180030050  xor     ecx, ecx; lpThreadAttributes
0x180030052  call    cs:__imp_CreateThread
0x180030058  mov     rsi, rax
0x18003005b  test    rax, rax
0x18003005e  jnz     short loc_18003006E
0x180030060  mov     rcx, rbx; lpThreadParameter
0x180030063  call    ?ApplnCleanupProc@CAppln@@CAKPEAX@Z; CAppln::ApplnCleanupProc(void *)
0x180030068  nop
0x180030069  jmp     loc_18001CEE1
0x18003006e  mov     eax, edi
0x180030070  lea     rbx, ds:0[rax*8]
0x180030078  mov     eax, cs:nCount
0x18003007e  cmp     edi, eax
0x180030080  jnb     short loc_18003008F
0x180030082  mov     rcx, [rbx+r13+38h]; hObject
0x180030087  call    cs:__imp_CloseHandle
0x18003008d  jmp     short loc_180030097
0x18003008f  inc     eax
0x180030091  mov     cs:nCount, eax
0x180030097  mov     [rbx+r13+38h], rsi
0x18003009c  jmp     loc_18001CEE1
0x1800300a1  dec     eax
0x1800300a3  mov     cs:nCount, eax
0x1800300a9  mov     rcx, [r13+rax*8+38h]; hObject
0x1800300ae  call    cs:__imp_CloseHandle
0x1800300b4  mov     eax, cs:nCount
0x1800300ba  test    eax, eax
0x1800300bc  jnz     short loc_1800300A1
0x1800300be  xor     eax, eax
0x1800300c0  add     rsp, 38h
0x1800300c4  pop     r13
0x1800300c6  pop     rdi
0x1800300c7  pop     rsi
0x1800300c8  pop     rbx
0x1800300c9  retn
```
