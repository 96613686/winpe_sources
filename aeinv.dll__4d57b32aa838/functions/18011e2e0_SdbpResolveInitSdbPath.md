# SdbpResolveInitSdbPath

- ea: `0x18011e2e0`
- end: `0x18011e47f`
- name: `SdbpResolveInitSdbPath`
- size: `415`
- prototype: `__int64(_WORD *, __int64, int, _WORD *, ...)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18011da30`

## callees

- `0x1800197d4`
- `0x18002256c`
- `0x18006baf0`
- `0x18011c4dc`
- `0x18011e2e0`

## string_xrefs

- `0x18011e330`: `SdbpResolveInitSdbPath`
- `0x18011e353`: `SdbpResolveInitSdbPath`
- `0x18011e3ec`: `SdbpResolveInitSdbPath`
- `0x18011e45a`: `SdbpResolveInitSdbPath`
- `0x18011e31f`: `Failed to copy path [%x]`
- `0x18011e346`: `Database not specified with the database path flag`
- `0x18011e427`: `AslPathCombine failed to copy file path [%x]`
- `0x18011e44d`: `SdbGetPathSystemSdb failed to get file path for SDB_SYSTEM`
- `0x18011e3a7`: `Cannot get standard database path for supplied flags: 0x%x`
- `0x18011e3db`: `SdbGetPathSystemSdb failed to get file path for flags: 0x%x`

## pseudocode

