# FwRuleInGroup(_tag_FW_RULE const *,ushort const *)

- ea: `0x180006e14`
- end: `0x180006eb2`
- name: `?FwRuleInGroup@@YAHPEBU_tag_FW_RULE@@PEBG@Z`
- size: `158`
- prototype: `int(const struct _tag_FW_RULE *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007e30`
- `0x180009a50`

## callees

- `0x180006e14`
- `0x1800294b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180006e74`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180006e74`
- `fwbase!FwBaseFree` at `0x180006e8b`
- `fwbase!FwBaseFree` at `0x180006e8b`
- `fwbase!FwLoadIndirectString` at `0x180006e48`
- `fwbase!FwLoadIndirectString` at `0x180006e48`

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
0x180006e14  mov     [rsp+arg_10], rbx
0x180006e19  push    rdi
0x180006e1a  sub     rsp, 40h
0x180006e1e  mov     rax, cs:__security_cookie
0x180006e25  xor     rax, rsp
0x180006e28  mov     [rsp+48h+var_10], rax
0x180006e2d  mov     rcx, [rcx+138h]
0x180006e34  xor     ebx, ebx
0x180006e36  mov     [rsp+48h+var_18], rbx
0x180006e3b  mov     rdi, rdx
0x180006e3e  test    rcx, rcx
0x180006e41  jz      short loc_180006E86
0x180006e43  lea     rdx, [rsp+48h+var_18]
0x180006e48  call    cs:__imp_FwLoadIndirectString
0x180006e4f  nop     dword ptr [rax+rax+00h]
0x180006e54  test    eax, eax
0x180006e56  js      short loc_180006E86
0x180006e58  mov     rax, [rsp+48h+var_18]
0x180006e5d  lea     edx, [rbx+1]; dwCmpFlags
0x180006e60  or      r9d, 0FFFFFFFFh; cchCount1
0x180006e64  lea     ecx, [rbx+7Fh]; Locale
0x180006e67  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x180006e6c  mov     r8, rdi; lpString1
0x180006e6f  mov     [rsp+48h+lpString2], rax; lpString2
0x180006e74  call    cs:__imp_CompareStringW
0x180006e7b  nop     dword ptr [rax+rax+00h]
0x180006e80  cmp     eax, 2
0x180006e83  setz    bl
0x180006e86  mov     rcx, [rsp+48h+var_18]
0x180006e8b  call    cs:__imp_FwBaseFree
0x180006e92  nop     dword ptr [rax+rax+00h]
0x180006e97  mov     eax, ebx
0x180006e99  mov     rcx, [rsp+48h+var_10]
0x180006e9e  xor     rcx, rsp; StackCookie
0x180006ea1  call    __security_check_cookie
0x180006ea6  mov     rbx, [rsp+48h+arg_10]
0x180006eab  add     rsp, 40h
0x180006eaf  pop     rdi
0x180006eb0  retn
```
