# ReregisterNonCustomNonApppatchSdbs(RtlArray<_SavedSdbInfo> &)

- ea: `0x1800390fc`
- end: `0x1800392ab`
- name: `?ReregisterNonCustomNonApppatchSdbs@@YAJAEAV?$RtlArray@U_SavedSdbInfo@@@@@Z`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800382f0`

## callees

- `0x180001cf0`
- `0x18000a51c`
- `0x18003862c`
- `0x1800390fc`
- `0x1800392b4`
- `0x1800543c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180039282`
- `ADVAPI32!RegCloseKey` at `0x180039282`
- `ADVAPI32!RegOpenKeyExW` at `0x18003919e`
- `ADVAPI32!RegOpenKeyExW` at `0x18003919e`

## string_xrefs

- `0x18003914d`: `\InstalledSDB`
- `0x18003924e`: `Failed to open installed sdb key: 0x%x`

## pseudocode

```c
__int64 __fastcall ReregisterNonCustomNonApppatchSdbs(
        unsigned __int64 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int PersistedLocation; // eax
  signed int v6; // ebx
  HRESULT v7; // eax
  LSTATUS v8; // eax
  unsigned __int64 v9; // rcx
  unsigned __int64 i; // rbx
  unsigned __int64 v11; // rax
  const unsigned __int16 *v12; // r8
  int v13; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-248h]
  HKEY hKey; // [rsp+30h] [rbp-238h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-228h] BYREF

  hKey = 0;
  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(pszDest, a2, a3, a4);
  v6 = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    AslLogCallPrintf(
      1,
      "ReregisterNonCustomNonApppatchSdbs",
      1003,
      "Failed to get persisted reg key location: 0x%x",
      PersistedLocation);
    goto LABEL_26;
  }
  v7 = StringCchCatW(pszDest, 0x104u, L"\\InstalledSDB");
  v6 = v7;
  if ( v7 < 0 )
  {
    AslLogCallPrintf(1, "ReregisterNonCustomNonApppatchSdbs", 1010, "Failed to concat string: 0x%x", v7);
    goto LABEL_26;
  }
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20119u, &hKey);
  v6 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
  }
  else if ( hKey )
  {
    v9 = a1[2];
    if ( v9 )
    {
      for ( i = 0; i < v9; ++i )
      {
        v11 = 0;
        if ( i < v9 )
        {
          if ( !is_mul_ok(a1[1], i) || (v11 = a1[5] + a1[1] * i, v11 < a1[5]) )
            v11 = 0;
        }
        if ( *(_QWORD *)v11 )
        {
          v12 = *(const unsigned __int16 **)(v11 + 32);
          if ( v12 )
          {
            if ( !*(_DWORD *)(v11 + 8) && !*(_DWORD *)(v11 + 24) )
            {
              v13 = ReregisterSdb(hKey, *(const unsigned __int16 **)v11, v12);
              if ( v13 < 0 )
                AslLogCallPrintf(1, "ReregisterNonCustomNonApppatchSdbs", 1057, "Failed to reregister sdb: 0x%x", v13);
            }
          }
        }
        v9 = a1[2];
      }
    }
    v6 = 0;
    goto LABEL_26;
  }
  if ( v6 >= 0 )
    v6 = -2147467259;
  LODWORD(phkResult) = v6;
  AslLogCallPrintf(1, "ReregisterNonCustomNonApppatchSdbs", 1022, "Failed to open installed sdb key: 0x%x", phkResult);
