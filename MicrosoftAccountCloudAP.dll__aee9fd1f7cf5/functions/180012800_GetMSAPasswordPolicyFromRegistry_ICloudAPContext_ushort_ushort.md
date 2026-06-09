# GetMSAPasswordPolicyFromRegistry(ICloudAPContext *,ushort *,ushort *)

- ea: `0x180012800`
- end: `0x18001291c`
- name: `?GetMSAPasswordPolicyFromRegistry@@YAJPEAVICloudAPContext@@PEAG1@Z`
- size: `284`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180013c0c`

## callees

- `0x180008440`
- `0x18000baac`
- `0x180012800`
- `0x180026c8c`
- `0x180029c18`
- `0x180032010`

## string_xrefs

- `0x180012867`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x1800128b4`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180012838`: `GetMSAPasswordPolicyFromRegistry`
- `0x18001289c`: `hr = registryHelper.ReadDwordFromRegistry(HKEY_USERS, WLID_REG_SYSTEM_USER_IDCRL_PATH, WLID_REG_PROVIDER_DEFAULT_PASSWORD_LENGTH, &providerPasswordLength)`
- `0x1800128e2`: `hr = registryHelper.ReadDwordFromRegistry(HKEY_USERS, WLID_REG_SYSTEM_USER_IDCRL_PATH, WLID_REG_PROVIDER_DEFAULT_PASSWORD_CHARACTER_GROUPS, &providerPasswordCharacterGroups)`

## pseudocode

```c
__int64 __fastcall GetMSAPasswordPolicyFromRegistry(
        struct ICloudAPContext *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  int v11; // r8d
  int v12; // eax
  unsigned int v13; // ebx
  char *v15; // [rsp+20h] [rbp-38h]
  bool v16; // [rsp+20h] [rbp-38h]
  bool v17; // [rsp+20h] [rbp-38h]
  _QWORD v18[5]; // [rsp+30h] [rbp-28h] BYREF
  int v19; // [rsp+80h] [rbp+28h] BYREF
  int v20; // [rsp+88h] [rbp+30h] BYREF
  int v21; // [rsp+90h] [rbp+38h] BYREF
  __int64 v22; // [rsp+98h] [rbp+40h] BYREF

  v19 = 0;
  v22 = (*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 8LL))(a1);
  v20 = 0;
  v21 = 0;
  v18[0] = "GetMSAPasswordPolicyFromRegistry";
  v18[1] = &v19;
  v18[2] = 0;
  v18[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    "GetMSAPasswordPolicyFromRegistry",
    (const char *)0x69F,
    0,
    (const unsigned __int16 *)v15);
  *a2 = 0;
  *a3 = 0;
  v7 = RegistryHelper::ReadValueFromRegistry<unsigned long>(&v22, v5, v6, (__int64)L"ProviderPasswordLength", v16, &v20);
  v19 = v7;
  if ( v7 >= 0 )
  {
    v12 = RegistryHelper::ReadValueFromRegistry<unsigned long>(
            &v22,
            v8,
            v9,
            (__int64)L"ProviderPasswordCharacterGroups",
            v17,
            &v21);
    v19 = v12;
    if ( v12 >= 0 )
    {
      *a2 = v20;
      *a3 = v21;
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
        "GetMSAPasswordPolicyFromRegistry",
        0x6ACu,
        v12,
        "hr = registryHelper.ReadDwordFromRegistry(HKEY_USERS, WLID_REG_SYSTEM_USER_IDCRL_PATH, WLID_REG_PROVIDER_DEFAULT"
        "_PASSWORD_CHARACTER_GROUPS, &providerPasswordCharacterGroups)");
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
      "GetMSAPasswordPolicyFromRegistry",
      0x6A7u,
      v7,
      "hr = registryHelper.ReadDwordFromRegistry(HKEY_USERS, WLID_REG_SYSTEM_USER_IDCRL_PATH, WLID_REG_PROVIDER_DEFAULT_P"
      "ASSWORD_LENGTH, &providerPasswordLength)");
  }
  v13 = v19;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v18, v10, v11);
  return v13;
}

