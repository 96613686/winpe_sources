# AipGetPackageClaim

- ea: `0x140022b60`
- end: `0x140022bd9`
- name: `AipGetPackageClaim`
- size: `121`
- prototype: `__int64 __fastcall(struct _KPROCESS *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003dd8`
- `0x140022afc`

## callees

- `0x140022b60`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140022bb8`
- `ntoskrnl!ObfDereferenceObject` at `0x140022bb8`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140022b72`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140022b72`
- `ntoskrnl!RtlQueryPackageClaims` at `0x140022ba7`
- `ntoskrnl!RtlQueryPackageClaims` at `0x140022ba7`

## pseudocode

```c
__int64 __fastcall AipGetPackageClaim(struct _KPROCESS *a1, _QWORD *a2)
{
  PACCESS_TOKEN v3; // rdi
  unsigned int PackageClaims; // ebx

  *a2 = 0;
  v3 = PsReferencePrimaryToken(a1);
  if ( v3 )
  {
    PackageClaims = RtlQueryPackageClaims(v3, 0, 0, 0, 0, 0, a2, 0);
    ObfDereferenceObject(v3);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return PackageClaims;
}

```

## disassembly

```asm
0x140022b60  mov     [rsp+arg_0], rbx
0x140022b65  push    rdi
0x140022b66  sub     rsp, 40h
0x140022b6a  xor     eax, eax
0x140022b6c  mov     rbx, rdx
0x140022b6f  mov     [rdx], rax
0x140022b72  call    cs:__imp_PsReferencePrimaryToken
0x140022b79  nop     dword ptr [rax+rax+00h]
0x140022b7e  mov     rdi, rax
0x140022b81  xor     eax, eax
0x140022b83  test    rdi, rdi
0x140022b86  jz      short loc_140022BC6
0x140022b88  mov     [rsp+48h+var_10], rax
0x140022b8d  xor     r9d, r9d
0x140022b90  mov     [rsp+48h+var_18], rbx
0x140022b95  xor     r8d, r8d
0x140022b98  mov     [rsp+48h+var_20], rax
0x140022b9d  xor     edx, edx
0x140022b9f  mov     rcx, rdi
0x140022ba2  mov     [rsp+48h+var_28], rax
0x140022ba7  call    cs:__imp_RtlQueryPackageClaims
0x140022bae  nop     dword ptr [rax+rax+00h]
0x140022bb3  mov     rcx, rdi; Object
0x140022bb6  mov     ebx, eax
0x140022bb8  call    cs:__imp_ObfDereferenceObject
0x140022bbf  nop     dword ptr [rax+rax+00h]
0x140022bc4  jmp     short loc_140022BCB
0x140022bc6  mov     ebx, 0C000000Dh
0x140022bcb  mov     eax, ebx
0x140022bcd  mov     rbx, [rsp+48h+arg_0]
0x140022bd2  add     rsp, 40h
0x140022bd6  pop     rdi
0x140022bd7  retn
```
