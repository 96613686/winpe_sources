# RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)

- ea: `0x180026a10`
- end: `0x180026bd6`
- name: `?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z`
- size: `454`
- prototype: `RegistryKey *__fastcall(HKEY *, RegistryKey *, const WCHAR *, REGSAM samDesired, HANDLE)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009cfc`
- `0x18001e3a8`
- `0x180021650`
- `0x1800296fc`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008c78`
- `0x18002498c`
- `0x180026958`
- `0x180026a10`
- `0x18002804c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180026b02`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180026b46`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180026b02`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180026b46`

## pseudocode

```c
RegistryKey *__fastcall RegistryKey::CreateSubKey(
        HKEY *a1,
        RegistryKey *a2,
        const WCHAR *a3,
        REGSAM samDesired,
        HANDLE a5)
{
  HKEY v7; // r14
  signed int v9; // ebx
  LSTATUS v10; // ebx
  DWORD dwOptions; // [rsp+20h] [rbp-148h]
  int lpSecurityAttributes; // [rsp+30h] [rbp-138h]
  _BYTE pExceptionObject[208]; // [rsp+58h] [rbp-110h] BYREF
  HKEY phkResult; // [rsp+128h] [rbp-40h] BYREF

  phkResult = (HKEY)a2;
  v7 = *a1;
  phkResult = 0;
  if ( a5 )
  {
    v9 = RegCreateKeyTransacted_Wrapper(v7, a3, dwOptions, &phkResult, lpSecurityAttributes, a5);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_419802ccba213757c01acb0d7aa84d96_Traceguids,
          (_DWORD)a3,
          v9);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v9);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  else
  {
    v10 = RegCreateKeyExW(v7, a3, 0, 0, 0, samDesired, 0, &phkResult, 0);
    if ( v10 == 5 )
      v10 = RegCreateKeyExW(v7, a3, 0, 0, 4u, samDesired, 0, &phkResult, 0);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_419802ccba213757c01acb0d7aa84d96_Traceguids,
          (_DWORD)a3,
          v10);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v10);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  RegistryKey::RegistryKey(a2, phkResult);
  return a2;
}

```

## disassembly

```asm
0x180026a10  mov     r11, rsp
0x180026a13  push    rbx
0x180026a14  push    rbp
0x180026a15  push    rsi
0x180026a16  push    rdi
0x180026a17  push    r14
0x180026a19  sub     rsp, 140h
0x180026a20  mov     rax, cs:__security_cookie
0x180026a27  xor     rax, rsp
0x180026a2a  mov     [rsp+168h+var_38], rax
0x180026a32  mov     rax, [rsp+168h+arg_20]
0x180026a3a  mov     rsi, rdx
0x180026a3d  mov     [rsp+168h+var_40], rdx
0x180026a45  mov     ebp, r9d
0x180026a48  mov     r14, [rcx]
0x180026a4b  mov     rdi, r8
0x180026a4e  mov     qword ptr [r11-40h], 0
0x180026a56  mov     rcx, r14; hKey
0x180026a59  mov     rdx, r8; lpSubKey
0x180026a5c  test    rax, rax
0x180026a5f  jz      short loc_180026AD1
0x180026a61  mov     [rsp+168h+phkResult], rax; HANDLE
0x180026a66  lea     rax, [r11-40h]
0x180026a6a  mov     qword ptr [rsp+168h+samDesired], rax; PHKEY
0x180026a6f  call    RegCreateKeyTransacted_Wrapper
0x180026a74  mov     ebx, eax
0x180026a76  test    eax, eax
0x180026a78  jz      loc_180026BA5
0x180026a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a85  lea     rax, WPP_GLOBAL_Control
0x180026a8c  cmp     rcx, rax
0x180026a8f  jz      short loc_180026AB3
0x180026a91  cmp     byte ptr [rcx+19h], 2
0x180026a95  jb      short loc_180026AB3
0x180026a97  mov     rcx, [rcx+10h]
0x180026a9b  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180026aa2  mov     edx, 0Fh
0x180026aa7  mov     [rsp+168h+dwOptions], ebx
0x180026aab  mov     r9, rdi
0x180026aae  call    WPP_SF_Sd
0x180026ab3  mov     edx, ebx; int
0x180026ab5  lea     rcx, [rsp+168h+pExceptionObject]; this
0x180026aba  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180026abf  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180026ac6  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x180026acb  call    _CxxThrowException_0
0x180026ad1  mov     [rsp+168h+lpdwDisposition], 0; lpdwDisposition
0x180026ada  lea     rax, [rsp+168h+var_40]
0x180026ae2  mov     [rsp+168h+phkResult], rax; phkResult
0x180026ae7  xor     r9d, r9d; lpClass
0x180026aea  mov     [rsp+168h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180026af3  xor     r8d, r8d; Reserved
0x180026af6  mov     [rsp+168h+samDesired], ebp; samDesired
0x180026afa  mov     [rsp+168h+dwOptions], 0; dwOptions
0x180026b02  call    cs:__imp_RegCreateKeyExW
0x180026b08  mov     ebx, eax
0x180026b0a  cmp     eax, 5
0x180026b0d  jnz     short loc_180026B4E
0x180026b0f  mov     [rsp+168h+lpdwDisposition], 0; lpdwDisposition
0x180026b18  lea     rax, [rsp+168h+var_40]
0x180026b20  mov     [rsp+168h+phkResult], rax; phkResult
0x180026b25  xor     r9d, r9d; lpClass
0x180026b28  mov     [rsp+168h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180026b31  xor     r8d, r8d; Reserved
0x180026b34  mov     [rsp+168h+samDesired], ebp; samDesired
0x180026b38  mov     rdx, rdi; lpSubKey
0x180026b3b  mov     rcx, r14; hKey
0x180026b3e  mov     [rsp+168h+dwOptions], 4; dwOptions
0x180026b46  call    cs:__imp_RegCreateKeyExW
0x180026b4c  mov     ebx, eax
0x180026b4e  test    ebx, ebx
0x180026b50  jz      short loc_180026BA5
0x180026b52  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b59  lea     rax, WPP_GLOBAL_Control
0x180026b60  cmp     rcx, rax
0x180026b63  jz      short loc_180026B87
0x180026b65  cmp     byte ptr [rcx+19h], 2
0x180026b69  jb      short loc_180026B87
0x180026b6b  mov     rcx, [rcx+10h]
0x180026b6f  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180026b76  mov     edx, 10h
0x180026b7b  mov     [rsp+168h+dwOptions], ebx
0x180026b7f  mov     r9, rdi
0x180026b82  call    WPP_SF_Sd
0x180026b87  mov     edx, ebx; int
0x180026b89  lea     rcx, [rsp+168h+pExceptionObject]; this
0x180026b8e  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180026b93  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180026b9a  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x180026b9f  call    _CxxThrowException_0
0x180026ba5  mov     rdx, [rsp+168h+var_40]; HKEY
0x180026bad  mov     rcx, rsi; this
0x180026bb0  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x180026bb5  mov     rax, rsi
0x180026bb8  mov     rcx, [rsp+168h+var_38]
0x180026bc0  xor     rcx, rsp; StackCookie
0x180026bc3  call    __security_check_cookie
0x180026bc8  add     rsp, 140h
0x180026bcf  pop     r14
0x180026bd1  pop     rdi
0x180026bd2  pop     rsi
0x180026bd3  pop     rbp
0x180026bd4  pop     rbx
0x180026bd5  retn
```
