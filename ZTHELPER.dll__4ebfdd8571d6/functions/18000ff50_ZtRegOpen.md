# ZtRegOpen

- ea: `0x18000ff50`
- end: `0x180010114`
- name: `ZtRegOpen`
- size: `452`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, HKEY *, HANDLE *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000376c`
- `0x1800049b0`

## callees

- `0x1800014b0`
- `0x18000f670`
- `0x18000ff50`
- `0x180015008`
- `0x180015040`

## import_xrefs

- `ntdll!NtCreateRegistryTransaction` at `0x18000ffe1`
- `ntdll!NtCreateRegistryTransaction` at `0x18000ffe1`
- `ntdll!RtlNtStatusToDosError` at `0x18000ffe9`
- `ntdll!RtlNtStatusToDosError` at `0x18000ffe9`
- `ntdll!NtClose` at `0x1800100eb`
- `ntdll!NtClose` at `0x1800100eb`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180010045`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180010045`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800100d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800100d4`

## string_xrefs

- `0x18000ffcc`: `Parameters\ZTDNS\ZTStagingConfig`
- `0x180010006`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x180010015`: `Dnscache`

## pseudocode

```c
__int64 __fastcall ZtRegOpen(unsigned int a1, __int64 a2, __int64 a3, HKEY *a4, HANDLE *a5)
{
  const wchar_t *v7; // r14
  NTSTATUS v8; // eax
  ULONG v9; // ebx
  int v10; // r9d
  ULONG PersistedRegistryKeyHelper; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  HKEY hKey; // [rsp+40h] [rbp-20h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-18h] BYREF

  Handle = 0;
  hKey = 0;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_dqq(1035, 10, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids, a1, a4, a5);
  if ( a1 > 1 )
  {
    v9 = 87;
    if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
      goto LABEL_17;
    v12 = 11;
    v13 = 87;
  }
  else
  {
    v7 = L"Parameters\\ZTDNS\\ZTStagingConfig";
    if ( a1 != 1 )
      v7 = L"Parameters\\ZTDNS";
    v8 = NtCreateRegistryTransaction(&Handle, 2031679, 0, 0);
    v9 = RtlNtStatusToDosError(v8);
    if ( v9 )
      goto LABEL_15;
    PersistedRegistryKeyHelper = CreatePersistedRegistryKeyHelper(
                                   (unsigned int)L"Dnscache",
                                   (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                   (_DWORD)v7,
                                   v10,
                                   458783,
                                   (__int64)Handle,
                                   1,
                                   (__int64)&hKey);
    v9 = PersistedRegistryKeyHelper;
    if ( !PersistedRegistryKeyHelper )
    {
      v9 = RegSetKeySecurity(hKey, 4u, (PSECURITY_DESCRIPTOR)&g_rgbZtdnsSecurityDescriptor);
      if ( !v9 )
      {
        *a4 = hKey;
        *a5 = Handle;
        hKey = 0;
        Handle = 0;
      }
      goto LABEL_15;
    }
    if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
      goto LABEL_17;
    v12 = 12;
    v13 = PersistedRegistryKeyHelper;
  }
  WPP_SF_d(1035, v12, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids, v13);
LABEL_15:
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 13, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids, v9);
LABEL_17:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( Handle )
    NtClose(Handle);
  return v9;
}

