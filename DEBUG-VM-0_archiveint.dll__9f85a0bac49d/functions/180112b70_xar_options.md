# xar_options

- ea: `0x180112b70`
- end: `0x180112e5f`
- name: `xar_options`
- size: `751`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006c00`
- `0x180026460`
- `0x180112b70`
- `0x180119956`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180112dec`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180112e12`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180112dec`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180112e12`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x180112e06`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x180112e06`

## string_xrefs

- `0x180112cff`: `compression-level`
- `0x180112c0b`: `compression`
- `0x180112dc7`: `threads`
- `0x180112cd4`: `Unknown compression name: `%s'`

## pseudocode

```c
__int64 __fastcall xar_options(__int64 a1, const char *a2, unsigned __int8 *a3)
{
  _DWORD *v3; // rdi
  int v7; // edx
  _BYTE *v9; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_DWORD **)(a1 + 248);
  if ( !strcmp_0(a2, "checksum") )
  {
    if ( !a3 || !strcmp_0((const char *)a3, "none") )
    {
      v3[33] = 0;
      return 0;
    }
    if ( !strcmp_0((const char *)a3, "sha1") )
    {
      v3[33] = 1;
      return 0;
    }
    if ( !strcmp_0((const char *)a3, "md5") )
    {
      v3[33] = 2;
      return 0;
    }
    goto LABEL_39;
  }
  if ( !strcmp_0(a2, "compression") )
  {
    if ( !a3 || !strcmp_0((const char *)a3, "none") )
    {
      v3[34] = 0;
      return 0;
    }
    if ( !strcmp_0((const char *)a3, "gzip") )
    {
      v3[34] = 1;
      return 0;
    }
    if ( !strcmp_0((const char *)a3, "bzip2") )
    {
      v3[34] = 2;
      return 0;
    }
    if ( !strcmp_0((const char *)a3, "lzma") )
    {
      v3[34] = 3;
      return 0;
    }
    v7 = *a3 - 120;
    if ( *a3 == 120 )
    {
      v7 = a3[1] - 122;
      if ( a3[1] == 122 )
        v7 = a3[2];
    }
    if ( !v7 )
    {
      v3[34] = 4;
      return 0;
    }
    archive_set_error(a1, 0xFFFFFFFFLL, "Unknown compression name: `%s'", a3);
    return 4294967271LL;
  }
  if ( !strcmp_0(a2, "compression-level") )
  {
    if ( a3 && (unsigned __int8)(*a3 - 48) <= 9u && !a3[1] )
    {
      v3[35] = (char)*a3 - 48;
      return 0;
    }
    goto LABEL_49;
  }
  if ( !strcmp_0(a2, "toc-checksum") )
  {
    if ( !a3 || !strcmp_0((const char *)a3, "none") )
    {
      v3[32] = 0;
      return 0;
    }
    if ( !strcmp_0((const char *)a3, "sha1") )
    {
      v3[32] = 1;
      return 0;
    }
    if ( !strcmp_0((const char *)a3, "md5") )
    {
      v3[32] = 2;
      return 0;
    }
LABEL_39:
    archive_set_error(a1, 0xFFFFFFFFLL, "Unknown checksum name: `%s'", a3);
    return 4294967271LL;
  }
  if ( !strcmp_0(a2, "threads") )
  {
    v9 = 0;
    if ( !a3 )
      return 4294967271LL;
    *(_DWORD *)_o__errno() = 0;
    v3[36] = _o_strtoul(a3, &v9, 10);
    if ( *(_DWORD *)_o__errno() || *v9 )
    {
      v3[36] = 1;
LABEL_49:
      archive_set_error(a1, 0xFFFFFFFFLL, "Illegal value `%s'", a3);
      return 4294967271LL;
    }
    if ( !v3[36] )
      v3[36] = lzma_cputhreads();
  }
  return 4294967276LL;
}

