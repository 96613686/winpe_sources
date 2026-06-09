# FwOpenPort::Initialize(_tag_FW_PROFILE_TYPE,ushort,NET_FW_IP_PROTOCOL_,_tag_FW_RULE * const)

- ea: `0x18003bc1c`
- end: `0x18003bd94`
- name: `?Initialize@FwOpenPort@@AEAAJW4_tag_FW_PROFILE_TYPE@@GW4NET_FW_IP_PROTOCOL_@@QEAU_tag_FW_RULE@@@Z`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bb48`

## callees

- `0x1800037dc`
- `0x180009780`
- `0x18000be5c`
- `0x18000c3f0`
- `0x1800294b0`
- `0x18003bc1c`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x18003bcd1`
- `fwbase!FwReportReturnError` at `0x18003bd14`
- `fwbase!FwReportReturnError` at `0x18003bcd1`
- `fwbase!FwReportReturnError` at `0x18003bd14`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18003bcb8`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18003bcb8`
- `FWPolicyIOMgr!FwFindMatchingOpenPortRule` at `0x18003bd78`
- `FWPolicyIOMgr!FwFindMatchingOpenPortRule` at `0x18003bd78`
- `FWPolicyIOMgr!FwCopyRule` at `0x18003bc83`
- `FWPolicyIOMgr!FwCopyRule` at `0x18003bc83`

## string_xrefs

- `0x18003bc3e`: `FwOpenPort::Initialize`

## pseudocode

