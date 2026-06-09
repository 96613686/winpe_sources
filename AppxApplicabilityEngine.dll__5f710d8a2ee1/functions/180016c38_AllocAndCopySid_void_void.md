# AllocAndCopySid(void *,void * *)

- ea: `0x180016c38`
- end: `0x180016cc0`
- name: `?AllocAndCopySid@@YAJPEAXPEAPEAX@Z`
- size: `136`
- prototype: `__int64 __fastcall(PSID pSourceSid, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009da8`

## callees

- `0x180016c38`
- `0x180016cc8`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180016cad`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180016cad`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180016c76`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180016c76`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180016c62`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180016c62`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180016c55`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180016c55`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180016c8c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180016c8c`

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
0x180016c38  push    rbx
0x180016c3a  push    rbp
0x180016c3b  push    rsi
0x180016c3c  push    rdi
0x180016c3d  push    r14
0x180016c3f  sub     rsp, 20h
0x180016c43  mov     r14, rdx
0x180016c46  mov     qword ptr [rdx], 0
0x180016c4d  mov     rsi, rcx
0x180016c50  mov     ebx, 80070057h
0x180016c55  call    cs:__imp_IsValidSid
0x180016c5b  test    eax, eax
0x180016c5d  jz      short loc_180016CB3
0x180016c5f  mov     rcx, rsi; pSid
0x180016c62  call    cs:__imp_GetLengthSid
0x180016c68  mov     edx, eax; uBytes
0x180016c6a  mov     ecx, 40h ; '@'; uFlags
0x180016c6f  mov     ebp, eax
0x180016c71  mov     ebx, 8007000Eh
0x180016c76  call    cs:__imp_LocalAlloc
0x180016c7c  mov     rdi, rax
0x180016c7f  test    rax, rax
0x180016c82  jz      short loc_180016CB3
0x180016c84  mov     r8, rsi; pSourceSid
0x180016c87  mov     rdx, rax; pDestinationSid
0x180016c8a  mov     ecx, ebp; nDestinationSidLength
0x180016c8c  call    cs:__imp_CopySid
0x180016c92  test    eax, eax
0x180016c94  jz      short loc_180016C9A
0x180016c96  xor     ebx, ebx
0x180016c98  jmp     short loc_180016CA5
0x180016c9a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016c9f  mov     ebx, eax
0x180016ca1  test    eax, eax
0x180016ca3  js      short loc_180016CAA
0x180016ca5  mov     [r14], rdi
0x180016ca8  jmp     short loc_180016CB3
0x180016caa  mov     rcx, rdi; hMem
0x180016cad  call    cs:__imp_LocalFree
0x180016cb3  mov     eax, ebx
0x180016cb5  add     rsp, 20h
0x180016cb9  pop     r14
0x180016cbb  pop     rdi
0x180016cbc  pop     rsi
0x180016cbd  pop     rbp
0x180016cbe  pop     rbx
0x180016cbf  retn
```
