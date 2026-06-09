# PolicyManager::ReadProPolicyValuesFromRegistry

- ea: `0x18005366c`
- end: `0x180053add`
- name: `PolicyManager::ReadProPolicyValuesFromRegistry`
- size: `1137`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ffec`
- `0x180053248`

## callees

- `0x180018194`
- `0x180019c94`
- `0x1800215ec`
- `0x180053580`
- `0x18005366c`
- `0x18005ed68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800536d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800536d5`

## string_xrefs

- `0x1800537f9`: `PINComplexity`
- `0x1800538ea`: `PINComplexity`
- `0x18005391f`: `PINComplexity`
- `0x18005395e`: `PINComplexity`
- `0x1800537bd`: `AllowAllUserAccessToSmartCardNode`
- `0x180053741`: `RequireSecurityDevice`

## pseudocode

```c
__int64 __fastcall PolicyManager::ReadProPolicyValuesFromRegistry(int a1, _OWORD *a2)
{
  LSTATUS v3; // eax
  int PolicyValue; // eax
  int v5; // ecx
  int v6; // edi
  unsigned int v7; // r13d
  unsigned int v8; // r12d
  int v9; // r15d
  int v10; // r14d
  int v11; // esi
  int v12; // edi
  int v13; // ebx
  int v14; // eax
  int v15; // ebx
  unsigned __int8 *v16; // rdx
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  unsigned int v21; // [rsp+50h] [rbp-79h] BYREF
  void **v22; // [rsp+58h] [rbp-71h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-69h] BYREF
  unsigned int v24; // [rsp+68h] [rbp-61h]
  unsigned int v25; // [rsp+6Ch] [rbp-5Dh]
  __int128 v26; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v27[44]; // [rsp+80h] [rbp-49h]
  _BYTE v28[4]; // [rsp+B0h] [rbp-19h] BYREF
  int v29; // [rsp+B4h] [rbp-15h]
  int v30; // [rsp+B8h] [rbp-11h]
  __int128 v31; // [rsp+BCh] [rbp-Dh]
  int v32; // [rsp+CCh] [rbp+3h]
  __int64 v33; // [rsp+D0h] [rbp+7h]
  int v34; // [rsp+D8h] [rbp+Fh]
  int v37; // [rsp+140h] [rbp+77h] BYREF
  unsigned int v38; // [rsp+148h] [rbp+7Fh] BYREF

  phkResult = 0;
  v37 = -1;
  v22 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v22);
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WinBio\\Credential Provider",
         0,
         0x20019u,
         &phkResult);
  if ( (v3 & 0xFFFFFFFD) != 0 && (unsigned int)dword_1800BE0B8 > 3 )
  {
    v38 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)byte_1800AD587,
      0,
      0,
      (__int64)&v38);
  }
  PolicyValue = PolicyManager::ReadPolicyValue((unsigned int)&v22, 0, (unsigned int)L"Enabled", 0, 1, (__int64)&v37);
  v5 = 1;
  if ( PolicyValue >= 0 )
    v5 = v37;
  v6 = 0;
  v25 = v5;
  v37 = -1;
  if ( (int)PolicyManager::ReadPolicyValue(a1, 0, (unsigned int)L"RequireSecurityDevice", 0, 1, (__int64)&v37) >= 0 )
    v6 = v37;
  v24 = v6;
  v37 = -1;
  if ( (int)PolicyManager::ReadPolicyValue(a1, 0, (unsigned int)L"DisableSmartCardNode", 0, 1, (__int64)&v37) >= 0
    && v37 == 1 )
  {
    v7 = 0;
  }
  else
  {
    v7 = 1;
    if ( (int)PolicyManager::ReadPolicyValue(
                a1,
                0,
                (unsigned int)L"AllowAllUserAccessToSmartCardNode",
                0,
                1,
                (__int64)&v37) >= 0
      && v37 == 1 )
    {
      v7 = 2;
    }
  }
  v21 = 6;
  PolicyManager::ReadPolicyValue(
    a1,
    (unsigned int)L"PINComplexity",
    (unsigned int)L"MinimumPINLength",
    4,
    127,
    (__int64)&v21);
  v38 = 127;
  PolicyManager::ReadPolicyValue(
    a1,
    (unsigned int)L"PINComplexity",
    (unsigned int)L"MaximumPINLength",
    4,
    127,
    (__int64)&v38);
  v37 = -1;
  v8 = 0;
  if ( (int)PolicyManager::ReadPolicyValue(
              a1,
              (unsigned int)L"PINComplexity",
              (unsigned int)L"UppercaseLetters",
              0,
              2,
              (__int64)&v37) >= 0 )
    v8 = v37;
  v37 = -1;
  v9 = 0;
  if ( (int)PolicyManager::ReadPolicyValue(
              a1,
              (unsigned int)L"PINComplexity",
              (unsigned int)L"LowercaseLetters",
              0,
              2,
              (__int64)&v37) >= 0 )
    v9 = v37;
  v10 = 0;
  v37 = -1;
  if ( (int)PolicyManager::ReadPolicyValue(
              a1,
              (unsigned int)L"PINComplexity",
              (unsigned int)L"Digits",
              0,
              2,
              (__int64)&v37) >= 0 )
    v10 = v37;
  v37 = -1;
  v11 = 0;
  if ( (int)PolicyManager::ReadPolicyValue(
              a1,
              (unsigned int)L"PINComplexity",
              (unsigned int)L"SpecialCharacters",
              0,
              2,
              (__int64)&v37) >= 0 )
    v11 = v37;
  v37 = -1;
  v12 = 0;
  if ( (int)PolicyManager::ReadPolicyValue(
              a1,
              (unsigned int)L"PINComplexity",
              (unsigned int)L"History",
              0,
              50,
              (__int64)&v37) >= 0 )
    v12 = v37;
  v37 = -1;
  v13 = 0;
  v14 = PolicyManager::ReadPolicyValue(
          a1,
          (unsigned int)L"PINComplexity",
          (unsigned int)L"Expiration",
          0,
          730,
          (__int64)&v37);
  v28[0] = 0;
  if ( v14 >= 0 )
    v13 = v37;
  v34 = 0;
  v29 = 8;
  v30 = 127;
  v31 = 0;
  v32 = 2;
  v33 = 1;
  v15 = NgcPolicy::NgcPinPolicy::Initialize(v28, v21, v38, v8, v9, v10, v11, 0, v12, v13);
  if ( v15 >= 0 )
  {
    DWORD1(v26) = 1;
    *((_QWORD *)&v26 + 1) = 1;
    *(_QWORD *)&v27[32] = 1;
    LOBYTE(v26) = 0;
    v27[0] = 0;
    *(_QWORD *)&v27[4] = 0x7F00000008LL;
    *(_OWORD *)&v27[12] = 0;
    *(_DWORD *)&v27[28] = 2;
    *(_DWORD *)&v27[40] = 0;
    v15 = NgcPolicy::NgcPolicy::Initialize(&v26, v25, v7, v24, v28);
    if ( v15 >= 0 )
    {
      v17 = *(_OWORD *)v27;
      *a2 = v26;
      v18 = *(_OWORD *)&v27[16];
      a2[1] = v17;
      v19 = *(_OWORD *)&v27[28];
      a2[2] = v18;
      *(_OWORD *)((char *)a2 + 44) = v19;
      goto LABEL_34;
    }
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v16 = (unsigned __int8 *)byte_1800AD5B5;
      goto LABEL_29;
    }
  }
  else if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    v16 = (unsigned __int8 *)&word_1800AD556;
