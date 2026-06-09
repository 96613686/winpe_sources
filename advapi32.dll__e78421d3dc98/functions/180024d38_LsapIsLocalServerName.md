# LsapIsLocalServerName

- ea: `0x180024d38`
- end: `0x180024ed5`
- name: `LsapIsLocalServerName`
- size: `413`
- prototype: `__int64 __fastcall(size_t MaxCount, wchar_t *String2)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180024b60`
- `0x180024c1c`

## callees

- `0x180024d38`
- `0x180065090`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180024e31`
- `msvcrt!_wcsnicmp` at `0x180024e7e`
- `msvcrt!_wcsnicmp` at `0x180024ec6`
- `msvcrt!_wcsnicmp` at `0x180024e31`
- `msvcrt!_wcsnicmp` at `0x180024e7e`
- `msvcrt!_wcsnicmp` at `0x180024ec6`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180024e0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180024ea0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180024e0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180024ea0`

## pseudocode

```c
__int64 __fastcall LsapIsLocalServerName(size_t MaxCount, wchar_t *String2, _BYTE *a3)
{
  const wchar_t *v4; // rdi
  size_t v5; // rbx
  unsigned int v6; // r14d
  unsigned int i; // ebp
  DWORD nSize[4]; // [rsp+20h] [rbp-268h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-258h] BYREF

  nSize[0] = 261;
  *a3 = 0;
  v4 = String2;
  v5 = MaxCount;
  v6 = 0;
  if ( String2 && MaxCount && *String2 )
  {
    if ( MaxCount > 1 && *String2 == 92 && String2[1] == 92 )
    {
      v5 = MaxCount - 2;
      if ( MaxCount == 2 )
        return (unsigned int)-1073741534;
      v4 = String2 + 2;
    }
    for ( i = 0; i < 2; ++i )
    {
      if ( v5 == dword_180083C98[i] && !_wcsnicmp(off_18006CB80[i], v4, v5) )
        goto LABEL_24;
    }
    if ( v5 <= 0xF
      && GetComputerNameExW(ComputerNameNetBIOS, Buffer, nSize)
      && v5 == nSize[0]
      && !_wcsnicmp(Buffer, v4, v5) )
    {
      goto LABEL_24;
    }
    if ( v4[v5 - 1] == 46 )
      --v5;
    nSize[0] = 261;
    if ( GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, nSize) )
    {
      if ( v5 == nSize[0] && !_wcsnicmp(Buffer, v4, v5) )
LABEL_24:
        *a3 = 1;
    }
  }
  else
  {
    *a3 = 1;
  }
  return v6;
}

```

## disassembly

