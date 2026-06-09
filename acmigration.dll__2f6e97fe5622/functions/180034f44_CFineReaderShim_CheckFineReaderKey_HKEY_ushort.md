# CFineReaderShim::CheckFineReaderKey(HKEY__ *,ushort *)

- ea: `0x180034f44`
- end: `0x180035192`
- name: `?CheckFineReaderKey@CFineReaderShim@@AEAAHPEAUHKEY__@@PEAG@Z`
- size: `590`
- prototype: `int(CFineReaderShim *__hidden this, HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180035214`

## callees

- `0x180001cf0`
- `0x180034f44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035070`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003508b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800350a6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003513a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035070`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003508b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800350a6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003513a`
- `ADVAPI32!RegQueryValueExW` at `0x180034fe6`
- `ADVAPI32!RegQueryValueExW` at `0x180035124`
- `ADVAPI32!RegQueryValueExW` at `0x180034fe6`
- `ADVAPI32!RegQueryValueExW` at `0x180035124`
- `ADVAPI32!RegCloseKey` at `0x180035150`
- `ADVAPI32!RegCloseKey` at `0x180035160`
- `ADVAPI32!RegCloseKey` at `0x180035150`
- `ADVAPI32!RegCloseKey` at `0x180035160`
- `ADVAPI32!RegEnumKeyExW` at `0x18003505a`
- `ADVAPI32!RegEnumKeyExW` at `0x18003505a`
- `ADVAPI32!RegOpenKeyExW` at `0x180034fad`
- `ADVAPI32!RegOpenKeyExW` at `0x1800350ef`
- `ADVAPI32!RegOpenKeyExW` at `0x180034fad`
- `ADVAPI32!RegOpenKeyExW` at `0x1800350ef`

## string_xrefs

- `0x180035133`: `ole32.dll`

## pseudocode

```c
__int64 __fastcall CFineReaderShim::CheckFineReaderKey(CFineReaderShim *this, HKEY a2, unsigned __int16 *a3)
{
  unsigned int v3; // edi
  __int64 v4; // rax
  int v5; // r14d
  int v6; // esi
  int v7; // r15d
  DWORD i; // ebx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Data[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  phkResult = 0;
  Type = 0;
  cbData = 0;
  v3 = 0;
  if ( !RegOpenKeyExW(a2, a3, 0, 0x20019u, &hKey) )
  {
    cbData = 520;
    if ( !RegQueryValueExW(hKey, 0, 0, &Type, (LPBYTE)Data, &cbData) && Type == 1 )
    {
      v4 = -1;
      do
        ++v4;
      while ( Data[v4] );
      if ( v4 == 38 )
      {
        v5 = 0;
        v6 = 0;
        v7 = 0;
        for ( i = 0; i < 3; ++i )
        {
          cbData = 259;
          if ( RegEnumKeyExW(hKey, i, Data, &cbData, 0, 0, 0, 0) )
            break;
          if ( (unsigned int)_o__wcsicmp(L"Implemented Categories", Data) )
          {
            if ( (unsigned int)_o__wcsicmp(L"InProcServer32", Data) )
            {
              if ( !(unsigned int)_o__wcsicmp(L"Version", Data) )
                v6 = 1;
            }
            else
            {
              v7 = 1;
            }
          }
          else
          {
            v5 = 1;
          }
        }
        if ( v6 )
        {
          if ( v7 )
          {
            if ( v5 )
            {
              if ( !RegOpenKeyExW(hKey, L"InProcServer32", 0, 0x20019u, &phkResult) )
              {
                cbData = 520;
                if ( !RegQueryValueExW(phkResult, 0, 0, &Type, (LPBYTE)Data, &cbData)
                  && !(unsigned int)_o__wcsicmp(L"ole32.dll", Data) )
                {
                  v3 = 1;
                }
              }
            }
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v3;
}

```

## disassembly

