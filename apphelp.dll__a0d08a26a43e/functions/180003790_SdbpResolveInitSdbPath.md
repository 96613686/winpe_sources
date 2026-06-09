# SdbpResolveInitSdbPath

- ea: `0x180003790`
- end: `0x18000392a`
- name: `SdbpResolveInitSdbPath`
- size: `410`
- prototype: `__int64(__int64, __int64, unsigned int, _WORD *, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180002be0`

## callees

- `0x180003760`
- `0x180003790`
- `0x180003930`
- `0x180005318`
- `0x1800055e0`
- `0x18000f114`
- `0x1800483e4`

## string_xrefs

- `0x1800037f2`: `SdbpResolveInitSdbPath`
- `0x180003849`: `SdbpResolveInitSdbPath`
- `0x180003899`: `SdbpResolveInitSdbPath`
- `0x1800038ef`: `SdbpResolveInitSdbPath`
- `0x1800037e5`: `SdbGetPathSystemSdb failed to get file path for SDB_SYSTEM`
- `0x18000383c`: `Database not specified with the database path flag`
- `0x180003861`: `Failed to copy path [%x]`
- `0x18000388c`: `Cannot get standard database path for supplied flags: 0x%x`
- `0x1800038de`: `SdbGetPathSystemSdb failed to get file path for flags: 0x%x`
- `0x180003870`: `AslPathCombine failed to copy file path [%x]`

## pseudocode

```c
__int64 SdbpResolveInitSdbPath(__int64 a1, __int64 a2, unsigned int a3, _WORD *a4, ...)
{
  unsigned int v5; // ebx
  int v6; // eax
  const char *v8; // r9
  __int64 v9; // r8
  unsigned int SdbFileFromInitSdbFlags; // eax
  __int64 v11; // r10
  int v12; // [rsp+20h] [rbp-18h]
  va_list va; // [rsp+60h] [rbp+28h] BYREF

  va_start(va, a4);
  if ( (a3 & 2) != 0 )
  {
    if ( !a4 || !*a4 )
    {
      AslLogCallPrintf(1, "SdbpResolveInitSdbPath", 410, "Database not specified with the database path flag");
      return (unsigned int)-1073741811;
    }
    v6 = RtlStringCchCopyW(a1, 260, a4);
    v5 = v6;
    if ( v6 >= 0 )
      return 0;
    v8 = "Failed to copy path [%x]";
    v9 = 418;
LABEL_14:
    v12 = v6;
    goto LABEL_16;
  }
  if ( (a3 & 0xF00F0000) != 0 )
  {
    SdbFileFromInitSdbFlags = SdbpGetSdbFileFromInitSdbFlags(a3);
    if ( SdbFileFromInitSdbFlags && SdbFileFromInitSdbFlags != 11 )
    {
      if ( !(unsigned int)SdbGetPathSystemSdb(v11, 260, SdbFileFromInitSdbFlags, va) )
      {
        AslLogCallPrintf(
          1,
          "SdbpResolveInitSdbPath",
          436,
          "SdbGetPathSystemSdb failed to get file path for flags: 0x%x",
          a3);
        return (unsigned int)-1073741823;
      }
      return 0;
    }
    v5 = -1073741811;
    v12 = a3;
    v8 = "Cannot get standard database path for supplied flags: 0x%x";
    v9 = 431;
LABEL_16:
    AslLogCallPrintf(1, "SdbpResolveInitSdbPath", v9, v8, v12);
    return v5;
  }
  if ( a4 )
  {
    v6 = AslPathCombine(a4, L"sysmain.sdb", a1, 260);
    v5 = v6;
    if ( v6 >= 0 )
      return 0;
    v8 = "AslPathCombine failed to copy file path [%x]";
    v9 = 452;
    goto LABEL_14;
  }
  if ( (int)SdbpGetSystemSdbFilePath(a1, 260, 1, 0, 0, (__int64)va) >= 0 )
    return 0;
  AslLogCallPrintf(1, "SdbpResolveInitSdbPath", 466, "SdbGetPathSystemSdb failed to get file path for SDB_SYSTEM");
  return (unsigned int)-1073741823;
}

```

## disassembly

