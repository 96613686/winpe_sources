# ESEDataSource::_GetCorruptionKey(int *)

- ea: `0x180011930`
- end: `0x180011a1d`
- name: `?_GetCorruptionKey@ESEDataSource@@AEAAXPEAH@Z`
- size: `237`
- prototype: `void __fastcall(ESEDataSource *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011f70`

## callees

- `0x180003edc`
- `0x1800067c0`
- `0x18000c5b8`
- `0x18001087c`
- `0x180011930`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a11`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011998`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011998`

## pseudocode

```c
void __fastcall ESEDataSource::_GetCorruptionKey(ESEDataSource *this, int *a2)
{
  HKEY *phkResult; // rax
  const unsigned __int16 *v4; // rdx
  HKEY v5; // rcx
  int DWORD; // eax
  void *v7; // rax
  unsigned int v8; // [rsp+60h] [rbp+8h] BYREF
  int v9; // [rsp+64h] [rbp+Ch]
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  v9 = HIDWORD(this);
  v8 = 0;
  hKey = 0;
  *a2 = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  if ( RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Poom\\Indexing", 0, 0, 0, 0x20019u, 0, phkResult, 0) )
    goto LABEL_9;
  DWORD = RegistryGetDWORD(v5, v4, L"IndexesCorrupt", &v8);
  if ( DWORD == -2147024894 )
  {
    *a2 = 0;
    goto LABEL_9;
  }
  if ( DWORD >= 0 )
  {
    if ( !v8 )
      goto LABEL_9;
  }
  else if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
  {
    v7 = _t_address();
    EtwTraceMessage(&ETWMESSAGE, v7, 0);
  }
  *a2 = 1;
LABEL_9:
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180011930  mov     rax, rsp
0x180011933  mov     [rax+8], rcx
0x180011937  push    rbx
0x180011938  sub     rsp, 50h
0x18001193c  lea     rcx, [rax+10h]
0x180011940  mov     dword ptr [rax+8], 0
0x180011947  mov     rbx, rdx
0x18001194a  mov     qword ptr [rax+10h], 0
0x180011952  mov     dword ptr [rdx], 0
0x180011958  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001195d  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180011966  lea     rdx, SubKey; "Software\\Microsoft\\Poom\\Indexing"
0x18001196d  mov     [rsp+58h+phkResult], rax; phkResult
0x180011972  xor     r9d, r9d; lpClass
0x180011975  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001197e  xor     r8d, r8d; Reserved
0x180011981  mov     [rsp+58h+samDesired], 20019h; samDesired
0x180011989  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180011990  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180011998  call    cs:__imp_RegCreateKeyExW
0x18001199e  test    eax, eax
0x1800119a0  jnz     short loc_180011A07
0x1800119a2  lea     r9, [rsp+58h+arg_0]; unsigned int *
0x1800119a7  lea     r8, aIndexescorrupt; "IndexesCorrupt"
0x1800119ae  call    ?RegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; RegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800119b3  cmp     eax, 80070002h
0x1800119b8  jnz     short loc_1800119C2
0x1800119ba  mov     dword ptr [rbx], 0
0x1800119c0  jmp     short loc_180011A07
0x1800119c2  test    eax, eax
0x1800119c4  jns     short loc_1800119FA
0x1800119c6  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x1800119cd  jz      short loc_180011A01
0x1800119cf  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x1800119d4  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800119d8  lea     rcx, _ETWMESSAGE; EventDescriptor
0x1800119df  mov     qword ptr [rsp+58h+samDesired], r9
0x1800119e4  mov     rdx, rax; void *
0x1800119e7  xor     r8d, r8d
0x1800119ea  mov     qword ptr [rsp+58h+dwOptions], 0
0x1800119f3  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x1800119f8  jmp     short loc_180011A01
0x1800119fa  cmp     [rsp+58h+arg_0], 0
0x1800119ff  jz      short loc_180011A07
0x180011a01  mov     dword ptr [rbx], 1
0x180011a07  mov     rcx, [rsp+58h+hKey]; hKey
0x180011a0c  test    rcx, rcx
0x180011a0f  jz      short loc_180011A17
0x180011a11  call    cs:__imp_RegCloseKey
0x180011a17  add     rsp, 50h
0x180011a1b  pop     rbx
0x180011a1c  retn
```
