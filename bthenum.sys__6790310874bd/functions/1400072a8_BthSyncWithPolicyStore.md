# BthSyncWithPolicyStore

- ea: `0x1400072a8`
- end: `0x140007784`
- name: `BthSyncWithPolicyStore`
- size: `1244`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140007790`
- `0x140020078`

## callees

- `0x140006e5c`
- `0x1400072a8`
- `0x140008140`
- `0x14001f598`
- `0x14001f5ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400074f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007566`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400075d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400076c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400076e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400076fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400074f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007566`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400075d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400076c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400076e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400076fd`
- `ntoskrnl!ZwClose` at `0x14000775e`
- `ntoskrnl!ZwClose` at `0x14000775e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400076ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400076ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007749`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007749`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007317`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007361`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400073a4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400073e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000741e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000745b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007499`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007516`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007584`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400075f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007630`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000766e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007317`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007361`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400073a4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400073e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000741e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000745b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007499`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007516`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007584`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400075f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007630`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000766e`

## string_xrefs

- `0x140007450`: `PM_LinkSecurityLevel`
- `0x140007579`: `PM_ServicesAllowedList`
- `0x140007625`: `PM_AllowPrepairing`

## pseudocode

```c
__int64 BthSyncWithPolicyStore()
{
  __int64 v0; // rcx
  NTSTATUS v2; // edi
  KIRQL v3; // bl
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-29h] BYREF
  _OWORD v5[7]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v6; // [rsp+C0h] [rbp+67h] BYREF
  HANDLE Handle; // [rsp+C8h] [rbp+6Fh] BYREF

  Handle = 0;
  LODWORD(v6) = 0;
  DestinationString = 0;
  memset(v5, 0, 0x50u);
  if ( !g_PolicyStorePath.Buffer )
    return 3221225473LL;
  v2 = BthOpenKeyEx(v0, &g_PolicyStorePath, &Handle);
  if ( v2 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"PM_AllowBluetooth");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, v5, 0) >= 0 && (v5[0] & 0xFFFFFFFD) == 0 )
      DWORD1(v5[4]) |= 1u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowDiscoverableMode");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, (char *)v5 + 4, 0) >= 0 && DWORD1(v5[0]) <= 1 )
      DWORD1(v5[4]) |= 2u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowConnectableMode");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, (char *)v5 + 8, 0) >= 0 && DWORD2(v5[0]) <= 1 )
      DWORD1(v5[4]) |= 4u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowAdvertising");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, (char *)v5 + 12, 0) >= 0 && HIDWORD(v5[0]) <= 1 )
      DWORD1(v5[4]) |= 8u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowOutOfBandPairing");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, &v5[1], 0) >= 0 && LODWORD(v5[1]) <= 1 )
      DWORD1(v5[4]) |= 0x10u;
    RtlInitUnicodeString(&DestinationString, L"PM_LinkSecurityLevel");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, (char *)&v5[1] + 4, 0) >= 0 && DWORD1(v5[1]) <= 2 )
      DWORD1(v5[4]) |= 0x20u;
    RtlInitUnicodeString(&DestinationString, L"PM_LocalDeviceName");
    if ( (int)ReadVariableLengthPolicy(Handle, &DestinationString, (__int64)&v5[2], (__int64)&v6) < 0
      || (unsigned int)v6 > 0xFFFF )
    {
      if ( *(_QWORD *)&v5[2] )
      {
        ExFreePoolWithTag(*(PVOID *)&v5[2], 0);
        *(_OWORD *)((char *)&v5[1] + 8) = 0;
      }
    }
    else
    {
      WORD5(v5[1]) = v6;
      if ( (unsigned __int16)v6 >= 2u )
      {
        DWORD1(v5[4]) |= 0x40u;
        WORD4(v5[1]) = v6 - 2;
      }
    }
    RtlInitUnicodeString(&DestinationString, L"PM_DevicesAllowedList");
    if ( (int)ReadVariableLengthPolicy(Handle, &DestinationString, (__int64)&v5[2] + 8, (__int64)&v6) < 0 )
    {
      if ( *((_QWORD *)&v5[2] + 1) )
      {
        ExFreePoolWithTag(*((PVOID *)&v5[2] + 1), 0);
        *((_QWORD *)&v5[2] + 1) = 0;
        DWORD2(v5[4]) = 0;
      }
    }
    else
    {
      DWORD1(v5[4]) |= 0x80u;
      DWORD2(v5[4]) = (unsigned int)v6 >> 3;
    }
    RtlInitUnicodeString(&DestinationString, L"PM_ServicesAllowedList");
    if ( (int)ReadVariableLengthPolicy(Handle, &DestinationString, (__int64)&v5[3], (__int64)&v6) < 0 )
    {
      if ( *(_QWORD *)&v5[3] )
      {
        ExFreePoolWithTag(*(PVOID *)&v5[3], 0);
        *(_QWORD *)&v5[3] = 0;
        HIDWORD(v5[4]) = 0;
      }
    }
    else
    {
      DWORD1(v5[4]) |= 0x100u;
      HIDWORD(v5[4]) = (unsigned int)v6 >> 4;
    }
    RtlInitUnicodeString(&DestinationString, L"PM_RequireRestrictedMode");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, (char *)&v5[3] + 8, 0) >= 0 && DWORD2(v5[3]) <= 1 )
      DWORD1(v5[4]) |= 0x200u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowPrepairing");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, (char *)&v5[3] + 12, 0) >= 0 && HIDWORD(v5[3]) <= 1 )
      DWORD1(v5[4]) |= 0x400u;
    RtlInitUnicodeString(&DestinationString, L"PM_SetMinimumEncryptionKeySize");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, &v5[4], 0) >= 0
      && (unsigned int)(LODWORD(v5[4]) - 1) <= 0xF )
    {
      DWORD1(v5[4]) |= 0x800u;
    }
    v3 = KeAcquireSpinLockRaiseToDpc(&g_PolicyLock);
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( *(&P + 1) )
      ExFreePoolWithTag(*(&P + 1), 0);
    if ( xmmword_140015290 )
      ExFreePoolWithTag(xmmword_140015290, 0);
    g_Policies = v5[0];
    *(_OWORD *)&P = v5[2];
    xmmword_140015270 = v5[1];
    *(_OWORD *)byte_1400152A0 = v5[4];
    *(_OWORD *)&xmmword_140015290 = v5[3];
    KeReleaseSpinLock(&g_PolicyLock, v3);
  }
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400072a8  mov     [rsp-8+arg_10], rbx
0x1400072ad  push    rbp
0x1400072ae  push    rsi
0x1400072af  push    rdi
0x1400072b0  push    r14
0x1400072b2  push    r15
0x1400072b4  lea     rbp, [rsp-37h]
0x1400072b9  sub     rsp, 90h
0x1400072c0  xor     esi, esi
0x1400072c2  lea     rcx, [rbp+57h+var_70]; void *
0x1400072c6  xorps   xmm0, xmm0
0x1400072c9  mov     [rbp+57h+Handle], rsi
0x1400072cd  xor     edx, edx; Val
0x1400072cf  mov     dword ptr [rbp+57h+arg_0], esi
0x1400072d2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400072d6  lea     r8d, [rsi+50h]; Size
0x1400072da  call    memset
0x1400072df  cmp     cs:?g_PolicyStorePath@@3U_UNICODE_STRING@@A.Buffer, rsi; _UNICODE_STRING g_PolicyStorePath ...
0x1400072e6  jnz     short loc_1400072F2
0x1400072e8  mov     eax, 0C0000001h
0x1400072ed  jmp     loc_14000776C
0x1400072f2  lea     r8, [rbp+57h+Handle]
0x1400072f6  lea     rdx, ?g_PolicyStorePath@@3U_UNICODE_STRING@@A; _UNICODE_STRING g_PolicyStorePath
0x1400072fd  call    BthOpenKeyEx
0x140007302  mov     edi, eax
0x140007304  test    eax, eax
0x140007306  js      loc_140007755
0x14000730c  lea     rdx, aPmAllowbluetoo; "PM_AllowBluetooth"
0x140007313  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140007317  call    cs:__imp_RtlInitUnicodeString
0x14000731e  nop     dword ptr [rax+rax+00h]
0x140007323  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140007327  lea     r8, [rbp+57h+var_70]; void *
0x14000732b  mov     r14d, 4
0x140007331  mov     [rsp+0B0h+var_90], rsi; __int64
0x140007336  mov     r9d, r14d
0x140007339  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14000733d  call    BthQueryKeyValueEx
0x140007342  lea     ebx, [r14-3]
0x140007346  test    eax, eax
0x140007348  js      short loc_140007356
0x14000734a  test    dword ptr [rbp+57h+var_70], 0FFFFFFFDh
0x140007351  jnz     short loc_140007356
0x140007353  or      dword ptr [rbp+57h+var_30+4], ebx
0x140007356  lea     rdx, aPmAllowdiscove; "PM_AllowDiscoverableMode"
0x14000735d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140007361  call    cs:__imp_RtlInitUnicodeString
0x140007368  nop     dword ptr [rax+rax+00h]
0x14000736d  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140007371  lea     r8, [rbp+57h+var_70+4]; void *
0x140007375  mov     r9d, r14d
0x140007378  mov     [rsp+0B0h+var_90], rsi; __int64
0x14000737d  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140007381  call    BthQueryKeyValueEx
0x140007386  mov     r15d, 2
0x14000738c  test    eax, eax
0x14000738e  js      short loc_140007399
0x140007390  cmp     dword ptr [rbp+57h+var_70+4], ebx
0x140007393  ja      short loc_140007399
0x140007395  or      dword ptr [rbp+57h+var_30+4], r15d
0x140007399  lea     rdx, aPmAllowconnect; "PM_AllowConnectableMode"
0x1400073a0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400073a4  call    cs:__imp_RtlInitUnicodeString
0x1400073ab  nop     dword ptr [rax+rax+00h]
0x1400073b0  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1400073b4  lea     r8, [rbp+57h+var_70+8]; void *
0x1400073b8  mov     r9d, r14d
0x1400073bb  mov     [rsp+0B0h+var_90], rsi; __int64
0x1400073c0  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1400073c4  call    BthQueryKeyValueEx
0x1400073c9  test    eax, eax
0x1400073cb  js      short loc_1400073D6
0x1400073cd  cmp     dword ptr [rbp+57h+var_70+8], ebx
0x1400073d0  ja      short loc_1400073D6
0x1400073d2  or      dword ptr [rbp+57h+var_30+4], r14d
0x1400073d6  lea     rdx, aPmAllowadverti; "PM_AllowAdvertising"
0x1400073dd  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400073e1  call    cs:__imp_RtlInitUnicodeString
0x1400073e8  nop     dword ptr [rax+rax+00h]
0x1400073ed  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1400073f1  lea     r8, [rbp+57h+var_70+0Ch]; void *
0x1400073f5  mov     r9d, r14d
0x1400073f8  mov     [rsp+0B0h+var_90], rsi; __int64
0x1400073fd  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140007401  call    BthQueryKeyValueEx
0x140007406  test    eax, eax
0x140007408  js      short loc_140007413
0x14000740a  cmp     dword ptr [rbp+57h+var_70+0Ch], ebx
0x14000740d  ja      short loc_140007413
0x14000740f  or      dword ptr [rbp+57h+var_30+4], 8
0x140007413  lea     rdx, aPmAllowoutofba; "PM_AllowOutOfBandPairing"
0x14000741a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000741e  call    cs:__imp_RtlInitUnicodeString
0x140007425  nop     dword ptr [rax+rax+00h]
0x14000742a  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14000742e  lea     r8, [rbp+57h+var_60]; void *
0x140007432  mov     r9d, r14d
0x140007435  mov     [rsp+0B0h+var_90], rsi; __int64
0x14000743a  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14000743e  call    BthQueryKeyValueEx
0x140007443  test    eax, eax
0x140007445  js      short loc_140007450
0x140007447  cmp     dword ptr [rbp+57h+var_60], ebx
0x14000744a  ja      short loc_140007450
0x14000744c  or      dword ptr [rbp+57h+var_30+4], 10h
0x140007450  lea     rdx, aPmLinksecurity; "PM_LinkSecurityLevel"
0x140007457  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000745b  call    cs:__imp_RtlInitUnicodeString
0x140007462  nop     dword ptr [rax+rax+00h]
0x140007467  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14000746b  lea     r8, [rbp+57h+var_60+4]; void *
0x14000746f  mov     r9d, r14d
0x140007472  mov     [rsp+0B0h+var_90], rsi; __int64
0x140007477  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14000747b  call    BthQueryKeyValueEx
0x140007480  test    eax, eax
0x140007482  js      short loc_14000748E
0x140007484  cmp     dword ptr [rbp+57h+var_60+4], r15d
0x140007488  ja      short loc_14000748E
0x14000748a  or      dword ptr [rbp+57h+var_30+4], 20h
0x14000748e  lea     rdx, aPmLocaldevicen; "PM_LocalDeviceName"
0x140007495  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140007499  call    cs:__imp_RtlInitUnicodeString
0x1400074a0  nop     dword ptr [rax+rax+00h]
0x1400074a5  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1400074a9  lea     rax, [rbp+57h+arg_0]
0x1400074ad  mov     [rsp+0B0h+var_88], rax; __int64
0x1400074b2  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1400074b6  lea     rax, [rbp+57h+var_50]
0x1400074ba  mov     r8d, r15d
0x1400074bd  mov     [rsp+0B0h+var_90], rax; __int64
0x1400074c2  call    ReadVariableLengthPolicy
0x1400074c7  test    eax, eax
0x1400074c9  js      short loc_1400074ED
0x1400074cb  mov     eax, dword ptr [rbp+57h+arg_0]
0x1400074ce  cmp     eax, 0FFFFh
0x1400074d3  ja      short loc_1400074ED
0x1400074d5  mov     word ptr [rbp+57h+var_60+0Ah], ax
0x1400074d9  cmp     ax, r15w
0x1400074dd  jb      short loc_14000750B
0x1400074df  sub     ax, r15w
0x1400074e3  or      dword ptr [rbp+57h+var_30+4], 40h
0x1400074e7  mov     word ptr [rbp+57h+var_60+8], ax
0x1400074eb  jmp     short loc_14000750B
0x1400074ed  mov     rcx, [rbp+57h+var_50]; P
0x1400074f1  test    rcx, rcx
0x1400074f4  jz      short loc_14000750B
0x1400074f6  xor     edx, edx; Tag
0x1400074f8  call    cs:__imp_ExFreePoolWithTag
0x1400074ff  nop     dword ptr [rax+rax+00h]
0x140007504  xorps   xmm0, xmm0
0x140007507  movups  [rbp+57h+var_60+8], xmm0
0x14000750b  lea     rdx, aPmDevicesallow; "PM_DevicesAllowedList"
0x140007512  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140007516  call    cs:__imp_RtlInitUnicodeString
0x14000751d  nop     dword ptr [rax+rax+00h]
0x140007522  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140007526  lea     rax, [rbp+57h+arg_0]
0x14000752a  mov     [rsp+0B0h+var_88], rax; __int64
0x14000752f  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140007533  lea     rax, [rbp+57h+P]
0x140007537  mov     r8d, 8
0x14000753d  mov     [rsp+0B0h+var_90], rax; __int64
0x140007542  call    ReadVariableLengthPolicy
0x140007547  test    eax, eax
0x140007549  js      short loc_14000755B
0x14000754b  mov     eax, dword ptr [rbp+57h+arg_0]
0x14000754e  shr     eax, 3
0x140007551  bts     dword ptr [rbp+57h+var_30+4], 7
0x140007556  mov     dword ptr [rbp+57h+var_30+8], eax
0x140007559  jmp     short loc_140007579
0x14000755b  mov     rcx, [rbp+57h+P]; P
0x14000755f  test    rcx, rcx
0x140007562  jz      short loc_140007579
0x140007564  xor     edx, edx; Tag
0x140007566  call    cs:__imp_ExFreePoolWithTag
0x14000756d  nop     dword ptr [rax+rax+00h]
0x140007572  mov     [rbp+57h+P], rsi
0x140007576  mov     dword ptr [rbp+57h+var_30+8], esi
0x140007579  lea     rdx, aPmServicesallo; "PM_ServicesAllowedList"
0x140007580  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140007584  call    cs:__imp_RtlInitUnicodeString
0x14000758b  nop     dword ptr [rax+rax+00h]
0x140007590  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140007594  lea     rax, [rbp+57h+arg_0]
0x140007598  mov     [rsp+0B0h+var_88], rax; __int64
0x14000759d  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1400075a1  lea     rax, [rbp+57h+var_40]
0x1400075a5  mov     r8d, 10h
0x1400075ab  mov     [rsp+0B0h+var_90], rax; __int64
0x1400075b0  call    ReadVariableLengthPolicy
0x1400075b5  test    eax, eax
0x1400075b7  js      short loc_1400075C9
0x1400075b9  mov     eax, dword ptr [rbp+57h+arg_0]
0x1400075bc  shr     eax, 4
0x1400075bf  bts     dword ptr [rbp+57h+var_30+4], 8
0x1400075c4  mov     dword ptr [rbp+57h+var_30+0Ch], eax
0x1400075c7  jmp     short loc_1400075E7
0x1400075c9  mov     rcx, [rbp+57h+var_40]; P
0x1400075cd  test    rcx, rcx
0x1400075d0  jz      short loc_1400075E7
0x1400075d2  xor     edx, edx; Tag
0x1400075d4  call    cs:__imp_ExFreePoolWithTag
0x1400075db  nop     dword ptr [rax+rax+00h]
0x1400075e0  mov     [rbp+57h+var_40], rsi
0x1400075e4  mov     dword ptr [rbp+57h+var_30+0Ch], esi
0x1400075e7  lea     rdx, aPmRequirerestr; "PM_RequireRestrictedMode"
0x1400075ee  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400075f2  call    cs:__imp_RtlInitUnicodeString
0x1400075f9  nop     dword ptr [rax+rax+00h]
0x1400075fe  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140007602  lea     r8, [rbp+57h+var_40+8]; void *
0x140007606  mov     r9d, r14d
0x140007609  mov     [rsp+0B0h+var_90], rsi; __int64
0x14000760e  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140007612  call    BthQueryKeyValueEx
0x140007617  test    eax, eax
0x140007619  js      short loc_140007625
0x14000761b  cmp     dword ptr [rbp+57h+var_40+8], ebx
0x14000761e  ja      short loc_140007625
0x140007620  bts     dword ptr [rbp+57h+var_30+4], 9
0x140007625  lea     rdx, aPmAllowprepair; "PM_AllowPrepairing"
0x14000762c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140007630  call    cs:__imp_RtlInitUnicodeString
0x140007637  nop     dword ptr [rax+rax+00h]
0x14000763c  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140007640  lea     r8, [rbp+57h+var_40+0Ch]; void *
0x140007644  mov     r9d, r14d
0x140007647  mov     [rsp+0B0h+var_90], rsi; __int64
0x14000764c  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140007650  call    BthQueryKeyValueEx
0x140007655  test    eax, eax
0x140007657  js      short loc_140007663
0x140007659  cmp     dword ptr [rbp+57h+var_40+0Ch], ebx
0x14000765c  ja      short loc_140007663
0x14000765e  bts     dword ptr [rbp+57h+var_30+4], 0Ah
0x140007663  lea     rdx, aPmSetminimumen; "PM_SetMinimumEncryptionKeySize"
0x14000766a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000766e  call    cs:__imp_RtlInitUnicodeString
0x140007675  nop     dword ptr [rax+rax+00h]
0x14000767a  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14000767e  lea     r8, [rbp+57h+var_30]; void *
0x140007682  mov     r9d, r14d
0x140007685  mov     [rsp+0B0h+var_90], rsi; __int64
0x14000768a  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14000768e  call    BthQueryKeyValueEx
0x140007693  test    eax, eax
0x140007695  js      short loc_1400076A6
0x140007697  mov     eax, dword ptr [rbp+57h+var_30]
0x14000769a  dec     eax
0x14000769c  cmp     eax, 0Fh
0x14000769f  ja      short loc_1400076A6
0x1400076a1  bts     dword ptr [rbp+57h+var_30+4], 0Bh
0x1400076a6  lea     rcx, ?g_PolicyLock@@3_KA; SpinLock
0x1400076ad  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400076b4  nop     dword ptr [rax+rax+00h]
0x1400076b9  mov     rcx, qword ptr cs:P; P
0x1400076c0  mov     bl, al
0x1400076c2  test    rcx, rcx
0x1400076c5  jz      short loc_1400076D5
0x1400076c7  xor     edx, edx; Tag
0x1400076c9  call    cs:__imp_ExFreePoolWithTag
0x1400076d0  nop     dword ptr [rax+rax+00h]
0x1400076d5  mov     rcx, qword ptr cs:P+8; P
0x1400076dc  test    rcx, rcx
0x1400076df  jz      short loc_1400076EF
0x1400076e1  xor     edx, edx; Tag
0x1400076e3  call    cs:__imp_ExFreePoolWithTag
0x1400076ea  nop     dword ptr [rax+rax+00h]
0x1400076ef  mov     rcx, qword ptr cs:xmmword_140015290; P
0x1400076f6  test    rcx, rcx
0x1400076f9  jz      short loc_140007709
0x1400076fb  xor     edx, edx; Tag
0x1400076fd  call    cs:__imp_ExFreePoolWithTag
0x140007704  nop     dword ptr [rax+rax+00h]
0x140007709  movaps  xmm0, [rbp+57h+var_70]
0x14000770d  lea     rcx, ?g_PolicyLock@@3_KA; SpinLock
0x140007714  movaps  xmm1, [rbp+57h+var_60]
0x140007718  mov     dl, bl; NewIrql
0x14000771a  movaps  cs:?g_Policies@@3UPolicies@@A, xmm0; Policies g_Policies
0x140007721  movaps  xmm0, xmmword ptr [rbp+7]
0x140007725  movaps  cs:P, xmm0
0x14000772c  movaps  xmm0, [rbp+57h+var_30]
0x140007730  movaps  cs:xmmword_140015270, xmm1
0x140007737  movaps  xmm1, xmmword ptr [rbp+57h+var_40]
0x14000773b  movaps  xmmword ptr cs:byte_1400152A0, xmm0
0x140007742  movaps  cs:xmmword_140015290, xmm1
0x140007749  call    cs:__imp_KeReleaseSpinLock
0x140007750  nop     dword ptr [rax+rax+00h]
0x140007755  mov     rcx, [rbp+57h+Handle]; Handle
0x140007759  test    rcx, rcx
0x14000775c  jz      short loc_14000776A
0x14000775e  call    cs:__imp_ZwClose
0x140007765  nop     dword ptr [rax+rax+00h]
0x14000776a  mov     eax, edi
0x14000776c  mov     rbx, [rsp+0B0h+arg_10]
0x140007774  add     rsp, 90h
0x14000777b  pop     r15
0x14000777d  pop     r14
0x14000777f  pop     rdi
  ... truncated ...
```