```c
__int64 SdbpResolveInitSdbPath(_WORD *a1, __int64 a2, int a3, _WORD *a4, ...)
{
  int v4; // ebx
  const char *v5; // r9
  int v6; // r8d
  unsigned int v7; // eax
  __int64 v8; // r8
  va_list va; // [rsp+60h] [rbp+28h] BYREF

  va_start(va, a4);
  if ( (a3 & 2) == 0 )
  {
    if ( (a3 & 0xF00F0000) != 0 )
    {
      v7 = a3 & 0xF02F0000;
      if ( (a3 & 0xF02F0000) == 0x80020000 )
      {
        v8 = 4;
      }
      else if ( v7 == -2147287040 )
      {
        v8 = 1;
      }
      else
      {
        if ( v7 != -2147221504 )
        {
          v4 = -1073741811;
          v5 = "Cannot get standard database path for supplied flags: 0x%x";
          v6 = 431;
          goto LABEL_6;
        }
        v8 = 3;
      }
      if ( !(unsigned int)SdbGetPathSystemSdb(a1, a2, v8, va) )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpResolveInitSdbPath",
          436,
          (unsigned int)"SdbGetPathSystemSdb failed to get file path for flags: 0x%x");
        return (unsigned int)-1073741823;
      }
    }
    else
    {
      if ( !a4 )
      {
        if ( (unsigned int)SdbGetPathSystemSdb(a1, a2, 1, va) )
          return 0;
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpResolveInitSdbPath",
          466,
          (unsigned int)"SdbGetPathSystemSdb failed to get file path for SDB_SYSTEM");
        return (unsigned int)-1073741823;
      }
      v4 = AslPathCombine(a4, (__int64)L"sysmain.sdb", a1, 260);
      if ( v4 < 0 )
      {
        v5 = "AslPathCombine failed to copy file path [%x]";
        v6 = 452;
        goto LABEL_6;
      }
    }
    return 0;
  }
  if ( !a4 || !*a4 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpResolveInitSdbPath",
      410,
      (unsigned int)"Database not specified with the database path flag");
    return (unsigned int)-1073741811;
  }
  v4 = RtlStringCchCopyW(a1, 260, a4);
  if ( v4 >= 0 )
    return 0;
  v5 = "Failed to copy path [%x]";
  v6 = 418;
LABEL_6:
  AslLogCallPrintf(1, (unsigned int)"SdbpResolveInitSdbPath", v6, (_DWORD)v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18011e2e0  mov     [rsp+arg_0], rbx
0x18011e2e5  mov     [rsp+arg_8], rsi
0x18011e2ea  push    rdi
0x18011e2eb  sub     rsp, 30h
0x18011e2ef  mov     rax, r9
0x18011e2f2  mov     esi, r8d
0x18011e2f5  test    r8b, 2
0x18011e2f9  jz      short loc_18011E36E
0x18011e2fb  xor     edi, edi
0x18011e2fd  test    rax, rax
0x18011e300  jz      short loc_18011E346
0x18011e302  cmp     [r9], di
0x18011e306  jz      short loc_18011E346
0x18011e308  mov     r8, rax
0x18011e30b  mov     edx, 104h
0x18011e310  call    RtlStringCchCopyW
0x18011e315  mov     ebx, eax
0x18011e317  test    eax, eax
0x18011e319  jns     loc_18011E46B
0x18011e31f  lea     r9, aFailedToCopyPa; "Failed to copy path [%x]"
0x18011e326  mov     r8d, 1A2h
0x18011e32c  mov     [rsp+38h+var_18], eax
0x18011e330  lea     rdx, aSdbpresolveini; "SdbpResolveInitSdbPath"
0x18011e337  mov     ecx, 1
0x18011e33c  call    AslLogCallPrintf
0x18011e341  jmp     loc_18011E46D
0x18011e346  lea     r9, aDatabaseNotSpe; "Database not specified with the databas"...
0x18011e34d  mov     r8d, 19Ah
0x18011e353  lea     rdx, aSdbpresolveini; "SdbpResolveInitSdbPath"
0x18011e35a  mov     ecx, 1
0x18011e35f  call    AslLogCallPrintf
0x18011e364  mov     ebx, 0C000000Dh
0x18011e369  jmp     loc_18011E46D
0x18011e36e  test    esi, 0F00F0000h
0x18011e374  jz      loc_18011E402
0x18011e37a  mov     eax, esi
0x18011e37c  and     eax, 0F02F0000h
0x18011e381  cmp     eax, 80020000h
0x18011e386  jz      short loc_18011E3C1
0x18011e388  cmp     eax, 80030000h
0x18011e38d  jz      short loc_18011E3B9
0x18011e38f  cmp     eax, 80040000h
0x18011e394  jnz     short loc_18011E39E
0x18011e396  mov     r8d, 3
0x18011e39c  jmp     short loc_18011E3C7
0x18011e39e  mov     ebx, 0C000000Dh
0x18011e3a3  mov     [rsp+38h+var_18], esi
0x18011e3a7  lea     r9, aCannotGetStand; "Cannot get standard database path for s"...
0x18011e3ae  mov     r8d, 1AFh
0x18011e3b4  jmp     loc_18011E330
0x18011e3b9  mov     r8d, 1
0x18011e3bf  jmp     short loc_18011E3C7
0x18011e3c1  mov     r8d, 4
0x18011e3c7  lea     r9, [rsp+38h+arg_20]
0x18011e3cc  call    SdbGetPathSystemSdb
0x18011e3d1  xor     edi, edi
0x18011e3d3  test    eax, eax
0x18011e3d5  jnz     loc_18011E46B
0x18011e3db  lea     r9, aSdbgetpathsyst_0; "SdbGetPathSystemSdb failed to get file "...
0x18011e3e2  mov     [rsp+38h+var_18], esi
0x18011e3e6  mov     r8d, 1B4h
0x18011e3ec  lea     rdx, aSdbpresolveini; "SdbpResolveInitSdbPath"
0x18011e3f3  lea     ecx, [rdi+1]
0x18011e3f6  call    AslLogCallPrintf
0x18011e3fb  mov     ebx, 0C0000001h
0x18011e400  jmp     short loc_18011E46D
0x18011e402  xor     edi, edi
0x18011e404  test    rax, rax
0x18011e407  jz      short loc_18011E439
0x18011e409  mov     r8, rcx
0x18011e40c  lea     rdx, aSysmainSdb; "sysmain.sdb"
0x18011e413  mov     rcx, rax
0x18011e416  mov     r9d, 104h
0x18011e41c  call    AslPathCombine
0x18011e421  mov     ebx, eax
0x18011e423  test    eax, eax
0x18011e425  jns     short loc_18011E46B
0x18011e427  lea     r9, aAslpathcombine_1; "AslPathCombine failed to copy file path"...
0x18011e42e  mov     r8d, 1C4h
0x18011e434  jmp     loc_18011E32C
0x18011e439  lea     r9, [rsp+38h+arg_20]
0x18011e43e  mov     r8d, 1
0x18011e444  call    SdbGetPathSystemSdb
0x18011e449  test    eax, eax
0x18011e44b  jnz     short loc_18011E46B
0x18011e44d  lea     r9, aSdbgetpathsyst; "SdbGetPathSystemSdb failed to get file "...
0x18011e454  mov     r8d, 1D2h
0x18011e45a  lea     rdx, aSdbpresolveini; "SdbpResolveInitSdbPath"
0x18011e461  lea     ecx, [rax+1]
0x18011e464  call    AslLogCallPrintf
0x18011e469  jmp     short loc_18011E3FB
0x18011e46b  mov     ebx, edi
0x18011e46d  mov     rsi, [rsp+38h+arg_8]
0x18011e472  mov     eax, ebx
0x18011e474  mov     rbx, [rsp+38h+arg_0]
0x18011e479  add     rsp, 30h
0x18011e47d  pop     rdi
0x18011e47e  retn
```
