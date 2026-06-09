# MoveFileInheritSecurityW

- ea: `0x18000b0e0`
- end: `0x18000b34a`
- name: `MoveFileInheritSecurityW`
- size: `618`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn, PCWSTR, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800010b0`
- `0x1800050f0`
- `0x1800081a4`
- `0x18000b0e0`
- `0x18000b350`
- `0x1800267e0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000b1a5`
- `RPCRT4!NdrClientCall3` at `0x18000b1a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b10a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b1e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b10a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b1e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b1dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b1dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b143`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b143`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b180`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b1d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b180`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b1d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b167`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b167`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000b132`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000b132`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MoveFileInheritSecurityW(PCWSTR pszPathIn, PCWSTR a2, DWORD dwFlags)
{
  ULONGLONG TickCount64; // r15
  unsigned int v7; // edi
  __int64 Simple; // rbx
  __int64 v9; // r8
  ULONGLONG v11; // [rsp+40h] [rbp-108h] BYREF
  __int64 v12; // [rsp+48h] [rbp-100h] BYREF
  __int64 v13; // [rsp+50h] [rbp-F8h] BYREF
  ULONGLONG v14; // [rsp+58h] [rbp-F0h] BYREF
  ULONGLONG v15; // [rsp+60h] [rbp-E8h] BYREF
  ULONGLONG v16; // [rsp+68h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+70h] [rbp-D8h] BYREF
  char v18[32]; // [rsp+80h] [rbp-C8h] BYREF
  __int64 *v19; // [rsp+A0h] [rbp-A8h]
  __int64 v20; // [rsp+A8h] [rbp-A0h]
  ULONGLONG *v21; // [rsp+B0h] [rbp-98h]
  __int64 v22; // [rsp+B8h] [rbp-90h]
  ULONGLONG *v23; // [rsp+C0h] [rbp-88h]
  __int64 v24; // [rsp+C8h] [rbp-80h]
  ULONGLONG *v25; // [rsp+D0h] [rbp-78h]
  __int64 v26; // [rsp+D8h] [rbp-70h]
  ULONGLONG *v27; // [rsp+E0h] [rbp-68h]
  __int64 v28; // [rsp+E8h] [rbp-60h]
  __int64 *v29; // [rsp+F0h] [rbp-58h]
  __int64 v30; // [rsp+F8h] [rbp-50h]
  __int64 *v31; // [rsp+100h] [rbp-48h]
  __int64 v32; // [rsp+108h] [rbp-40h]

  TickCount64 = GetTickCount64();
  v11 = TickCount64;
  v7 = 0;
  if ( !(unsigned int)AreParentDirectoriesEqual(pszPathIn, a2) )
  {
    if ( (int)OpenSvcContext() >= 0 )
    {
      AcquireSRWLockShared(&g_SvcContextLock);
      if ( g_hSvcContext )
      {
        Simple = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18002E100, 0xEu, 0).Simple;
        v12 = Simple;
        ReleaseSRWLockShared(&g_SvcContextLock);
LABEL_10:
        if ( !Simple )
          goto LABEL_12;
LABEL_11:
        SetLastError(Simple);
        goto LABEL_12;
      }
      ReleaseSRWLockShared(&g_SvcContextLock);
    }
    Simple = 31;
    goto LABEL_11;
  }
  if ( !MoveFileExW(pszPathIn, a2, dwFlags) )
  {
    Simple = GetLastError();
    goto LABEL_10;
  }
  Simple = 0;
LABEL_12:
  GetTickCount64();
  if ( (unsigned int)dword_180040048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040048, 0x400000000000LL) )
  {
    v13 = 1;
    v19 = &v13;
    v20 = 8;
    v14 = v9 - TickCount64;
    v21 = &v14;
    v22 = 8;
    v15 = v9 - TickCount64;
    v23 = &v15;
    v24 = 8;
    v16 = v9 - TickCount64;
    v25 = &v16;
    v26 = 8;
    LODWORD(v11) = 29;
    v27 = &v11;
    v28 = 4;
    v17 = Simple;
    v29 = &v17;
    v30 = 8;
    v12 = 0x1000000;
    v31 = &v12;
    v32 = 8;
    tlgWriteAgg((unsigned int)&dword_180040048, (unsigned int)&dword_180036AF4, 0, 9, (__int64)v18);
  }
  LOBYTE(v7) = Simple == 0;
  return v7;
}

