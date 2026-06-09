# BfeSidCopy

- ea: `0x1800385a0`
- end: `0x180038703`
- name: `BfeSidCopy`
- size: `355`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004b49c`
- `0x18004cce8`

## callees

- `0x18000e7e0`
- `0x180012d8c`
- `0x1800135ac`
- `0x1800197d0`
- `0x1800385a0`
- `0x18004fb50`
- `0x1800560f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800385f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800385f4`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800386eb`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800386eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038641`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800385cb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800385cb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003862c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003862c`

## string_xrefs

- `0x180038650`: `CopySid`
- `0x18003869c`: `BfeSidCopy`

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
0x1800385a0  mov     [rsp+arg_8], rbx
0x1800385a5  mov     [rsp+arg_10], rbp
0x1800385aa  push    rsi
0x1800385ab  push    rdi
0x1800385ac  push    r14
0x1800385ae  sub     rsp, 20h
0x1800385b2  xor     ebx, ebx
0x1800385b4  mov     r14, rdx
0x1800385b7  mov     [rsp+38h+arg_0], rbx
0x1800385bc  mov     rsi, rcx
0x1800385bf  mov     [rdx], rbx
0x1800385c2  test    rcx, rcx
0x1800385c5  jz      loc_180038664
0x1800385cb  call    cs:__imp_GetLengthSid
0x1800385d2  nop     dword ptr [rax+rax+00h]
0x1800385d7  mov     ebp, eax
0x1800385d9  mov     ebx, eax
0x1800385db  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x1800385e0  xor     edx, edx; dwFlags
0x1800385e2  test    eax, eax
0x1800385e4  jnz     loc_18003867B
0x1800385ea  mov     rcx, cs:gWfpHeap; hHeap
0x1800385f1  mov     r8d, ebx; dwBytes
0x1800385f4  call    cs:__imp_HeapAlloc
0x1800385fb  nop     dword ptr [rax+rax+00h]
0x180038600  mov     [rsp+38h+arg_0], rax
0x180038605  mov     rdi, rax
0x180038608  test    rax, rax
0x18003860b  jz      loc_1800386AD
0x180038611  xor     ebx, ebx
0x180038613  cmp     cs:gWfpTrackHeapBytes, ebx
0x180038619  jnz     loc_1800386DF
0x18003861f  test    rbx, rbx
0x180038622  jnz     short loc_180038692
0x180038624  mov     r8, rsi; pSourceSid
0x180038627  mov     rdx, rdi; pDestinationSid
0x18003862a  mov     ecx, ebp; nDestinationSidLength
0x18003862c  call    cs:__imp_CopySid
0x180038633  nop     dword ptr [rax+rax+00h]
0x180038638  test    eax, eax
0x18003863a  jz      short loc_180038641
0x18003863c  mov     [r14], rdi
0x18003863f  jmp     short loc_180038664
0x180038641  call    cs:__imp_GetLastError
0x180038648  nop     dword ptr [rax+rax+00h]
0x18003864d  mov     r8d, eax
0x180038650  lea     rdx, aCopysid; "CopySid"
0x180038657  call    WfpReportSysErrorAsWinError
0x18003865c  mov     rbx, rax
0x18003865f  test    rax, rax
0x180038662  jnz     short loc_180038692
0x180038664  mov     rbp, [rsp+38h+arg_10]
0x180038669  mov     rax, rbx
0x18003866c  mov     rbx, [rsp+38h+arg_8]
0x180038671  add     rsp, 20h
0x180038675  pop     r14
0x180038677  pop     rdi
0x180038678  pop     rsi
0x180038679  retn
0x18003867b  lea     r8, [rsp+38h+arg_0]
0x180038680  mov     rcx, rbx; dwBytes
0x180038683  call    WfpMemAlloc25B
0x180038688  mov     rdi, [rsp+38h+arg_0]
0x18003868d  mov     rbx, rax
0x180038690  jmp     short loc_18003861F
0x180038692  lea     rcx, [rsp+38h+arg_0]
0x180038697  call    WfpMemFree
0x18003869c  lea     rdx, aBfesidcopy; "BfeSidCopy"
0x1800386a3  mov     rcx, rbx
0x1800386a6  call    WfpReportError
0x1800386ab  jmp     short loc_180038664
0x1800386ad  mov     r8d, 0C0000017h
0x1800386b3  lea     rdx, aHeapalloc; "HeapAlloc"
0x1800386ba  call    WfpReportSysErrorAsNtStatus
0x1800386bf  mov     rbx, rax
0x1800386c2  test    rax, rax
0x1800386c5  jz      loc_18003861F
0x1800386cb  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x1800386d2  mov     rcx, rax
0x1800386d5  call    WfpReportError
0x1800386da  jmp     loc_18003861F
0x1800386df  mov     rcx, cs:gWfpHeap; hHeap
0x1800386e6  mov     r8, rax; lpMem
0x1800386e9  xor     edx, edx; dwFlags
0x1800386eb  call    cs:__imp_HeapSize
0x1800386f2  nop     dword ptr [rax+rax+00h]
0x1800386f7  lock add cs:gWfpHeapBytesAllocated, eax
0x1800386fe  jmp     loc_18003861F
```
