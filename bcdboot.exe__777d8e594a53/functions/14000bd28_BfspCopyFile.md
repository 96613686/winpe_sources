# BfspCopyFile

- ea: `0x14000bd28`
- end: `0x14000c01b`
- name: `BfspCopyFile`
- size: `755`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140009fd4`
- `0x14000b57c`
- `0x14000c8d8`
- `0x14000d494`

## callees

- `0x140003368`
- `0x14000bd28`
- `0x14000db18`
- `0x14000e628`
- `0x140011b18`
- `0x140012810`
- `0x140012cec`
- `0x140026650`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x14000bd67`
- `RPCRT4!UuidCreate` at `0x14000bd67`
- `KERNEL32!SetLastError` at `0x14000bf3c`
- `KERNEL32!SetLastError` at `0x14000bf58`
- `KERNEL32!SetLastError` at `0x14000bfe3`
- `KERNEL32!SetLastError` at `0x14000bf3c`
- `KERNEL32!SetLastError` at `0x14000bf58`
- `KERNEL32!SetLastError` at `0x14000bfe3`
- `KERNEL32!GetLastError` at `0x14000be49`
- `KERNEL32!GetLastError` at `0x14000bef0`
- `KERNEL32!GetLastError` at `0x14000befe`
- `KERNEL32!GetLastError` at `0x14000bf61`
- `KERNEL32!GetLastError` at `0x14000be49`
- `KERNEL32!GetLastError` at `0x14000bef0`
- `KERNEL32!GetLastError` at `0x14000befe`
- `KERNEL32!GetLastError` at `0x14000bf61`
- `KERNEL32!HeapFree` at `0x14000be82`
- `KERNEL32!HeapFree` at `0x14000bf1a`
- `KERNEL32!HeapFree` at `0x14000bf33`
- `KERNEL32!HeapFree` at `0x14000be82`
- `KERNEL32!HeapFree` at `0x14000bf1a`
- `KERNEL32!HeapFree` at `0x14000bf33`
- `KERNEL32!HeapAlloc` at `0x14000bd9c`
- `KERNEL32!HeapAlloc` at `0x14000bd9c`
- `KERNEL32!GetProcessHeap` at `0x14000bd8b`
- `KERNEL32!GetProcessHeap` at `0x14000be74`
- `KERNEL32!GetProcessHeap` at `0x14000bf0c`
- `KERNEL32!GetProcessHeap` at `0x14000bf25`
- `KERNEL32!GetProcessHeap` at `0x14000bd8b`
- `KERNEL32!GetProcessHeap` at `0x14000be74`
- `KERNEL32!GetProcessHeap` at `0x14000bf0c`
- `KERNEL32!GetProcessHeap` at `0x14000bf25`
- `KERNEL32!Sleep` at `0x14000bfdb`
- `KERNEL32!Sleep` at `0x14000bfdb`
- `KERNEL32!GetFileAttributesW` at `0x14000becb`
- `KERNEL32!GetFileAttributesW` at `0x14000becb`
- `KERNEL32!MoveFileExW` at `0x14000be30`
- `KERNEL32!MoveFileExW` at `0x14000be6e`
- `KERNEL32!MoveFileExW` at `0x14000be30`
- `KERNEL32!MoveFileExW` at `0x14000be6e`

## string_xrefs

- `0x14000bf99`: `BfspCopyFile(%s, %s) failed! (Attempt %d of %d) Last Error = %#x`
- `0x14000be52`: `BfspCopyFile failed to delete temporary file (%s)! Last Error = %#x.`

## pseudocode

