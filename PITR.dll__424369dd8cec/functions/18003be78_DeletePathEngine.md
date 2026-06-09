# DeletePathEngine

- ea: `0x18003be78`
- end: `0x18003bfa9`
- name: `DeletePathEngine`
- size: `305`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003bfb0`

## callees

- `0x18003a8d8`
- `0x18003b094`
- `0x18003be78`
- `0x18003c3b8`
- `0x18003cfe4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bf74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bf74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003bf82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003bf82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bedc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bf8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bedc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bf8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003befe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003befe`

## string_xrefs

- `0x18003bf2e`: `DeletePathEngine: Hit %u failure%s during recursive deletion of [%s]; 1st error = 0x%x, cd = [%s]`

## pseudocode

```c
__int64 __fastcall DeletePathEngine(const WCHAR *a1)
{
  unsigned int v2; // ebx
  void *CurrDirectory; // rbx
  HANDLE ProcessHeap; // rax
  __int64 dwErrCode; // [rsp+40h] [rbp-20h]

  dwErrCode = 0;
  v2 = EnumeratePathEx(a1, 1);
  if ( a1 )
  {
    if ( DeleteFileEx2((__int64)a1, 32) )
      goto LABEL_5;
  }
  else
  {
    SetLastError(0x57u);
  }
  dwErrCode = GetLastError() | 0x100000000LL;
LABEL_5:
  if ( HIDWORD(dwErrCode) )
  {
    CurrDirectory = (void *)GetCurrDirectory();
    LibLog(
      &g_WdsLibLog,
      0x4000000,
      L"DeletePathEngine: Hit %u failure%s during recursive deletion of [%s]; 1st error = 0x%x, cd = [%s]");
    if ( CurrDirectory )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, CurrDirectory);
    }
    if ( (_DWORD)dwErrCode )
      SetLastError(dwErrCode);
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18003be78  mov     [rsp-8+arg_0], rbx
0x18003be7d  mov     [rsp-8+arg_8], rdi
0x18003be82  push    rbp
0x18003be83  mov     rbp, rsp
0x18003be86  sub     rsp, 60h
0x18003be8a  lea     r9, [rbp+dwErrCode]
0x18003be8e  mov     qword ptr [rbp+dwErrCode], 0
0x18003be96  lea     r8, DeletePathFileCallback
0x18003be9d  mov     [rbp+var_18], 1
0x18003bea4  lea     rdx, DeletePathDirectoryCallback
0x18003beab  mov     [rbp+var_14], 20h ; ' '
0x18003beb2  mov     rdi, rcx
0x18003beb5  mov     [rbp+var_8], 0
0x18003bebd  mov     [rbp+var_10], 0
0x18003bec5  mov     [rsp+60h+var_40], 1; int
0x18003becd  call    EnumeratePathEx
0x18003bed2  mov     ebx, eax
0x18003bed4  test    rdi, rdi
0x18003bed7  jnz     short loc_18003BEE4
0x18003bed9  lea     ecx, [rdi+57h]; dwErrCode
0x18003bedc  call    cs:__imp_SetLastError
0x18003bee2  jmp     short loc_18003BEF5
0x18003bee4  mov     edx, 20h ; ' '
0x18003bee9  mov     rcx, rdi
0x18003beec  call    DeleteFileEx2
0x18003bef1  test    eax, eax
0x18003bef3  jnz     short loc_18003BF07
0x18003bef5  inc     [rbp+dwErrCode+4]
0x18003bef8  cmp     [rbp+dwErrCode], 0
0x18003befc  jnz     short loc_18003BF07
0x18003befe  call    cs:__imp_GetLastError
0x18003bf04  mov     [rbp+dwErrCode], eax
0x18003bf07  cmp     [rbp+dwErrCode+4], 0
0x18003bf0b  jbe     loc_18003BF97
0x18003bf11  call    GetCurrDirectory
0x18003bf16  mov     r9d, [rbp+dwErrCode+4]
0x18003bf1a  lea     rcx, aUnavailable; "<unavailable>"
0x18003bf21  test    rax, rax
0x18003bf24  lea     rdx, aS; "s"
0x18003bf2b  mov     rbx, rax
0x18003bf2e  lea     r8, aDeletepathengi; "DeletePathEngine: Hit %u failure%s duri"...
0x18003bf35  cmovnz  rcx, rax
0x18003bf39  cmp     r9d, 1
0x18003bf3d  mov     [rsp+60h+var_28], rcx
0x18003bf42  lea     rax, Format
0x18003bf49  mov     ecx, [rbp+dwErrCode]
0x18003bf4c  cmovz   rdx, rax
0x18003bf50  mov     [rsp+60h+var_30], ecx
0x18003bf54  lea     rcx, g_WdsLibLog
0x18003bf5b  mov     [rsp+60h+var_38], rdi
0x18003bf60  mov     qword ptr [rsp+60h+var_40], rdx
0x18003bf65  mov     edx, 4000000h
0x18003bf6a  call    LibLog
0x18003bf6f  test    rbx, rbx
0x18003bf72  jz      short loc_18003BF88
0x18003bf74  call    cs:__imp_GetProcessHeap
0x18003bf7a  mov     r8, rbx; lpMem
0x18003bf7d  xor     edx, edx; dwFlags
0x18003bf7f  mov     rcx, rax; hHeap
0x18003bf82  call    cs:__imp_HeapFree
0x18003bf88  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18003bf8b  test    ecx, ecx
0x18003bf8d  jz      short loc_18003BF95
0x18003bf8f  call    cs:__imp_SetLastError
0x18003bf95  xor     ebx, ebx
0x18003bf97  mov     rdi, [rsp+60h+arg_8]
0x18003bf9c  mov     eax, ebx
0x18003bf9e  mov     rbx, [rsp+60h+arg_0]
0x18003bfa3  add     rsp, 60h
0x18003bfa7  pop     rbp
0x18003bfa8  retn
```
