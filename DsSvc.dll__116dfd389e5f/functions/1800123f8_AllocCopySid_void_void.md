# AllocCopySid(void *,void * *)

- ea: `0x1800123f8`
- end: `0x1800124aa`
- name: `?AllocCopySid@@YAJPEAXPEAPEAX@Z`
- size: `178`
- prototype: `__int64 __fastcall(PSID pSourceSid, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012748`

## callees

- `0x18000c93c`
- `0x1800123f8`
- `0x180012d54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012466`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180012417`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180012417`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001245c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001245c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001242d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001242d`

## pseudocode

```c
__int64 __fastcall AllocCopySid(PSID pSourceSid, void **a2)
{
  DWORD LengthSid; // eax
  DWORD v5; // r14d
  HLOCAL v6; // rax
  PSID v7; // rdi
  signed int v8; // ebx
  signed int LastError; // eax
  PSID pDestinationSid; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  LengthSid = GetLengthSid(pSourceSid);
  pDestinationSid = 0;
  v5 = LengthSid;
  v6 = LocalAlloc(0, LengthSid);
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::reset(&pDestinationSid, v6);
  v7 = pDestinationSid;
  if ( pDestinationSid )
  {
    v8 = 0;
    if ( CopySid(v5, pDestinationSid, pSourceSid) )
      goto LABEL_7;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
    {
LABEL_7:
      pDestinationSid = 0;
      *a2 = v7;
    }
  }
  else
  {
    v8 = -2147024882;
  }
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(&pDestinationSid);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800123f8  mov     [rsp+arg_0], rbx
0x1800123fd  mov     [rsp+arg_10], rbp
0x180012402  push    rsi
0x180012403  push    rdi
0x180012404  push    r14
0x180012406  sub     rsp, 20h
0x18001240a  mov     rsi, rdx
0x18001240d  mov     qword ptr [rdx], 0
0x180012414  mov     rbp, rcx
0x180012417  call    cs:__imp_GetLengthSid
0x18001241d  xor     ecx, ecx; uFlags
0x18001241f  mov     [rsp+38h+pDestinationSid], 0
0x180012428  mov     edx, eax; uBytes
0x18001242a  mov     r14d, eax
0x18001242d  call    cs:__imp_LocalAlloc
0x180012433  mov     rdx, rax
0x180012436  lea     rcx, [rsp+38h+pDestinationSid]
0x18001243b  call    ?reset@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@QEAAXPEAX@Z; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::reset(void *)
0x180012440  mov     rdi, [rsp+38h+pDestinationSid]
0x180012445  test    rdi, rdi
0x180012448  jnz     short loc_180012451
0x18001244a  mov     ebx, 8007000Eh
0x18001244f  jmp     short loc_18001248B
0x180012451  mov     r8, rbp; pSourceSid
0x180012454  mov     rdx, rdi; pDestinationSid
0x180012457  mov     ecx, r14d; nDestinationSidLength
0x18001245a  xor     ebx, ebx
0x18001245c  call    cs:__imp_CopySid
0x180012462  test    eax, eax
0x180012464  jnz     short loc_18001247F
0x180012466  call    cs:__imp_GetLastError
0x18001246c  mov     ebx, eax
0x18001246e  test    eax, eax
0x180012470  jle     short loc_18001247B
0x180012472  movzx   ebx, ax
0x180012475  or      ebx, 80070000h
0x18001247b  test    ebx, ebx
0x18001247d  js      short loc_18001248B
0x18001247f  mov     [rsp+38h+pDestinationSid], 0
0x180012488  mov     [rsi], rdi
0x18001248b  lea     rcx, [rsp+38h+pDestinationSid]
0x180012490  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x180012495  mov     rbp, [rsp+38h+arg_10]
0x18001249a  mov     eax, ebx
0x18001249c  mov     rbx, [rsp+38h+arg_0]
0x1800124a1  add     rsp, 20h
0x1800124a5  pop     r14
0x1800124a7  pop     rdi
0x1800124a8  pop     rsi
0x1800124a9  retn
```
