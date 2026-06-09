# SdbpResolveInitSdbPath

- ea: `0x140042e28`
- end: `0x140042fbc`
- name: `SdbpResolveInitSdbPath`
- size: `404`
- prototype: `__int64 __usercall@<rax>(NTSTRSAFE_PWSTR pszDest@<rcx>, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140042724`

## callees

- `0x1400012f0`
- `0x14002e8e8`
- `0x14003e364`
- `0x140040a5c`
- `0x140042e28`
- `0x140042fc4`
- `0x140042fec`

## string_xrefs

- `0x140042e85`: `SdbpResolveInitSdbPath`
- `0x140042f08`: `SdbpResolveInitSdbPath`
- `0x140042f2b`: `SdbpResolveInitSdbPath`
- `0x140042f81`: `SdbpResolveInitSdbPath`
- `0x140042e78`: `SdbGetPathSystemSdb failed to get file path for SDB_SYSTEM`
- `0x140042f1e`: `Database not specified with the database path flag`
- `0x140042ed0`: `Failed to copy path [%x]`
- `0x140042efb`: `Cannot get standard database path for supplied flags: 0x%x`
- `0x140042f70`: `SdbGetPathSystemSdb failed to get file path for flags: 0x%x`
- `0x140042edf`: `AslPathCombine failed to copy file path [%x]`

## pseudocode

```c
__int64 SdbpResolveInitSdbPath(NTSTRSAFE_PWSTR pszDest, int a2, unsigned int a3, const wchar_t *a4, ...)
{
  unsigned int v5; // edi
  NTSTATUS v7; // eax
  const char *v8; // r9
  __int64 v9; // r8
  unsigned int SdbFileFromInitSdbFlags; // eax
  __int64 v11; // rdx
  __int64 v12; // r10
  NTSTATUS v13; // [rsp+20h] [rbp-18h]
  va_list va; // [rsp+60h] [rbp+28h] BYREF

  va_start(va, a4);
  if ( (a3 & 2) != 0 )
  {
    if ( !a4 || !*a4 )
    {
      AslLogCallPrintf(1, "SdbpResolveInitSdbPath", 410, "Database not specified with the database path flag");
      return (unsigned int)-1073741811;
    }
    v7 = RtlStringCchCopyW(pszDest, 0x104u, a4);
    v5 = v7;
    if ( v7 >= 0 )
      return 0;
    v8 = "Failed to copy path [%x]";
    v9 = 418;
LABEL_13:
    v13 = v7;
    goto LABEL_15;
  }
  if ( (a3 & 0xF00F0000) != 0 )
  {
    SdbFileFromInitSdbFlags = SdbpGetSdbFileFromInitSdbFlags(a3);
    if ( SdbFileFromInitSdbFlags && SdbFileFromInitSdbFlags != 11 )
    {
      if ( !(unsigned int)SdbGetPathSystemSdb(v12, v11, SdbFileFromInitSdbFlags, va) )
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
    v13 = a3;
    v8 = "Cannot get standard database path for supplied flags: 0x%x";
    v9 = 431;
LABEL_15:
    AslLogCallPrintf(1, "SdbpResolveInitSdbPath", v9, v8, v13);
    return v5;
  }
  if ( a4 )
  {
    v7 = AslPathCombine(a4, L"sysmain.sdb", pszDest, 0x104u);
    v5 = v7;
    if ( v7 >= 0 )
      return 0;
    v8 = "AslPathCombine failed to copy file path [%x]";
    v9 = 452;
    goto LABEL_13;
  }
  if ( (int)SdbpGetSystemSdbFilePath((_DWORD)pszDest, a2, 1, 0, 0, (__int64)va) >= 0 )
    return 0;
  AslLogCallPrintf(1, "SdbpResolveInitSdbPath", 466, "SdbGetPathSystemSdb failed to get file path for SDB_SYSTEM");
  return (unsigned int)-1073741823;
}

```

## disassembly

