# BthSyncWithPolicyStore

- ea: `0x1800305a8`
- end: `0x180030a3e`
- name: `BthSyncWithPolicyStore`
- size: `1174`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180030a90`

## callees

- `0x180002470`
- `0x1800024ac`
- `0x18002ff48`
- `0x1800305a8`
- `0x180030af0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180030630`
- `ntdll!RtlInitUnicodeString` at `0x180030674`
- `ntdll!RtlInitUnicodeString` at `0x1800306b6`
- `ntdll!RtlInitUnicodeString` at `0x1800306f1`
- `ntdll!RtlInitUnicodeString` at `0x18003072d`
- `ntdll!RtlInitUnicodeString` at `0x180030769`
- `ntdll!RtlInitUnicodeString` at `0x1800307a5`
- `ntdll!RtlInitUnicodeString` at `0x180030819`
- `ntdll!RtlInitUnicodeString` at `0x18003087f`
- `ntdll!RtlInitUnicodeString` at `0x1800308e1`
- `ntdll!RtlInitUnicodeString` at `0x18003091e`
- `ntdll!RtlInitUnicodeString` at `0x18003095b`
- `ntdll!RtlInitUnicodeString` at `0x180030630`
- `ntdll!RtlInitUnicodeString` at `0x180030674`
- `ntdll!RtlInitUnicodeString` at `0x1800306b6`
- `ntdll!RtlInitUnicodeString` at `0x1800306f1`
- `ntdll!RtlInitUnicodeString` at `0x18003072d`
- `ntdll!RtlInitUnicodeString` at `0x180030769`
- `ntdll!RtlInitUnicodeString` at `0x1800307a5`
- `ntdll!RtlInitUnicodeString` at `0x180030819`
- `ntdll!RtlInitUnicodeString` at `0x18003087f`
- `ntdll!RtlInitUnicodeString` at `0x1800308e1`
- `ntdll!RtlInitUnicodeString` at `0x18003091e`
- `ntdll!RtlInitUnicodeString` at `0x18003095b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030998`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030998`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030a0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030a0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030a1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030a1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030615`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030615`

## string_xrefs

- `0x18003075e`: `PM_LinkSecurityLevel`
- `0x180030874`: `PM_ServicesAllowedList`
- `0x180030913`: `PM_AllowPrepairing`

## pseudocode

