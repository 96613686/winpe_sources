# CProfilesHandler::OnDelete(ushort const *,ushort const *,ulong)

- ea: `0x18001a140`
- end: `0x18001a39b`
- name: `?OnDelete@CProfilesHandler@@UEAAJPEBG0K@Z`
- size: `603`
- prototype: `__int64 __fastcall(CProfilesHandler *this, const unsigned __int16 *, const unsigned __int16 *, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002aa0`
- `0x180013368`
- `0x1800133d4`
- `0x18001a140`
- `0x18001a468`
- `0x18001a6a8`
- `0x18001a960`
- `0x18001b1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a23c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a23c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a256`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a198`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a198`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a1cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a1cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a1dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a1dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a24c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a26e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a335`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a24c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a26e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a335`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a2b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a2b4`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001a22f`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001a22f`

## string_xrefs

- `0x18001a2c9`: `Software\Microsoft\Windows\Currentversion\Installer\Managed`

## pseudocode

```c
__int64 __fastcall CProfilesHandler::OnDelete(
        CProfilesHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4)
{
  int v5; // ebx
  int v6; // edi
  CProfilesHandler *v7; // rcx
  signed int SoftwareInstallationDirectory; // edi
  WCHAR *v9; // r15
  const unsigned __int16 *v10; // rcx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rbx
  int v13; // esi
  signed int LastError; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // r15
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rsi
  signed int v19; // ebx
  unsigned __int16 *v20; // rax
  int v21; // eax
  BYTE Data[8]; // [rsp+30h] [rbp-20h] BYREF
  LPCWSTR lpPathName; // [rsp+38h] [rbp-18h] BYREF
  DWORD Type; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+48h] BYREF

  Type = 0;
  cbData = 0;
  hKey = 0;
  *(_DWORD *)Data = 0;
  v5 = 0;
  v6 = a4 & 2;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\System", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"LeaveAppMgmtData", 0, &Type, Data, &cbData) )
      v5 = *(_DWORD *)Data;
    RegCloseKey(hKey);
  }
  if ( !v6 || !v5 )
  {
    lpPathName = 0;
    SoftwareInstallationDirectory = CProfilesHandler::_GetSoftwareInstallationDirectory(
                                      v7,
                                      a2,
                                      (unsigned __int16 **)&lpPathName);
    if ( SoftwareInstallationDirectory < 0 )
      goto LABEL_16;
    v9 = (WCHAR *)lpPathName;
    v10 = lpPathName;
    LODWORD(lpPathName) = 0;
    v11 = SupportLongFileName(v10, (unsigned int *)&lpPathName);
    v12 = v11;
    if ( !v11 )
      goto LABEL_38;
    Delnode_Recurse(v11, (unsigned int)lpPathName);
    if ( RemoveDirectoryW(v9) )
    {
      v13 = 1;
    }
    else
    {
      v13 = 0;
      GetLastError();
    }
    LocalFree(v12);
    if ( !v13 )
    {
LABEL_38:
      LastError = GetLastError();
      SoftwareInstallationDirectory = LastError;
      if ( LastError > 0 )
        SoftwareInstallationDirectory = (unsigned __int16)LastError | 0x80070000;
    }
    LocalFree(v9);
    if ( SoftwareInstallationDirectory < 0 )
    {
LABEL_16:
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(2u, 0xFA0u, a2, (unsigned int)SoftwareInstallationDirectory);
    }
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    v16 = (unsigned int)(v15 + 60);
    v17 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v16);
    v18 = v17;
    if ( v17 )
    {
      LODWORD(lpPathName) = 0;
      v19 = StringCchCopyW(v17, v16, L"Software\\Microsoft\\Windows\\Currentversion\\Installer\\Managed");
      if ( v19 >= 0 )
      {
        v20 = CheckSlashEx(v18, v16, (unsigned int *)&lpPathName);
        if ( v20 )
        {
          v19 = StringCchCopyW(v20, (unsigned int)lpPathName, a2);
          if ( v19 >= 0 )
          {
            v21 = GPRegDelnode(HKEY_LOCAL_MACHINE, v18);
            v19 = v21;
            if ( v21 > 0 )
              v19 = (unsigned __int16)v21 | 0x80070000;
          }
        }
        else
        {
          v19 = -2147024774;
        }
      }
      LocalFree(v18);
      if ( v19 >= 0 )
        goto LABEL_31;
    }
    else
    {
      v19 = -2147024882;
    }
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(2u, 0xFA1u, a2, (unsigned int)v19);
LABEL_31:
    if ( SoftwareInstallationDirectory >= 0 && v19 >= 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4u, 0xFA2u, a2);
  }
  return 0;
}

