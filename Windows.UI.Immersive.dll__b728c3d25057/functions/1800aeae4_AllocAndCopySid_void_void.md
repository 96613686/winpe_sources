# AllocAndCopySid(void *,void * *)

- ea: `0x1800aeae4`
- end: `0x1800aeb6c`
- name: `?AllocAndCopySid@@YAJPEAXPEAPEAX@Z`
- size: `136`
- prototype: `__int64 __fastcall(PSID pSourceSid, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039d24`
- `0x1800d46b8`

## callees

- `0x18003aa84`
- `0x1800aeae4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aeb59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aeb59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800aeb22`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800aeb22`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800aeb0e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800aeb0e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800aeb01`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800aeb01`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800aeb38`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800aeb38`

## pseudocode

```c
__int64 __fastcall AllocAndCopySid(PSID pSourceSid, void **a2)
{
  int Error; // ebx
  DWORD LengthSid; // ebp
  HLOCAL v6; // rax
  void *v7; // rdi

  *a2 = 0;
  Error = -2147024809;
  if ( IsValidSid(pSourceSid) )
  {
    LengthSid = GetLengthSid(pSourceSid);
    Error = -2147024882;
    v6 = LocalAlloc(0x40u, LengthSid);
    v7 = v6;
    if ( v6 )
    {
      if ( CopySid(LengthSid, v6, pSourceSid) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
          LocalFree(v7);
          return (unsigned int)Error;
        }
      }
      *a2 = v7;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800aeae4  push    rbx
0x1800aeae6  push    rbp
0x1800aeae7  push    rsi
0x1800aeae8  push    rdi
0x1800aeae9  push    r14
0x1800aeaeb  sub     rsp, 20h
0x1800aeaef  mov     r14, rdx
0x1800aeaf2  mov     qword ptr [rdx], 0
0x1800aeaf9  mov     rsi, rcx
0x1800aeafc  mov     ebx, 80070057h
0x1800aeb01  call    cs:__imp_IsValidSid
0x1800aeb07  test    eax, eax
0x1800aeb09  jz      short loc_1800AEB5F
0x1800aeb0b  mov     rcx, rsi; pSid
0x1800aeb0e  call    cs:__imp_GetLengthSid
0x1800aeb14  mov     edx, eax; uBytes
0x1800aeb16  mov     ecx, 40h ; '@'; uFlags
0x1800aeb1b  mov     ebp, eax
0x1800aeb1d  mov     ebx, 8007000Eh
0x1800aeb22  call    cs:__imp_LocalAlloc
0x1800aeb28  mov     rdi, rax
0x1800aeb2b  test    rax, rax
0x1800aeb2e  jz      short loc_1800AEB5F
0x1800aeb30  mov     r8, rsi; pSourceSid
0x1800aeb33  mov     rdx, rax; pDestinationSid
0x1800aeb36  mov     ecx, ebp; nDestinationSidLength
0x1800aeb38  call    cs:__imp_CopySid
0x1800aeb3e  test    eax, eax
0x1800aeb40  jz      short loc_1800AEB46
0x1800aeb42  xor     ebx, ebx
0x1800aeb44  jmp     short loc_1800AEB51
0x1800aeb46  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800aeb4b  mov     ebx, eax
0x1800aeb4d  test    eax, eax
0x1800aeb4f  js      short loc_1800AEB56
0x1800aeb51  mov     [r14], rdi
0x1800aeb54  jmp     short loc_1800AEB5F
0x1800aeb56  mov     rcx, rdi; hMem
0x1800aeb59  call    cs:__imp_LocalFree
0x1800aeb5f  mov     eax, ebx
0x1800aeb61  add     rsp, 20h
0x1800aeb65  pop     r14
0x1800aeb67  pop     rdi
0x1800aeb68  pop     rsi
0x1800aeb69  pop     rbp
0x1800aeb6a  pop     rbx
0x1800aeb6b  retn
```
