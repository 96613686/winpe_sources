# BfspSpacesCopyToPhysicalPartitions

- ea: `0x18004c194`
- end: `0x18004c44f`
- name: `BfspSpacesCopyToPhysicalPartitions`
- size: `699`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task`

## callers

- `0x18004bc94`

## callees

- `0x1800078b0`
- `0x1800078f0`
- `0x18001be20`
- `0x1800466c0`
- `0x18004aca0`
- `0x18004b568`
- `0x18004c0c4`
- `0x18004c194`
- `0x18004cdd4`
- `0x1800513d4`
- `0x18005214c`
- `0x180052c8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c219`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c232`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c219`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c232`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c20b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c224`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c20b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c224`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c242`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c1e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c344`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c3d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c1e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c344`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c3d4`

## string_xrefs

- `0x18004c357`: `ServiceSpaces: Failed to create path %s. Last error = %#x`
- `0x18004c3a3`: `ServiceSpaces: Skipping non-Windows %s`
- `0x18004c25e`: `ServiceSpaces: %s does not exist`
- `0x18004c3e2`: `ServiceSpaces: Failed to copy %s to %s. Last Error = %#x`
- `0x18004c3f9`: `ServiceSpaces: Skipping %s`

## pseudocode

```c
__int64 __fastcall BfspSpacesCopyToPhysicalPartitions(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v7; // r14d
  _WORD *v8; // r15
  DWORD v9; // edi
  __int64 v10; // rax
  wchar_t *v11; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v13; // rax
  int v15; // esi
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned int v18; // r12d
  __int64 v19; // rcx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rsi
  DWORD LastError; // eax
  unsigned int FirmwareType; // eax
  __int64 v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+30h] [rbp-D0h]
  WCHAR v27[264]; // [rsp+40h] [rbp-C0h] BYREF

  v7 = 0;
  v8 = (_WORD *)BfspEnvExpandString(a1, a3);
  if ( v8 )
  {
    v10 = BfspEnvExpandString(a1, a2);
    v11 = (wchar_t *)v10;
    if ( v10 )
    {
      if ( (unsigned int)BfspFileExists(v10) )
      {
        v15 = 0;
        v25 = 0;
        v9 = 0;
        v16 = -1;
        do
          ++v16;
        while ( v8[v16] );
        v17 = v16 - 1;
        v18 = 0;
        if ( v16 )
        {
          while ( v8[v17] != 92 )
          {
            ++v18;
            --v17;
            if ( v18 >= v16 )
              goto LABEL_18;
          }
          v15 = 1;
          v25 = 1;
        }
LABEL_18:
        if ( *(_DWORD *)(a5 + 8) )
        {
          do
          {
            LODWORD(v24) = *(_DWORD *)(a5 + 12LL * v7 + 20);
            StringCchPrintfW(
              v27,
              0x104u,
              L"\\\\?\\Harddisk%uPartition%u\\%s",
              *(unsigned int *)(a5 + 12LL * v7 + 16),
              v24,
              v8);
            if ( v15 )
            {
              v19 = -1;
              do
                ++v19;
              while ( v27[v19] );
              v20 = v19 + ~(unsigned __int64)v18;
              v21 = v20;
              if ( 2 * v20 >= 0x208 )
                _report_rangecheckfailure(v19);
              v27[v20] = 0;
              if ( !CreatePath(v27) )
              {
                LastError = GetLastError();
                BfspLogMessage(3, L"ServiceSpaces: Failed to create path %s. Last error = %#x", v27, LastError);
              }
              v27[v21] = 92;
              v15 = v25;
            }
            if ( a4
              && (unsigned int)BfspFileExists(v27)
              && (FirmwareType = BfspGetFirmwareType(), !(unsigned int)BfspIsWindowsBinary(v27, a4, FirmwareType)) )
            {
              BfspLogMessage(3, L"ServiceSpaces: Skipping non-Windows %s", v27);
            }
            else if ( (unsigned int)BfspShouldFileBeCopied(v11) )
            {
              if ( !(unsigned int)BfspCopyFile((__int64)v11, v27) )
              {
                LODWORD(v24) = GetLastError();
                BfspLogMessage(3, L"ServiceSpaces: Failed to copy %s to %s. Last Error = %#x", v11, v27, v24);
              }
            }
            else
            {
              BfspLogMessage(3, L"ServiceSpaces: Skipping %s", v27);
            }
            ++v7;
          }
          while ( v7 < *(_DWORD *)(a5 + 8) );
        }
      }
      else
      {
        BfspLogMessage(4, L"ServiceSpaces: %s does not exist", v11);
        v9 = 2;
      }
    }
    else
    {
      v9 = GetLastError();
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
    if ( v11 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v11);
    }
  }
  else
  {
    v9 = GetLastError();
  }
  if ( !v9 )
    return 1;
  SetLastError(v9);
  return 0;
}

```

## disassembly

