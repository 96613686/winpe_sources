# AllocAndCopySid(void *,void * *)

- ea: `0x1800247d0`
- end: `0x180024877`
- name: `?AllocAndCopySid@@YAJPEAXPEAPEAX@Z`
- size: `167`
- prototype: `__int64 __fastcall(PSID pSourceSid, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025678`

## callees

- `0x18001f164`
- `0x1800247d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002481a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002481a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002485d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002485d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180024800`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180024800`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180024836`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180024836`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800247ed`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800247ed`

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
0x1800247d0  push    rbx
0x1800247d2  push    rbp
0x1800247d3  push    rsi
0x1800247d4  push    rdi
0x1800247d5  push    r14
0x1800247d7  sub     rsp, 20h
0x1800247db  mov     r14, rdx
0x1800247de  mov     qword ptr [rdx], 0
0x1800247e5  mov     rsi, rcx
0x1800247e8  mov     ebx, 80070057h
0x1800247ed  call    cs:__imp_IsValidSid
0x1800247f4  nop     dword ptr [rax+rax+00h]
0x1800247f9  test    eax, eax
0x1800247fb  jz      short loc_180024869
0x1800247fd  mov     rcx, rsi; pSid
0x180024800  call    cs:__imp_GetLengthSid
0x180024807  nop     dword ptr [rax+rax+00h]
0x18002480c  mov     edx, eax; uBytes
0x18002480e  mov     ecx, 40h ; '@'; uFlags
0x180024813  mov     ebp, eax
0x180024815  mov     ebx, 8007000Eh
0x18002481a  call    cs:__imp_LocalAlloc
0x180024821  nop     dword ptr [rax+rax+00h]
0x180024826  mov     rdi, rax
0x180024829  test    rax, rax
0x18002482c  jz      short loc_180024869
0x18002482e  mov     r8, rsi; pSourceSid
0x180024831  mov     rdx, rax; pDestinationSid
0x180024834  mov     ecx, ebp; nDestinationSidLength
0x180024836  call    cs:__imp_CopySid
0x18002483d  nop     dword ptr [rax+rax+00h]
0x180024842  test    eax, eax
0x180024844  jz      short loc_18002484A
0x180024846  xor     ebx, ebx
0x180024848  jmp     short loc_180024855
0x18002484a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002484f  mov     ebx, eax
0x180024851  test    eax, eax
0x180024853  js      short loc_18002485A
0x180024855  mov     [r14], rdi
0x180024858  jmp     short loc_180024869
0x18002485a  mov     rcx, rdi; hMem
0x18002485d  call    cs:__imp_LocalFree
0x180024864  nop     dword ptr [rax+rax+00h]
0x180024869  mov     eax, ebx
0x18002486b  add     rsp, 20h
0x18002486f  pop     r14
0x180024871  pop     rdi
0x180024872  pop     rsi
0x180024873  pop     rbp
0x180024874  pop     rbx
0x180024875  retn
```