```

## disassembly

```asm
0x180112b70  push    rbx
0x180112b72  push    rbp
0x180112b73  push    rsi
0x180112b74  push    rdi
0x180112b75  sub     rsp, 28h
0x180112b79  mov     rdi, [rcx+0F8h]
0x180112b80  mov     rsi, rdx
0x180112b83  mov     rbp, rcx
0x180112b86  lea     rdx, aChecksum; "checksum"
0x180112b8d  mov     rcx, rsi; Str1
0x180112b90  mov     rbx, r8
0x180112b93  call    strcmp_0
0x180112b98  test    eax, eax
0x180112b9a  jnz     short loc_180112C0B
0x180112b9c  test    rbx, rbx
0x180112b9f  jz      short loc_180112BFC
0x180112ba1  lea     rdx, aNone; "none"
0x180112ba8  mov     rcx, rbx; Str1
0x180112bab  call    strcmp_0
0x180112bb0  test    eax, eax
0x180112bb2  jz      short loc_180112BFC
0x180112bb4  lea     rdx, aSha1_0; "sha1"
0x180112bbb  mov     rcx, rbx; Str1
0x180112bbe  call    strcmp_0
0x180112bc3  test    eax, eax
0x180112bc5  jnz     short loc_180112BD6
0x180112bc7  mov     dword ptr [rdi+84h], 1
0x180112bd1  jmp     loc_180112D3C
0x180112bd6  lea     rdx, aMd5; "md5"
0x180112bdd  mov     rcx, rbx; Str1
0x180112be0  call    strcmp_0
0x180112be5  test    eax, eax
0x180112be7  jnz     loc_180112DAC
0x180112bed  mov     dword ptr [rdi+84h], 2
0x180112bf7  jmp     loc_180112D3C
0x180112bfc  mov     dword ptr [rdi+84h], 0
0x180112c06  jmp     loc_180112D3C
0x180112c0b  lea     rdx, aCompression; "compression"
0x180112c12  mov     rcx, rsi; Str1
0x180112c15  call    strcmp_0
0x180112c1a  test    eax, eax
0x180112c1c  jnz     loc_180112CFF
0x180112c22  test    rbx, rbx
0x180112c25  jz      loc_180112CF3
0x180112c2b  lea     rdx, aNone; "none"
0x180112c32  mov     rcx, rbx; Str1
0x180112c35  call    strcmp_0
0x180112c3a  test    eax, eax
0x180112c3c  jz      loc_180112CF3
0x180112c42  lea     rdx, aGzip; "gzip"
0x180112c49  mov     rcx, rbx; Str1
0x180112c4c  call    strcmp_0
0x180112c51  test    eax, eax
0x180112c53  jnz     short loc_180112C64
0x180112c55  mov     dword ptr [rdi+88h], 1
0x180112c5f  jmp     loc_180112D3C
0x180112c64  lea     rdx, aBzip2_0; "bzip2"
0x180112c6b  mov     rcx, rbx; Str1
0x180112c6e  call    strcmp_0
0x180112c73  test    eax, eax
0x180112c75  jnz     short loc_180112C86
0x180112c77  mov     dword ptr [rdi+88h], 2
0x180112c81  jmp     loc_180112D3C
0x180112c86  lea     rdx, aLzma; "lzma"
0x180112c8d  mov     rcx, rbx; Str1
0x180112c90  call    strcmp_0
0x180112c95  test    eax, eax
0x180112c97  jnz     short loc_180112CA8
0x180112c99  mov     dword ptr [rdi+88h], 3
0x180112ca3  jmp     loc_180112D3C
0x180112ca8  movzx   edx, byte ptr [rbx]
0x180112cab  sub     edx, 78h ; 'x'
0x180112cae  jnz     short loc_180112CC4
0x180112cb0  movzx   edx, byte ptr [rbx+1]
0x180112cb4  sub     edx, 7Ah ; 'z'
0x180112cb7  jnz     short loc_180112CC4
0x180112cb9  movzx   edx, byte ptr [rbx+2]
0x180112cbd  xor     eax, eax
0x180112cbf  movzx   ecx, al
0x180112cc2  sub     edx, ecx
0x180112cc4  test    edx, edx
0x180112cc6  jnz     short loc_180112CD4
0x180112cc8  mov     dword ptr [rdi+88h], 4
0x180112cd2  jmp     short loc_180112D3C
0x180112cd4  lea     r8, aUnknownCompres; "Unknown compression name: `%s'"
0x180112cdb  mov     r9, rbx
0x180112cde  or      edx, 0FFFFFFFFh
0x180112ce1  mov     rcx, rbp
0x180112ce4  call    archive_set_error
0x180112ce9  mov     eax, 0FFFFFFE7h
0x180112cee  jmp     loc_180112E40
0x180112cf3  mov     dword ptr [rdi+88h], 0
0x180112cfd  jmp     short loc_180112D3C
0x180112cff  lea     rdx, aCompressionLev_0; "compression-level"
0x180112d06  mov     rcx, rsi; Str1
0x180112d09  call    strcmp_0
0x180112d0e  test    eax, eax
0x180112d10  jnz     short loc_180112D43
0x180112d12  test    rbx, rbx
0x180112d15  jz      loc_180112E53
0x180112d1b  movsx   ecx, byte ptr [rbx]
0x180112d1e  lea     eax, [rcx-30h]
0x180112d21  cmp     al, 9
0x180112d23  ja      loc_180112E53
0x180112d29  cmp     byte ptr [rbx+1], 0
0x180112d2d  jnz     loc_180112E53
0x180112d33  lea     eax, [rcx-30h]
0x180112d36  mov     [rdi+8Ch], eax
0x180112d3c  xor     eax, eax
0x180112d3e  jmp     loc_180112E40
0x180112d43  lea     rdx, aTocChecksum; "toc-checksum"
0x180112d4a  mov     rcx, rsi; Str1
0x180112d4d  call    strcmp_0
0x180112d52  test    eax, eax
0x180112d54  jnz     short loc_180112DC7
0x180112d56  test    rbx, rbx
0x180112d59  jz      short loc_180112DB8
0x180112d5b  lea     rdx, aNone; "none"
0x180112d62  mov     rcx, rbx; Str1
0x180112d65  call    strcmp_0
0x180112d6a  test    eax, eax
0x180112d6c  jz      short loc_180112DB8
0x180112d6e  lea     rdx, aSha1_0; "sha1"
0x180112d75  mov     rcx, rbx; Str1
0x180112d78  call    strcmp_0
0x180112d7d  test    eax, eax
0x180112d7f  jnz     short loc_180112D8D
0x180112d81  mov     dword ptr [rdi+80h], 1
0x180112d8b  jmp     short loc_180112D3C
0x180112d8d  lea     rdx, aMd5; "md5"
0x180112d94  mov     rcx, rbx; Str1
0x180112d97  call    strcmp_0
0x180112d9c  test    eax, eax
0x180112d9e  jnz     short loc_180112DAC
0x180112da0  mov     dword ptr [rdi+80h], 2
0x180112daa  jmp     short loc_180112D3C
0x180112dac  lea     r8, aUnknownChecksu; "Unknown checksum name: `%s'"
0x180112db3  jmp     loc_180112CDB
0x180112db8  mov     dword ptr [rdi+80h], 0
0x180112dc2  jmp     loc_180112D3C
0x180112dc7  lea     rdx, aThreads; "threads"
0x180112dce  mov     rcx, rsi; Str1
0x180112dd1  call    strcmp_0
0x180112dd6  test    eax, eax
0x180112dd8  jnz     short loc_180112E3B
0x180112dda  mov     [rsp+48h+arg_0], 0
0x180112de3  test    rbx, rbx
0x180112de6  jz      loc_180112CE9
0x180112dec  call    cs:__imp__o__errno
0x180112df2  mov     r8d, 0Ah
0x180112df8  lea     rdx, [rsp+48h+arg_0]
0x180112dfd  mov     rcx, rbx
0x180112e00  mov     dword ptr [rax], 0
0x180112e06  call    cs:__imp__o_strtoul
0x180112e0c  mov     [rdi+90h], eax
0x180112e12  call    cs:__imp__o__errno
0x180112e18  cmp     dword ptr [rax], 0
0x180112e1b  jnz     short loc_180112E49
0x180112e1d  mov     rax, [rsp+48h+arg_0]
0x180112e22  cmp     byte ptr [rax], 0
0x180112e25  jnz     short loc_180112E49
0x180112e27  cmp     dword ptr [rdi+90h], 0
0x180112e2e  jnz     short loc_180112E3B
0x180112e30  call    lzma_cputhreads
0x180112e35  mov     [rdi+90h], eax
0x180112e3b  mov     eax, 0FFFFFFECh
0x180112e40  add     rsp, 28h
0x180112e44  pop     rdi
0x180112e45  pop     rsi
0x180112e46  pop     rbp
0x180112e47  pop     rbx
0x180112e48  retn
0x180112e49  mov     dword ptr [rdi+90h], 1
0x180112e53  lea     r8, aIllegalValueS; "Illegal value `%s'"
0x180112e5a  jmp     loc_180112CDB
```
