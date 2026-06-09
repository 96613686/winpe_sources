# FwSvcPortsEnum::CreateInstance(_tag_FW_PROFILE_TYPE,_tag_FW_RULE * const,ulong,ulong,IEnumVARIANT * *)

- ea: `0x180047de4`
- end: `0x180047edd`
- name: `?CreateInstance@FwSvcPortsEnum@@SAJW4_tag_FW_PROFILE_TYPE@@QEAU_tag_FW_RULE@@KKPEAPEAUIEnumVARIANT@@@Z`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047bb0`
- `0x180047cf0`

## callees

- `0x180047d18`
- `0x180047de4`
- `0x18005e010`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180047e73`
- `fwbase!FwReportReturnError` at `0x180047e82`
- `fwbase!FwReportReturnError` at `0x180047e97`
- `fwbase!FwReportReturnError` at `0x180047eba`
- `fwbase!FwReportReturnError` at `0x180047e73`
- `fwbase!FwReportReturnError` at `0x180047e82`
- `fwbase!FwReportReturnError` at `0x180047e97`
- `fwbase!FwReportReturnError` at `0x180047eba`
- `FWPolicyIOMgr!FwCopyRule` at `0x180047e56`
- `FWPolicyIOMgr!FwCopyRule` at `0x180047e56`

## string_xrefs

- `0x180047e90`: `FwSvcPortsEnum::CreateInstance`
- `0x180047eb3`: `FwSvcPortsEnum::CreateInstance`

## pseudocode

```c
__int64 __fastcall FwSvcPortsEnum::CreateInstance(int a1, _QWORD *a2, int a3, int a4, _QWORD *a5)
{
  int v9; // eax
  _DWORD *v10; // rdi
  unsigned int v11; // ebx
  _QWORD *v12; // r14
  int v13; // eax
  _DWORD *v15; // [rsp+20h] [rbp-58h] BYREF

  v15 = 0;
  *a5 = 0;
  v9 = ATL::CComObject<FwSvcPortsEnum>::CreateInstance(&v15);
  v10 = v15;
  v11 = v9;
  if ( v9 < 0 )
  {
LABEL_7:
    FwReportReturnError("FwSvcPortsEnum::CreateInstance", (unsigned int)v9);
    if ( v10 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v10 + 16LL))(v10);
    return (unsigned int)FwReportReturnError("FwSvcPortsEnum::CreateInstance", v11);
  }
  else
  {
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v15 + 8LL))(v15);
    v11 = 0;
    v10[16] = a4;
    v12 = v10 + 20;
    v10[18] = a1;
    while ( 1 )
    {
      if ( !a2 )
      {
        v10[22] = a3;
        goto LABEL_11;
      }
      v13 = FwCopyRule(a2, v12);
      v11 = v13;
      if ( v13 < 0 )
        break;
      v12 = (_QWORD *)*v12;
      a2 = (_QWORD *)*a2;
    }
    FwReportReturnError("FwSvcPortsEnum::Initialize", (unsigned int)v13);
    v9 = FwReportReturnError("FwSvcPortsEnum::Initialize", v11);
    v11 = v9;
    if ( v9 < 0 )
      goto LABEL_7;
LABEL_11:
    *a5 = v10;
  }
  return v11;
}

```

## disassembly

```asm
0x180047de4  push    rbx
0x180047de6  push    rbp
0x180047de7  push    rsi
0x180047de8  push    rdi
0x180047de9  push    r12
0x180047deb  push    r13
0x180047ded  push    r14
0x180047def  push    r15
0x180047df1  sub     rsp, 38h
0x180047df5  mov     r15, [rsp+78h+arg_20]
0x180047dfd  mov     r13d, ecx
0x180047e00  lea     rcx, [rsp+78h+var_58]
0x180047e05  mov     [rsp+78h+var_58], 0
0x180047e0e  mov     r12d, r9d
0x180047e11  mov     ebp, r8d
0x180047e14  mov     rsi, rdx
0x180047e17  mov     qword ptr [r15], 0
0x180047e1e  call    ?CreateInstance@?$CComObject@VFwSvcPortsEnum@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<FwSvcPortsEnum>::CreateInstance(ATL::CComObject<FwSvcPortsEnum> * *)
0x180047e23  mov     rdi, [rsp+78h+var_58]
0x180047e28  mov     ebx, eax
0x180047e2a  test    eax, eax
0x180047e2c  js      short loc_180047E8E
0x180047e2e  mov     rax, [rdi]
0x180047e31  mov     rcx, rdi
0x180047e34  mov     rax, [rax+8]
0x180047e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e3d  xor     ebx, ebx
0x180047e3f  mov     [rdi+40h], r12d
0x180047e43  lea     r14, [rdi+50h]
0x180047e47  mov     [rdi+48h], r13d
0x180047e4b  test    rsi, rsi
0x180047e4e  jz      short loc_180047EC4
0x180047e50  mov     rdx, r14
0x180047e53  mov     rcx, rsi
0x180047e56  call    cs:__imp_FwCopyRule
0x180047e5c  mov     ebx, eax
0x180047e5e  test    eax, eax
0x180047e60  js      short loc_180047E6A
0x180047e62  mov     r14, [r14]
0x180047e65  mov     rsi, [rsi]
0x180047e68  jmp     short loc_180047E4B
0x180047e6a  mov     edx, ebx
0x180047e6c  lea     rcx, aFwsvcportsenum_1; "FwSvcPortsEnum::Initialize"
0x180047e73  call    cs:__imp_FwReportReturnError
0x180047e79  mov     edx, ebx
0x180047e7b  lea     rcx, aFwsvcportsenum_1; "FwSvcPortsEnum::Initialize"
0x180047e82  call    cs:__imp_FwReportReturnError
0x180047e88  mov     ebx, eax
0x180047e8a  test    eax, eax
0x180047e8c  jns     short loc_180047EC7
0x180047e8e  mov     edx, eax
0x180047e90  lea     rcx, aFwsvcportsenum_0; "FwSvcPortsEnum::CreateInstance"
0x180047e97  call    cs:__imp_FwReportReturnError
0x180047e9d  test    rdi, rdi
0x180047ea0  jz      short loc_180047EB1
0x180047ea2  mov     rax, [rdi]
0x180047ea5  mov     rcx, rdi
0x180047ea8  mov     rax, [rax+10h]
0x180047eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047eb1  mov     edx, ebx
0x180047eb3  lea     rcx, aFwsvcportsenum_0; "FwSvcPortsEnum::CreateInstance"
0x180047eba  call    cs:__imp_FwReportReturnError
0x180047ec0  mov     ebx, eax
0x180047ec2  jmp     short loc_180047ECA
0x180047ec4  mov     [rdi+58h], ebp
0x180047ec7  mov     [r15], rdi
0x180047eca  mov     eax, ebx
0x180047ecc  add     rsp, 38h
0x180047ed0  pop     r15
0x180047ed2  pop     r14
0x180047ed4  pop     r13
0x180047ed6  pop     r12
0x180047ed8  pop     rdi
0x180047ed9  pop     rsi
0x180047eda  pop     rbp
0x180047edb  pop     rbx
0x180047edc  retn
```
