# CBaseHandlerKeys::Register(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x18002422c`
- end: `0x18002437f`
- name: `?Register@CBaseHandlerKeys@@KAJPEAUHKEY__@@PEBG11KK@Z`
- size: `339`
- prototype: `static int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ae00`

## callees

- `0x18000a7a4`
- `0x18002422c`
- `0x180024400`
- `0x180024420`
- `0x180052950`

## import_xrefs

- `SHLWAPI!SHSetValueW` at `0x18002431e`
- `SHLWAPI!SHSetValueW` at `0x18002431e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024347`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024347`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800242f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800242f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800242cc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800242cc`

## pseudocode

```c
__int64 __fastcall CBaseHandlerKeys::Register(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const BYTE *a4,
        unsigned int a5,
        unsigned int pvData)
{
  int ItemName; // ebx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  int v11; // eax
  HKEY hKey; // [rsp+50h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-228h] BYREF

  ItemName = CSettingsBase::MakeItemName(SubKey, (unsigned __int64)a2, L"Handlers", a3, 0, 0);
  if ( ItemName >= 0 )
  {
    hKey = 0;
    v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
    if ( v9 )
    {
      return (unsigned int)ResultFromKnownError(v9);
    }
    else
    {
      RegSetValueExW(hKey, 0, 0, 1u, a4, 0x100u);
      v10 = SHSetValueW(HKEY_LOCAL_MACHINE, SubKey, L"RegistrationFlags", 4u, &pvData, 4u);
      if ( v10 )
        v11 = ResultFromKnownError(v10);
      else
        v11 = CSyncMgrSettings::SetRegistrationFlags(a3, pvData);
      ItemName = v11;
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)ItemName;
}

```

## disassembly

```asm
0x18002422c  mov     [rsp+arg_0], rbx
0x180024231  mov     [rsp+arg_8], rsi
0x180024236  push    rdi
0x180024237  sub     rsp, 280h
0x18002423e  mov     rax, cs:__security_cookie
0x180024245  xor     rax, rsp
0x180024248  mov     [rsp+288h+var_18], rax
0x180024250  mov     rsi, r9
0x180024253  mov     byte ptr [rsp+288h+samDesired], 0; bool
0x180024258  mov     r9, r8; unsigned __int16 *
0x18002425b  mov     qword ptr [rsp+288h+dwOptions], 0; unsigned __int16 *
0x180024264  mov     rdi, r8
0x180024267  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x18002426c  lea     r8, ?s_szHandlers_regkey@CSettingsBase@@1QBGB; "Handlers"
0x180024273  call    ?MakeItemName@CSettingsBase@@KAJPEAG_KPEBG22_N@Z; CSettingsBase::MakeItemName(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *,bool)
0x180024278  mov     ebx, eax
0x18002427a  test    eax, eax
0x18002427c  js      loc_180024358
0x180024282  mov     [rsp+288h+lpdwDisposition], 0; lpdwDisposition
0x18002428b  lea     rax, [rsp+288h+hKey]
0x180024290  mov     [rsp+288h+phkResult], rax; phkResult
0x180024295  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x18002429a  mov     [rsp+288h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800242a3  mov     rbx, 0FFFFFFFF80000002h
0x1800242aa  mov     [rsp+288h+samDesired], 2001Fh; samDesired
0x1800242b2  xor     r9d, r9d; lpClass
0x1800242b5  xor     r8d, r8d; Reserved
0x1800242b8  mov     [rsp+288h+dwOptions], 0; dwOptions
0x1800242c0  mov     rcx, rbx; hKey
0x1800242c3  mov     [rsp+288h+hKey], 0
0x1800242cc  call    cs:__imp_RegCreateKeyExW
0x1800242d2  test    eax, eax
0x1800242d4  jnz     short loc_18002434F
0x1800242d6  mov     rcx, [rsp+288h+hKey]; hKey
0x1800242db  lea     r9d, [rax+1]; dwType
0x1800242df  mov     [rsp+288h+samDesired], 100h; cbData
0x1800242e7  xor     r8d, r8d; Reserved
0x1800242ea  xor     edx, edx; lpValueName
0x1800242ec  mov     qword ptr [rsp+288h+dwOptions], rsi; lpData
0x1800242f1  call    cs:__imp_RegSetValueExW
0x1800242f7  mov     r9d, 4; dwType
0x1800242fd  lea     rax, [rsp+288h+pvData]
0x180024305  mov     [rsp+288h+samDesired], r9d; cbData
0x18002430a  lea     r8, ?s_szRegistrationFlags_value@CSettingsBase@@1QBGB; "RegistrationFlags"
0x180024311  lea     rdx, [rsp+288h+SubKey]; pszSubKey
0x180024316  mov     qword ptr [rsp+288h+dwOptions], rax; pvData
0x18002431b  mov     rcx, rbx; hkey
0x18002431e  call    cs:__imp_SHSetValueW
0x180024324  test    eax, eax
0x180024326  jnz     short loc_180024339
0x180024328  mov     edx, [rsp+288h+pvData]; unsigned int
0x18002432f  mov     rcx, rdi; unsigned __int16 *
0x180024332  call    ?SetRegistrationFlags@CSyncMgrSettings@@SAJPEBGK@Z; CSyncMgrSettings::SetRegistrationFlags(ushort const *,ulong)
0x180024337  jmp     short loc_180024340
0x180024339  mov     ecx, eax; unsigned int
0x18002433b  call    ?ResultFromKnownError@@YAJK@Z; ResultFromKnownError(ulong)
0x180024340  mov     rcx, [rsp+288h+hKey]; hKey
0x180024345  mov     ebx, eax
0x180024347  call    cs:__imp_RegCloseKey
0x18002434d  jmp     short loc_180024358
0x18002434f  mov     ecx, eax; unsigned int
0x180024351  call    ?ResultFromKnownError@@YAJK@Z; ResultFromKnownError(ulong)
0x180024356  mov     ebx, eax
0x180024358  mov     eax, ebx
0x18002435a  mov     rcx, [rsp+288h+var_18]
0x180024362  xor     rcx, rsp; StackCookie
0x180024365  call    __security_check_cookie
0x18002436a  lea     r11, [rsp+288h+var_8]
0x180024372  mov     rbx, [r11+10h]
0x180024376  mov     rsi, [r11+18h]
0x18002437a  mov     rsp, r11
0x18002437d  pop     rdi
0x18002437e  retn
```
