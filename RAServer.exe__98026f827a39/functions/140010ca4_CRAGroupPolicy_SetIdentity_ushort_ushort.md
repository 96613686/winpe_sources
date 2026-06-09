# CRAGroupPolicy::SetIdentity(ushort *,ushort *)

- ea: `0x140010ca4`
- end: `0x140010dbc`
- name: `?SetIdentity@CRAGroupPolicy@@AEAAKPEAG0@Z`
- size: `280`
- prototype: `__int64 __fastcall(CRAGroupPolicy *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000fc0c`

## callees

- `0x140010ca4`
- `0x140011394`
- `0x140015240`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140010ce3`
- `ADVAPI32!RegOpenKeyExW` at `0x140010ce3`
- `ADVAPI32!RegSetValueExW` at `0x140010d72`
- `ADVAPI32!RegSetValueExW` at `0x140010d72`
- `ADVAPI32!RegCloseKey` at `0x140010dae`
- `ADVAPI32!RegCloseKey` at `0x140010dae`

## string_xrefs

- `0x140010d3b`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x140010d93`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`

## pseudocode

```c
__int64 __fastcall CRAGroupPolicy::SetIdentity(CRAGroupPolicy *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  const struct _EVENT_DESCRIPTOR *v3; // rdx
  unsigned int v4; // ebx
  unsigned int v5; // r9d
  signed int v6; // eax
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  const BYTE *lpData; // r11
  unsigned __int64 v10; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v10 = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Classes\\AppID\\{F8FD03A6-DDD9-4C1B-84EE-58159476A0D7}",
         0,
         2u,
         &hKey);
  if ( v4 )
  {
    v5 = 668;
LABEL_8:
    CEventLogger::LogError(
      (CEventLogger *)L"CRAGroupPolicy::SetIdentity",
      v3,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      v5,
      L"CRAGroupPolicy::SetIdentity",
      0);
    goto LABEL_9;
  }
  if ( !hKey )
    return v4;
  v6 = StringCbLengthW(L"Interactive User", 0x104u, &v10);
  LOWORD(v4) = v6;
  if ( v6 < 0 )
  {
    CEventLogger::LogError(
      (CEventLogger *)L"CRAGroupPolicy::SetIdentity",
      v7,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      0x2A9u,
      L"CRAGroupPolicy::SetIdentity",
      v6);
    v4 = (unsigned __int16)v4;
    goto LABEL_9;
  }
  v4 = RegSetValueExW(hKey, L"RunAs", 0, 1u, lpData, v10 + 1);
  if ( v4 )
  {
    v5 = 696;
    goto LABEL_8;
  }
LABEL_9:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x140010ca4  mov     r11, rsp
0x140010ca7  mov     [r11+18h], r8
0x140010cab  mov     [r11+10h], rdx
0x140010caf  push    rbx
0x140010cb0  sub     rsp, 30h
0x140010cb4  lea     rax, [r11+18h]
0x140010cb8  mov     qword ptr [r11+18h], 0
0x140010cc0  mov     r9d, 2; samDesired
0x140010cc6  mov     [r11-18h], rax
0x140010cca  xor     r8d, r8d; ulOptions
0x140010ccd  mov     qword ptr [r11+10h], 0
0x140010cd5  lea     rdx, aSoftwareClasse; "SOFTWARE\\Classes\\AppID\\{F8FD03A6-DDD"...
0x140010cdc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140010ce3  call    cs:__imp_RegOpenKeyExW
0x140010ce9  mov     ebx, eax
0x140010ceb  test    eax, eax
0x140010ced  jz      short loc_140010CFA
0x140010cef  mov     r9d, 29Ch
0x140010cf5  jmp     loc_140010D84
0x140010cfa  cmp     [rsp+38h+hKey], 0
0x140010d00  jz      loc_140010DB4
0x140010d06  lea     r11, aInteractiveUse; "Interactive User"
0x140010d0d  mov     edx, 104h; unsigned __int64
0x140010d12  mov     rcx, r11; unsigned __int16 *
0x140010d15  lea     r8, [rsp+38h+arg_8]; unsigned __int64 *
0x140010d1a  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140010d1f  mov     ebx, eax
0x140010d21  test    eax, eax
0x140010d23  jns     short loc_140010D4C
0x140010d25  lea     rcx, aCragrouppolicy_1; "CRAGroupPolicy::SetIdentity"
0x140010d2c  mov     [rsp+38h+cbData], eax; unsigned int
0x140010d30  mov     r9d, 2A9h; unsigned int
0x140010d36  mov     [rsp+38h+lpData], rcx; unsigned __int16 *
0x140010d3b  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x140010d42  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140010d47  movzx   ebx, bx
0x140010d4a  jmp     short loc_140010DA4
0x140010d4c  mov     rax, [rsp+38h+arg_8]
0x140010d51  lea     rdx, aRunas; "RunAs"
0x140010d58  mov     rcx, [rsp+38h+hKey]; hKey
0x140010d5d  inc     rax
0x140010d60  mov     [rsp+38h+cbData], eax; cbData
0x140010d64  mov     r9d, 1; dwType
0x140010d6a  xor     r8d, r8d; Reserved
0x140010d6d  mov     [rsp+38h+lpData], r11; lpData
0x140010d72  call    cs:__imp_RegSetValueExW
0x140010d78  mov     ebx, eax
0x140010d7a  test    eax, eax
0x140010d7c  jz      short loc_140010DA4
0x140010d7e  mov     r9d, 2B8h; unsigned int
0x140010d84  lea     rcx, aCragrouppolicy_1; "CRAGroupPolicy::SetIdentity"
0x140010d8b  mov     [rsp+38h+cbData], 0; unsigned int
0x140010d93  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x140010d9a  mov     [rsp+38h+lpData], rcx; unsigned __int16 *
0x140010d9f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140010da4  mov     rcx, [rsp+38h+hKey]; hKey
0x140010da9  test    rcx, rcx
0x140010dac  jz      short loc_140010DB4
0x140010dae  call    cs:__imp_RegCloseKey
0x140010db4  mov     eax, ebx
0x140010db6  add     rsp, 30h
0x140010dba  pop     rbx
0x140010dbb  retn
```
