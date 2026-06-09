# VfsReleaseMappingEntry

- ea: `0x140009368`
- end: `0x1400093e8`
- name: `VfsReleaseMappingEntry`
- size: `128`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `21`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002b4c`
- `0x1400034a0`
- `0x140003c00`
- `0x1400061b4`
- `0x140007124`
- `0x140007c7c`
- `0x14000874c`
- `0x140009350`
- `0x140009784`
- `0x140009f94`
- `0x14000a3c0`
- `0x14000a5a0`
- `0x14000a790`
- `0x14000aefc`
- `0x14000b4ec`
- `0x14000c574`
- `0x14000c6fc`
- `0x14000ca28`
- `0x14000cfd8`
- `0x14000d72c`
- `0x14000e110`

## callees

- `0x140009368`
- `0x14000e850`
- `0x140013844`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009391`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400093b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400093d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009391`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400093b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400093d5`

## pseudocode

```c
void __fastcall VfsReleaseMappingEntry(PVOID P)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P, 0xFFFFFFFF) == 1 )
  {
    DeleteMappingNames((__int64)P + 40);
    v2 = (void *)*((_QWORD *)P + 2);
    if ( v2 )
    {
      ExFreePoolWithTag(v2, 0);
      *((_QWORD *)P + 2) = 0;
    }
    v3 = (void *)*((_QWORD *)P + 4);
    if ( v3 )
    {
      ExFreePoolWithTag(v3, 0);
      *((_QWORD *)P + 4) = 0;
    }
    VfsDeleteSecurityDescriptors((void **)P + 9);
    ExFreePoolWithTag(P, 0x654D4656u);
  }
}

```

## disassembly

```asm
0x140009368  push    rbx
0x14000936a  sub     rsp, 20h
0x14000936e  mov     rbx, rcx
0x140009371  or      eax, 0FFFFFFFFh
0x140009374  lock xadd [rcx], eax
0x140009378  cmp     eax, 1
0x14000937b  jnz     short loc_1400093E1
0x14000937d  add     rcx, 28h ; '('
0x140009381  call    DeleteMappingNames
0x140009386  mov     rcx, [rbx+10h]; P
0x14000938a  test    rcx, rcx
0x14000938d  jz      short loc_1400093A5
0x14000938f  xor     edx, edx; Tag
0x140009391  call    cs:__imp_ExFreePoolWithTag
0x140009398  nop     dword ptr [rax+rax+00h]
0x14000939d  mov     qword ptr [rbx+10h], 0
0x1400093a5  mov     rcx, [rbx+20h]; P
0x1400093a9  test    rcx, rcx
0x1400093ac  jz      short loc_1400093C4
0x1400093ae  xor     edx, edx; Tag
0x1400093b0  call    cs:__imp_ExFreePoolWithTag
0x1400093b7  nop     dword ptr [rax+rax+00h]
0x1400093bc  mov     qword ptr [rbx+20h], 0
0x1400093c4  lea     rcx, [rbx+48h]
0x1400093c8  call    VfsDeleteSecurityDescriptors
0x1400093cd  mov     edx, 654D4656h; Tag
0x1400093d2  mov     rcx, rbx; P
0x1400093d5  call    cs:__imp_ExFreePoolWithTag
0x1400093dc  nop     dword ptr [rax+rax+00h]
0x1400093e1  add     rsp, 20h
0x1400093e5  pop     rbx
0x1400093e6  retn
```
