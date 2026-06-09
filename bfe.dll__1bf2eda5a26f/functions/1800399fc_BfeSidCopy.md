# BfeSidCopy

- ea: `0x1800399fc`
- end: `0x180039b38`
- name: `BfeSidCopy`
- size: `316`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180034234`
- `0x18004aeb8`

## callees

- `0x18000e000`
- `0x18001236c`
- `0x180012b54`
- `0x180018b74`
- `0x1800399fc`
- `0x18004e230`
- `0x1800542bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039a42`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039a42`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180039b26`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180039b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a83`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180039a23`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180039a23`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180039a74`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180039a74`

## string_xrefs

- `0x180039a8c`: `CopySid`
- `0x180039ad7`: `BfeSidCopy`

## pseudocode

```c
__int64 __fastcall BfeSidCopy(PSID pSourceSid, _QWORD *a2)
{
  __int64 v2; // rbx
  SIZE_T LengthSid; // rbp
  void *v6; // rax
  __int64 v7; // rcx
  void *v8; // rdi
  DWORD LastError; // eax
  __int64 v10; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  void *v14; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  v14 = 0;
  *a2 = 0;
  if ( pSourceSid )
  {
    LengthSid = GetLengthSid(pSourceSid);
    if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
    {
      v12 = WfpMemAlloc25B(LengthSid);
      v8 = v14;
      v2 = v12;
    }
    else
    {
      v6 = HeapAlloc(gWfpHeap, 0, (unsigned int)LengthSid);
      v14 = v6;
      v8 = v6;
      if ( v6 )
      {
        v2 = 0;
        if ( gWfpTrackHeapBytes )
          _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v6));
      }
      else
      {
        v13 = WfpReportSysErrorAsNtStatus(v7, "HeapAlloc", 3221225495LL);
        v2 = v13;
        if ( v13 )
          WfpReportError(v13, "WfpMemAlloc");
      }
    }
    if ( !v2 )
    {
      if ( CopySid(LengthSid, v8, pSourceSid) )
      {
        *a2 = v8;
        return v2;
      }
      LastError = GetLastError();
      v2 = WfpReportSysErrorAsWinError(v10, "CopySid", LastError);
      if ( !v2 )
        return v2;
    }
    WfpMemFree(&v14);
    WfpReportError(v2, "BfeSidCopy");
  }
  return v2;
}

```

## disassembly

```asm
0x1800399fc  mov     [rsp+arg_8], rbx
0x180039a01  mov     [rsp+arg_10], rbp
0x180039a06  push    rsi
0x180039a07  push    rdi
0x180039a08  push    r14
0x180039a0a  sub     rsp, 20h
0x180039a0e  xor     ebx, ebx
0x180039a10  mov     r14, rdx
0x180039a13  mov     [rsp+38h+arg_0], rbx
0x180039a18  mov     rsi, rcx
0x180039a1b  mov     [rdx], rbx
0x180039a1e  test    rcx, rcx
0x180039a21  jz      short loc_180039AA0
0x180039a23  call    cs:__imp_GetLengthSid
0x180039a29  mov     ebp, eax
0x180039a2b  mov     ebx, eax
0x180039a2d  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180039a32  xor     edx, edx; dwFlags
0x180039a34  test    eax, eax
0x180039a36  jnz     short loc_180039AB6
0x180039a38  mov     rcx, cs:gWfpHeap; hHeap
0x180039a3f  mov     r8d, ebx; dwBytes
0x180039a42  call    cs:__imp_HeapAlloc
0x180039a48  mov     [rsp+38h+arg_0], rax
0x180039a4d  mov     rdi, rax
0x180039a50  test    rax, rax
0x180039a53  jz      loc_180039AE8
0x180039a59  xor     ebx, ebx
0x180039a5b  cmp     cs:gWfpTrackHeapBytes, ebx
0x180039a61  jnz     loc_180039B1A
0x180039a67  test    rbx, rbx
0x180039a6a  jnz     short loc_180039ACD
0x180039a6c  mov     r8, rsi; pSourceSid
0x180039a6f  mov     rdx, rdi; pDestinationSid
0x180039a72  mov     ecx, ebp; nDestinationSidLength
0x180039a74  call    cs:__imp_CopySid
0x180039a7a  test    eax, eax
0x180039a7c  jz      short loc_180039A83
0x180039a7e  mov     [r14], rdi
0x180039a81  jmp     short loc_180039AA0
0x180039a83  call    cs:__imp_GetLastError
0x180039a89  mov     r8d, eax
0x180039a8c  lea     rdx, aCopysid; "CopySid"
0x180039a93  call    WfpReportSysErrorAsWinError
0x180039a98  mov     rbx, rax
0x180039a9b  test    rax, rax
0x180039a9e  jnz     short loc_180039ACD
0x180039aa0  mov     rbp, [rsp+38h+arg_10]
0x180039aa5  mov     rax, rbx
0x180039aa8  mov     rbx, [rsp+38h+arg_8]
0x180039aad  add     rsp, 20h
0x180039ab1  pop     r14
0x180039ab3  pop     rdi
0x180039ab4  pop     rsi
0x180039ab5  retn
0x180039ab6  lea     r8, [rsp+38h+arg_0]
0x180039abb  mov     rcx, rbx; dwBytes
0x180039abe  call    WfpMemAlloc25B
0x180039ac3  mov     rdi, [rsp+38h+arg_0]
0x180039ac8  mov     rbx, rax
0x180039acb  jmp     short loc_180039A67
0x180039acd  lea     rcx, [rsp+38h+arg_0]
0x180039ad2  call    WfpMemFree
0x180039ad7  lea     rdx, aBfesidcopy; "BfeSidCopy"
0x180039ade  mov     rcx, rbx
0x180039ae1  call    WfpReportError
0x180039ae6  jmp     short loc_180039AA0
0x180039ae8  mov     r8d, 0C0000017h
0x180039aee  lea     rdx, aHeapalloc; "HeapAlloc"
0x180039af5  call    WfpReportSysErrorAsNtStatus
0x180039afa  mov     rbx, rax
0x180039afd  test    rax, rax
0x180039b00  jz      loc_180039A67
0x180039b06  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x180039b0d  mov     rcx, rax
0x180039b10  call    WfpReportError
0x180039b15  jmp     loc_180039A67
0x180039b1a  mov     rcx, cs:gWfpHeap; hHeap
0x180039b21  mov     r8, rax; lpMem
0x180039b24  xor     edx, edx; dwFlags
0x180039b26  call    cs:__imp_HeapSize
0x180039b2c  lock add cs:gWfpHeapBytesAllocated, eax
0x180039b33  jmp     loc_180039A67
```
