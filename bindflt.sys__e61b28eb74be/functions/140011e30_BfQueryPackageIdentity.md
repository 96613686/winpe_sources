# BfQueryPackageIdentity

- ea: `0x140011e30`
- end: `0x140011ea8`
- name: `BfQueryPackageIdentity`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140011fb4`

## callees

- `0x140011e30`

## import_xrefs

- `ntoskrnl!PsReferencePrimaryToken` at `0x140011e42`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140011e42`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140011e90`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140011e90`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140011e7f`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140011e7f`

## pseudocode

```c
__int64 __fastcall BfQueryPackageIdentity(struct _KPROCESS *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  PACCESS_TOKEN v8; // rdi
  unsigned int PackageIdentity; // ebx

  v8 = PsReferencePrimaryToken(a1);
  if ( v8 )
  {
    PackageIdentity = RtlQueryPackageIdentity(v8, a2, a3, a4, a5, 0);
    PsDereferencePrimaryToken(v8);
  }
  else
  {
    return (unsigned int)-1073741823;
  }
  return PackageIdentity;
}

```

## disassembly

```asm
0x140011e30  push    rbx
0x140011e32  push    rbp
0x140011e33  push    rsi
0x140011e34  push    rdi
0x140011e35  sub     rsp, 38h
0x140011e39  mov     rbx, r9
0x140011e3c  mov     rsi, r8
0x140011e3f  mov     rbp, rdx
0x140011e42  call    cs:__imp_PsReferencePrimaryToken
0x140011e49  nop     dword ptr [rax+rax+00h]
0x140011e4e  mov     rdi, rax
0x140011e51  test    rax, rax
0x140011e54  jnz     short loc_140011E5D
0x140011e56  mov     ebx, 0C0000001h
0x140011e5b  jmp     short loc_140011E9C
0x140011e5d  mov     rax, [rsp+58h+arg_20]
0x140011e65  mov     r9, rbx
0x140011e68  mov     [rsp+58h+var_30], 0
0x140011e71  mov     r8, rsi
0x140011e74  mov     rdx, rbp
0x140011e77  mov     [rsp+58h+var_38], rax
0x140011e7c  mov     rcx, rdi
0x140011e7f  call    cs:__imp_RtlQueryPackageIdentity
0x140011e86  nop     dword ptr [rax+rax+00h]
0x140011e8b  mov     ebx, eax
0x140011e8d  mov     rcx, rdi; PrimaryToken
0x140011e90  call    cs:__imp_PsDereferencePrimaryToken
0x140011e97  nop     dword ptr [rax+rax+00h]
0x140011e9c  mov     eax, ebx
0x140011e9e  add     rsp, 38h
0x140011ea2  pop     rdi
0x140011ea3  pop     rsi
0x140011ea4  pop     rbp
0x140011ea5  pop     rbx
0x140011ea6  retn
```