```

## disassembly

```asm
0x180012800  push    rbp
0x180012802  push    rbx
0x180012803  push    rdi
0x180012804  push    r14
0x180012806  mov     rbp, rsp
0x180012809  sub     rsp, 58h
0x18001280d  mov     rbx, r8
0x180012810  mov     rdi, rdx
0x180012813  mov     [rbp+arg_0], 0
0x18001281a  mov     rax, [rcx]
0x18001281d  mov     rax, [rax+8]
0x180012821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012826  mov     [rbp+arg_18], rax
0x18001282a  mov     [rbp+arg_8], 0
0x180012831  mov     [rbp+arg_10], 0
0x180012838  lea     r14, aGetmsapassword; "GetMSAPasswordPolicyFromRegistry"
0x18001283f  mov     [rbp+var_28], r14
0x180012843  lea     rax, [rbp+arg_0]
0x180012847  mov     [rbp+var_20], rax
0x18001284b  mov     [rbp+var_18], 0
0x180012853  mov     [rbp+var_10], 0
0x18001285b  xor     r9d, r9d; unsigned int
0x18001285e  mov     r8d, 69Fh; char *
0x180012864  mov     rdx, r14; char *
0x180012867  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18001286e  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180012873  nop
0x180012874  xor     eax, eax
0x180012876  mov     [rdi], ax
0x180012879  mov     [rbx], ax
0x18001287c  lea     rax, [rbp+arg_8]
0x180012880  mov     [rsp+58h+var_30], rax
0x180012885  lea     r9, aProviderpasswo_0; "ProviderPasswordLength"
0x18001288c  lea     rcx, [rbp+arg_18]
0x180012890  call    ??$ReadValueFromRegistry@K@RegistryHelper@@AEAAJPEAUHKEY__@@PEBG1KPEAK@Z; RegistryHelper::ReadValueFromRegistry<ulong>(HKEY__ *,ushort const *,ushort const *,ulong,ulong *)
0x180012895  mov     [rbp+arg_0], eax
0x180012898  test    eax, eax
0x18001289a  jns     short loc_1800128C2
0x18001289c  lea     r8, aHrRegistryhelp_0; "hr = registryHelper.ReadDwordFromRegist"...
0x1800128a3  mov     [rsp+58h+var_38], r8; char *
0x1800128a8  mov     r8d, 6A7h; unsigned int
0x1800128ae  mov     r9d, eax; int
0x1800128b1  mov     rdx, r14; char *
0x1800128b4  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x1800128bb  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800128c0  jmp     short loc_180012904
0x1800128c2  lea     rax, [rbp+arg_10]
0x1800128c6  mov     [rsp+58h+var_30], rax
0x1800128cb  lea     r9, aProviderpasswo; "ProviderPasswordCharacterGroups"
0x1800128d2  lea     rcx, [rbp+arg_18]
0x1800128d6  call    ??$ReadValueFromRegistry@K@RegistryHelper@@AEAAJPEAUHKEY__@@PEBG1KPEAK@Z; RegistryHelper::ReadValueFromRegistry<ulong>(HKEY__ *,ushort const *,ushort const *,ulong,ulong *)
0x1800128db  mov     [rbp+arg_0], eax
0x1800128de  test    eax, eax
0x1800128e0  jns     short loc_1800128F6
0x1800128e2  lea     rcx, aHrRegistryhelp_2; "hr = registryHelper.ReadDwordFromRegist"...
0x1800128e9  mov     [rsp+58h+var_38], rcx
0x1800128ee  mov     r8d, 6ACh
0x1800128f4  jmp     short loc_1800128AE
0x1800128f6  movzx   eax, word ptr [rbp+arg_8]
0x1800128fa  mov     [rdi], ax
0x1800128fd  movzx   eax, word ptr [rbp+arg_10]
0x180012901  mov     [rbx], ax
0x180012904  mov     ebx, [rbp+arg_0]
0x180012907  lea     rcx, [rbp+var_28]
0x18001290b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180012910  mov     eax, ebx
0x180012912  add     rsp, 58h
0x180012916  pop     r14
0x180012918  pop     rdi
0x180012919  pop     rbx
0x18001291a  pop     rbp
0x18001291b  retn
```
