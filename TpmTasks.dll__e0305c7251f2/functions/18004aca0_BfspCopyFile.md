# BfspCopyFile

- ea: `0x18004aca0`
- end: `0x18004aebb`
- name: `BfspCopyFile`
- size: `539`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180049234`
- `0x18004a678`
- `0x18004b700`
- `0x18004c194`

## callees

- `0x1800078b0`
- `0x180047280`
- `0x18004aca0`
- `0x18004c658`
- `0x18004cdd4`
- `0x1800538b8`
- `0x180053994`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004ae7b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004ae7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004adfa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004adfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ad03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004adec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ad03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004adec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ad14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ad14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ae83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ae83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004adc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ae1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004adc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ae1b`
- `RPCRT4!UuidCreate` at `0x18004acdf`
- `RPCRT4!UuidCreate` at `0x18004acdf`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18004ada8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18004ade6`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18004ada8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18004ade6`

## string_xrefs

- `0x18004adca`: `BfspCopyFile failed to delete temporary file (%s)! Last Error = %#x.`
- `0x18004ae3b`: `BfspCopyFile(%s, %s) failed! (Attempt %d of %d) Last Error = %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=279
__int64 __fastcall BfspCopyFile(__int64 a1, const WCHAR *a2)
{
  __int64 v2; // r14
  __int64 v4; // rax
  SIZE_T v5; // rbx
  HANDLE ProcessHeap; // rax
  wchar_t *v7; // r12
  DWORD LastError; // eax
  HANDLE v9; // rax
  unsigned int v10; // ebx
  unsigned int v11; // esi
  __int64 v12; // rdi
  DWORD v13; // ecx
  __int64 v15; // [rsp+20h] [rbp-69h]
  __int64 v16; // [rsp+28h] [rbp-61h]
  __int64 v17; // [rsp+30h] [rbp-59h]
  UUID Uuid; // [rsp+90h] [rbp+7h] BYREF

  v2 = a1;
  Uuid = 0;
  UuidCreate(&Uuid);
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = 2 * v4 + 80;
  ProcessHeap = GetProcessHeap();
  v7 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v5);
  if ( v7 )
  {
    StringCbPrintfW(
      v7,
      v5,
      L"%ws.{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
      a2,
      Uuid.Data1,
      Uuid.Data2,
      Uuid.Data3,
      Uuid.Data4[0],
      Uuid.Data4[1],
      Uuid.Data4[2],
      Uuid.Data4[3],
      Uuid.Data4[4],
      Uuid.Data4[5],
      Uuid.Data4[6],
      Uuid.Data4[7]);
    if ( MoveFileExW(a2, v7, 0) && !(unsigned int)DeleteFileEx2(v7) )
    {
      LastError = GetLastError();
      BfspLogMessage(3, L"BfspCopyFile failed to delete temporary file (%s)! Last Error = %#x.", v7, LastError);
      MoveFileExW(v7, 0, 4u);
    }
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v7);
    v2 = a1;
  }
  v10 = 0;
  do
  {
    v11 = CopyFileWithAttributesEx2(v2, a2, 0);
    if ( v11 )
      break;
    v12 = GetLastError();
    BfspPrintOwnerProcessOnSharingError(v2, v12);
    BfspPrintOwnerProcessOnSharingError(a2, (unsigned int)v12);
    LODWORD(v17) = v12;
    ++v10;
    LODWORD(v16) = 60;
    LODWORD(v15) = v10;
    BfspLogMessage(4, L"BfspCopyFile(%s, %s) failed! (Attempt %d of %d) Last Error = %#x", v2, a2, v15, v16, v17);
    if ( v10 < 0x3C )
    {
      v13 = *((_DWORD *)BfspRetryWaitInMilliseconds + v10 / 0xA);
      if ( v13 )
        Sleep(v13);
    }
    SetLastError(v12);
  }
  while ( v10 < 0x3C );
  return v11;
}

```

## disassembly