```c
__int64 __fastcall FwOpenPort::Initialize(__int64 a1, int a2, unsigned __int16 a3, unsigned int a4, __int64 a5)
{
  __int64 MatchingOpenPortRule; // rax
  unsigned int v6; // esi
  int v9; // eax
  signed int v10; // ebx
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+38h] [rbp-40h] BYREF
  void *v16; // [rsp+40h] [rbp-38h] BYREF

  MatchingOpenPortRule = a5;
  v6 = a3;
  v15 = 0;
  v14 = 0;
  v16 = 0;
  *(_DWORD *)(a1 + 64) = a2;
  if ( a5 )
  {
    *(_DWORD *)(a1 + 80) = 1;
    goto LABEL_3;
  }
  v9 = OpenLocalPolicyStore(1, &v16);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v13 = FWEnumFirewallRules((_DWORD)v16, 196608, *(_DWORD *)(a1 + 64), 7, (__int64)&v14, (__int64)&v15);
    v10 = v13;
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
    if ( v10 >= 0 )
    {
      MatchingOpenPortRule = FwFindMatchingOpenPortRule(v15, v14, v6, a4);
      if ( MatchingOpenPortRule )
      {
LABEL_3:
        v9 = FwCopyRule(MatchingOpenPortRule, a1 + 72);
        v10 = v9;
        if ( v9 >= 0 )
        {
          *(_DWORD *)(a1 + 84) = 1;
          goto LABEL_5;
        }
        goto LABEL_9;
      }
      v10 = -2147024894;
    }
    v12 = (unsigned int)v10;
    goto LABEL_10;
  }
LABEL_9:
  v12 = (unsigned int)v9;
LABEL_10:
  FwReportReturnError("FwOpenPort::Initialize", v12);
LABEL_5:
  FWFreeFirewallRules(v15);
  CloseLocalPolicyStore(v16);
  if ( v10 < 0 )
  {
    FwFreeWFRule(*(_QWORD *)(a1 + 72));
    *(_QWORD *)(a1 + 72) = 0;
    return (unsigned int)FwReportReturnError("FwOpenPort::Initialize", (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003bc1c  push    rbx
0x18003bc1e  push    rbp
0x18003bc1f  push    rsi
0x18003bc20  push    rdi
0x18003bc21  push    r15
0x18003bc23  sub     rsp, 50h
0x18003bc27  mov     rax, cs:__security_cookie
0x18003bc2e  xor     rax, rsp
0x18003bc31  mov     [rsp+78h+var_30], rax
0x18003bc36  mov     rax, [rsp+78h+arg_20]
0x18003bc3e  lea     r15, aFwopenportInit; "FwOpenPort::Initialize"
0x18003bc45  movzx   esi, r8w
0x18003bc49  mov     ebp, r9d
0x18003bc4c  mov     [rsp+78h+var_40], 0
0x18003bc55  mov     rdi, rcx
0x18003bc58  mov     [rsp+78h+var_48], 0
0x18003bc60  mov     [rsp+78h+var_38], 0
0x18003bc69  mov     [rcx+40h], edx
0x18003bc6c  test    rax, rax
0x18003bc6f  jz      loc_18003BCFA
0x18003bc75  mov     dword ptr [rcx+50h], 1
0x18003bc7c  lea     rdx, [rdi+48h]
0x18003bc80  mov     rcx, rax
0x18003bc83  call    cs:__imp_FwCopyRule
0x18003bc8a  nop     dword ptr [rax+rax+00h]
0x18003bc8f  mov     ebx, eax
0x18003bc91  test    eax, eax
0x18003bc93  js      short loc_18003BD0F
0x18003bc95  mov     dword ptr [rdi+54h], 1
0x18003bc9c  mov     rcx, [rsp+78h+var_40]
0x18003bca1  call    FWFreeFirewallRules
0x18003bca6  mov     rcx, [rsp+78h+var_38]; void *
0x18003bcab  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x18003bcb0  test    ebx, ebx
0x18003bcb2  jns     short loc_18003BCDF
0x18003bcb4  mov     rcx, [rdi+48h]
0x18003bcb8  call    cs:__imp_FwFreeWFRule
0x18003bcbf  nop     dword ptr [rax+rax+00h]
0x18003bcc4  mov     edx, ebx
0x18003bcc6  mov     qword ptr [rdi+48h], 0
0x18003bcce  mov     rcx, r15
0x18003bcd1  call    cs:__imp_FwReportReturnError
0x18003bcd8  nop     dword ptr [rax+rax+00h]
0x18003bcdd  mov     ebx, eax
0x18003bcdf  mov     eax, ebx
0x18003bce1  mov     rcx, [rsp+78h+var_30]
0x18003bce6  xor     rcx, rsp; StackCookie
0x18003bce9  call    __security_check_cookie
0x18003bcee  add     rsp, 50h
0x18003bcf2  pop     r15
0x18003bcf4  pop     rdi
0x18003bcf5  pop     rsi
0x18003bcf6  pop     rbp
0x18003bcf7  pop     rbx
0x18003bcf8  retn
0x18003bcfa  lea     rdx, [rsp+78h+var_38]
0x18003bcff  mov     ecx, 1
0x18003bd04  call    ?OpenLocalPolicyStore@@YAJW4_tag_FW_POLICY_ACCESS_RIGHT@@PEAPEAX@Z; OpenLocalPolicyStore(_tag_FW_POLICY_ACCESS_RIGHT,void * *)
0x18003bd09  mov     ebx, eax
0x18003bd0b  test    eax, eax
0x18003bd0d  jns     short loc_18003BD25
0x18003bd0f  mov     edx, eax
0x18003bd11  mov     rcx, r15
0x18003bd14  call    cs:__imp_FwReportReturnError
0x18003bd1b  nop     dword ptr [rax+rax+00h]
0x18003bd20  jmp     loc_18003BC9C
0x18003bd25  mov     r8d, [rdi+40h]
0x18003bd29  lea     rax, [rsp+78h+var_40]
0x18003bd2e  mov     rcx, [rsp+78h+var_38]
0x18003bd33  mov     r9d, 7
0x18003bd39  mov     [rsp+78h+var_50], rax
0x18003bd3e  mov     edx, 30000h
0x18003bd43  lea     rax, [rsp+78h+var_48]
0x18003bd48  mov     [rsp+78h+var_58], rax
0x18003bd4d  call    FWEnumFirewallRules
0x18003bd52  mov     ebx, eax
0x18003bd54  test    eax, eax
0x18003bd56  jle     short loc_18003BD61
0x18003bd58  movzx   ebx, ax
0x18003bd5b  or      ebx, 80070000h
0x18003bd61  test    ebx, ebx
0x18003bd63  jns     short loc_18003BD69
0x18003bd65  mov     edx, ebx
0x18003bd67  jmp     short loc_18003BD11
0x18003bd69  mov     edx, [rsp+78h+var_48]
0x18003bd6d  mov     r8d, esi
0x18003bd70  mov     rcx, [rsp+78h+var_40]
0x18003bd75  mov     r9d, ebp
0x18003bd78  call    cs:__imp_FwFindMatchingOpenPortRule
0x18003bd7f  nop     dword ptr [rax+rax+00h]
0x18003bd84  test    rax, rax
0x18003bd87  jnz     loc_18003BC7C
0x18003bd8d  mov     ebx, 80070002h
0x18003bd92  jmp     short loc_18003BD65
```
