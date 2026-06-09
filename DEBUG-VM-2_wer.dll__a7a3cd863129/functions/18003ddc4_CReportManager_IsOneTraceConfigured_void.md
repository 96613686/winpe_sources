# CReportManager::IsOneTraceConfigured(void)

- ea: `0x18003ddc4`
- end: `0x18003df86`
- name: `?IsOneTraceConfigured@CReportManager@@SAHXZ`
- size: `450`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008fec`

## callees

- `0x18003ddc4`
- `0x180050db0`
- `0x180075314`
- `0x1800753d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003de61`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003de61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003df5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003df5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003de25`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003de25`

## pseudocode

```c
__int64 CReportManager::IsOneTraceConfigured(void)
{
  DWORD v0; // r14d
  unsigned int v1; // r15d
  unsigned __int64 v2; // rbx
  WCHAR *v3; // rsi
  __int64 v4; // rax
  __int64 v5; // rdi
  char *v6; // rsi
  WCHAR *v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rbx
  DWORD cchName[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[1032]; // [rsp+50h] [rbp-B0h] BYREF

  cchName[0] = 0;
  hKey = 0;
  v0 = 0;
  v1 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\Windows Error Reporting\\DynamicEtwSessions",
          0,
          0x20119u,
          &hKey) )
  {
    while ( 1 )
    {
      cchName[0] = 1025;
      if ( RegEnumKeyExW(hKey, v0, Name, cchName, 0, 0, 0, 0) )
        break;
      v2 = -1;
      do
        ++v2;
      while ( Name[v2] );
      if ( v2 >= 8 )
      {
        v3 = Name;
        while ( 1 )
        {
          v4 = tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::find(
                 v3,
                 ((char *)cchName + 2 * v2 + 2 - (char *)v3) >> 1,
                 L"OneTrace");
          v5 = v4;
          if ( !v4 )
            break;
          v3 = (WCHAR *)(v4 + 2);
          if ( !(unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(
                                v4 + 2,
                                L"neTrace",
                                7) )
          {
            if ( (v5 - (__int64)Name) >> 1 != -1 )
            {
LABEL_16:
              v1 = 1;
              goto LABEL_17;
            }
            break;
          }
        }
        if ( v2 >= 9 )
        {
          v6 = (char *)cchName + 2 * v2;
          v7 = Name;
          while ( 1 )
          {
            v8 = tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::find(
                   v7,
                   (v6 - (char *)v7) >> 1,
                   L"One Trace");
            v9 = v8;
            if ( !v8 )
              break;
            v7 = (WCHAR *)(v8 + 2);
            if ( !(unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(
                                  v8 + 2,
                                  L"ne Trace",
                                  8) )
            {
              if ( (v9 - (__int64)Name) >> 1 != -1 )
                goto LABEL_16;
              break;
            }
          }
        }
      }
      ++v0;
    }
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x18003ddc4  push    rbp
0x18003ddc6  push    rbx
0x18003ddc7  push    rsi
0x18003ddc8  push    rdi
0x18003ddc9  push    r12
0x18003ddcb  push    r13
0x18003ddcd  push    r14
0x18003ddcf  push    r15
0x18003ddd1  lea     rbp, [rsp-778h]
0x18003ddd9  sub     rsp, 878h
0x18003dde0  mov     rax, cs:__security_cookie
0x18003dde7  xor     rax, rsp
0x18003ddea  mov     [rbp+7B0h+var_50], rax
0x18003ddf1  xor     r13d, r13d
0x18003ddf4  lea     rax, [rsp+8B0h+hKey]
0x18003ddf9  mov     r9d, 20119h; samDesired
0x18003ddff  mov     [rsp+8B0h+cchName], r13d
0x18003de04  xor     r8d, r8d; ulOptions
0x18003de07  mov     [rsp+8B0h+hKey], r13
0x18003de0c  lea     rdx, aSoftwareMicros_29; "Software\\Microsoft\\Windows\\Windows E"...
0x18003de13  mov     [rsp+8B0h+phkResult], rax; phkResult
0x18003de18  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003de1f  mov     r14d, r13d
0x18003de22  mov     r15d, r13d
0x18003de25  call    cs:__imp_RegOpenKeyExW
0x18003de2b  test    eax, eax
0x18003de2d  jnz     loc_18003DF50
0x18003de33  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18003de38  lea     r9, [rsp+8B0h+cchName]; lpcchName
0x18003de3d  mov     [rsp+8B0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18003de42  lea     r8, [rsp+8B0h+Name]; lpName
0x18003de47  mov     [rsp+8B0h+lpcchClass], r13; lpcchClass
0x18003de4c  mov     edx, r14d; dwIndex
0x18003de4f  mov     [rsp+8B0h+lpClass], r13; lpClass
0x18003de54  mov     [rsp+8B0h+phkResult], r13; lpReserved
0x18003de59  mov     [rsp+8B0h+cchName], 401h
0x18003de61  call    cs:__imp_RegEnumKeyExW
0x18003de67  test    eax, eax
0x18003de69  jnz     loc_18003DF50
0x18003de6f  lea     rax, [rsp+8B0h+Name]
0x18003de74  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003de78  inc     rbx
0x18003de7b  cmp     [rax+rbx*2], r13w
0x18003de80  jnz     short loc_18003DE78
0x18003de82  cmp     rbx, 8
0x18003de86  jb      loc_18003DF42
0x18003de8c  lea     r12, [rsp+rbx*2+8B0h+cchName+2]
0x18003de91  lea     rsi, [rsp+8B0h+Name]
0x18003de96  mov     rdx, r12
0x18003de99  lea     r8, aOnetrace; "OneTrace"
0x18003dea0  sub     rdx, rsi
0x18003dea3  mov     rcx, rsi
0x18003dea6  sar     rdx, 1
0x18003dea9  call    ?find@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAPEB_WPEB_W_KAEB_W@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::find(wchar_t const *,unsigned __int64,wchar_t const &)
0x18003deae  mov     rdi, rax
0x18003deb1  test    rax, rax
0x18003deb4  jz      short loc_18003DEE4
0x18003deb6  lea     rsi, [rax+2]
0x18003deba  mov     r8d, 7
0x18003dec0  mov     rcx, rsi
0x18003dec3  lea     rdx, aOnetrace+2; "neTrace"
0x18003deca  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x18003decf  test    eax, eax
0x18003ded1  jnz     short loc_18003DE96
0x18003ded3  lea     rax, [rsp+8B0h+Name]
0x18003ded8  sub     rdi, rax
0x18003dedb  sar     rdi, 1
0x18003dede  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003dee2  jnz     short loc_18003DF4A
0x18003dee4  cmp     rbx, 9
0x18003dee8  jb      short loc_18003DF42
0x18003deea  lea     rsi, [rsp+rbx*2+8B0h+cchName]
0x18003deef  lea     rdi, [rsp+8B0h+Name]
0x18003def4  mov     rdx, rsi
0x18003def7  lea     r8, aOneTrace; "One Trace"
0x18003defe  sub     rdx, rdi
0x18003df01  mov     rcx, rdi
0x18003df04  sar     rdx, 1
0x18003df07  call    ?find@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAPEB_WPEB_W_KAEB_W@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::find(wchar_t const *,unsigned __int64,wchar_t const &)
0x18003df0c  mov     rbx, rax
0x18003df0f  test    rax, rax
0x18003df12  jz      short loc_18003DF42
0x18003df14  lea     rdi, [rax+2]
0x18003df18  mov     r8d, 8
0x18003df1e  mov     rcx, rdi
0x18003df21  lea     rdx, aOneTrace+2; "ne Trace"
0x18003df28  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x18003df2d  test    eax, eax
0x18003df2f  jnz     short loc_18003DEF4
0x18003df31  lea     rax, [rsp+8B0h+Name]
0x18003df36  sub     rbx, rax
0x18003df39  sar     rbx, 1
0x18003df3c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003df40  jnz     short loc_18003DF4A
0x18003df42  inc     r14d
0x18003df45  jmp     loc_18003DE33
0x18003df4a  mov     r15d, 1
0x18003df50  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18003df55  test    rcx, rcx
0x18003df58  jz      short loc_18003DF60
0x18003df5a  call    cs:__imp_RegCloseKey
0x18003df60  mov     eax, r15d
0x18003df63  mov     rcx, [rbp+7B0h+var_50]
0x18003df6a  xor     rcx, rsp; StackCookie
0x18003df6d  call    __security_check_cookie
0x18003df72  add     rsp, 878h
0x18003df79  pop     r15
0x18003df7b  pop     r14
0x18003df7d  pop     r13
0x18003df7f  pop     r12
0x18003df81  pop     rdi
0x18003df82  pop     rsi
0x18003df83  pop     rbx
0x18003df84  pop     rbp
0x18003df85  retn
```
