# GetFileIntegrityRid(ushort const *,ulong *)

- ea: `0x180020c60`
- end: `0x180020d6e`
- name: `?GetFileIntegrityRid@@YAJPEBGPEAK@Z`
- size: `270`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800211c0`

## callees

- `0x180020c60`
- `0x180020d74`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020d5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ce8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020d54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020d54`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180020c89`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180020cd9`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180020c89`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180020cd9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020d3f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020d3f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180020d2b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180020d2b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180020d1d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180020d1d`

## pseudocode

```c
__int64 __fastcall GetFileIntegrityRid(const unsigned __int16 *a1, unsigned int *a2)
{
  void *File2; // rdi
  signed int LastError; // eax
  int HandleIntegrityLevel; // ebx
  PUCHAR SidSubAuthorityCount; // rax
  _DWORD v9[2]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+38h] [rbp-20h]
  __int128 v11; // [rsp+40h] [rbp-18h]
  PSID pSid; // [rsp+90h] [rbp+38h] BYREF

  File2 = (void *)CreateFile2(a1, 0x20000, 3, 3, 0);
  if ( File2 == (void *)-1LL
    && (GetLastError() != 5
     || (v9[0] = 32,
         v9[1] = 128,
         v10 = 0x2000000,
         v11 = 0,
         File2 = (void *)CreateFile2(a1, 0x20000, 3, 3, v9),
         File2 == (void *)-1LL)) )
  {
    LastError = GetLastError();
    HandleIntegrityLevel = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    pSid = 0;
    HandleIntegrityLevel = GetHandleIntegrityLevel(File2, &pSid);
    if ( HandleIntegrityLevel >= 0 )
    {
      if ( IsValidSid(pSid) && (SidSubAuthorityCount = GetSidSubAuthorityCount(pSid), *SidSubAuthorityCount) )
        *a2 = *GetSidSubAuthority(pSid, (unsigned int)*SidSubAuthorityCount - 1);
      else
        HandleIntegrityLevel = -2147467259;
      LocalFree(pSid);
    }
    CloseHandle(File2);
  }
  return (unsigned int)HandleIntegrityLevel;
}

```

## disassembly

```asm
0x180020c60  push    rbp
0x180020c62  push    rbx
0x180020c63  push    rsi
0x180020c64  push    rdi
0x180020c65  mov     rbp, rsp
0x180020c68  sub     rsp, 58h
0x180020c6c  mov     r9d, 3
0x180020c72  mov     [rsp+58h+var_38], 0
0x180020c7b  mov     rsi, rdx
0x180020c7e  mov     r8d, r9d
0x180020c81  mov     edx, 20000h
0x180020c86  mov     rbx, rcx
0x180020c89  call    cs:__imp_CreateFile2
0x180020c8f  mov     rdi, rax
0x180020c92  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020c96  jnz     short loc_180020CFF
0x180020c98  call    cs:__imp_GetLastError
0x180020c9e  cmp     eax, 5
0x180020ca1  jnz     short loc_180020CE8
0x180020ca3  lea     r9d, [rdi+4]
0x180020ca7  mov     [rbp+var_28], 20h ; ' '
0x180020cae  xorps   xmm0, xmm0
0x180020cb1  mov     [rbp+var_24], 80h
0x180020cb8  lea     rax, [rbp+var_28]
0x180020cbc  mov     [rbp+var_20], 2000000h
0x180020cc4  mov     r8d, r9d
0x180020cc7  mov     [rsp+58h+var_38], rax
0x180020ccc  mov     edx, 20000h
0x180020cd1  mov     rcx, rbx
0x180020cd4  movdqu  [rbp+var_18], xmm0
0x180020cd9  call    cs:__imp_CreateFile2
0x180020cdf  mov     rdi, rax
0x180020ce2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020ce6  jnz     short loc_180020CFF
0x180020ce8  call    cs:__imp_GetLastError
0x180020cee  mov     ebx, eax
0x180020cf0  test    eax, eax
0x180020cf2  jle     short loc_180020D63
0x180020cf4  movzx   ebx, ax
0x180020cf7  or      ebx, 80070000h
0x180020cfd  jmp     short loc_180020D63
0x180020cff  lea     rdx, [rbp+pSid]; Sid
0x180020d03  mov     [rbp+pSid], 0
0x180020d0b  mov     rcx, rdi; Handle
0x180020d0e  call    ?GetHandleIntegrityLevel@@YAJPEAXPEAPEAX@Z; GetHandleIntegrityLevel(void *,void * *)
0x180020d13  mov     ebx, eax
0x180020d15  test    eax, eax
0x180020d17  js      short loc_180020D5A
0x180020d19  mov     rcx, [rbp+pSid]; pSid
0x180020d1d  call    cs:__imp_IsValidSid
0x180020d23  test    eax, eax
0x180020d25  jz      short loc_180020D4B
0x180020d27  mov     rcx, [rbp+pSid]; pSid
0x180020d2b  call    cs:__imp_GetSidSubAuthorityCount
0x180020d31  cmp     byte ptr [rax], 0
0x180020d34  jbe     short loc_180020D4B
0x180020d36  movzx   edx, byte ptr [rax]
0x180020d39  mov     rcx, [rbp+pSid]; pSid
0x180020d3d  dec     edx; nSubAuthority
0x180020d3f  call    cs:__imp_GetSidSubAuthority
0x180020d45  mov     ecx, [rax]
0x180020d47  mov     [rsi], ecx
0x180020d49  jmp     short loc_180020D50
0x180020d4b  mov     ebx, 80004005h
0x180020d50  mov     rcx, [rbp+pSid]; hMem
0x180020d54  call    cs:__imp_LocalFree
0x180020d5a  mov     rcx, rdi; hObject
0x180020d5d  call    cs:__imp_CloseHandle
0x180020d63  mov     eax, ebx
0x180020d65  add     rsp, 58h
0x180020d69  pop     rdi
0x180020d6a  pop     rsi
0x180020d6b  pop     rbx
0x180020d6c  pop     rbp
0x180020d6d  retn
```