```asm
0x18004c194  push    rbp
0x18004c196  push    rbx
0x18004c197  push    rsi
0x18004c198  push    rdi
0x18004c199  push    r12
0x18004c19b  push    r13
0x18004c19d  push    r14
0x18004c19f  push    r15
0x18004c1a1  lea     rbp, [rsp-168h]
0x18004c1a9  sub     rsp, 268h
0x18004c1b0  mov     rax, cs:__security_cookie
0x18004c1b7  xor     rax, rsp
0x18004c1ba  mov     [rbp+1A0h+var_50], rax
0x18004c1c1  mov     r13, [rbp+1A0h+arg_20]
0x18004c1c8  mov     rdi, rdx
0x18004c1cb  mov     rdx, r8
0x18004c1ce  mov     [rsp+2A0h+var_268], r9
0x18004c1d3  mov     rbx, rcx
0x18004c1d6  call    BfspEnvExpandString
0x18004c1db  xor     r14d, r14d
0x18004c1de  mov     r15, rax
0x18004c1e1  test    rax, rax
0x18004c1e4  jnz     short loc_18004C1F0
0x18004c1e6  call    cs:__imp_GetLastError
0x18004c1ec  mov     edi, eax
0x18004c1ee  jmp     short loc_18004C238
0x18004c1f0  mov     rdx, rdi
0x18004c1f3  mov     rcx, rbx
0x18004c1f6  call    BfspEnvExpandString
0x18004c1fb  mov     rbx, rax
0x18004c1fe  test    rax, rax
0x18004c201  jnz     short loc_18004C24F
0x18004c203  call    cs:__imp_GetLastError
0x18004c209  mov     edi, eax
0x18004c20b  call    cs:__imp_GetProcessHeap
0x18004c211  mov     r8, r15; lpMem
0x18004c214  xor     edx, edx; dwFlags
0x18004c216  mov     rcx, rax; hHeap
0x18004c219  call    cs:__imp_HeapFree
0x18004c21f  test    rbx, rbx
0x18004c222  jz      short loc_18004C238
0x18004c224  call    cs:__imp_GetProcessHeap
0x18004c22a  mov     r8, rbx; lpMem
0x18004c22d  xor     edx, edx; dwFlags
0x18004c22f  mov     rcx, rax; hHeap
0x18004c232  call    cs:__imp_HeapFree
0x18004c238  test    edi, edi
0x18004c23a  jz      loc_18004C421
0x18004c240  mov     ecx, edi; dwErrCode
0x18004c242  call    cs:__imp_SetLastError
0x18004c248  xor     eax, eax
0x18004c24a  jmp     loc_18004C426
0x18004c24f  mov     rcx, rbx
0x18004c252  call    BfspFileExists
0x18004c257  test    eax, eax
0x18004c259  jnz     short loc_18004C274
0x18004c25b  mov     r8, rbx
0x18004c25e  lea     rdx, aServicespacesS_1; "ServiceSpaces: %s does not exist"
0x18004c265  lea     ecx, [rax+4]
0x18004c268  call    BfspLogMessage
0x18004c26d  mov     edi, 2
0x18004c272  jmp     short loc_18004C20B
0x18004c274  mov     esi, r14d
0x18004c277  mov     [rsp+2A0h+var_270], r14d
0x18004c27c  mov     edi, r14d
0x18004c27f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004c283  inc     rcx
0x18004c286  cmp     [r15+rcx*2], r14w
0x18004c28b  jnz     short loc_18004C283
0x18004c28d  lea     rdx, [rcx-1]
0x18004c291  mov     r12d, r14d
0x18004c294  mov     eax, 5Ch ; '\'
0x18004c299  test    rcx, rcx
0x18004c29c  jz      short loc_18004C2C3
0x18004c29e  cmp     [r15+rdx*2], ax
0x18004c2a3  jz      short loc_18004C2BA
0x18004c2a5  inc     r12d
0x18004c2a8  dec     rdx
0x18004c2ab  mov     eax, r12d
0x18004c2ae  cmp     rax, rcx
0x18004c2b1  mov     eax, 5Ch ; '\'
0x18004c2b6  jb      short loc_18004C29E
0x18004c2b8  jmp     short loc_18004C2C3
0x18004c2ba  mov     esi, 1
0x18004c2bf  mov     [rsp+2A0h+var_270], esi
0x18004c2c3  cmp     [r13+8], edi
0x18004c2c7  jbe     loc_18004C20B
0x18004c2cd  mov     eax, r14d
0x18004c2d0  lea     r8, aHarddiskUparti; "\\\\?\\Harddisk%uPartition%u\\%s"
0x18004c2d7  mov     [rsp+2A0h+var_278], r15
0x18004c2dc  lea     rcx, [rsp+2A0h+var_260]; unsigned __int16 *
0x18004c2e1  mov     edx, 104h; unsigned __int64
0x18004c2e6  lea     r9, [rax+rax*2]
0x18004c2ea  mov     eax, [r13+r9*4+14h]
0x18004c2ef  mov     r9d, [r13+r9*4+10h]
0x18004c2f4  mov     dword ptr [rsp+2A0h+var_280], eax
0x18004c2f8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c2fd  xor     edx, edx
0x18004c2ff  test    esi, esi
0x18004c301  jz      short loc_18004C373
0x18004c303  lea     rax, [rsp+2A0h+var_260]
0x18004c308  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004c30c  inc     rcx
0x18004c30f  cmp     [rax+rcx*2], dx
0x18004c313  jnz     short loc_18004C30C
0x18004c315  mov     eax, r12d
0x18004c318  not     rax
0x18004c31b  add     rax, rcx
0x18004c31e  lea     rsi, [rax+rax]
0x18004c322  cmp     rsi, 208h
0x18004c329  jnb     loc_18004C449
0x18004c32f  lea     rcx, [rsp+2A0h+var_260]
0x18004c334  mov     [rsp+rsi+2A0h+var_260], dx
0x18004c339  call    CreatePath
0x18004c33e  xor     edx, edx
0x18004c340  test    eax, eax
0x18004c342  jnz     short loc_18004C365
0x18004c344  call    cs:__imp_GetLastError
0x18004c34a  lea     r8, [rsp+2A0h+var_260]
0x18004c34f  mov     ecx, 3
0x18004c354  mov     r9d, eax
0x18004c357  lea     rdx, aServicespacesF; "ServiceSpaces: Failed to create path %s"...
0x18004c35e  call    BfspLogMessage
0x18004c363  xor     edx, edx
0x18004c365  mov     eax, 5Ch ; '\'
0x18004c36a  mov     [rsp+rsi+2A0h+var_260], ax
0x18004c36f  mov     esi, [rsp+2A0h+var_270]
0x18004c373  cmp     [rsp+2A0h+var_268], rdx
0x18004c378  jz      short loc_18004C3AC
0x18004c37a  lea     rcx, [rsp+2A0h+var_260]
0x18004c37f  call    BfspFileExists
0x18004c384  test    eax, eax
0x18004c386  jz      short loc_18004C3AC
0x18004c388  call    BfspGetFirmwareType
0x18004c38d  mov     rdx, [rsp+2A0h+var_268]
0x18004c392  lea     rcx, [rsp+2A0h+var_260]
0x18004c397  mov     r8d, eax
0x18004c39a  call    BfspIsWindowsBinary
0x18004c39f  test    eax, eax
0x18004c3a1  jnz     short loc_18004C3AC
0x18004c3a3  lea     rdx, aServicespacesS_0; "ServiceSpaces: Skipping non-Windows %s"
0x18004c3aa  jmp     short loc_18004C400
0x18004c3ac  mov     r8d, 1
0x18004c3b2  lea     rdx, [rsp+2A0h+var_260]
0x18004c3b7  mov     rcx, rbx; Str
0x18004c3ba  call    BfspShouldFileBeCopied
0x18004c3bf  test    eax, eax
0x18004c3c1  jz      short loc_18004C3F9
0x18004c3c3  lea     rdx, [rsp+2A0h+var_260]
0x18004c3c8  mov     rcx, rbx
0x18004c3cb  call    BfspCopyFile
0x18004c3d0  test    eax, eax
0x18004c3d2  jnz     short loc_18004C40F
0x18004c3d4  call    cs:__imp_GetLastError
0x18004c3da  lea     r9, [rsp+2A0h+var_260]
0x18004c3df  mov     r8, rbx
0x18004c3e2  lea     rdx, aServicespacesF_0; "ServiceSpaces: Failed to copy %s to %s."...
0x18004c3e9  mov     dword ptr [rsp+2A0h+var_280], eax
0x18004c3ed  mov     ecx, 3
0x18004c3f2  call    BfspLogMessage
0x18004c3f7  jmp     short loc_18004C40F
0x18004c3f9  lea     rdx, aServicespacesS; "ServiceSpaces: Skipping %s"
0x18004c400  lea     r8, [rsp+2A0h+var_260]
0x18004c405  mov     ecx, 3
0x18004c40a  call    BfspLogMessage
0x18004c40f  inc     r14d
0x18004c412  cmp     r14d, [r13+8]
0x18004c416  jb      loc_18004C2CD
0x18004c41c  jmp     loc_18004C20B
0x18004c421  mov     eax, 1
0x18004c426  mov     rcx, [rbp+1A0h+var_50]
0x18004c42d  xor     rcx, rsp; StackCookie
0x18004c430  call    __security_check_cookie
0x18004c435  add     rsp, 268h
0x18004c43c  pop     r15
0x18004c43e  pop     r14
0x18004c440  pop     r13
0x18004c442  pop     r12
0x18004c444  pop     rdi
0x18004c445  pop     rsi
0x18004c446  pop     rbx
0x18004c447  pop     rbp
0x18004c448  retn
0x18004c449  call    __report_rangecheckfailure
```
