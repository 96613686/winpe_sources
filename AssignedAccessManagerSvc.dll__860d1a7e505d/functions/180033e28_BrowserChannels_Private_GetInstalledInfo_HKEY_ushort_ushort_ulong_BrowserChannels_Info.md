# BrowserChannels::Private::GetInstalledInfo(HKEY__ *,ushort *,ushort *,ulong,BrowserChannels::Info *)

- ea: `0x180033e28`
- end: `0x180033f84`
- name: `?GetInstalledInfo@Private@BrowserChannels@@YA_NPEAUHKEY__@@PEAG1KPEAUInfo@2@@Z`
- size: `348`
- prototype: `bool(BrowserChannels::Private *__hidden this, HKEY, unsigned __int16 *, unsigned __int16 *, unsigned int, struct BrowserChannels::Info *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180033d1c`

## callees

- `0x180006640`
- `0x180033e28`
- `0x1800344ac`
- `0x180034514`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180033eba`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180033f4f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180033eba`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180033f4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033f5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033f5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033e78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033e78`

## pseudocode

```c
char __fastcall BrowserChannels::Private::GetInstalledInfo(
        BrowserChannels::Private *this,
        const WCHAR *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        __int64 a5)
{
  char v6; // bl
  unsigned __int16 *v7; // r8
  unsigned __int16 *v8; // r8
  const unsigned __int16 *phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultc; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *phkResultd; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v16[56]; // [rsp+40h] [rbp-C0h] BYREF
  struct HKEY__ v17; // [rsp+B0h] [rbp-50h] BYREF

  hKey = 0;
  v6 = 0;
  if ( !RegOpenKeyExW((HKEY)this, a2, 0, 0x20219u, &hKey) )
  {
    if ( BrowserChannels::Private::ReadExePath(
           (BrowserChannels::Private *)hKey,
           (HKEY)a3,
           v7,
           (unsigned int)L"msedge.exe",
           phkResult) )
    {
      v6 = 1;
      if ( a5 )
      {
        v6 = 0;
        if ( !(unsigned int)_o_wcscpy_s(a5, 260, a3)
          && BrowserChannels::Private::ReadRegStringValue(
               (BrowserChannels::Private *)hKey,
               (HKEY)&stru_1800A43F8,
               (const unsigned __int16 *)(a5 + 520),
               (unsigned __int16 *)0x32,
               phkResulta)
          && BrowserChannels::Private::ReadRegStringValue(
               (BrowserChannels::Private *)hKey,
               (HKEY)&stru_1800A43F0,
               (const unsigned __int16 *)(a5 + 620),
               (unsigned __int16 *)0x32,
               phkResultb) )
        {
          v6 = 1;
          if ( BrowserChannels::Private::ReadRegStringValue(
                 (BrowserChannels::Private *)hKey,
                 (HKEY)&stru_1800A43E8,
                 v16,
                 (unsigned __int16 *)0x32,
                 phkResultc)
            && BrowserChannels::Private::ReadExePath(
                 (BrowserChannels::Private *)hKey,
                 &v17,
                 v8,
                 (unsigned int)L"new_msedge.exe",
                 phkResultd) )
          {
            _o_wcscpy_s(a5 + 620, 50, v16);
          }
        }
      }
    }
    RegCloseKey(hKey);
  }
  return v6;
}

