# FwOpenPorts::get_Count(long *)

- ea: `0x180048d40`
- end: `0x180048e5f`
- name: `?get_Count@FwOpenPorts@@UEAAJPEAJ@Z`
- size: `287`
- prototype: `__int64 __fastcall(FwOpenPorts *__hidden this, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800037dc`
- `0x180009780`
- `0x18000be5c`
- `0x18000c3f0`
- `0x1800294b0`
- `0x180048d40`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180048d94`
- `fwbase!FwReportReturnError` at `0x180048e32`
- `fwbase!FwReportReturnError` at `0x180048d94`
- `fwbase!FwReportReturnError` at `0x180048e32`
- `FWPolicyIOMgr!FwCountGlobalOpenPortRules` at `0x180048e02`
- `FWPolicyIOMgr!FwCountGlobalOpenPortRules` at `0x180048e02`

## string_xrefs

- `0x180048d8d`: `FwOpenPorts::get_Count`
- `0x180048e2b`: `FwOpenPorts::get_Count`

## pseudocode

```c
__int64 __fastcall FwOpenPorts::get_Count(FwOpenPorts *this, int *a2)
{
  signed int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  int v7; // eax
  __int64 v9; // [rsp+30h] [rbp-20h] BYREF
  void *v10; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v11; // [rsp+40h] [rbp-10h] BYREF
  int v12; // [rsp+44h] [rbp-Ch] BYREF

  v9 = 0;
  v11 = 0;
  v12 = 0;
  v10 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    goto LABEL_3;
  }
  v6 = OpenLocalPolicyStore(1, &v10);
  v4 = v6;
  if ( v6 < 0 )
  {
    v5 = (unsigned int)v6;
    goto LABEL_4;
  }
  v7 = FWEnumFirewallRules((__int64)v10, 196608, *((_DWORD *)this + 6), 7, (__int64)&v11, (__int64)&v9);
  v4 = v7;
  if ( v7 > 0 )
    v4 = (unsigned __int16)v7 | 0x80070000;
  if ( v4 < 0 )
  {
LABEL_3:
    v5 = (unsigned int)v4;
LABEL_4:
    FwReportReturnError("FwOpenPorts::get_Count", v5);
    goto LABEL_11;
  }
  FwCountGlobalOpenPortRules(v9, v11, &v12);
  *a2 = v12;
LABEL_11:
  FWFreeFirewallRules(v9);
  CloseLocalPolicyStore(v10);
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPorts::get_Count", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180048d40  mov     [rsp-18h+arg_10], rbx
0x180048d45  push    rbp
0x180048d46  push    rsi
0x180048d47  push    rdi
0x180048d48  mov     rbp, rsp
0x180048d4b  sub     rsp, 50h
0x180048d4f  mov     rax, cs:__security_cookie
0x180048d56  xor     rax, rsp
0x180048d59  mov     [rbp+var_8], rax
0x180048d5d  mov     [rbp+var_20], 0
0x180048d65  mov     rdi, rdx
0x180048d68  mov     [rbp+var_10], 0
0x180048d6f  mov     rsi, rcx
0x180048d72  mov     [rbp+var_C], 0
0x180048d79  mov     [rbp+var_18], 0
0x180048d81  test    rdx, rdx
0x180048d84  jnz     short loc_180048DA2
0x180048d86  mov     ebx, 80004003h
0x180048d8b  mov     edx, ebx
0x180048d8d  lea     rcx, aFwopenportsGet_0; "FwOpenPorts::get_Count"
0x180048d94  call    cs:__imp_FwReportReturnError
0x180048d9b  nop     dword ptr [rax+rax+00h]
0x180048da0  jmp     short loc_180048E13
0x180048da2  lea     rdx, [rbp+var_18]
0x180048da6  mov     ecx, 1
0x180048dab  call    ?OpenLocalPolicyStore@@YAJW4_tag_FW_POLICY_ACCESS_RIGHT@@PEAPEAX@Z; OpenLocalPolicyStore(_tag_FW_POLICY_ACCESS_RIGHT,void * *)
0x180048db0  mov     ebx, eax
0x180048db2  test    eax, eax
0x180048db4  jns     short loc_180048DBA
0x180048db6  mov     edx, eax
0x180048db8  jmp     short loc_180048D8D
0x180048dba  mov     r8d, [rsi+18h]
0x180048dbe  lea     rax, [rbp+var_20]
0x180048dc2  mov     rcx, [rbp+var_18]
0x180048dc6  mov     r9d, 7
0x180048dcc  mov     [rsp+50h+var_28], rax
0x180048dd1  mov     edx, 30000h
0x180048dd6  lea     rax, [rbp+var_10]
0x180048dda  mov     [rsp+50h+var_30], rax
0x180048ddf  call    FWEnumFirewallRules
0x180048de4  mov     ebx, eax
0x180048de6  test    eax, eax
0x180048de8  jle     short loc_180048DF3
0x180048dea  movzx   ebx, ax
0x180048ded  or      ebx, 80070000h
0x180048df3  test    ebx, ebx
0x180048df5  js      short loc_180048D8B
0x180048df7  mov     edx, [rbp+var_10]
0x180048dfa  lea     r8, [rbp+var_C]
0x180048dfe  mov     rcx, [rbp+var_20]
0x180048e02  call    cs:__imp_FwCountGlobalOpenPortRules
0x180048e09  nop     dword ptr [rax+rax+00h]
0x180048e0e  mov     eax, [rbp+var_C]
0x180048e11  mov     [rdi], eax
0x180048e13  mov     rcx, [rbp+var_20]
0x180048e17  call    FWFreeFirewallRules
0x180048e1c  mov     rcx, [rbp+var_18]; void *
0x180048e20  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x180048e25  test    ebx, ebx
0x180048e27  jns     short loc_180048E40
0x180048e29  mov     edx, ebx
0x180048e2b  lea     rcx, aFwopenportsGet_0; "FwOpenPorts::get_Count"
0x180048e32  call    cs:__imp_FwReportReturnError
0x180048e39  nop     dword ptr [rax+rax+00h]
0x180048e3e  mov     ebx, eax
0x180048e40  mov     eax, ebx
0x180048e42  mov     rcx, [rbp+var_8]
0x180048e46  xor     rcx, rsp; StackCookie
0x180048e49  call    __security_check_cookie
0x180048e4e  mov     rbx, [rsp+50h+arg_10]
0x180048e56  add     rsp, 50h
0x180048e5a  pop     rdi
0x180048e5b  pop     rsi
0x180048e5c  pop     rbp
0x180048e5d  retn
```
