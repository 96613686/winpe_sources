# CNonClusterTmInstance::SetRegistryValue(ushort const *,ushort const *,ulong,uchar *,ulong)

- ea: `0x180053200`
- end: `0x18005334a`
- name: `?SetRegistryValue@CNonClusterTmInstance@@UEAAJPEBG0KPEAEK@Z`
- size: `330`
- prototype: `int(CNonClusterTmInstance *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180053200`
- `0x1800709bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800532bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800532d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053300`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800532bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800532d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053300`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005332f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005332f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053264`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053273`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053282`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053264`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053273`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053282`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::SetRegistryValue(
        CNonClusterTmInstance *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        unsigned __int8 *lpData,
        DWORD cbData)
{
  const unsigned __int16 *v6; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  bool v12; // cc
  HKEY v14; // rcx
  HKEY v15; // [rsp+30h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+20h] BYREF

  v6 = (const unsigned __int16 *)*((_QWORD *)this + 5);
  v15 = 0;
  hKey = 0;
  phkResult = 0;
  v10 = RegConnectHostnameW(v6, HKEY_LOCAL_MACHINE, &v15);
  v11 = v10;
  v12 = v10 <= 0;
  if ( v10 )
  {
LABEL_2:
    if ( v12 )
      goto LABEL_4;
    goto LABEL_3;
  }
  if ( a2 )
  {
    v10 = RegOpenKeyExW(v15, L"Software\\Microsoft\\MSDTC", 0, 0x20100u, &hKey);
    v11 = v10;
    v12 = v10 <= 0;
    if ( v10 )
      goto LABEL_2;
    v10 = RegOpenKeyExW(hKey, a2, 0, 0x102u, &phkResult);
    v11 = v10;
    v12 = v10 <= 0;
    if ( v10 )
      goto LABEL_2;
    v14 = phkResult;
  }
  else
  {
    v10 = RegOpenKeyExW(v15, L"Software\\Microsoft\\MSDTC", 0, 0x102u, &hKey);
    v11 = v10;
    v12 = v10 <= 0;
    if ( v10 )
      goto LABEL_2;
    v14 = hKey;
  }
  v11 = 0;
  v10 = RegSetValueExW(v14, a3, 0, a4, lpData, cbData);
  if ( v10 )
  {
    if ( v10 > 0 )
    {
LABEL_3:
      v11 = (unsigned __int16)v10 | 0x80070000;
      goto LABEL_4;
    }
    v11 = v10;
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v15 )
    RegCloseKey(v15);
  return v11;
}

```

## disassembly

```asm
0x180053200  mov     [rsp-18h+arg_8], rbx
0x180053205  mov     [rsp-18h+arg_10], rsi
0x18005320a  push    rbp
0x18005320b  push    rdi
0x18005320c  push    r14
0x18005320e  mov     rbp, rsp
0x180053211  sub     rsp, 40h
0x180053215  mov     rcx, [rcx+28h]; unsigned __int16 *
0x180053219  mov     r14, r8
0x18005321c  mov     rdi, rdx
0x18005321f  mov     [rbp+var_10], 0
0x180053227  lea     r8, [rbp+var_10]; HKEY *
0x18005322b  mov     [rbp+hKey], 0
0x180053233  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18005323a  mov     [rbp+var_8], 0
0x180053242  mov     esi, r9d
0x180053245  call    ?RegConnectHostnameW@@YAJPEBGPEAUHKEY__@@PEAPEAU1@@Z; RegConnectHostnameW(ushort const *,HKEY__ *,HKEY__ * *)
0x18005324a  mov     ebx, eax
0x18005324c  test    eax, eax
0x18005324e  jz      short loc_18005329D
0x180053250  jle     short loc_18005325B
0x180053252  movzx   ebx, ax
0x180053255  or      ebx, 80070000h
0x18005325b  mov     rcx, [rbp+hKey]; hKey
0x18005325f  test    rcx, rcx
0x180053262  jz      short loc_18005326A
0x180053264  call    cs:__imp_RegCloseKey
0x18005326a  mov     rcx, [rbp+var_8]; hKey
0x18005326e  test    rcx, rcx
0x180053271  jz      short loc_180053279
0x180053273  call    cs:__imp_RegCloseKey
0x180053279  mov     rcx, [rbp+var_10]; hKey
0x18005327d  test    rcx, rcx
0x180053280  jz      short loc_180053288
0x180053282  call    cs:__imp_RegCloseKey
0x180053288  mov     rsi, [rsp+40h+arg_10]
0x18005328d  mov     eax, ebx
0x18005328f  mov     rbx, [rsp+40h+arg_8]
0x180053294  add     rsp, 40h
0x180053298  pop     r14
0x18005329a  pop     rdi
0x18005329b  pop     rbp
0x18005329c  retn
0x18005329d  mov     rcx, [rbp+var_10]; hKey
0x1800532a1  lea     rax, [rbp+hKey]
0x1800532a5  xor     r8d, r8d; ulOptions
0x1800532a8  mov     [rsp+40h+phkResult], rax; phkResult
0x1800532ad  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\MSDTC"
0x1800532b4  test    rdi, rdi
0x1800532b7  jnz     short loc_1800532D1
0x1800532b9  mov     r9d, 102h; samDesired
0x1800532bf  call    cs:__imp_RegOpenKeyExW
0x1800532c5  mov     ebx, eax
0x1800532c7  test    eax, eax
0x1800532c9  jnz     short loc_180053250
0x1800532cb  mov     rcx, [rbp+hKey]
0x1800532cf  jmp     short loc_180053314
0x1800532d1  mov     r9d, 20100h; samDesired
0x1800532d7  call    cs:__imp_RegOpenKeyExW
0x1800532dd  mov     ebx, eax
0x1800532df  test    eax, eax
0x1800532e1  jnz     loc_180053250
0x1800532e7  mov     rcx, [rbp+hKey]; hKey
0x1800532eb  lea     rax, [rbp+var_8]
0x1800532ef  mov     r9d, 102h; samDesired
0x1800532f5  mov     [rsp+40h+phkResult], rax; phkResult
0x1800532fa  xor     r8d, r8d; ulOptions
0x1800532fd  mov     rdx, rdi; lpSubKey
0x180053300  call    cs:__imp_RegOpenKeyExW
0x180053306  mov     ebx, eax
0x180053308  test    eax, eax
0x18005330a  jnz     loc_180053250
0x180053310  mov     rcx, [rbp+var_8]; hKey
0x180053314  mov     eax, [rbp+arg_28]
0x180053317  mov     r9d, esi; dwType
0x18005331a  mov     [rsp+40h+cbData], eax; cbData
0x18005331e  xor     r8d, r8d; Reserved
0x180053321  mov     rax, [rbp+lpData]
0x180053325  mov     rdx, r14; lpValueName
0x180053328  mov     [rsp+40h+phkResult], rax; lpData
0x18005332d  xor     ebx, ebx
0x18005332f  call    cs:__imp_RegSetValueExW
0x180053335  test    eax, eax
0x180053337  jz      loc_18005325B
0x18005333d  jg      loc_180053252
0x180053343  mov     ebx, eax
0x180053345  jmp     loc_18005325B
```