```asm
0x180034f44  mov     [rsp-8+arg_0], rbx
0x180034f49  push    rbp
0x180034f4a  push    rsi
0x180034f4b  push    rdi
0x180034f4c  push    r12
0x180034f4e  push    r13
0x180034f50  push    r14
0x180034f52  push    r15
0x180034f54  lea     rbp, [rsp-180h]
0x180034f5c  sub     rsp, 280h
0x180034f63  mov     rax, cs:__security_cookie
0x180034f6a  xor     rax, rsp
0x180034f6d  mov     [rbp+1B0h+var_40], rax
0x180034f74  xor     r12d, r12d
0x180034f77  lea     rcx, [rsp+2B0h+hKey]
0x180034f7c  mov     r10, r8
0x180034f7f  mov     [rsp+2B0h+phkResult], rcx; phkResult
0x180034f84  mov     rax, rdx
0x180034f87  mov     [rsp+2B0h+hKey], r12
0x180034f8c  mov     rcx, rax; hKey
0x180034f8f  mov     [rsp+2B0h+var_260], r12
0x180034f94  mov     r9d, 20019h; samDesired
0x180034f9a  mov     [rsp+2B0h+Type], r12d
0x180034f9f  xor     r8d, r8d; ulOptions
0x180034fa2  mov     [rsp+2B0h+cbData], r12d
0x180034fa7  mov     rdx, r10; lpSubKey
0x180034faa  mov     edi, r12d
0x180034fad  call    cs:__imp_RegOpenKeyExW
0x180034fb3  test    eax, eax
0x180034fb5  jnz     loc_180035146
0x180034fbb  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180034fc0  lea     rax, [rsp+2B0h+cbData]
0x180034fc5  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x180034fca  lea     r9, [rsp+2B0h+Type]; lpType
0x180034fcf  lea     rax, [rsp+2B0h+Data]
0x180034fd4  mov     [rsp+2B0h+cbData], 208h
0x180034fdc  xor     r8d, r8d; lpReserved
0x180034fdf  mov     [rsp+2B0h+phkResult], rax; lpData
0x180034fe4  xor     edx, edx; lpValueName
0x180034fe6  call    cs:__imp_RegQueryValueExW
0x180034fec  test    eax, eax
0x180034fee  jnz     loc_180035146
0x180034ff4  lea     r13d, [r12+1]
0x180034ff9  cmp     [rsp+2B0h+Type], r13d
0x180034ffe  jnz     loc_180035146
0x180035004  lea     rcx, [rsp+2B0h+Data]
0x180035009  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003500d  inc     rax
0x180035010  cmp     [rcx+rax*2], r12w
0x180035015  jnz     short loc_18003500D
0x180035017  cmp     rax, 26h ; '&'
0x18003501b  jnz     loc_180035146
0x180035021  mov     r14d, r12d
0x180035024  mov     esi, r12d
0x180035027  mov     r15d, r12d
0x18003502a  mov     ebx, r12d
0x18003502d  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180035032  lea     r9, [rsp+2B0h+cbData]; lpcchName
0x180035037  mov     [rsp+2B0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18003503c  lea     r8, [rsp+2B0h+Data]; lpName
0x180035041  mov     [rsp+2B0h+lpcchClass], r12; lpcchClass
0x180035046  mov     edx, ebx; dwIndex
0x180035048  mov     [rsp+2B0h+lpcbData], r12; lpClass
0x18003504d  mov     [rsp+2B0h+phkResult], r12; lpReserved
0x180035052  mov     [rsp+2B0h+cbData], 103h
0x18003505a  call    cs:__imp_RegEnumKeyExW
0x180035060  test    eax, eax
0x180035062  jnz     short loc_1800350BE
0x180035064  lea     rdx, [rsp+2B0h+Data]
0x180035069  lea     rcx, aImplementedCat; "Implemented Categories"
0x180035070  call    cs:__imp__o__wcsicmp
0x180035076  test    eax, eax
0x180035078  jnz     short loc_18003507F
0x18003507a  mov     r14d, r13d
0x18003507d  jmp     short loc_1800350B2
0x18003507f  lea     rdx, [rsp+2B0h+Data]
0x180035084  lea     rcx, aInprocserver32; "InProcServer32"
0x18003508b  call    cs:__imp__o__wcsicmp
0x180035091  test    eax, eax
0x180035093  jnz     short loc_18003509A
0x180035095  mov     r15d, r13d
0x180035098  jmp     short loc_1800350B2
0x18003509a  lea     rdx, [rsp+2B0h+Data]
0x18003509f  lea     rcx, aVersion_0; "Version"
0x1800350a6  call    cs:__imp__o__wcsicmp
0x1800350ac  test    eax, eax
0x1800350ae  cmovz   esi, r13d
0x1800350b2  add     ebx, r13d
0x1800350b5  cmp     ebx, 3
0x1800350b8  jb      loc_18003502D
0x1800350be  test    esi, esi
0x1800350c0  jz      loc_180035146
0x1800350c6  test    r15d, r15d
0x1800350c9  jz      short loc_180035146
0x1800350cb  test    r14d, r14d
0x1800350ce  jz      short loc_180035146
0x1800350d0  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800350d5  lea     rax, [rsp+2B0h+var_260]
0x1800350da  mov     r9d, 20019h; samDesired
0x1800350e0  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1800350e5  xor     r8d, r8d; ulOptions
0x1800350e8  lea     rdx, aInprocserver32; "InProcServer32"
0x1800350ef  call    cs:__imp_RegOpenKeyExW
0x1800350f5  test    eax, eax
0x1800350f7  jnz     short loc_180035146
0x1800350f9  mov     rcx, [rsp+2B0h+var_260]; hKey
0x1800350fe  lea     rax, [rsp+2B0h+cbData]
0x180035103  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x180035108  lea     r9, [rsp+2B0h+Type]; lpType
0x18003510d  lea     rax, [rsp+2B0h+Data]
0x180035112  mov     [rsp+2B0h+cbData], 208h
0x18003511a  xor     r8d, r8d; lpReserved
0x18003511d  mov     [rsp+2B0h+phkResult], rax; lpData
0x180035122  xor     edx, edx; lpValueName
0x180035124  call    cs:__imp_RegQueryValueExW
0x18003512a  test    eax, eax
0x18003512c  jnz     short loc_180035146
0x18003512e  lea     rdx, [rsp+2B0h+Data]
0x180035133  lea     rcx, aOle32Dll_0; "ole32.dll"
0x18003513a  call    cs:__imp__o__wcsicmp
0x180035140  test    eax, eax
0x180035142  cmovz   edi, r13d
0x180035146  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003514b  test    rcx, rcx
0x18003514e  jz      short loc_180035156
0x180035150  call    cs:__imp_RegCloseKey
0x180035156  mov     rcx, [rsp+2B0h+var_260]; hKey
0x18003515b  test    rcx, rcx
0x18003515e  jz      short loc_180035166
0x180035160  call    cs:__imp_RegCloseKey
0x180035166  mov     eax, edi
0x180035168  mov     rcx, [rbp+1B0h+var_40]
0x18003516f  xor     rcx, rsp; StackCookie
0x180035172  call    __security_check_cookie
0x180035177  mov     rbx, [rsp+2B0h+arg_0]
0x18003517f  add     rsp, 280h
0x180035186  pop     r15
0x180035188  pop     r14
0x18003518a  pop     r13
0x18003518c  pop     r12
0x18003518e  pop     rdi
0x18003518f  pop     rsi
0x180035190  pop     rbp
0x180035191  retn
```