```

## disassembly

```asm
0x18001a140  mov     [rsp-28h+arg_0], rbx
0x18001a145  mov     [rsp-28h+arg_8], rsi
0x18001a14a  push    rbp
0x18001a14b  push    rdi
0x18001a14c  push    r12
0x18001a14e  push    r14
0x18001a150  push    r15
0x18001a152  mov     rbp, rsp
0x18001a155  sub     rsp, 50h
0x18001a159  xor     r12d, r12d
0x18001a15c  lea     rax, [rbp+hKey]
0x18001a160  mov     edi, r9d
0x18001a163  mov     [rbp+Type], r12d
0x18001a167  mov     r14, rdx
0x18001a16a  mov     [rbp+cbData], r12d
0x18001a16e  mov     r9d, 20019h; samDesired
0x18001a174  mov     [rbp+hKey], r12
0x18001a178  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18001a17f  mov     dword ptr [rbp+Data], r12d
0x18001a183  xor     r8d, r8d; ulOptions
0x18001a186  mov     [rsp+50h+phkResult], rax; phkResult
0x18001a18b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a192  mov     ebx, r12d
0x18001a195  and     edi, 2
0x18001a198  call    cs:__imp_RegOpenKeyExW
0x18001a19e  test    eax, eax
0x18001a1a0  jnz     short loc_18001A1E3
0x18001a1a2  mov     rcx, [rbp+hKey]; hKey
0x18001a1a6  lea     rax, [rbp+cbData]
0x18001a1aa  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18001a1af  lea     r9, [rbp+Type]; lpType
0x18001a1b3  lea     rax, [rbp+Data]
0x18001a1b7  mov     [rbp+cbData], 4
0x18001a1be  xor     r8d, r8d; lpReserved
0x18001a1c1  mov     [rsp+50h+phkResult], rax; lpData
0x18001a1c6  lea     rdx, aLeaveappmgmtda; "LeaveAppMgmtData"
0x18001a1cd  call    cs:__imp_RegQueryValueExW
0x18001a1d3  mov     rcx, [rbp+hKey]; hKey
0x18001a1d7  test    eax, eax
0x18001a1d9  cmovz   ebx, dword ptr [rbp+Data]
0x18001a1dd  call    cs:__imp_RegCloseKey
0x18001a1e3  test    edi, edi
0x18001a1e5  jz      short loc_18001A1EF
0x18001a1e7  test    ebx, ebx
0x18001a1e9  jnz     loc_18001A380
0x18001a1ef  lea     r8, [rbp+lpPathName]; unsigned __int16 **
0x18001a1f3  mov     [rbp+lpPathName], r12
0x18001a1f7  mov     rdx, r14; unsigned __int16 *
0x18001a1fa  call    ?_GetSoftwareInstallationDirectory@CProfilesHandler@@AEAAJPEBGPEAPEAG@Z; CProfilesHandler::_GetSoftwareInstallationDirectory(ushort const *,ushort * *)
0x18001a1ff  mov     edi, eax
0x18001a201  test    eax, eax
0x18001a203  js      short loc_18001A278
0x18001a205  mov     r15, [rbp+lpPathName]
0x18001a209  lea     rdx, [rbp+lpPathName]; unsigned int *
0x18001a20d  mov     rcx, r15; unsigned __int16 *
0x18001a210  mov     dword ptr [rbp+lpPathName], r12d
0x18001a214  call    ?SupportLongFileName@@YAPEAGPEBGPEAK@Z; SupportLongFileName(ushort const *,ulong *)
0x18001a219  mov     rbx, rax
0x18001a21c  test    rax, rax
0x18001a21f  jz      short loc_18001A256
0x18001a221  mov     edx, dword ptr [rbp+lpPathName]; unsigned int
0x18001a224  mov     rcx, rax; unsigned __int16 *
0x18001a227  call    ?Delnode_Recurse@@YAHPEAGK@Z; Delnode_Recurse(ushort *,ulong)
0x18001a22c  mov     rcx, r15; lpPathName
0x18001a22f  call    cs:__imp_RemoveDirectoryW
0x18001a235  test    eax, eax
0x18001a237  jnz     short loc_18001A244
0x18001a239  mov     esi, r12d
0x18001a23c  call    cs:__imp_GetLastError
0x18001a242  jmp     short loc_18001A249
0x18001a244  mov     esi, 1
0x18001a249  mov     rcx, rbx; hMem
0x18001a24c  call    cs:__imp_LocalFree
0x18001a252  test    esi, esi
0x18001a254  jnz     short loc_18001A26B
0x18001a256  call    cs:__imp_GetLastError
0x18001a25c  mov     edi, eax
0x18001a25e  test    eax, eax
0x18001a260  jle     short loc_18001A26B
0x18001a262  movzx   edi, ax
0x18001a265  or      edi, 80070000h
0x18001a26b  mov     rcx, r15; hMem
0x18001a26e  call    cs:__imp_LocalFree
0x18001a274  test    edi, edi
0x18001a276  jns     short loc_18001A296
0x18001a278  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x18001a27f  jz      short loc_18001A296
0x18001a281  mov     r9d, edi
0x18001a284  mov     r8, r14
0x18001a287  mov     edx, 0FA0h; unsigned int
0x18001a28c  mov     ecx, 2; unsigned int
0x18001a291  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001a296  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a29a  inc     rax
0x18001a29d  cmp     [r14+rax*2], r12w
0x18001a2a2  jnz     short loc_18001A29A
0x18001a2a4  lea     r15d, [rax+3Ch]
0x18001a2a8  mov     ecx, 40h ; '@'; uFlags
0x18001a2ad  lea     rdx, [r15+r15]; uBytes
0x18001a2b1  mov     ebx, r15d
0x18001a2b4  call    cs:__imp_LocalAlloc
0x18001a2ba  mov     rsi, rax
0x18001a2bd  test    rax, rax
0x18001a2c0  jnz     short loc_18001A2C9
0x18001a2c2  mov     ebx, 8007000Eh
0x18001a2c7  jmp     short loc_18001A33F
0x18001a2c9  lea     r8, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\Currentve"...
0x18001a2d0  mov     dword ptr [rbp+lpPathName], r12d
0x18001a2d4  mov     rdx, rbx; unsigned __int64
0x18001a2d7  mov     rcx, rsi; unsigned __int16 *
0x18001a2da  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a2df  mov     ebx, eax
0x18001a2e1  test    eax, eax
0x18001a2e3  js      short loc_18001A332
0x18001a2e5  lea     r8, [rbp+lpPathName]; unsigned int *
0x18001a2e9  mov     edx, r15d; unsigned int
0x18001a2ec  mov     rcx, rsi; unsigned __int16 *
0x18001a2ef  call    ?CheckSlashEx@@YAPEAGPEAGIPEAI@Z; CheckSlashEx(ushort *,uint,uint *)
0x18001a2f4  test    rax, rax
0x18001a2f7  jnz     short loc_18001A300
0x18001a2f9  mov     ebx, 8007007Ah
0x18001a2fe  jmp     short loc_18001A332
0x18001a300  mov     edx, dword ptr [rbp+lpPathName]; unsigned __int64
0x18001a303  mov     r8, r14; unsigned __int16 *
0x18001a306  mov     rcx, rax; unsigned __int16 *
0x18001a309  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a30e  mov     ebx, eax
0x18001a310  test    eax, eax
0x18001a312  js      short loc_18001A332
0x18001a314  mov     rdx, rsi; unsigned __int16 *
0x18001a317  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18001a31e  call    ?GPRegDelnode@@YAKPEAUHKEY__@@PEBG@Z; GPRegDelnode(HKEY__ *,ushort const *)
0x18001a323  mov     ebx, eax
0x18001a325  test    eax, eax
0x18001a327  jle     short loc_18001A332
0x18001a329  movzx   ebx, ax
0x18001a32c  or      ebx, 80070000h
0x18001a332  mov     rcx, rsi; hMem
0x18001a335  call    cs:__imp_LocalFree
0x18001a33b  test    ebx, ebx
0x18001a33d  jns     short loc_18001A35D
0x18001a33f  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x18001a346  jz      short loc_18001A35D
0x18001a348  mov     r9d, ebx
0x18001a34b  mov     r8, r14
0x18001a34e  mov     edx, 0FA1h; unsigned int
0x18001a353  mov     ecx, 2; unsigned int
0x18001a358  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001a35d  test    edi, edi
0x18001a35f  js      short loc_18001A380
0x18001a361  test    ebx, ebx
0x18001a363  js      short loc_18001A380
0x18001a365  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x18001a36c  jz      short loc_18001A380
0x18001a36e  mov     r8, r14
0x18001a371  mov     edx, 0FA2h; unsigned int
0x18001a376  mov     ecx, 4; unsigned int
0x18001a37b  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001a380  lea     r11, [rsp+50h+var_s0]
0x18001a385  xor     eax, eax
0x18001a387  mov     rbx, [r11+30h]
0x18001a38b  mov     rsi, [r11+38h]
0x18001a38f  mov     rsp, r11
0x18001a392  pop     r15
0x18001a394  pop     r14
0x18001a396  pop     r12
0x18001a398  pop     rdi
0x18001a399  pop     rbp
0x18001a39a  retn
```
