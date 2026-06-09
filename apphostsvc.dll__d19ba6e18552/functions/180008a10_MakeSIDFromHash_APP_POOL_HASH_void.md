# MakeSIDFromHash(APP_POOL_HASH *,void * *)

- ea: `0x180008a10`
- end: `0x180008b16`
- name: `?MakeSIDFromHash@@YAJPEAUAPP_POOL_HASH@@PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct APP_POOL_HASH *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180007c5c`

## callees

- `0x180008a10`
- `0x180008c50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008a53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008a53`
- `ntdll!RtlInitializeSid` at `0x180008a76`
- `ntdll!RtlInitializeSid` at `0x180008a76`
- `ntdll!RtlSubAuthoritySid` at `0x180008a81`
- `ntdll!RtlSubAuthoritySid` at `0x180008a98`
- `ntdll!RtlSubAuthoritySid` at `0x180008aac`
- `ntdll!RtlSubAuthoritySid` at `0x180008ac0`
- `ntdll!RtlSubAuthoritySid` at `0x180008ad4`
- `ntdll!RtlSubAuthoritySid` at `0x180008ae8`
- `ntdll!RtlSubAuthoritySid` at `0x180008a81`
- `ntdll!RtlSubAuthoritySid` at `0x180008a98`
- `ntdll!RtlSubAuthoritySid` at `0x180008aac`
- `ntdll!RtlSubAuthoritySid` at `0x180008ac0`
- `ntdll!RtlSubAuthoritySid` at `0x180008ad4`
- `ntdll!RtlSubAuthoritySid` at `0x180008ae8`
- `ntdll!RtlLengthRequiredSid` at `0x180008a48`
- `ntdll!RtlLengthRequiredSid` at `0x180008a48`

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
0x180008a10  mov     [rsp+arg_0], rbx
0x180008a15  mov     [rsp+arg_10], rsi
0x180008a1a  push    rdi
0x180008a1b  push    r14
0x180008a1d  push    r15
0x180008a1f  sub     rsp, 30h
0x180008a23  mov     rax, cs:__security_cookie
0x180008a2a  xor     rax, rsp
0x180008a2d  mov     [rsp+48h+var_20], rax
0x180008a32  xor     esi, esi
0x180008a34  mov     word ptr [rsp+48h+IdentifierAuthority.Value+4], 500h
0x180008a3b  mov     r14, rcx
0x180008a3e  mov     dword ptr [rsp+48h+IdentifierAuthority.Value], esi
0x180008a42  mov     r15, rdx
0x180008a45  lea     ecx, [rsi+6]; SubAuthorityCount
0x180008a48  call    cs:__imp_RtlLengthRequiredSid
0x180008a4e  mov     edx, eax; uBytes
0x180008a50  lea     ecx, [rsi+40h]; uFlags
0x180008a53  call    cs:__imp_LocalAlloc
0x180008a59  mov     rdi, rax
0x180008a5c  test    rax, rax
0x180008a5f  jnz     short loc_180008A6B
0x180008a61  mov     esi, 8007000Eh
0x180008a66  jmp     loc_180008AF3
0x180008a6b  mov     r8b, 6; SubAuthorityCount
0x180008a6e  lea     rdx, [rsp+48h+IdentifierAuthority]; IdentifierAuthority
0x180008a73  mov     rcx, rdi; Sid
0x180008a76  call    cs:__imp_RtlInitializeSid
0x180008a7c  xor     edx, edx; SubAuthority
0x180008a7e  mov     rcx, rdi; Sid
0x180008a81  call    cs:__imp_RtlSubAuthoritySid
0x180008a87  mov     edx, 1; SubAuthority
0x180008a8c  mov     rcx, rdi; Sid
0x180008a8f  mov     dword ptr [rax], 52h ; 'R'
0x180008a95  mov     ebx, [r14]
0x180008a98  call    cs:__imp_RtlSubAuthoritySid
0x180008a9e  mov     edx, 2; SubAuthority
0x180008aa3  mov     rcx, rdi; Sid
0x180008aa6  mov     [rax], ebx
0x180008aa8  mov     ebx, [r14+4]
0x180008aac  call    cs:__imp_RtlSubAuthoritySid
0x180008ab2  mov     edx, 3; SubAuthority
0x180008ab7  mov     rcx, rdi; Sid
0x180008aba  mov     [rax], ebx
0x180008abc  mov     ebx, [r14+8]
0x180008ac0  call    cs:__imp_RtlSubAuthoritySid
0x180008ac6  mov     edx, 4; SubAuthority
0x180008acb  mov     rcx, rdi; Sid
0x180008ace  mov     [rax], ebx
0x180008ad0  mov     ebx, [r14+0Ch]
0x180008ad4  call    cs:__imp_RtlSubAuthoritySid
0x180008ada  mov     edx, 5; SubAuthority
0x180008adf  mov     rcx, rdi; Sid
0x180008ae2  mov     [rax], ebx
0x180008ae4  mov     ebx, [r14+10h]
0x180008ae8  call    cs:__imp_RtlSubAuthoritySid
0x180008aee  mov     [rax], ebx
0x180008af0  mov     [r15], rdi
0x180008af3  mov     eax, esi
0x180008af5  mov     rcx, [rsp+48h+var_20]
0x180008afa  xor     rcx, rsp; StackCookie
0x180008afd  call    __security_check_cookie
0x180008b02  mov     rbx, [rsp+48h+arg_0]
0x180008b07  mov     rsi, [rsp+48h+arg_10]
0x180008b0c  add     rsp, 30h
0x180008b10  pop     r15
0x180008b12  pop     r14
0x180008b14  pop     rdi
0x180008b15  retn
```
