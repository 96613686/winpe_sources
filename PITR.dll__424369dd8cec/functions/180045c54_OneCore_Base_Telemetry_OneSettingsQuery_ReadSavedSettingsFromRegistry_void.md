# OneCore::Base::Telemetry::OneSettingsQuery::ReadSavedSettingsFromRegistry(void)

- ea: `0x180045c54`
- end: `0x180045f1d`
- name: `?ReadSavedSettingsFromRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `713`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180044ba0`

## callees

- `0x18001c5bc`
- `0x180040c7c`
- `0x18004110c`
- `0x180045c54`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180045ead`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180045ead`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045d3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045d3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045ed9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045ed9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180045e0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180045e0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045dad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045e22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045ee4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045dad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045e22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045ee4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045e31`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045e31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045d78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045d99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045ef2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045d78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045d99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045ef2`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::ReadSavedSettingsFromRegistry(
        OneCore::Base::Telemetry::OneSettingsQuery *this)
{
  char *v1; // r14
  char *v2; // r12
  char *v3; // r15
  BYTE *v5; // rsi
  signed int v6; // ebx
  LSTATUS v7; // eax
  bool v8; // cc
  int v9; // ebx
  RtlNameValueArray *v10; // rdi
  void *v11; // r8
  void *v12; // r8
  HANDLE ProcessHeap; // rax
  HKEY v14; // rcx
  DWORD v15; // ebx
  HANDLE v16; // rax
  int v17; // r14d
  DWORD i; // edx
  LSTATUS v19; // eax
  HANDLE v20; // rax
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[264]; // [rsp+290h] [rbp+190h] BYREF

  v1 = (char *)this + 560;
  v2 = (char *)this + 1080;
  v3 = (char *)this + 40;
  cchValueName = 0;
  cbData = 0;
  cbMaxValueLen = 0;
  Type = 0;
  hKey = 0;
  v5 = 0;
  v6 = StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls\\%ls", (char *)this + 1080, (char *)this + 40, (char *)this + 560);
  if ( v6 >= 0 )
  {
    v6 = StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls\\%ls\\%ls", v2, v3, v1, L"Settings");
    if ( v6 >= 0 )
    {
      v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
      v6 = v7;
      v8 = v7 <= 0;
      if ( v7 )
        goto LABEL_4;
      v10 = (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1608);
      RtlNameValueArray::Clear(v10);
      v11 = (void *)*((_QWORD *)v10 + 5);
      if ( v11 )
        HeapFree(*(HANDLE *)v10, 0, v11);
      *(_OWORD *)v10 = 0;
      *((_OWORD *)v10 + 1) = 0;
      *((_OWORD *)v10 + 2) = 0;
      v12 = (void *)*((_QWORD *)v10 + 5);
      if ( v12 )
        HeapFree(0, 0, v12);
      *(_OWORD *)v10 = 0;
      *((_OWORD *)v10 + 1) = 0;
      *((_OWORD *)v10 + 2) = 0;
      ProcessHeap = GetProcessHeap();
      v14 = hKey;
      *(_QWORD *)v10 = ProcessHeap;
      *((_QWORD *)v10 + 4) = 16;
      *((_QWORD *)v10 + 2) = 0;
      *((_QWORD *)v10 + 3) = 0;
      *((_QWORD *)v10 + 5) = 0;
      *((_QWORD *)v10 + 1) = 8;
      v7 = RegQueryInfoKeyW(v14, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
      v6 = v7;
      v8 = v7 <= 0;
      if ( v7 )
      {
LABEL_4:
        if ( v8 )
          goto LABEL_22;
        v9 = (unsigned __int16)v7;
        goto LABEL_6;
      }
      v15 = cbMaxValueLen;
      v16 = GetProcessHeap();
      v5 = (BYTE *)HeapAlloc(v16, 8u, v15);
      if ( !v5 )
      {
        v6 = -2147024882;
        goto LABEL_22;
      }
      v17 = 1;
      for ( i = 0; ; i = v17++ )
      {
        cbData = cbMaxValueLen;
        cchValueName = 260;
        v19 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, v5, &cbData);
        v6 = v19;
        if ( v19 )
          break;
        v6 = RtlNameValueArray::Append(v10, ValueName, (const unsigned __int16 *)v5);
        if ( v6 < 0 )
          goto LABEL_22;
      }
      if ( v19 == 259 )
      {
        v6 = 0;
      }
      else if ( v19 > 0 )
      {
        v9 = (unsigned __int16)v19;
LABEL_6:
        v6 = v9 | 0x80070000;
      }
    }
  }
LABEL_22:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v5);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180045c54  push    rbp
0x180045c56  push    rbx
0x180045c57  push    rsi
0x180045c58  push    rdi
0x180045c59  push    r12
0x180045c5b  push    r13
0x180045c5d  push    r14
0x180045c5f  push    r15
0x180045c61  lea     rbp, [rsp-3B8h]
0x180045c69  sub     rsp, 4B8h
0x180045c70  mov     rax, cs:__security_cookie
0x180045c77  xor     rax, rsp
0x180045c7a  mov     [rbp+3F0h+var_50], rax
0x180045c81  xor     r13d, r13d
0x180045c84  lea     r14, [rcx+230h]
0x180045c8b  lea     r12, [rcx+438h]
0x180045c92  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r14
0x180045c97  lea     r15, [rcx+28h]
0x180045c9b  mov     [rsp+4F0h+cchValueName], r13d
0x180045ca0  mov     rdi, rcx
0x180045ca3  mov     [rsp+4F0h+phkResult], r15
0x180045ca8  mov     r9, r12
0x180045cab  mov     [rsp+4F0h+cbData], r13d
0x180045cb0  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x180045cb7  mov     [rsp+4F0h+cbMaxValueLen], r13d
0x180045cbc  mov     edx, 104h; unsigned __int64
0x180045cc1  mov     [rsp+4F0h+Type], r13d
0x180045cc6  lea     rcx, [rbp+3F0h+SubKey]; unsigned __int16 *
0x180045cca  mov     [rsp+4F0h+hKey], r13
0x180045ccf  mov     esi, r13d
0x180045cd2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180045cd7  mov     ebx, eax
0x180045cd9  test    eax, eax
0x180045cdb  js      loc_180045ECF
0x180045ce1  lea     rax, aSettings_0; "Settings"
0x180045ce8  mov     r9, r12
0x180045ceb  mov     [rsp+4F0h+lpcbMaxClassLen], rax
0x180045cf0  lea     r8, aLsLsLsLs; "%ls\\%ls\\%ls\\%ls"
0x180045cf7  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r14
0x180045cfc  lea     rcx, [rbp+3F0h+SubKey]; unsigned __int16 *
0x180045d00  mov     [rsp+4F0h+phkResult], r15
0x180045d05  mov     r15d, 104h
0x180045d0b  mov     edx, r15d; unsigned __int64
0x180045d0e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180045d13  mov     ebx, eax
0x180045d15  test    eax, eax
0x180045d17  js      loc_180045ECF
0x180045d1d  lea     rax, [rsp+4F0h+hKey]
0x180045d22  mov     r9d, 20019h; samDesired
0x180045d28  xor     r8d, r8d; ulOptions
0x180045d2b  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180045d30  lea     rdx, [rbp+3F0h+SubKey]; lpSubKey
0x180045d34  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180045d3b  call    cs:__imp_RegOpenKeyExW
0x180045d41  mov     ebx, eax
0x180045d43  test    eax, eax
0x180045d45  jz      short loc_180045D5B
0x180045d47  jle     loc_180045ECF
0x180045d4d  movzx   ebx, ax
0x180045d50  or      ebx, 80070000h
0x180045d56  jmp     loc_180045ECF
0x180045d5b  add     rdi, 648h
0x180045d62  mov     rcx, rdi; this
0x180045d65  call    ?Clear@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Clear(void)
0x180045d6a  mov     r8, [rdi+28h]; lpMem
0x180045d6e  test    r8, r8
0x180045d71  jz      short loc_180045D7E
0x180045d73  mov     rcx, [rdi]; hHeap
0x180045d76  xor     edx, edx; dwFlags
0x180045d78  call    cs:__imp_HeapFree
0x180045d7e  xorps   xmm0, xmm0
0x180045d81  movups  xmmword ptr [rdi], xmm0
0x180045d84  movups  xmmword ptr [rdi+10h], xmm0
0x180045d88  movups  xmmword ptr [rdi+20h], xmm0
0x180045d8c  mov     r8, [rdi+28h]; lpMem
0x180045d90  test    r8, r8
0x180045d93  jz      short loc_180045D9F
0x180045d95  xor     edx, edx; dwFlags
0x180045d97  xor     ecx, ecx; hHeap
0x180045d99  call    cs:__imp_HeapFree
0x180045d9f  xorps   xmm0, xmm0
0x180045da2  movups  xmmword ptr [rdi], xmm0
0x180045da5  movups  xmmword ptr [rdi+10h], xmm0
0x180045da9  movups  xmmword ptr [rdi+20h], xmm0
0x180045dad  call    cs:__imp_GetProcessHeap
0x180045db3  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180045db8  mov     r14d, 8
0x180045dbe  mov     [rsp+4F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180045dc3  xor     r9d, r9d; lpReserved
0x180045dc6  mov     [rsp+4F0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180045dcb  xor     r8d, r8d; lpcchClass
0x180045dce  mov     [rdi], rax
0x180045dd1  xor     edx, edx; lpClass
0x180045dd3  lea     rax, [rsp+4F0h+cbMaxValueLen]
0x180045dd8  mov     qword ptr [rdi+20h], 10h
0x180045de0  mov     [rsp+4F0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180045de5  mov     [rsp+4F0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180045dea  mov     [rsp+4F0h+lpcValues], r13; lpcValues
0x180045def  mov     [rsp+4F0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180045df4  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180045df9  mov     [rsp+4F0h+phkResult], r13; lpcSubKeys
0x180045dfe  mov     [rdi+10h], r13
0x180045e02  mov     [rdi+18h], r13
0x180045e06  mov     [rdi+28h], r13
0x180045e0a  mov     [rdi+8], r14
0x180045e0e  call    cs:__imp_RegQueryInfoKeyW
0x180045e14  mov     ebx, eax
0x180045e16  test    eax, eax
0x180045e18  jnz     loc_180045D47
0x180045e1e  mov     ebx, [rsp+4F0h+cbMaxValueLen]
0x180045e22  call    cs:__imp_GetProcessHeap
0x180045e28  mov     r8d, ebx; dwBytes
0x180045e2b  mov     edx, r14d; dwFlags
0x180045e2e  mov     rcx, rax; hHeap
0x180045e31  call    cs:__imp_HeapAlloc
0x180045e37  mov     rsi, rax
0x180045e3a  test    rax, rax
0x180045e3d  jnz     short loc_180045E49
0x180045e3f  mov     ebx, 8007000Eh
0x180045e44  jmp     loc_180045ECF
0x180045e49  mov     r14d, 1
0x180045e4f  xor     edx, edx
0x180045e51  jmp     short loc_180045E71
0x180045e53  mov     r8, rsi; unsigned __int16 *
0x180045e56  lea     rdx, [rbp+3F0h+ValueName]; unsigned __int16 *
0x180045e5d  mov     rcx, rdi; this
0x180045e60  call    ?Append@RtlNameValueArray@@QEAAJPEBG0@Z; RtlNameValueArray::Append(ushort const *,ushort const *)
0x180045e65  mov     ebx, eax
0x180045e67  test    eax, eax
0x180045e69  js      short loc_180045ECF
0x180045e6b  mov     edx, r14d; dwIndex
0x180045e6e  inc     r14d
0x180045e71  mov     eax, [rsp+4F0h+cbMaxValueLen]
0x180045e75  lea     r9, [rsp+4F0h+cchValueName]; lpcchValueName
0x180045e7a  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180045e7f  lea     r8, [rbp+3F0h+ValueName]; lpValueName
0x180045e86  mov     [rsp+4F0h+cbData], eax
0x180045e8a  lea     rax, [rsp+4F0h+cbData]
0x180045e8f  mov     [rsp+4F0h+lpcValues], rax; lpcbData
0x180045e94  lea     rax, [rsp+4F0h+Type]
0x180045e99  mov     [rsp+4F0h+lpcbMaxClassLen], rsi; lpData
0x180045e9e  mov     [rsp+4F0h+lpcbMaxSubKeyLen], rax; lpType
0x180045ea3  mov     [rsp+4F0h+phkResult], r13; lpReserved
0x180045ea8  mov     [rsp+4F0h+cchValueName], r15d
0x180045ead  call    cs:__imp_RegEnumValueW
0x180045eb3  mov     ebx, eax
0x180045eb5  test    eax, eax
0x180045eb7  jz      short loc_180045E53
0x180045eb9  cmp     eax, 103h
0x180045ebe  jz      short loc_180045ECC
0x180045ec0  test    eax, eax
0x180045ec2  jle     short loc_180045ECF
0x180045ec4  movzx   ebx, bx
0x180045ec7  jmp     loc_180045D50
0x180045ecc  mov     ebx, r13d
0x180045ecf  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180045ed4  test    rcx, rcx
0x180045ed7  jz      short loc_180045EDF
0x180045ed9  call    cs:__imp_RegCloseKey
0x180045edf  test    rsi, rsi
0x180045ee2  jz      short loc_180045EF8
0x180045ee4  call    cs:__imp_GetProcessHeap
0x180045eea  mov     r8, rsi; lpMem
0x180045eed  xor     edx, edx; dwFlags
0x180045eef  mov     rcx, rax; hHeap
0x180045ef2  call    cs:__imp_HeapFree
0x180045ef8  mov     eax, ebx
0x180045efa  mov     rcx, [rbp+3F0h+var_50]
0x180045f01  xor     rcx, rsp; StackCookie
0x180045f04  call    __security_check_cookie
0x180045f09  add     rsp, 4B8h
0x180045f10  pop     r15
0x180045f12  pop     r14
0x180045f14  pop     r13
0x180045f16  pop     r12
0x180045f18  pop     rdi
0x180045f19  pop     rsi
0x180045f1a  pop     rbx
0x180045f1b  pop     rbp
0x180045f1c  retn
```
