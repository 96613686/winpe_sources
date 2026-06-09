# FwIcmpSettings::CacheOutboundRule(_tag_FW_RULE *,FW_ICMP_RULE_ *)

- ea: `0x18004484c`
- end: `0x1800448e4`
- name: `?CacheOutboundRule@FwIcmpSettings@@AEAAJPEAU_tag_FW_RULE@@PEAUFW_ICMP_RULE_@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(FwIcmpSettings *__hidden this, struct _tag_FW_RULE *, struct FW_ICMP_RULE_ *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800448ec`

## callees

- `0x18003104c`
- `0x18004484c`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180044895`
- `fwbase!FwReportReturnError` at `0x1800448a4`
- `fwbase!FwReportReturnError` at `0x180044895`
- `fwbase!FwReportReturnError` at `0x1800448a4`
- `FWPolicyIOMgr!FwCopyRule` at `0x180044880`
- `FWPolicyIOMgr!FwCopyRule` at `0x180044880`

## string_xrefs

- `0x18004488e`: `FwIcmpSettings::CacheOutboundRule`
- `0x18004489d`: `FwIcmpSettings::CacheOutboundRule`

## pseudocode

```c
__int64 __fastcall FwIcmpSettings::CacheOutboundRule(
        FwIcmpSettings *this,
        struct _tag_FW_RULE *a2,
        struct FW_ICMP_RULE_ *a3)
{
  int v3; // eax
  int v4; // eax
  unsigned int v5; // ebx

  if ( *((_QWORD *)a3 + 2) )
  {
    v5 = 0;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_20be8c82b411374fbd35ad9fa76ebe93_Traceguids);
  }
  else
  {
    if ( *((_DWORD *)a2 + 72) != 3 || (v3 = 1, (*((_BYTE *)a2 + 292) & 1) == 0) )
      v3 = 0;
    *((_DWORD *)a3 + 7) = v3;
    v4 = FwCopyRule(a2, (char *)a3 + 16);
    v5 = v4;
    if ( v4 < 0 )
    {
      FwReportReturnError("FwIcmpSettings::CacheOutboundRule", (unsigned int)v4);
      return (unsigned int)FwReportReturnError("FwIcmpSettings::CacheOutboundRule", v5);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18004484c  push    rbx
0x18004484e  sub     rsp, 20h
0x180044852  mov     r9, rdx
0x180044855  lea     rdx, [r8+10h]
0x180044859  cmp     qword ptr [rdx], 0
0x18004485d  jnz     short loc_1800448AE
0x18004485f  cmp     dword ptr [r9+120h], 3
0x180044867  jnz     short loc_180044877
0x180044869  mov     eax, 1
0x18004486e  test    [r9+124h], al
0x180044875  jnz     short loc_180044879
0x180044877  xor     eax, eax
0x180044879  mov     rcx, r9
0x18004487c  mov     [r8+1Ch], eax
0x180044880  call    cs:__imp_FwCopyRule
0x180044886  mov     ebx, eax
0x180044888  test    eax, eax
0x18004488a  jns     short loc_1800448DC
0x18004488c  mov     edx, eax
0x18004488e  lea     rcx, aFwicmpsettings_9; "FwIcmpSettings::CacheOutboundRule"
0x180044895  call    cs:__imp_FwReportReturnError
0x18004489b  mov     edx, ebx
0x18004489d  lea     rcx, aFwicmpsettings_9; "FwIcmpSettings::CacheOutboundRule"
0x1800448a4  call    cs:__imp_FwReportReturnError
0x1800448aa  mov     ebx, eax
0x1800448ac  jmp     short loc_1800448DC
0x1800448ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800448b5  lea     rax, WPP_GLOBAL_Control
0x1800448bc  xor     ebx, ebx
0x1800448be  cmp     rcx, rax
0x1800448c1  jz      short loc_1800448DC
0x1800448c3  test    byte ptr [rcx+1Ch], 2
0x1800448c7  jz      short loc_1800448DC
0x1800448c9  mov     rcx, [rcx+10h]
0x1800448cd  lea     edx, [rbx+0Bh]
0x1800448d0  lea     r8, WPP_20be8c82b411374fbd35ad9fa76ebe93_Traceguids
0x1800448d7  call    WPP_SF_
0x1800448dc  mov     eax, ebx
0x1800448de  add     rsp, 20h
0x1800448e2  pop     rbx
0x1800448e3  retn
```
