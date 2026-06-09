# ScanDirectory

- ea: `0x18000d3e0`
- end: `0x18000d645`
- name: `ScanDirectory`
- size: `613`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18000d3e0`
- `0x18000d9f4`

## callees

- `0x180004e2c`
- `0x18000c014`
- `0x18000d060`
- `0x18000d3e0`
- `0x18000ede8`
- `0x1800136c6`
- `0x180013700`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000d573`
- `KERNEL32!GetProcessHeap` at `0x18000d5f5`
- `KERNEL32!GetProcessHeap` at `0x18000d573`
- `KERNEL32!GetProcessHeap` at `0x18000d5f5`
- `KERNEL32!HeapFree` at `0x18000d581`
- `KERNEL32!HeapFree` at `0x18000d603`
- `KERNEL32!HeapFree` at `0x18000d581`
- `KERNEL32!HeapFree` at `0x18000d603`
- `KERNEL32!GetLastError` at `0x18000d491`
- `KERNEL32!GetLastError` at `0x18000d491`
- `KERNEL32!FindFirstFileW` at `0x18000d482`
- `KERNEL32!FindFirstFileW` at `0x18000d482`
- `KERNEL32!FindNextFileW` at `0x18000d5e0`
- `KERNEL32!FindNextFileW` at `0x18000d5e0`
- `KERNEL32!FindClose` at `0x18000d612`
- `KERNEL32!FindClose` at `0x18000d612`

## pseudocode

```c
__int64 __fastcall ScanDirectory(__int64 a1, const unsigned __int16 *a2, __int64 a3)
{
  WCHAR *v6; // r14
  DWORD LastError; // ebx
  HANDLE FirstFileW; // rsi
  const unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbp
  HANDLE ProcessHeap; // rax
  HANDLE v12; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-298h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v6 = MemMallocAndCat(a2, L"\\*.*", 0);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, a2);
    FirstFileW = FindFirstFileW(v6, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      LastError = 0;
      while ( 1 )
      {
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          if ( FindFileData.cFileName[0] != 46
            || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
          {
            v9 = MemMallocAndCat(a2, L"\\", FindFileData.cFileName, 0);
            v10 = (unsigned __int16 *)v9;
            if ( !v9 )
            {
              LastError = 8;
              goto LABEL_30;
            }
            ScanDirectory(a1, v9, a3);
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v10);
          }
        }
        else if ( (unsigned int)InstallStoreFile(a1, a2, FindFileData.cFileName, a3)
               && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)&WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids,
            (unsigned int)FindFileData.cFileName,
            (__int64)a2);
        }
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
          goto LABEL_30;
      }
    }
    LastError = GetLastError();
    if ( LastError - 2 <= 1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, a2);
      LastError = 0;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, a2);
    }
LABEL_30:
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v6);
    if ( FirstFileW != (HANDLE)-1LL )
      FindClose(FirstFileW);
  }
  else
  {
    return 8;
  }
  return LastError;
}

```

## disassembly

