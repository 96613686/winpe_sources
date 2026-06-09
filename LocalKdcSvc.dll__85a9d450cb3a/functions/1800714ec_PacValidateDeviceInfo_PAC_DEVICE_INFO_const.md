# PacValidateDeviceInfo(_PAC_DEVICE_INFO * const)

- ea: `0x1800714ec`
- end: `0x1800715c2`
- name: `?PacValidateDeviceInfo@@YAJQEAU_PAC_DEVICE_INFO@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(struct _PAC_DEVICE_INFO *const)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180070fdc`

## callees

- `0x1800714ec`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180071536`
- `ntdll!RtlSubAuthorityCountSid` at `0x180071576`
- `ntdll!RtlSubAuthorityCountSid` at `0x180071536`
- `ntdll!RtlSubAuthorityCountSid` at `0x180071576`
- `ntdll!RtlValidSid` at `0x180071528`
- `ntdll!RtlValidSid` at `0x180071564`
- `ntdll!RtlValidSid` at `0x180071599`
- `ntdll!RtlValidSid` at `0x180071528`
- `ntdll!RtlValidSid` at `0x180071564`
- `ntdll!RtlValidSid` at `0x180071599`

## pseudocode

```c
__int64 __fastcall PacValidateDeviceInfo(struct _PAC_DEVICE_INFO *const a1)
{
  unsigned int v1; // eax
  unsigned int v3; // ecx
  unsigned int v4; // esi
  __int64 i; // rdi
  __int64 v6; // rcx
  unsigned int j; // edi

  v1 = *((_DWORD *)a1 + 4);
  if ( v1 > 0x4000 )
    return 3221225818LL;
  v3 = *((_DWORD *)a1 + 8);
  if ( v3 > 0x4000 )
    return 3221225818LL;
  v4 = v3 + v1;
  if ( v3 + v1 > 0x4000 )
    return 3221225818LL;
  if ( !RtlValidSid(*((PSID *)a1 + 1)) || *RtlSubAuthorityCountSid(*((PSID *)a1 + 1)) == 15 )
    return 3221225592LL;
  for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 12); i = (unsigned int)(i + 1) )
  {
    v6 = *((_QWORD *)a1 + 7);
    if ( *(_DWORD *)(v6 + 24 * i + 8) > 0x4000u )
      return 3221225818LL;
    v4 += *(_DWORD *)(v6 + 24 * i + 8);
    if ( v4 > 0x4000 )
      return 3221225818LL;
    if ( !RtlValidSid(*(PSID *)(v6 + 24 * i)) || *RtlSubAuthorityCountSid(*(PSID *)(*((_QWORD *)a1 + 7) + 24 * i)) == 15 )
      return 3221225592LL;
  }
  for ( j = 0; j < *((_DWORD *)a1 + 8); ++j )
  {
    if ( !RtlValidSid(*(PSID *)(*((_QWORD *)a1 + 5) + 16LL * j)) )
      return 3221225592LL;
  }
  return 0;
}

```

## disassembly

```asm
0x1800714ec  push    rbx
0x1800714ee  push    rbp
0x1800714ef  push    rsi
0x1800714f0  push    rdi
0x1800714f1  push    r14
0x1800714f3  sub     rsp, 20h
0x1800714f7  mov     eax, [rcx+10h]
0x1800714fa  mov     r14d, 4000h
0x180071500  mov     rbx, rcx
0x180071503  cmp     eax, r14d
0x180071506  ja      loc_1800715B2
0x18007150c  mov     ecx, [rcx+20h]
0x18007150f  cmp     ecx, r14d
0x180071512  ja      loc_1800715B2
0x180071518  lea     esi, [rcx+rax]
0x18007151b  cmp     esi, r14d
0x18007151e  ja      loc_1800715B2
0x180071524  mov     rcx, [rbx+8]; Sid
0x180071528  call    cs:__imp_RtlValidSid
0x18007152e  test    al, al
0x180071530  jz      short loc_1800715AB
0x180071532  mov     rcx, [rbx+8]; Sid
0x180071536  call    cs:__imp_RtlSubAuthorityCountSid
0x18007153c  cmp     byte ptr [rax], 0Fh
0x18007153f  jz      short loc_1800715AB
0x180071541  xor     edi, edi
0x180071543  cmp     edi, [rbx+30h]
0x180071546  jnb     short loc_180071585
0x180071548  mov     rcx, [rbx+38h]
0x18007154c  lea     rbp, [rdi+rdi*2]
0x180071550  cmp     [rcx+rbp*8+8], r14d
0x180071555  ja      short loc_1800715B2
0x180071557  add     esi, [rcx+rbp*8+8]
0x18007155b  cmp     esi, r14d
0x18007155e  ja      short loc_1800715B2
0x180071560  mov     rcx, [rcx+rbp*8]; Sid
0x180071564  call    cs:__imp_RtlValidSid
0x18007156a  test    al, al
0x18007156c  jz      short loc_1800715AB
0x18007156e  mov     rcx, [rbx+38h]
0x180071572  mov     rcx, [rcx+rbp*8]; Sid
0x180071576  call    cs:__imp_RtlSubAuthorityCountSid
0x18007157c  cmp     byte ptr [rax], 0Fh
0x18007157f  jz      short loc_1800715AB
0x180071581  inc     edi
0x180071583  jmp     short loc_180071543
0x180071585  xor     edi, edi
0x180071587  cmp     edi, [rbx+20h]
0x18007158a  jnb     short loc_1800715A7
0x18007158c  mov     rcx, [rbx+28h]
0x180071590  mov     eax, edi
0x180071592  add     rax, rax
0x180071595  mov     rcx, [rcx+rax*8]; Sid
0x180071599  call    cs:__imp_RtlValidSid
0x18007159f  test    al, al
0x1800715a1  jz      short loc_1800715AB
0x1800715a3  inc     edi
0x1800715a5  jmp     short loc_180071587
0x1800715a7  xor     eax, eax
0x1800715a9  jmp     short loc_1800715B7
0x1800715ab  mov     eax, 0C0000078h
0x1800715b0  jmp     short loc_1800715B7
0x1800715b2  mov     eax, 0C000015Ah
0x1800715b7  add     rsp, 20h
0x1800715bb  pop     r14
0x1800715bd  pop     rdi
0x1800715be  pop     rsi
0x1800715bf  pop     rbp
0x1800715c0  pop     rbx
0x1800715c1  retn
```