```

## disassembly

```asm
0x18000b0e0  push    rbx
0x18000b0e2  push    rsi
0x18000b0e3  push    rdi
0x18000b0e4  push    r14
0x18000b0e6  push    r15
0x18000b0e8  sub     rsp, 120h
0x18000b0ef  mov     rax, cs:__security_cookie
0x18000b0f6  xor     rax, rsp
0x18000b0f9  mov     [rsp+148h+var_38], rax
0x18000b101  mov     r14d, r8d
0x18000b104  mov     rsi, rdx
0x18000b107  mov     rbx, rcx
0x18000b10a  call    cs:__imp_GetTickCount64
0x18000b110  mov     r15, rax
0x18000b113  mov     [rsp+148h+var_108], rax
0x18000b118  mov     rdx, rsi; PCWSTR
0x18000b11b  mov     rcx, rbx; pszPathIn
0x18000b11e  call    AreParentDirectoriesEqual
0x18000b123  xor     edi, edi
0x18000b125  test    eax, eax
0x18000b127  jz      short loc_18000B150
0x18000b129  mov     r8d, r14d; dwFlags
0x18000b12c  mov     rdx, rsi; lpNewFileName
0x18000b12f  mov     rcx, rbx; lpExistingFileName
0x18000b132  call    cs:__imp_MoveFileExW
0x18000b138  test    eax, eax
0x18000b13a  jz      short loc_18000B143
0x18000b13c  mov     ebx, edi
0x18000b13e  jmp     loc_18000B1E3
0x18000b143  call    cs:__imp_GetLastError
0x18000b149  mov     ebx, eax
0x18000b14b  jmp     loc_18000B1D6
0x18000b150  call    OpenSvcContext
0x18000b155  test    eax, eax
0x18000b157  jns     short loc_18000B160
0x18000b159  mov     ebx, 1Fh
0x18000b15e  jmp     short loc_18000B1DB
0x18000b160  lea     rcx, g_SvcContextLock; SRWLock
0x18000b167  call    cs:__imp_AcquireSRWLockShared
0x18000b16d  mov     r9, cs:g_hSvcContext
0x18000b174  test    r9, r9
0x18000b177  jnz     short loc_18000B188
0x18000b179  lea     rcx, g_SvcContextLock; SRWLock
0x18000b180  call    cs:__imp_ReleaseSRWLockShared
0x18000b186  jmp     short loc_18000B159
0x18000b188  mov     [rsp+148h+var_118], r14d
0x18000b18d  mov     [rsp+148h+var_120], rsi
0x18000b192  mov     [rsp+148h+var_128], rbx
0x18000b197  xor     r8d, r8d; pReturnValue
0x18000b19a  lea     edx, [r8+0Eh]; nProcNum
0x18000b19e  lea     rcx, stru_18002E100; pProxyInfo
0x18000b1a5  call    cs:__imp_NdrClientCall3
0x18000b1ab  mov     rbx, rax
0x18000b1ae  mov     [rsp+148h+var_100], rax
0x18000b1b3  jmp     short loc_18000B1C9
0x18000b1b5  mov     ebx, eax
0x18000b1b7  mov     eax, 1Fh
0x18000b1bc  test    rbx, rbx
0x18000b1bf  cmovz   ebx, eax
0x18000b1c2  xor     edi, edi
0x18000b1c4  mov     r15, [rsp+148h+var_108]
0x18000b1c9  lea     rcx, g_SvcContextLock; SRWLock
0x18000b1d0  call    cs:__imp_ReleaseSRWLockShared
0x18000b1d6  test    rbx, rbx
0x18000b1d9  jz      short loc_18000B1E3
0x18000b1db  mov     ecx, ebx; dwErrCode
0x18000b1dd  call    cs:__imp_SetLastError
0x18000b1e3  call    cs:__imp_GetTickCount64
0x18000b1e9  mov     r8, rax
0x18000b1ec  mov     ecx, cs:dword_180040048
0x18000b1f2  cmp     ecx, 5
0x18000b1f5  jbe     loc_18000B322
0x18000b1fb  mov     rdx, 400000000000h
0x18000b205  lea     rcx, dword_180040048
0x18000b20c  call    _tlgKeywordOn
0x18000b211  test    al, al
0x18000b213  jz      loc_18000B322
0x18000b219  sub     r8, r15
0x18000b21c  mov     [rsp+148h+var_F8], 1
0x18000b225  lea     rax, [rsp+148h+var_F8]
0x18000b22a  mov     [rsp+148h+var_A8], rax
0x18000b232  mov     [rsp+148h+var_A0], 8
0x18000b23e  mov     [rsp+148h+var_F0], r8
0x18000b243  lea     rax, [rsp+148h+var_F0]
0x18000b248  mov     [rsp+148h+var_98], rax
0x18000b250  mov     [rsp+148h+var_90], 8
0x18000b25c  mov     [rsp+148h+var_E8], r8
0x18000b261  lea     rax, [rsp+148h+var_E8]
0x18000b266  mov     [rsp+148h+var_88], rax
0x18000b26e  mov     [rsp+148h+var_80], 8
0x18000b27a  mov     [rsp+148h+var_E0], r8
0x18000b27f  lea     rax, [rsp+148h+var_E0]
0x18000b284  mov     [rsp+148h+var_78], rax
0x18000b28c  mov     [rsp+148h+var_70], 8
0x18000b298  mov     dword ptr [rsp+148h+var_108], 1Dh
0x18000b2a0  lea     rax, [rsp+148h+var_108]
0x18000b2a5  mov     [rsp+148h+var_68], rax
0x18000b2ad  mov     [rsp+148h+var_60], 4
0x18000b2b9  mov     [rsp+148h+var_D8], rbx
0x18000b2be  lea     rax, [rsp+148h+var_D8]
0x18000b2c3  mov     [rsp+148h+var_58], rax
0x18000b2cb  mov     [rsp+148h+var_50], 8
0x18000b2d7  mov     [rsp+148h+var_100], 1000000h
0x18000b2e0  lea     rax, [rsp+148h+var_100]
0x18000b2e5  mov     [rsp+148h+var_48], rax
0x18000b2ed  mov     [rsp+148h+var_40], 8
0x18000b2f9  lea     rax, [rsp+148h+var_C8]
0x18000b301  mov     [rsp+148h+var_128], rax
0x18000b306  mov     r9d, 9
0x18000b30c  xor     r8d, r8d
0x18000b30f  lea     rdx, dword_180036AF4
0x18000b316  lea     rcx, dword_180040048
0x18000b31d  call    _tlgWriteAgg
0x18000b322  test    rbx, rbx
0x18000b325  setz    dil
0x18000b329  mov     eax, edi
0x18000b32b  mov     rcx, [rsp+148h+var_38]
0x18000b333  xor     rcx, rsp; StackCookie
0x18000b336  call    __security_check_cookie
0x18000b33b  add     rsp, 120h
0x18000b342  pop     r15
0x18000b344  pop     r14
0x18000b346  pop     rdi
0x18000b347  pop     rsi
0x18000b348  pop     rbx
0x18000b349  retn
0x18002b19c  push    rbp
0x18002b19e  sub     rsp, 40h
0x18002b1a2  mov     rbp, rdx
0x18002b1a5  mov     rcx, [rcx]
0x18002b1a8  mov     ecx, [rcx]; ExceptionCode
0x18002b1aa  call    cs:__imp_I_RpcExceptionFilter
0x18002b1b0  nop
0x18002b1b1  add     rsp, 40h
0x18002b1b5  pop     rbp
0x18002b1b6  retn
```
