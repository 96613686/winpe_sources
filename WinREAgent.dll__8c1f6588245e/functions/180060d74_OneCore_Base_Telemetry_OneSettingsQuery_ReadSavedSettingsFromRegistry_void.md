# OneCore::Base::Telemetry::OneSettingsQuery::ReadSavedSettingsFromRegistry(void)

- ea: `0x180060d74`
- end: `0x180060fec`
- name: `?ReadSavedSettingsFromRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `632`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18005fd5c`

## callees

- `0x180012864`
- `0x18005ce88`
- `0x18005dbe4`
- `0x18005ea9c`
- `0x180060d74`
- `0x18006c690`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x180060ed6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180060ed6`
- `ADVAPI32!RegEnumValueW` at `0x180060f7c`
- `ADVAPI32!RegEnumValueW` at `0x180060f7c`
- `ADVAPI32!RegCloseKey` at `0x180060fa8`
- `ADVAPI32!RegCloseKey` at `0x180060fa8`
- `ADVAPI32!RegOpenKeyExW` at `0x180060e5b`
- `ADVAPI32!RegOpenKeyExW` at `0x180060e5b`
- `KERNEL32!HeapFree` at `0x180060fc1`
- `KERNEL32!HeapFree` at `0x180060fc1`
- `KERNEL32!HeapAlloc` at `0x180060ef7`
- `KERNEL32!HeapAlloc` at `0x180060ef7`
- `KERNEL32!GetProcessHeap` at `0x180060ee6`
- `KERNEL32!GetProcessHeap` at `0x180060fb3`
- `KERNEL32!GetProcessHeap` at `0x180060ee6`
- `KERNEL32!GetProcessHeap` at `0x180060fb3`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::ReadSavedSettingsFromRegistry(
        OneCore::Base::Telemetry::OneSettingsQuery *this)
{
  char *v1; // r14
  char *v2; // r12
  char *v3; // r15
  BYTE *v5; // rdi
  signed int v6; // ebx
  LSTATUS v7; // eax
  bool v8; // cc
  int v9; // ebx
  unsigned __int64 *v10; // rsi
  DWORD v11; // ebx
  HANDLE ProcessHeap; // rax
  int v13; // r14d
  DWORD i; // edx
  LSTATUS v15; // eax
  const unsigned __int16 *v16; // rdx
  HANDLE v17; // rax
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
      {
LABEL_4:
        if ( v8 )
          goto LABEL_19;
        v9 = (unsigned __int16)v7;
        goto LABEL_6;
      }
      v10 = (unsigned __int64 *)((char *)this + 1608);
      RtlNameValueArray::Free((RtlNameValueArray *)v10);
      v6 = RtlArray<unsigned short *>::Initialize(v10);
      if ( v6 >= 0 )
      {
        v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
        v6 = v7;
        v8 = v7 <= 0;
        if ( v7 )
          goto LABEL_4;
        v11 = cbMaxValueLen;
        ProcessHeap = GetProcessHeap();
        v5 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v11);
        if ( v5 )
        {
          v13 = 1;
          for ( i = 0; ; i = v13++ )
          {
            cbData = cbMaxValueLen;
            cchValueName = 260;
            v15 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, v5, &cbData);
            v6 = v15;
            if ( v15 )
              break;
            v6 = RtlNameValueArray::Insert(
                   (RtlNameValueArray *)v10,
                   v16,
                   ValueName,
                   (const unsigned __int16 *)v5,
                   v10[2]);
            if ( v6 < 0 )
              goto LABEL_19;
          }
          if ( v15 == 259 )
          {
            v6 = 0;
          }
          else if ( v15 > 0 )
          {
            v9 = (unsigned __int16)v15;
LABEL_6:
            v6 = v9 | 0x80070000;
          }
        }
        else
        {
          v6 = -2147024882;
        }
      }
    }
  }
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v5);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180060d74  push    rbp
0x180060d76  push    rbx
0x180060d77  push    rsi
0x180060d78  push    rdi
0x180060d79  push    r12
0x180060d7b  push    r13
0x180060d7d  push    r14
0x180060d7f  push    r15
0x180060d81  lea     rbp, [rsp-3B8h]
0x180060d89  sub     rsp, 4B8h
0x180060d90  mov     rax, cs:__security_cookie
0x180060d97  xor     rax, rsp
0x180060d9a  mov     [rbp+3F0h+var_50], rax
0x180060da1  xor     r13d, r13d
0x180060da4  lea     r14, [rcx+230h]
0x180060dab  lea     r12, [rcx+438h]
0x180060db2  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r14
0x180060db7  lea     r15, [rcx+28h]
0x180060dbb  mov     [rsp+4F0h+cchValueName], r13d
0x180060dc0  mov     rsi, rcx
0x180060dc3  mov     [rsp+4F0h+phkResult], r15
0x180060dc8  mov     r9, r12
0x180060dcb  mov     [rsp+4F0h+cbData], r13d
0x180060dd0  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x180060dd7  mov     [rsp+4F0h+cbMaxValueLen], r13d
0x180060ddc  mov     edx, 104h; unsigned __int64
0x180060de1  mov     [rsp+4F0h+Type], r13d
0x180060de6  lea     rcx, [rbp+3F0h+SubKey]; unsigned __int16 *
0x180060dea  mov     [rsp+4F0h+hKey], r13
0x180060def  mov     edi, r13d
0x180060df2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180060df7  mov     ebx, eax
0x180060df9  test    eax, eax
0x180060dfb  js      loc_180060F9E
0x180060e01  lea     rax, aSettings_0; "Settings"
0x180060e08  mov     r9, r12
0x180060e0b  mov     [rsp+4F0h+lpcbMaxClassLen], rax
0x180060e10  lea     r8, aLsLsLsLs; "%ls\\%ls\\%ls\\%ls"
0x180060e17  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r14
0x180060e1c  lea     rcx, [rbp+3F0h+SubKey]; unsigned __int16 *
0x180060e20  mov     [rsp+4F0h+phkResult], r15
0x180060e25  mov     r15d, 104h
0x180060e2b  mov     edx, r15d; unsigned __int64
0x180060e2e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180060e33  mov     ebx, eax
0x180060e35  test    eax, eax
0x180060e37  js      loc_180060F9E
0x180060e3d  lea     rax, [rsp+4F0h+hKey]
0x180060e42  mov     r9d, 20019h; samDesired
0x180060e48  xor     r8d, r8d; ulOptions
0x180060e4b  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180060e50  lea     rdx, [rbp+3F0h+SubKey]; lpSubKey
0x180060e54  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180060e5b  call    cs:__imp_RegOpenKeyExW
0x180060e61  mov     ebx, eax
0x180060e63  test    eax, eax
0x180060e65  jz      short loc_180060E7B
0x180060e67  jle     loc_180060F9E
0x180060e6d  movzx   ebx, ax
0x180060e70  or      ebx, 80070000h
0x180060e76  jmp     loc_180060F9E
0x180060e7b  add     rsi, 648h
0x180060e82  mov     rcx, rsi; this
0x180060e85  call    ?Free@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Free(void)
0x180060e8a  mov     rcx, rsi
0x180060e8d  call    ?Initialize@?$RtlArray@PEAG@@QEAAJPEAX_K1H@Z; RtlArray<ushort *>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x180060e92  mov     ebx, eax
0x180060e94  test    eax, eax
0x180060e96  js      loc_180060F9E
0x180060e9c  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180060ea1  lea     rax, [rsp+4F0h+cbMaxValueLen]
0x180060ea6  mov     [rsp+4F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180060eab  xor     r9d, r9d; lpReserved
0x180060eae  mov     [rsp+4F0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180060eb3  xor     r8d, r8d; lpcchClass
0x180060eb6  mov     [rsp+4F0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180060ebb  xor     edx, edx; lpClass
0x180060ebd  mov     [rsp+4F0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180060ec2  mov     [rsp+4F0h+lpcValues], r13; lpcValues
0x180060ec7  mov     [rsp+4F0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180060ecc  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180060ed1  mov     [rsp+4F0h+phkResult], r13; lpcSubKeys
0x180060ed6  call    cs:__imp_RegQueryInfoKeyW
0x180060edc  mov     ebx, eax
0x180060ede  test    eax, eax
0x180060ee0  jnz     short loc_180060E67
0x180060ee2  mov     ebx, [rsp+4F0h+cbMaxValueLen]
0x180060ee6  call    cs:__imp_GetProcessHeap
0x180060eec  mov     r8d, ebx; dwBytes
0x180060eef  mov     edx, 8; dwFlags
0x180060ef4  mov     rcx, rax; hHeap
0x180060ef7  call    cs:__imp_HeapAlloc
0x180060efd  mov     rdi, rax
0x180060f00  test    rax, rax
0x180060f03  jnz     short loc_180060F0F
0x180060f05  mov     ebx, 8007000Eh
0x180060f0a  jmp     loc_180060F9E
0x180060f0f  mov     r14d, 1
0x180060f15  xor     edx, edx
0x180060f17  jmp     short loc_180060F40
0x180060f19  mov     rax, [rsi+10h]
0x180060f1d  lea     r8, [rbp+3F0h+ValueName]; unsigned __int16 *
0x180060f24  mov     r9, rdi; unsigned __int16 *
0x180060f27  mov     [rsp+4F0h+phkResult], rax; unsigned __int64
0x180060f2c  mov     rcx, rsi; this
0x180060f2f  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x180060f34  mov     ebx, eax
0x180060f36  test    eax, eax
0x180060f38  js      short loc_180060F9E
0x180060f3a  mov     edx, r14d; dwIndex
0x180060f3d  inc     r14d
0x180060f40  mov     eax, [rsp+4F0h+cbMaxValueLen]
0x180060f44  lea     r9, [rsp+4F0h+cchValueName]; lpcchValueName
0x180060f49  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180060f4e  lea     r8, [rbp+3F0h+ValueName]; lpValueName
0x180060f55  mov     [rsp+4F0h+cbData], eax
0x180060f59  lea     rax, [rsp+4F0h+cbData]
0x180060f5e  mov     [rsp+4F0h+lpcValues], rax; lpcbData
0x180060f63  lea     rax, [rsp+4F0h+Type]
0x180060f68  mov     [rsp+4F0h+lpcbMaxClassLen], rdi; lpData
0x180060f6d  mov     [rsp+4F0h+lpcbMaxSubKeyLen], rax; lpType
0x180060f72  mov     [rsp+4F0h+phkResult], r13; lpReserved
0x180060f77  mov     [rsp+4F0h+cchValueName], r15d
0x180060f7c  call    cs:__imp_RegEnumValueW
0x180060f82  mov     ebx, eax
0x180060f84  test    eax, eax
0x180060f86  jz      short loc_180060F19
0x180060f88  cmp     eax, 103h
0x180060f8d  jz      short loc_180060F9B
0x180060f8f  test    eax, eax
0x180060f91  jle     short loc_180060F9E
0x180060f93  movzx   ebx, bx
0x180060f96  jmp     loc_180060E70
0x180060f9b  mov     ebx, r13d
0x180060f9e  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180060fa3  test    rcx, rcx
0x180060fa6  jz      short loc_180060FAE
0x180060fa8  call    cs:__imp_RegCloseKey
0x180060fae  test    rdi, rdi
0x180060fb1  jz      short loc_180060FC7
0x180060fb3  call    cs:__imp_GetProcessHeap
0x180060fb9  mov     r8, rdi; lpMem
0x180060fbc  xor     edx, edx; dwFlags
0x180060fbe  mov     rcx, rax; hHeap
0x180060fc1  call    cs:__imp_HeapFree
0x180060fc7  mov     eax, ebx
0x180060fc9  mov     rcx, [rbp+3F0h+var_50]
0x180060fd0  xor     rcx, rsp; StackCookie
0x180060fd3  call    __security_check_cookie
0x180060fd8  add     rsp, 4B8h
0x180060fdf  pop     r15
0x180060fe1  pop     r14
0x180060fe3  pop     r13
0x180060fe5  pop     r12
0x180060fe7  pop     rdi
0x180060fe8  pop     rsi
0x180060fe9  pop     rbx
0x180060fea  pop     rbp
0x180060feb  retn
```
