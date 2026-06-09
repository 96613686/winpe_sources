# CTSSDFarmRpc::OnLogon(_SN_ONLOGON_PARAMS *)

- ea: `0x180039bb0`
- end: `0x180039dc1`
- name: `?OnLogon@CTSSDFarmRpc@@EEAAJPEAU_SN_ONLOGON_PARAMS@@@Z`
- size: `529`
- prototype: `__int64 __fastcall(CTSSDFarmRpc *__hidden this, struct _SN_ONLOGON_PARAMS *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180003f30`
- `0x180005190`
- `0x180012630`
- `0x180012a90`
- `0x180012be0`
- `0x180012d7c`
- `0x1800130a8`
- `0x180039bb0`
- `0x18003a028`
- `0x18005a80c`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039d6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039d6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039d83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039d83`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180039d51`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180039d51`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180039d1a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180039d1a`

## string_xrefs

- `0x180039c4a`: `OpenKey REG_TS_CLUSTERSETTINGS failed: 0x%x in %s`
- `0x180039cb2`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x180039c97`: `ReadRegString TSSDFARM_ADDED_USER failed: 0x%x in %s`
- `0x180039d3d`: `ConvertSidToStringSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSDFarmRpc::OnLogon(CTSSDFarmRpc *this, struct _SN_ONLOGON_PARAMS *a2)
{
  int v3; // eax
  signed int v4; // ebx
  const char *v5; // rdx
  int v6; // eax
  int ClientToken; // eax
  int InstanceOfUserName; // eax
  struct IUserName *v9; // rdi
  signed int LastError; // eax
  const unsigned __int16 *v12; // [rsp+20h] [rbp-60h]
  LPWSTR StringSid; // [rsp+30h] [rbp-50h] BYREF
  void *v14; // [rsp+38h] [rbp-48h] BYREF
  struct IUserName *v15; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpString2; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v17[2]; // [rsp+50h] [rbp-30h] BYREF
  int v18; // [rsp+60h] [rbp-20h]
  __int64 v19; // [rsp+68h] [rbp-18h]
  int v20; // [rsp+70h] [rbp-10h]
  int v21; // [rsp+74h] [rbp-Ch]
  unsigned int v22; // [rsp+B0h] [rbp+30h] BYREF
  PSID Sid; // [rsp+B8h] [rbp+38h] BYREF

  v15 = 0;
  v17[0] = &CRegistry::`vftable';
  StringSid = 0;
  v20 = -1;
  v21 = -1;
  Sid = 0;
  v17[1] = 0;
  v18 = 0;
  v19 = 0;
  lpString2 = 0;
  v14 = 0;
  v3 = CRegistry::OpenKey(
         (CRegistry *)v17,
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\ClusterSettings",
         0x20019u,
         v12);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = "OpenKey REG_TS_CLUSTERSETTINGS failed: 0x%x in %s";
LABEL_6:
      _DbgPrintMessage(8, v5, (unsigned int)v4, "CTSSDFarmRpc::OnLogon");
      goto LABEL_26;
    }
  }
  v6 = CRegistry::ReadRegString((CRegistry *)v17, L"AddedRDSUser", (unsigned __int16 **)&lpString2, &v22);
  v4 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v4 = (unsigned __int16)v6 | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = "ReadRegString TSSDFARM_ADDED_USER failed: 0x%x in %s";
      goto LABEL_6;
    }
  }
  ClientToken = CRpcUtils::GetClientToken(&v14);
  v4 = ClientToken;
  if ( ClientToken < 0 )
  {
    _DbgPrintMessage(
      8,
      "CRpcUtils::GetClientToken failed: 0x%x in %s",
      (unsigned int)ClientToken,
      "CTSSDFarmRpc::OnLogon");
    goto LABEL_26;
  }
  InstanceOfUserName = CUtils::GetInstanceOfUserName(&v15);
  v4 = InstanceOfUserName;
  if ( InstanceOfUserName < 0
    || (v9 = v15,
        InstanceOfUserName = (*(__int64 (__fastcall **)(struct IUserName *, void *, _QWORD))(*(_QWORD *)v15 + 24LL))(
                               v15,
                               v14,
                               0),
        v4 = InstanceOfUserName,
        InstanceOfUserName < 0)
    || (InstanceOfUserName = (*(__int64 (__fastcall **)(struct IUserName *, PSID *))(*(_QWORD *)v9 + 72LL))(v9, &Sid),
        v4 = InstanceOfUserName,
        InstanceOfUserName < 0) )
  {
    _DbgPrintMessage(
      8,
      "CRpcUtils::GetInstanceOfUserName failed: 0x%x in %s",
      (unsigned int)InstanceOfUserName,
      "CTSSDFarmRpc::OnLogon");
    goto LABEL_26;
  }
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = "ConvertSidToStringSid failed: 0x%x in %s";
      goto LABEL_6;
    }
  }
  if ( !lstrcmpiW(StringSid, lpString2) )
    CTSSDFarmRpc::StopConnectionMonitoringTimer(this);
LABEL_26:
  if ( Sid )
  {
    CoTaskMemFree(Sid);
    Sid = 0;
  }
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&v14);
  CRegistry::~CRegistry((CRegistry *)v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180039bb0  mov     [rsp-18h+arg_0], rbx
0x180039bb5  push    rbp
0x180039bb6  push    rsi
0x180039bb7  push    rdi
0x180039bb8  mov     rbp, rsp
0x180039bbb  sub     rsp, 80h
0x180039bc2  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180039bc9  mov     [rbp+var_40], 0
0x180039bd1  mov     [rbp+var_30], rax
0x180039bd5  lea     r8, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180039bdc  or      eax, 0FFFFFFFFh
0x180039bdf  mov     [rbp+StringSid], 0
0x180039be7  mov     rsi, rcx
0x180039bea  mov     [rbp+var_10], eax
0x180039bed  mov     r9d, 20019h; unsigned int
0x180039bf3  mov     [rbp+var_C], eax
0x180039bf6  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180039bfd  mov     [rbp+Sid], 0
0x180039c05  lea     rcx, [rbp+var_30]; this
0x180039c09  mov     [rbp+var_28], 0
0x180039c11  mov     [rbp+var_20], 0
0x180039c18  mov     [rbp+var_18], 0
0x180039c20  mov     [rbp+lpString2], 0
0x180039c28  mov     [rbp+var_48], 0
0x180039c30  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180039c35  mov     ebx, eax
0x180039c37  test    eax, eax
0x180039c39  jz      short loc_180039C6A
0x180039c3b  jle     short loc_180039C46
0x180039c3d  movzx   ebx, ax
0x180039c40  or      ebx, 80070000h
0x180039c46  test    ebx, ebx
0x180039c48  jns     short loc_180039C6A
0x180039c4a  lea     rdx, aOpenkeyRegTsCl; "OpenKey REG_TS_CLUSTERSETTINGS failed: "...
0x180039c51  mov     r8d, ebx
0x180039c54  lea     r9, aCtssdfarmrpcOn; "CTSSDFarmRpc::OnLogon"
0x180039c5b  mov     ecx, 8; int
0x180039c60  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180039c65  jmp     loc_180039D63
0x180039c6a  lea     r9, [rbp+arg_10]; unsigned int *
0x180039c6e  lea     r8, [rbp+lpString2]; unsigned __int16 **
0x180039c72  lea     rdx, ValueName; "AddedRDSUser"
0x180039c79  lea     rcx, [rbp+var_30]; this
0x180039c7d  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x180039c82  mov     ebx, eax
0x180039c84  test    eax, eax
0x180039c86  jz      short loc_180039CA0
0x180039c88  jle     short loc_180039C93
0x180039c8a  movzx   ebx, ax
0x180039c8d  or      ebx, 80070000h
0x180039c93  test    ebx, ebx
0x180039c95  jns     short loc_180039CA0
0x180039c97  lea     rdx, aReadregstringT; "ReadRegString TSSDFARM_ADDED_USER faile"...
0x180039c9e  jmp     short loc_180039C51
0x180039ca0  lea     rcx, [rbp+var_48]; void **
0x180039ca4  call    ?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z; CRpcUtils::GetClientToken(void * *,int)
0x180039ca9  mov     ebx, eax
0x180039cab  test    eax, eax
0x180039cad  jns     short loc_180039CBB
0x180039caf  mov     r8d, eax
0x180039cb2  lea     rdx, aCrpcutilsGetcl_4; "CRpcUtils::GetClientToken failed: 0x%x "...
0x180039cb9  jmp     short loc_180039C54
0x180039cbb  lea     rcx, [rbp+var_40]; struct IUserName **
0x180039cbf  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x180039cc4  mov     ebx, eax
0x180039cc6  test    eax, eax
0x180039cc8  jns     short loc_180039CD9
0x180039cca  mov     r8d, eax
0x180039ccd  lea     rdx, aCrpcutilsGetin; "CRpcUtils::GetInstanceOfUserName failed"...
0x180039cd4  jmp     loc_180039C54
0x180039cd9  mov     rdi, [rbp+var_40]
0x180039cdd  xor     r8d, r8d
0x180039ce0  mov     rdx, [rbp+var_48]
0x180039ce4  mov     rcx, rdi
0x180039ce7  mov     rax, [rdi]
0x180039cea  mov     rax, [rax+18h]
0x180039cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039cf3  mov     ebx, eax
0x180039cf5  test    eax, eax
0x180039cf7  js      short loc_180039CCA
0x180039cf9  mov     rax, [rdi]
0x180039cfc  lea     rdx, [rbp+Sid]
0x180039d00  mov     rcx, rdi
0x180039d03  mov     rax, [rax+48h]
0x180039d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d0c  mov     ebx, eax
0x180039d0e  test    eax, eax
0x180039d10  js      short loc_180039CCA
0x180039d12  mov     rcx, [rbp+Sid]; Sid
0x180039d16  lea     rdx, [rbp+StringSid]; StringSid
0x180039d1a  call    cs:__imp_ConvertSidToStringSidW
0x180039d20  test    eax, eax
0x180039d22  jnz     short loc_180039D49
0x180039d24  call    cs:__imp_GetLastError
0x180039d2a  mov     ebx, eax
0x180039d2c  test    eax, eax
0x180039d2e  jle     short loc_180039D39
0x180039d30  movzx   ebx, ax
0x180039d33  or      ebx, 80070000h
0x180039d39  test    ebx, ebx
0x180039d3b  jns     short loc_180039D49
0x180039d3d  lea     rdx, aConvertsidtost_0; "ConvertSidToStringSid failed: 0x%x in %"...
0x180039d44  jmp     loc_180039C51
0x180039d49  mov     rdx, [rbp+lpString2]; lpString2
0x180039d4d  mov     rcx, [rbp+StringSid]; lpString1
0x180039d51  call    cs:__imp_lstrcmpiW
0x180039d57  test    eax, eax
0x180039d59  jnz     short loc_180039D63
0x180039d5b  mov     rcx, rsi; this
0x180039d5e  call    ?StopConnectionMonitoringTimer@CTSSDFarmRpc@@AEAAJXZ; CTSSDFarmRpc::StopConnectionMonitoringTimer(void)
0x180039d63  mov     rcx, [rbp+Sid]; pv
0x180039d67  test    rcx, rcx
0x180039d6a  jz      short loc_180039D7A
0x180039d6c  call    cs:__imp_CoTaskMemFree
0x180039d72  mov     [rbp+Sid], 0
0x180039d7a  mov     rcx, [rbp+StringSid]; hMem
0x180039d7e  test    rcx, rcx
0x180039d81  jz      short loc_180039D91
0x180039d83  call    cs:__imp_LocalFree
0x180039d89  mov     [rbp+StringSid], 0
0x180039d91  lea     rcx, [rbp+var_48]; this
0x180039d95  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x180039d9a  lea     rcx, [rbp+var_30]; this
0x180039d9e  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180039da3  lea     rcx, [rbp+var_40]
0x180039da7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180039dac  mov     eax, ebx
0x180039dae  mov     rbx, [rsp+80h+arg_0]
0x180039db6  add     rsp, 80h
0x180039dbd  pop     rdi
0x180039dbe  pop     rsi
0x180039dbf  pop     rbp
0x180039dc0  retn
```
