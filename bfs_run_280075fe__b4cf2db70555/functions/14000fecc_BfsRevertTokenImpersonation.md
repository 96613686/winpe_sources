# BfsRevertTokenImpersonation

- ea: `0x14000fecc`
- end: `0x14000ff33`
- name: `BfsRevertTokenImpersonation`
- size: `103`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140006810`
- `0x14000a3a0`
- `0x14000a7a0`
- `0x14000e110`

## callees

- `0x14000fecc`

## import_xrefs

- `ntoskrnl!PsRevertToSelf` at `0x14000fedb`
- `ntoskrnl!PsRevertToSelf` at `0x14000fedb`
- `ntoskrnl!PsImpersonateClient` at `0x14000ff17`
- `ntoskrnl!PsImpersonateClient` at `0x14000ff17`
- `ntoskrnl!ObfDereferenceObject` at `0x14000feea`
- `ntoskrnl!ObfDereferenceObject` at `0x14000feea`

## pseudocode

```c
__int64 __fastcall BfsRevertTokenImpersonation(__int64 a1)
{
  unsigned int v2; // edi
  void *v3; // rdx

  v2 = 0;
  PsRevertToSelf();
  ObfDereferenceObject(*(PVOID *)a1);
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    return (unsigned int)PsImpersonateClient(
                           KeGetCurrentThread(),
                           v3,
                           *(_BYTE *)(a1 + 16),
                           *(_BYTE *)(a1 + 17),
                           *(SECURITY_IMPERSONATION_LEVEL *)(a1 + 20));
  return v2;
}

```

## disassembly

```asm
0x14000fecc  mov     [rsp+arg_0], rbx
0x14000fed1  push    rdi
0x14000fed2  sub     rsp, 30h
0x14000fed6  mov     rbx, rcx
0x14000fed9  xor     edi, edi
0x14000fedb  call    cs:__imp_PsRevertToSelf
0x14000fee2  nop     dword ptr [rax+rax+00h]
0x14000fee7  mov     rcx, [rbx]; Object
0x14000feea  call    cs:__imp_ObfDereferenceObject
0x14000fef1  nop     dword ptr [rax+rax+00h]
0x14000fef6  mov     rdx, [rbx+8]; Token
0x14000fefa  test    rdx, rdx
0x14000fefd  jz      short loc_14000FF25
0x14000feff  mov     rcx, gs:188h; Thread
0x14000ff08  mov     eax, [rbx+14h]
0x14000ff0b  mov     r9b, [rbx+11h]; EffectiveOnly
0x14000ff0f  mov     r8b, [rbx+10h]; CopyOnOpen
0x14000ff13  mov     [rsp+38h+ImpersonationLevel], eax; ImpersonationLevel
0x14000ff17  call    cs:__imp_PsImpersonateClient
0x14000ff1e  nop     dword ptr [rax+rax+00h]
0x14000ff23  mov     edi, eax
0x14000ff25  mov     rbx, [rsp+38h+arg_0]
0x14000ff2a  mov     eax, edi
0x14000ff2c  add     rsp, 30h
0x14000ff30  pop     rdi
0x14000ff31  retn
```
