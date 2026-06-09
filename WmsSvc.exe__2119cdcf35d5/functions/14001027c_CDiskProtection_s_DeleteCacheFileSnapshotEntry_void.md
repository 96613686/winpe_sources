# CDiskProtection::s_DeleteCacheFileSnapshotEntry(void)

- ea: `0x14001027c`
- end: `0x14001043d`
- name: `?s_DeleteCacheFileSnapshotEntry@CDiskProtection@@KAJXZ`
- size: `449`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140013794`

## callees

- `0x14001027c`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400102bc`
- `ADVAPI32!RegOpenKeyExW` at `0x1400102bc`
- `ADVAPI32!RegCloseKey` at `0x14001042b`
- `ADVAPI32!RegCloseKey` at `0x14001042b`
- `ADVAPI32!RegDeleteValueW` at `0x140010365`
- `ADVAPI32!RegDeleteValueW` at `0x140010365`
- `KERNEL32!IsDebuggerPresent` at `0x14001030c`
- `KERNEL32!IsDebuggerPresent` at `0x1400103d4`
- `KERNEL32!IsDebuggerPresent` at `0x14001030c`
- `KERNEL32!IsDebuggerPresent` at `0x1400103d4`

## string_xrefs

- `0x140010286`: `CDiskProtection::s_DeleteCacheFileSnapshotEntry\n`
- `0x1400102e2`: `CDiskProtection::s_DeleteCacheFileSnapshotEntry`
- `0x1400103aa`: `CDiskProtection::s_DeleteCacheFileSnapshotEntry`
- `0x140010377`: `CDiskProtection::s_DeleteCacheFileSnapshotEntry - %s was not present, ignoring.\n`
- `0x140010415`: `CDiskProtection::s_DeleteCacheFileSnapshotEntry - Exiting, hr = 0x%08X\n`

## pseudocode

