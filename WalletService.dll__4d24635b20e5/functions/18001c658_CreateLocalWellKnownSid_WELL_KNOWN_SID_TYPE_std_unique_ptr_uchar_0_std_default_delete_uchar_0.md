# CreateLocalWellKnownSid(WELL_KNOWN_SID_TYPE,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &)

- ea: `0x18001c658`
- end: `0x18001c707`
- name: `?CreateLocalWellKnownSid@@YAJW4WELL_KNOWN_SID_TYPE@@AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@Z`
- size: `175`
- prototype: `signed int __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001d5cc`
- `0x18001d83c`

## callees

- `0x180002e48`
- `0x18001b458`
- `0x18001c658`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c6d2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c6d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c68a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c68a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c695`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001c679`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001c6f0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001c679`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001c6f0`

## pseudocode

```c
signed int __fastcall CreateLocalWellKnownSid(WELL_KNOWN_SID_TYPE WellKnownSidType, void **a2)
{
  void *v2; // r8
  signed int result; // eax
  DWORD cbSid; // [rsp+38h] [rbp+10h] BYREF
  void *v7; // [rsp+40h] [rbp+18h] BYREF

  v2 = *a2;
  cbSid = 0;
  if ( CreateWellKnownSid(WellKnownSidType, 0, v2, &cbSid) )
    return -2147418113;
  if ( GetLastError() != 122 )
    goto LABEL_4;
  v7 = operator new[](cbSid);
  std::unique_ptr<unsigned char [0]>::operator=(a2, &v7);
  operator delete[](v7);
  if ( !*a2 )
    return -2147024882;
  if ( CreateWellKnownSid(WellKnownSidType, 0, *a2, &cbSid) )
    return 0;
LABEL_4:
  result = GetLastError();
  if ( !result )
    return -2143748092;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001c658  mov     [rsp+arg_0], rbx
0x18001c65d  push    rdi
0x18001c65e  sub     rsp, 20h
0x18001c662  mov     r8, [rdx]; pSid
0x18001c665  lea     r9, [rsp+28h+cbSid]; cbSid
0x18001c66a  mov     rbx, rdx
0x18001c66d  mov     [rsp+28h+cbSid], 0
0x18001c675  xor     edx, edx; DomainSid
0x18001c677  mov     edi, ecx
0x18001c679  call    cs:__imp_CreateWellKnownSid
0x18001c67f  test    eax, eax
0x18001c681  jz      short loc_18001C68A
0x18001c683  mov     eax, 8000FFFFh
0x18001c688  jmp     short loc_18001C6FC
0x18001c68a  call    cs:__imp_GetLastError
0x18001c690  cmp     eax, 7Ah ; 'z'
0x18001c693  jz      short loc_18001C6B2
0x18001c695  call    cs:__imp_GetLastError
0x18001c69b  test    eax, eax
0x18001c69d  jz      short loc_18001C6AB
0x18001c69f  jle     short loc_18001C6FC
0x18001c6a1  movzx   eax, ax
0x18001c6a4  or      eax, 80070000h
0x18001c6a9  jmp     short loc_18001C6FC
0x18001c6ab  mov     eax, 80390004h
0x18001c6b0  jmp     short loc_18001C6FC
0x18001c6b2  mov     ecx, [rsp+28h+cbSid]; unsigned __int64
0x18001c6b6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001c6bb  lea     rdx, [rsp+28h+arg_10]
0x18001c6c0  mov     [rsp+28h+arg_10], rax
0x18001c6c5  mov     rcx, rbx
0x18001c6c8  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=(std::unique_ptr<uchar [0]> &&)
0x18001c6cd  mov     rcx, [rsp+28h+arg_10]
0x18001c6d2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001c6d8  mov     r8, [rbx]; pSid
0x18001c6db  test    r8, r8
0x18001c6de  jnz     short loc_18001C6E7
0x18001c6e0  mov     eax, 8007000Eh
0x18001c6e5  jmp     short loc_18001C6FC
0x18001c6e7  lea     r9, [rsp+28h+cbSid]; cbSid
0x18001c6ec  xor     edx, edx; DomainSid
0x18001c6ee  mov     ecx, edi; WellKnownSidType
0x18001c6f0  call    cs:__imp_CreateWellKnownSid
0x18001c6f6  test    eax, eax
0x18001c6f8  jz      short loc_18001C695
0x18001c6fa  xor     eax, eax
0x18001c6fc  mov     rbx, [rsp+28h+arg_0]
0x18001c701  add     rsp, 20h
0x18001c705  pop     rdi
0x18001c706  retn
```
