# _7z_options

- ea: `0x1800f8ed0`
- end: `0x1800f9230`
- name: `_7z_options`
- size: `864`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006c00`
- `0x1800433f0`
- `0x180043400`
- `0x1800f8ed0`
- `0x180119956`

## import_xrefs

- `api-ms-win-crt-convert-l1-1-0!strtoimax` at `0x1800f91dd`
- `api-ms-win-crt-convert-l1-1-0!strtoimax` at `0x1800f91dd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f91f5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f91f5`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x1800f9131`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x1800f9131`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x1800f920f`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x1800f920f`

## string_xrefs

- `0x1800f90f4`: `compression-level`
- `0x1800f8ee6`: `compression`
- `0x1800f91ac`: `threads`
- `0x1800f907c`: `Unknown compression name: `%s'`
- `0x1800f91a0`: `Invalid compression-level option value `%s'`
- `0x1800f9194`: `parsing compression-level option value failed `%s'`
- `0x1800f917d`: `compression-level option value `%ld' out of range`

## pseudocode

```c
__int64 __fastcall 7z_options(__int64 a1, const char *a2, const char *a3)
{
  _DWORD *v3; // rdi
  int v8; // esi
  int v9; // ebx
  int v10; // eax
  intmax_t v11; // rsi
  char *EndPtr; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_DWORD **)(a1 + 248);
  if ( !strcmp_0(a2, "compression") )
  {
    if ( !a3 || !strcmp_0(a3, "copy") || !strcmp_0(a3, "COPY") || !strcmp_0(a3, "store") || !strcmp_0(a3, "STORE") )
    {
      v3[32] = 0;
    }
    else if ( !strcmp_0(a3, "deflate") || !strcmp_0(a3, "DEFLATE") )
    {
      v3[32] = 262408;
    }
    else if ( !strcmp_0(a3, "bzip2") || !strcmp_0(a3, "BZIP2") )
    {
      v3[32] = 262658;
    }
    else if ( !strcmp_0(a3, "lzma1") || !strcmp_0(a3, "LZMA1") )
    {
      v3[32] = 196865;
    }
    else if ( !strcmp_0(a3, "lzma2") || !strcmp_0(a3, "LZMA2") )
    {
      v3[32] = 33;
    }
    else if ( !strcmp_0(a3, "zstd") || !strcmp_0(a3, "ZSTD") )
    {
      v3[32] = 83300609;
    }
    else
    {
      if ( strcmp_0(a3, "ppmd") && strcmp_0(a3, "PPMD") && strcmp_0(a3, "PPMd") )
      {
        archive_set_error(a1, 0xFFFFFFFFLL, "Unknown compression name: `%s'", a3);
        return 4294967271LL;
      }
      v3[32] = 197633;
    }
    return 0;
  }
  if ( !strcmp_0(a2, "compression-level") )
  {
    if ( !a3 || !*a3 )
    {
      archive_set_error(a1, 0xFFFFFFFFLL, "Invalid compression-level option value `%s'", a3);
      return 4294967271LL;
    }
    EndPtr = 0;
    v8 = strtol(a3, &EndPtr, 10);
    if ( !EndPtr || *EndPtr )
    {
      archive_set_error(a1, 0xFFFFFFFFLL, "parsing compression-level option value failed `%s'", a3);
      return 4294967271LL;
    }
    if ( (int)ZSTD_minCLevel() <= 0 )
      v9 = ZSTD_minCLevel();
    else
      v9 = 0;
    v10 = ZSTD_maxCLevel();
    if ( v8 < v9 || v8 > v10 )
    {
      archive_set_error(a1, 0xFFFFFFFFLL, "compression-level option value `%ld' out of range", v8);
      return 4294967271LL;
    }
    v3[33] = v8;
    v3[34] = v8;
    return 0;
  }
  if ( !strcmp_0(a2, "threads") )
  {
    EndPtr = 0;
    if ( a3 )
    {
      if ( *a3 )
      {
        v11 = strtoimax(a3, &EndPtr, 10);
        if ( EndPtr != a3 && !*EndPtr && *(_DWORD *)_o__errno() != 132 && v11 >= 0 )
        {
          if ( !v11 )
            LODWORD(v11) = GetActiveProcessorCount(0xFFFFu);
          v3[35] = v11;
          return 0;
        }
      }
    }
  }
  return 4294967276LL;
}