LABEL_29:
    v37 = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      v16,
      0,
      0,
      (__int64)&v37);
  }
LABEL_34:
  v22 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v22);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18005366c  mov     [rsp-8+arg_8], rdx
0x180053671  mov     [rsp-8+arg_0], rcx
0x180053676  push    rbp
0x180053677  push    rbx
0x180053678  push    rsi
0x180053679  push    rdi
0x18005367a  push    r12
0x18005367c  push    r13
0x18005367e  push    r14
0x180053680  push    r15
0x180053682  lea     rbp, [rsp-1Fh]
0x180053687  sub     rsp, 0E8h
0x18005368e  mov     rbx, rcx
0x180053691  mov     [rbp+57h+var_C0], 0
0x180053699  lea     rax, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x1800536a0  or      r15d, 0FFFFFFFFh
0x1800536a4  lea     rcx, [rbp+57h+var_C8]
0x1800536a8  mov     [rbp+57h+arg_10], r15d
0x1800536ac  mov     [rbp+57h+var_C8], rax
0x1800536b0  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x1800536b5  lea     rax, [rbp+57h+var_C0]
0x1800536b9  mov     r9d, 20019h; samDesired
0x1800536bf  xor     r8d, r8d; ulOptions
0x1800536c2  mov     [rsp+120h+phkResult], rax; phkResult
0x1800536c7  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800536ce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800536d5  call    cs:__imp_RegOpenKeyExW
0x1800536dc  nop     dword ptr [rax+rax+00h]
0x1800536e1  test    eax, 0FFFFFFFDh
0x1800536e6  jz      short loc_180053718
0x1800536e8  mov     ecx, cs:dword_1800BE0B8
0x1800536ee  cmp     ecx, 3
0x1800536f1  jbe     short loc_180053718
0x1800536f3  mov     [rbp+57h+arg_18], eax
0x1800536f6  lea     rdx, byte_1800AD587
0x1800536fd  lea     rax, [rbp+57h+arg_18]
0x180053701  xor     r9d, r9d
0x180053704  xor     r8d, r8d
0x180053707  mov     [rsp+120h+phkResult], rax
0x18005370c  lea     rcx, dword_1800BE0B8
0x180053713  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180053718  lea     rax, [rbp+57h+arg_10]
0x18005371c  mov     esi, 1
0x180053721  mov     [rsp+120h+var_F8], rax
0x180053726  lea     r8, aEnabled; "Enabled"
0x18005372d  xor     r9d, r9d
0x180053730  mov     dword ptr [rsp+120h+phkResult], esi
0x180053734  xor     edx, edx
0x180053736  lea     rcx, [rbp+57h+var_C8]
0x18005373a  call    PolicyManager__ReadPolicyValue
0x18005373f  test    eax, eax
0x180053741  lea     r8, aRequiresecurit; "RequireSecurityDevice"
0x180053748  mov     ecx, esi
0x18005374a  lea     rax, [rbp+57h+arg_10]
0x18005374e  cmovns  ecx, [rbp+57h+arg_10]
0x180053752  xor     edi, edi
0x180053754  mov     [rbp+57h+var_B4], ecx
0x180053757  xor     r9d, r9d
0x18005375a  mov     [rsp+120h+var_F8], rax
0x18005375f  mov     rcx, rbx
0x180053762  xor     edx, edx
0x180053764  mov     [rbp+57h+arg_10], r15d
0x180053768  mov     dword ptr [rsp+120h+phkResult], esi
0x18005376c  call    PolicyManager__ReadPolicyValue
0x180053771  test    eax, eax
0x180053773  lea     r8, aDisablesmartca; "DisableSmartCardNode"
0x18005377a  lea     rax, [rbp+57h+arg_10]
0x18005377e  mov     rcx, rbx
0x180053781  cmovns  edi, [rbp+57h+arg_10]
0x180053785  xor     r9d, r9d
0x180053788  mov     [rsp+120h+var_F8], rax
0x18005378d  xor     edx, edx
0x18005378f  mov     [rbp+57h+var_B8], edi
0x180053792  mov     [rbp+57h+arg_10], r15d
0x180053796  mov     dword ptr [rsp+120h+phkResult], esi
0x18005379a  call    PolicyManager__ReadPolicyValue
0x18005379f  lea     r14d, [rsi+1]
0x1800537a3  test    eax, eax
0x1800537a5  js      short loc_1800537B1
0x1800537a7  cmp     [rbp+57h+arg_10], esi
0x1800537aa  jnz     short loc_1800537B1
0x1800537ac  xor     r13d, r13d
0x1800537af  jmp     short loc_1800537E0
0x1800537b1  lea     rax, [rbp+57h+arg_10]
0x1800537b5  xor     r9d, r9d
0x1800537b8  mov     [rsp+120h+var_F8], rax
0x1800537bd  lea     r8, aAllowalluserac; "AllowAllUserAccessToSmartCardNode"
0x1800537c4  xor     edx, edx
0x1800537c6  mov     dword ptr [rsp+120h+phkResult], esi
0x1800537ca  mov     rcx, rbx
0x1800537cd  mov     r13d, esi
0x1800537d0  call    PolicyManager__ReadPolicyValue
0x1800537d5  test    eax, eax
0x1800537d7  js      short loc_1800537E0
0x1800537d9  cmp     [rbp+57h+arg_10], esi
0x1800537dc  cmovz   r13d, r14d
0x1800537e0  mov     r12d, 7Fh
0x1800537e6  mov     [rbp+57h+var_D0], 6
0x1800537ed  lea     rax, [rbp+57h+var_D0]
0x1800537f1  mov     rcx, rbx
0x1800537f4  mov     [rsp+120h+var_F8], rax
0x1800537f9  lea     rsi, aPincomplexity; "PINComplexity"
0x180053800  lea     r8, aMinimumpinleng_0; "MinimumPINLength"
0x180053807  mov     dword ptr [rsp+120h+phkResult], r12d
0x18005380c  lea     edi, [r12-7Bh]
0x180053811  mov     rdx, rsi
0x180053814  mov     r9d, edi
0x180053817  call    PolicyManager__ReadPolicyValue
0x18005381c  lea     rax, [rbp+57h+arg_18]
0x180053820  mov     [rbp+57h+arg_18], r12d
0x180053824  mov     [rsp+120h+var_F8], rax
0x180053829  lea     r8, aMaximumpinleng; "MaximumPINLength"
0x180053830  mov     r9d, edi
0x180053833  mov     dword ptr [rsp+120h+phkResult], r12d
0x180053838  mov     rdx, rsi
0x18005383b  mov     rcx, rbx
0x18005383e  call    PolicyManager__ReadPolicyValue
0x180053843  lea     rax, [rbp+57h+arg_10]
0x180053847  mov     [rbp+57h+arg_10], r15d
0x18005384b  mov     [rsp+120h+var_F8], rax
0x180053850  lea     r8, aUppercaselette; "UppercaseLetters"
0x180053857  xor     r9d, r9d
0x18005385a  mov     dword ptr [rsp+120h+phkResult], r14d
0x18005385f  mov     rdx, rsi
0x180053862  mov     rcx, rbx
0x180053865  xor     r12d, r12d
0x180053868  call    PolicyManager__ReadPolicyValue
0x18005386d  test    eax, eax
0x18005386f  lea     r8, aLowercaselette; "LowercaseLetters"
0x180053876  lea     rax, [rbp+57h+arg_10]
0x18005387a  mov     rdx, rsi
0x18005387d  cmovns  r12d, [rbp+57h+arg_10]
0x180053882  mov     rcx, rbx
0x180053885  mov     [rbp+57h+arg_10], r15d
0x180053889  xor     r9d, r9d
0x18005388c  mov     [rsp+120h+var_F8], rax
0x180053891  xor     r15d, r15d
0x180053894  mov     dword ptr [rsp+120h+phkResult], r14d
0x180053899  call    PolicyManager__ReadPolicyValue
0x18005389e  test    eax, eax
0x1800538a0  lea     r8, aDigits; "Digits"
0x1800538a7  lea     rax, [rbp+57h+arg_10]
0x1800538ab  mov     rdx, rsi
0x1800538ae  cmovns  r15d, [rbp+57h+arg_10]
0x1800538b3  mov     rcx, rbx
0x1800538b6  mov     [rsp+120h+var_F8], rax
0x1800538bb  xor     r14d, r14d
0x1800538be  xor     r9d, r9d
0x1800538c1  mov     [rbp+57h+arg_10], 0FFFFFFFFh
0x1800538c8  lea     edi, [r14+2]
0x1800538cc  mov     dword ptr [rsp+120h+phkResult], edi
0x1800538d0  call    PolicyManager__ReadPolicyValue
0x1800538d5  test    eax, eax
0x1800538d7  lea     r8, aSpecialcharact; "SpecialCharacters"
0x1800538de  lea     rax, [rbp+57h+arg_10]
0x1800538e2  mov     rcx, rbx
0x1800538e5  cmovns  r14d, [rbp+57h+arg_10]
0x1800538ea  lea     rdx, aPincomplexity; "PINComplexity"
0x1800538f1  mov     [rsp+120h+var_F8], rax
0x1800538f6  xor     r9d, r9d
0x1800538f9  mov     [rbp+57h+arg_10], 0FFFFFFFFh
0x180053900  xor     esi, esi
0x180053902  mov     dword ptr [rsp+120h+phkResult], edi
0x180053906  call    PolicyManager__ReadPolicyValue
0x18005390b  test    eax, eax
0x18005390d  lea     r8, aHistory; "History"
0x180053914  lea     rax, [rbp+57h+arg_10]
0x180053918  mov     rcx, rbx
0x18005391b  cmovns  esi, [rbp+57h+arg_10]
0x18005391f  lea     rdx, aPincomplexity; "PINComplexity"
0x180053926  mov     [rsp+120h+var_F8], rax
0x18005392b  xor     r9d, r9d
0x18005392e  mov     [rbp+57h+arg_10], 0FFFFFFFFh
0x180053935  xor     edi, edi
0x180053937  mov     dword ptr [rsp+120h+phkResult], 32h ; '2'
0x18005393f  call    PolicyManager__ReadPolicyValue
0x180053944  test    eax, eax
0x180053946  cmovns  edi, [rbp+57h+arg_10]
0x18005394a  lea     rax, [rbp+57h+arg_10]
0x18005394e  mov     rcx, [rbp+57h+arg_0]
0x180053952  lea     r8, aExpiration; "Expiration"
0x180053959  mov     [rsp+120h+var_F8], rax
0x18005395e  lea     rdx, aPincomplexity; "PINComplexity"
0x180053965  xor     r9d, r9d
0x180053968  mov     dword ptr [rsp+120h+phkResult], 2DAh
0x180053970  mov     [rbp+57h+arg_10], 0FFFFFFFFh
0x180053977  xor     ebx, ebx
0x180053979  call    PolicyManager__ReadPolicyValue
0x18005397e  mov     r8d, [rbp+57h+arg_18]
0x180053982  xor     ecx, ecx
0x180053984  mov     edx, [rbp+57h+var_D0]
0x180053987  test    eax, eax
0x180053989  mov     [rbp+57h+var_70], cl
0x18005398c  xorps   xmm0, xmm0
0x18005398f  cmovns  ebx, [rbp+57h+arg_10]
0x180053993  mov     r9d, r12d
0x180053996  mov     [rsp+120h+var_D8], ebx
0x18005399a  mov     [rsp+120h+var_E0], edi
0x18005399e  xor     edi, edi
0x1800539a0  mov     [rsp+120h+var_E8], edi
0x1800539a4  mov     [rsp+120h+var_F0], esi
0x1800539a8  mov     [rbp+57h+var_48], ecx
0x1800539ab  lea     rcx, [rbp+57h+var_70]
0x1800539af  mov     dword ptr [rsp+120h+var_F8], r14d
0x1800539b4  mov     dword ptr [rsp+120h+phkResult], r15d
0x1800539b9  mov     [rbp+57h+var_6C], 8
0x1800539c0  mov     [rbp+57h+var_68], 7Fh
0x1800539c7  movups  [rbp+57h+var_64], xmm0
0x1800539cb  mov     [rbp+57h+var_54], 2
0x1800539d2  mov     [rbp+57h+var_50], 1
0x1800539da  call    ?Initialize@NgcPinPolicy@NgcPolicy@@QEAAJKKW4_PIN_CHARACTER_POLICY_OPTION@@000HKK@Z; NgcPolicy::NgcPinPolicy::Initialize(ulong,ulong,_PIN_CHARACTER_POLICY_OPTION,_PIN_CHARACTER_POLICY_OPTION,_PIN_CHARACTER_POLICY_OPTION,_PIN_CHARACTER_POLICY_OPTION,int,ulong,ulong)
0x1800539df  mov     ebx, eax
0x1800539e1  test    eax, eax
0x1800539e3  jns     short loc_180053A1E
0x1800539e5  mov     edx, cs:dword_1800BE0B8
0x1800539eb  cmp     edx, 2
0x1800539ee  jbe     loc_180053AB2
0x1800539f4  lea     rdx, word_1800AD556
0x1800539fb  xor     r9d, r9d
0x1800539fe  lea     rax, [rbp+57h+arg_10]
0x180053a02  xor     r8d, r8d
0x180053a05  mov     [rsp+120h+phkResult], rax
0x180053a0a  lea     rcx, dword_1800BE0B8
0x180053a11  mov     [rbp+57h+arg_10], ebx
0x180053a14  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180053a19  jmp     loc_180053AB2
0x180053a1e  mov     r9d, [rbp+57h+var_B8]
0x180053a22  lea     rcx, [rbp+57h+var_B0]
0x180053a26  mov     edx, [rbp+57h+var_B4]
0x180053a29  mov     eax, 1
0x180053a2e  mov     dword ptr [rbp+57h+var_B0+4], eax
0x180053a31  xorps   xmm0, xmm0
0x180053a34  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180053a38  mov     r8d, r13d
0x180053a3b  mov     qword ptr [rbp+57h+var_84+4], rax
0x180053a3f  lea     rax, [rbp+57h+var_70]
0x180053a43  mov     [rsp+120h+phkResult], rax
0x180053a48  mov     byte ptr [rbp+57h+var_B0], dil
0x180053a4c  mov     byte ptr [rbp+57h+var_A0], dil
0x180053a50  mov     dword ptr [rbp+57h+var_A0+4], 8
0x180053a57  mov     dword ptr [rbp+57h+var_A0+8], 7Fh
0x180053a5e  movdqu  [rbp+57h+var_A0+0Ch], xmm0
0x180053a63  mov     dword ptr [rbp+57h+var_84], 2
0x180053a6a  mov     dword ptr [rbp+57h+var_84+0Ch], edi
0x180053a6d  call    ?Initialize@NgcPolicy@1@QEAAJW4_NGC_BIOMETRICS_POLICY@@W4_NGC_SMART_CARD_POLICY@@W4_NGC_HARDWARE_POLICY@@AEBVNgcPinPolicy@1@@Z; NgcPolicy::NgcPolicy::Initialize(_NGC_BIOMETRICS_POLICY,_NGC_SMART_CARD_POLICY,_NGC_HARDWARE_POLICY,NgcPolicy::NgcPinPolicy const &)
0x180053a72  mov     ebx, eax
0x180053a74  test    eax, eax
0x180053a76  jns     short loc_180053A8F
0x180053a78  mov     ecx, cs:dword_1800BE0B8
0x180053a7e  cmp     ecx, 2
0x180053a81  jbe     short loc_180053AB2
0x180053a83  lea     rdx, byte_1800AD5B5
0x180053a8a  jmp     loc_1800539FB
0x180053a8f  mov     rax, [rbp+57h+arg_8]
0x180053a93  movups  xmm0, [rbp+57h+var_B0]
0x180053a97  movups  xmm1, [rbp+57h+var_A0]
0x180053a9b  movups  xmmword ptr [rax], xmm0
0x180053a9e  movups  xmm0, xmmword ptr [rbp-39h]
0x180053aa2  movups  xmmword ptr [rax+10h], xmm1
0x180053aa6  movups  xmm1, [rbp+57h+var_84]
0x180053aaa  movups  xmmword ptr [rax+20h], xmm0
0x180053aae  movups  xmmword ptr [rax+2Ch], xmm1
0x180053ab2  lea     rax, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x180053ab9  lea     rcx, [rbp+57h+var_C8]
0x180053abd  mov     [rbp+57h+var_C8], rax
0x180053ac1  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180053ac6  mov     eax, ebx
0x180053ac8  add     rsp, 0E8h
0x180053acf  pop     r15
0x180053ad1  pop     r14
0x180053ad3  pop     r13
0x180053ad5  pop     r12
0x180053ad7  pop     rdi
0x180053ad8  pop     rsi
0x180053ad9  pop     rbx
0x180053ada  pop     rbp
0x180053adb  retn
```
