# IISCERTMAP_AUTH_PROVIDER::InitializeInstance(void)

- ea: `0x180002480`
- end: `0x180002578`
- name: `?InitializeInstance@IISCERTMAP_AUTH_PROVIDER@@QEAAJXZ`
- size: `248`
- prototype: `__int64 __fastcall(IISCERTMAP_AUTH_PROVIDER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180002f90`

## callees

- `0x180002480`
- `0x18000551c`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000255e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000255e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002521`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002521`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800024d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800024d3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002501`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002501`

## string_xrefs

- `0x1800024b0`: `System\CurrentControlSet\Services\inetinfo\Parameters`

## pseudocode

```c
signed int __fastcall IISCERTMAP_AUTH_PROVIDER::InitializeInstance(IISCERTMAP_AUTH_PROVIDER *this)
{
  void *v1; // rdi
  LSTATUS v2; // eax
  signed int result; // eax
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  int v5; // [rsp+54h] [rbp+24h]
  int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  v5 = HIDWORD(this);
  v1 = s_pIisCertmapAuthProvider;
  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\inetinfo\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    v2 = RegQueryValueExW(hKey, L"LastPriorityUPNLogon", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v2 && Type == 4 )
    {
      LOBYTE(v2) = Data != 0;
      *((_DWORD *)v1 + 645) = v2;
    }
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (int)IIS_LOGON_PROVIDER::GetDefaultDomainName((wchar_t *)v1 + 8) < 0 )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    *((_DWORD *)v1 + 646) = 1;
    (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v1 + 64LL))(v1, 128);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002480  mov     qword ptr [rsp-18h+Type], rcx
0x180002485  push    rbp
0x180002486  push    rbx
0x180002487  push    rdi
0x180002488  mov     rbp, rsp
0x18000248b  sub     rsp, 30h
0x18000248f  mov     rdi, cs:?s_pIisCertmapAuthProvider@@3PEAVIISCERTMAP_AUTH_PROVIDER@@EA; IISCERTMAP_AUTH_PROVIDER * s_pIisCertmapAuthProvider
0x180002496  lea     rax, [rbp+hKey]
0x18000249a  mov     r9d, 20019h; samDesired
0x1800024a0  mov     [rsp+30h+phkResult], rax; phkResult
0x1800024a5  xor     r8d, r8d; ulOptions
0x1800024a8  mov     [rbp+hKey], 0
0x1800024b0  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\in"...
0x1800024b7  mov     [rbp+Data], 0
0x1800024be  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800024c5  mov     [rbp+Type], 0
0x1800024cc  mov     [rbp+cbData], 4
0x1800024d3  call    cs:__imp_RegOpenKeyExW
0x1800024d9  test    eax, eax
0x1800024db  jnz     short loc_18000252F
0x1800024dd  mov     rcx, [rbp+hKey]; hKey
0x1800024e1  lea     rax, [rbp+cbData]
0x1800024e5  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800024ea  lea     r9, [rbp+Type]; lpType
0x1800024ee  lea     rax, [rbp+Data]
0x1800024f2  xor     r8d, r8d; lpReserved
0x1800024f5  lea     rdx, ValueName; "LastPriorityUPNLogon"
0x1800024fc  mov     [rsp+30h+phkResult], rax; lpData
0x180002501  call    cs:__imp_RegQueryValueExW
0x180002507  test    eax, eax
0x180002509  jnz     short loc_18000251D
0x18000250b  cmp     [rbp+Type], 4
0x18000250f  jnz     short loc_18000251D
0x180002511  cmp     [rbp+Data], eax
0x180002514  setnz   al
0x180002517  mov     [rdi+0A14h], eax
0x18000251d  mov     rcx, [rbp+hKey]; hKey
0x180002521  call    cs:__imp_RegCloseKey
0x180002527  mov     [rbp+hKey], 0
0x18000252f  lea     rcx, [rdi+10h]; Destination
0x180002533  call    ?GetDefaultDomainName@IIS_LOGON_PROVIDER@@AEAAJXZ; IIS_LOGON_PROVIDER::GetDefaultDomainName(void)
0x180002538  test    eax, eax
0x18000253a  js      short loc_18000255E
0x18000253c  mov     dword ptr [rdi+0A18h], 1
0x180002546  mov     edx, 80h
0x18000254b  mov     rax, [rdi]
0x18000254e  mov     rcx, rdi
0x180002551  mov     rax, [rax+40h]
0x180002555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000255a  xor     eax, eax
0x18000255c  jmp     short loc_180002570
0x18000255e  call    cs:__imp_GetLastError
0x180002564  test    eax, eax
0x180002566  jle     short loc_180002570
0x180002568  movzx   eax, ax
0x18000256b  or      eax, 80070000h
0x180002570  add     rsp, 30h
0x180002574  pop     rdi
0x180002575  pop     rbx
0x180002576  pop     rbp
0x180002577  retn
```
