# BiCloseKey

- ea: `0x14001e5e4`
- end: `0x14001e640`
- name: `BiCloseKey`
- size: `92`
- prototype: `NTSTATUS __fastcall(HANDLE Handle)`
- caller_count: `24`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140013b48`
- `0x140013c1c`
- `0x140013ee8`
- `0x140014130`
- `0x140014574`
- `0x140018890`
- `0x140018b54`
- `0x140019990`
- `0x140019bb8`
- `0x14001a264`
- `0x14001af00`
- `0x14001b354`
- `0x14001b4bc`
- `0x14001ba1c`
- `0x14001bd44`
- `0x14001c088`
- `0x14001ec14`
- `0x14001fc5c`
- `0x14001fd7c`
- `0x1400201ec`
- `0x1400207d4`
- `0x14002090c`
- `0x1400214ec`
- `0x140022258`

## callees

- `0x14001e5e4`
- `0x14001e980`

## import_xrefs

- `ntdll!ZwClose` at `0x14001e639`
- `ntdll!ZwSetSecurityObject` at `0x14001e60e`
- `ntdll!ZwSetSecurityObject` at `0x14001e60e`
- `ntdll!RtlFreeHeap` at `0x14001e626`
- `ntdll!RtlFreeHeap` at `0x14001e626`

## pseudocode

```c
NTSTATUS __fastcall BiCloseKey(HANDLE Handle)
{
  void *KeySecurityDescriptor; // rax
  void *v3; // rbx

  KeySecurityDescriptor = (void *)BiCreateKeySecurityDescriptor(0x60019u);
  v3 = KeySecurityDescriptor;
  if ( KeySecurityDescriptor )
  {
    ZwSetSecurityObject(Handle, 4u, KeySecurityDescriptor);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  }
  return ZwClose(Handle);
}

```

## disassembly

```asm
0x14001e5e4  mov     [rsp+arg_0], rbx
0x14001e5e9  push    rdi
0x14001e5ea  sub     rsp, 20h
0x14001e5ee  mov     rdi, rcx
0x14001e5f1  mov     ecx, 60019h; AccessMask
0x14001e5f6  call    BiCreateKeySecurityDescriptor
0x14001e5fb  mov     rbx, rax
0x14001e5fe  test    rax, rax
0x14001e601  jz      short loc_14001E62C
0x14001e603  mov     r8, rax; SecurityDescriptor
0x14001e606  mov     edx, 4; SecurityInformation
0x14001e60b  mov     rcx, rdi; Handle
0x14001e60e  call    cs:__imp_ZwSetSecurityObject
0x14001e614  mov     rcx, gs:60h
0x14001e61d  mov     r8, rbx; P
0x14001e620  xor     edx, edx; Flags
0x14001e622  mov     rcx, [rcx+30h]; HeapHandle
0x14001e626  call    cs:__imp_RtlFreeHeap
0x14001e62c  mov     rcx, rdi
0x14001e62f  mov     rbx, [rsp+28h+arg_0]
0x14001e634  add     rsp, 20h
0x14001e638  pop     rdi
0x14001e639  jmp     cs:__imp_ZwClose
```
