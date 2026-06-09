# FwFindMatchingAppRule(_tag_FW_RULE * const,ulong,ushort const *,ushort)

- ea: `0x180003024`
- end: `0x180003114`
- name: `?FwFindMatchingAppRule@@YAPEAU_tag_FW_RULE@@QEAU1@KPEBGG@Z`
- size: `240`
- prototype: `struct _tag_FW_RULE *__fastcall(struct _tag_FW_RULE *const, unsigned int, const unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e3c`

## callees

- `0x180003024`
- `0x1800277b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800030d3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800030d3`
- `fwbase!FwBaseFree` at `0x18000308a`
- `fwbase!FwBaseFree` at `0x18000308a`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x1800030bb`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x1800030bb`
- `fwbase!IsRuleOldAuthApp` at `0x1800030a0`
- `fwbase!IsRuleOldAuthApp` at `0x1800030a0`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x18000307b`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x18000307b`

## pseudocode

```c
struct _tag_FW_RULE *__fastcall FwFindMatchingAppRule(
        struct _tag_FW_RULE *const a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        __int16 a4)
{
  unsigned int i; // edi
  BOOL v9; // esi
  __int64 v11; // [rsp+20h] [rbp-48h] BYREF
  int v12; // [rsp+28h] [rbp-40h] BYREF

  for ( i = 0; i < a2; ++i )
  {
    v11 = 0;
    v12 = 0;
    v9 = 0;
    if ( (unsigned int)IsRuleOpenPortOrAuthApp(a1)
      && (unsigned int)IsRuleOldAuthApp(a1)
      && (int)FwGetExpandedCanonicalLongPathName(*((_QWORD *)a1 + 34), &v11, &v12) >= 0
      && v12 )
    {
      v9 = _o__wcsicmp(a3, v11) == 0;
    }
    FwBaseFree(v11);
    if ( v9 && a4 == *((_WORD *)a1 + 24) )
      return a1;
    a1 = *(struct _tag_FW_RULE *const *)a1;
  }
  return 0;
}

```

## disassembly

```asm
0x180003024  mov     [rsp+arg_8], rbx
0x180003029  mov     [rsp+arg_18], rbp
0x18000302e  push    rsi
0x18000302f  push    rdi
0x180003030  push    r13
0x180003032  push    r14
0x180003034  push    r15
0x180003036  sub     rsp, 40h
0x18000303a  mov     rax, cs:__security_cookie
0x180003041  xor     rax, rsp
0x180003044  mov     [rsp+68h+var_38], rax
0x180003049  xor     edi, edi
0x18000304b  movzx   ebp, r9w
0x18000304f  mov     r15, r8
0x180003052  mov     r14d, edx
0x180003055  mov     rbx, rcx
0x180003058  lea     r13d, [rdi+1]
0x18000305c  cmp     edi, r14d
0x18000305f  jnb     loc_1800030EC
0x180003065  mov     rcx, rbx
0x180003068  mov     [rsp+68h+var_48], 0
0x180003071  mov     [rsp+68h+var_40], 0
0x180003079  xor     esi, esi
0x18000307b  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180003081  test    eax, eax
0x180003083  jnz     short loc_18000309D
0x180003085  mov     rcx, [rsp+68h+var_48]
0x18000308a  call    cs:__imp_FwBaseFree
0x180003090  cmp     esi, r13d
0x180003093  jz      short loc_1800030E1
0x180003095  mov     rbx, [rbx]
0x180003098  add     edi, r13d
0x18000309b  jmp     short loc_18000305C
0x18000309d  mov     rcx, rbx
0x1800030a0  call    cs:__imp_IsRuleOldAuthApp
0x1800030a6  test    eax, eax
0x1800030a8  jz      short loc_180003085
0x1800030aa  mov     rcx, [rbx+110h]
0x1800030b1  lea     r8, [rsp+68h+var_40]
0x1800030b6  lea     rdx, [rsp+68h+var_48]
0x1800030bb  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x1800030c1  test    eax, eax
0x1800030c3  js      short loc_180003085
0x1800030c5  cmp     [rsp+68h+var_40], esi
0x1800030c9  jz      short loc_180003085
0x1800030cb  mov     rdx, [rsp+68h+var_48]
0x1800030d0  mov     rcx, r15
0x1800030d3  call    cs:__imp__o__wcsicmp
0x1800030d9  test    eax, eax
0x1800030db  cmovz   esi, r13d
0x1800030df  jmp     short loc_180003085
0x1800030e1  cmp     bp, [rbx+30h]
0x1800030e5  jnz     short loc_180003095
0x1800030e7  mov     rax, rbx
0x1800030ea  jmp     short loc_1800030EE
0x1800030ec  xor     eax, eax
0x1800030ee  mov     rcx, [rsp+68h+var_38]
0x1800030f3  xor     rcx, rsp; StackCookie
0x1800030f6  call    __security_check_cookie
0x1800030fb  lea     r11, [rsp+68h+var_28]
0x180003100  mov     rbx, [r11+38h]
0x180003104  mov     rbp, [r11+48h]
0x180003108  mov     rsp, r11
0x18000310b  pop     r15
0x18000310d  pop     r14
0x18000310f  pop     r13
0x180003111  pop     rdi
0x180003112  pop     rsi
0x180003113  retn
```
