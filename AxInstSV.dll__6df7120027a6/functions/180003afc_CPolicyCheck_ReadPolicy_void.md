# CPolicyCheck::ReadPolicy(void)

- ea: `0x180003afc`
- end: `0x180003d88`
- name: `?ReadPolicy@CPolicyCheck@@QEAAJXZ`
- size: `652`
- prototype: `__int64 __fastcall(CPolicyCheck *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000c224`

## callees

- `0x18000300c`
- `0x18000383c`
- `0x180003afc`
- `0x180003d90`
- `0x180004318`
- `0x180004fe8`
- `0x18000725c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180003cf6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180003cf6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180003be5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180003be5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003d48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003d57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003d48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003d57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003b63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003b9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003b63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003b9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d65`
- `ntdll!RtlAcquireResourceExclusive` at `0x180003c8b`
- `ntdll!RtlAcquireResourceExclusive` at `0x180003c8b`
- `ntdll!RtlReleaseResource` at `0x180003d33`
- `ntdll!RtlReleaseResource` at `0x180003d33`

## string_xrefs

- `0x180003b90`: `ApprovedActiveXInstallSites`

## pseudocode

```c
__int64 __fastcall CPolicyCheck::ReadPolicy(CPolicyCheck *this)
{
  unsigned __int16 *v2; // r14
  int v3; // esi
  LSTATUS v4; // eax
  int v5; // edx
  int v6; // r12d
  DWORD v7; // ecx
  DWORD v8; // r15d
  PHKEY phkResult; // [rsp+20h] [rbp-49h]
  HKEY v11; // [rsp+60h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-1h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+70h] [rbp+7h] BYREF
  LPWSTR lpName; // [rsp+78h] [rbp+Fh] BYREF
  struct _FILETIME v15; // [rsp+80h] [rbp+17h] BYREF
  char *v16; // [rsp+88h] [rbp+1Fh]
  DWORD cbMaxSubKeyLen; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD cSubKeys; // [rsp+E0h] [rbp+77h] BYREF
  DWORD cchName; // [rsp+E8h] [rbp+7Fh] BYREF

  hKey = 0;
  v11 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  ftLastWriteTime = 0;
  v15 = 0;
  v2 = 0;
  lpName = 0;
  cchName = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
         0,
         0x20019u,
         &hKey)
    || (CPolicyCheck::ReadTrustedZonePolicy(this, hKey),
        RegOpenKeyExW(hKey, L"ApprovedActiveXInstallSites", 0, 0x20019u, &v11)) )
  {
    v3 = 0;
  }
  else
  {
    v4 = RegQueryInfoKeyW(v11, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, &ftLastWriteTime);
    if ( !v4 || v4 == 234 )
    {
      if ( ftLastWriteTime == *((_QWORD *)this + 16) )
      {
        v3 = 0;
        *((_DWORD *)this + 3) = 1;
        AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 3u, L"Returning as Policy hasn't changed");
      }
      else
      {
        v3 = Utils::AllocateCchStringBuffer(cbMaxSubKeyLen, &lpName, &cbMaxSubKeyLen);
        if ( v3 < 0 )
        {
          v2 = lpName;
        }
        else
        {
          v16 = (char *)this + 16;
          RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 16), 1u);
          if ( *((_QWORD *)this + 15) )
          {
            v6 = 1;
            CPolicyCheck::UpdateMarkToBeDeletedFlag(this, v5);
          }
          else
          {
            v6 = 0;
          }
          v7 = cSubKeys;
          *((_DWORD *)this + 34) = cSubKeys;
          *((struct _FILETIME *)this + 16) = ftLastWriteTime;
          v8 = 0;
          v2 = lpName;
          if ( v7 )
          {
            do
            {
              cchName = cbMaxSubKeyLen;
              if ( !RegEnumKeyExW(v11, v8, v2, &cchName, 0, 0, 0, &v15) )
                CPolicyCheck::AddPolicyEntryFromRegistry(this, v11, v2);
              ++v8;
            }
            while ( v8 < cSubKeys );
          }
          if ( v6 )
            CPolicyCheck::DeletedMarkedEntries(this, v11, 0, 0);
          RtlReleaseResource((PRTL_RESOURCE)((char *)this + 16));
        }
      }
    }
    else
    {
      v3 = 0;
      *((_DWORD *)this + 34) = 0;
      *((_DWORD *)this + 3) = 1;
      LODWORD(phkResult) = v4;
      AxISEvents::DebugMsg(
        (AxISEvents *)&qword_180021AD8,
        8u,
        3u,
        L"Returning as Policy doesn't exist. Code %d",
        phkResult);
    }
  }
  if ( v11 )
    RegCloseKey(v11);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v2 )
    LocalFree(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003afc  mov     [rsp-8+arg_0], rbx
0x180003b01  push    rbp
0x180003b02  push    rsi
0x180003b03  push    rdi
0x180003b04  push    r12
0x180003b06  push    r13
0x180003b08  push    r14
0x180003b0a  push    r15
0x180003b0c  lea     rbp, [rsp-27h]
0x180003b11  sub     rsp, 90h
0x180003b18  mov     rdi, rcx
0x180003b1b  xor     r13d, r13d
0x180003b1e  mov     [rbp+57h+hKey], r13
0x180003b22  mov     [rbp+57h+var_60], r13
0x180003b26  mov     [rbp+57h+cSubKeys], r13d
0x180003b2a  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x180003b2e  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], r13
0x180003b32  mov     qword ptr [rbp+57h+var_40.dwLowDateTime], r13
0x180003b36  mov     r14d, r13d
0x180003b39  mov     [rbp+57h+lpName], r13
0x180003b3d  mov     [rbp+57h+cchName], r13d
0x180003b41  lea     rax, [rbp+57h+hKey]
0x180003b45  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180003b4a  mov     ebx, 20019h
0x180003b4f  mov     r9d, ebx; samDesired
0x180003b52  xor     r8d, r8d; ulOptions
0x180003b55  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003b5c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003b63  call    cs:__imp_RegOpenKeyExW
0x180003b69  test    eax, eax
0x180003b6b  jz      short loc_180003B75
0x180003b6d  mov     esi, r13d
0x180003b70  jmp     loc_180003D3F
0x180003b75  mov     rdx, [rbp+57h+hKey]; HKEY
0x180003b79  mov     rcx, rdi; this
0x180003b7c  call    ?ReadTrustedZonePolicy@CPolicyCheck@@QEAAXPEAUHKEY__@@@Z; CPolicyCheck::ReadTrustedZonePolicy(HKEY__ *)
0x180003b81  lea     rax, [rbp+57h+var_60]
0x180003b85  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180003b8a  mov     r9d, ebx; samDesired
0x180003b8d  xor     r8d, r8d; ulOptions
0x180003b90  lea     rdx, aApprovedactive; "ApprovedActiveXInstallSites"
0x180003b97  mov     rcx, [rbp+57h+hKey]; hKey
0x180003b9b  call    cs:__imp_RegOpenKeyExW
0x180003ba1  test    eax, eax
0x180003ba3  jnz     short loc_180003B6D
0x180003ba5  lea     rax, [rbp+57h+ftLastWriteTime]
0x180003ba9  mov     [rsp+0C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180003bae  mov     [rsp+0C0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180003bb3  mov     [rsp+0C0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180003bb8  mov     [rsp+0C0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180003bbd  mov     [rsp+0C0h+lpcValues], r13; lpcValues
0x180003bc2  mov     [rsp+0C0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180003bc7  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180003bcb  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180003bd0  lea     rax, [rbp+57h+cSubKeys]
0x180003bd4  mov     [rsp+0C0h+phkResult], rax; lpcSubKeys
0x180003bd9  xor     r9d, r9d; lpReserved
0x180003bdc  xor     r8d, r8d; lpcchClass
0x180003bdf  xor     edx, edx; lpClass
0x180003be1  mov     rcx, [rbp+57h+var_60]; hKey
0x180003be5  call    cs:__imp_RegQueryInfoKeyW
0x180003beb  test    eax, eax
0x180003bed  jz      short loc_180003C2C
0x180003bef  cmp     eax, 0EAh
0x180003bf4  jz      short loc_180003C2C
0x180003bf6  mov     esi, r13d
0x180003bf9  mov     [rdi+88h], r13d
0x180003c00  mov     dword ptr [rdi+0Ch], 1
0x180003c07  mov     dword ptr [rsp+0C0h+phkResult], eax
0x180003c0b  lea     r9, aReturningAsPol; "Returning as Policy doesn't exist. Code"...
0x180003c12  mov     edx, 8; unsigned int
0x180003c17  lea     r8d, [rdx-5]; unsigned __int8
0x180003c1b  lea     rcx, qword_180021AD8; this
0x180003c22  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180003c27  jmp     loc_180003D3F
0x180003c2c  mov     rax, qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime]
0x180003c30  cmp     rax, [rdi+80h]
0x180003c37  jnz     short loc_180003C64
0x180003c39  mov     esi, r13d
0x180003c3c  mov     dword ptr [rdi+0Ch], 1
0x180003c43  lea     r9, aReturningAsPol_0; "Returning as Policy hasn't changed"
0x180003c4a  mov     edx, 8; unsigned int
0x180003c4f  lea     r8d, [rdx-5]; unsigned __int8
0x180003c53  lea     rcx, qword_180021AD8; this
0x180003c5a  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180003c5f  jmp     loc_180003D3F
0x180003c64  lea     r8, [rbp+57h+cbMaxSubKeyLen]; unsigned int *
0x180003c68  lea     rdx, [rbp+57h+lpName]; unsigned __int16 **
0x180003c6c  mov     ecx, [rbp+57h+cbMaxSubKeyLen]; unsigned int
0x180003c6f  call    ?AllocateCchStringBuffer@Utils@@SAJKPEAPEAGPEAK@Z; Utils::AllocateCchStringBuffer(ulong,ushort * *,ulong *)
0x180003c74  mov     esi, eax
0x180003c76  test    eax, eax
0x180003c78  js      loc_180003D3B
0x180003c7e  lea     rbx, [rdi+10h]
0x180003c82  mov     [rbp+57h+var_38], rbx
0x180003c86  mov     dl, 1; Wait
0x180003c88  mov     rcx, rbx; Resource
0x180003c8b  call    cs:__imp_RtlAcquireResourceExclusive
0x180003c91  nop
0x180003c92  cmp     [rdi+78h], r13
0x180003c96  jbe     short loc_180003CA8
0x180003c98  mov     r12d, 1
0x180003c9e  mov     rcx, rdi; this
0x180003ca1  call    ?UpdateMarkToBeDeletedFlag@CPolicyCheck@@QEAAJH@Z; CPolicyCheck::UpdateMarkToBeDeletedFlag(int)
0x180003ca6  jmp     short loc_180003CAB
0x180003ca8  mov     r12d, r13d
0x180003cab  mov     ecx, [rbp+57h+cSubKeys]
0x180003cae  mov     [rdi+88h], ecx
0x180003cb4  mov     rax, qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime]
0x180003cb8  mov     [rdi+80h], rax
0x180003cbf  mov     r15d, r13d
0x180003cc2  mov     r14, [rbp+57h+lpName]
0x180003cc6  test    ecx, ecx
0x180003cc8  jz      short loc_180003D18
0x180003cca  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180003ccd  mov     [rbp+57h+cchName], eax
0x180003cd0  lea     rax, [rbp+57h+var_40]
0x180003cd4  mov     [rsp+0C0h+lpcValues], rax; lpftLastWriteTime
0x180003cd9  mov     [rsp+0C0h+lpcbMaxClassLen], r13; lpcchClass
0x180003cde  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r13; lpClass
0x180003ce3  mov     [rsp+0C0h+phkResult], r13; lpReserved
0x180003ce8  lea     r9, [rbp+57h+cchName]; lpcchName
0x180003cec  mov     r8, r14; lpName
0x180003cef  mov     edx, r15d; dwIndex
0x180003cf2  mov     rcx, [rbp+57h+var_60]; hKey
0x180003cf6  call    cs:__imp_RegEnumKeyExW
0x180003cfc  test    eax, eax
0x180003cfe  jnz     short loc_180003D0F
0x180003d00  mov     r8, r14; unsigned __int16 *
0x180003d03  mov     rdx, [rbp+57h+var_60]; hKey
0x180003d07  mov     rcx, rdi; this
0x180003d0a  call    ?AddPolicyEntryFromRegistry@CPolicyCheck@@QEAAJPEAUHKEY__@@PEBG@Z; CPolicyCheck::AddPolicyEntryFromRegistry(HKEY__ *,ushort const *)
0x180003d0f  inc     r15d
0x180003d12  cmp     r15d, [rbp+57h+cSubKeys]
0x180003d16  jb      short loc_180003CCA
0x180003d18  test    r12d, r12d
0x180003d1b  jz      short loc_180003D30
0x180003d1d  xor     r9d, r9d; int
0x180003d20  xor     r8d, r8d; int
0x180003d23  mov     rdx, [rbp+57h+var_60]; HKEY
0x180003d27  mov     rcx, rdi; this
0x180003d2a  call    ?DeletedMarkedEntries@CPolicyCheck@@QEAAJPEAUHKEY__@@HH@Z; CPolicyCheck::DeletedMarkedEntries(HKEY__ *,int,int)
0x180003d2f  nop
0x180003d30  mov     rcx, rbx; Resource
0x180003d33  call    cs:__imp_RtlReleaseResource
0x180003d39  jmp     short loc_180003D3F
0x180003d3b  mov     r14, [rbp+57h+lpName]
0x180003d3f  mov     rcx, [rbp+57h+var_60]; hKey
0x180003d43  test    rcx, rcx
0x180003d46  jz      short loc_180003D4E
0x180003d48  call    cs:__imp_RegCloseKey
0x180003d4e  mov     rcx, [rbp+57h+hKey]; hKey
0x180003d52  test    rcx, rcx
0x180003d55  jz      short loc_180003D5D
0x180003d57  call    cs:__imp_RegCloseKey
0x180003d5d  test    r14, r14
0x180003d60  jz      short loc_180003D6B
0x180003d62  mov     rcx, r14; hMem
0x180003d65  call    cs:__imp_LocalFree
0x180003d6b  mov     eax, esi
0x180003d6d  mov     rbx, [rsp+0C0h+arg_0]
0x180003d75  add     rsp, 90h
0x180003d7c  pop     r15
0x180003d7e  pop     r14
0x180003d80  pop     r13
0x180003d82  pop     r12
0x180003d84  pop     rdi
0x180003d85  pop     rsi
0x180003d86  pop     rbp
0x180003d87  retn
```
