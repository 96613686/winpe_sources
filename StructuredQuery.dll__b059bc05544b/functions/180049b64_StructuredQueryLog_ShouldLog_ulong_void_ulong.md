# StructuredQueryLog::ShouldLog(ulong,void * *,ulong *)

- ea: `0x180049b64`
- end: `0x180049c28`
- name: `?ShouldLog@StructuredQueryLog@@AEAAJKPEAPEAXPEAK@Z`
- size: `196`
- prototype: `__int64 __fastcall(FILETIME *lpFileTime2, unsigned int, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011d68`
- `0x180049ad8`

## callees

- `0x180049b64`
- `0x180049c30`
- `0x180059848`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049bd0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049bd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049c16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049c16`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180049b9b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180049be9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180049b9b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180049be9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049b8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049bdb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049b8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049bdb`

## pseudocode

```c
__int64 __fastcall StructuredQueryLog::ShouldLog(FILETIME *lpFileTime2, int a2, void **a3, unsigned int *a4)
{
  unsigned int dwLowDateTime; // edi
  __int64 result; // rax
  __int64 v10; // rdx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+8h] BYREF

  dwLowDateTime = lpFileTime2[1].dwLowDateTime;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( CompareFileTime(&SystemTimeAsFileTime, lpFileTime2) > 0 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)&lpFileTime2[2]);
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( CompareFileTime(&SystemTimeAsFileTime, lpFileTime2) > 0 )
    {
      dwLowDateTime = SHRegGetUSDWORDW();
      v10 = *(_QWORD *)&SystemTimeAsFileTime + 300000000LL;
      lpFileTime2[1].dwLowDateTime = dwLowDateTime;
      *lpFileTime2 = (FILETIME)v10;
    }
    ReleaseSRWLockExclusive((PSRWLOCK)&lpFileTime2[2]);
  }
  if ( a4 )
    *a4 = dwLowDateTime;
  result = 1;
  if ( ((a2 | 1) & dwLowDateTime) != 0 )
    return StructuredQueryLogHandle(a3);
  *a3 = (void *)-1LL;
  return result;
}

```

## disassembly

```asm
0x180049b64  push    rbx
0x180049b66  push    rbp
0x180049b67  push    rsi
0x180049b68  push    rdi
0x180049b69  push    r14
0x180049b6b  push    r15
0x180049b6d  sub     rsp, 28h
0x180049b71  mov     edi, [rcx+8]
0x180049b74  mov     rbx, rcx
0x180049b77  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180049b7c  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180049b85  mov     r15, r9
0x180049b88  mov     r14, r8
0x180049b8b  mov     esi, edx
0x180049b8d  call    cs:__imp_GetSystemTimeAsFileTime
0x180049b93  mov     rdx, rbx; lpFileTime2
0x180049b96  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpFileTime1
0x180049b9b  call    cs:__imp_CompareFileTime
0x180049ba1  test    eax, eax
0x180049ba3  jg      short loc_180049BCC
0x180049ba5  test    r15, r15
0x180049ba8  jz      short loc_180049BAD
0x180049baa  mov     [r15], edi
0x180049bad  mov     eax, 1
0x180049bb2  or      esi, eax
0x180049bb4  test    edi, esi
0x180049bb6  jnz     short loc_180049C1E
0x180049bb8  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180049bbf  add     rsp, 28h
0x180049bc3  pop     r15
0x180049bc5  pop     r14
0x180049bc7  pop     rdi
0x180049bc8  pop     rsi
0x180049bc9  pop     rbp
0x180049bca  pop     rbx
0x180049bcb  retn
0x180049bcc  lea     rcx, [rbx+10h]; SRWLock
0x180049bd0  call    cs:__imp_AcquireSRWLockExclusive
0x180049bd6  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180049bdb  call    cs:__imp_GetSystemTimeAsFileTime
0x180049be1  mov     rdx, rbx; lpFileTime2
0x180049be4  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpFileTime1
0x180049be9  call    cs:__imp_CompareFileTime
0x180049bef  test    eax, eax
0x180049bf1  jle     short loc_180049C12
0x180049bf3  call    SHRegGetUSDWORDW
0x180049bf8  mov     rdx, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x180049bfd  mov     edi, eax
0x180049bff  add     rdx, 11E1A300h
0x180049c06  mov     [rbx+8], eax
0x180049c09  mov     [rbx], edx
0x180049c0b  shr     rdx, 20h
0x180049c0f  mov     [rbx+4], edx
0x180049c12  lea     rcx, [rbx+10h]; SRWLock
0x180049c16  call    cs:__imp_ReleaseSRWLockExclusive
0x180049c1c  jmp     short loc_180049BA5
0x180049c1e  mov     rcx, r14
0x180049c21  call    StructuredQueryLogHandle
0x180049c26  jmp     short loc_180049BBF
```