```asm
0x18004aca0  mov     [rsp-8+arg_10], rbx
0x18004aca5  push    rbp
0x18004aca6  push    rsi
0x18004aca7  push    rdi
0x18004aca8  push    r12
0x18004acaa  push    r13
0x18004acac  push    r14
0x18004acae  push    r15
0x18004acb0  lea     rbp, [rsp-27h]
0x18004acb5  sub     rsp, 0B0h
0x18004acbc  mov     rax, cs:__security_cookie
0x18004acc3  xor     rax, rsp
0x18004acc6  mov     [rbp+57h+var_40], rax
0x18004acca  mov     r14, rcx
0x18004accd  mov     [rbp+57h+var_58], rcx
0x18004acd1  xorps   xmm0, xmm0
0x18004acd4  lea     rcx, [rbp+57h+Uuid]; Uuid
0x18004acd8  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18004acdc  mov     r13, rdx
0x18004acdf  call    cs:__imp_UuidCreate
0x18004ace5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004ace9  xor     r15d, r15d
0x18004acec  inc     rax
0x18004acef  cmp     [r13+rax*2+0], r15w
0x18004acf5  jnz     short loc_18004ACEC
0x18004acf7  lea     rbx, ds:50h[rax*2]
0x18004acff  mov     [rbp+57h+cbDest], rbx
0x18004ad03  call    cs:__imp_GetProcessHeap
0x18004ad09  mov     r8, rbx; dwBytes
0x18004ad0c  mov     edx, 8; dwFlags
0x18004ad11  mov     rcx, rax; hHeap
0x18004ad14  call    cs:__imp_HeapAlloc
0x18004ad1a  mov     r12, rax
0x18004ad1d  test    rax, rax
0x18004ad20  jz      loc_18004AE04
0x18004ad26  movzx   ecx, [rbp+57h+Uuid.Data4+7]
0x18004ad2a  movzx   r8d, [rbp+57h+Uuid.Data4+6]
0x18004ad2f  movzx   r9d, [rbp+57h+Uuid.Data4+5]
0x18004ad34  movzx   r10d, [rbp+57h+Uuid.Data4+4]
0x18004ad39  movzx   r11d, [rbp+57h+Uuid.Data4+3]
0x18004ad3e  movzx   ebx, [rbp+57h+Uuid.Data4+2]
0x18004ad42  movzx   edi, [rbp+57h+Uuid.Data4+1]
0x18004ad46  movzx   esi, [rbp+57h+Uuid.Data4]
0x18004ad4a  movzx   r14d, [rbp+57h+Uuid.Data3]
0x18004ad4f  movzx   r15d, [rbp+57h+Uuid.Data2]
0x18004ad54  mov     eax, [rbp+57h+Uuid.Data1]
0x18004ad57  mov     rdx, [rbp+57h+cbDest]; cbDest
0x18004ad5b  mov     [rsp+0E0h+var_70], ecx
0x18004ad5f  mov     rcx, r12; pszDest
0x18004ad62  mov     [rsp+0E0h+var_78], r8d
0x18004ad67  lea     r8, aWs8x4x4x2x2x2x; "%ws.{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%."...
0x18004ad6e  mov     [rsp+0E0h+var_80], r9d
0x18004ad73  mov     r9, r13
0x18004ad76  mov     [rsp+0E0h+var_88], r10d
0x18004ad7b  mov     [rsp+0E0h+var_90], r11d
0x18004ad80  mov     [rsp+0E0h+var_98], ebx
0x18004ad84  mov     [rsp+0E0h+var_A0], edi
0x18004ad88  mov     [rsp+0E0h+var_A8], esi
0x18004ad8c  mov     dword ptr [rsp+0E0h+var_B0], r14d
0x18004ad91  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x18004ad96  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18004ad9a  call    StringCbPrintfW
0x18004ad9f  xor     r8d, r8d; dwFlags
0x18004ada2  mov     rdx, r12; lpNewFileName
0x18004ada5  mov     rcx, r13; lpExistingFileName
0x18004ada8  call    cs:__imp_MoveFileExW
0x18004adae  xor     r15d, r15d
0x18004adb1  test    eax, eax
0x18004adb3  jz      short loc_18004ADEC
0x18004adb5  mov     rcx, r12
0x18004adb8  call    DeleteFileEx2
0x18004adbd  test    eax, eax
0x18004adbf  jnz     short loc_18004ADEC
0x18004adc1  call    cs:__imp_GetLastError
0x18004adc7  mov     r8, r12
0x18004adca  lea     rdx, aBfspcopyfileFa; "BfspCopyFile failed to delete temporary"...
0x18004add1  mov     r9d, eax
0x18004add4  lea     ecx, [r15+3]
0x18004add8  call    BfspLogMessage
0x18004addd  xor     edx, edx; lpNewFileName
0x18004addf  lea     r8d, [r15+4]; dwFlags
0x18004ade3  mov     rcx, r12; lpExistingFileName
0x18004ade6  call    cs:__imp_MoveFileExW
0x18004adec  call    cs:__imp_GetProcessHeap
0x18004adf2  mov     r8, r12; lpMem
0x18004adf5  xor     edx, edx; dwFlags
0x18004adf7  mov     rcx, rax; hHeap
0x18004adfa  call    cs:__imp_HeapFree
0x18004ae00  mov     r14, [rbp+57h+var_58]
0x18004ae04  mov     ebx, r15d
0x18004ae07  xor     r8d, r8d
0x18004ae0a  mov     rdx, r13
0x18004ae0d  mov     rcx, r14
0x18004ae10  call    CopyFileWithAttributesEx2
0x18004ae15  mov     esi, eax
0x18004ae17  test    eax, eax
0x18004ae19  jnz     short loc_18004AE92
0x18004ae1b  call    cs:__imp_GetLastError
0x18004ae21  mov     edx, eax
0x18004ae23  mov     rcx, r14
0x18004ae26  mov     edi, eax
0x18004ae28  call    BfspPrintOwnerProcessOnSharingError
0x18004ae2d  mov     edx, edi
0x18004ae2f  mov     rcx, r13
0x18004ae32  call    BfspPrintOwnerProcessOnSharingError
0x18004ae37  mov     dword ptr [rsp+0E0h+var_B0], edi
0x18004ae3b  lea     rdx, aBfspcopyfileSS; "BfspCopyFile(%s, %s) failed! (Attempt %"...
0x18004ae42  inc     ebx
0x18004ae44  mov     dword ptr [rsp+0E0h+var_B8], 3Ch ; '<'
0x18004ae4c  mov     r9, r13
0x18004ae4f  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18004ae53  mov     r8, r14
0x18004ae56  lea     ecx, [rsi+4]
0x18004ae59  call    BfspLogMessage
0x18004ae5e  cmp     ebx, 3Ch ; '<'
0x18004ae61  jnb     short loc_18004AE81
0x18004ae63  mov     eax, 0CCCCCCCDh
0x18004ae68  lea     rcx, BfspRetryWaitInMilliseconds
0x18004ae6f  mul     ebx
0x18004ae71  shr     edx, 3
0x18004ae74  mov     ecx, [rcx+rdx*4]; dwMilliseconds
0x18004ae77  test    ecx, ecx
0x18004ae79  jz      short loc_18004AE81
0x18004ae7b  call    cs:__imp_Sleep
0x18004ae81  mov     ecx, edi; dwErrCode
0x18004ae83  call    cs:__imp_SetLastError
0x18004ae89  cmp     ebx, 3Ch ; '<'
0x18004ae8c  jb      loc_18004AE07
0x18004ae92  mov     eax, esi
0x18004ae94  mov     rcx, [rbp+57h+var_40]
0x18004ae98  xor     rcx, rsp; StackCookie
0x18004ae9b  call    __security_check_cookie
0x18004aea0  mov     rbx, [rsp+0E0h+arg_10]
0x18004aea8  add     rsp, 0B0h
0x18004aeaf  pop     r15
0x18004aeb1  pop     r14
0x18004aeb3  pop     r13
0x18004aeb5  pop     r12
0x18004aeb7  pop     rdi
0x18004aeb8  pop     rsi
0x18004aeb9  pop     rbp
0x18004aeba  retn
```
