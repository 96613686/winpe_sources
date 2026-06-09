# GetProgLangIdOfName(char const *,_GUID *)

- ea: `0x18001c700`
- end: `0x18001c87a`
- name: `?GetProgLangIdOfName@@YAJPEBDPEAU_GUID@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006e24`

## callees

- `0x180013178`
- `0x180013230`
- `0x18001c700`
- `0x180023dd0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001c7c5`
- `ADVAPI32!RegCloseKey` at `0x18001c844`
- `ADVAPI32!RegCloseKey` at `0x18001c7c5`
- `ADVAPI32!RegCloseKey` at `0x18001c844`
- `ADVAPI32!RegQueryValueExA` at `0x18001c800`
- `ADVAPI32!RegQueryValueExA` at `0x18001c800`
- `ADVAPI32!RegOpenKeyExA` at `0x18001c789`
- `ADVAPI32!RegOpenKeyExA` at `0x18001c7b8`
- `ADVAPI32!RegOpenKeyExA` at `0x18001c789`
- `ADVAPI32!RegOpenKeyExA` at `0x18001c7b8`
- `ole32!CLSIDFromString` at `0x18001c82e`
- `ole32!CLSIDFromString` at `0x18001c82e`

## string_xrefs

- `0x18001c7b1`: `CLSID`

## pseudocode

