# BASIC_AUTH_PROVIDER::InitializeInstance(void)

- ea: `0x180002820`
- end: `0x180002904`
- name: `?InitializeInstance@BASIC_AUTH_PROVIDER@@QEAAJXZ`
- size: `228`
- prototype: `__int64 __fastcall(BASIC_AUTH_PROVIDER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180003530`

## callees

- `0x180002820`
- `0x18000428c`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800028a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800028a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002873`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002873`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800028c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800028c1`

## string_xrefs

- `0x180002850`: `System\CurrentControlSet\Services\inetinfo\Parameters`

## pseudocode

```c
__int64 __fastcall BASIC_AUTH_PROVIDER::InitializeInstance(BASIC_AUTH_PROVIDER *this)
{
  void *v1; // rdi
  LSTATUS v2; // eax
  __int64 result; // rax
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  int v5; // [rsp+54h] [rbp+24h]
  int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  v5 = HIDWORD(this);
  v1 = s_pBasicAuthProvider;
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
  result = IIS_LOGON_PROVIDER::GetDefaultDomainName((wchar_t *)v1 + 8);
  if ( (int)result >= 0 )
  {
    *((_DWORD *)v1 + 646) = 1;
    (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v1 + 64LL))(v1, 2);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002820  mov     qword ptr [rsp-18h+Type], rcx
0x180002825  push    rbp
0x180002826  push    rbx
0x180002827  push    rdi
0x180002828  mov     rbp, rsp
0x18000282b  sub     rsp, 30h
0x18000282f  mov     rdi, cs:?s_pBasicAuthProvider@@3PEAVBASIC_AUTH_PROVIDER@@EA; BASIC_AUTH_PROVIDER * s_pBasicAuthProvider
0x180002836  lea     rax, [rbp+hKey]
0x18000283a  mov     r9d, 20019h; samDesired
0x180002840  mov     [rsp+30h+phkResult], rax; phkResult
0x180002845  xor     r8d, r8d; ulOptions
0x180002848  mov     [rbp+hKey], 0
0x180002850  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\in"...
0x180002857  mov     [rbp+Data], 0
0x18000285e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002865  mov     [rbp+Type], 0
0x18000286c  mov     [rbp+cbData], 4
0x180002873  call    cs:__imp_RegOpenKeyExW
0x180002879  test    eax, eax
0x18000287b  jnz     short loc_1800028CF
0x18000287d  mov     rcx, [rbp+hKey]; hKey
0x180002881  lea     rax, [rbp+cbData]
0x180002885  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000288a  lea     r9, [rbp+Type]; lpType
0x18000288e  lea     rax, [rbp+Data]
0x180002892  xor     r8d, r8d; lpReserved
0x180002895  lea     rdx, ValueName; "LastPriorityUPNLogon"
0x18000289c  mov     [rsp+30h+phkResult], rax; lpData
0x1800028a1  call    cs:__imp_RegQueryValueExW
0x1800028a7  test    eax, eax
0x1800028a9  jnz     short loc_1800028BD
0x1800028ab  cmp     [rbp+Type], 4
0x1800028af  jnz     short loc_1800028BD
0x1800028b1  cmp     [rbp+Data], eax
0x1800028b4  setnz   al
0x1800028b7  mov     [rdi+0A14h], eax
0x1800028bd  mov     rcx, [rbp+hKey]; hKey
0x1800028c1  call    cs:__imp_RegCloseKey
0x1800028c7  mov     [rbp+hKey], 0
0x1800028cf  lea     rcx, [rdi+10h]; Destination
0x1800028d3  call    ?GetDefaultDomainName@IIS_LOGON_PROVIDER@@AEAAJXZ; IIS_LOGON_PROVIDER::GetDefaultDomainName(void)
0x1800028d8  test    eax, eax
0x1800028da  js      short loc_1800028FC
0x1800028dc  mov     dword ptr [rdi+0A18h], 1
0x1800028e6  mov     edx, 2
0x1800028eb  mov     rax, [rdi]
0x1800028ee  mov     rcx, rdi
0x1800028f1  mov     rax, [rax+40h]
0x1800028f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028fa  xor     eax, eax
0x1800028fc  add     rsp, 30h
0x180002900  pop     rdi
0x180002901  pop     rbx
0x180002902  pop     rbp
0x180002903  retn
```
