# FwIcmpSettings::CacheOutboundRule(_tag_FW_RULE *,FW_ICMP_RULE_ *)

- ea: `0x180047e10`
- end: `0x180047ebb`
- name: `?CacheOutboundRule@FwIcmpSettings@@AEAAJPEAU_tag_FW_RULE@@PEAUFW_ICMP_RULE_@@@Z`
- size: `171`
- prototype: `__int64 __fastcall(FwIcmpSettings *__hidden this, struct _tag_FW_RULE *, struct FW_ICMP_RULE_ *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180047ec4`

## callees

- `0x18003336c`
- `0x180047e10`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180047e5f`
- `fwbase!FwReportReturnError` at `0x180047e74`
- `fwbase!FwReportReturnError` at `0x180047e5f`
- `fwbase!FwReportReturnError` at `0x180047e74`
- `FWPolicyIOMgr!FwCopyRule` at `0x180047e44`
- `FWPolicyIOMgr!FwCopyRule` at `0x180047e44`

## string_xrefs

- `0x180047e58`: `FwIcmpSettings::CacheOutboundRule`
- `0x180047e6d`: `FwIcmpSettings::CacheOutboundRule`

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
0x180047e10  push    rbx
0x180047e12  sub     rsp, 20h
0x180047e16  mov     r9, rdx
0x180047e19  lea     rdx, [r8+10h]
0x180047e1d  cmp     qword ptr [rdx], 0
0x180047e21  jnz     short loc_180047E84
0x180047e23  cmp     dword ptr [r9+120h], 3
0x180047e2b  jnz     short loc_180047E3B
0x180047e2d  mov     eax, 1
0x180047e32  test    [r9+124h], al
0x180047e39  jnz     short loc_180047E3D
0x180047e3b  xor     eax, eax
0x180047e3d  mov     rcx, r9
0x180047e40  mov     [r8+1Ch], eax
0x180047e44  call    cs:__imp_FwCopyRule
0x180047e4b  nop     dword ptr [rax+rax+00h]
0x180047e50  mov     ebx, eax
0x180047e52  test    eax, eax
0x180047e54  jns     short loc_180047EB2
0x180047e56  mov     edx, eax
0x180047e58  lea     rcx, aFwicmpsettings_9; "FwIcmpSettings::CacheOutboundRule"
0x180047e5f  call    cs:__imp_FwReportReturnError
0x180047e66  nop     dword ptr [rax+rax+00h]
0x180047e6b  mov     edx, ebx
0x180047e6d  lea     rcx, aFwicmpsettings_9; "FwIcmpSettings::CacheOutboundRule"
0x180047e74  call    cs:__imp_FwReportReturnError
0x180047e7b  nop     dword ptr [rax+rax+00h]
0x180047e80  mov     ebx, eax
0x180047e82  jmp     short loc_180047EB2
0x180047e84  mov     rcx, cs:WPP_GLOBAL_Control
0x180047e8b  lea     rax, WPP_GLOBAL_Control
0x180047e92  xor     ebx, ebx
0x180047e94  cmp     rcx, rax
0x180047e97  jz      short loc_180047EB2
0x180047e99  test    byte ptr [rcx+1Ch], 2
0x180047e9d  jz      short loc_180047EB2
0x180047e9f  mov     rcx, [rcx+10h]
0x180047ea3  lea     edx, [rbx+0Bh]
0x180047ea6  lea     r8, WPP_20be8c82b411374fbd35ad9fa76ebe93_Traceguids
0x180047ead  call    WPP_SF_
0x180047eb2  mov     eax, ebx
0x180047eb4  add     rsp, 20h
0x180047eb8  pop     rbx
0x180047eb9  retn
```
