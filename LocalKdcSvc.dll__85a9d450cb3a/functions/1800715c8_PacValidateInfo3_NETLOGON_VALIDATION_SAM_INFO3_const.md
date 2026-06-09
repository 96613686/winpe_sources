# PacValidateInfo3(_NETLOGON_VALIDATION_SAM_INFO3 * const)

- ea: `0x1800715c8`
- end: `0x1800716b3`
- name: `?PacValidateInfo3@@YAJQEAU_NETLOGON_VALIDATION_SAM_INFO3@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *const)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800710d8`

## callees

- `0x1800715c8`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18007162d`
- `ntdll!RtlSubAuthorityCountSid` at `0x180071665`
- `ntdll!RtlSubAuthorityCountSid` at `0x18007162d`
- `ntdll!RtlSubAuthorityCountSid` at `0x180071665`
- `ntdll!RtlValidSid` at `0x18007161c`
- `ntdll!RtlValidSid` at `0x180071654`
- `ntdll!RtlValidSid` at `0x18007168a`
- `ntdll!RtlValidSid` at `0x18007161c`
- `ntdll!RtlValidSid` at `0x180071654`
- `ntdll!RtlValidSid` at `0x18007168a`

## pseudocode

```c
__int64 __fastcall PacValidateInfo3(struct _NETLOGON_VALIDATION_SAM_INFO3 *const a1)
{
  unsigned int v2; // ecx
  unsigned int v3; // eax
  unsigned int v4; // edx
  unsigned int i; // edi

  v2 = *((_DWORD *)a1 + 39);
  if ( v2 > 0x4000 )
    return 3221225818LL;
  v3 = *((_DWORD *)a1 + 74);
  if ( v3 > 0x4000 )
    return 3221225818LL;
  v4 = *((_DWORD *)a1 + 68);
  if ( v4 > 0x4000 || v2 + v4 + v3 > 0x4000 )
    return 3221225818LL;
  if ( !RtlValidSid(*((PSID *)a1 + 28))
    || *RtlSubAuthorityCountSid(*((PSID *)a1 + 28)) == 15
    || (*((_DWORD *)a1 + 42) & 0x200) != 0
    && *((_DWORD *)a1 + 74)
    && (!RtlValidSid(*((PSID *)a1 + 36)) || *RtlSubAuthorityCountSid(*((PSID *)a1 + 36)) == 15) )
  {
    return 3221225592LL;
  }
  for ( i = 0; i < *((_DWORD *)a1 + 68); ++i )
  {
    if ( !RtlValidSid(*(PSID *)(*((_QWORD *)a1 + 35) + 16LL * i)) )
      return 3221225592LL;
  }
  return 0;
}

```

## disassembly

```asm
0x1800715c8  mov     [rsp+arg_0], rbx
0x1800715cd  push    rdi
0x1800715ce  sub     rsp, 20h
0x1800715d2  mov     rbx, rcx
0x1800715d5  mov     r8d, 4000h
0x1800715db  mov     ecx, [rcx+9Ch]
0x1800715e1  cmp     ecx, r8d
0x1800715e4  ja      loc_1800716A3
0x1800715ea  mov     eax, [rbx+128h]
0x1800715f0  cmp     eax, r8d
0x1800715f3  ja      loc_1800716A3
0x1800715f9  mov     edx, [rbx+110h]
0x1800715ff  cmp     edx, r8d
0x180071602  ja      loc_1800716A3
0x180071608  add     eax, edx
0x18007160a  add     eax, ecx
0x18007160c  cmp     eax, r8d
0x18007160f  ja      loc_1800716A3
0x180071615  mov     rcx, [rbx+0E0h]; Sid
0x18007161c  call    cs:__imp_RtlValidSid
0x180071622  test    al, al
0x180071624  jz      short loc_18007169C
0x180071626  mov     rcx, [rbx+0E0h]; Sid
0x18007162d  call    cs:__imp_RtlSubAuthorityCountSid
0x180071633  cmp     byte ptr [rax], 0Fh
0x180071636  jz      short loc_18007169C
0x180071638  test    dword ptr [rbx+0A8h], 200h
0x180071642  jz      short loc_180071670
0x180071644  cmp     dword ptr [rbx+128h], 0
0x18007164b  jz      short loc_180071670
0x18007164d  mov     rcx, [rbx+120h]; Sid
0x180071654  call    cs:__imp_RtlValidSid
0x18007165a  test    al, al
0x18007165c  jz      short loc_18007169C
0x18007165e  mov     rcx, [rbx+120h]; Sid
0x180071665  call    cs:__imp_RtlSubAuthorityCountSid
0x18007166b  cmp     byte ptr [rax], 0Fh
0x18007166e  jz      short loc_18007169C
0x180071670  xor     edi, edi
0x180071672  cmp     edi, [rbx+110h]
0x180071678  jnb     short loc_180071698
0x18007167a  mov     rcx, [rbx+118h]
0x180071681  mov     eax, edi
0x180071683  add     rax, rax
0x180071686  mov     rcx, [rcx+rax*8]; Sid
0x18007168a  call    cs:__imp_RtlValidSid
0x180071690  test    al, al
0x180071692  jz      short loc_18007169C
0x180071694  inc     edi
0x180071696  jmp     short loc_180071672
0x180071698  xor     eax, eax
0x18007169a  jmp     short loc_1800716A8
0x18007169c  mov     eax, 0C0000078h
0x1800716a1  jmp     short loc_1800716A8
0x1800716a3  mov     eax, 0C000015Ah
0x1800716a8  mov     rbx, [rsp+28h+arg_0]
0x1800716ad  add     rsp, 20h
0x1800716b1  pop     rdi
0x1800716b2  retn
```
