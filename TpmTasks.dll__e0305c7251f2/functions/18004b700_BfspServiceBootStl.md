# BfspServiceBootStl

- ea: `0x18004b700`
- end: `0x18004b979`
- name: `BfspServiceBootStl`
- size: `633`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x180049234`

## callees

- `0x18001bddc`
- `0x18001be20`
- `0x1800466c0`
- `0x18004aca0`
- `0x18004b700`
- `0x18004cdd4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b94c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b960`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b94c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b960`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b736`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b783`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b93e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b952`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b736`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b783`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b93e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b952`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b749`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b791`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b749`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b791`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b759`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b7a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b759`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b7a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b88c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b88c`

## string_xrefs

- `0x18004b895`: `Error copying %s to %s. Last Error = %#x`
- `0x18004b8bc`: `Source Boot.stl (%s) does not exist. Will skip copying %s`
- `0x18004b928`: `Source Pending Boot.stl (%s) does not exist. Will skip copying %s`
- `0x18004b84a`: `Destination Boot.stl exists. Will copy both boot.stls (current and pending) to the destination.`

## pseudocode

```c
__int64 __fastcall BfspServiceBootStl(__int64 a1, __int64 a2)
{
  __int64 v2; // rbp
  __int64 v4; // rax
  unsigned __int64 v6; // r12
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  char *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // rax
  unsigned __int64 v12; // r13
  SIZE_T v13; // rbx
  HANDLE v14; // rax
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rsi
  __int64 v17; // rax
  unsigned __int16 *v18; // r12
  unsigned __int16 *v19; // r14
  int v20; // ebp
  const unsigned __int16 *v21; // r8
  HANDLE v22; // rax
  HANDLE v23; // rax
  DWORD LastError; // [rsp+20h] [rbp-58h]

  v2 = -1;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(a1 + 2 * v4) );
  v6 = v4 + 262;
  v7 = 2 * (v4 + 262);
  ProcessHeap = GetProcessHeap();
  v9 = (char *)HeapAlloc(ProcessHeap, 8u, v7);
  if ( v9 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(a2 + 2 * v11) );
    v12 = v11 + 262;
    v13 = 2 * (v11 + 262);
    v14 = GetProcessHeap();
    v15 = (unsigned __int16 *)HeapAlloc(v14, 8u, v13);
    v10 = 0;
    v16 = v15;
    if ( !v15 )
    {
      SetLastError(8u);
LABEL_27:
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v9);
      return v10;
    }
    StringCchPrintfW((unsigned __int16 *)v9, v6, L"%s\\", a1);
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)&v9[2 * v17] );
    v18 = (unsigned __int16 *)&v9[2 * v17];
    StringCchPrintfW(v16, v12, L"%s\\", a2);
    do
      ++v2;
    while ( v16[v2] );
    v19 = &v16[v2];
    StringCchCopyW(v19, 0x105u, L"boot.stl");
    if ( (unsigned int)BfspFileExists(v16) )
    {
      BfspLogMessage(
        2,
        L"Destination Boot.stl exists. Will copy both boot.stls (current and pending) to the destination.");
      v20 = 0;
    }
    else
    {
      StringCchCopyW(v18, 0x105u, L"boot.pnd.stl");
      BfspLogMessage(
        2,
        L"Destination Boot.stl does not exist. Will enforce Pending Boot.stl (%s) as Boot.stl. (%s)",
        v9,
        v16);
      v20 = 1;
    }
    StringCchCopyW(v18, 0x105u, L"boot.stl");
    if ( (unsigned int)BfspFileExists(v9) )
    {
      v10 = BfspCopyFile((__int64)v9, v16);
      if ( !v10 )
        goto LABEL_18;
    }
    else
    {
      BfspLogMessage(3, L"Source Boot.stl (%s) does not exist. Will skip copying %s", v9, L"boot.stl");
    }
    v21 = L"boot.stl";
    if ( !v20 )
      v21 = L"boot.pnd.stl";
    StringCchCopyW(v19, 0x105u, v21);
    StringCchCopyW(v18, 0x105u, L"boot.pnd.stl");
    if ( !(unsigned int)BfspFileExists(v9) )
    {
      BfspLogMessage(3, L"Source Pending Boot.stl (%s) does not exist. Will skip copying %s", v9, L"boot.pnd.stl");
      v10 = 1;
      goto LABEL_26;
    }
    v10 = BfspCopyFile((__int64)v9, v16);
    if ( v10 )
    {
LABEL_26:
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v16);
      goto LABEL_27;
    }
LABEL_18:
    LastError = GetLastError();
    BfspLogMessage(4, L"Error copying %s to %s. Last Error = %#x", v9, v16, LastError);
    goto LABEL_26;
  }
  SetLastError(8u);
  return 0;
}

```

