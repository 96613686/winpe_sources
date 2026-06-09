# COfflineSystem::SetContext(eOfflineContextID,ushort const *)

- ea: `0x1801a9574`
- end: `0x1801a9858`
- name: `?SetContext@COfflineSystem@@QEAAKW4eOfflineContextID@@PEBG@Z`
- size: `740`
- prototype: `unsigned int __high(enum eOfflineContextID, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801a9860`

## callees

- `0x180046220`
- `0x180071494`
- `0x180074bd0`
- `0x180113f98`
- `0x1801a8fc4`
- `0x1801a9574`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x1801a9827`
- `ADVAPI32!RegOpenKeyExW` at `0x1801a96fa`
- `ADVAPI32!RegOpenKeyExW` at `0x1801a973e`
- `ADVAPI32!RegOpenKeyExW` at `0x1801a96fa`
- `ADVAPI32!RegOpenKeyExW` at `0x1801a973e`
- `ADVAPI32!RegOpenKeyExW` at `0x1801a9819`
- `ADVAPI32!RegCloseKey` at `0x1801a9751`
- `ADVAPI32!RegCloseKey` at `0x1801a976a`
- `ADVAPI32!RegCloseKey` at `0x1801a9787`
- `ADVAPI32!RegCloseKey` at `0x1801a97a9`
- `ADVAPI32!RegCloseKey` at `0x1801a9751`
- `ADVAPI32!RegCloseKey` at `0x1801a976a`
- `ADVAPI32!RegCloseKey` at `0x1801a9787`
- `ADVAPI32!RegCloseKey` at `0x1801a97a9`
- `KERNEL32!LocalAlloc` at `0x1801a9656`
- `KERNEL32!LocalAlloc` at `0x1801a9656`

## string_xrefs

- `0x1801a9693`: `\Installer\`

## pseudocode

```c
__int64 __fastcall COfflineSystem::SetContext(HKEY a1, int a2, const WCHAR *a3)
{
  unsigned __int64 v5; // rbx
  unsigned int FileAttributes; // eax
  unsigned __int16 *v7; // rax
  COfflineSystem *v8; // rcx
  unsigned int LogicInstallerPath; // ebx
  int (__high *v11)(const unsigned __int16 *, enum ismEnum, struct IStorage **); // rax
  struct _FILETIME *phkResult; // [rsp+20h] [rbp-10h]
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF
  HKEY v14; // [rsp+68h] [rbp+38h] BYREF

  hKey = a1;
  switch ( a2 )
  {
    case 0:
      COfflineSystem::ReleaseRegistryKeys((COfflineSystem *)&g_OfflineSystem);
      RegOpenKeyAPI = RegOpenKeyExW;
      RegCreateKeyAPI = (int (*)(HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY *, unsigned int *))RegCreateKeyExW;
      v11 = (int (__high *)(const unsigned __int16 *, enum ismEnum, struct IStorage **))&RealOpenRootStorage;
      goto LABEL_43;
    case 1:
      if ( !g_OfflineSystem || !qword_180309618 || !(_DWORD)dword_180309630 )
        return 1627;
      RegOpenKeyAPI = (int (*)(HKEY, const unsigned __int16 *, unsigned int, unsigned int, HKEY *))OfflineRegOpenKey;
      RegCreateKeyAPI = (int (*)(HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY *, unsigned int *))OfflineRegCreateKey;
      v11 = (int (__high *)(const unsigned __int16 *, enum ismEnum, struct IStorage **))&OfflineOpenRootStorage;
LABEL_43:
      OpenRootStorage = v11;
      return 0;
    case 2:
    case 3:
      if ( a3 )
      {
        if ( *a3 )
        {
          hKey = 0;
          if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, &hKey) )
          {
            if ( a2 != 2 )
            {
              if ( qword_180309618 )
                RegCloseKey(qword_180309618);
              qword_180309618 = hKey;
              return 0;
            }
            LogicInstallerPath = COfflineSystem::GetLogicInstallerPath(v8, hKey);
            if ( !LogicInstallerPath )
            {
              v14 = 0;
              if ( !RegOpenKeyExW(hKey, L"Classes", 0, 0x20019u, &v14) )
              {
                if ( g_OfflineSystem )
                  RegCloseKey(g_OfflineSystem);
                g_OfflineSystem = hKey;
                if ( ::hKey )
                  RegCloseKey(::hKey);
                ::hKey = v14;
                return 0;
              }
              LogicInstallerPath = 87;
            }
            RegCloseKey(hKey);
            return LogicInstallerPath;
          }
        }
      }
      return 87;
  }
  if ( a2 != 4 )
    return 87;
  if ( !a3 )
    return 87;
  if ( !*a3 )
    return 87;
  hKey = 0;
  if ( (int)StringCchLengthW(a3, 0x104u, (unsigned __int64 *)&hKey) < 0 )
    return 87;
  v5 = (unsigned __int64)hKey;
  if ( hKey && a3[(_QWORD)hKey - 1] == 92 )
    v5 = (unsigned __int64)hKey - 1;
  if ( v5 - 1 > 0x102 )
    return 87;
  FileAttributes = MsiGetFileAttributesEx(a3, 0, 0, 0, phkResult, 0);
  if ( FileAttributes == -1 || (FileAttributes & 0x10) == 0 )
    return 87;
  v7 = qword_180309620;
  if ( !qword_180309620 )
  {
    v7 = (unsigned __int16 *)LocalAlloc(0, 0x208u);
    qword_180309620 = v7;
    if ( !v7 )
      return 1627;
  }
  LODWORD(dword_180309630) = 0;
  if ( (int)StringCchCopyNW(v7, 0x104u, a3, v5) < 0
    || (int)StringCchCopyNW(&qword_180309620[v5], 260 - v5, L"\\Installer\\", 0xBu) < 0 )
  {
    return 1627;
  }
  LODWORD(dword_180309630) = v5 + 11;
  return 0;
}

