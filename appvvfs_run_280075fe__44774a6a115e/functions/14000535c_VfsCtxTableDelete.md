# VfsCtxTableDelete

- ea: `0x14000535c`
- end: `0x1400053f7`
- name: `VfsCtxTableDelete`
- size: `155`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400059e8`
- `0x140024008`

## callees

- `0x14000535c`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400053a3`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400053a3`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14000537e`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14000537e`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140005392`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140005392`
- `ntoskrnl!ExRundownCompleted` at `0x1400053df`
- `ntoskrnl!ExRundownCompleted` at `0x1400053df`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400053bb`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400053bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400053cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400053cf`

## pseudocode

```c
void __fastcall VfsCtxTableDelete(PRTL_AVL_TABLE Table)
{
  PVOID v2; // rax
  struct _ERESOURCE *RightChild; // rbx

  if ( Table[1].BalancedRoot.RightChild )
  {
    if ( (*(_DWORD *)&Table[1].BalancedRoot.Balance & 1) != 0 )
      ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)&Table[1].BalancedRoot.LeftChild);
    while ( 1 )
    {
      v2 = RtlEnumerateGenericTableAvl(Table, 1u);
      if ( !v2 )
        break;
      RtlDeleteElementGenericTableAvl(Table, v2);
    }
    RightChild = (struct _ERESOURCE *)Table[1].BalancedRoot.RightChild;
    ExDeleteResourceLite(RightChild);
    ExFreePoolWithTag(RightChild, 0x72454656u);
    ExRundownCompleted((PEX_RUNDOWN_REF)&Table[1].BalancedRoot.LeftChild);
  }
}

```

## disassembly

```asm
0x14000535c  mov     [rsp+arg_0], rbx
0x140005361  push    rdi
0x140005362  sub     rsp, 20h
0x140005366  cmp     qword ptr [rcx+78h], 0
0x14000536b  mov     rdi, rcx
0x14000536e  jz      short loc_1400053EB
0x140005370  mov     eax, [rcx+80h]
0x140005376  test    al, 1
0x140005378  jz      short loc_14000539E
0x14000537a  add     rcx, 70h ; 'p'; RunRef
0x14000537e  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140005385  nop     dword ptr [rax+rax+00h]
0x14000538a  jmp     short loc_14000539E
0x14000538c  mov     rdx, rax; Buffer
0x14000538f  mov     rcx, rdi; Table
0x140005392  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140005399  nop     dword ptr [rax+rax+00h]
0x14000539e  mov     dl, 1; Restart
0x1400053a0  mov     rcx, rdi; Table
0x1400053a3  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400053aa  nop     dword ptr [rax+rax+00h]
0x1400053af  test    rax, rax
0x1400053b2  jnz     short loc_14000538C
0x1400053b4  mov     rbx, [rdi+78h]
0x1400053b8  mov     rcx, rbx; Resource
0x1400053bb  call    cs:__imp_ExDeleteResourceLite
0x1400053c2  nop     dword ptr [rax+rax+00h]
0x1400053c7  mov     edx, 72454656h; Tag
0x1400053cc  mov     rcx, rbx; P
0x1400053cf  call    cs:__imp_ExFreePoolWithTag
0x1400053d6  nop     dword ptr [rax+rax+00h]
0x1400053db  lea     rcx, [rdi+70h]; RunRef
0x1400053df  call    cs:__imp_ExRundownCompleted
0x1400053e6  nop     dword ptr [rax+rax+00h]
0x1400053eb  mov     rbx, [rsp+28h+arg_0]
0x1400053f0  add     rsp, 20h
0x1400053f4  pop     rdi
0x1400053f5  retn
```
