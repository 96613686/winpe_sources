# MakeSIDFromHash(APP_POOL_HASH *,void * *)

- ea: `0x18002be00`
- end: `0x18002bf06`
- name: `?MakeSIDFromHash@@YAJPEAUAPP_POOL_HASH@@PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct APP_POOL_HASH *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002bda4`

## callees

- `0x180003460`
- `0x18002be00`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x18002be66`
- `ntdll!RtlInitializeSid` at `0x18002be66`
- `ntdll!RtlSubAuthoritySid` at `0x18002be71`
- `ntdll!RtlSubAuthoritySid` at `0x18002be88`
- `ntdll!RtlSubAuthoritySid` at `0x18002be9c`
- `ntdll!RtlSubAuthoritySid` at `0x18002beb0`
- `ntdll!RtlSubAuthoritySid` at `0x18002bec4`
- `ntdll!RtlSubAuthoritySid` at `0x18002bed8`
- `ntdll!RtlSubAuthoritySid` at `0x18002be71`
- `ntdll!RtlSubAuthoritySid` at `0x18002be88`
- `ntdll!RtlSubAuthoritySid` at `0x18002be9c`
- `ntdll!RtlSubAuthoritySid` at `0x18002beb0`
- `ntdll!RtlSubAuthoritySid` at `0x18002bec4`
- `ntdll!RtlSubAuthoritySid` at `0x18002bed8`
- `ntdll!RtlLengthRequiredSid` at `0x18002be38`
- `ntdll!RtlLengthRequiredSid` at `0x18002be38`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002be43`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002be43`

## pseudocode

```c
__int64 __fastcall MakeSIDFromHash(ULONG *a1, void **a2)
{
  unsigned int v2; // esi
  ULONG v5; // eax
  HLOCAL v6; // rax
  void *v7; // rdi
  ULONG v8; // ebx
  ULONG v9; // ebx
  ULONG v10; // ebx
  ULONG v11; // ebx
  ULONG v12; // ebx
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-28h] BYREF

  v2 = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v5 = RtlLengthRequiredSid(6u);
  v6 = LocalAlloc(0x40u, v5);
  v7 = v6;
  if ( v6 )
  {
    RtlInitializeSid(v6, &IdentifierAuthority, 6u);
    *RtlSubAuthoritySid(v7, 0) = 82;
    v8 = *a1;
    *RtlSubAuthoritySid(v7, 1u) = v8;
    v9 = a1[1];
    *RtlSubAuthoritySid(v7, 2u) = v9;
    v10 = a1[2];
    *RtlSubAuthoritySid(v7, 3u) = v10;
    v11 = a1[3];
    *RtlSubAuthoritySid(v7, 4u) = v11;
    v12 = a1[4];
    *RtlSubAuthoritySid(v7, 5u) = v12;
    *a2 = v7;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v2;
}

```

## disassembly

```asm
0x18002be00  mov     [rsp+arg_0], rbx
0x18002be05  mov     [rsp+arg_10], rsi
0x18002be0a  push    rdi
0x18002be0b  push    r14
0x18002be0d  push    r15
0x18002be0f  sub     rsp, 30h
0x18002be13  mov     rax, cs:__security_cookie
0x18002be1a  xor     rax, rsp
0x18002be1d  mov     [rsp+48h+var_20], rax
0x18002be22  xor     esi, esi
0x18002be24  mov     word ptr [rsp+48h+IdentifierAuthority.Value+4], 500h
0x18002be2b  mov     r14, rcx
0x18002be2e  mov     dword ptr [rsp+48h+IdentifierAuthority.Value], esi
0x18002be32  mov     r15, rdx
0x18002be35  lea     ecx, [rsi+6]; SubAuthorityCount
0x18002be38  call    cs:__imp_RtlLengthRequiredSid
0x18002be3e  mov     edx, eax; uBytes
0x18002be40  lea     ecx, [rsi+40h]; uFlags
0x18002be43  call    cs:__imp_LocalAlloc
0x18002be49  mov     rdi, rax
0x18002be4c  test    rax, rax
0x18002be4f  jnz     short loc_18002BE5B
0x18002be51  mov     esi, 8007000Eh
0x18002be56  jmp     loc_18002BEE3
0x18002be5b  mov     r8b, 6; SubAuthorityCount
0x18002be5e  lea     rdx, [rsp+48h+IdentifierAuthority]; IdentifierAuthority
0x18002be63  mov     rcx, rdi; Sid
0x18002be66  call    cs:__imp_RtlInitializeSid
0x18002be6c  xor     edx, edx; SubAuthority
0x18002be6e  mov     rcx, rdi; Sid
0x18002be71  call    cs:__imp_RtlSubAuthoritySid
0x18002be77  mov     edx, 1; SubAuthority
0x18002be7c  mov     rcx, rdi; Sid
0x18002be7f  mov     dword ptr [rax], 52h ; 'R'
0x18002be85  mov     ebx, [r14]
0x18002be88  call    cs:__imp_RtlSubAuthoritySid
0x18002be8e  mov     edx, 2; SubAuthority
0x18002be93  mov     rcx, rdi; Sid
0x18002be96  mov     [rax], ebx
0x18002be98  mov     ebx, [r14+4]
0x18002be9c  call    cs:__imp_RtlSubAuthoritySid
0x18002bea2  mov     edx, 3; SubAuthority
0x18002bea7  mov     rcx, rdi; Sid
0x18002beaa  mov     [rax], ebx
0x18002beac  mov     ebx, [r14+8]
0x18002beb0  call    cs:__imp_RtlSubAuthoritySid
0x18002beb6  mov     edx, 4; SubAuthority
0x18002bebb  mov     rcx, rdi; Sid
0x18002bebe  mov     [rax], ebx
0x18002bec0  mov     ebx, [r14+0Ch]
0x18002bec4  call    cs:__imp_RtlSubAuthoritySid
0x18002beca  mov     edx, 5; SubAuthority
0x18002becf  mov     rcx, rdi; Sid
0x18002bed2  mov     [rax], ebx
0x18002bed4  mov     ebx, [r14+10h]
0x18002bed8  call    cs:__imp_RtlSubAuthoritySid
0x18002bede  mov     [rax], ebx
0x18002bee0  mov     [r15], rdi
0x18002bee3  mov     eax, esi
0x18002bee5  mov     rcx, [rsp+48h+var_20]
0x18002beea  xor     rcx, rsp; StackCookie
0x18002beed  call    __security_check_cookie
0x18002bef2  mov     rbx, [rsp+48h+arg_0]
0x18002bef7  mov     rsi, [rsp+48h+arg_10]
0x18002befc  add     rsp, 30h
0x18002bf00  pop     r15
0x18002bf02  pop     r14
0x18002bf04  pop     rdi
0x18002bf05  retn
```
