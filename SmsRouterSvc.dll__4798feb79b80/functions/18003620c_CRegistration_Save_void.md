# CRegistration::Save(void)

- ea: `0x18003620c`
- end: `0x180036649`
- name: `?Save@CRegistration@@QEAAJXZ`
- size: `1085`
- prototype: `__int64 __fastcall(void (__fastcall ***lpSubKey)(_QWORD))`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180010a28`

## callees

- `0x18003620c`
- `0x180051420`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800363d3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800363fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036420`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036444`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003646b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800364ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800364e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003651c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036556`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036583`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800365aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800365d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036603`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800363d3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800363fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036420`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036444`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003646b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800364ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800364e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003651c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036556`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036583`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800365aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800365d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036603`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003632e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003632e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003638c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036612`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036621`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003638c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036612`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036621`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180036273`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180036273`

## string_xrefs

- `0x1800362a3`: `RegCreateKey Key: %S`
- `0x180036362`: `RegCreateKey RegistrationId: %S`
- `0x1800364a4`: `FilterXML`
- `0x18003654c`: `UserSid`
- `0x1800365a0`: `LastAccessedMessageId`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CRegistration::Save(void (__fastcall ***lpSubKey)(_QWORD))
{
  void (__fastcall ***v1)(_QWORD); // rsi
  LPCWSTR v2; // r14
  LSTATUS v3; // eax
  int v4; // ebx
  unsigned int v5; // r8d
  HKEY v7; // rdi
  const WCHAR *v8; // rdx
  unsigned int v9; // r8d
  HKEY v10; // rbx
  const BYTE *v11; // rax
  const BYTE *v12; // rax
  const BYTE *v13; // rax
  const BYTE *v14; // rax
  DWORD dwDisposition; // [rsp+A0h] [rbp+40h] BYREF
  HKEY phkResult; // [rsp+A8h] [rbp+48h] BYREF
  HKEY v17; // [rsp+B0h] [rbp+50h]
  __int64 v18; // [rsp+B8h] [rbp+58h]

  v1 = lpSubKey;
  v2 = (LPCWSTR)(lpSubKey + 38);
  (*lpSubKey[38])(lpSubKey + 38);
  v17 = 0;
  v18 = 0;
  phkResult = 0;
  v3 = RegCreateKeyW(g_SmsRouterKey, L"Registration\\Ids", &phkResult);
  v4 = v3;
  dwDisposition = 0;
  if ( v3 )
  {
    if ( v3 > 0 )
      v5 = (unsigned __int16)v3 | 0x80070000;
    else
      v5 = v3;
    LogSmsRouterError("CRegistration::Save", 0x29Fu, v5, "RegCreateKey Key: %S", L"Registration\\Ids");
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
LABEL_7:
    (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v2 + 8LL))(v2);
    return (unsigned int)v4;
  }
  v7 = phkResult;
  v17 = phkResult;
  phkResult = 0;
  if ( (unsigned __int64)v1[3] <= 7 )
    v8 = (const WCHAR *)v1;
  else
    v8 = (const WCHAR *)*v1;
  v4 = RegCreateKeyExW(v7, v8, 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
  if ( v4 )
  {
    if ( (unsigned __int64)v1[3] > 7 )
      v1 = (void (__fastcall ***)(_QWORD))*v1;
    if ( v4 > 0 )
      v9 = (unsigned __int16)v4 | 0x80070000;
    else
      v9 = v4;
    LogSmsRouterError("CRegistration::Save", 0x2ABu, v9, "RegCreateKey RegistrationId: %S", (const wchar_t *)v1);
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    if ( v7 )
      RegCloseKey(v7);
    goto LABEL_7;
  }
  v10 = phkResult;
  RegSetValueExW(phkResult, L"Priority", 0, 4u, (const BYTE *)v1 + 220, 4u);
  RegSetValueExW(v10, L"CreationTime", 0, 0xBu, (const BYTE *)v1 + 40, 8u);
  RegSetValueExW(v10, L"Transient", 0, 4u, (const BYTE *)v1 + 32, 4u);
  RegSetValueExW(v10, L"IsPackaged", 0, 4u, (const BYTE *)v1 + 36, 4u);
  RegSetValueExW(v10, L"DeliveryType", 0, 4u, (const BYTE *)v1 + 236, 4u);
  v11 = (const BYTE *)(v1 + 18);
  if ( (unsigned __int64)v1[21] > 7 )
    v11 = *(const BYTE **)v11;
  RegSetValueExW(v10, L"FilterXML", 0, 1u, v11, 2 * *((_DWORD *)v1 + 40) + 2);
  v12 = (const BYTE *)(v1 + 6);
  if ( (unsigned __int64)v1[9] > 7 )
    v12 = *(const BYTE **)v12;
  RegSetValueExW(v10, L"RegistrationName", 0, 1u, v12, 2 * *((_DWORD *)v1 + 16) + 2);
  v13 = (const BYTE *)(v1 + 10);
  if ( (unsigned __int64)v1[13] > 7 )
    v13 = *(const BYTE **)v13;
  RegSetValueExW(v10, L"ApplicationName", 0, 1u, v13, 2 * *((_DWORD *)v1 + 24) + 2);
  v14 = (const BYTE *)(v1 + 14);
  if ( (unsigned __int64)v1[17] > 7 )
    v14 = *(const BYTE **)v14;
  RegSetValueExW(v10, L"UserSid", 0, 1u, v14, 2 * *((_DWORD *)v1 + 32) + 2);
  RegSetValueExW(v10, L"LastNotifiedMessageId", 0, 0xBu, (const BYTE *)v1 + 264, 8u);
  RegSetValueExW(v10, L"LastAccessedMessageId", 0, 0xBu, (const BYTE *)v1 + 288, 8u);
  RegSetValueExW(v10, L"NotifyCount", 0, 4u, (const BYTE *)v1 + 272, 4u);
  if ( *((_DWORD *)v1 + 54) )
    RegSetValueExW(v10, L"MessageAvailableEventName", 0, 3u, (const BYTE *)v1 + 208, 8u);
  if ( v10 )
    RegCloseKey(v10);
  if ( v7 )
    RegCloseKey(v7);
  (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v2 + 8LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x18003620c  push    rbp
0x18003620e  push    rbx
0x18003620f  push    rsi
0x180036210  push    rdi
0x180036211  push    r12
0x180036213  push    r14
0x180036215  push    r15
0x180036217  mov     rbp, rsp
0x18003621a  sub     rsp, 60h
0x18003621e  mov     rsi, rcx
0x180036221  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180036228  mov     [rbp+var_10], rax
0x18003622c  lea     r14, [rcx+130h]
0x180036233  mov     [rbp+var_8], r14
0x180036237  mov     rax, [r14]
0x18003623a  mov     rcx, r14
0x18003623d  mov     rax, [rax]
0x180036240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036245  nop
0x180036246  mov     [rbp+arg_10], 0
0x18003624e  mov     [rbp+arg_18], 0
0x180036256  mov     [rbp+phkResult], 0
0x18003625e  lea     r8, [rbp+phkResult]; phkResult
0x180036262  lea     r12, aRegistrationId; "Registration\\Ids"
0x180036269  mov     rdx, r12; lpSubKey
0x18003626c  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x180036273  call    cs:__imp_RegCreateKeyW
0x180036279  mov     ebx, eax
0x18003627b  mov     [rbp+dwDisposition], 0
0x180036282  test    eax, eax
0x180036284  jz      short loc_1800362DB
0x180036286  movzx   edi, bx
0x180036289  mov     r15d, 80070000h
0x18003628f  test    eax, eax
0x180036291  jg      short loc_180036298
0x180036293  mov     r8d, eax
0x180036296  jmp     short loc_18003629E
0x180036298  mov     r8d, edi
0x18003629b  or      r8d, r15d; int
0x18003629e  mov     qword ptr [rsp+60h+dwOptions], r12
0x1800362a3  lea     r9, aRegcreatekeyKe; "RegCreateKey Key: %S"
0x1800362aa  mov     edx, 29Fh; unsigned int
0x1800362af  lea     rcx, aCregistrationS; "CRegistration::Save"
0x1800362b6  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800362bb  test    ebx, ebx
0x1800362bd  jle     short loc_1800362C4
0x1800362bf  mov     ebx, edi
0x1800362c1  or      ebx, r15d
0x1800362c4  mov     rdx, [r14]
0x1800362c7  mov     rcx, r14
0x1800362ca  mov     rax, [rdx+8]
0x1800362ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362d3  nop
0x1800362d4  mov     eax, ebx
0x1800362d6  jmp     loc_18003663A
0x1800362db  mov     rdi, [rbp+phkResult]
0x1800362df  mov     [rbp+arg_10], rdi
0x1800362e3  mov     [rbp+phkResult], 0
0x1800362eb  cmp     qword ptr [rsi+18h], 7
0x1800362f0  jbe     short loc_1800362F7
0x1800362f2  mov     rdx, [rsi]
0x1800362f5  jmp     short loc_1800362FA
0x1800362f7  mov     rdx, rsi; lpSubKey
0x1800362fa  lea     rax, [rbp+dwDisposition]
0x1800362fe  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180036303  lea     rax, [rbp+phkResult]
0x180036307  mov     [rsp+60h+var_28], rax; phkResult
0x18003630c  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180036315  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18003631d  mov     [rsp+60h+dwOptions], 0; dwOptions
0x180036325  xor     r9d, r9d; lpClass
0x180036328  xor     r8d, r8d; Reserved
0x18003632b  mov     rcx, rdi; hKey
0x18003632e  call    cs:__imp_RegCreateKeyExW
0x180036334  mov     ebx, eax
0x180036336  test    eax, eax
0x180036338  jz      short loc_1800363A8
0x18003633a  cmp     qword ptr [rsi+18h], 7
0x18003633f  jbe     short loc_180036344
0x180036341  mov     rsi, [rsi]
0x180036344  movzx   r12d, bx
0x180036348  mov     r15d, 80070000h
0x18003634e  test    ebx, ebx
0x180036350  jg      short loc_180036357
0x180036352  mov     r8d, ebx
0x180036355  jmp     short loc_18003635D
0x180036357  mov     r8d, r12d
0x18003635a  or      r8d, r15d; int
0x18003635d  mov     qword ptr [rsp+60h+dwOptions], rsi
0x180036362  lea     r9, aRegcreatekeyRe; "RegCreateKey RegistrationId: %S"
0x180036369  mov     edx, 2ABh; unsigned int
0x18003636e  lea     rcx, aCregistrationS; "CRegistration::Save"
0x180036375  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003637a  test    ebx, ebx
0x18003637c  jle     short loc_180036384
0x18003637e  mov     ebx, r12d
0x180036381  or      ebx, r15d
0x180036384  test    rdi, rdi
0x180036387  jz      short loc_180036393
0x180036389  mov     rcx, rdi; hKey
0x18003638c  call    cs:__imp_RegCloseKey
0x180036392  nop
0x180036393  mov     rcx, [r14]
0x180036396  mov     rax, [rcx+8]
0x18003639a  mov     rcx, r14
0x18003639d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363a2  nop
0x1800363a3  jmp     loc_1800362D4
0x1800363a8  mov     rbx, [rbp+phkResult]
0x1800363ac  lea     rax, [rsi+0DCh]
0x1800363b3  mov     r15d, 4
0x1800363b9  mov     [rsp+60h+samDesired], r15d; cbData
0x1800363be  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800363c3  mov     r9d, r15d; dwType
0x1800363c6  xor     r8d, r8d; Reserved
0x1800363c9  lea     rdx, aPriority; "Priority"
0x1800363d0  mov     rcx, rbx; hKey
0x1800363d3  call    cs:__imp_RegSetValueExW
0x1800363d9  lea     rax, [rsi+28h]
0x1800363dd  lea     r12d, [r15+4]
0x1800363e1  mov     [rsp+60h+samDesired], r12d; cbData
0x1800363e6  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800363eb  lea     r9d, [r15+7]; dwType
0x1800363ef  xor     r8d, r8d; Reserved
0x1800363f2  lea     rdx, aCreationtime; "CreationTime"
0x1800363f9  mov     rcx, rbx; hKey
0x1800363fc  call    cs:__imp_RegSetValueExW
0x180036402  lea     rax, [rsi+20h]
0x180036406  mov     [rsp+60h+samDesired], r15d; cbData
0x18003640b  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180036410  mov     r9d, r15d; dwType
0x180036413  xor     r8d, r8d; Reserved
0x180036416  lea     rdx, aTransient; "Transient"
0x18003641d  mov     rcx, rbx; hKey
0x180036420  call    cs:__imp_RegSetValueExW
0x180036426  lea     rax, [rsi+24h]
0x18003642a  mov     [rsp+60h+samDesired], r15d; cbData
0x18003642f  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180036434  mov     r9d, r15d; dwType
0x180036437  xor     r8d, r8d; Reserved
0x18003643a  lea     rdx, aIspackaged; "IsPackaged"
0x180036441  mov     rcx, rbx; hKey
0x180036444  call    cs:__imp_RegSetValueExW
0x18003644a  lea     rax, [rsi+0ECh]
0x180036451  mov     [rsp+60h+samDesired], r15d; cbData
0x180036456  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18003645b  mov     r9d, r15d; dwType
0x18003645e  xor     r8d, r8d; Reserved
0x180036461  lea     rdx, aDeliverytype; "DeliveryType"
0x180036468  mov     rcx, rbx; hKey
0x18003646b  call    cs:__imp_RegSetValueExW
0x180036471  mov     eax, [rsi+0A0h]
0x180036477  lea     ecx, ds:2[rax*2]
0x18003647e  lea     rax, [rsi+90h]
0x180036485  cmp     qword ptr [rax+18h], 7
0x18003648a  jbe     short loc_18003648F
0x18003648c  mov     rax, [rax]
0x18003648f  mov     [rsp+60h+samDesired], ecx; cbData
0x180036493  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180036498  mov     r15d, 1
0x18003649e  mov     r9d, r15d; dwType
0x1800364a1  xor     r8d, r8d; Reserved
0x1800364a4  lea     rdx, aFilterxml; "FilterXML"
0x1800364ab  mov     rcx, rbx; hKey
0x1800364ae  call    cs:__imp_RegSetValueExW
0x1800364b4  mov     eax, [rsi+40h]
0x1800364b7  lea     ecx, ds:2[rax*2]
0x1800364be  lea     rax, [rsi+30h]
0x1800364c2  cmp     qword ptr [rax+18h], 7
0x1800364c7  jbe     short loc_1800364CC
0x1800364c9  mov     rax, [rax]
0x1800364cc  mov     [rsp+60h+samDesired], ecx; cbData
0x1800364d0  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800364d5  mov     r9d, r15d; dwType
0x1800364d8  xor     r8d, r8d; Reserved
0x1800364db  lea     rdx, aRegistrationna; "RegistrationName"
0x1800364e2  mov     rcx, rbx; hKey
0x1800364e5  call    cs:__imp_RegSetValueExW
0x1800364eb  mov     eax, [rsi+60h]
0x1800364ee  lea     ecx, ds:2[rax*2]
0x1800364f5  lea     rax, [rsi+50h]
0x1800364f9  cmp     qword ptr [rax+18h], 7
0x1800364fe  jbe     short loc_180036503
0x180036500  mov     rax, [rax]
0x180036503  mov     [rsp+60h+samDesired], ecx; cbData
0x180036507  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18003650c  mov     r9d, r15d; dwType
0x18003650f  xor     r8d, r8d; Reserved
0x180036512  lea     rdx, aApplicationnam; "ApplicationName"
0x180036519  mov     rcx, rbx; hKey
0x18003651c  call    cs:__imp_RegSetValueExW
0x180036522  mov     eax, [rsi+80h]
0x180036528  lea     ecx, ds:2[rax*2]
0x18003652f  lea     rax, [rsi+70h]
0x180036533  cmp     qword ptr [rax+18h], 7
0x180036538  jbe     short loc_18003653D
0x18003653a  mov     rax, [rax]
0x18003653d  mov     [rsp+60h+samDesired], ecx; cbData
0x180036541  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180036546  mov     r9d, r15d; dwType
0x180036549  xor     r8d, r8d; Reserved
0x18003654c  lea     rdx, aUsersid; "UserSid"
0x180036553  mov     rcx, rbx; hKey
0x180036556  call    cs:__imp_RegSetValueExW
0x18003655c  lea     rax, [rsi+108h]
0x180036563  mov     [rsp+60h+samDesired], r12d; cbData
0x180036568  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18003656d  mov     r15d, 0Bh
0x180036573  mov     r9d, r15d; dwType
0x180036576  xor     r8d, r8d; Reserved
0x180036579  lea     rdx, aLastnotifiedme; "LastNotifiedMessageId"
0x180036580  mov     rcx, rbx; hKey
0x180036583  call    cs:__imp_RegSetValueExW
0x180036589  lea     rax, [rsi+120h]
0x180036590  mov     [rsp+60h+samDesired], r12d; cbData
0x180036595  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18003659a  mov     r9d, r15d; dwType
0x18003659d  xor     r8d, r8d; Reserved
0x1800365a0  lea     rdx, aLastaccessedme; "LastAccessedMessageId"
0x1800365a7  mov     rcx, rbx; hKey
0x1800365aa  call    cs:__imp_RegSetValueExW
0x1800365b0  lea     rax, [rsi+110h]
0x1800365b7  lea     r9d, [r15-7]; dwType
0x1800365bb  mov     [rsp+60h+samDesired], r9d; cbData
0x1800365c0  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800365c5  xor     r8d, r8d; Reserved
0x1800365c8  lea     rdx, aNotifycount; "NotifyCount"
0x1800365cf  mov     rcx, rbx; hKey
0x1800365d2  call    cs:__imp_RegSetValueExW
0x1800365d8  cmp     dword ptr [rsi+0D8h], 0
0x1800365df  jz      short loc_18003660A
0x1800365e1  lea     rax, [rsi+0D0h]
0x1800365e8  mov     [rsp+60h+samDesired], r12d; cbData
0x1800365ed  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800365f2  lea     r9d, [r15-8]; dwType
0x1800365f6  xor     r8d, r8d; Reserved
0x1800365f9  lea     rdx, aMessageavailab; "MessageAvailableEventName"
0x180036600  mov     rcx, rbx; hKey
0x180036603  call    cs:__imp_RegSetValueExW
0x180036609  nop
0x18003660a  test    rbx, rbx
0x18003660d  jz      short loc_180036619
0x18003660f  mov     rcx, rbx; hKey
0x180036612  call    cs:__imp_RegCloseKey
0x180036618  nop
0x180036619  test    rdi, rdi
0x18003661c  jz      short loc_180036628
0x18003661e  mov     rcx, rdi; hKey
0x180036621  call    cs:__imp_RegCloseKey
0x180036627  nop
0x180036628  mov     rax, [r14]
0x18003662b  mov     rcx, r14
0x18003662e  mov     rax, [rax+8]
0x180036632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036637  nop
0x180036638  xor     eax, eax
0x18003663a  add     rsp, 60h
0x18003663e  pop     r15
0x180036640  pop     r14
0x180036642  pop     r12
0x180036644  pop     rdi
0x180036645  pop     rsi
0x180036646  pop     rbx
0x180036647  pop     rbp
0x180036648  retn
```
