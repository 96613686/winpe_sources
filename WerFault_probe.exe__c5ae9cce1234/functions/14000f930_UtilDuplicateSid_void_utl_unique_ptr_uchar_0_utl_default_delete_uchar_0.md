# UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x14000f930`
- end: `0x14000f9ff`
- name: `?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400115cc`

## callees

- `0x140002728`
- `0x140004198`
- `0x14000f930`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f9af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f9af`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000f9a5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000f9a5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000f96b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000f96b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14000f957`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14000f957`

## pseudocode

```c
__int64 __fastcall UtilDuplicateSid(PSID pSourceSid, PSID *a2)
{
  signed int v4; // ebx
  DWORD LengthSid; // esi
  void *v6; // rax
  const struct std::nothrow_t *v7; // rdx
  PSID v8; // rcx
  signed int LastError; // eax
  const struct std::nothrow_t *v10; // rdx
  PSID v11; // rcx

  if ( !a2 || !pSourceSid )
    return 2147942487LL;
  if ( IsValidSid(pSourceSid) )
  {
    LengthSid = GetLengthSid(pSourceSid);
    v6 = operator new[](LengthSid, (const struct std::nothrow_t *)&std::nothrow);
    v8 = *a2;
    *a2 = v6;
    if ( v8 )
      operator delete(v8, v7);
    if ( *a2 )
    {
      if ( CopySid(LengthSid, *a2, pSourceSid) )
      {
        return 0;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        v11 = *a2;
        *a2 = 0;
        if ( v4 >= 0 )
          v4 = -2147467259;
        if ( v11 )
          operator delete(v11, v10);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000f930  mov     [rsp+arg_0], rbx
0x14000f935  mov     [rsp+arg_8], rsi
0x14000f93a  push    rdi
0x14000f93b  sub     rsp, 20h
0x14000f93f  mov     rdi, rdx
0x14000f942  mov     rbx, rcx
0x14000f945  test    rdx, rdx
0x14000f948  jz      loc_14000F9EA
0x14000f94e  test    rcx, rcx
0x14000f951  jz      loc_14000F9EA
0x14000f957  call    cs:__imp_IsValidSid
0x14000f95d  test    eax, eax
0x14000f95f  jnz     short loc_14000F968
0x14000f961  mov     ebx, 80070057h
0x14000f966  jmp     short loc_14000F9E6
0x14000f968  mov     rcx, rbx; pSid
0x14000f96b  call    cs:__imp_GetLengthSid
0x14000f971  mov     ecx, eax; unsigned __int64
0x14000f973  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000f97a  mov     esi, eax
0x14000f97c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000f981  mov     rcx, [rdi]; void *
0x14000f984  mov     [rdi], rax
0x14000f987  test    rcx, rcx
0x14000f98a  jz      short loc_14000F991
0x14000f98c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f991  mov     rdx, [rdi]; pDestinationSid
0x14000f994  test    rdx, rdx
0x14000f997  jnz     short loc_14000F9A0
0x14000f999  mov     ebx, 8007000Eh
0x14000f99e  jmp     short loc_14000F9E6
0x14000f9a0  mov     r8, rbx; pSourceSid
0x14000f9a3  mov     ecx, esi; nDestinationSidLength
0x14000f9a5  call    cs:__imp_CopySid
0x14000f9ab  test    eax, eax
0x14000f9ad  jnz     short loc_14000F9E4
0x14000f9af  call    cs:__imp_GetLastError
0x14000f9b5  mov     ebx, eax
0x14000f9b7  test    eax, eax
0x14000f9b9  jle     short loc_14000F9C4
0x14000f9bb  movzx   ebx, ax
0x14000f9be  or      ebx, 80070000h
0x14000f9c4  mov     rcx, [rdi]; void *
0x14000f9c7  test    ebx, ebx
0x14000f9c9  mov     eax, 80004005h
0x14000f9ce  mov     qword ptr [rdi], 0
0x14000f9d5  cmovns  ebx, eax
0x14000f9d8  test    rcx, rcx
0x14000f9db  jz      short loc_14000F9E6
0x14000f9dd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f9e2  jmp     short loc_14000F9E6
0x14000f9e4  xor     ebx, ebx
0x14000f9e6  mov     eax, ebx
0x14000f9e8  jmp     short loc_14000F9EF
0x14000f9ea  mov     eax, 80070057h
0x14000f9ef  mov     rbx, [rsp+28h+arg_0]
0x14000f9f4  mov     rsi, [rsp+28h+arg_8]
0x14000f9f9  add     rsp, 20h
0x14000f9fd  pop     rdi
0x14000f9fe  retn
```
