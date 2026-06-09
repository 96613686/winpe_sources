# LoadModFromSystem

- ea: `0x1800035f4`
- end: `0x1800036e7`
- name: `LoadModFromSystem`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180003ac8`

## callees

- `0x180002590`
- `0x180002634`
- `0x1800035f4`
- `0x180007040`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x18000361b`
- `KERNEL32!GetSystemDirectoryW` at `0x18000361b`
- `KERNEL32!GetLastError` at `0x180003625`
- `KERNEL32!GetLastError` at `0x180003625`
- `KERNEL32!LoadLibraryW` at `0x1800036c2`
- `KERNEL32!LoadLibraryW` at `0x1800036c2`

## string_xrefs

- `0x180003648`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`
- `0x1800036a0`: `msi.dll`
- `0x180003675`: `MSI-COFIRE WARNING: %s:%d - hr = 0x%08X\n`

## pseudocode

```c
HMODULE LoadModFromSystem()
{
  __int64 v0; // rbx
  UINT SystemDirectoryW; // eax
  unsigned __int64 v2; // rdx
  signed int LastError; // eax
  int v4; // r9d
  unsigned __int64 v5; // rdx
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  v0 = 0;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( SystemDirectoryW )
  {
    if ( SystemDirectoryW >= 0x104 )
    {
      DebugPrint(1u, "MSI-COFIRE WARNING: %s:%d - hr = 0x%08X\n", "LoadModFromSystem", 917, 0);
      return (HMODULE)v0;
    }
    LastError = StringCbCatW(Buffer, v2, L"\\");
    if ( LastError >= 0 )
    {
      LastError = StringCbCatW(Buffer, v5, L"msi.dll");
      if ( LastError >= 0 )
        return LoadLibraryW(Buffer);
      v4 = 932;
    }
    else
    {
      v4 = 925;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = 914;
  }
  DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "LoadModFromSystem", v4, LastError);
  return (HMODULE)v0;
}

```

## disassembly

```asm
0x1800035f4  push    rbx
0x1800035f6  sub     rsp, 250h
0x1800035fd  mov     rax, cs:__security_cookie
0x180003604  xor     rax, rsp
0x180003607  mov     [rsp+258h+var_18], rax
0x18000360f  mov     edx, 104h; uSize
0x180003614  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180003619  xor     ebx, ebx
0x18000361b  call    cs:__imp_GetSystemDirectoryW
0x180003621  test    eax, eax
0x180003623  jnz     short loc_180003658
0x180003625  call    cs:__imp_GetLastError
0x18000362b  test    eax, eax
0x18000362d  jle     short loc_180003637
0x18000362f  movzx   eax, ax
0x180003632  or      eax, 80070000h
0x180003637  mov     r9d, 392h
0x18000363d  lea     r8, aLoadmodfromsys; "LoadModFromSystem"
0x180003644  mov     [rsp+258h+var_238], eax
0x180003648  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x18000364f  xor     ecx, ecx; Level
0x180003651  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180003656  jmp     short loc_1800036CB
0x180003658  cmp     eax, 104h
0x18000365d  jb      short loc_180003683
0x18000365f  mov     r9d, 395h
0x180003665  mov     [rsp+258h+var_238], ebx
0x180003669  lea     r8, aLoadmodfromsys; "LoadModFromSystem"
0x180003670  mov     ecx, 1; Level
0x180003675  lea     rdx, aMsiCofireWarni; "MSI-COFIRE WARNING: %s:%d - hr = 0x%08X"...
0x18000367c  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180003681  jmp     short loc_1800036CB
0x180003683  lea     r8, asc_18000AAF4; "\\"
0x18000368a  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x18000368f  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180003694  test    eax, eax
0x180003696  jns     short loc_1800036A0
0x180003698  mov     r9d, 39Dh
0x18000369e  jmp     short loc_18000363D
0x1800036a0  lea     r8, aMsiDll; "msi.dll"
0x1800036a7  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x1800036ac  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800036b1  test    eax, eax
0x1800036b3  jns     short loc_1800036BD
0x1800036b5  mov     r9d, 3A4h
0x1800036bb  jmp     short loc_18000363D
0x1800036bd  lea     rcx, [rsp+258h+Buffer]; lpLibFileName
0x1800036c2  call    cs:__imp_LoadLibraryW
0x1800036c8  mov     rbx, rax
0x1800036cb  mov     rax, rbx
0x1800036ce  mov     rcx, [rsp+258h+var_18]
0x1800036d6  xor     rcx, rsp; StackCookie
0x1800036d9  call    __security_check_cookie
0x1800036de  add     rsp, 250h
0x1800036e5  pop     rbx
0x1800036e6  retn
```
