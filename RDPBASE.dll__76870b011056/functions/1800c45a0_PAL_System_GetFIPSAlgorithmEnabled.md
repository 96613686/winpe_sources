# PAL_System_GetFIPSAlgorithmEnabled

- ea: `0x1800c45a0`
- end: `0x1800c46e8`
- name: `PAL_System_GetFIPSAlgorithmEnabled`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180004a94`
- `0x1800c45a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c461c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c4687`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c461c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c4687`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4628`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4693`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4628`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4693`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c45e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4652`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c45e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4652`

## pseudocode

```c
__int64 PAL_System_GetFIPSAlgorithmEnabled()
{
  LSTATUS v0; // ebx
  int v1; // ecx
  int v2; // r8d
  int v3; // r9d
  LSTATUS v4; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  const char *v7; // [rsp+38h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF
  DWORD Type; // [rsp+70h] [rbp+28h] BYREF
  unsigned int v11; // [rsp+78h] [rbp+30h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 4;
  Type = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\LSA\\FipsAlgorithmPolicy",
         0,
         0x20019u,
         &hKey)
    || (cbData = 4, v0 = RegQueryValueExW(hKey, L"Enabled", 0, &Type, (LPBYTE)&Data, &cbData), RegCloseKey(hKey), v0) )
  {
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\LSA", 0, 0x20019u, &hKey)
      || (cbData = 4,
          v4 = RegQueryValueExW(hKey, L"FipsAlgorithmPolicy", 0, &Type, (LPBYTE)&Data, &cbData),
          RegCloseKey(hKey),
          v4) )
    {
      Data = 0;
    }
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v11 = Data;
    v7 = "GP setting for FIPS is %d";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v1,
      (unsigned int)&word_1801B83E6,
      v2,
      v3,
      (__int64)&v7,
      (__int64)&v11);
  }
  return Data;
}

```

## disassembly

```asm
0x1800c45a0  push    rbp
0x1800c45a2  push    rbx
0x1800c45a3  mov     rbp, rsp
0x1800c45a6  sub     rsp, 48h
0x1800c45aa  lea     rax, [rbp+hKey]
0x1800c45ae  mov     [rbp+hKey], 0
0x1800c45b6  mov     r9d, 20019h; samDesired
0x1800c45bc  mov     [rsp+48h+phkResult], rax; phkResult
0x1800c45c1  xor     r8d, r8d; ulOptions
0x1800c45c4  mov     [rbp+Data], 0
0x1800c45cb  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\LSA"...
0x1800c45d2  mov     [rbp+cbData], 4
0x1800c45d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c45e0  mov     [rbp+Type], 0
0x1800c45e7  call    cs:__imp_RegOpenKeyExW
0x1800c45ed  test    eax, eax
0x1800c45ef  jnz     short loc_1800C4632
0x1800c45f1  mov     rcx, [rbp+hKey]; hKey
0x1800c45f5  lea     rax, [rbp+cbData]
0x1800c45f9  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800c45fe  lea     r9, [rbp+Type]; lpType
0x1800c4602  lea     rax, [rbp+Data]
0x1800c4606  mov     [rbp+cbData], 4
0x1800c460d  xor     r8d, r8d; lpReserved
0x1800c4610  mov     [rsp+48h+phkResult], rax; lpData
0x1800c4615  lea     rdx, aEnabled; "Enabled"
0x1800c461c  call    cs:__imp_RegQueryValueExW
0x1800c4622  mov     rcx, [rbp+hKey]; hKey
0x1800c4626  mov     ebx, eax
0x1800c4628  call    cs:__imp_RegCloseKey
0x1800c462e  test    ebx, ebx
0x1800c4630  jz      short loc_1800C46A4
0x1800c4632  lea     rax, [rbp+hKey]
0x1800c4636  mov     r9d, 20019h; samDesired
0x1800c463c  xor     r8d, r8d; ulOptions
0x1800c463f  mov     [rsp+48h+phkResult], rax; phkResult
0x1800c4644  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\LSA"
0x1800c464b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c4652  call    cs:__imp_RegOpenKeyExW
0x1800c4658  test    eax, eax
0x1800c465a  jnz     short loc_1800C469D
0x1800c465c  mov     rcx, [rbp+hKey]; hKey
0x1800c4660  lea     rax, [rbp+cbData]
0x1800c4664  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800c4669  lea     r9, [rbp+Type]; lpType
0x1800c466d  lea     rax, [rbp+Data]
0x1800c4671  mov     [rbp+cbData], 4
0x1800c4678  xor     r8d, r8d; lpReserved
0x1800c467b  mov     [rsp+48h+phkResult], rax; lpData
0x1800c4680  lea     rdx, aFipsalgorithmp; "FipsAlgorithmPolicy"
0x1800c4687  call    cs:__imp_RegQueryValueExW
0x1800c468d  mov     rcx, [rbp+hKey]; hKey
0x1800c4691  mov     ebx, eax
0x1800c4693  call    cs:__imp_RegCloseKey
0x1800c4699  test    ebx, ebx
0x1800c469b  jz      short loc_1800C46A4
0x1800c469d  mov     [rbp+Data], 0
0x1800c46a4  mov     eax, cs:CallbackContext
0x1800c46aa  cmp     eax, 4
0x1800c46ad  jbe     short loc_1800C46DE
0x1800c46af  mov     eax, [rbp+Data]
0x1800c46b2  lea     rdx, word_1801B83E6
0x1800c46b9  mov     [rbp+arg_18], eax
0x1800c46bc  lea     rax, aGpSettingForFi; "GP setting for FIPS is %d"
0x1800c46c3  mov     [rbp+var_10], rax
0x1800c46c7  lea     rax, [rbp+arg_18]
0x1800c46cb  mov     [rsp+48h+lpcbData], rax
0x1800c46d0  lea     rax, [rbp+var_10]
0x1800c46d4  mov     [rsp+48h+phkResult], rax
0x1800c46d9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800c46de  mov     eax, [rbp+Data]
0x1800c46e1  add     rsp, 48h
0x1800c46e5  pop     rbx
0x1800c46e6  pop     rbp
0x1800c46e7  retn
```
