# StripLinkPrefix(ushort const *)

- ea: `0x18002a9e0`
- end: `0x18002aa7b`
- name: `?StripLinkPrefix@@YAPEBGPEBG@Z`
- size: `155`
- prototype: `PCNZWCH __fastcall(PCNZWCH lpString1)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000de50`
- `0x1800223b4`

## callees

- `0x1800016d0`
- `0x18002a9e0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002aa4e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002aa4e`

## pseudocode

```c
PCNZWCH __fastcall StripLinkPrefix(PCNZWCH lpString1)
{
  unsigned __int64 v2; // rcx
  __int64 cchCount2; // rdi
  WCHAR String2[8]; // [rsp+30h] [rbp-28h] BYREF

  v2 = -1;
  wcscpy(String2, L"LDAP://");
  cchCount2 = -1;
  do
    ++cchCount2;
  while ( String2[cchCount2] );
  do
    ++v2;
  while ( lpString1[v2] );
  if ( v2 > (unsigned int)cchCount2 && CompareStringW(0x400u, 1u, lpString1, cchCount2, String2, cchCount2) == 2 )
    lpString1 += (int)cchCount2;
  return lpString1;
}

```

## disassembly

```asm
0x18002a9e0  mov     [rsp+arg_8], rbx
0x18002a9e5  push    rdi
0x18002a9e6  sub     rsp, 50h
0x18002a9ea  mov     rax, cs:__security_cookie
0x18002a9f1  xor     rax, rsp
0x18002a9f4  mov     [rsp+58h+var_18], rax
0x18002a9f9  movups  xmm0, xmmword ptr cs:aLdap; "LDAP://"
0x18002aa00  mov     rbx, rcx
0x18002aa03  lea     rax, [rsp+58h+String2]
0x18002aa08  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002aa0c  movdqu  xmmword ptr [rsp+58h+String2], xmm0
0x18002aa12  mov     rdi, rcx
0x18002aa15  inc     rdi
0x18002aa18  cmp     word ptr [rax+rdi*2], 0
0x18002aa1d  jnz     short loc_18002AA15
0x18002aa1f  inc     rcx
0x18002aa22  cmp     word ptr [rbx+rcx*2], 0
0x18002aa27  jnz     short loc_18002AA1F
0x18002aa29  mov     eax, edi
0x18002aa2b  cmp     rcx, rax
0x18002aa2e  jbe     short loc_18002AA60
0x18002aa30  lea     rax, [rsp+58h+String2]
0x18002aa35  mov     [rsp+58h+cchCount2], edi; cchCount2
0x18002aa39  mov     r9d, edi; cchCount1
0x18002aa3c  mov     [rsp+58h+lpString2], rax; lpString2
0x18002aa41  mov     r8, rbx; lpString1
0x18002aa44  mov     edx, 1; dwCmpFlags
0x18002aa49  mov     ecx, 400h; Locale
0x18002aa4e  call    cs:__imp_CompareStringW
0x18002aa54  cmp     eax, 2
0x18002aa57  jnz     short loc_18002AA60
0x18002aa59  movsxd  rax, edi
0x18002aa5c  lea     rbx, [rbx+rax*2]
0x18002aa60  mov     rax, rbx
0x18002aa63  mov     rcx, [rsp+58h+var_18]
0x18002aa68  xor     rcx, rsp; StackCookie
0x18002aa6b  call    __security_check_cookie
0x18002aa70  mov     rbx, [rsp+58h+arg_8]
0x18002aa75  add     rsp, 50h
0x18002aa79  pop     rdi
0x18002aa7a  retn
```