```c
__int64 __fastcall GetProgLangIdOfName(LPCSTR lpSubKey, struct _GUID *a2)
{
  LSTATUS v3; // eax
  int v4; // ebx
  LSTATUS v5; // eax
  int v6; // r9d
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  CLSID pclsid; // [rsp+48h] [rbp-B8h] BYREF
  LPCOLESTR lpsz; // [rsp+60h] [rbp-A0h] BYREF
  char v14; // [rsp+68h] [rbp-98h] BYREF
  int v15; // [rsp+268h] [rbp+168h]
  BYTE Data[40]; // [rsp+270h] [rbp+170h] BYREF

  hKey = 0;
  lpsz = (LPCOLESTR)&v14;
  phkResult = 0;
  Type = 0;
  cbData = 0;
  v15 = 0;
  pclsid = 0;
  v3 = RegOpenKeyExA(HKEY_CLASSES_ROOT, lpSubKey, 0, 0x20019u, &hKey);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 <= 0 )
      goto LABEL_6;
    v4 = (unsigned __int16)v3;
LABEL_11:
    v4 |= 0x80070000;
    goto LABEL_6;
  }
  v4 = RegOpenKeyExA(hKey, "CLSID", 0, 0x20019u, &phkResult);
  RegCloseKey(hKey);
  if ( v4 )
  {
    if ( v4 <= 0 )
      goto LABEL_6;
    v4 = (unsigned __int16)v4;
    goto LABEL_11;
  }
  cbData = 40;
  v5 = RegQueryValueExA(phkResult, 0, 0, &Type, Data, &cbData);
  v4 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
  }
  else
  {
    CMBCSToWChar::Init((LPVOID *)&lpsz, (const char *)Data, 0, v6);
    v4 = CLSIDFromString(lpsz, &pclsid);
    *a2 = pclsid;
  }
  RegCloseKey(phkResult);
LABEL_6:
  CMBCSToWChar::~CMBCSToWChar((CMBCSToWChar *)&lpsz);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001c700  mov     [rsp-8+arg_10], rbx
0x18001c705  mov     [rsp-8+arg_18], rdi
0x18001c70a  push    rbp
0x18001c70b  lea     rbp, [rsp-1A0h]
0x18001c713  sub     rsp, 2A0h
0x18001c71a  mov     rax, cs:__security_cookie
0x18001c721  xor     rax, rsp
0x18001c724  mov     [rbp+1A0h+var_8], rax
0x18001c72b  lea     rax, [rsp+2A0h+var_238]
0x18001c730  mov     [rsp+2A0h+hKey], 0
0x18001c739  mov     [rsp+2A0h+lpsz], rax
0x18001c73e  mov     rdi, rdx
0x18001c741  lea     rax, [rsp+2A0h+hKey]
0x18001c746  mov     [rsp+2A0h+var_260], 0
0x18001c74f  xorps   xmm0, xmm0
0x18001c752  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18001c757  mov     rdx, rcx; lpSubKey
0x18001c75a  mov     [rsp+2A0h+Type], 0
0x18001c762  mov     r9d, 20019h; samDesired
0x18001c768  mov     [rsp+2A0h+cbData], 0
0x18001c770  xor     r8d, r8d; ulOptions
0x18001c773  mov     [rbp+1A0h+var_38], 0
0x18001c77d  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001c784  movups  xmmword ptr [rsp+2A0h+pclsid.Data1], xmm0
0x18001c789  call    cs:__imp_RegOpenKeyExA
0x18001c78f  mov     ebx, eax
0x18001c791  test    eax, eax
0x18001c793  jnz     loc_18002FBCA
0x18001c799  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001c79e  lea     rax, [rsp+2A0h+var_260]
0x18001c7a3  mov     r9d, 20019h; samDesired
0x18001c7a9  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18001c7ae  xor     r8d, r8d; ulOptions
0x18001c7b1  lea     rdx, aClsid_0; "CLSID"
0x18001c7b8  call    cs:__imp_RegOpenKeyExA
0x18001c7be  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001c7c3  mov     ebx, eax
0x18001c7c5  call    cs:__imp_RegCloseKey
0x18001c7cb  test    ebx, ebx
0x18001c7cd  jnz     loc_18002FBD5
0x18001c7d3  mov     rcx, [rsp+2A0h+var_260]; hKey
0x18001c7d8  lea     rax, [rsp+2A0h+cbData]
0x18001c7dd  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x18001c7e2  lea     r9, [rsp+2A0h+Type]; lpType
0x18001c7e7  lea     rax, [rbp+1A0h+Data]
0x18001c7ee  mov     [rsp+2A0h+cbData], 28h ; '('
0x18001c7f6  xor     r8d, r8d; lpReserved
0x18001c7f9  mov     [rsp+2A0h+phkResult], rax; lpData
0x18001c7fe  xor     edx, edx; lpValueName
0x18001c800  call    cs:__imp_RegQueryValueExA
0x18001c806  mov     ebx, eax
0x18001c808  test    eax, eax
0x18001c80a  jnz     loc_18002FBE9
0x18001c810  xor     r8d, r8d; unsigned int
0x18001c813  lea     rdx, [rbp+1A0h+Data]; char *
0x18001c81a  lea     rcx, [rsp+2A0h+lpsz]; this
0x18001c81f  call    ?Init@CMBCSToWChar@@QEAAJPEBDIH@Z; CMBCSToWChar::Init(char const *,uint,int)
0x18001c824  mov     rcx, [rsp+2A0h+lpsz]; lpsz
0x18001c829  lea     rdx, [rsp+2A0h+pclsid]; pclsid
0x18001c82e  call    cs:__imp_CLSIDFromString
0x18001c834  movups  xmm0, xmmword ptr [rsp+2A0h+pclsid.Data1]
0x18001c839  mov     ebx, eax
0x18001c83b  movdqu  xmmword ptr [rdi], xmm0
0x18001c83f  mov     rcx, [rsp+2A0h+var_260]; hKey
0x18001c844  call    cs:__imp_RegCloseKey
0x18001c84a  lea     rcx, [rsp+2A0h+lpsz]; this
0x18001c84f  call    ??1CMBCSToWChar@@QEAA@XZ; CMBCSToWChar::~CMBCSToWChar(void)
0x18001c854  mov     eax, ebx
0x18001c856  mov     rcx, [rbp+1A0h+var_8]
0x18001c85d  xor     rcx, rsp; StackCookie
0x18001c860  call    __security_check_cookie
0x18001c865  lea     r11, [rsp+2A0h+var_s0]
0x18001c86d  mov     rbx, [r11+20h]
0x18001c871  mov     rdi, [r11+28h]
0x18001c875  mov     rsp, r11
0x18001c878  pop     rbp
0x18001c879  retn
0x18002fbca  jle     loc_18001C84A
0x18002fbd0  movzx   ebx, ax
0x18002fbd3  jmp     short loc_18002FBDE
0x18002fbd5  jle     loc_18001C84A
0x18002fbdb  movzx   ebx, bx
0x18002fbde  or      ebx, 80070000h
0x18002fbe4  jmp     loc_18001C84A
0x18002fbe9  jle     loc_18001C83F
0x18002fbef  movzx   ebx, ax
0x18002fbf2  or      ebx, 80070000h
0x18002fbf8  jmp     loc_18001C83F
```
