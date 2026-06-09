# CWwanDataExecutorState::ReadPerDevice5GSAConfig(void)

- ea: `0x18003f90c`
- end: `0x18003fbac`
- name: `?ReadPerDevice5GSAConfig@CWwanDataExecutorState@@AEAAXXZ`
- size: `672`
- prototype: `void __fastcall(CWwanDataExecutorState *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18003a1c4`

## callees

- `0x180008abc`
- `0x180010e94`
- `0x1800117a8`
- `0x180011a1c`
- `0x180012300`
- `0x180014b5c`
- `0x180014f1c`
- `0x180016c50`
- `0x18003f90c`

## string_xrefs

- `0x18003fa18`: `Reg sub path %s or value %s not present`
- `0x18003faad`: `Reg sub path %s or value %s not present`
- `0x18003fb31`: `Reg sub path %s or value %s not present`
- `0x18003f99d`: `Failed to read Reg sub path %s or value %s (err 0x%x)`
- `0x18003fa41`: `Failed to read Reg sub path %s or value %s (err 0x%x)`
- `0x18003fac8`: `Failed to read Reg sub path %s or value %s (err 0x%x)`
- `0x18003fb4c`: `Failed to read Reg sub path %s or value %s (err 0x%x)`
- `0x18003f9d4`: `Reg sub path %s value %s contains %d`
- `0x18003fa6b`: `Reg sub path %s value %s contains %d`
- `0x18003faf0`: `Reg sub path %s value %s contains %d`
- `0x18003fb74`: `Reg sub path %s value %s contains %d`
- `0x18003f958`: `DefaultNetworkSliceServiceType`
- `0x18003f97f`: `CWwanDataExecutorState::ReadPerDevice5GSAConfig`
- `0x18003f9a4`: `CWwanDataExecutorState::ReadPerDevice5GSAConfig`
- `0x18003f9bf`: `CWwanDataExecutorState::ReadPerDevice5GSAConfig`
- `0x18003fa5d`: `Reg sub path %s value %s contains invalid data %d`
- `0x18003fae2`: `Reg sub path %s value %s contains invalid data %d`
- `0x18003fb66`: `Reg sub path %s value %s contains invalid data %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWwanDataExecutorState::ReadPerDevice5GSAConfig(CWwanDataExecutorState *this)
{
  __int64 v2; // rax
  unsigned int DWORD; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  const unsigned __int16 *v7; // [rsp+20h] [rbp-10h]
  __int64 v8; // [rsp+28h] [rbp-8h]
  unsigned int v9; // [rsp+58h] [rbp+28h] BYREF
  StateSeparation *v10; // [rsp+60h] [rbp+30h] BYREF

  v9 = 0;
  v10 = (StateSeparation *)operator new(0x20u);
  v2 = StateSeparation::StateSeparation(v10, 2);
  std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(&v10, v2);
  DWORD = StateSeparation::GetDWORD(v10, L"ParametersFor5GSA", L"DefaultNetworkSliceServiceType", &v9);
  if ( DWORD == 2 )
  {
    WwanLog::Verbose(
      "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
      0,
      L"Reg sub path %s or value %s not present",
      L"ParametersFor5GSA",
      L"DefaultNetworkSliceServiceType");
    goto LABEL_15;
  }
  if ( DWORD )
  {
    WwanLog::Error(
      "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
      0,
      L"Failed to read Reg sub path %s or value %s (err 0x%x)",
      L"ParametersFor5GSA",
      L"DefaultNetworkSliceServiceType",
      DWORD);
    goto LABEL_15;
  }
  LODWORD(v8) = v9;
  v7 = L"DefaultNetworkSliceServiceType";
  if ( v9 <= 0xFF )
  {
    WwanLog::Info(
      "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
      0,
      L"Reg sub path %s value %s contains %d",
      L"ParametersFor5GSA",
      L"DefaultNetworkSliceServiceType",
      v9);
    *((_DWORD *)this + 4087) |= 1u;
    *((_WORD *)this + 8176) = (unsigned __int8)v9;
    v4 = StateSeparation::GetDWORD(v10, L"ParametersFor5GSA", L"DefaultNetworkSliceDifferentiator", &v9);
    if ( v4 == 2 )
    {
      WwanLog::Verbose(
        "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
        0,
        L"Reg sub path %s or value %s not present",
        L"ParametersFor5GSA",
        L"DefaultNetworkSliceDifferentiator");
      goto LABEL_15;
    }
    if ( v4 )
    {
      LODWORD(v8) = v4;
      WwanLog::Error(
        "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
        0,
        L"Failed to read Reg sub path %s or value %s (err 0x%x)",
        L"ParametersFor5GSA",
        L"DefaultNetworkSliceDifferentiator",
        v8);
      goto LABEL_15;
    }
    LODWORD(v8) = v9;
    v7 = L"DefaultNetworkSliceDifferentiator";
    if ( v9 <= 0xFF )
    {
      WwanLog::Info(
        "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
        0,
        L"Reg sub path %s value %s contains %d",
        L"ParametersFor5GSA",
        L"DefaultNetworkSliceDifferentiator",
        v8);
      *((_DWORD *)this + 4089) = (unsigned __int8)v9;
      goto LABEL_15;
    }
  }
  WwanLog::Error(
    "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
    0,
    L"Reg sub path %s value %s contains invalid data %d",
    L"ParametersFor5GSA",
    v7,
    v8);
LABEL_15:
  v5 = StateSeparation::GetDWORD(v10, L"ParametersFor5GSA", L"ForcedReRegisterWhenNeeded", &v9);
  if ( v5 == 2 )
  {
    WwanLog::Verbose(
      "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
      0,
      L"Reg sub path %s or value %s not present",
      L"ParametersFor5GSA",
      L"ForcedReRegisterWhenNeeded");
  }
  else if ( v5 )
  {
    LODWORD(v8) = v5;
    WwanLog::Error(
      "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
      0,
      L"Failed to read Reg sub path %s or value %s (err 0x%x)",
      L"ParametersFor5GSA",
      L"ForcedReRegisterWhenNeeded",
      v8);
  }
  else
  {
    LODWORD(v8) = v9;
    if ( v9 <= 1 )
    {
      WwanLog::Info(
        "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
        0,
        L"Reg sub path %s value %s contains %d",
        L"ParametersFor5GSA",
        L"ForcedReRegisterWhenNeeded",
        v8);
      *((_DWORD *)this + 4091) = v9;
    }
    else
    {
      WwanLog::Error(
        "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
        0,
        L"Reg sub path %s value %s contains invalid data %d",
        L"ParametersFor5GSA",
        L"ForcedReRegisterWhenNeeded",
        v8);
    }
  }
  v6 = StateSeparation::GetDWORD(v10, L"ParametersFor5GSA", L"COSAInitialRegParamUsed", &v9);
  if ( v6 == 2 )
  {
    WwanLog::Verbose(
      "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
      0,
      L"Reg sub path %s or value %s not present",
      L"ParametersFor5GSA",
      L"COSAInitialRegParamUsed");
  }
  else if ( v6 )
  {
    LODWORD(v8) = v6;
    WwanLog::Error(
      "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
      0,
      L"Failed to read Reg sub path %s or value %s (err 0x%x)",
      L"ParametersFor5GSA",
      L"COSAInitialRegParamUsed",
      v8);
  }
  else
  {
    LODWORD(v8) = v9;
    if ( v9 < 2 )
    {
      WwanLog::Info(
        "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
        0,
        L"Reg sub path %s value %s contains %d",
        L"ParametersFor5GSA",
        L"COSAInitialRegParamUsed",
        v8);
      *((_DWORD *)this + 4092) = v9 == 1;
    }
    else
    {
      WwanLog::Error(
        "CWwanDataExecutorState::ReadPerDevice5GSAConfig",
        0,
        L"Reg sub path %s value %s contains invalid data %d",
        L"ParametersFor5GSA",
        L"COSAInitialRegParamUsed",
        v8);
    }
  }
  std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(&v10);
}

```

