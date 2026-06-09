# CVaultMgr::GetSidHashId(void *,ulong *)

- ea: `0x18002e6a0`
- end: `0x18002e700`
- name: `?GetSidHashId@CVaultMgr@@AEAAKPEAXPEAK@Z`
- size: `96`
- prototype: `__int64 __fastcall(CVaultMgr *this, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003c9f8`

## callees

- `0x18002e6a0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002e6d3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002e6d3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002e6c0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002e6c0`
- `ntdll!RtlValidSid` at `0x18002e6b3`
- `ntdll!RtlValidSid` at `0x18002e6b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVaultMgr::GetSidHashId(CVaultMgr *this, void *a2, unsigned int *a3)
{
  int v5; // ecx

  if ( !RtlValidSid(a2) )
    return 87;
  v5 = *GetSidSubAuthorityCount(a2);
  if ( !(_BYTE)v5 )
    return 87;
  *a3 = *GetSidSubAuthority(a2, v5 - 1) % 0xB;
  return 0;
}

```

## disassembly

```asm
0x18002e6a0  mov     [rsp+arg_0], rbx
0x18002e6a5  push    rdi
0x18002e6a6  sub     rsp, 20h
0x18002e6aa  mov     rcx, rdx; Sid
0x18002e6ad  mov     rdi, r8
0x18002e6b0  mov     rbx, rdx
0x18002e6b3  call    cs:__imp_RtlValidSid
0x18002e6b9  test    al, al
0x18002e6bb  jz      short loc_18002E6F9
0x18002e6bd  mov     rcx, rbx; pSid
0x18002e6c0  call    cs:__imp_GetSidSubAuthorityCount
0x18002e6c6  movzx   ecx, byte ptr [rax]
0x18002e6c9  test    cl, cl
0x18002e6cb  jz      short loc_18002E6F9
0x18002e6cd  lea     edx, [rcx-1]; nSubAuthority
0x18002e6d0  mov     rcx, rbx; pSid
0x18002e6d3  call    cs:__imp_GetSidSubAuthority
0x18002e6d9  mov     ecx, [rax]
0x18002e6db  mov     eax, 0BA2E8BA3h
0x18002e6e0  mul     ecx
0x18002e6e2  shr     edx, 3
0x18002e6e5  imul    eax, edx, 0Bh
0x18002e6e8  sub     ecx, eax
0x18002e6ea  mov     [rdi], ecx
0x18002e6ec  xor     eax, eax
0x18002e6ee  mov     rbx, [rsp+28h+arg_0]
0x18002e6f3  add     rsp, 20h
0x18002e6f7  pop     rdi
0x18002e6f8  retn
0x18002e6f9  mov     eax, 57h ; 'W'
0x18002e6fe  jmp     short loc_18002E6EE
```
