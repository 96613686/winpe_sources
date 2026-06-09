# PacValidateInfo4(_NETLOGON_VALIDATION_SAM_INFO4 * const)

- ea: `0x1800716bc`
- end: `0x18007174e`
- name: `?PacValidateInfo4@@YAJQEAU_NETLOGON_VALIDATION_SAM_INFO4@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO4 *const)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18006f428`

## callees

- `0x1800716bc`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180071700`
- `ntdll!RtlSubAuthorityCountSid` at `0x180071700`
- `ntdll!RtlValidSid` at `0x1800716ef`
- `ntdll!RtlValidSid` at `0x180071725`
- `ntdll!RtlValidSid` at `0x1800716ef`
- `ntdll!RtlValidSid` at `0x180071725`

## pseudocode

```c
__int64 __fastcall PacValidateInfo4(struct _NETLOGON_VALIDATION_SAM_INFO4 *const a1)
{
  unsigned int v1; // eax
  unsigned int v3; // ecx
  unsigned int i; // edi

  v1 = *((_DWORD *)a1 + 39);
  if ( v1 > 0x4000 )
    return 3221225818LL;
  v3 = *((_DWORD *)a1 + 68);
  if ( v3 > 0x4000 || v3 + v1 > 0x4000 )
    return 3221225818LL;
  if ( !RtlValidSid(*((PSID *)a1 + 28)) || *RtlSubAuthorityCountSid(*((PSID *)a1 + 28)) == 15 )
    return 3221225592LL;
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
0x1800716bc  mov     [rsp+arg_0], rbx
0x1800716c1  push    rdi
0x1800716c2  sub     rsp, 20h
0x1800716c6  mov     eax, [rcx+9Ch]
0x1800716cc  mov     edx, 4000h
0x1800716d1  mov     rbx, rcx
0x1800716d4  cmp     eax, edx
0x1800716d6  ja      short loc_18007173E
0x1800716d8  mov     ecx, [rcx+110h]
0x1800716de  cmp     ecx, edx
0x1800716e0  ja      short loc_18007173E
0x1800716e2  add     eax, ecx
0x1800716e4  cmp     eax, edx
0x1800716e6  ja      short loc_18007173E
0x1800716e8  mov     rcx, [rbx+0E0h]; Sid
0x1800716ef  call    cs:__imp_RtlValidSid
0x1800716f5  test    al, al
0x1800716f7  jz      short loc_180071737
0x1800716f9  mov     rcx, [rbx+0E0h]; Sid
0x180071700  call    cs:__imp_RtlSubAuthorityCountSid
0x180071706  cmp     byte ptr [rax], 0Fh
0x180071709  jz      short loc_180071737
0x18007170b  xor     edi, edi
0x18007170d  cmp     edi, [rbx+110h]
0x180071713  jnb     short loc_180071733
0x180071715  mov     rcx, [rbx+118h]
0x18007171c  mov     eax, edi
0x18007171e  add     rax, rax
0x180071721  mov     rcx, [rcx+rax*8]; Sid
0x180071725  call    cs:__imp_RtlValidSid
0x18007172b  test    al, al
0x18007172d  jz      short loc_180071737
0x18007172f  inc     edi
0x180071731  jmp     short loc_18007170D
0x180071733  xor     eax, eax
0x180071735  jmp     short loc_180071743
0x180071737  mov     eax, 0C0000078h
0x18007173c  jmp     short loc_180071743
0x18007173e  mov     eax, 0C000015Ah
0x180071743  mov     rbx, [rsp+28h+arg_0]
0x180071748  add     rsp, 20h
0x18007174c  pop     rdi
0x18007174d  retn
```
