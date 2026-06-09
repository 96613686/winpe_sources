# appv::shared::kernel::ThreadHandles<Streaming::StreamFaultTagInfo>::~ThreadHandles<Streaming::StreamFaultTagInfo>(void)

- ea: `0x1400039e4`
- end: `0x140003aa1`
- name: `??1?$ThreadHandles@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003aa8`
- `0x14000528c`

## callees

- `0x1400039e4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140003a07`
- `ntoskrnl!ObfDereferenceObject` at `0x140003a07`
- `ntoskrnl!ExDeleteResourceLite` at `0x140003a44`
- `ntoskrnl!ExDeleteResourceLite` at `0x140003a44`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a89`

## pseudocode

```c
void __fastcall appv::shared::kernel::ThreadHandles<Streaming::StreamFaultTagInfo>::~ThreadHandles<Streaming::StreamFaultTagInfo>(
        __int64 a1)
{
  int i; // eax
  __int64 v3; // rbx
  struct _ERESOURCE *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  for ( i = *(_DWORD *)(a1 + 36); i; i = *(_DWORD *)(a1 + 36) )
  {
    v3 = (unsigned int)(i - 1);
    ObfDereferenceObject(*(PVOID *)(*(_QWORD *)(a1 + 8) + 8 * v3));
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v3) = *(_QWORD *)(*(_QWORD *)(a1 + 8)
                                                          + 8LL * (unsigned int)--*(_DWORD *)(a1 + 36));
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * *(unsigned int *)(a1 + 36)) = 0;
  }
  v4 = *(struct _ERESOURCE **)(a1 + 56);
  if ( v4 )
  {
    ExDeleteResourceLite(v4);
    v5 = *(void **)(a1 + 56);
    if ( v5 )
      ExFreePoolWithTag(v5, 0);
  }
  v6 = *(void **)(a1 + 24);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  v7 = *(void **)(a1 + 8);
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
}

```

## disassembly

```asm
0x1400039e4  mov     [rsp+arg_0], rbx
0x1400039e9  push    rdi
0x1400039ea  sub     rsp, 20h
0x1400039ee  mov     eax, [rcx+24h]
0x1400039f1  mov     rdi, rcx
0x1400039f4  jmp     short loc_140003A37
0x1400039f6  lea     ecx, [rax-1]
0x1400039f9  cmp     ecx, eax
0x1400039fb  jnb     short loc_140003A34
0x1400039fd  mov     ebx, ecx
0x1400039ff  mov     rcx, [rdi+8]
0x140003a03  mov     rcx, [rcx+rbx*8]; Object
0x140003a07  call    cs:__imp_ObfDereferenceObject
0x140003a0e  nop     dword ptr [rax+rax+00h]
0x140003a13  dec     dword ptr [rdi+24h]
0x140003a16  mov     rcx, [rdi+8]
0x140003a1a  mov     eax, [rdi+24h]
0x140003a1d  mov     rax, [rcx+rax*8]
0x140003a21  mov     [rcx+rbx*8], rax
0x140003a25  mov     ecx, [rdi+24h]
0x140003a28  mov     rax, [rdi+8]
0x140003a2c  mov     qword ptr [rax+rcx*8], 0
0x140003a34  mov     eax, [rdi+24h]
0x140003a37  test    eax, eax
0x140003a39  jnz     short loc_1400039F6
0x140003a3b  mov     rcx, [rdi+38h]; Resource
0x140003a3f  test    rcx, rcx
0x140003a42  jz      short loc_140003A67
0x140003a44  call    cs:__imp_ExDeleteResourceLite
0x140003a4b  nop     dword ptr [rax+rax+00h]
0x140003a50  mov     rcx, [rdi+38h]; P
0x140003a54  test    rcx, rcx
0x140003a57  jz      short loc_140003A67
0x140003a59  xor     edx, edx; Tag
0x140003a5b  call    cs:__imp_ExFreePoolWithTag
0x140003a62  nop     dword ptr [rax+rax+00h]
0x140003a67  mov     rcx, [rdi+18h]; P
0x140003a6b  test    rcx, rcx
0x140003a6e  jz      short loc_140003A7E
0x140003a70  xor     edx, edx; Tag
0x140003a72  call    cs:__imp_ExFreePoolWithTag
0x140003a79  nop     dword ptr [rax+rax+00h]
0x140003a7e  mov     rcx, [rdi+8]; P
0x140003a82  test    rcx, rcx
0x140003a85  jz      short loc_140003A95
0x140003a87  xor     edx, edx; Tag
0x140003a89  call    cs:__imp_ExFreePoolWithTag
0x140003a90  nop     dword ptr [rax+rax+00h]
0x140003a95  mov     rbx, [rsp+28h+arg_0]
0x140003a9a  add     rsp, 20h
0x140003a9e  pop     rdi
0x140003a9f  retn
```