```c
__int64 CDiskProtection::s_DeleteCacheFileSnapshotEntry(void)
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  __int64 v2; // r9
  __int64 v3; // r8
  LSTATUS v4; // eax
  unsigned int v6; // [rsp+30h] [rbp-38h]
  unsigned int v7; // [rsp+38h] [rbp-30h]
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  hKey = 0;
  DEBUGMSG(L"CDiskProtection::s_DeleteCacheFileSnapshotEntry\n");
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\BackupRestore\\FilesNotToSnapshot",
         0,
         2u,
         &hKey);
  v1 = v0;
  if ( v0 )
  {
    if ( v0 > 0 )
      v1 = (unsigned __int16)v0 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x1291u,
      L"CDiskProtection::s_DeleteCacheFileSnapshotEntry",
      L"CBRAEx",
      L"lResult == 0L",
      v1);
    if ( IsDebuggerPresent() )
    {
      v2 = 4753;
LABEL_6:
      v7 = v1;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v2,
        L"CDiskProtection::s_DeleteCacheFileSnapshotEntry",
        L"CBRAEx",
        L"lResult == 0L",
        v7);
      goto LABEL_18;
    }
    v3 = 4753;
LABEL_17:
    v6 = v1;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v3,
      L"CDiskProtection::s_DeleteCacheFileSnapshotEntry",
      L"CBRAEx",
      L"lResult == 0L",
      v6);
    goto LABEL_18;
  }
  v1 = 0;
  v4 = RegDeleteValueW(hKey, L"Windows MultiPoint Server Disk Protection");
  if ( v4 == 2 )
  {
    DEBUGMSG(
      L"CDiskProtection::s_DeleteCacheFileSnapshotEntry - %s was not present, ignoring.\n",
      L"Windows MultiPoint Server Disk Protection");
    goto LABEL_18;
  }
  if ( v4 )
  {
    if ( v4 > 0 )
      v1 = (unsigned __int16)v4 | 0x80070000;
    else
      v1 = v4;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x129Au,
      L"CDiskProtection::s_DeleteCacheFileSnapshotEntry",
      L"CBRAEx",
      L"lResult == 0L",
      v1);
    if ( IsDebuggerPresent() )
    {
      v2 = 4762;
      goto LABEL_6;
    }
    v3 = 4762;
    goto LABEL_17;
  }
LABEL_18:
  DEBUGMSG(L"CDiskProtection::s_DeleteCacheFileSnapshotEntry - Exiting, hr = 0x%08X\n", v1);
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x14001027c  push    rbx
0x14001027e  push    rbp
0x14001027f  push    rsi
0x140010280  push    r14
0x140010282  sub     rsp, 48h
0x140010286  lea     rcx, aCdiskprotectio_124; "CDiskProtection::s_DeleteCacheFileSnaps"...
0x14001028d  mov     [rsp+68h+hKey], 0
0x140010296  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14001029b  lea     rax, [rsp+68h+hKey]
0x1400102a0  mov     r9d, 2; samDesired
0x1400102a6  xor     r8d, r8d; ulOptions
0x1400102a9  mov     [rsp+68h+phkResult], rax; phkResult
0x1400102ae  lea     rdx, ?s_szFilesNotToSnapshot@CDiskProtection@@1QBGB; "SYSTEM\\CurrentControlSet\\Control\\Bac"...
0x1400102b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400102bc  call    cs:__imp_RegOpenKeyExW
0x1400102c2  mov     ebx, eax
0x1400102c4  test    eax, eax
0x1400102c6  jz      loc_140010357
0x1400102cc  jle     short loc_1400102D7
0x1400102ce  movzx   ebx, ax
0x1400102d1  or      ebx, 80070000h
0x1400102d7  lea     r14, aCbraex; "CBRAEx"
0x1400102de  mov     [rsp+68h+var_40], ebx; int
0x1400102e2  lea     rsi, aCdiskprotectio_104; "CDiskProtection::s_DeleteCacheFileSnaps"...
0x1400102e9  mov     r9, r14; unsigned __int16 *
0x1400102ec  lea     rbp, aLresult0l; "lResult == 0L"
0x1400102f3  mov     r8, rsi; unsigned __int16 *
0x1400102f6  mov     edx, 1291h; unsigned int
0x1400102fb  mov     [rsp+68h+phkResult], rbp; unsigned __int16 *
0x140010300  lea     rcx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140010307  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001030c  call    cs:__imp_IsDebuggerPresent
0x140010312  test    eax, eax
0x140010314  jz      short loc_14001034C
0x140010316  mov     r9d, 1291h
0x14001031c  mov     [rsp+68h+var_30], ebx
0x140010320  lea     r8, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140010327  mov     [rsp+68h+var_38], rbp
0x14001032c  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140010333  mov     qword ptr [rsp+68h+var_40], r14
0x140010338  mov     ecx, 2; unsigned __int8
0x14001033d  mov     [rsp+68h+phkResult], rsi
0x140010342  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140010347  jmp     loc_140010413
0x14001034c  mov     r8d, 1291h
0x140010352  jmp     loc_1400103EF
0x140010357  mov     rcx, [rsp+68h+hKey]; hKey
0x14001035c  lea     rdx, ?s_szWmsDp@CDiskProtection@@1QBGB; "Windows MultiPoint Server Disk Protecti"...
0x140010363  xor     ebx, ebx
0x140010365  call    cs:__imp_RegDeleteValueW
0x14001036b  cmp     eax, 2
0x14001036e  jnz     short loc_140010388
0x140010370  lea     rdx, ?s_szWmsDp@CDiskProtection@@1QBGB; "Windows MultiPoint Server Disk Protecti"...
0x140010377  lea     rcx, aCdiskprotectio_172; "CDiskProtection::s_DeleteCacheFileSnaps"...
0x14001037e  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140010383  jmp     loc_140010413
0x140010388  test    eax, eax
0x14001038a  jz      loc_140010413
0x140010390  jg      short loc_140010396
0x140010392  mov     ebx, eax
0x140010394  jmp     short loc_14001039F
0x140010396  movzx   ebx, ax
0x140010399  or      ebx, 80070000h
0x14001039f  lea     r14, aCbraex; "CBRAEx"
0x1400103a6  mov     [rsp+68h+var_40], ebx; int
0x1400103aa  lea     rsi, aCdiskprotectio_104; "CDiskProtection::s_DeleteCacheFileSnaps"...
0x1400103b1  mov     r9, r14; unsigned __int16 *
0x1400103b4  lea     rbp, aLresult0l; "lResult == 0L"
0x1400103bb  mov     r8, rsi; unsigned __int16 *
0x1400103be  mov     edx, 129Ah; unsigned int
0x1400103c3  mov     [rsp+68h+phkResult], rbp; unsigned __int16 *
0x1400103c8  lea     rcx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x1400103cf  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400103d4  call    cs:__imp_IsDebuggerPresent
0x1400103da  test    eax, eax
0x1400103dc  jz      short loc_1400103E9
0x1400103de  mov     r9d, 129Ah
0x1400103e4  jmp     loc_14001031C
0x1400103e9  mov     r8d, 129Ah
0x1400103ef  mov     dword ptr [rsp+68h+var_38], ebx
0x1400103f3  lea     rdx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x1400103fa  mov     qword ptr [rsp+68h+var_40], rbp
0x1400103ff  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140010406  mov     r9, rsi
0x140010409  mov     [rsp+68h+phkResult], r14
0x14001040e  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140010413  mov     edx, ebx
0x140010415  lea     rcx, aCdiskprotectio_8; "CDiskProtection::s_DeleteCacheFileSnaps"...
0x14001041c  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140010421  mov     rcx, [rsp+68h+hKey]; hKey
0x140010426  test    rcx, rcx
0x140010429  jz      short loc_140010431
0x14001042b  call    cs:__imp_RegCloseKey
0x140010431  mov     eax, ebx
0x140010433  add     rsp, 48h
0x140010437  pop     r14
0x140010439  pop     rsi
0x14001043a  pop     rbp
0x14001043b  pop     rbx
0x14001043c  retn
```