LABEL_26:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800390fc  mov     [rsp+arg_8], rbx
0x180039101  push    rdi
0x180039102  sub     rsp, 260h
0x180039109  mov     rax, cs:__security_cookie
0x180039110  xor     rax, rsp
0x180039113  mov     [rsp+268h+var_18], rax
0x18003911b  mov     rdi, rcx
0x18003911e  mov     [rsp+268h+hKey], 0
0x180039127  lea     rcx, [rsp+268h+pszDest]; unsigned __int16 *
0x18003912c  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x180039131  mov     ebx, eax
0x180039133  test    eax, eax
0x180039135  jns     short loc_18003914D
0x180039137  mov     dword ptr [rsp+268h+phkResult], eax
0x18003913b  lea     r9, aFailedToGetPer; "Failed to get persisted reg key locatio"...
0x180039142  mov     r8d, 3EBh
0x180039148  jmp     loc_180039267
0x18003914d  lea     r8, aInstalledsdb; "\\InstalledSDB"
0x180039154  mov     edx, 104h; cchDest
0x180039159  lea     rcx, [rsp+268h+pszDest]; pszDest
0x18003915e  call    StringCchCatW
0x180039163  mov     ebx, eax
0x180039165  test    eax, eax
0x180039167  jns     short loc_18003917F
0x180039169  mov     dword ptr [rsp+268h+phkResult], eax
0x18003916d  lea     r9, aFailedToConcat; "Failed to concat string: 0x%x"
0x180039174  mov     r8d, 3F2h
0x18003917a  jmp     loc_180039267
0x18003917f  lea     rax, [rsp+268h+hKey]
0x180039184  mov     r9d, 20119h; samDesired
0x18003918a  xor     r8d, r8d; ulOptions
0x18003918d  mov     [rsp+268h+phkResult], rax; phkResult
0x180039192  lea     rdx, [rsp+268h+pszDest]; lpSubKey
0x180039197  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003919e  call    cs:__imp_RegOpenKeyExW
0x1800391a4  mov     ebx, eax
0x1800391a6  test    eax, eax
0x1800391a8  jnz     loc_180039241
0x1800391ae  cmp     [rsp+268h+hKey], 0
0x1800391b4  jz      loc_18003924C
0x1800391ba  mov     rcx, [rdi+10h]
0x1800391be  test    rcx, rcx
0x1800391c1  jz      short loc_18003923D
0x1800391c3  xor     ebx, ebx
0x1800391c5  xor     eax, eax
0x1800391c7  cmp     rbx, rcx
0x1800391ca  jnb     short loc_1800391E4
0x1800391cc  mov     rax, rbx
0x1800391cf  mul     qword ptr [rdi+8]
0x1800391d3  test    rdx, rdx
0x1800391d6  jnz     short loc_1800391E2
0x1800391d8  add     rax, [rdi+28h]
0x1800391dc  cmp     rax, [rdi+28h]
0x1800391e0  jnb     short loc_1800391E4
0x1800391e2  xor     eax, eax
0x1800391e4  mov     rdx, [rax]; unsigned __int16 *
0x1800391e7  test    rdx, rdx
0x1800391ea  jz      short loc_180039231
0x1800391ec  mov     r8, [rax+20h]; unsigned __int16 *
0x1800391f0  test    r8, r8
0x1800391f3  jz      short loc_180039231
0x1800391f5  cmp     dword ptr [rax+8], 0
0x1800391f9  jnz     short loc_180039231
0x1800391fb  cmp     dword ptr [rax+18h], 0
0x1800391ff  jnz     short loc_180039231
0x180039201  mov     rcx, [rsp+268h+hKey]; HKEY
0x180039206  call    ?ReregisterSdb@@YAJPEAUHKEY__@@PEBG1@Z; ReregisterSdb(HKEY__ *,ushort const *,ushort const *)
0x18003920b  test    eax, eax
0x18003920d  jns     short loc_180039231
0x18003920f  lea     r9, aFailedToReregi_0; "Failed to reregister sdb: 0x%x"
0x180039216  mov     dword ptr [rsp+268h+phkResult], eax
0x18003921a  mov     r8d, 421h
0x180039220  lea     rdx, aReregisternonc; "ReregisterNonCustomNonApppatchSdbs"
0x180039227  mov     ecx, 1
0x18003922c  call    AslLogCallPrintf
0x180039231  mov     rcx, [rdi+10h]
0x180039235  inc     rbx
0x180039238  cmp     rbx, rcx
0x18003923b  jb      short loc_1800391C5
0x18003923d  xor     ebx, ebx
0x18003923f  jmp     short loc_180039278
0x180039241  jle     short loc_18003924C
0x180039243  movzx   ebx, ax
0x180039246  or      ebx, 80070000h
0x18003924c  test    ebx, ebx
0x18003924e  lea     r9, aFailedToOpenIn_0; "Failed to open installed sdb key: 0x%x"
0x180039255  mov     eax, 80004005h
0x18003925a  mov     r8d, 3FEh
0x180039260  cmovns  ebx, eax
0x180039263  mov     dword ptr [rsp+268h+phkResult], ebx
0x180039267  lea     rdx, aReregisternonc; "ReregisterNonCustomNonApppatchSdbs"
0x18003926e  mov     ecx, 1
0x180039273  call    AslLogCallPrintf
0x180039278  mov     rcx, [rsp+268h+hKey]; hKey
0x18003927d  test    rcx, rcx
0x180039280  jz      short loc_180039288
0x180039282  call    cs:__imp_RegCloseKey
0x180039288  mov     eax, ebx
0x18003928a  mov     rcx, [rsp+268h+var_18]
0x180039292  xor     rcx, rsp; StackCookie
0x180039295  call    __security_check_cookie
0x18003929a  mov     rbx, [rsp+268h+arg_8]
0x1800392a2  add     rsp, 260h
0x1800392a9  pop     rdi
0x1800392aa  retn
```
