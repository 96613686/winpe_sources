# FwRuleInGroup(_tag_FW_RULE const *,ushort const *)

- ea: `0x180006910`
- end: `0x18000699b`
- name: `?FwRuleInGroup@@YAHPEBU_tag_FW_RULE@@PEBG@Z`
- size: `139`
- prototype: `int(const struct _tag_FW_RULE *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007880`
- `0x180009340`

## callees

- `0x180006910`
- `0x1800277b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000696a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000696a`
- `fwbase!FwBaseFree` at `0x18000697b`
- `fwbase!FwBaseFree` at `0x18000697b`
- `fwbase!FwLoadIndirectString` at `0x180006944`
- `fwbase!FwLoadIndirectString` at `0x180006944`

## pseudocode

```c
__int64 __fastcall FwRuleInGroup(const struct _tag_FW_RULE *a1, const unsigned __int16 *a2)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  PCNZWCH lpString2; // [rsp+30h] [rbp-18h] BYREF

  v2 = *((_QWORD *)a1 + 39);
  v3 = 0;
  lpString2 = 0;
  if ( v2 && (int)FwLoadIndirectString(v2, &lpString2) >= 0 )
    LOBYTE(v3) = CompareStringW(0x7Fu, 1u, a2, -1, lpString2, -1) == 2;
  FwBaseFree(lpString2);
  return v3;
}

```

## disassembly

```asm
0x180006910  mov     [rsp+arg_10], rbx
0x180006915  push    rdi
0x180006916  sub     rsp, 40h
0x18000691a  mov     rax, cs:__security_cookie
0x180006921  xor     rax, rsp
0x180006924  mov     [rsp+48h+var_10], rax
0x180006929  mov     rcx, [rcx+138h]
0x180006930  xor     ebx, ebx
0x180006932  mov     [rsp+48h+var_18], rbx
0x180006937  mov     rdi, rdx
0x18000693a  test    rcx, rcx
0x18000693d  jz      short loc_180006976
0x18000693f  lea     rdx, [rsp+48h+var_18]
0x180006944  call    cs:__imp_FwLoadIndirectString
0x18000694a  test    eax, eax
0x18000694c  js      short loc_180006976
0x18000694e  mov     rax, [rsp+48h+var_18]
0x180006953  lea     edx, [rbx+1]; dwCmpFlags
0x180006956  or      r9d, 0FFFFFFFFh; cchCount1
0x18000695a  lea     ecx, [rbx+7Fh]; Locale
0x18000695d  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x180006962  mov     r8, rdi; lpString1
0x180006965  mov     [rsp+48h+lpString2], rax; lpString2
0x18000696a  call    cs:__imp_CompareStringW
0x180006970  cmp     eax, 2
0x180006973  setz    bl
0x180006976  mov     rcx, [rsp+48h+var_18]
0x18000697b  call    cs:__imp_FwBaseFree
0x180006981  mov     eax, ebx
0x180006983  mov     rcx, [rsp+48h+var_10]
0x180006988  xor     rcx, rsp; StackCookie
0x18000698b  call    __security_check_cookie
0x180006990  mov     rbx, [rsp+48h+arg_10]
0x180006995  add     rsp, 40h
0x180006999  pop     rdi
0x18000699a  retn
```