```asm
0x140042e28  mov     r11, rsp
0x140042e2b  mov     [r11+8], rbx
0x140042e2f  mov     [r11+10h], rsi
0x140042e33  push    rdi
0x140042e34  sub     rsp, 30h
0x140042e38  mov     rax, r9
0x140042e3b  mov     esi, r8d
0x140042e3e  mov     r10, rcx
0x140042e41  test    r8b, 2
0x140042e45  jnz     short loc_140042EB0
0x140042e47  test    r8d, 0F00F0000h
0x140042e4e  jnz     loc_140042F46
0x140042e54  xor     ebx, ebx
0x140042e56  test    rax, rax
0x140042e59  jnz     loc_140042F95
0x140042e5f  lea     rax, [r11+28h]
0x140042e63  mov     [r11-10h], rax
0x140042e67  lea     r8d, [r9+1]
0x140042e6b  mov     [r11-18h], rbx
0x140042e6f  call    SdbpGetSystemSdbFilePath
0x140042e74  test    eax, eax
0x140042e76  jns     short loc_140042EAC
0x140042e78  lea     r9, aSdbgetpathsyst; "SdbGetPathSystemSdb failed to get file "...
0x140042e7f  mov     r8d, 1D2h
0x140042e85  lea     rdx, aSdbpresolveini; "SdbpResolveInitSdbPath"
0x140042e8c  lea     ecx, [rbx+1]
0x140042e8f  call    AslLogCallPrintf
0x140042e94  mov     edi, 0C0000001h
0x140042e99  mov     rbx, [rsp+38h+arg_0]
0x140042e9e  mov     eax, edi
0x140042ea0  mov     rsi, [rsp+38h+arg_8]
0x140042ea5  add     rsp, 30h
0x140042ea9  pop     rdi
0x140042eaa  retn
0x140042eac  mov     edi, ebx
0x140042eae  jmp     short loc_140042E99
0x140042eb0  xor     ebx, ebx
0x140042eb2  test    rax, rax
0x140042eb5  jz      short loc_140042F1E
0x140042eb7  cmp     [r9], bx
0x140042ebb  jz      short loc_140042F1E
0x140042ebd  mov     r8, rax; pszSrc
0x140042ec0  mov     edx, 104h; cchDest
0x140042ec5  call    RtlStringCchCopyW
0x140042eca  mov     edi, eax
0x140042ecc  test    eax, eax
0x140042ece  jns     short loc_140042EAC
0x140042ed0  lea     r9, aFailedToCopyPa; "Failed to copy path [%x]"
0x140042ed7  mov     r8d, 1A2h
0x140042edd  jmp     short loc_140042EEC
0x140042edf  lea     r9, aAslpathcombine_1; "AslPathCombine failed to copy file path"...
0x140042ee6  mov     r8d, 1C4h
0x140042eec  mov     [rsp+38h+var_18], eax
0x140042ef0  jmp     short loc_140042F08
0x140042ef2  mov     edi, 0C000000Dh
0x140042ef7  mov     [rsp+38h+var_18], esi
0x140042efb  lea     r9, aCannotGetStand; "Cannot get standard database path for s"...
0x140042f02  mov     r8d, 1AFh
0x140042f08  lea     rdx, aSdbpresolveini; "SdbpResolveInitSdbPath"
0x140042f0f  mov     ecx, 1
0x140042f14  call    AslLogCallPrintf
0x140042f19  jmp     loc_140042E99
0x140042f1e  lea     r9, aDatabaseNotSpe; "Database not specified with the databas"...
0x140042f25  mov     r8d, 19Ah
0x140042f2b  lea     rdx, aSdbpresolveini; "SdbpResolveInitSdbPath"
0x140042f32  mov     ecx, 1
0x140042f37  call    AslLogCallPrintf
0x140042f3c  mov     edi, 0C000000Dh
0x140042f41  jmp     loc_140042E99
0x140042f46  mov     ecx, esi
0x140042f48  call    SdbpGetSdbFileFromInitSdbFlags
0x140042f4d  xor     ebx, ebx
0x140042f4f  test    eax, eax
0x140042f51  jz      short loc_140042EF2
0x140042f53  cmp     eax, 0Bh
0x140042f56  jz      short loc_140042EF2
0x140042f58  lea     r9, [rsp+38h+arg_20]
0x140042f5d  mov     r8d, eax
0x140042f60  mov     rcx, r10
0x140042f63  call    SdbGetPathSystemSdb
0x140042f68  test    eax, eax
0x140042f6a  jnz     loc_140042EAC
0x140042f70  lea     r9, aSdbgetpathsyst_0; "SdbGetPathSystemSdb failed to get file "...
0x140042f77  mov     [rsp+38h+var_18], esi
0x140042f7b  mov     r8d, 1B4h
0x140042f81  lea     rdx, aSdbpresolveini; "SdbpResolveInitSdbPath"
0x140042f88  lea     ecx, [rbx+1]
0x140042f8b  call    AslLogCallPrintf
0x140042f90  jmp     loc_140042E94
0x140042f95  mov     r9d, 104h; cchDest
0x140042f9b  lea     rdx, aSysmainSdb; "sysmain.sdb"
0x140042fa2  mov     r8, r10; pszDest
0x140042fa5  mov     rcx, rax; pszSrc
0x140042fa8  call    AslPathCombine
0x140042fad  mov     edi, eax
0x140042faf  test    eax, eax
0x140042fb1  jns     loc_140042EAC
0x140042fb7  jmp     loc_140042EDF
```
