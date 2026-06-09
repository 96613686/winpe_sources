# DependentFSRegisterDeviceName

- ea: `0x18000e680`
- end: `0x18000e762`
- name: `DependentFSRegisterDeviceName`
- size: `226`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180002180`
- `0x18000e680`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x18000e6a7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18000e6a7`
- `ntoskrnl!ExAllocatePool2` at `0x18000e6cf`
- `ntoskrnl!ExAllocatePool2` at `0x18000e6cf`

## pseudocode

```c
__int64 __fastcall DependentFSRegisterDeviceName(__int64 a1, const UNICODE_STRING *a2)
{
  void *Pool2; // rax

  if ( *(_QWORD *)(a1 + 160) )
    return RtlCompareUnicodeString(a2, (PCUNICODE_STRING)(a1 + 152), 0) != 0 ? 0xC000000D : 0;
  Pool2 = (void *)ExAllocatePool2(256, a2->Length, 1682206788);
  *(_QWORD *)(a1 + 160) = Pool2;
  if ( Pool2 )
  {
    *(_WORD *)(a1 + 152) = a2->Length;
    *(_WORD *)(a1 + 154) = a2->Length;
    memmove(Pool2, a2->Buffer, a2->Length);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        WPP_d7b1782a7daa350f3d08b40019c93e7e_Traceguids,
        3221225626LL,
        a2->Length);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x18000e680  mov     [rsp+arg_0], rbx
0x18000e685  push    rdi
0x18000e686  sub     rsp, 30h
0x18000e68a  cmp     qword ptr [rcx+0A0h], 0
0x18000e692  mov     rbx, rdx
0x18000e695  mov     rdi, rcx
0x18000e698  jz      short loc_18000E6C1
0x18000e69a  lea     rdx, [rcx+98h]; String2
0x18000e6a1  xor     r8d, r8d; CaseInSensitive
0x18000e6a4  mov     rcx, rbx; String1
0x18000e6a7  call    cs:__imp_RtlCompareUnicodeString
0x18000e6ae  nop     dword ptr [rax+rax+00h]
0x18000e6b3  neg     eax
0x18000e6b5  sbb     eax, eax
0x18000e6b7  and     eax, 0C000000Dh
0x18000e6bc  jmp     loc_18000E756
0x18000e6c1  movzx   edx, word ptr [rdx]
0x18000e6c4  mov     ecx, 100h
0x18000e6c9  mov     r8d, 64447044h
0x18000e6cf  call    cs:__imp_ExAllocatePool2
0x18000e6d6  nop     dword ptr [rax+rax+00h]
0x18000e6db  mov     [rdi+0A0h], rax
0x18000e6e2  mov     rcx, rax; void *
0x18000e6e5  test    rax, rax
0x18000e6e8  jnz     short loc_18000E733
0x18000e6ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6f1  lea     rax, WPP_GLOBAL_Control
0x18000e6f8  cmp     rcx, rax
0x18000e6fb  jz      short loc_18000E72C
0x18000e6fd  mov     eax, [rcx+2Ch]
0x18000e700  test    al, 1
0x18000e702  jz      short loc_18000E72C
0x18000e704  cmp     byte ptr [rcx+29h], 2
0x18000e708  jb      short loc_18000E72C
0x18000e70a  movzx   eax, word ptr [rbx]
0x18000e70d  lea     r8, WPP_d7b1782a7daa350f3d08b40019c93e7e_Traceguids
0x18000e714  mov     rcx, [rcx+18h]
0x18000e718  mov     edx, 19h
0x18000e71d  mov     r9d, 0C000009Ah
0x18000e723  mov     [rsp+38h+var_18], eax
0x18000e727  call    WPP_SF_DD
0x18000e72c  mov     eax, 0C000009Ah
0x18000e731  jmp     short loc_18000E756
0x18000e733  movzx   eax, word ptr [rbx]
0x18000e736  mov     [rdi+98h], ax
0x18000e73d  movzx   eax, word ptr [rbx]
0x18000e740  mov     [rdi+9Ah], ax
0x18000e747  movzx   r8d, word ptr [rbx]; Size
0x18000e74b  mov     rdx, [rbx+8]; Src
0x18000e74f  call    memmove
0x18000e754  xor     eax, eax
0x18000e756  mov     rbx, [rsp+38h+arg_0]
0x18000e75b  add     rsp, 30h
0x18000e75f  pop     rdi
0x18000e760  retn
```
