# FwRule::CreateInstance(FwPolicyViewFlags,_tag_FW_RULE *,FwRule * *)

- ea: `0x180004cd0`
- end: `0x180004e3f`
- name: `?CreateInstance@FwRule@@SAJW4FwPolicyViewFlags@@PEAU_tag_FW_RULE@@PEAPEAV1@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004300`

## callees

- `0x180004cd0`
- `0x180004e50`
- `0x18003104c`
- `0x18005e010`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180004d94`
- `fwbase!FwReportReturnError` at `0x180004dbc`
- `fwbase!FwReportReturnError` at `0x180004dcd`
- `fwbase!FwReportReturnError` at `0x180004dea`
- `fwbase!FwReportReturnError` at `0x180004e03`
- `fwbase!FwReportReturnError` at `0x180004d94`
- `fwbase!FwReportReturnError` at `0x180004dbc`
- `fwbase!FwReportReturnError` at `0x180004dcd`
- `fwbase!FwReportReturnError` at `0x180004dea`
- `fwbase!FwReportReturnError` at `0x180004e03`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180004dd7`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180004dd7`
- `FWPolicyIOMgr!FwCopyRule` at `0x180004d5c`
- `FWPolicyIOMgr!FwCopyRule` at `0x180004d5c`

## string_xrefs

- `0x180004d8d`: `FwRule::CreateInstance`
- `0x180004db5`: `FwRule::CreateInstance`
- `0x180004dfc`: `FwRule::CreateInstance`

## pseudocode

```c
__int64 __fastcall FwRule::CreateInstance(int a1, __int64 a2, _QWORD *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rsi
  int v9; // eax
  int v11; // eax
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  v12 = 0;
  *a3 = 0;
  v6 = ATL::CComObject<FwRule>::CreateInstance(&v12);
  v7 = v6;
  if ( v6 < 0 )
  {
    FwReportReturnError("FwRule::CreateInstance", (unsigned int)v6);
    v8 = v12;
  }
  else
  {
    v8 = v12;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
    *(_DWORD *)(v8 + 64) = a1;
    v9 = FwCopyRule(a2, v8 + 80);
    v7 = v9;
    if ( v9 >= 0 )
    {
      *(_DWORD *)(v8 + 88) = 1;
LABEL_10:
      *a3 = v8;
      return v7;
    }
    FwReportReturnError("FwRule::Initialize", (unsigned int)v9);
    FwFreeWFRule(*(_QWORD *)(v8 + 80));
    *(_QWORD *)(v8 + 80) = 0;
    v11 = FwReportReturnError("FwRule::Initialize", v7);
    v7 = v11;
    if ( v11 >= 0 )
      goto LABEL_10;
    FwReportReturnError("FwRule::CreateInstance", (unsigned int)v11);
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return FwReportReturnError("FwRule::CreateInstance", v7);
}

```

## disassembly

```asm
0x180004cd0  mov     [rsp+arg_8], rbx
0x180004cd5  push    rbp
0x180004cd6  push    rdi
0x180004cd7  push    r12
0x180004cd9  push    r14
0x180004cdb  push    r15
0x180004cdd  sub     rsp, 20h
0x180004ce1  mov     rdi, r8
0x180004ce4  mov     rbp, rdx
0x180004ce7  mov     r14d, ecx
0x180004cea  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cf1  lea     r12, WPP_GLOBAL_Control
0x180004cf8  cmp     rcx, r12
0x180004cfb  jz      short loc_180004D07
0x180004cfd  test    byte ptr [rcx+1Ch], 8
0x180004d01  jnz     loc_180004E0B
0x180004d07  xor     r15d, r15d
0x180004d0a  mov     [rsp+48h+arg_0], rsi
0x180004d0f  lea     rcx, [rsp+48h+arg_10]
0x180004d14  mov     [rsp+48h+arg_10], r15
0x180004d19  mov     [rdi], r15
0x180004d1c  call    ?CreateInstance@?$CComObject@VFwRule@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<FwRule>::CreateInstance(ATL::CComObject<FwRule> * *)
0x180004d21  mov     ebx, eax
0x180004d23  test    eax, eax
0x180004d25  js      short loc_180004D8B
0x180004d27  mov     rsi, [rsp+48h+arg_10]
0x180004d2c  mov     rcx, rsi
0x180004d2f  mov     rax, [rsi]
0x180004d32  mov     rax, [rax+8]
0x180004d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d42  cmp     rcx, r12
0x180004d45  jz      short loc_180004D51
0x180004d47  test    byte ptr [rcx+1Ch], 8
0x180004d4b  jnz     loc_180004E25
0x180004d51  lea     rdx, [rsi+50h]
0x180004d55  mov     [rsi+40h], r14d
0x180004d59  mov     rcx, rbp
0x180004d5c  call    cs:__imp_FwCopyRule
0x180004d62  mov     ebx, eax
0x180004d64  test    eax, eax
0x180004d66  js      short loc_180004DC4
0x180004d68  mov     dword ptr [rsi+58h], 1
0x180004d6f  mov     [rdi], rsi
0x180004d72  mov     eax, ebx
0x180004d74  mov     rsi, [rsp+48h+arg_0]
0x180004d79  mov     rbx, [rsp+48h+arg_8]
0x180004d7e  add     rsp, 20h
0x180004d82  pop     r15
0x180004d84  pop     r14
0x180004d86  pop     r12
0x180004d88  pop     rdi
0x180004d89  pop     rbp
0x180004d8a  retn
0x180004d8b  mov     edx, eax
0x180004d8d  lea     rcx, aFwruleCreatein; "FwRule::CreateInstance"
0x180004d94  call    cs:__imp_FwReportReturnError
0x180004d9a  mov     rsi, [rsp+48h+arg_10]
0x180004d9f  test    rsi, rsi
0x180004da2  jz      short loc_180004DB3
0x180004da4  mov     rax, [rsi]
0x180004da7  mov     rcx, rsi
0x180004daa  mov     rax, [rax+10h]
0x180004dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004db3  mov     edx, ebx
0x180004db5  lea     rcx, aFwruleCreatein; "FwRule::CreateInstance"
0x180004dbc  call    cs:__imp_FwReportReturnError
0x180004dc2  jmp     short loc_180004D74
0x180004dc4  mov     edx, ebx
0x180004dc6  lea     rcx, aFwruleInitiali; "FwRule::Initialize"
0x180004dcd  call    cs:__imp_FwReportReturnError
0x180004dd3  mov     rcx, [rsi+50h]
0x180004dd7  call    cs:__imp_FwFreeWFRule
0x180004ddd  mov     edx, ebx
0x180004ddf  mov     [rsi+50h], r15
0x180004de3  lea     rcx, aFwruleInitiali; "FwRule::Initialize"
0x180004dea  call    cs:__imp_FwReportReturnError
0x180004df0  mov     ebx, eax
0x180004df2  test    eax, eax
0x180004df4  jns     loc_180004D6F
0x180004dfa  mov     edx, eax
0x180004dfc  lea     rcx, aFwruleCreatein; "FwRule::CreateInstance"
0x180004e03  call    cs:__imp_FwReportReturnError
0x180004e09  jmp     short loc_180004D9F
0x180004e0b  mov     rcx, [rcx+10h]
0x180004e0f  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180004e16  mov     edx, 55h ; 'U'
0x180004e1b  call    WPP_SF_
0x180004e20  jmp     loc_180004D07
0x180004e25  mov     rcx, [rcx+10h]
0x180004e29  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180004e30  mov     edx, 5Ah ; 'Z'
0x180004e35  call    WPP_SF_
0x180004e3a  jmp     loc_180004D51
```
