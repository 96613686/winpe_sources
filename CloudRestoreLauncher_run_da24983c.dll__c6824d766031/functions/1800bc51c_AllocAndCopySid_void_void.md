# AllocAndCopySid(void *,void * *)

- ea: `0x1800bc51c`
- end: `0x1800bc5a4`
- name: `?AllocAndCopySid@@YAJPEAXPEAPEAX@Z`
- size: `136`
- prototype: `__int64 __fastcall(PSID pSourceSid, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800bdb98`

## callees

- `0x1800bc51c`
- `0x1800beb8c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800bc591`
- `KERNEL32!LocalFree` at `0x1800bc591`
- `KERNEL32!LocalAlloc` at `0x1800bc55a`
- `KERNEL32!LocalAlloc` at `0x1800bc55a`
- `ADVAPI32!IsValidSid` at `0x1800bc539`
- `ADVAPI32!IsValidSid` at `0x1800bc539`
- `ADVAPI32!GetLengthSid` at `0x1800bc546`
- `ADVAPI32!GetLengthSid` at `0x1800bc546`
- `ADVAPI32!CopySid` at `0x1800bc570`
- `ADVAPI32!CopySid` at `0x1800bc570`

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
0x1800bc51c  push    rbx
0x1800bc51e  push    rbp
0x1800bc51f  push    rsi
0x1800bc520  push    rdi
0x1800bc521  push    r14
0x1800bc523  sub     rsp, 20h
0x1800bc527  mov     r14, rdx
0x1800bc52a  mov     qword ptr [rdx], 0
0x1800bc531  mov     rsi, rcx
0x1800bc534  mov     ebx, 80070057h
0x1800bc539  call    cs:__imp_IsValidSid
0x1800bc53f  test    eax, eax
0x1800bc541  jz      short loc_1800BC597
0x1800bc543  mov     rcx, rsi; pSid
0x1800bc546  call    cs:__imp_GetLengthSid
0x1800bc54c  mov     edx, eax; uBytes
0x1800bc54e  mov     ecx, 40h ; '@'; uFlags
0x1800bc553  mov     ebp, eax
0x1800bc555  mov     ebx, 8007000Eh
0x1800bc55a  call    cs:__imp_LocalAlloc
0x1800bc560  mov     rdi, rax
0x1800bc563  test    rax, rax
0x1800bc566  jz      short loc_1800BC597
0x1800bc568  mov     r8, rsi; pSourceSid
0x1800bc56b  mov     rdx, rax; pDestinationSid
0x1800bc56e  mov     ecx, ebp; nDestinationSidLength
0x1800bc570  call    cs:__imp_CopySid
0x1800bc576  test    eax, eax
0x1800bc578  jz      short loc_1800BC57E
0x1800bc57a  xor     ebx, ebx
0x1800bc57c  jmp     short loc_1800BC589
0x1800bc57e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800bc583  mov     ebx, eax
0x1800bc585  test    eax, eax
0x1800bc587  js      short loc_1800BC58E
0x1800bc589  mov     [r14], rdi
0x1800bc58c  jmp     short loc_1800BC597
0x1800bc58e  mov     rcx, rdi; hMem
0x1800bc591  call    cs:__imp_LocalFree
0x1800bc597  mov     eax, ebx
0x1800bc599  add     rsp, 20h
0x1800bc59d  pop     r14
0x1800bc59f  pop     rdi
0x1800bc5a0  pop     rsi
0x1800bc5a1  pop     rbp
0x1800bc5a2  pop     rbx
0x1800bc5a3  retn
```
