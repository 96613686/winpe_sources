# FwIcmpSettings::CacheInboundRule(_tag_FW_RULE *,FW_ICMP_RULE_ *)

- ea: `0x1800447ac`
- end: `0x180044844`
- name: `?CacheInboundRule@FwIcmpSettings@@AEAAJPEAU_tag_FW_RULE@@PEAUFW_ICMP_RULE_@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(FwIcmpSettings *__hidden this, struct _tag_FW_RULE *, struct FW_ICMP_RULE_ *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800448ec`

## callees

- `0x18003104c`
- `0x1800447ac`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x1800447f5`
- `fwbase!FwReportReturnError` at `0x180044804`
- `fwbase!FwReportReturnError` at `0x1800447f5`
- `fwbase!FwReportReturnError` at `0x180044804`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800447e0`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800447e0`

## string_xrefs

- `0x1800447ee`: `FwIcmpSettings::CacheInboundRule`
- `0x1800447fd`: `FwIcmpSettings::CacheInboundRule`

## pseudocode

```c
__int64 __fastcall FwIcmpSettings::CacheInboundRule(
        FwIcmpSettings *this,
        struct _tag_FW_RULE *a2,
        struct FW_ICMP_RULE_ *a3)
{
  int v3; // eax
  int v4; // eax
  unsigned int v5; // ebx

  if ( *((_QWORD *)a3 + 1) )
  {
    v5 = 0;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_20be8c82b411374fbd35ad9fa76ebe93_Traceguids);
  }
  else
  {
    if ( *((_DWORD *)a2 + 72) != 3 || (v3 = 1, (*((_BYTE *)a2 + 292) & 1) == 0) )
      v3 = 0;
    *((_DWORD *)a3 + 6) = v3;
    v4 = FwCopyRule(a2, (char *)a3 + 8);
    v5 = v4;
    if ( v4 < 0 )
    {
      FwReportReturnError("FwIcmpSettings::CacheInboundRule", (unsigned int)v4);
      return (unsigned int)FwReportReturnError("FwIcmpSettings::CacheInboundRule", v5);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800447ac  push    rbx
0x1800447ae  sub     rsp, 20h
0x1800447b2  mov     r9, rdx
0x1800447b5  lea     rdx, [r8+8]
0x1800447b9  cmp     qword ptr [rdx], 0
0x1800447bd  jnz     short loc_18004480E
0x1800447bf  cmp     dword ptr [r9+120h], 3
0x1800447c7  jnz     short loc_1800447D7
0x1800447c9  mov     eax, 1
0x1800447ce  test    [r9+124h], al
0x1800447d5  jnz     short loc_1800447D9
0x1800447d7  xor     eax, eax
0x1800447d9  mov     rcx, r9
0x1800447dc  mov     [r8+18h], eax
0x1800447e0  call    cs:__imp_FwCopyRule
0x1800447e6  mov     ebx, eax
0x1800447e8  test    eax, eax
0x1800447ea  jns     short loc_18004483C
0x1800447ec  mov     edx, eax
0x1800447ee  lea     rcx, aFwicmpsettings_11; "FwIcmpSettings::CacheInboundRule"
0x1800447f5  call    cs:__imp_FwReportReturnError
0x1800447fb  mov     edx, ebx
0x1800447fd  lea     rcx, aFwicmpsettings_11; "FwIcmpSettings::CacheInboundRule"
0x180044804  call    cs:__imp_FwReportReturnError
0x18004480a  mov     ebx, eax
0x18004480c  jmp     short loc_18004483C
0x18004480e  mov     rcx, cs:WPP_GLOBAL_Control
0x180044815  lea     rax, WPP_GLOBAL_Control
0x18004481c  xor     ebx, ebx
0x18004481e  cmp     rcx, rax
0x180044821  jz      short loc_18004483C
0x180044823  test    byte ptr [rcx+1Ch], 2
0x180044827  jz      short loc_18004483C
0x180044829  mov     rcx, [rcx+10h]
0x18004482d  lea     edx, [rbx+0Ah]
0x180044830  lea     r8, WPP_20be8c82b411374fbd35ad9fa76ebe93_Traceguids
0x180044837  call    WPP_SF_
0x18004483c  mov     eax, ebx
0x18004483e  add     rsp, 20h
0x180044842  pop     rbx
0x180044843  retn
```