```

## disassembly

```asm
0x18000ff50  mov     r11, rsp
0x18000ff53  mov     [r11+10h], rbx
0x18000ff57  mov     [r11+18h], rsi
0x18000ff5b  push    rbp
0x18000ff5c  push    rdi
0x18000ff5d  push    r14
0x18000ff5f  mov     rbp, rsp
0x18000ff62  sub     rsp, 60h
0x18000ff66  mov     rax, cs:__security_cookie
0x18000ff6d  xor     rax, rsp
0x18000ff70  mov     [rbp+var_10], rax
0x18000ff74  mov     rsi, [rbp+arg_20]
0x18000ff78  mov     rdi, r9
0x18000ff7b  mov     ebx, ecx
0x18000ff7d  mov     [rbp+Handle], 0
0x18000ff85  mov     [rbp+hKey], 0
0x18000ff8d  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000ff94  jz      short loc_18000FFB7
0x18000ff96  mov     [r11-50h], rsi
0x18000ff9a  lea     r8, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids
0x18000ffa1  mov     [r11-58h], r9
0x18000ffa5  mov     edx, 0Ah
0x18000ffaa  mov     r9d, ebx
0x18000ffad  mov     ecx, 40Bh
0x18000ffb2  call    WPP_SF_dqq
0x18000ffb7  cmp     ebx, 1
0x18000ffba  ja      loc_180010084
0x18000ffc0  lea     rax, aParametersZtdn; "Parameters\\ZTDNS"
0x18000ffc7  mov     edx, 1F003Fh
0x18000ffcc  lea     r14, aParametersZtdn_0; "Parameters\\ZTDNS\\ZTStagingConfig"
0x18000ffd3  cmovnz  r14, rax
0x18000ffd7  lea     rcx, [rbp+Handle]
0x18000ffdb  xor     r9d, r9d
0x18000ffde  xor     r8d, r8d
0x18000ffe1  call    cs:__imp_NtCreateRegistryTransaction
0x18000ffe7  mov     ecx, eax; Status
0x18000ffe9  call    cs:__imp_RtlNtStatusToDosError
0x18000ffef  mov     ebx, eax
0x18000fff1  test    eax, eax
0x18000fff3  jnz     loc_1800100A9
0x18000fff9  mov     rax, [rbp+Handle]
0x18000fffd  lea     rcx, [rbp+hKey]
0x180010001  mov     [rsp+60h+var_28], rcx
0x180010006  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18001000d  mov     [rsp+60h+var_30], 1
0x180010015  lea     rcx, aDnscache; "Dnscache"
0x18001001c  mov     [rsp+60h+var_38], rax
0x180010021  mov     r8, r14
0x180010024  mov     [rsp+60h+var_40], 7001Fh
0x18001002c  call    CreatePersistedRegistryKeyHelper
0x180010031  mov     ebx, eax
0x180010033  test    eax, eax
0x180010035  jnz     short loc_180010071
0x180010037  mov     rcx, [rbp+hKey]; hKey
0x18001003b  lea     r8, ?g_rgbZtdnsSecurityDescriptor@@3QBEB; pSecurityDescriptor
0x180010042  lea     edx, [rax+4]; SecurityInformation
0x180010045  call    cs:__imp_RegSetKeySecurity
0x18001004b  mov     ebx, eax
0x18001004d  test    eax, eax
0x18001004f  jnz     short loc_1800100A9
0x180010051  mov     rax, [rbp+hKey]
0x180010055  mov     [rdi], rax
0x180010058  mov     rax, [rbp+Handle]
0x18001005c  mov     [rsi], rax
0x18001005f  mov     [rbp+hKey], 0
0x180010067  mov     [rbp+Handle], 0
0x18001006f  jmp     short loc_1800100A9
0x180010071  test    byte ptr cs:xmmword_18001F260+1, 8
0x180010078  jz      short loc_1800100CB
0x18001007a  mov     edx, 0Ch
0x18001007f  mov     r9d, eax
0x180010082  jmp     short loc_180010098
0x180010084  mov     ebx, 57h ; 'W'
0x180010089  test    byte ptr cs:xmmword_18001F260+1, 8
0x180010090  jz      short loc_1800100CB
0x180010092  lea     edx, [rbx-4Ch]
0x180010095  mov     r9d, ebx
0x180010098  lea     r8, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids
0x18001009f  mov     ecx, 40Bh
0x1800100a4  call    WPP_SF_d
0x1800100a9  test    byte ptr cs:xmmword_18001F260+1, 8
0x1800100b0  jz      short loc_1800100CB
0x1800100b2  mov     edx, 0Dh
0x1800100b7  lea     r8, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids
0x1800100be  mov     ecx, 40Bh
0x1800100c3  mov     r9d, ebx
0x1800100c6  call    WPP_SF_d
0x1800100cb  mov     rcx, [rbp+hKey]; hKey
0x1800100cf  test    rcx, rcx
0x1800100d2  jz      short loc_1800100E2
0x1800100d4  call    cs:__imp_RegCloseKey
0x1800100da  mov     [rbp+hKey], 0
0x1800100e2  mov     rcx, [rbp+Handle]; Handle
0x1800100e6  test    rcx, rcx
0x1800100e9  jz      short loc_1800100F1
0x1800100eb  call    cs:__imp_NtClose
0x1800100f1  mov     eax, ebx
0x1800100f3  mov     rcx, [rbp+var_10]
0x1800100f7  xor     rcx, rsp; StackCookie
0x1800100fa  call    __security_check_cookie
0x1800100ff  lea     r11, [rsp+60h+var_s0]
0x180010104  mov     rbx, [r11+28h]
0x180010108  mov     rsi, [r11+30h]
0x18001010c  mov     rsp, r11
0x18001010f  pop     r14
0x180010111  pop     rdi
0x180010112  pop     rbp
0x180010113  retn
```