```asm
0x18000d3e0  mov     [rsp+arg_18], rbx
0x18000d3e5  push    rbp
0x18000d3e6  push    rsi
0x18000d3e7  push    rdi
0x18000d3e8  push    r12
0x18000d3ea  push    r13
0x18000d3ec  push    r14
0x18000d3ee  push    r15
0x18000d3f0  sub     rsp, 290h
0x18000d3f7  mov     rax, cs:__security_cookie
0x18000d3fe  xor     rax, rsp
0x18000d401  mov     [rsp+2C8h+var_48], rax
0x18000d409  mov     r12, r8
0x18000d40c  mov     rdi, rdx
0x18000d40f  mov     r15, rcx
0x18000d412  xor     edx, edx; Val
0x18000d414  mov     r8d, 250h; Size
0x18000d41a  lea     rcx, [rsp+2C8h+FindFileData]; void *
0x18000d41f  call    memset_0
0x18000d424  xor     r8d, r8d
0x18000d427  lea     rdx, asc_180017548; "\\*.*"
0x18000d42e  mov     rcx, rdi; unsigned __int16 *
0x18000d431  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x18000d436  xor     r13d, r13d
0x18000d439  mov     r14, rax
0x18000d43c  test    rax, rax
0x18000d43f  jnz     short loc_18000D449
0x18000d441  lea     ebx, [rax+8]
0x18000d444  jmp     loc_18000D618
0x18000d449  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d450  lea     rbp, WPP_GLOBAL_Control
0x18000d457  cmp     rcx, rbp
0x18000d45a  jz      short loc_18000D47A
0x18000d45c  test    byte ptr [rcx+1Ch], 8
0x18000d460  jz      short loc_18000D47A
0x18000d462  mov     rcx, [rcx+10h]
0x18000d466  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000d46d  mov     edx, 16h
0x18000d472  mov     r9, rdi
0x18000d475  call    WPP_SF_S
0x18000d47a  lea     rdx, [rsp+2C8h+FindFileData]; lpFindFileData
0x18000d47f  mov     rcx, r14; lpFileName
0x18000d482  call    cs:__imp_FindFirstFileW
0x18000d488  mov     rsi, rax
0x18000d48b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d48f  jnz     short loc_18000D508
0x18000d491  call    cs:__imp_GetLastError
0x18000d497  mov     ebx, eax
0x18000d499  lea     ecx, [rax-2]
0x18000d49c  cmp     ecx, 1
0x18000d49f  jbe     short loc_18000D4D6
0x18000d4a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4a8  cmp     rcx, rbp
0x18000d4ab  jz      loc_18000D5F5
0x18000d4b1  test    byte ptr [rcx+1Ch], 1
0x18000d4b5  jz      loc_18000D5F5
0x18000d4bb  mov     rcx, [rcx+10h]
0x18000d4bf  lea     edx, [rsi+19h]
0x18000d4c2  mov     r9, rdi
0x18000d4c5  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000d4cc  call    WPP_SF_S
0x18000d4d1  jmp     loc_18000D5F5
0x18000d4d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4dd  cmp     rcx, rbp
0x18000d4e0  jz      short loc_18000D500
0x18000d4e2  test    byte ptr [rcx+1Ch], 8
0x18000d4e6  jz      short loc_18000D500
0x18000d4e8  mov     rcx, [rcx+10h]
0x18000d4ec  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000d4f3  mov     edx, 17h
0x18000d4f8  mov     r9, rdi
0x18000d4fb  call    WPP_SF_S
0x18000d500  mov     ebx, r13d
0x18000d503  jmp     loc_18000D5F5
0x18000d508  mov     ebx, r13d
0x18000d50b  test    byte ptr [rsp+2C8h+FindFileData.dwFileAttributes], 10h
0x18000d510  jz      short loc_18000D590
0x18000d512  cmp     [rsp+2C8h+FindFileData.cFileName], 2Eh ; '.'
0x18000d518  movzx   eax, [rsp+2C8h+FindFileData.cFileName+2]
0x18000d51d  jnz     short loc_18000D542
0x18000d51f  test    ax, ax
0x18000d522  jz      loc_18000D5D8
0x18000d528  cmp     [rsp+2C8h+FindFileData.cFileName], 2Eh ; '.'
0x18000d52e  jnz     short loc_18000D542
0x18000d530  cmp     ax, 2Eh ; '.'
0x18000d534  jnz     short loc_18000D542
0x18000d536  cmp     [rsp+2C8h+FindFileData.cFileName+4], r13w
0x18000d53c  jz      loc_18000D5D8
0x18000d542  xor     r9d, r9d
0x18000d545  lea     r8, [rsp+2C8h+FindFileData.cFileName]
0x18000d54a  lea     rdx, asc_180016E08; "\\"
0x18000d551  mov     rcx, rdi; unsigned __int16 *
0x18000d554  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x18000d559  mov     rbp, rax
0x18000d55c  test    rax, rax
0x18000d55f  jz      loc_18000D5F0
0x18000d565  mov     r8, r12
0x18000d568  mov     rdx, rax
0x18000d56b  mov     rcx, r15
0x18000d56e  call    ScanDirectory
0x18000d573  call    cs:__imp_GetProcessHeap
0x18000d579  mov     r8, rbp; lpMem
0x18000d57c  xor     edx, edx; dwFlags
0x18000d57e  mov     rcx, rax; hHeap
0x18000d581  call    cs:__imp_HeapFree
0x18000d587  lea     rbp, WPP_GLOBAL_Control
0x18000d58e  jmp     short loc_18000D5D8
0x18000d590  mov     r9, r12
0x18000d593  lea     r8, [rsp+2C8h+FindFileData.cFileName]
0x18000d598  mov     rdx, rdi
0x18000d59b  mov     rcx, r15
0x18000d59e  call    InstallStoreFile
0x18000d5a3  test    eax, eax
0x18000d5a5  jz      short loc_18000D5D8
0x18000d5a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5ae  cmp     rcx, rbp
0x18000d5b1  jz      short loc_18000D5D8
0x18000d5b3  test    byte ptr [rcx+1Ch], 1
0x18000d5b7  jz      short loc_18000D5D8
0x18000d5b9  mov     rcx, [rcx+10h]
0x18000d5bd  lea     r9, [rsp+2C8h+FindFileData.cFileName]
0x18000d5c2  mov     edx, 19h
0x18000d5c7  mov     [rsp+2C8h+var_2A8], rdi
0x18000d5cc  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000d5d3  call    WPP_SF_SS
0x18000d5d8  lea     rdx, [rsp+2C8h+FindFileData]; lpFindFileData
0x18000d5dd  mov     rcx, rsi; hFindFile
0x18000d5e0  call    cs:__imp_FindNextFileW
0x18000d5e6  test    eax, eax
0x18000d5e8  jnz     loc_18000D50B
0x18000d5ee  jmp     short loc_18000D5F5
0x18000d5f0  mov     ebx, 8
0x18000d5f5  call    cs:__imp_GetProcessHeap
0x18000d5fb  mov     r8, r14; lpMem
0x18000d5fe  xor     edx, edx; dwFlags
0x18000d600  mov     rcx, rax; hHeap
0x18000d603  call    cs:__imp_HeapFree
0x18000d609  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000d60d  jz      short loc_18000D618
0x18000d60f  mov     rcx, rsi; hFindFile
0x18000d612  call    cs:__imp_FindClose
0x18000d618  mov     eax, ebx
0x18000d61a  mov     rcx, [rsp+2C8h+var_48]
0x18000d622  xor     rcx, rsp; StackCookie
0x18000d625  call    __security_check_cookie
0x18000d62a  mov     rbx, [rsp+2C8h+arg_18]
0x18000d632  add     rsp, 290h
0x18000d639  pop     r15
0x18000d63b  pop     r14
0x18000d63d  pop     r13
0x18000d63f  pop     r12
0x18000d641  pop     rdi
0x18000d642  pop     rsi
0x18000d643  pop     rbp
0x18000d644  retn
```
