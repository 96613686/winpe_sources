# SetRegistryPathReadAccessForAllACsAndLPAC(HKEY__ *,ushort const *)

- ea: `0x1800208fc`
- end: `0x1800209f3`
- name: `?SetRegistryPathReadAccessForAllACsAndLPAC@@YAJPEAUHKEY__@@PEBG@Z`
- size: `247`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000bd80`

## callees

- `0x1800204ac`
- `0x180020730`
- `0x1800208fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002095c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002095c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800209c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800209c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800209cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800209cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002092f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002092f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800209b9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800209b9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180020952`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180020952`

## pseudocode

```c
__int64 __fastcall SetRegistryPathReadAccessForAllACsAndLPAC(HKEY a1, const unsigned __int16 *a2)
{
  int LastError; // ebx
  bool v3; // cc
  bool phkResult; // [rsp+20h] [rbp-10h]
  bool phkResulta; // [rsp+20h] [rbp-10h]
  HKEY hKey; // [rsp+40h] [rbp+10h] BYREF
  PSID pSid; // [rsp+50h] [rbp+20h] BYREF
  PSID Sid; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  LastError = RegOpenKeyExW(HKEY_CURRENT_USER, a2, 0, 0x60000u, &hKey);
  if ( LastError )
  {
    v3 = LastError < 0;
LABEL_11:
    if ( !v3 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)LastError;
  }
  Sid = 0;
  if ( ConvertStringSidToSidW(
         L"S-1-15-3-1024-1065365936-1281604716-3511738428-1654721687-432734479-3232135806-4053264122-3456934681",
         &Sid)
    || (LastError = GetLastError()) == 0 )
  {
    LastError = SetHandleAccessWithInheritance(hKey, SE_REGISTRY_KEY, Sid, 0x20019u, phkResult);
    if ( !LastError )
    {
      pSid = 0;
      LastError = CreateAllApplicationPackagesSID(&pSid);
      if ( !LastError )
      {
        LastError = SetHandleAccessWithInheritance(hKey, SE_REGISTRY_KEY, pSid, 0x20019u, phkResulta);
        FreeSid(pSid);
      }
    }
    LocalFree(Sid);
  }
  RegCloseKey(hKey);
  v3 = LastError <= 0;
  if ( LastError )
    goto LABEL_11;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800208fc  mov     [rsp-8+arg_8], rbx
0x180020901  mov     [rsp-8+hKey], rcx
0x180020906  push    rbp
0x180020907  mov     rbp, rsp
0x18002090a  sub     rsp, 30h
0x18002090e  lea     rax, [rbp+hKey]
0x180020912  mov     [rbp+hKey], 0
0x18002091a  mov     r9d, 60000h; samDesired
0x180020920  mov     qword ptr [rsp+30h+phkResult], rax; bool
0x180020925  xor     r8d, r8d; ulOptions
0x180020928  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002092f  call    cs:__imp_RegOpenKeyExW
0x180020935  mov     ebx, eax
0x180020937  test    eax, eax
0x180020939  jnz     loc_1800209D9
0x18002093f  lea     rdx, [rbp+Sid]; Sid
0x180020943  mov     [rbp+Sid], 0
0x18002094b  lea     rcx, StringSid; "S-1-15-3-1024-1065365936-1281604716-351"...
0x180020952  call    cs:__imp_ConvertStringSidToSidW
0x180020958  test    eax, eax
0x18002095a  jnz     short loc_180020968
0x18002095c  call    cs:__imp_GetLastError
0x180020962  mov     ebx, eax
0x180020964  test    eax, eax
0x180020966  jnz     short loc_1800209C9
0x180020968  mov     r8, [rbp+Sid]; void *
0x18002096c  mov     r9d, 20019h; unsigned int
0x180020972  mov     rcx, [rbp+hKey]; handle
0x180020976  mov     edx, 4; ObjectType
0x18002097b  call    SetHandleAccessWithInheritance
0x180020980  mov     ebx, eax
0x180020982  test    eax, eax
0x180020984  jnz     short loc_1800209BF
0x180020986  lea     rcx, [rbp+pSid]; pSid
0x18002098a  mov     [rbp+pSid], 0
0x180020992  call    ?CreateAllApplicationPackagesSID@@YAKPEAPEAX@Z; CreateAllApplicationPackagesSID(void * *)
0x180020997  mov     ebx, eax
0x180020999  test    eax, eax
0x18002099b  jnz     short loc_1800209BF
0x18002099d  mov     r8, [rbp+pSid]; void *
0x1800209a1  lea     edx, [rax+4]; ObjectType
0x1800209a4  mov     rcx, [rbp+hKey]; handle
0x1800209a8  mov     r9d, 20019h; unsigned int
0x1800209ae  call    SetHandleAccessWithInheritance
0x1800209b3  mov     rcx, [rbp+pSid]; pSid
0x1800209b7  mov     ebx, eax
0x1800209b9  call    cs:__imp_FreeSid
0x1800209bf  mov     rcx, [rbp+Sid]; hMem
0x1800209c3  call    cs:__imp_LocalFree
0x1800209c9  mov     rcx, [rbp+hKey]; hKey
0x1800209cd  call    cs:__imp_RegCloseKey
0x1800209d3  test    ebx, ebx
0x1800209d5  jnz     short loc_1800209DB
0x1800209d7  jmp     short loc_1800209E6
0x1800209d9  test    ebx, ebx
0x1800209db  jle     short loc_1800209E6
0x1800209dd  movzx   ebx, bx
0x1800209e0  or      ebx, 80070000h
0x1800209e6  mov     eax, ebx
0x1800209e8  mov     rbx, [rsp+30h+arg_8]
0x1800209ed  add     rsp, 30h
0x1800209f1  pop     rbp
0x1800209f2  retn
```
