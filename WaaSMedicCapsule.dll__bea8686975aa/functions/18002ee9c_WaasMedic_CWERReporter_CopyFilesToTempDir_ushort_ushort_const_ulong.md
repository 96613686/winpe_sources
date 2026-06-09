# WaasMedic::CWERReporter::CopyFilesToTempDir(ushort *,ushort * * const,ulong)

- ea: `0x18002ee9c`
- end: `0x18002f0e1`
- name: `?CopyFilesToTempDir@CWERReporter@WaasMedic@@AEAAJPEAGQEAPEAGK@Z`
- size: `581`
- prototype: `int(WaasMedic::CWERReporter *__hidden this, unsigned __int16 *, unsigned __int16 **const, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18002ede4`

## callees

- `0x180003bb0`
- `0x18000a5d0`
- `0x18002543c`
- `0x18002ee9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f08b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f08b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002ef3b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002ef3b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002eeda`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002eeda`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002effa`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002effa`

## string_xrefs

- `0x18002ef05`: `Failed to create directory %s! hr=0x%08x`
- `0x18002f0a4`: `Failed to expand log file share path %s! hr = 0x%08x`
- `0x18002f062`: `Failed to calculate length of the path %s! hr = 0x%08x`
- `0x18002f06f`: `Failed to expand log file share path %s due to insufficient buffer. Saved %u characters.! hr = 0x%08x`
- `0x18002f03c`: `Failed to copy file from %s to %s! hr = 0x%08x`
- `0x18002f052`: `Failed to format destination file path for file %s! hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::CWERReporter::CopyFilesToTempDir(
        WaasMedic::CWERReporter *this,
        unsigned __int16 *a2,
        unsigned __int16 **const a3,
        unsigned int a4)
{
  signed int v7; // eax
  unsigned int v8; // ebx
  int v9; // r14d
  DWORD v10; // eax
  __int64 v11; // r8
  WCHAR *v12; // rax
  __int64 v13; // rdx
  WCHAR *i; // rax
  int v15; // eax
  signed int LastError; // eax
  signed int v17; // eax
  __int64 v19; // [rsp+20h] [rbp-E0h]
  WCHAR Dst[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR NewFileName[264]; // [rsp+240h] [rbp+140h] BYREF

  if ( CreateDirectoryW(a2, 0) || (v7 = GetLastError(), v8 = v7, v7 == 183) )
  {
    v8 = 0;
    v9 = 0;
    if ( a4 )
    {
      while ( 1 )
      {
        v10 = ExpandEnvironmentStringsW(a3[v9], Dst, 0x104u);
        if ( !v10 )
          break;
        if ( v10 > 0x104 )
        {
          v8 = -2147024774;
          LODWORD(v19) = -2147024774;
          LogLevelW(
            2u,
            L"Failed to expand log file share path %s due to insufficient buffer. Saved %u characters.! hr = 0x%08x",
            a3[v9],
            v10,
            v19);
          return v8;
        }
        v11 = 0x7FFFFFFF;
        v12 = Dst;
        do
        {
          if ( !*v12 )
            break;
          ++v12;
          --v11;
        }
        while ( v11 );
        v8 = v11 == 0 ? 0x80070057 : 0;
        v13 = (0x7FFFFFFF - v11) & ((unsigned __int128)-(__int128)(unsigned __int64)v11 >> 64);
        if ( !v11 )
        {
          LogLevelW(2u, L"Failed to calculate length of the path %s! hr = 0x%08x", Dst, v8);
          return v8;
        }
        for ( i = &Dst[v13]; v13 && Dst[v13 - 1] != 92 && i != Dst; --i )
          --v13;
        v15 = StringCchPrintfW(NewFileName, 0x104u, L"%s\\%s", a2, i);
        v8 = v15;
        if ( v15 < 0 )
        {
          LogLevelW(2u, L"Failed to format destination file path for file %s! hr = 0x%08x", Dst, (unsigned int)v15);
          return v8;
        }
        if ( !CopyFileW(Dst, NewFileName, 0) )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          LODWORD(v19) = v8;
          LogLevelW(2u, L"Failed to copy file from %s to %s! hr = 0x%08x", Dst, NewFileName, v19);
          return v8;
        }
        if ( ++v9 >= a4 )
          return v8;
      }
      v17 = GetLastError();
      v8 = v17;
      if ( v17 > 0 )
        v8 = (unsigned __int16)v17 | 0x80070000;
      LogLevelW(2u, L"Failed to expand log file share path %s! hr = 0x%08x", a3[v9], v8);
    }
  }
  else
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    LogLevelW(2u, L"Failed to create directory %s! hr=0x%08x", a2, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x18002ee9c  mov     [rsp-8+arg_0], rbx
0x18002eea1  push    rbp
0x18002eea2  push    rsi
0x18002eea3  push    rdi
0x18002eea4  push    r12
0x18002eea6  push    r13
0x18002eea8  push    r14
0x18002eeaa  push    r15
0x18002eeac  lea     rbp, [rsp-360h]
0x18002eeb4  sub     rsp, 460h
0x18002eebb  mov     rax, cs:__security_cookie
0x18002eec2  xor     rax, rsp
0x18002eec5  mov     [rbp+390h+var_40], rax
0x18002eecc  mov     r13, rdx
0x18002eecf  mov     r12d, r9d
0x18002eed2  mov     rcx, r13; lpPathName
0x18002eed5  xor     edx, edx; lpSecurityAttributes
0x18002eed7  mov     r15, r8
0x18002eeda  call    cs:__imp_CreateDirectoryW
0x18002eee0  xor     edi, edi
0x18002eee2  test    eax, eax
0x18002eee4  jnz     short loc_18002EF16
0x18002eee6  call    cs:__imp_GetLastError
0x18002eeec  mov     ebx, eax
0x18002eeee  cmp     eax, 0B7h
0x18002eef3  jz      short loc_18002EF16
0x18002eef5  test    eax, eax
0x18002eef7  jle     short loc_18002EF02
0x18002eef9  movzx   ebx, ax
0x18002eefc  or      ebx, 80070000h
0x18002ef02  mov     r8, r13
0x18002ef05  lea     rdx, aFailedToCreate_3; "Failed to create directory %s! hr=0x%08"...
0x18002ef0c  mov     ecx, 2
0x18002ef11  jmp     loc_18002F0AD
0x18002ef16  mov     ebx, edi
0x18002ef18  mov     r14d, edi
0x18002ef1b  test    r12d, r12d
0x18002ef1e  jz      loc_18002F0B5
0x18002ef24  mov     edi, 2
0x18002ef29  mov     esi, r14d
0x18002ef2c  lea     rdx, [rsp+490h+Dst]; lpDst
0x18002ef31  mov     r8d, 104h; nSize
0x18002ef37  mov     rcx, [r15+rsi*8]; lpSrc
0x18002ef3b  call    cs:__imp_ExpandEnvironmentStringsW
0x18002ef41  test    eax, eax
0x18002ef43  jz      loc_18002F08B
0x18002ef49  cmp     eax, 104h
0x18002ef4e  ja      loc_18002F06B
0x18002ef54  mov     r8d, 7FFFFFFFh
0x18002ef5a  lea     rax, [rsp+490h+Dst]
0x18002ef5f  xor     esi, esi
0x18002ef61  cmp     [rax], si
0x18002ef64  jz      short loc_18002EF6F
0x18002ef66  add     rax, rdi
0x18002ef69  sub     r8, 1
0x18002ef6d  jnz     short loc_18002EF61
0x18002ef6f  mov     rax, r8
0x18002ef72  mov     ecx, 7FFFFFFFh
0x18002ef77  neg     rax
0x18002ef7a  mov     rax, r8
0x18002ef7d  sbb     ebx, ebx
0x18002ef7f  sub     rcx, r8
0x18002ef82  not     ebx
0x18002ef84  and     ebx, 80070057h
0x18002ef8a  neg     rax
0x18002ef8d  sbb     rdx, rdx
0x18002ef90  and     rdx, rcx
0x18002ef93  test    r8, r8
0x18002ef96  jz      loc_18002F05D
0x18002ef9c  lea     rax, [rsp+490h+Dst]
0x18002efa1  lea     rax, [rax+rdx*2]
0x18002efa5  jmp     short loc_18002EFBF
0x18002efa7  cmp     [rsp+rdx*2+490h+var_462], 5Ch ; '\'
0x18002efad  jz      short loc_18002EFC5
0x18002efaf  lea     rcx, [rsp+490h+Dst]
0x18002efb4  cmp     rax, rcx
0x18002efb7  jz      short loc_18002EFC5
0x18002efb9  dec     rdx
0x18002efbc  sub     rax, rdi
0x18002efbf  cmp     rdx, 1
0x18002efc3  jnb     short loc_18002EFA7
0x18002efc5  mov     r9, r13
0x18002efc8  mov     [rsp+490h+var_470], rax
0x18002efcd  lea     r8, aSS; "%s\\%s"
0x18002efd4  mov     edx, 104h; unsigned __int64
0x18002efd9  lea     rcx, [rbp+390h+NewFileName]; unsigned __int16 *
0x18002efe0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002efe5  mov     ebx, eax
0x18002efe7  test    eax, eax
0x18002efe9  js      short loc_18002F04A
0x18002efeb  xor     r8d, r8d; bFailIfExists
0x18002efee  lea     rdx, [rbp+390h+NewFileName]; lpNewFileName
0x18002eff5  lea     rcx, [rsp+490h+Dst]; lpExistingFileName
0x18002effa  call    cs:__imp_CopyFileW
0x18002f000  test    eax, eax
0x18002f002  jz      short loc_18002F015
0x18002f004  inc     r14d
0x18002f007  cmp     r14d, r12d
0x18002f00a  jb      loc_18002EF29
0x18002f010  jmp     loc_18002F0B5
0x18002f015  call    cs:__imp_GetLastError
0x18002f01b  mov     ebx, eax
0x18002f01d  test    eax, eax
0x18002f01f  jle     short loc_18002F02A
0x18002f021  movzx   ebx, ax
0x18002f024  or      ebx, 80070000h
0x18002f02a  lea     r9, [rbp+390h+NewFileName]
0x18002f031  mov     dword ptr [rsp+490h+var_470], ebx
0x18002f035  lea     r8, [rsp+490h+Dst]
0x18002f03a  mov     ecx, edi; unsigned __int8
0x18002f03c  lea     rdx, aFailedToCopyFi; "Failed to copy file from %s to %s! hr ="...
0x18002f043  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002f048  jmp     short loc_18002F0B5
0x18002f04a  mov     r9d, eax
0x18002f04d  lea     r8, [rsp+490h+Dst]
0x18002f052  lea     rdx, aFailedToFormat; "Failed to format destination file path "...
0x18002f059  mov     ecx, edi
0x18002f05b  jmp     short loc_18002F0B0
0x18002f05d  lea     r8, [rsp+490h+Dst]
0x18002f062  lea     rdx, aFailedToCalcul_0; "Failed to calculate length of the path "...
0x18002f069  jmp     short loc_18002F0AB
0x18002f06b  mov     r8, [r15+rsi*8]
0x18002f06f  lea     rdx, aFailedToExpand_4; "Failed to expand log file share path %s"...
0x18002f076  mov     ebx, 8007007Ah
0x18002f07b  mov     r9d, eax
0x18002f07e  mov     ecx, edi; unsigned __int8
0x18002f080  mov     dword ptr [rsp+490h+var_470], ebx
0x18002f084  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002f089  jmp     short loc_18002F0B5
0x18002f08b  call    cs:__imp_GetLastError
0x18002f091  mov     ebx, eax
0x18002f093  test    eax, eax
0x18002f095  jle     short loc_18002F0A0
0x18002f097  movzx   ebx, ax
0x18002f09a  or      ebx, 80070000h
0x18002f0a0  mov     r8, [r15+rsi*8]
0x18002f0a4  lea     rdx, aFailedToExpand_0; "Failed to expand log file share path %s"...
0x18002f0ab  mov     ecx, edi; unsigned __int8
0x18002f0ad  mov     r9d, ebx
0x18002f0b0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002f0b5  mov     eax, ebx
0x18002f0b7  mov     rcx, [rbp+390h+var_40]
0x18002f0be  xor     rcx, rsp; StackCookie
0x18002f0c1  call    __security_check_cookie
0x18002f0c6  mov     rbx, [rsp+490h+arg_0]
0x18002f0ce  add     rsp, 460h
0x18002f0d5  pop     r15
0x18002f0d7  pop     r14
0x18002f0d9  pop     r13
0x18002f0db  pop     r12
0x18002f0dd  pop     rdi
0x18002f0de  pop     rsi
0x18002f0df  pop     rbp
0x18002f0e0  retn
```