```c
__int64 __fastcall BfspCopyFile(STRSAFE_LPCWSTR pszSrc, LPCWSTR lpFileName)
{
  const wchar_t *v2; // r14
  __int64 v4; // rax
  SIZE_T v5; // rbx
  HANDLE ProcessHeap; // rax
  wchar_t *v7; // r12
  DWORD LastError; // eax
  HANDLE v9; // rax
  unsigned int v10; // edi
  unsigned int v11; // esi
  wchar_t *v12; // r14
  const WCHAR *v13; // rax
  wchar_t *v14; // rbx
  DWORD v15; // r15d
  HANDLE v16; // rax
  HANDLE v17; // rax
  DWORD v18; // eax
  DWORD v19; // ebx
  DWORD v20; // ecx
  __int64 v22; // [rsp+20h] [rbp-69h]
  __int64 v23; // [rsp+28h] [rbp-61h]
  __int64 v24; // [rsp+30h] [rbp-59h]
  UUID Uuid; // [rsp+90h] [rbp+7h] BYREF

  v2 = pszSrc;
  Uuid = 0;
  UuidCreate(&Uuid);
  v4 = -1;
  do
    ++v4;
  while ( lpFileName[v4] );
  v5 = 2 * v4 + 80;
  ProcessHeap = GetProcessHeap();
  v7 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v5);
  if ( v7 )
  {
    LODWORD(v22) = Uuid.Data1;
    StringCbPrintfW(v7, v5, L"%ws.{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}", lpFileName);
    if ( MoveFileExW(lpFileName, v7, 0) && !(unsigned int)DeleteFileEx2(v7) )
    {
      LastError = GetLastError();
      BfspLogMessage(3, L"BfspCopyFile failed to delete temporary file (%s)! Last Error = %#x.", v7, LastError);
      MoveFileExW(v7, 0, 4u);
    }
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v7);
    v2 = pszSrc;
  }
  v10 = 0;
  do
  {
    if ( !v2 || !lpFileName )
    {
      SetLastError(0x57u);
      v11 = 0;
      goto LABEL_23;
    }
    v11 = 0;
    v12 = (wchar_t *)PrepareUnicodePathEx(v2);
    if ( v12 )
    {
      v13 = (const WCHAR *)PrepareUnicodePathEx(lpFileName);
      v14 = (wchar_t *)v13;
      if ( v13 )
      {
        if ( GetFileAttributesW(v13) != -1 )
          DeleteFileEx2(v14);
        v11 = WdsCopyFileEx(v12, v14, v22, 0);
        v15 = GetLastError();
LABEL_18:
        v16 = GetProcessHeap();
        HeapFree(v16, 0, v12);
        if ( v14 )
        {
          v17 = GetProcessHeap();
          HeapFree(v17, 0, v14);
        }
        goto LABEL_20;
      }
    }
    else
    {
      v14 = 0;
    }
    v15 = GetLastError();
    if ( v12 )
      goto LABEL_18;
LABEL_20:
    SetLastError(v15);
    if ( v11 )
      return v11;
    v2 = pszSrc;
LABEL_23:
    v18 = GetLastError();
    v19 = v18;
    if ( (v18 == 5 || v18 - 32 <= 1) && ((BfspPrintFileOwnerProcess(v2), v19 == 5) || v19 == 32) || v19 == 33 )
      BfspPrintFileOwnerProcess(lpFileName);
    LODWORD(v24) = v19;
    ++v10;
    LODWORD(v23) = 60;
    LODWORD(v22) = v10;
    BfspLogMessage(
      4,
      L"BfspCopyFile(%s, %s) failed! (Attempt %d of %d) Last Error = %#x",
      v2,
      lpFileName,
      v22,
      v23,
      v24);
    if ( v10 < 0x3C )
    {
      v20 = *((_DWORD *)BfspRetryWaitInMilliseconds + v10 / 0xA);
      if ( v20 )
        Sleep(v20);
    }
    SetLastError(v19);
  }
  while ( v10 < 0x3C );
  return v11;
}

```

## disassembly