## disassembly

```asm
0x18004b700  push    rbx
0x18004b702  push    rbp
0x18004b703  push    rsi
0x18004b704  push    rdi
0x18004b705  push    r12
0x18004b707  push    r13
0x18004b709  push    r14
0x18004b70b  push    r15
0x18004b70d  sub     rsp, 38h
0x18004b711  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18004b715  mov     r15, rdx
0x18004b718  mov     rax, rbp
0x18004b71b  xor     r13d, r13d
0x18004b71e  mov     r14, rcx
0x18004b721  inc     rax
0x18004b724  cmp     [rcx+rax*2], r13w
0x18004b729  jnz     short loc_18004B721
0x18004b72b  lea     r12, [rax+106h]
0x18004b732  lea     rbx, [r12+r12]
0x18004b736  call    cs:__imp_GetProcessHeap
0x18004b73c  mov     esi, 8
0x18004b741  mov     r8, rbx; dwBytes
0x18004b744  mov     rcx, rax; hHeap
0x18004b747  mov     edx, esi; dwFlags
0x18004b749  call    cs:__imp_HeapAlloc
0x18004b74f  mov     rdi, rax
0x18004b752  test    rax, rax
0x18004b755  jnz     short loc_18004B767
0x18004b757  mov     ecx, esi; dwErrCode
0x18004b759  call    cs:__imp_SetLastError
0x18004b75f  mov     ebx, r13d
0x18004b762  jmp     loc_18004B966
0x18004b767  mov     rax, rbp
0x18004b76a  inc     rax
0x18004b76d  cmp     [r15+rax*2], r13w
0x18004b772  jnz     short loc_18004B76A
0x18004b774  lea     r13, [rax+106h]
0x18004b77b  lea     rbx, ds:0[r13*2]
0x18004b783  call    cs:__imp_GetProcessHeap
0x18004b789  mov     r8, rbx; dwBytes
0x18004b78c  mov     edx, esi; dwFlags
0x18004b78e  mov     rcx, rax; hHeap
0x18004b791  call    cs:__imp_HeapAlloc
0x18004b797  xor     ebx, ebx
0x18004b799  mov     rsi, rax
0x18004b79c  test    rax, rax
0x18004b79f  jnz     short loc_18004B7AF
0x18004b7a1  lea     ecx, [rax+8]; dwErrCode
0x18004b7a4  call    cs:__imp_SetLastError
0x18004b7aa  jmp     loc_18004B952
0x18004b7af  mov     r9, r14
0x18004b7b2  lea     r8, aS_0; "%s\\"
0x18004b7b9  mov     rdx, r12; unsigned __int64
0x18004b7bc  mov     rcx, rdi; unsigned __int16 *
0x18004b7bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b7c4  mov     rax, rbp
0x18004b7c7  inc     rax
0x18004b7ca  cmp     [rdi+rax*2], bx
0x18004b7ce  jnz     short loc_18004B7C7
0x18004b7d0  mov     r9, r15
0x18004b7d3  lea     r8, aS_0; "%s\\"
0x18004b7da  mov     rdx, r13; unsigned __int64
0x18004b7dd  lea     r12, [rdi+rax*2]
0x18004b7e1  mov     rcx, rsi; unsigned __int16 *
0x18004b7e4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b7e9  inc     rbp
0x18004b7ec  cmp     [rsi+rbp*2], bx
0x18004b7f0  jnz     short loc_18004B7E9
0x18004b7f2  lea     r14, [rsi+rbp*2]
0x18004b7f6  mov     r15d, 105h
0x18004b7fc  mov     edx, r15d; unsigned __int64
0x18004b7ff  lea     r8, aBootStl; "boot.stl"
0x18004b806  mov     rcx, r14; unsigned __int16 *
0x18004b809  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b80e  mov     rcx, rsi
0x18004b811  call    BfspFileExists
0x18004b816  test    eax, eax
0x18004b818  jnz     short loc_18004B84A
0x18004b81a  lea     r8, aBootPndStl; "boot.pnd.stl"
0x18004b821  mov     edx, r15d; unsigned __int64
0x18004b824  mov     rcx, r12; unsigned __int16 *
0x18004b827  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b82c  mov     r9, rsi
0x18004b82f  lea     rdx, aDestinationBoo; "Destination Boot.stl does not exist. Wi"...
0x18004b836  mov     r8, rdi
0x18004b839  mov     ecx, 2
0x18004b83e  call    BfspLogMessage
0x18004b843  mov     ebp, 1
0x18004b848  jmp     short loc_18004B85D
0x18004b84a  lea     rdx, aDestinationBoo_0; "Destination Boot.stl exists. Will copy "...
0x18004b851  mov     ecx, 2
0x18004b856  call    BfspLogMessage
0x18004b85b  mov     ebp, ebx
0x18004b85d  lea     r8, aBootStl; "boot.stl"
0x18004b864  mov     rdx, r15; unsigned __int64
0x18004b867  mov     rcx, r12; unsigned __int16 *
0x18004b86a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b86f  mov     rcx, rdi
0x18004b872  call    BfspFileExists
0x18004b877  test    eax, eax
0x18004b879  jz      short loc_18004B8B2
0x18004b87b  mov     rdx, rsi
0x18004b87e  mov     rcx, rdi
0x18004b881  call    BfspCopyFile
0x18004b886  mov     ebx, eax
0x18004b888  test    eax, eax
0x18004b88a  jnz     short loc_18004B8CD
0x18004b88c  call    cs:__imp_GetLastError
0x18004b892  mov     r9, rsi
0x18004b895  lea     rdx, aErrorCopyingST; "Error copying %s to %s. Last Error = %#"...
0x18004b89c  mov     r8, rdi
0x18004b89f  mov     [rsp+78h+var_58], eax
0x18004b8a3  mov     ecx, 4
0x18004b8a8  call    BfspLogMessage
0x18004b8ad  jmp     loc_18004B93E
0x18004b8b2  lea     r9, aBootStl; "boot.stl"
0x18004b8b9  mov     r8, rdi
0x18004b8bc  lea     rdx, aSourceBootStlS; "Source Boot.stl (%s) does not exist. Wi"...
0x18004b8c3  mov     ecx, 3
0x18004b8c8  call    BfspLogMessage
0x18004b8cd  lea     r8, aBootStl; "boot.stl"
0x18004b8d4  mov     rdx, r15; unsigned __int64
0x18004b8d7  mov     rcx, r14; unsigned __int16 *
0x18004b8da  test    ebp, ebp
0x18004b8dc  jnz     short loc_18004B8E5
0x18004b8de  lea     r8, aBootPndStl; "boot.pnd.stl"
0x18004b8e5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b8ea  lea     r8, aBootPndStl; "boot.pnd.stl"
0x18004b8f1  mov     rdx, r15; unsigned __int64
0x18004b8f4  mov     rcx, r12; unsigned __int16 *
0x18004b8f7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b8fc  mov     rcx, rdi
0x18004b8ff  call    BfspFileExists
0x18004b904  test    eax, eax
0x18004b906  jz      short loc_18004B91E
0x18004b908  mov     rdx, rsi
0x18004b90b  mov     rcx, rdi
0x18004b90e  call    BfspCopyFile
0x18004b913  mov     ebx, eax
0x18004b915  test    eax, eax
0x18004b917  jnz     short loc_18004B93E
0x18004b919  jmp     loc_18004B88C
0x18004b91e  lea     r9, aBootPndStl; "boot.pnd.stl"
0x18004b925  mov     r8, rdi
0x18004b928  lea     rdx, aSourcePendingB; "Source Pending Boot.stl (%s) does not e"...
0x18004b92f  mov     ecx, 3
0x18004b934  call    BfspLogMessage
0x18004b939  mov     ebx, 1
0x18004b93e  call    cs:__imp_GetProcessHeap
0x18004b944  mov     r8, rsi; lpMem
0x18004b947  xor     edx, edx; dwFlags
0x18004b949  mov     rcx, rax; hHeap
0x18004b94c  call    cs:__imp_HeapFree
0x18004b952  call    cs:__imp_GetProcessHeap
0x18004b958  mov     r8, rdi; lpMem
0x18004b95b  xor     edx, edx; dwFlags
0x18004b95d  mov     rcx, rax; hHeap
0x18004b960  call    cs:__imp_HeapFree
0x18004b966  mov     eax, ebx
0x18004b968  add     rsp, 38h
0x18004b96c  pop     r15
0x18004b96e  pop     r14
0x18004b970  pop     r13
0x18004b972  pop     r12
0x18004b974  pop     rdi
0x18004b975  pop     rsi
0x18004b976  pop     rbp
0x18004b977  pop     rbx
0x18004b978  retn
```
