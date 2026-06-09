# FwOpenPorts::get_Count(long *)

- ea: `0x1800456b0`
- end: `0x1800457bc`
- name: `?get_Count@FwOpenPorts@@UEAAJPEAJ@Z`
- size: `268`
- prototype: `__int64 __fastcall(FwOpenPorts *__hidden this, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180003520`
- `0x180009080`
- `0x18000b34c`
- `0x18000b8c0`
- `0x1800277b0`
- `0x1800456b0`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180045704`
- `fwbase!FwReportReturnError` at `0x180045796`
- `fwbase!FwReportReturnError` at `0x180045704`
- `fwbase!FwReportReturnError` at `0x180045796`
- `FWPolicyIOMgr!FwCountGlobalOpenPortRules` at `0x18004576c`
- `FWPolicyIOMgr!FwCountGlobalOpenPortRules` at `0x18004576c`

## string_xrefs

- `0x1800456fd`: `FwOpenPorts::get_Count`
- `0x18004578f`: `FwOpenPorts::get_Count`

## pseudocode

```c
__int64 __fastcall FwOpenPorts::get_Count(FwOpenPorts *this, int *a2)
{
  signed int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  int v9; // eax
  __int64 v11; // [rsp+30h] [rbp-20h] BYREF
  void *v12; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v13; // [rsp+40h] [rbp-10h] BYREF
  int v14; // [rsp+44h] [rbp-Ch] BYREF

  v11 = 0;
  v13 = 0;
  v14 = 0;
  v12 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    goto LABEL_3;
  }
  v8 = OpenLocalPolicyStore(1, &v12);
  v4 = v8;
  if ( v8 < 0 )
  {
    v5 = (unsigned int)v8;
    goto LABEL_4;
  }
  v9 = FWEnumFirewallRules((__int64)v12, 196608, *((_DWORD *)this + 6), 7, (__int64)&v13, (__int64)&v11);
  v4 = v9;
  if ( v9 > 0 )
    v4 = (unsigned __int16)v9 | 0x80070000;
  if ( v4 < 0 )
  {
LABEL_3:
    v5 = (unsigned int)v4;
LABEL_4:
    FwReportReturnError("FwOpenPorts::get_Count", v5);
    goto LABEL_11;
  }
  FwCountGlobalOpenPortRules(v11, v13, &v14);
  *a2 = v14;
LABEL_11:
  FWFreeFirewallRules(v11, v6, v7);
  CloseLocalPolicyStore(v12);
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPorts::get_Count", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800456b0  mov     [rsp-18h+arg_10], rbx
0x1800456b5  push    rbp
0x1800456b6  push    rsi
0x1800456b7  push    rdi
0x1800456b8  mov     rbp, rsp
0x1800456bb  sub     rsp, 50h
0x1800456bf  mov     rax, cs:__security_cookie
0x1800456c6  xor     rax, rsp
0x1800456c9  mov     [rbp+var_8], rax
0x1800456cd  mov     [rbp+var_20], 0
0x1800456d5  mov     rdi, rdx
0x1800456d8  mov     [rbp+var_10], 0
0x1800456df  mov     rsi, rcx
0x1800456e2  mov     [rbp+var_C], 0
0x1800456e9  mov     [rbp+var_18], 0
0x1800456f1  test    rdx, rdx
0x1800456f4  jnz     short loc_18004570C
0x1800456f6  mov     ebx, 80004003h
0x1800456fb  mov     edx, ebx
0x1800456fd  lea     rcx, aFwopenportsGet_0; "FwOpenPorts::get_Count"
0x180045704  call    cs:__imp_FwReportReturnError
0x18004570a  jmp     short loc_180045777
0x18004570c  lea     rdx, [rbp+var_18]
0x180045710  mov     ecx, 1
0x180045715  call    ?OpenLocalPolicyStore@@YAJW4_tag_FW_POLICY_ACCESS_RIGHT@@PEAPEAX@Z; OpenLocalPolicyStore(_tag_FW_POLICY_ACCESS_RIGHT,void * *)
0x18004571a  mov     ebx, eax
0x18004571c  test    eax, eax
0x18004571e  jns     short loc_180045724
0x180045720  mov     edx, eax
0x180045722  jmp     short loc_1800456FD
0x180045724  mov     r8d, [rsi+18h]
0x180045728  lea     rax, [rbp+var_20]
0x18004572c  mov     rcx, [rbp+var_18]
0x180045730  mov     r9d, 7
0x180045736  mov     [rsp+50h+var_28], rax
0x18004573b  mov     edx, 30000h
0x180045740  lea     rax, [rbp+var_10]
0x180045744  mov     [rsp+50h+var_30], rax
0x180045749  call    FWEnumFirewallRules
0x18004574e  mov     ebx, eax
0x180045750  test    eax, eax
0x180045752  jle     short loc_18004575D
0x180045754  movzx   ebx, ax
0x180045757  or      ebx, 80070000h
0x18004575d  test    ebx, ebx
0x18004575f  js      short loc_1800456FB
0x180045761  mov     edx, [rbp+var_10]
0x180045764  lea     r8, [rbp+var_C]
0x180045768  mov     rcx, [rbp+var_20]
0x18004576c  call    cs:__imp_FwCountGlobalOpenPortRules
0x180045772  mov     eax, [rbp+var_C]
0x180045775  mov     [rdi], eax
0x180045777  mov     rcx, [rbp+var_20]
0x18004577b  call    FWFreeFirewallRules
0x180045780  mov     rcx, [rbp+var_18]; void *
0x180045784  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x180045789  test    ebx, ebx
0x18004578b  jns     short loc_18004579E
0x18004578d  mov     edx, ebx
0x18004578f  lea     rcx, aFwopenportsGet_0; "FwOpenPorts::get_Count"
0x180045796  call    cs:__imp_FwReportReturnError
0x18004579c  mov     ebx, eax
0x18004579e  mov     eax, ebx
0x1800457a0  mov     rcx, [rbp+var_8]
0x1800457a4  xor     rcx, rsp; StackCookie
0x1800457a7  call    __security_check_cookie
0x1800457ac  mov     rbx, [rsp+50h+arg_10]
0x1800457b4  add     rsp, 50h
0x1800457b8  pop     rdi
0x1800457b9  pop     rsi
0x1800457ba  pop     rbp
0x1800457bb  retn
```
