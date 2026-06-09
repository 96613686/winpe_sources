# CCertManager::GetComputerFQDN(void)

- ea: `0x180029d60`
- end: `0x180029e83`
- name: `?GetComputerFQDN@CCertManager@@AEAAJXZ`
- size: `291`
- prototype: `__int64 __fastcall(CCertManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002a298`

## callees

- `0x180003f30`
- `0x18001a2a4`
- `0x18001a2ec`
- `0x180029d60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029db8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029db8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e2a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180029daa`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180029e20`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180029daa`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180029e20`

## string_xrefs

- `0x180029e43`: `CCertManager::GetComputerFQDN`
- `0x180029e4d`: `GetComputerNameEx failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CCertManager::GetComputerFQDN(CCertManager *this)
{
  WCHAR *v2; // rax
  WCHAR *v3; // rdi
  unsigned int v4; // ebx
  signed int LastError; // eax
  const struct std::nothrow_t *v6; // rdx
  size_t v7; // rax
  WCHAR *v8; // rax
  signed int v9; // eax
  const struct std::nothrow_t *v10; // rdx
  DWORD nSize; // [rsp+38h] [rbp+10h] BYREF

  nSize = 261;
  v2 = (WCHAR *)operator new(0x20Au, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  if ( v2 )
  {
    if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, v2, &nSize) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 != -2147024662 )
      {
LABEL_13:
        if ( (v4 & 0x80000000) != 0 )
        {
          _DbgPrintMessage(8, "GetComputerNameEx failed: 0x%x in %s", v4, "CCertManager::GetComputerFQDN");
          operator delete(v3, v10);
          return v4;
        }
LABEL_16:
        *((_QWORD *)this + 202) = v3;
        return v4;
      }
      operator delete(v3, v6);
      v7 = 2LL * ++nSize;
      if ( !is_mul_ok(nSize, 2u) )
        v7 = -1;
      v8 = (WCHAR *)operator new(v7, (const struct std::nothrow_t *)std::nothrow);
      v3 = v8;
      if ( !v8 )
        return (unsigned int)-2147024882;
      if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, v8, &nSize) )
      {
        v9 = GetLastError();
        v4 = v9;
        if ( v9 > 0 )
          v4 = (unsigned __int16)v9 | 0x80070000;
        goto LABEL_13;
      }
    }
    v4 = 0;
    goto LABEL_16;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180029d60  mov     [rsp+arg_0], rbx
0x180029d65  mov     [rsp+arg_10], rsi
0x180029d6a  push    rdi
0x180029d6b  sub     rsp, 20h
0x180029d6f  mov     rsi, rcx
0x180029d72  mov     [rsp+28h+nSize], 105h
0x180029d7a  mov     ecx, 20Ah; unsigned __int64
0x180029d7f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029d86  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180029d8b  mov     rdi, rax
0x180029d8e  test    rax, rax
0x180029d91  jnz     short loc_180029D9D
0x180029d93  mov     ebx, 8007000Eh
0x180029d98  jmp     loc_180029E71
0x180029d9d  lea     r8, [rsp+28h+nSize]; nSize
0x180029da2  mov     rdx, rdi; lpBuffer
0x180029da5  mov     ecx, 3; NameType
0x180029daa  call    cs:__imp_GetComputerNameExW
0x180029db0  test    eax, eax
0x180029db2  jnz     loc_180029E68
0x180029db8  call    cs:__imp_GetLastError
0x180029dbe  mov     ebx, eax
0x180029dc0  test    eax, eax
0x180029dc2  jle     short loc_180029DCD
0x180029dc4  movzx   ebx, ax
0x180029dc7  or      ebx, 80070000h
0x180029dcd  cmp     ebx, 800700EAh
0x180029dd3  jnz     short loc_180029E3F
0x180029dd5  mov     rcx, rdi; void *
0x180029dd8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029ddd  mov     eax, [rsp+28h+nSize]
0x180029de1  inc     eax
0x180029de3  mov     ecx, eax
0x180029de5  mov     [rsp+28h+nSize], eax
0x180029de9  mov     eax, 2
0x180029dee  mul     rcx
0x180029df1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180029df8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029dff  cmovb   rax, rcx
0x180029e03  mov     rcx, rax; unsigned __int64
0x180029e06  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180029e0b  mov     rdi, rax
0x180029e0e  test    rax, rax
0x180029e11  jz      short loc_180029D93
0x180029e13  lea     r8, [rsp+28h+nSize]; nSize
0x180029e18  mov     rdx, rax; lpBuffer
0x180029e1b  mov     ecx, 3; NameType
0x180029e20  call    cs:__imp_GetComputerNameExW
0x180029e26  test    eax, eax
0x180029e28  jnz     short loc_180029E68
0x180029e2a  call    cs:__imp_GetLastError
0x180029e30  mov     ebx, eax
0x180029e32  test    eax, eax
0x180029e34  jle     short loc_180029E3F
0x180029e36  movzx   ebx, ax
0x180029e39  or      ebx, 80070000h
0x180029e3f  test    ebx, ebx
0x180029e41  jns     short loc_180029E6A
0x180029e43  lea     r9, aCcertmanagerGe; "CCertManager::GetComputerFQDN"
0x180029e4a  mov     r8d, ebx
0x180029e4d  lea     rdx, aGetcomputernam_0; "GetComputerNameEx failed: 0x%x in %s"
0x180029e54  mov     ecx, 8; int
0x180029e59  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029e5e  mov     rcx, rdi; void *
0x180029e61  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029e66  jmp     short loc_180029E71
0x180029e68  xor     ebx, ebx
0x180029e6a  mov     [rsi+650h], rdi
0x180029e71  mov     rsi, [rsp+28h+arg_10]
0x180029e76  mov     eax, ebx
0x180029e78  mov     rbx, [rsp+28h+arg_0]
0x180029e7d  add     rsp, 20h
0x180029e81  pop     rdi
0x180029e82  retn
```