```asm
0x14000bd28  mov     [rsp-8+arg_10], rbx
0x14000bd2d  push    rbp
0x14000bd2e  push    rsi
0x14000bd2f  push    rdi
0x14000bd30  push    r12
0x14000bd32  push    r13
0x14000bd34  push    r14
0x14000bd36  push    r15
0x14000bd38  lea     rbp, [rsp-27h]
0x14000bd3d  sub     rsp, 0B0h
0x14000bd44  mov     rax, cs:__security_cookie
0x14000bd4b  xor     rax, rsp
0x14000bd4e  mov     [rbp+57h+var_40], rax
0x14000bd52  mov     r14, rcx
0x14000bd55  mov     [rbp+57h+lpFileName], rcx
0x14000bd59  xorps   xmm0, xmm0
0x14000bd5c  lea     rcx, [rbp+57h+Uuid]; Uuid
0x14000bd60  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x14000bd64  mov     r13, rdx
0x14000bd67  call    cs:__imp_UuidCreate
0x14000bd6d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000bd71  xor     r15d, r15d
0x14000bd74  inc     rax
0x14000bd77  cmp     [r13+rax*2+0], r15w
0x14000bd7d  jnz     short loc_14000BD74
0x14000bd7f  lea     rbx, ds:50h[rax*2]
0x14000bd87  mov     [rbp+57h+cbDest], rbx
0x14000bd8b  call    cs:__imp_GetProcessHeap
0x14000bd91  mov     r8, rbx; dwBytes
0x14000bd94  mov     edx, 8; dwFlags
0x14000bd99  mov     rcx, rax; hHeap
0x14000bd9c  call    cs:__imp_HeapAlloc
0x14000bda2  mov     r12, rax
0x14000bda5  test    rax, rax
0x14000bda8  jz      loc_14000BE8C
0x14000bdae  movzx   ecx, [rbp+57h+Uuid.Data4+7]
0x14000bdb2  movzx   r8d, [rbp+57h+Uuid.Data4+6]
0x14000bdb7  movzx   r9d, [rbp+57h+Uuid.Data4+5]
0x14000bdbc  movzx   r10d, [rbp+57h+Uuid.Data4+4]
0x14000bdc1  movzx   r11d, [rbp+57h+Uuid.Data4+3]
0x14000bdc6  movzx   ebx, [rbp+57h+Uuid.Data4+2]
0x14000bdca  movzx   edi, [rbp+57h+Uuid.Data4+1]
0x14000bdce  movzx   esi, [rbp+57h+Uuid.Data4]
0x14000bdd2  movzx   r14d, [rbp+57h+Uuid.Data3]
0x14000bdd7  movzx   r15d, [rbp+57h+Uuid.Data2]
0x14000bddc  mov     eax, [rbp+57h+Uuid.Data1]
0x14000bddf  mov     rdx, [rbp+57h+cbDest]; cbDest
0x14000bde3  mov     [rsp+0E0h+var_70], ecx
0x14000bde7  mov     rcx, r12; pszDest
0x14000bdea  mov     [rsp+0E0h+var_78], r8d
0x14000bdef  lea     r8, aWs8x4x4x2x2x2x; "%ws.{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%."...
0x14000bdf6  mov     [rsp+0E0h+var_80], r9d
0x14000bdfb  mov     r9, r13
0x14000bdfe  mov     [rsp+0E0h+var_88], r10d
0x14000be03  mov     [rsp+0E0h+var_90], r11d
0x14000be08  mov     [rsp+0E0h+var_98], ebx
0x14000be0c  mov     [rsp+0E0h+var_A0], edi
0x14000be10  mov     [rsp+0E0h+var_A8], esi
0x14000be14  mov     dword ptr [rsp+0E0h+var_B0], r14d
0x14000be19  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x14000be1e  mov     dword ptr [rsp+0E0h+var_C0], eax; int
0x14000be22  call    StringCbPrintfW
0x14000be27  xor     r8d, r8d; dwFlags
0x14000be2a  mov     rdx, r12; lpNewFileName
0x14000be2d  mov     rcx, r13; lpExistingFileName
0x14000be30  call    cs:__imp_MoveFileExW
0x14000be36  xor     r15d, r15d
0x14000be39  test    eax, eax
0x14000be3b  jz      short loc_14000BE74
0x14000be3d  mov     rcx, r12
0x14000be40  call    DeleteFileEx2
0x14000be45  test    eax, eax
0x14000be47  jnz     short loc_14000BE74
0x14000be49  call    cs:__imp_GetLastError
0x14000be4f  mov     r8, r12
0x14000be52  lea     rdx, aBfspcopyfileFa; "BfspCopyFile failed to delete temporary"...
0x14000be59  mov     r9d, eax
0x14000be5c  lea     ecx, [r15+3]
0x14000be60  call    BfspLogMessage
0x14000be65  xor     edx, edx; lpNewFileName
0x14000be67  lea     r8d, [r15+4]; dwFlags
0x14000be6b  mov     rcx, r12; lpExistingFileName
0x14000be6e  call    cs:__imp_MoveFileExW
0x14000be74  call    cs:__imp_GetProcessHeap
0x14000be7a  mov     r8, r12; lpMem
0x14000be7d  xor     edx, edx; dwFlags
0x14000be7f  mov     rcx, rax; hHeap
0x14000be82  call    cs:__imp_HeapFree
0x14000be88  mov     r14, [rbp+57h+lpFileName]
0x14000be8c  mov     edi, r15d
0x14000be8f  test    r14, r14
0x14000be92  jz      loc_14000BF53
0x14000be98  test    r13, r13
0x14000be9b  jz      loc_14000BF53
0x14000bea1  xor     edx, edx
0x14000bea3  mov     rcx, r14; pszSrc
0x14000bea6  mov     esi, r15d
0x14000bea9  call    PrepareUnicodePathEx
0x14000beae  mov     r14, rax
0x14000beb1  test    rax, rax
0x14000beb4  jz      short loc_14000BEFB
0x14000beb6  xor     edx, edx
0x14000beb8  mov     rcx, r13; pszSrc
0x14000bebb  call    PrepareUnicodePathEx
0x14000bec0  mov     rbx, rax
0x14000bec3  test    rax, rax
0x14000bec6  jz      short loc_14000BEFE
0x14000bec8  mov     rcx, rax; lpFileName
0x14000becb  call    cs:__imp_GetFileAttributesW
0x14000bed1  cmp     eax, 0FFFFFFFFh
0x14000bed4  jz      short loc_14000BEDE
0x14000bed6  mov     rcx, rbx
0x14000bed9  call    DeleteFileEx2
0x14000bede  mov     rdx, rbx; STRSAFE_LPCWSTR
0x14000bee1  mov     dword ptr [rsp+0E0h+var_B8], r15d; int
0x14000bee6  mov     rcx, r14; pszSrc
0x14000bee9  call    WdsCopyFileEx
0x14000beee  mov     esi, eax
0x14000bef0  call    cs:__imp_GetLastError
0x14000bef6  mov     r15d, eax
0x14000bef9  jmp     short loc_14000BF0C
0x14000befb  mov     rbx, r15
0x14000befe  call    cs:__imp_GetLastError
0x14000bf04  mov     r15d, eax
0x14000bf07  test    r14, r14
0x14000bf0a  jz      short loc_14000BF39
0x14000bf0c  call    cs:__imp_GetProcessHeap
0x14000bf12  mov     r8, r14; lpMem
0x14000bf15  xor     edx, edx; dwFlags
0x14000bf17  mov     rcx, rax; hHeap
0x14000bf1a  call    cs:__imp_HeapFree
0x14000bf20  test    rbx, rbx
0x14000bf23  jz      short loc_14000BF39
0x14000bf25  call    cs:__imp_GetProcessHeap
0x14000bf2b  mov     r8, rbx; lpMem
0x14000bf2e  xor     edx, edx; dwFlags
0x14000bf30  mov     rcx, rax; hHeap
0x14000bf33  call    cs:__imp_HeapFree
0x14000bf39  mov     ecx, r15d; dwErrCode
0x14000bf3c  call    cs:__imp_SetLastError
0x14000bf42  xor     r15d, r15d
0x14000bf45  test    esi, esi
0x14000bf47  jnz     loc_14000BFF2
0x14000bf4d  mov     r14, [rbp+57h+lpFileName]
0x14000bf51  jmp     short loc_14000BF61
0x14000bf53  mov     ecx, 57h ; 'W'; dwErrCode
0x14000bf58  call    cs:__imp_SetLastError
0x14000bf5e  mov     esi, r15d
0x14000bf61  call    cs:__imp_GetLastError
0x14000bf67  mov     ebx, eax
0x14000bf69  cmp     eax, 5
0x14000bf6c  jz      short loc_14000BF76
0x14000bf6e  lea     ecx, [rax-20h]
0x14000bf71  cmp     ecx, 1
0x14000bf74  ja      short loc_14000BF88
0x14000bf76  mov     rcx, r14; lpFileName
0x14000bf79  call    BfspPrintFileOwnerProcess
0x14000bf7e  cmp     ebx, 5
0x14000bf81  jz      short loc_14000BF8D
0x14000bf83  cmp     ebx, 20h ; ' '
0x14000bf86  jz      short loc_14000BF8D
0x14000bf88  cmp     ebx, 21h ; '!'
0x14000bf8b  jnz     short loc_14000BF95
0x14000bf8d  mov     rcx, r13; lpFileName
0x14000bf90  call    BfspPrintFileOwnerProcess
0x14000bf95  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x14000bf99  lea     rdx, aBfspcopyfileSS; "BfspCopyFile(%s, %s) failed! (Attempt %"...
0x14000bfa0  inc     edi
0x14000bfa2  mov     dword ptr [rsp+0E0h+var_B8], 3Ch ; '<'
0x14000bfaa  mov     r9, r13
0x14000bfad  mov     dword ptr [rsp+0E0h+var_C0], edi
0x14000bfb1  mov     r8, r14
0x14000bfb4  mov     ecx, 4
0x14000bfb9  call    BfspLogMessage
0x14000bfbe  cmp     edi, 3Ch ; '<'
0x14000bfc1  jnb     short loc_14000BFE1
0x14000bfc3  mov     eax, 0CCCCCCCDh
0x14000bfc8  lea     rcx, BfspRetryWaitInMilliseconds
0x14000bfcf  mul     edi
0x14000bfd1  shr     edx, 3
0x14000bfd4  mov     ecx, [rcx+rdx*4]; dwMilliseconds
0x14000bfd7  test    ecx, ecx
0x14000bfd9  jz      short loc_14000BFE1
0x14000bfdb  call    cs:__imp_Sleep
0x14000bfe1  mov     ecx, ebx; dwErrCode
0x14000bfe3  call    cs:__imp_SetLastError
0x14000bfe9  cmp     edi, 3Ch ; '<'
0x14000bfec  jb      loc_14000BE8F
0x14000bff2  mov     eax, esi
0x14000bff4  mov     rcx, [rbp+57h+var_40]
0x14000bff8  xor     rcx, rsp; StackCookie
0x14000bffb  call    __security_check_cookie
0x14000c000  mov     rbx, [rsp+0E0h+arg_10]
0x14000c008  add     rsp, 0B0h
0x14000c00f  pop     r15
0x14000c011  pop     r14
0x14000c013  pop     r13
0x14000c015  pop     r12
0x14000c017  pop     rdi
0x14000c018  pop     rsi
0x14000c019  pop     rbp
0x14000c01a  retn
```
