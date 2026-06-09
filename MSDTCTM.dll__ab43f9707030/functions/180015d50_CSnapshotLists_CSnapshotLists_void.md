# CSnapshotLists::CSnapshotLists(void)

- ea: `0x180015d50`
- end: `0x180015e8e`
- name: `??0CSnapshotLists@@QEAA@XZ`
- size: `318`
- prototype: `CSnapshotLists *__fastcall(CSnapshotLists *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002220`

## callees

- `0x180015d50`
- `0x180015e94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180015e27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180015e27`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180015e55`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180015e55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015e75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015e75`

## string_xrefs

- `0x180015e4a`: `SnapshotPreferTransactionsTimeoutDuringBackup`

## pseudocode

```c
CSnapshotLists *__fastcall CSnapshotLists::CSnapshotLists(CSnapshotLists *this)
{
  CSnapshotLists *Data; // [rsp+60h] [rbp+18h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+30h] BYREF

  Data = this;
  g_SnapshotLists = &CSnapshotLists::`vftable'{for `IBroadcastToSnapshotLists'};
  qword_1801587B8 = &CSnapshotLists::`vftable'{for `ISnapshotToSnapshotLists'};
  CRWLock::CRWLock((CRWLock *)qword_1801587C0);
  qword_1801588A0 = (__int64)&UTStaticList2<CXaOpenState *>::`vftable';
  dword_1801588A8 = 0;
  xmmword_1801588B0 = 0;
  qword_1801588C0 = (__int64)&UTStaticList2<CXaOpenState *>::`vftable';
  dword_1801588C8 = 0;
  xmmword_1801588D0 = 0;
  xmmword_180158864 = 0;
  xmmword_180158874 = 0;
  qword_180158884 = 0;
  dword_180158890 = 1;
  qword_180158898 = 0;
  hKey = 0;
  Type = 0;
  LODWORD(Data) = 0;
  cbData = 4;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\MSDTC", 0, 0x20119u, &hKey)
    || RegQueryValueExA(hKey, "SnapshotPreferTransactionsTimeoutDuringBackup", 0, &Type, (LPBYTE)&Data, &cbData)
    || Type != 4 )
  {
    LODWORD(Data) = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  dword_1801588E0 = (int)Data;
  return (CSnapshotLists *)&g_SnapshotLists;
}

```

## disassembly

```asm
0x180015d50  mov     [rsp-10h+Data], rcx
0x180015d55  push    rbp
0x180015d56  push    rdi
0x180015d57  mov     rbp, rsp
0x180015d5a  sub     rsp, 48h
0x180015d5e  lea     rdi, ?g_SnapshotLists@@3VCSnapshotLists@@A; CSnapshotLists g_SnapshotLists
0x180015d65  mov     [rbp+var_18], rdi
0x180015d69  lea     rax, ??_7CSnapshotLists@@6BIBroadcastToSnapshotLists@@@; const CSnapshotLists::`vftable'{for `IBroadcastToSnapshotLists'}
0x180015d70  mov     cs:?g_SnapshotLists@@3VCSnapshotLists@@A, rax; CSnapshotLists g_SnapshotLists
0x180015d77  lea     rax, ??_7CSnapshotLists@@6BISnapshotToSnapshotLists@@@; const CSnapshotLists::`vftable'{for `ISnapshotToSnapshotLists'}
0x180015d7e  mov     cs:qword_1801587B8, rax
0x180015d85  lea     rcx, qword_1801587C0; this
0x180015d8c  call    ??0CRWLock@@QEAA@XZ; CRWLock::CRWLock(void)
0x180015d91  nop
0x180015d92  lea     rax, ??_7?$UTStaticList2@PEAVCXaOpenState@@@@6B@; const UTStaticList2<CXaOpenState *>::`vftable'
0x180015d99  mov     cs:qword_1801588A0, rax
0x180015da0  mov     cs:dword_1801588A8, 0
0x180015daa  xorps   xmm0, xmm0
0x180015dad  movdqa  cs:xmmword_1801588B0, xmm0
0x180015db5  mov     cs:qword_1801588C0, rax
0x180015dbc  mov     cs:dword_1801588C8, 0
0x180015dc6  movdqa  cs:xmmword_1801588D0, xmm0
0x180015dce  xor     eax, eax
0x180015dd0  movups  cs:xmmword_180158864, xmm0
0x180015dd7  movups  cs:xmmword_180158874, xmm0
0x180015dde  mov     cs:qword_180158884, rax
0x180015de5  mov     cs:dword_180158890, 1
0x180015def  mov     cs:qword_180158898, rax
0x180015df6  mov     [rbp+hKey], rax
0x180015dfa  mov     [rbp+Type], eax
0x180015dfd  mov     dword ptr [rbp+Data], eax
0x180015e00  mov     [rbp+cbData], 4
0x180015e07  lea     rax, [rbp+hKey]
0x180015e0b  mov     [rsp+48h+phkResult], rax; phkResult
0x180015e10  mov     r9d, 20119h; samDesired
0x180015e16  xor     r8d, r8d; ulOptions
0x180015e19  lea     rdx, SubKey; "Software\\Microsoft\\MSDTC"
0x180015e20  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015e27  call    cs:__imp_RegOpenKeyExA
0x180015e2d  test    eax, eax
0x180015e2f  jnz     short loc_180015E65
0x180015e31  lea     rax, [rbp+cbData]
0x180015e35  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180015e3a  lea     rax, [rbp+Data]
0x180015e3e  mov     [rsp+48h+phkResult], rax; lpData
0x180015e43  lea     r9, [rbp+Type]; lpType
0x180015e47  xor     r8d, r8d; lpReserved
0x180015e4a  lea     rdx, aSnapshotprefer; "SnapshotPreferTransactionsTimeoutDuring"...
0x180015e51  mov     rcx, [rbp+hKey]; hKey
0x180015e55  call    cs:__imp_RegQueryValueExA
0x180015e5b  test    eax, eax
0x180015e5d  jnz     short loc_180015E65
0x180015e5f  cmp     [rbp+Type], 4
0x180015e63  jz      short loc_180015E6C
0x180015e65  mov     dword ptr [rbp+Data], 0
0x180015e6c  mov     rcx, [rbp+hKey]; hKey
0x180015e70  test    rcx, rcx
0x180015e73  jz      short loc_180015E7B
0x180015e75  call    cs:__imp_RegCloseKey
0x180015e7b  mov     ecx, dword ptr [rbp+Data]
0x180015e7e  mov     cs:dword_1801588E0, ecx
0x180015e84  mov     rax, rdi
0x180015e87  add     rsp, 48h
0x180015e8b  pop     rdi
0x180015e8c  pop     rbp
0x180015e8d  retn
```
