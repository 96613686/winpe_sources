# DoPerAppBrokerInstancingDefaultForActivationConfigurationCheck(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1400060d0`
- end: `0x140006259`
- name: `?DoPerAppBrokerInstancingDefaultForActivationConfigurationCheck@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `393`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140005164`
- `0x1400060d0`
- `0x14000d63c`
- `0x14000ef0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140006152`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140006152`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400061d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400061d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006119`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006119`

## string_xrefs

- `0x140006194`: `CheckPerAppBrokerInstancingRegistryValue`
- `0x140006213`: `CheckPerAppBrokerInstancingRegistryValue`
- `0x14000619f`: `onecore\com\combase\common\core\perappruntimebroker.cpp`
- `0x140006228`: `onecore\com\combase\common\core\perappruntimebroker.cpp`
- `0x140006141`: `EnablePerStoreApplicationBrokerInstance`

## pseudocode

```c
__int64 __fastcall DoPerAppBrokerInstancingDefaultForActivationConfigurationCheck(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  LSTATUS v3; // edx
  bool v4; // bl
  char v5; // si
  LSTATUS v6; // edi
  BYTE Data[4]; // [rsp+40h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-14h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-10h] BYREF
  DWORD Type; // [rsp+98h] [rbp+40h] BYREF

  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\OLE\\Diagnosis", 0, 0x20019u, &hKey);
  if ( v3 )
  {
    if ( v3 != 2 && (dword_140018080 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
      ComTraceMessage(
        0xFFFFFFFFLL,
        "onecore\\com\\combase\\common\\core\\perappruntimebroker.cpp",
        "CheckPerAppBrokerInstancingRegistryValue",
        60,
        0,
        L"%!WINERROR!",
        v3);
    goto LABEL_18;
  }
  v4 = 0;
  v5 = 0;
  v6 = RegQueryValueExW(hKey, L"EnablePerStoreApplicationBrokerInstance", 0, &Type, Data, &cbData);
  if ( v6 )
  {
    if ( v6 == 2 )
      goto LABEL_10;
  }
  else if ( Type == 4 )
  {
    v5 = 1;
    v4 = *(_DWORD *)Data != 0;
    goto LABEL_10;
  }
  if ( dword_140018080 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    ComTraceMessage(
      0xFFFFFFFFLL,
      "onecore\\com\\combase\\common\\core\\perappruntimebroker.cpp",
      "CheckPerAppBrokerInstancingRegistryValue",
      54,
      0,
      L"error %!WINERROR! type %d",
      v6,
      Type);
LABEL_10:
  RegCloseKey(hKey);
  if ( v6 || !v5 )
  {
LABEL_18:
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerAppRuntimeBroker>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_PerAppRuntimeBroker>::GetImpl'::`2'::impl);
    v4 = 1;
  }
  byte_140018770 = v4;
  return 1;
}

```

## disassembly

```asm
0x1400060d0  push    rbp
0x1400060d2  push    rbx
0x1400060d3  push    rsi
0x1400060d4  push    rdi
0x1400060d5  mov     rbp, rsp
0x1400060d8  sub     rsp, 58h
0x1400060dc  lea     rax, [rbp+hKey]
0x1400060e0  mov     [rbp+hKey], 0
0x1400060e8  mov     r9d, 20019h; samDesired
0x1400060ee  mov     [rsp+58h+phkResult], rax; phkResult
0x1400060f3  xor     r8d, r8d; ulOptions
0x1400060f6  mov     [rbp+Type], 0
0x1400060fd  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\OLE\\Diagnosis"
0x140006104  mov     dword ptr [rbp+Data], 0
0x14000610b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140006112  mov     [rbp+cbData], 4
0x140006119  call    cs:__imp_RegOpenKeyExW
0x14000611f  mov     edx, eax
0x140006121  test    eax, eax
0x140006123  jnz     loc_1400061E1
0x140006129  mov     rcx, [rbp+hKey]; hKey
0x14000612d  lea     rax, [rbp+cbData]
0x140006131  mov     [rsp+58h+lpcbData], rax; lpcbData
0x140006136  lea     r9, [rbp+Type]; lpType
0x14000613a  lea     rax, [rbp+Data]
0x14000613e  xor     r8d, r8d; lpReserved
0x140006141  lea     rdx, ValueName; "EnablePerStoreApplicationBrokerInstance"
0x140006148  mov     [rsp+58h+phkResult], rax; lpData
0x14000614d  xor     bl, bl
0x14000614f  xor     sil, sil
0x140006152  call    cs:__imp_RegQueryValueExW
0x140006158  mov     edi, eax
0x14000615a  test    eax, eax
0x14000615c  jnz     short loc_14000616F
0x14000615e  cmp     [rbp+Type], 4
0x140006162  jnz     short loc_140006174
0x140006164  cmp     dword ptr [rbp+Data], eax
0x140006167  mov     sil, 1
0x14000616a  setnz   bl
0x14000616d  jmp     short loc_1400061CC
0x14000616f  cmp     edi, 2
0x140006172  jz      short loc_1400061CC
0x140006174  mov     eax, cs:dword_140018080
0x14000617a  test    eax, eax
0x14000617c  jnz     short loc_140006191
0x14000617e  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x140006184  jz      short loc_1400061CC
0x140006186  xor     ecx, ecx
0x140006188  call    IsWppLevelEnabled
0x14000618d  test    al, al
0x14000618f  jz      short loc_1400061CC
0x140006191  mov     eax, [rbp+Type]
0x140006194  lea     r8, aCheckperappbro; "CheckPerAppBrokerInstancingRegistryValu"...
0x14000619b  mov     [rsp+58h+var_20], eax
0x14000619f  lea     rdx, aOnecoreComComb_1; "onecore\\com\\combase\\common\\core\\pe"...
0x1400061a6  lea     rax, aErrorWinerrorT; "error %!WINERROR! type %d"
0x1400061ad  mov     [rsp+58h+var_28], edi
0x1400061b1  mov     [rsp+58h+lpcbData], rax
0x1400061b6  mov     r9d, 36h ; '6'
0x1400061bc  or      ecx, 0FFFFFFFFh
0x1400061bf  mov     dword ptr [rsp+58h+phkResult], 0
0x1400061c7  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1400061cc  mov     rcx, [rbp+hKey]; hKey
0x1400061d0  call    cs:__imp_RegCloseKey
0x1400061d6  test    edi, edi
0x1400061d8  jnz     short loc_140006237
0x1400061da  test    sil, sil
0x1400061dd  jz      short loc_140006237
0x1400061df  jmp     short loc_140006245
0x1400061e1  cmp     edx, 2
0x1400061e4  jz      short loc_140006237
0x1400061e6  mov     eax, cs:dword_140018080
0x1400061ec  test    eax, eax
0x1400061ee  jnz     short loc_140006203
0x1400061f0  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1400061f6  jz      short loc_140006237
0x1400061f8  xor     ecx, ecx
0x1400061fa  call    IsWppLevelEnabled
0x1400061ff  test    al, al
0x140006201  jz      short loc_140006237
0x140006203  mov     [rsp+58h+var_28], edx
0x140006207  lea     rax, aWinerror; "%!WINERROR!"
0x14000620e  mov     [rsp+58h+lpcbData], rax
0x140006213  lea     r8, aCheckperappbro; "CheckPerAppBrokerInstancingRegistryValu"...
0x14000621a  mov     r9d, 3Ch ; '<'
0x140006220  mov     dword ptr [rsp+58h+phkResult], 0
0x140006228  lea     rdx, aOnecoreComComb_1; "onecore\\com\\combase\\common\\core\\pe"...
0x14000622f  or      ecx, 0FFFFFFFFh
0x140006232  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x140006237  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PerAppRuntimeBroker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PerAppRuntimeBroker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerAppRuntimeBroker> `wil::Feature<__WilFeatureTraits_Feature_PerAppRuntimeBroker>::GetImpl(void)'::`2'::impl
0x14000623e  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_PerAppRuntimeBroker@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerAppRuntimeBroker>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x140006243  mov     bl, 1
0x140006245  mov     cs:byte_140018770, bl
0x14000624b  mov     eax, 1
0x140006250  add     rsp, 58h
0x140006254  pop     rdi
0x140006255  pop     rsi
0x140006256  pop     rbx
0x140006257  pop     rbp
0x140006258  retn
```
