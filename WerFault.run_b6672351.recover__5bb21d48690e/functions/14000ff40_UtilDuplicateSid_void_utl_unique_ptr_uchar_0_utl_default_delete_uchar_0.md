# UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x14000ff40`
- end: `0x14001002b`
- name: `?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140011d64`

## callees

- `0x140002748`
- `0x1400041e8`
- `0x14000ff40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ffd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ffd4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000ffc4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000ffc4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000ff84`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000ff84`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14000ff67`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14000ff67`

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
0x14000ff40  mov     [rsp+arg_0], rbx
0x14000ff45  mov     [rsp+arg_8], rsi
0x14000ff4a  push    rdi
0x14000ff4b  sub     rsp, 20h
0x14000ff4f  mov     rdi, rdx
0x14000ff52  mov     rbx, rcx
0x14000ff55  test    rdx, rdx
0x14000ff58  jz      loc_140010015
0x14000ff5e  test    rcx, rcx
0x14000ff61  jz      loc_140010015
0x14000ff67  call    cs:__imp_IsValidSid
0x14000ff6e  nop     dword ptr [rax+rax+00h]
0x14000ff73  test    eax, eax
0x14000ff75  jnz     short loc_14000FF81
0x14000ff77  mov     ebx, 80070057h
0x14000ff7c  jmp     loc_140010011
0x14000ff81  mov     rcx, rbx; pSid
0x14000ff84  call    cs:__imp_GetLengthSid
0x14000ff8b  nop     dword ptr [rax+rax+00h]
0x14000ff90  mov     ecx, eax; unsigned __int64
0x14000ff92  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000ff99  mov     esi, eax
0x14000ff9b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000ffa0  mov     rcx, [rdi]; void *
0x14000ffa3  mov     [rdi], rax
0x14000ffa6  test    rcx, rcx
0x14000ffa9  jz      short loc_14000FFB0
0x14000ffab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ffb0  mov     rdx, [rdi]; pDestinationSid
0x14000ffb3  test    rdx, rdx
0x14000ffb6  jnz     short loc_14000FFBF
0x14000ffb8  mov     ebx, 8007000Eh
0x14000ffbd  jmp     short loc_140010011
0x14000ffbf  mov     r8, rbx; pSourceSid
0x14000ffc2  mov     ecx, esi; nDestinationSidLength
0x14000ffc4  call    cs:__imp_CopySid
0x14000ffcb  nop     dword ptr [rax+rax+00h]
0x14000ffd0  test    eax, eax
0x14000ffd2  jnz     short loc_14001000F
0x14000ffd4  call    cs:__imp_GetLastError
0x14000ffdb  nop     dword ptr [rax+rax+00h]
0x14000ffe0  mov     ebx, eax
0x14000ffe2  test    eax, eax
0x14000ffe4  jle     short loc_14000FFEF
0x14000ffe6  movzx   ebx, ax
0x14000ffe9  or      ebx, 80070000h
0x14000ffef  mov     rcx, [rdi]; void *
0x14000fff2  test    ebx, ebx
0x14000fff4  mov     eax, 80004005h
0x14000fff9  mov     qword ptr [rdi], 0
0x140010000  cmovns  ebx, eax
0x140010003  test    rcx, rcx
0x140010006  jz      short loc_140010011
0x140010008  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001000d  jmp     short loc_140010011
0x14001000f  xor     ebx, ebx
0x140010011  mov     eax, ebx
0x140010013  jmp     short loc_14001001A
0x140010015  mov     eax, 80070057h
0x14001001a  mov     rbx, [rsp+28h+arg_0]
0x14001001f  mov     rsi, [rsp+28h+arg_8]
0x140010024  add     rsp, 20h
0x140010028  pop     rdi
0x140010029  retn
```