```asm
0x180024d38  push    rbx
0x180024d3a  push    rbp
0x180024d3b  push    rsi
0x180024d3c  push    rdi
0x180024d3d  push    r12
0x180024d3f  push    r14
0x180024d41  push    r15
0x180024d43  sub     rsp, 250h
0x180024d4a  mov     rax, cs:__security_cookie
0x180024d51  xor     rax, rsp
0x180024d54  mov     [rsp+288h+var_48], rax
0x180024d5c  xor     r15d, r15d
0x180024d5f  mov     [rsp+288h+nSize], 105h
0x180024d67  mov     [r8], r15b
0x180024d6a  mov     rsi, r8
0x180024d6d  mov     rdi, rdx
0x180024d70  mov     rbx, rcx
0x180024d73  mov     r14d, r15d
0x180024d76  test    rdx, rdx
0x180024d79  jz      short loc_180024D80
0x180024d7b  test    rcx, rcx
0x180024d7e  jnz     short loc_180024DA9
0x180024d80  mov     byte ptr [r8], 1
0x180024d84  mov     eax, r14d
0x180024d87  mov     rcx, [rsp+288h+var_48]
0x180024d8f  xor     rcx, rsp; StackCookie
0x180024d92  call    __security_check_cookie
0x180024d97  add     rsp, 250h
0x180024d9e  pop     r15
0x180024da0  pop     r14
0x180024da2  pop     r12
0x180024da4  pop     rdi
0x180024da5  pop     rsi
0x180024da6  pop     rbp
0x180024da7  pop     rbx
0x180024da8  retn
0x180024da9  cmp     [rdx], r15w
0x180024dad  jz      short loc_180024D80
0x180024daf  cmp     rbx, 1
0x180024db3  ja      loc_180024E41
0x180024db9  mov     ebp, r15d
0x180024dbc  lea     r12, __ImageBase
0x180024dc3  cmp     ebp, 2
0x180024dc6  jnb     short loc_180024DDF
0x180024dc8  mov     ecx, ebp
0x180024dca  mov     eax, ds:rva dword_180083C98[r12+rcx*4]
0x180024dd2  cmp     rbx, rax
0x180024dd5  jz      loc_180024E70
0x180024ddb  inc     ebp
0x180024ddd  jmp     short loc_180024DC3
0x180024ddf  cmp     rbx, 0Fh
0x180024de3  jbe     loc_180024E94
0x180024de9  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x180024def  jnz     short loc_180024DF4
0x180024df1  dec     rbx
0x180024df4  lea     r8, [rsp+288h+nSize]; nSize
0x180024df9  mov     [rsp+288h+nSize], 105h
0x180024e01  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x180024e06  mov     ecx, 3; NameType
0x180024e0b  call    cs:__imp_GetComputerNameExW
0x180024e11  test    eax, eax
0x180024e13  jz      loc_180024D84
0x180024e19  mov     eax, [rsp+288h+nSize]
0x180024e1d  cmp     rbx, rax
0x180024e20  jnz     loc_180024D84
0x180024e26  mov     r8, rbx; MaxCount
0x180024e29  lea     rcx, [rsp+288h+Buffer]; String1
0x180024e2e  mov     rdx, rdi; String2
0x180024e31  call    cs:__imp__wcsnicmp
0x180024e37  test    eax, eax
0x180024e39  jnz     loc_180024D84
0x180024e3f  jmp     short loc_180024E8C
0x180024e41  cmp     word ptr [rdx], 5Ch ; '\'
0x180024e45  jnz     loc_180024DB9
0x180024e4b  cmp     word ptr [rdx+2], 5Ch ; '\'
0x180024e50  jnz     loc_180024DB9
0x180024e56  add     rbx, 0FFFFFFFFFFFFFFFEh
0x180024e5a  jnz     short loc_180024E67
0x180024e5c  mov     r14d, 0C0000122h
0x180024e62  jmp     loc_180024D84
0x180024e67  add     rdi, 4
0x180024e6b  jmp     loc_180024DB9
0x180024e70  mov     rcx, ds:rva off_18006CB80[r12+rcx*8]; String1
0x180024e78  mov     r8, rbx; MaxCount
0x180024e7b  mov     rdx, rdi; String2
0x180024e7e  call    cs:__imp__wcsnicmp
0x180024e84  test    eax, eax
0x180024e86  jnz     loc_180024DDB
0x180024e8c  mov     byte ptr [rsi], 1
0x180024e8f  jmp     loc_180024D84
0x180024e94  lea     r8, [rsp+288h+nSize]; nSize
0x180024e99  xor     ecx, ecx; NameType
0x180024e9b  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x180024ea0  call    cs:__imp_GetComputerNameExW
0x180024ea6  test    eax, eax
0x180024ea8  jz      loc_180024DE9
0x180024eae  mov     eax, [rsp+288h+nSize]
0x180024eb2  cmp     rbx, rax
0x180024eb5  jnz     loc_180024DE9
0x180024ebb  mov     r8, rbx; MaxCount
0x180024ebe  lea     rcx, [rsp+288h+Buffer]; String1
0x180024ec3  mov     rdx, rdi; String2
0x180024ec6  call    cs:__imp__wcsnicmp
0x180024ecc  test    eax, eax
0x180024ece  jz      short loc_180024E8C
0x180024ed0  jmp     loc_180024DE9
```