```

## disassembly

```asm
0x1800f8ed0  push    rbx
0x1800f8ed2  push    rbp
0x1800f8ed3  push    rsi
0x1800f8ed4  push    rdi
0x1800f8ed5  sub     rsp, 28h
0x1800f8ed9  mov     rdi, [rcx+0F8h]
0x1800f8ee0  mov     rsi, rdx
0x1800f8ee3  mov     rbp, rcx
0x1800f8ee6  lea     rdx, aCompression; "compression"
0x1800f8eed  mov     rcx, rsi; Str1
0x1800f8ef0  mov     rbx, r8
0x1800f8ef3  call    strcmp_0
0x1800f8ef8  test    eax, eax
0x1800f8efa  jnz     loc_1800F90F4
0x1800f8f00  test    rbx, rbx
0x1800f8f03  jz      loc_1800F90E3
0x1800f8f09  lea     rdx, aCopy; "copy"
0x1800f8f10  mov     rcx, rbx; Str1
0x1800f8f13  call    strcmp_0
0x1800f8f18  test    eax, eax
0x1800f8f1a  jz      loc_1800F90E3
0x1800f8f20  lea     rdx, aCopy_0; "COPY"
0x1800f8f27  mov     rcx, rbx; Str1
0x1800f8f2a  call    strcmp_0
0x1800f8f2f  test    eax, eax
0x1800f8f31  jz      loc_1800F90E3
0x1800f8f37  lea     rdx, aStore; "store"
0x1800f8f3e  mov     rcx, rbx; Str1
0x1800f8f41  call    strcmp_0
0x1800f8f46  test    eax, eax
0x1800f8f48  jz      loc_1800F90E3
0x1800f8f4e  lea     rdx, aStore_0; "STORE"
0x1800f8f55  mov     rcx, rbx; Str1
0x1800f8f58  call    strcmp_0
0x1800f8f5d  test    eax, eax
0x1800f8f5f  jz      loc_1800F90E3
0x1800f8f65  lea     rdx, aDeflate; "deflate"
0x1800f8f6c  mov     rcx, rbx; Str1
0x1800f8f6f  call    strcmp_0
0x1800f8f74  test    eax, eax
0x1800f8f76  jz      loc_1800F90D7
0x1800f8f7c  lea     rdx, aDeflate_0; "DEFLATE"
0x1800f8f83  mov     rcx, rbx; Str1
0x1800f8f86  call    strcmp_0
0x1800f8f8b  test    eax, eax
0x1800f8f8d  jz      loc_1800F90D7
0x1800f8f93  lea     rdx, aBzip2_0; "bzip2"
0x1800f8f9a  mov     rcx, rbx; Str1
0x1800f8f9d  call    strcmp_0
0x1800f8fa2  test    eax, eax
0x1800f8fa4  jz      loc_1800F90CB
0x1800f8faa  lea     rdx, aBzip2; "BZIP2"
0x1800f8fb1  mov     rcx, rbx; Str1
0x1800f8fb4  call    strcmp_0
0x1800f8fb9  test    eax, eax
0x1800f8fbb  jz      loc_1800F90CB
0x1800f8fc1  lea     rdx, aLzma1; "lzma1"
0x1800f8fc8  mov     rcx, rbx; Str1
0x1800f8fcb  call    strcmp_0
0x1800f8fd0  test    eax, eax
0x1800f8fd2  jz      loc_1800F90BF
0x1800f8fd8  lea     rdx, aLzma1_0; "LZMA1"
0x1800f8fdf  mov     rcx, rbx; Str1
0x1800f8fe2  call    strcmp_0
0x1800f8fe7  test    eax, eax
0x1800f8fe9  jz      loc_1800F90BF
0x1800f8fef  lea     rdx, aLzma2; "lzma2"
0x1800f8ff6  mov     rcx, rbx; Str1
0x1800f8ff9  call    strcmp_0
0x1800f8ffe  test    eax, eax
0x1800f9000  jz      loc_1800F90B3
0x1800f9006  lea     rdx, aLzma2_0; "LZMA2"
0x1800f900d  mov     rcx, rbx; Str1
0x1800f9010  call    strcmp_0
0x1800f9015  test    eax, eax
0x1800f9017  jz      loc_1800F90B3
0x1800f901d  lea     rdx, aZstd; "zstd"
0x1800f9024  mov     rcx, rbx; Str1
0x1800f9027  call    strcmp_0
0x1800f902c  test    eax, eax
0x1800f902e  jz      short loc_1800F90A7
0x1800f9030  lea     rdx, aZstd_0; "ZSTD"
0x1800f9037  mov     rcx, rbx; Str1
0x1800f903a  call    strcmp_0
0x1800f903f  test    eax, eax
0x1800f9041  jz      short loc_1800F90A7
0x1800f9043  lea     rdx, aPpmd; "ppmd"
0x1800f904a  mov     rcx, rbx; Str1
0x1800f904d  call    strcmp_0
0x1800f9052  test    eax, eax
0x1800f9054  jz      short loc_1800F909B
0x1800f9056  lea     rdx, aPpmd_0; "PPMD"
0x1800f905d  mov     rcx, rbx; Str1
0x1800f9060  call    strcmp_0
0x1800f9065  test    eax, eax
0x1800f9067  jz      short loc_1800F909B
0x1800f9069  lea     rdx, aPpmd_1; "PPMd"
0x1800f9070  mov     rcx, rbx; Str1
0x1800f9073  call    strcmp_0
0x1800f9078  test    eax, eax
0x1800f907a  jz      short loc_1800F909B
0x1800f907c  lea     r8, aUnknownCompres; "Unknown compression name: `%s'"
0x1800f9083  mov     r9, rbx
0x1800f9086  or      edx, 0FFFFFFFFh
0x1800f9089  mov     rcx, rbp
0x1800f908c  call    archive_set_error
0x1800f9091  mov     eax, 0FFFFFFE7h
0x1800f9096  jmp     loc_1800F9227
0x1800f909b  mov     dword ptr [rdi+80h], 30401h
0x1800f90a5  jmp     short loc_1800F90ED
0x1800f90a7  mov     dword ptr [rdi+80h], 4F71101h
0x1800f90b1  jmp     short loc_1800F90ED
0x1800f90b3  mov     dword ptr [rdi+80h], 21h ; '!'
0x1800f90bd  jmp     short loc_1800F90ED
0x1800f90bf  mov     dword ptr [rdi+80h], 30101h
0x1800f90c9  jmp     short loc_1800F90ED
0x1800f90cb  mov     dword ptr [rdi+80h], 40202h
0x1800f90d5  jmp     short loc_1800F90ED
0x1800f90d7  mov     dword ptr [rdi+80h], 40108h
0x1800f90e1  jmp     short loc_1800F90ED
0x1800f90e3  mov     dword ptr [rdi+80h], 0
0x1800f90ed  xor     eax, eax
0x1800f90ef  jmp     loc_1800F9227
0x1800f90f4  lea     rdx, aCompressionLev_0; "compression-level"
0x1800f90fb  mov     rcx, rsi; Str1
0x1800f90fe  call    strcmp_0
0x1800f9103  test    eax, eax
0x1800f9105  jnz     loc_1800F91AC
0x1800f910b  test    rbx, rbx
0x1800f910e  jz      loc_1800F91A0
0x1800f9114  cmp     [rbx], al
0x1800f9116  jz      loc_1800F91A0
0x1800f911c  lea     r8d, [rax+0Ah]; Radix
0x1800f9120  mov     [rsp+48h+EndPtr], 0
0x1800f9129  lea     rdx, [rsp+48h+EndPtr]; EndPtr
0x1800f912e  mov     rcx, rbx; String
0x1800f9131  call    cs:__imp_strtol
0x1800f9137  mov     esi, eax
0x1800f9139  mov     rax, [rsp+48h+EndPtr]
0x1800f913e  test    rax, rax
0x1800f9141  jz      short loc_1800F9194
0x1800f9143  cmp     byte ptr [rax], 0
0x1800f9146  jnz     short loc_1800F9194
0x1800f9148  call    ZSTD_minCLevel
0x1800f914d  test    eax, eax
0x1800f914f  jle     short loc_1800F9155
0x1800f9151  xor     ebx, ebx
0x1800f9153  jmp     short loc_1800F915C
0x1800f9155  call    ZSTD_minCLevel
0x1800f915a  mov     ebx, eax
0x1800f915c  call    ZSTD_maxCLevel
0x1800f9161  cmp     esi, ebx
0x1800f9163  jl      short loc_1800F917A
0x1800f9165  cmp     esi, eax
0x1800f9167  jg      short loc_1800F917A
0x1800f9169  mov     [rdi+84h], esi
0x1800f916f  mov     [rdi+88h], esi
0x1800f9175  jmp     loc_1800F90ED
0x1800f917a  mov     r9d, esi
0x1800f917d  lea     r8, aCompressionLev; "compression-level option value `%ld' ou"...
0x1800f9184  or      edx, 0FFFFFFFFh
0x1800f9187  mov     rcx, rbp
0x1800f918a  call    archive_set_error
0x1800f918f  jmp     loc_1800F9091
0x1800f9194  lea     r8, aParsingCompres; "parsing compression-level option value "...
0x1800f919b  jmp     loc_1800F9083
0x1800f91a0  lea     r8, aInvalidCompres_0; "Invalid compression-level option value "...
0x1800f91a7  jmp     loc_1800F9083
0x1800f91ac  lea     rdx, aThreads; "threads"
0x1800f91b3  mov     rcx, rsi; Str1
0x1800f91b6  call    strcmp_0
0x1800f91bb  test    eax, eax
0x1800f91bd  jnz     short loc_1800F9222
0x1800f91bf  mov     [rsp+48h+EndPtr], 0
0x1800f91c8  test    rbx, rbx
0x1800f91cb  jz      short loc_1800F9222
0x1800f91cd  cmp     [rbx], al
0x1800f91cf  jz      short loc_1800F9222
0x1800f91d1  lea     r8d, [rax+0Ah]; Radix
0x1800f91d5  mov     rcx, rbx; String
0x1800f91d8  lea     rdx, [rsp+48h+EndPtr]; EndPtr
0x1800f91dd  call    cs:__imp_strtoimax
0x1800f91e3  mov     rsi, rax
0x1800f91e6  mov     rax, [rsp+48h+EndPtr]
0x1800f91eb  cmp     rax, rbx
0x1800f91ee  jz      short loc_1800F9222
0x1800f91f0  cmp     byte ptr [rax], 0
0x1800f91f3  jnz     short loc_1800F9222
0x1800f91f5  call    cs:__imp__o__errno
0x1800f91fb  cmp     dword ptr [rax], 84h
0x1800f9201  jz      short loc_1800F9222
0x1800f9203  test    rsi, rsi
0x1800f9206  js      short loc_1800F9222
0x1800f9208  jnz     short loc_1800F9217
0x1800f920a  mov     ecx, 0FFFFh; GroupNumber
0x1800f920f  call    cs:__imp_GetActiveProcessorCount
0x1800f9215  mov     esi, eax
0x1800f9217  mov     [rdi+8Ch], esi
0x1800f921d  jmp     loc_1800F90ED
0x1800f9222  mov     eax, 0FFFFFFECh
0x1800f9227  add     rsp, 28h
0x1800f922b  pop     rdi
0x1800f922c  pop     rsi
0x1800f922d  pop     rbp
0x1800f922e  pop     rbx
0x1800f922f  retn
```