```c
__int64 BthSyncWithPolicyStore()
{
  unsigned int v1; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-19h] BYREF
  __int128 v3; // [rsp+40h] [rbp-9h] BYREF
  __m256 v4; // [rsp+50h] [rbp+7h] BYREF
  void *v5[2]; // [rsp+70h] [rbp+27h] BYREF
  __int128 v6; // [rsp+80h] [rbp+37h] BYREF
  unsigned int v7; // [rsp+B0h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+6Fh] BYREF

  hKey = 0;
  v7 = 0;
  DestinationString = 0;
  memset_0(&v3, 0, 0x50u);
  if ( !lpSubKey )
    return 3221225473LL;
  v1 = -1073741823;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
  {
    v1 = 0;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowBluetooth");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, &v3, 4u, 0) >= 0 && (v3 & 0xFFFFFFFD) == 0 )
      DWORD1(v6) |= 1u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowDiscoverableMode");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, (char *)&v3 + 4, 4u, 0) >= 0 && DWORD1(v3) <= 1 )
      DWORD1(v6) |= 2u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowConnectableMode");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, (char *)&v3 + 8, 4u, 0) >= 0 && DWORD2(v3) <= 1 )
      DWORD1(v6) |= 4u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowAdvertising");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, (char *)&v3 + 12, 4u, 0) >= 0 && HIDWORD(v3) <= 1 )
      DWORD1(v6) |= 8u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowOutOfBandPairing");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, &v4, 4u, 0) >= 0 && LODWORD(v4.m256_f32[0]) <= 1 )
      DWORD1(v6) |= 0x10u;
    RtlInitUnicodeString(&DestinationString, L"PM_LinkSecurityLevel");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, &v4.m256_f32[1], 4u, 0) >= 0 && LODWORD(v4.m256_f32[1]) <= 2 )
      DWORD1(v6) |= 0x20u;
    RtlInitUnicodeString(&DestinationString, L"PM_LocalDeviceName");
    if ( (int)((__int64 (__fastcall *)(HKEY, struct _UNICODE_STRING *, __int64, __int64, float *, unsigned int *))ReadVariableLengthPolicy)(
                hKey,
                &DestinationString,
                2,
                1,
                &v4.m256_f32[4],
                &v7) < 0
      || v7 > 0xFFFF )
    {
      if ( *(_QWORD *)&v4.m256_f32[4] )
      {
        free(*(void **)&v4.m256_f32[4]);
        *(_OWORD *)&v4.m256_f32[2] = 0;
      }
    }
    else
    {
      HIWORD(v4.m256_f32[2]) = v7;
      if ( (unsigned __int16)v7 >= 2u )
      {
        DWORD1(v6) |= 0x40u;
        LOWORD(v4.m256_f32[2]) = v7 - 2;
      }
    }
    RtlInitUnicodeString(&DestinationString, L"PM_DevicesAllowedList");
    if ( (int)((__int64 (__fastcall *)(HKEY, struct _UNICODE_STRING *, __int64, __int64, float *, unsigned int *))ReadVariableLengthPolicy)(
                hKey,
                &DestinationString,
                8,
                3,
                &v4.m256_f32[6],
                &v7) < 0 )
    {
      if ( *(_QWORD *)&v4.m256_f32[6] )
      {
        free(*(void **)&v4.m256_f32[6]);
        *(_QWORD *)&v4.m256_f32[6] = 0;
        DWORD2(v6) = 0;
      }
    }
    else
    {
      DWORD1(v6) |= 0x80u;
      DWORD2(v6) = v7 >> 3;
    }
    RtlInitUnicodeString(&DestinationString, L"PM_ServicesAllowedList");
    if ( (int)((__int64 (__fastcall *)(HKEY, struct _UNICODE_STRING *, __int64, __int64, void **, unsigned int *))ReadVariableLengthPolicy)(
                hKey,
                &DestinationString,
                16,
                3,
                v5,
                &v7) < 0 )
    {
      if ( v5[0] )
      {
        free(v5[0]);
        v5[0] = 0;
        HIDWORD(v6) = 0;
      }
    }
    else
    {
      DWORD1(v6) |= 0x100u;
      HIDWORD(v6) = v7 >> 4;
    }
    RtlInitUnicodeString(&DestinationString, L"PM_RequireRestrictedMode");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, &v5[1], 4u, 0) >= 0 && LODWORD(v5[1]) <= 1 )
      DWORD1(v6) |= 0x200u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowPrepairing");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, (char *)&v5[1] + 4, 4u, 0) >= 0 && HIDWORD(v5[1]) <= 1 )
      DWORD1(v6) |= 0x400u;
    RtlInitUnicodeString(&DestinationString, L"PM_SetMinimumEncryptionKeySize");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, &v6, 4u, 0) >= 0 && (unsigned int)(v6 - 1) <= 0xF )
      DWORD1(v6) |= 0x800u;
    EnterCriticalSection(&g_PolicyLock);
    if ( *(_QWORD *)&ymmword_180044A20.m256_f32[4] )
      free(*(void **)&ymmword_180044A20.m256_f32[4]);
    if ( *(_QWORD *)&ymmword_180044A20.m256_f32[6] )
      free(*(void **)&ymmword_180044A20.m256_f32[6]);
    if ( Src )
      free(Src);
    g_Policies = v3;
    ymmword_180044A20 = v4;
    xmmword_180044A50 = v6;
    *(_OWORD *)&Src = *(_OWORD *)v5;
    LeaveCriticalSection(&g_PolicyLock);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x1800305a8  mov     [rsp-8+arg_10], rbx
0x1800305ad  mov     [rsp-8+arg_18], rsi
0x1800305b2  push    rbp
0x1800305b3  push    rdi
0x1800305b4  push    r15
0x1800305b6  lea     rbp, [rsp-47h]
0x1800305bb  sub     rsp, 90h
0x1800305c2  xor     edi, edi
0x1800305c4  lea     rcx, [rbp+57h+var_60]; void *
0x1800305c8  xorps   xmm0, xmm0
0x1800305cb  mov     [rbp+57h+hKey], rdi
0x1800305cf  xor     edx, edx; Val
0x1800305d1  mov     [rbp+57h+arg_0], edi
0x1800305d4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800305d8  lea     r8d, [rdi+50h]; Size
0x1800305dc  call    memset_0
0x1800305e1  mov     rdx, cs:lpSubKey; lpSubKey
0x1800305e8  test    rdx, rdx
0x1800305eb  jnz     short loc_1800305F7
0x1800305ed  mov     eax, 0C0000001h
0x1800305f2  jmp     loc_180030A26
0x1800305f7  lea     rax, [rbp+57h+hKey]
0x1800305fb  mov     r9d, 20019h; samDesired
0x180030601  xor     r8d, r8d; ulOptions
0x180030604  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180030609  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180030610  mov     ebx, 0C0000001h
0x180030615  call    cs:__imp_RegOpenKeyExW
0x18003061b  test    eax, eax
0x18003061d  jnz     loc_180030A15
0x180030623  lea     rdx, aPmAllowbluetoo; "PM_AllowBluetooth"
0x18003062a  mov     ebx, edi
0x18003062c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180030630  call    cs:__imp_RtlInitUnicodeString
0x180030636  mov     rcx, [rbp+57h+hKey]; HKEY
0x18003063a  lea     r9, [rbp+57h+var_60]; void *
0x18003063e  mov     esi, 4
0x180030643  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x180030648  mov     r8d, esi; unsigned int
0x18003064b  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x18003064f  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x180030653  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x180030658  test    eax, eax
0x18003065a  js      short loc_180030669
0x18003065c  test    dword ptr [rbp+57h+var_60], 0FFFFFFFDh
0x180030663  jnz     short loc_180030669
0x180030665  or      dword ptr [rbp+57h+var_20+4], 1
0x180030669  lea     rdx, aPmAllowdiscove; "PM_AllowDiscoverableMode"
0x180030670  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180030674  call    cs:__imp_RtlInitUnicodeString
0x18003067a  mov     rcx, [rbp+57h+hKey]; HKEY
0x18003067e  lea     r9, [rbp+57h+var_60+4]; void *
0x180030682  mov     r8d, esi; unsigned int
0x180030685  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x18003068a  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x18003068e  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x180030692  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x180030697  mov     r15d, 2
0x18003069d  test    eax, eax
0x18003069f  js      short loc_1800306AB
0x1800306a1  cmp     dword ptr [rbp+57h+var_60+4], 1
0x1800306a5  ja      short loc_1800306AB
0x1800306a7  or      dword ptr [rbp+57h+var_20+4], r15d
0x1800306ab  lea     rdx, aPmAllowconnect; "PM_AllowConnectableMode"
0x1800306b2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800306b6  call    cs:__imp_RtlInitUnicodeString
0x1800306bc  mov     rcx, [rbp+57h+hKey]; HKEY
0x1800306c0  lea     r9, [rbp+57h+var_60+8]; void *
0x1800306c4  mov     r8d, esi; unsigned int
0x1800306c7  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x1800306cc  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x1800306d0  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x1800306d4  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x1800306d9  test    eax, eax
0x1800306db  js      short loc_1800306E6
0x1800306dd  cmp     dword ptr [rbp+57h+var_60+8], 1
0x1800306e1  ja      short loc_1800306E6
0x1800306e3  or      dword ptr [rbp+57h+var_20+4], esi
0x1800306e6  lea     rdx, aPmAllowadverti; "PM_AllowAdvertising"
0x1800306ed  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800306f1  call    cs:__imp_RtlInitUnicodeString
0x1800306f7  mov     rcx, [rbp+57h+hKey]; HKEY
0x1800306fb  lea     r9, [rbp+57h+var_60+0Ch]; void *
0x1800306ff  mov     r8d, esi; unsigned int
0x180030702  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x180030707  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x18003070b  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x18003070f  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x180030714  test    eax, eax
0x180030716  js      short loc_180030722
0x180030718  cmp     dword ptr [rbp+57h+var_60+0Ch], 1
0x18003071c  ja      short loc_180030722
0x18003071e  or      dword ptr [rbp+57h+var_20+4], 8
0x180030722  lea     rdx, aPmAllowoutofba; "PM_AllowOutOfBandPairing"
0x180030729  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003072d  call    cs:__imp_RtlInitUnicodeString
0x180030733  mov     rcx, [rbp+57h+hKey]; HKEY
0x180030737  lea     r9, [rbp+57h+var_50]; void *
0x18003073b  mov     r8d, esi; unsigned int
0x18003073e  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x180030743  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x180030747  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x18003074b  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x180030750  test    eax, eax
0x180030752  js      short loc_18003075E
0x180030754  cmp     dword ptr [rbp+57h+var_50], 1
0x180030758  ja      short loc_18003075E
0x18003075a  or      dword ptr [rbp+57h+var_20+4], 10h
0x18003075e  lea     rdx, aPmLinksecurity; "PM_LinkSecurityLevel"
0x180030765  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180030769  call    cs:__imp_RtlInitUnicodeString
0x18003076f  mov     rcx, [rbp+57h+hKey]; HKEY
0x180030773  lea     r9, [rbp+57h+var_50+4]; void *
0x180030777  mov     r8d, esi; unsigned int
0x18003077a  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x18003077f  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x180030783  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x180030787  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x18003078c  test    eax, eax
0x18003078e  js      short loc_18003079A
0x180030790  cmp     dword ptr [rbp+57h+var_50+4], r15d
0x180030794  ja      short loc_18003079A
0x180030796  or      dword ptr [rbp+57h+var_20+4], 20h
0x18003079a  lea     rdx, aPmLocaldevicen; "PM_LocalDeviceName"
0x1800307a1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800307a5  call    cs:__imp_RtlInitUnicodeString
0x1800307ab  mov     rcx, [rbp+57h+hKey]
0x1800307af  lea     rax, [rbp+57h+arg_0]
0x1800307b3  mov     [rsp+0A0h+var_78], rax
0x1800307b8  lea     rdx, [rbp+57h+DestinationString]
0x1800307bc  lea     rax, [rbp+57h+Block]
0x1800307c0  mov     r9d, 1
0x1800307c6  mov     r8d, r15d
0x1800307c9  mov     [rsp+0A0h+phkResult], rax
0x1800307ce  call    ReadVariableLengthPolicy
0x1800307d3  test    eax, eax
0x1800307d5  js      short loc_1800307F9
0x1800307d7  mov     eax, [rbp+57h+arg_0]
0x1800307da  cmp     eax, 0FFFFh
0x1800307df  ja      short loc_1800307F9
0x1800307e1  mov     word ptr [rbp+57h+var_50+0Ah], ax
0x1800307e5  cmp     ax, r15w
0x1800307e9  jb      short loc_18003080E
0x1800307eb  sub     ax, r15w
0x1800307ef  or      dword ptr [rbp+57h+var_20+4], 40h
0x1800307f3  mov     word ptr [rbp+57h+var_50+8], ax
0x1800307f7  jmp     short loc_18003080E
0x1800307f9  mov     rcx, [rbp+57h+Block]; Block
0x1800307fd  test    rcx, rcx
0x180030800  jz      short loc_18003080E
0x180030802  call    free
0x180030807  xorps   xmm0, xmm0
0x18003080a  movups  [rbp+57h+var_50+8], xmm0
0x18003080e  lea     rdx, aPmDevicesallow; "PM_DevicesAllowedList"
0x180030815  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180030819  call    cs:__imp_RtlInitUnicodeString
0x18003081f  mov     rcx, [rbp+57h+hKey]
0x180030823  lea     rax, [rbp+57h+arg_0]
0x180030827  mov     [rsp+0A0h+var_78], rax
0x18003082c  lea     rdx, [rbp+57h+DestinationString]
0x180030830  mov     r15d, 3
0x180030836  lea     rax, [rbp+57h+Block+8]
0x18003083a  mov     r9d, r15d
0x18003083d  mov     [rsp+0A0h+phkResult], rax
0x180030842  lea     r8d, [r15+5]
0x180030846  call    ReadVariableLengthPolicy
0x18003084b  test    eax, eax
0x18003084d  js      short loc_18003085F
0x18003084f  mov     eax, [rbp+57h+arg_0]
0x180030852  shr     eax, 3
0x180030855  bts     dword ptr [rbp+57h+var_20+4], 7
0x18003085a  mov     dword ptr [rbp+57h+var_20+8], eax
0x18003085d  jmp     short loc_180030874
0x18003085f  mov     rcx, [rbp+57h+Block+8]; Block
0x180030863  test    rcx, rcx
0x180030866  jz      short loc_180030874
0x180030868  call    free
0x18003086d  mov     [rbp+57h+Block+8], rdi
0x180030871  mov     dword ptr [rbp+57h+var_20+8], edi
0x180030874  lea     rdx, aPmServicesallo; "PM_ServicesAllowedList"
0x18003087b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003087f  call    cs:__imp_RtlInitUnicodeString
0x180030885  mov     rcx, [rbp+57h+hKey]
0x180030889  lea     rax, [rbp+57h+arg_0]
0x18003088d  mov     [rsp+0A0h+var_78], rax
0x180030892  lea     rdx, [rbp+57h+DestinationString]
0x180030896  lea     rax, [rbp+57h+var_30]
0x18003089a  mov     r9d, r15d
0x18003089d  mov     r8d, 10h
0x1800308a3  mov     [rsp+0A0h+phkResult], rax
0x1800308a8  call    ReadVariableLengthPolicy
0x1800308ad  test    eax, eax
0x1800308af  js      short loc_1800308C1
0x1800308b1  mov     eax, [rbp+57h+arg_0]
0x1800308b4  shr     eax, 4
0x1800308b7  bts     dword ptr [rbp+57h+var_20+4], 8
0x1800308bc  mov     dword ptr [rbp+57h+var_20+0Ch], eax
0x1800308bf  jmp     short loc_1800308D6
0x1800308c1  mov     rcx, [rbp+57h+var_30]; Block
0x1800308c5  test    rcx, rcx
0x1800308c8  jz      short loc_1800308D6
0x1800308ca  call    free
0x1800308cf  mov     [rbp+57h+var_30], rdi
0x1800308d3  mov     dword ptr [rbp+57h+var_20+0Ch], edi
0x1800308d6  lea     rdx, aPmRequirerestr; "PM_RequireRestrictedMode"
0x1800308dd  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800308e1  call    cs:__imp_RtlInitUnicodeString
0x1800308e7  mov     rcx, [rbp+57h+hKey]; HKEY
0x1800308eb  lea     r9, [rbp+57h+var_30+8]; void *
0x1800308ef  mov     r8d, esi; unsigned int
0x1800308f2  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x1800308f7  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x1800308fb  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x1800308ff  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x180030904  test    eax, eax
0x180030906  js      short loc_180030913
0x180030908  cmp     dword ptr [rbp+57h+var_30+8], 1
0x18003090c  ja      short loc_180030913
0x18003090e  bts     dword ptr [rbp+57h+var_20+4], 9
0x180030913  lea     rdx, aPmAllowprepair; "PM_AllowPrepairing"
0x18003091a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003091e  call    cs:__imp_RtlInitUnicodeString
0x180030924  mov     rcx, [rbp+57h+hKey]; HKEY
0x180030928  lea     r9, [rbp+57h+var_30+0Ch]; void *
0x18003092c  mov     r8d, esi; unsigned int
0x18003092f  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x180030934  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x180030938  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x18003093c  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x180030941  test    eax, eax
0x180030943  js      short loc_180030950
0x180030945  cmp     dword ptr [rbp+57h+var_30+0Ch], 1
0x180030949  ja      short loc_180030950
0x18003094b  bts     dword ptr [rbp+57h+var_20+4], 0Ah
0x180030950  lea     rdx, aPmSetminimumen; "PM_SetMinimumEncryptionKeySize"
0x180030957  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003095b  call    cs:__imp_RtlInitUnicodeString
0x180030961  mov     rcx, [rbp+57h+hKey]; HKEY
0x180030965  lea     r9, [rbp+57h+var_20]; void *
0x180030969  mov     r8d, esi; unsigned int
0x18003096c  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x180030971  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x180030975  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x180030979  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x18003097e  test    eax, eax
0x180030980  js      short loc_180030991
0x180030982  mov     eax, dword ptr [rbp+57h+var_20]
0x180030985  dec     eax
0x180030987  cmp     eax, 0Fh
0x18003098a  ja      short loc_180030991
0x18003098c  bts     dword ptr [rbp+57h+var_20+4], 0Bh
0x180030991  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180030998  call    cs:__imp_EnterCriticalSection
0x18003099e  mov     rcx, qword ptr cs:ymmword_180044A20+10h; Block
0x1800309a5  test    rcx, rcx
0x1800309a8  jz      short loc_1800309AF
0x1800309aa  call    free
0x1800309af  mov     rcx, qword ptr cs:ymmword_180044A20+18h; Block
0x1800309b6  test    rcx, rcx
0x1800309b9  jz      short loc_1800309C0
0x1800309bb  call    free
0x1800309c0  mov     rcx, qword ptr cs:Src; Block
0x1800309c7  test    rcx, rcx
0x1800309ca  jz      short loc_1800309D1
0x1800309cc  call    free
0x1800309d1  movaps  xmm0, [rbp+57h+var_60]
0x1800309d5  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800309dc  movaps  xmm1, [rbp+57h+var_50]
0x1800309e0  movaps  cs:?g_Policies@@3UPolicies@@A, xmm0; Policies g_Policies
0x1800309e7  movaps  xmm0, xmmword ptr [rbp+57h+Block]
0x1800309eb  movaps  xmmword ptr cs:ymmword_180044A20+10h, xmm0
0x1800309f2  movaps  xmm0, [rbp+57h+var_20]
0x1800309f6  movaps  xmmword ptr cs:ymmword_180044A20, xmm1
0x1800309fd  movaps  xmm1, xmmword ptr [rbp+57h+var_30]
0x180030a01  movaps  cs:xmmword_180044A50, xmm0
0x180030a08  movaps  cs:Src, xmm1
0x180030a0f  call    cs:__imp_LeaveCriticalSection
0x180030a15  mov     rcx, [rbp+57h+hKey]; hKey
0x180030a19  test    rcx, rcx
0x180030a1c  jz      short loc_180030A24
0x180030a1e  call    cs:__imp_RegCloseKey
0x180030a24  mov     eax, ebx
0x180030a26  lea     r11, [rsp+0A0h+var_10]
0x180030a2e  mov     rbx, [r11+30h]
0x180030a32  mov     rsi, [r11+38h]
0x180030a36  mov     rsp, r11
0x180030a39  pop     r15
0x180030a3b  pop     rdi
0x180030a3c  pop     rbp
0x180030a3d  retn
```