```

## disassembly

```asm
0x180033e28  mov     [rsp-8+arg_18], rbx
0x180033e2d  push    rbp
0x180033e2e  push    rsi
0x180033e2f  push    rdi
0x180033e30  lea     rbp, [rsp-1D0h]
0x180033e38  sub     rsp, 2D0h
0x180033e3f  mov     rax, cs:__security_cookie
0x180033e46  xor     rax, rsp
0x180033e49  mov     [rbp+1E0h+var_20], rax
0x180033e50  mov     rdi, qword ptr [rbp+1E0h+arg_20]
0x180033e57  lea     rax, [rsp+2E0h+hKey]
0x180033e5c  mov     rsi, r8
0x180033e5f  mov     [rsp+2E0h+phkResult], rax; unsigned __int16 *
0x180033e64  xor     r8d, r8d; ulOptions
0x180033e67  mov     [rsp+2E0h+hKey], 0
0x180033e70  mov     r9d, 20219h; samDesired
0x180033e76  xor     bl, bl
0x180033e78  call    cs:__imp_RegOpenKeyExW
0x180033e7e  test    eax, eax
0x180033e80  jnz     loc_180033F60
0x180033e86  mov     rcx, [rsp+2E0h+hKey]; this
0x180033e8b  lea     r9, aMsedgeExe_0; "msedge.exe"
0x180033e92  mov     rdx, rsi; HKEY
0x180033e95  call    ?ReadExePath@Private@BrowserChannels@@YA_NPEAUHKEY__@@PEAGKPEBG@Z; BrowserChannels::Private::ReadExePath(HKEY__ *,ushort *,ulong,ushort const *)
0x180033e9a  test    al, al
0x180033e9c  jz      loc_180033F55
0x180033ea2  mov     bl, 1
0x180033ea4  test    rdi, rdi
0x180033ea7  jz      loc_180033F55
0x180033ead  mov     r8, rsi
0x180033eb0  mov     edx, 104h
0x180033eb5  mov     rcx, rdi
0x180033eb8  xor     bl, bl
0x180033eba  call    cs:__imp__o_wcscpy_s
0x180033ec0  test    eax, eax
0x180033ec2  jnz     loc_180033F55
0x180033ec8  mov     rcx, [rsp+2E0h+hKey]; this
0x180033ecd  lea     esi, [rax+32h]
0x180033ed0  mov     r9d, esi; unsigned __int16 *
0x180033ed3  lea     r8, [rdi+208h]; unsigned __int16 *
0x180033eda  lea     rdx, stru_1800A43F8; HKEY
0x180033ee1  call    ?ReadRegStringValue@Private@BrowserChannels@@YA_NPEAUHKEY__@@PEBGPEAGK@Z; BrowserChannels::Private::ReadRegStringValue(HKEY__ *,ushort const *,ushort *,ulong)
0x180033ee6  test    al, al
0x180033ee8  jz      short loc_180033F55
0x180033eea  mov     rcx, [rsp+2E0h+hKey]; this
0x180033eef  lea     r8, [rdi+26Ch]; unsigned __int16 *
0x180033ef6  mov     r9d, esi; unsigned __int16 *
0x180033ef9  lea     rdx, stru_1800A43F0; HKEY
0x180033f00  call    ?ReadRegStringValue@Private@BrowserChannels@@YA_NPEAUHKEY__@@PEBGPEAGK@Z; BrowserChannels::Private::ReadRegStringValue(HKEY__ *,ushort const *,ushort *,ulong)
0x180033f05  test    al, al
0x180033f07  jz      short loc_180033F55
0x180033f09  mov     rcx, [rsp+2E0h+hKey]; this
0x180033f0e  lea     r8, [rsp+2E0h+var_2A0]; unsigned __int16 *
0x180033f13  mov     r9d, esi; unsigned __int16 *
0x180033f16  lea     rdx, stru_1800A43E8; HKEY
0x180033f1d  mov     bl, 1
0x180033f1f  call    ?ReadRegStringValue@Private@BrowserChannels@@YA_NPEAUHKEY__@@PEBGPEAGK@Z; BrowserChannels::Private::ReadRegStringValue(HKEY__ *,ushort const *,ushort *,ulong)
0x180033f24  test    al, al
0x180033f26  jz      short loc_180033F55
0x180033f28  mov     rcx, [rsp+2E0h+hKey]; this
0x180033f2d  lea     r9, aNewMsedgeExe; "new_msedge.exe"
0x180033f34  lea     rdx, [rbp+1E0h+var_230]; HKEY
0x180033f38  call    ?ReadExePath@Private@BrowserChannels@@YA_NPEAUHKEY__@@PEAGKPEBG@Z; BrowserChannels::Private::ReadExePath(HKEY__ *,ushort *,ulong,ushort const *)
0x180033f3d  test    al, al
0x180033f3f  jz      short loc_180033F55
0x180033f41  lea     r8, [rsp+2E0h+var_2A0]
0x180033f46  mov     edx, esi
0x180033f48  lea     rcx, [rdi+26Ch]
0x180033f4f  call    cs:__imp__o_wcscpy_s
0x180033f55  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180033f5a  call    cs:__imp_RegCloseKey
0x180033f60  mov     al, bl
0x180033f62  mov     rcx, [rbp+1E0h+var_20]
0x180033f69  xor     rcx, rsp; StackCookie
0x180033f6c  call    __security_check_cookie
0x180033f71  mov     rbx, [rsp+2E0h+arg_18]
0x180033f79  add     rsp, 2D0h
0x180033f80  pop     rdi
0x180033f81  pop     rsi
0x180033f82  pop     rbp
0x180033f83  retn
```