```asm
0x180003790  mov     r11, rsp
0x180003793  mov     [r11+8], rbx
0x180003797  mov     [r11+10h], rsi
0x18000379b  push    rdi
0x18000379c  sub     rsp, 30h
0x1800037a0  mov     rax, r9
0x1800037a3  mov     esi, r8d
0x1800037a6  mov     r10, rcx
0x1800037a9  test    r8b, 2
0x1800037ad  jnz     short loc_180003808
0x1800037af  test    r8d, 0F00F0000h
0x1800037b6  jnz     loc_1800038AF
0x1800037bc  xor     edi, edi
0x1800037be  test    rax, rax
0x1800037c1  jnz     loc_180003903
0x1800037c7  lea     rax, [r11+28h]
0x1800037cb  mov     edx, 104h
0x1800037d0  mov     [r11-10h], rax
0x1800037d4  lea     r8d, [r9+1]
0x1800037d8  mov     [r11-18h], rdi
0x1800037dc  call    SdbpGetSystemSdbFilePath
0x1800037e1  test    eax, eax
0x1800037e3  jns     short loc_180003828
0x1800037e5  lea     r9, aSdbgetpathsyst_0; "SdbGetPathSystemSdb failed to get file "...
0x1800037ec  mov     r8d, 1D2h
0x1800037f2  lea     rdx, aSdbpresolveini; "SdbpResolveInitSdbPath"
0x1800037f9  lea     ecx, [rdi+1]
0x1800037fc  call    AslLogCallPrintf
0x180003801  mov     ebx, 0C0000001h
0x180003806  jmp     short loc_18000382A
0x180003808  xor     edi, edi
0x18000380a  test    rax, rax
0x18000380d  jz      short loc_18000383C
0x18000380f  cmp     [r9], di
0x180003813  jz      short loc_18000383C
0x180003815  mov     r8, rax
0x180003818  mov     edx, 104h
0x18000381d  call    RtlStringCchCopyW
0x180003822  mov     ebx, eax
0x180003824  test    eax, eax
0x180003826  js      short loc_180003861
0x180003828  mov     ebx, edi
0x18000382a  mov     rsi, [rsp+38h+arg_8]
0x18000382f  mov     eax, ebx
0x180003831  mov     rbx, [rsp+38h+arg_0]
0x180003836  add     rsp, 30h
0x18000383a  pop     rdi
0x18000383b  retn
0x18000383c  lea     r9, aDatabaseNotSpe; "Database not specified with the databas"...
0x180003843  mov     r8d, 19Ah
0x180003849  lea     rdx, aSdbpresolveini; "SdbpResolveInitSdbPath"
0x180003850  mov     ecx, 1
0x180003855  call    AslLogCallPrintf
0x18000385a  mov     ebx, 0C000000Dh
0x18000385f  jmp     short loc_18000382A
0x180003861  lea     r9, aFailedToCopyPa; "Failed to copy path [%x]"
0x180003868  mov     r8d, 1A2h
0x18000386e  jmp     short loc_18000387D
0x180003870  lea     r9, aAslpathcombine_1; "AslPathCombine failed to copy file path"...
0x180003877  mov     r8d, 1C4h
0x18000387d  mov     [rsp+38h+var_18], eax
0x180003881  jmp     short loc_180003899
0x180003883  mov     ebx, 0C000000Dh
0x180003888  mov     [rsp+38h+var_18], esi
0x18000388c  lea     r9, aCannotGetStand; "Cannot get standard database path for s"...
0x180003893  mov     r8d, 1AFh
0x180003899  lea     rdx, aSdbpresolveini; "SdbpResolveInitSdbPath"
0x1800038a0  mov     ecx, 1
0x1800038a5  call    AslLogCallPrintf
0x1800038aa  jmp     loc_18000382A
0x1800038af  mov     ecx, esi
0x1800038b1  call    SdbpGetSdbFileFromInitSdbFlags
0x1800038b6  xor     edi, edi
0x1800038b8  test    eax, eax
0x1800038ba  jz      short loc_180003883
0x1800038bc  cmp     eax, 0Bh
0x1800038bf  jz      short loc_180003883
0x1800038c1  lea     r9, [rsp+38h+arg_20]
0x1800038c6  mov     r8d, eax
0x1800038c9  mov     edx, 104h
0x1800038ce  mov     rcx, r10
0x1800038d1  call    SdbGetPathSystemSdb
0x1800038d6  test    eax, eax
0x1800038d8  jnz     loc_180003828
0x1800038de  lea     r9, aSdbgetpathsyst_1; "SdbGetPathSystemSdb failed to get file "...
0x1800038e5  mov     [rsp+38h+var_18], esi
0x1800038e9  mov     r8d, 1B4h
0x1800038ef  lea     rdx, aSdbpresolveini; "SdbpResolveInitSdbPath"
0x1800038f6  lea     ecx, [rdi+1]
0x1800038f9  call    AslLogCallPrintf
0x1800038fe  jmp     loc_180003801
0x180003903  mov     r9d, 104h
0x180003909  lea     rdx, aSysmainSdb; "sysmain.sdb"
0x180003910  mov     r8, r10
0x180003913  mov     rcx, rax
0x180003916  call    AslPathCombine
0x18000391b  mov     ebx, eax
0x18000391d  test    eax, eax
0x18000391f  jns     loc_180003828
0x180003925  jmp     loc_180003870
```
