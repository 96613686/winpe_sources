# OleCGetThreadModel(char *)

- ea: `0x18003b6f8`
- end: `0x18003b852`
- name: `?OleCGetThreadModel@@YA?AW4THREADMODEL@@PEAD@Z`
- size: `346`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ff44`
- `0x18008022c`
- `0x180080d48`
- `0x180081b04`

## callees

- `0x18003b6f8`
- `0x180379380`
- `0x180379520`
- `0x1803796b4`

## import_xrefs

- `KERNEL32!lstrcmpiA` at `0x18003b7e0`
- `KERNEL32!lstrcmpiA` at `0x18003b7fa`
- `KERNEL32!lstrcmpiA` at `0x18003b810`
- `KERNEL32!lstrcmpiA` at `0x18003b7e0`
- `KERNEL32!lstrcmpiA` at `0x18003b7fa`
- `KERNEL32!lstrcmpiA` at `0x18003b810`
- `USER32!wsprintfA` at `0x18003b760`
- `USER32!wsprintfA` at `0x18003b760`
- `ADVAPI32!RegOpenKeyExA` at `0x18003b785`
- `ADVAPI32!RegOpenKeyExA` at `0x18003b785`
- `ADVAPI32!RegQueryValueExA` at `0x18003b7bb`
- `ADVAPI32!RegQueryValueExA` at `0x18003b7bb`
- `ADVAPI32!RegCloseKey` at `0x18003b821`
- `ADVAPI32!RegCloseKey` at `0x18003b821`

## string_xrefs

- `0x18003b731`: `Clsid`
- `0x18003b79d`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall OleCGetThreadModel(const char *a1)
{
  unsigned int v1; // ebx
  __int64 v2; // rax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  CHAR Data[32]; // [rsp+50h] [rbp-B0h] BYREF
  CHAR SubKey[256]; // [rsp+70h] [rbp-90h] BYREF

  cbData = 20;
  v1 = 255;
  wsprintfA(SubKey, "%s%s%s%s%s", szCLSID, szSep, a1, szSep, szInprocServer32);
  if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey) )
  {
    v1 = 0;
    if ( !RegQueryValueExA(hKey, szThreadingModel, 0, 0, (LPBYTE)Data, &cbData) )
    {
      v2 = cbData - 1;
      if ( (unsigned int)v2 >= 0x14 )
        _report_gsfailure(0);
      Data[v2] = 0;
      v1 = lstrcmpiA(Data, (LPCSTR)szApartmentModel) == 0;
      if ( !lstrcmpiA(Data, szFreeModel) || !lstrcmpiA(Data, szBothModel) )
        v1 = 1;
    }
    RegCloseKey(hKey);
  }
  return v1;
}

```

## disassembly

```asm
0x18003b6f8  mov     [rsp-8+arg_8], rbx
0x18003b6fd  mov     [rsp-8+arg_10], rdi
0x18003b702  push    rbp
0x18003b703  lea     rbp, [rsp-80h]
0x18003b708  mov     eax, 180h
0x18003b70d  call    _alloca_probe
0x18003b712  sub     rsp, rax
0x18003b715  mov     rax, cs:__security_cookie
0x18003b71c  xor     rax, rsp
0x18003b71f  mov     [rbp+80h+var_10], rax
0x18003b723  lea     rax, ?szInprocServer32@@3PADA; "InprocServer32"
0x18003b72a  lea     r9, ?szSep@@3PADA; "\\"
0x18003b731  lea     r8, ?szCLSID@@3PADA; "Clsid"
0x18003b738  mov     [rsp+180h+var_150], rax
0x18003b73d  mov     [rsp+180h+lpcbData], r9
0x18003b742  mov     [rsp+180h+phkResult], rcx
0x18003b747  lea     rcx, [rsp+180h+SubKey]; LPSTR
0x18003b74c  lea     rdx, aSSSSS; "%s%s%s%s%s"
0x18003b753  mov     [rsp+180h+cbData], 14h
0x18003b75b  mov     ebx, 0FFh
0x18003b760  call    cs:__imp_wsprintfA
0x18003b766  lea     r11, [rsp+180h+hKey]
0x18003b76b  lea     rdx, [rsp+180h+SubKey]; lpSubKey
0x18003b770  mov     r9d, 20019h; samDesired
0x18003b776  xor     r8d, r8d; ulOptions
0x18003b779  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18003b780  mov     [rsp+180h+phkResult], r11; phkResult
0x18003b785  call    cs:__imp_RegOpenKeyExA
0x18003b78b  test    eax, eax
0x18003b78d  jnz     loc_18003B827
0x18003b793  mov     rcx, [rsp+180h+hKey]; hKey
0x18003b798  lea     rax, [rsp+180h+cbData]
0x18003b79d  lea     rdx, ?szThreadingModel@@3PADA; "ThreadingModel"
0x18003b7a4  mov     [rsp+180h+lpcbData], rax; lpcbData
0x18003b7a9  lea     rax, [rsp+180h+Data]
0x18003b7ae  xor     r9d, r9d; lpType
0x18003b7b1  xor     r8d, r8d; lpReserved
0x18003b7b4  xor     ebx, ebx
0x18003b7b6  mov     [rsp+180h+phkResult], rax; lpData
0x18003b7bb  call    cs:__imp_RegQueryValueExA
0x18003b7c1  test    eax, eax
0x18003b7c3  jnz     short loc_18003B81C
0x18003b7c5  mov     eax, [rsp+180h+cbData]
0x18003b7c9  dec     eax
0x18003b7cb  cmp     eax, 14h
0x18003b7ce  jnb     short loc_18003B84A
0x18003b7d0  lea     rdx, ?szApartmentModel@@3PADA; "Apartment"
0x18003b7d7  lea     rcx, [rsp+180h+Data]; lpString1
0x18003b7dc  mov     [rsp+rax+180h+Data], bl
0x18003b7e0  call    cs:__imp_lstrcmpiA
0x18003b7e6  lea     edi, [rbx+1]
0x18003b7e9  lea     rdx, ?szFreeModel@@3PADA; "Free"
0x18003b7f0  test    eax, eax
0x18003b7f2  lea     rcx, [rsp+180h+Data]; lpString1
0x18003b7f7  cmovz   ebx, edi
0x18003b7fa  call    cs:__imp_lstrcmpiA
0x18003b800  test    eax, eax
0x18003b802  jz      short loc_18003B81A
0x18003b804  lea     rdx, ?szBothModel@@3PADA; "Both"
0x18003b80b  lea     rcx, [rsp+180h+Data]; lpString1
0x18003b810  call    cs:__imp_lstrcmpiA
0x18003b816  test    eax, eax
0x18003b818  jnz     short loc_18003B81C
0x18003b81a  mov     ebx, edi
0x18003b81c  mov     rcx, [rsp+180h+hKey]; hKey
0x18003b821  call    cs:__imp_RegCloseKey
0x18003b827  mov     eax, ebx
0x18003b829  mov     rcx, [rbp+80h+var_10]
0x18003b82d  xor     rcx, rsp; StackCookie
0x18003b830  call    __security_check_cookie
0x18003b835  lea     r11, [rsp+180h+var_s0]
0x18003b83d  mov     rbx, [r11+18h]
0x18003b841  mov     rdi, [r11+20h]
0x18003b845  mov     rsp, r11
0x18003b848  pop     rbp
0x18003b849  retn
0x18003b84a  xor     ecx, ecx; StackCookie
0x18003b84c  call    __report_gsfailure
```