## disassembly

```asm
0x18003f90c  mov     [rsp-18h+arg_0], rsi
0x18003f911  mov     [rsp-18h+arg_18], rdi
0x18003f916  push    rbp
0x18003f917  push    r14
0x18003f919  push    r15
0x18003f91b  mov     rbp, rsp
0x18003f91e  sub     rsp, 30h
0x18003f922  mov     rsi, rcx
0x18003f925  mov     [rbp+arg_8], 0
0x18003f92c  mov     ecx, 20h ; ' '; Size
0x18003f931  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f936  mov     [rbp+arg_10], rax
0x18003f93a  mov     edx, 2
0x18003f93f  mov     rcx, rax
0x18003f942  call    ??0StateSeparation@@QEAA@W4_REG_ROOT_PATH@@@Z; StateSeparation::StateSeparation(_REG_ROOT_PATH)
0x18003f947  nop
0x18003f948  mov     rdx, rax
0x18003f94b  lea     rcx, [rbp+arg_10]
0x18003f94f  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x18003f954  lea     r9, [rbp+arg_8]; unsigned int *
0x18003f958  lea     rdi, aDefaultnetwork; "DefaultNetworkSliceServiceType"
0x18003f95f  mov     r8, rdi; unsigned __int16 *
0x18003f962  lea     r14, aParametersfor5; "ParametersFor5GSA"
0x18003f969  mov     rdx, r14; unsigned __int16 *
0x18003f96c  mov     rcx, [rbp+arg_10]; this
0x18003f970  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18003f975  cmp     eax, 2
0x18003f978  jnz     short loc_18003F98B
0x18003f97a  mov     [rsp+30h+var_10], rdi
0x18003f97f  lea     rdi, aCwwandataexecu_66; "CWwanDataExecutorState::ReadPerDevice5G"...
0x18003f986  jmp     loc_18003FA16
0x18003f98b  mov     r9, r14
0x18003f98e  xor     edx, edx; struct _GUID *
0x18003f990  test    eax, eax
0x18003f992  jz      short loc_18003F9B3
0x18003f994  mov     dword ptr [rsp+30h+var_8], eax
0x18003f998  mov     [rsp+30h+var_10], rdi
0x18003f99d  lea     r8, aFailedToReadRe; "Failed to read Reg sub path %s or value"...
0x18003f9a4  lea     rdi, aCwwandataexecu_66; "CWwanDataExecutorState::ReadPerDevice5G"...
0x18003f9ab  mov     rcx, rdi
0x18003f9ae  jmp     loc_18003FA64
0x18003f9b3  mov     eax, [rbp+arg_8]
0x18003f9b6  mov     dword ptr [rsp+30h+var_8], eax
0x18003f9ba  mov     [rsp+30h+var_10], rdi
0x18003f9bf  lea     rdi, aCwwandataexecu_66; "CWwanDataExecutorState::ReadPerDevice5G"...
0x18003f9c6  mov     rcx, rdi; char *
0x18003f9c9  cmp     eax, 0FFh
0x18003f9ce  ja      loc_18003FA5D
0x18003f9d4  lea     r8, aRegSubPathSVal_1; "Reg sub path %s value %s contains %d"
0x18003f9db  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003f9e0  or      dword ptr [rsi+3FDCh], 1
0x18003f9e7  movzx   eax, byte ptr [rbp+arg_8]
0x18003f9eb  mov     [rsi+3FE0h], ax
0x18003f9f2  lea     r9, [rbp+arg_8]; unsigned int *
0x18003f9f6  lea     r15, aDefaultnetwork_0; "DefaultNetworkSliceDifferentiator"
0x18003f9fd  mov     r8, r15; unsigned __int16 *
0x18003fa00  mov     rdx, r14; unsigned __int16 *
0x18003fa03  mov     rcx, [rbp+arg_10]; this
0x18003fa07  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18003fa0c  cmp     eax, 2
0x18003fa0f  jnz     short loc_18003FA2C
0x18003fa11  mov     [rsp+30h+var_10], r15
0x18003fa16  xor     edx, edx; struct _GUID *
0x18003fa18  lea     r8, aRegSubPathSOrV; "Reg sub path %s or value %s not present"
0x18003fa1f  mov     r9, r14
0x18003fa22  mov     rcx, rdi; char *
0x18003fa25  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18003fa2a  jmp     short loc_18003FA81
0x18003fa2c  mov     r9, r14
0x18003fa2f  xor     edx, edx; struct _GUID *
0x18003fa31  mov     rcx, rdi; char *
0x18003fa34  test    eax, eax
0x18003fa36  jz      short loc_18003FA4A
0x18003fa38  mov     dword ptr [rsp+30h+var_8], eax
0x18003fa3c  mov     [rsp+30h+var_10], r15
0x18003fa41  lea     r8, aFailedToReadRe; "Failed to read Reg sub path %s or value"...
0x18003fa48  jmp     short loc_18003FA64
0x18003fa4a  mov     eax, [rbp+arg_8]
0x18003fa4d  mov     dword ptr [rsp+30h+var_8], eax
0x18003fa51  mov     [rsp+30h+var_10], r15
0x18003fa56  cmp     eax, 0FFh
0x18003fa5b  jbe     short loc_18003FA6B
0x18003fa5d  lea     r8, aRegSubPathSVal; "Reg sub path %s value %s contains inval"...
0x18003fa64  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18003fa69  jmp     short loc_18003FA81
0x18003fa6b  lea     r8, aRegSubPathSVal_1; "Reg sub path %s value %s contains %d"
0x18003fa72  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003fa77  movzx   eax, byte ptr [rbp+arg_8]
0x18003fa7b  mov     [rsi+3FE4h], eax
0x18003fa81  lea     r9, [rbp+arg_8]; unsigned int *
0x18003fa85  lea     r15, aForcedreregist; "ForcedReRegisterWhenNeeded"
0x18003fa8c  mov     r8, r15; unsigned __int16 *
0x18003fa8f  mov     rdx, r14; unsigned __int16 *
0x18003fa92  mov     rcx, [rbp+arg_10]; this
0x18003fa96  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18003fa9b  mov     r9, r14
0x18003fa9e  xor     edx, edx; struct _GUID *
0x18003faa0  mov     rcx, rdi; char *
0x18003faa3  cmp     eax, 2
0x18003faa6  jnz     short loc_18003FABB
0x18003faa8  mov     [rsp+30h+var_10], r15
0x18003faad  lea     r8, aRegSubPathSOrV; "Reg sub path %s or value %s not present"
0x18003fab4  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18003fab9  jmp     short loc_18003FB05
0x18003fabb  test    eax, eax
0x18003fabd  jz      short loc_18003FAD1
0x18003fabf  mov     dword ptr [rsp+30h+var_8], eax
0x18003fac3  mov     [rsp+30h+var_10], r15
0x18003fac8  lea     r8, aFailedToReadRe; "Failed to read Reg sub path %s or value"...
0x18003facf  jmp     short loc_18003FAE9
0x18003fad1  mov     eax, [rbp+arg_8]
0x18003fad4  mov     dword ptr [rsp+30h+var_8], eax
0x18003fad8  mov     [rsp+30h+var_10], r15
0x18003fadd  cmp     eax, 1
0x18003fae0  jbe     short loc_18003FAF0
0x18003fae2  lea     r8, aRegSubPathSVal; "Reg sub path %s value %s contains inval"...
0x18003fae9  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18003faee  jmp     short loc_18003FB05
0x18003faf0  lea     r8, aRegSubPathSVal_1; "Reg sub path %s value %s contains %d"
0x18003faf7  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003fafc  mov     eax, [rbp+arg_8]
0x18003faff  mov     [rsi+3FECh], eax
0x18003fb05  lea     r9, [rbp+arg_8]; unsigned int *
0x18003fb09  lea     r15, aCosainitialreg; "COSAInitialRegParamUsed"
0x18003fb10  mov     r8, r15; unsigned __int16 *
0x18003fb13  mov     rdx, r14; unsigned __int16 *
0x18003fb16  mov     rcx, [rbp+arg_10]; this
0x18003fb1a  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18003fb1f  mov     r9, r14
0x18003fb22  xor     edx, edx; struct _GUID *
0x18003fb24  mov     rcx, rdi; char *
0x18003fb27  cmp     eax, 2
0x18003fb2a  jnz     short loc_18003FB3F
0x18003fb2c  mov     [rsp+30h+var_10], r15
0x18003fb31  lea     r8, aRegSubPathSOrV; "Reg sub path %s or value %s not present"
0x18003fb38  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18003fb3d  jmp     short loc_18003FB8F
0x18003fb3f  test    eax, eax
0x18003fb41  jz      short loc_18003FB55
0x18003fb43  mov     dword ptr [rsp+30h+var_8], eax
0x18003fb47  mov     [rsp+30h+var_10], r15
0x18003fb4c  lea     r8, aFailedToReadRe; "Failed to read Reg sub path %s or value"...
0x18003fb53  jmp     short loc_18003FB6D
0x18003fb55  mov     eax, [rbp+arg_8]
0x18003fb58  mov     dword ptr [rsp+30h+var_8], eax
0x18003fb5c  mov     [rsp+30h+var_10], r15
0x18003fb61  cmp     eax, 2
0x18003fb64  jb      short loc_18003FB74
0x18003fb66  lea     r8, aRegSubPathSVal; "Reg sub path %s value %s contains inval"...
0x18003fb6d  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18003fb72  jmp     short loc_18003FB8F
0x18003fb74  lea     r8, aRegSubPathSVal_1; "Reg sub path %s value %s contains %d"
0x18003fb7b  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003fb80  xor     eax, eax
0x18003fb82  cmp     [rbp+arg_8], 1
0x18003fb86  setz    al
0x18003fb89  mov     [rsi+3FF0h], eax
0x18003fb8f  lea     rcx, [rbp+arg_10]
0x18003fb93  call    ??1?$unique_ptr@VStateSeparation@@U?$default_delete@VStateSeparation@@@std@@@std@@QEAA@XZ; std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(void)
0x18003fb98  mov     rsi, [rsp+30h+arg_0]
0x18003fb9d  mov     rdi, [rsp+30h+arg_18]
0x18003fba2  add     rsp, 30h
0x18003fba6  pop     r15
0x18003fba8  pop     r14
0x18003fbaa  pop     rbp
0x18003fbab  retn
```