```

## disassembly

```asm
0x1801a9574  mov     [rsp-18h+arg_8], rbx
0x1801a9579  mov     [rsp-18h+arg_10], rsi
0x1801a957e  mov     [rsp-18h+hKey], rcx
0x1801a9583  push    rbp
0x1801a9584  push    rdi
0x1801a9585  push    r14
0x1801a9587  mov     rbp, rsp
0x1801a958a  sub     rsp, 30h
0x1801a958e  xor     r14d, r14d
0x1801a9591  mov     rdi, r8
0x1801a9594  mov     ebx, edx
0x1801a9596  mov     ecx, edx
0x1801a9598  test    edx, edx
0x1801a959a  jz      loc_1801A980D
0x1801a95a0  sub     ecx, 1
0x1801a95a3  jz      loc_1801A97C6
0x1801a95a9  sub     ecx, 1
0x1801a95ac  jz      loc_1801A96C5
0x1801a95b2  sub     ecx, 1
0x1801a95b5  jz      loc_1801A96C5
0x1801a95bb  cmp     ecx, 1
0x1801a95be  jnz     loc_1801A97BF
0x1801a95c4  test    r8, r8
0x1801a95c7  jz      loc_1801A97BF
0x1801a95cd  cmp     [r8], r14w
0x1801a95d1  jz      loc_1801A97BF
0x1801a95d7  mov     esi, 104h
0x1801a95dc  mov     [rbp+hKey], r14
0x1801a95e0  mov     edx, esi; unsigned __int64
0x1801a95e2  lea     r8, [rbp+hKey]; unsigned __int64 *
0x1801a95e6  mov     rcx, rdi; unsigned __int16 *
0x1801a95e9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1801a95ee  test    eax, eax
0x1801a95f0  js      loc_1801A97BF
0x1801a95f6  mov     rbx, [rbp+hKey]
0x1801a95fa  test    rbx, rbx
0x1801a95fd  jz      short loc_1801A960D
0x1801a95ff  lea     eax, [r14+5Ch]
0x1801a9603  cmp     ax, [rdi+rbx*2-2]
0x1801a9608  jnz     short loc_1801A960D
0x1801a960a  dec     rbx
0x1801a960d  lea     rax, [rbx-1]
0x1801a9611  cmp     rax, 102h
0x1801a9617  ja      loc_1801A97BF
0x1801a961d  xor     r9d, r9d; struct _FILETIME *
0x1801a9620  mov     [rsp+30h+var_8], r14; struct _FILETIME *
0x1801a9625  xor     r8d, r8d; unsigned __int64 *
0x1801a9628  xor     edx, edx; unsigned int *
0x1801a962a  mov     rcx, rdi; lpFileName
0x1801a962d  call    ?MsiGetFileAttributesEx@@YAKPEBGPEAKPEA_KPEAU_FILETIME@@33@Z; MsiGetFileAttributesEx(ushort const *,ulong *,unsigned __int64 *,_FILETIME *,_FILETIME *,_FILETIME *)
0x1801a9632  cmp     eax, 0FFFFFFFFh
0x1801a9635  jz      loc_1801A97BF
0x1801a963b  test    al, 10h
0x1801a963d  jz      loc_1801A97BF
0x1801a9643  mov     rax, cs:qword_180309620
0x1801a964a  test    rax, rax
0x1801a964d  jnz     short loc_1801A966C
0x1801a964f  mov     edx, 208h; uBytes
0x1801a9654  xor     ecx, ecx; uFlags
0x1801a9656  call    cs:__imp_LocalAlloc
0x1801a965c  mov     cs:qword_180309620, rax
0x1801a9663  test    rax, rax
0x1801a9666  jz      loc_1801A9806
0x1801a966c  mov     r9, rbx; unsigned __int64
0x1801a966f  mov     cs:dword_180309630, r14d
0x1801a9676  mov     r8, rdi; unsigned __int16 *
0x1801a9679  mov     rdx, rsi; unsigned __int64
0x1801a967c  mov     rcx, rax; unsigned __int16 *
0x1801a967f  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1801a9684  test    eax, eax
0x1801a9686  js      loc_1801A9806
0x1801a968c  mov     rax, cs:qword_180309620
0x1801a9693  lea     r8, aInstaller_0; "\\Installer\\"
0x1801a969a  sub     rsi, rbx
0x1801a969d  mov     r9d, 0Bh; unsigned __int64
0x1801a96a3  mov     rdx, rsi; unsigned __int64
0x1801a96a6  lea     rcx, [rax+rbx*2]; unsigned __int16 *
0x1801a96aa  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1801a96af  test    eax, eax
0x1801a96b1  js      loc_1801A9806
0x1801a96b7  lea     eax, [rbx+0Bh]
0x1801a96ba  mov     cs:dword_180309630, eax
0x1801a96c0  jmp     loc_1801A9843
0x1801a96c5  test    rdi, rdi
0x1801a96c8  jz      loc_1801A97BF
0x1801a96ce  cmp     [r8], r14w
0x1801a96d2  jz      loc_1801A97BF
0x1801a96d8  lea     rax, [rbp+hKey]
0x1801a96dc  mov     [rbp+hKey], r14
0x1801a96e0  mov     esi, 20019h
0x1801a96e5  mov     [rsp+30h+phkResult], rax; phkResult
0x1801a96ea  mov     r9d, esi; samDesired
0x1801a96ed  xor     r8d, r8d; ulOptions
0x1801a96f0  mov     rdx, rdi; lpSubKey
0x1801a96f3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801a96fa  call    cs:__imp_RegOpenKeyExW
0x1801a9700  test    eax, eax
0x1801a9702  jnz     loc_1801A97BF
0x1801a9708  cmp     ebx, 2
0x1801a970b  jnz     loc_1801A979D
0x1801a9711  mov     rdx, [rbp+hKey]; HKEY
0x1801a9715  call    ?GetLogicInstallerPath@COfflineSystem@@IEAAKPEAUHKEY__@@@Z; COfflineSystem::GetLogicInstallerPath(HKEY__ *)
0x1801a971a  mov     ebx, eax
0x1801a971c  test    eax, eax
0x1801a971e  jnz     short loc_1801A974D
0x1801a9720  mov     rcx, [rbp+hKey]; hKey
0x1801a9724  lea     rax, [rbp+arg_18]
0x1801a9728  mov     r9d, esi; samDesired
0x1801a972b  mov     [rsp+30h+phkResult], rax; phkResult
0x1801a9730  xor     r8d, r8d; ulOptions
0x1801a9733  mov     [rbp+arg_18], r14
0x1801a9737  lea     rdx, aClasses; "Classes"
0x1801a973e  call    cs:__imp_RegOpenKeyExW
0x1801a9744  test    eax, eax
0x1801a9746  jz      short loc_1801A975E
0x1801a9748  mov     ebx, 57h ; 'W'
0x1801a974d  mov     rcx, [rbp+hKey]; hKey
0x1801a9751  call    cs:__imp_RegCloseKey
0x1801a9757  mov     eax, ebx
0x1801a9759  jmp     loc_1801A9845
0x1801a975e  mov     rcx, cs:?g_OfflineSystem@@3VCOfflineSystem@@A; hKey
0x1801a9765  test    rcx, rcx
0x1801a9768  jz      short loc_1801A9770
0x1801a976a  call    cs:__imp_RegCloseKey
0x1801a9770  mov     rcx, cs:hKey; hKey
0x1801a9777  mov     rax, [rbp+hKey]
0x1801a977b  mov     cs:?g_OfflineSystem@@3VCOfflineSystem@@A, rax; COfflineSystem g_OfflineSystem
0x1801a9782  test    rcx, rcx
0x1801a9785  jz      short loc_1801A978D
0x1801a9787  call    cs:__imp_RegCloseKey
0x1801a978d  mov     rax, [rbp+arg_18]
0x1801a9791  mov     cs:hKey, rax
0x1801a9798  jmp     loc_1801A9843
0x1801a979d  mov     rcx, cs:qword_180309618; hKey
0x1801a97a4  test    rcx, rcx
0x1801a97a7  jz      short loc_1801A97AF
0x1801a97a9  call    cs:__imp_RegCloseKey
0x1801a97af  mov     rax, [rbp+hKey]
0x1801a97b3  mov     cs:qword_180309618, rax
0x1801a97ba  jmp     loc_1801A9843
0x1801a97bf  mov     eax, 57h ; 'W'
0x1801a97c4  jmp     short loc_1801A9845
0x1801a97c6  cmp     cs:?g_OfflineSystem@@3VCOfflineSystem@@A, r14; COfflineSystem g_OfflineSystem
0x1801a97cd  jz      short loc_1801A9806
0x1801a97cf  cmp     cs:qword_180309618, r14
0x1801a97d6  jz      short loc_1801A9806
0x1801a97d8  cmp     cs:dword_180309630, r14d
0x1801a97df  jz      short loc_1801A9806
0x1801a97e1  lea     rax, ?OfflineRegOpenKey@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; OfflineRegOpenKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x1801a97e8  mov     cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA, rax; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x1801a97ef  lea     rax, ?OfflineRegCreateKey@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; OfflineRegCreateKey(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x1801a97f6  mov     cs:?RegCreateKeyAPI@@3P6AJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@ZEA, rax; long (*RegCreateKeyAPI)(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x1801a97fd  lea     rax, ?OfflineOpenRootStorage@@YAJPEBGW4ismEnum@@PEAPEAUIStorage@@@Z; OfflineOpenRootStorage(ushort const *,ismEnum,IStorage * *)
0x1801a9804  jmp     short loc_1801A983C
0x1801a9806  mov     eax, 65Bh
0x1801a980b  jmp     short loc_1801A9845
0x1801a980d  lea     rcx, ?g_OfflineSystem@@3VCOfflineSystem@@A; this
0x1801a9814  call    ?ReleaseRegistryKeys@COfflineSystem@@IEAAXXZ; COfflineSystem::ReleaseRegistryKeys(void)
0x1801a9819  mov     rax, cs:__imp_RegOpenKeyExW
0x1801a9820  mov     cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA, rax; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x1801a9827  mov     rax, cs:__imp_RegCreateKeyExW
0x1801a982e  mov     cs:?RegCreateKeyAPI@@3P6AJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@ZEA, rax; long (*RegCreateKeyAPI)(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x1801a9835  lea     rax, ?RealOpenRootStorage@@YAJPEBGW4ismEnum@@PEAPEAUIStorage@@@Z; RealOpenRootStorage(ushort const *,ismEnum,IStorage * *)
0x1801a983c  mov     cs:?OpenRootStorage@@3P6AJPEBGW4ismEnum@@PEAPEAUIStorage@@@ZEA, rax; long (*OpenRootStorage)(ushort const *,ismEnum,IStorage * *)
0x1801a9843  xor     eax, eax
0x1801a9845  mov     rbx, [rsp+30h+arg_8]
0x1801a984a  mov     rsi, [rsp+30h+arg_10]
0x1801a984f  add     rsp, 30h
0x1801a9853  pop     r14
0x1801a9855  pop     rdi
0x1801a9856  pop     rbp
0x1801a9857  retn
```
