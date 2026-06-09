# BaseSrvCloseStandardHandles

- ea: `0x180009114`
- end: `0x1800091d5`
- name: `BaseSrvCloseStandardHandles`
- size: `193`
- prototype: `int __fastcall(HANDLE SourceProcessHandle, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008644`
- `0x18000c088`

## callees

- `0x180009114`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x18000914e`
- `ntdll!NtDuplicateObject` at `0x18000917e`
- `ntdll!NtDuplicateObject` at `0x1800091ae`
- `ntdll!NtDuplicateObject` at `0x18000914e`
- `ntdll!NtDuplicateObject` at `0x18000917e`
- `ntdll!NtDuplicateObject` at `0x1800091ae`

## pseudocode

```c
int __fastcall BaseSrvCloseStandardHandles(HANDLE SourceProcessHandle, __int64 a2)
{
  _UNKNOWN **v2; // rax
  _QWORD *v3; // rbx
  void *v5; // rdx
  void *v6; // rdx
  void *v7; // rdx
  _UNKNOWN *retaddr; // [rsp+48h] [rbp+0h] BYREF

  v2 = &retaddr;
  v3 = *(_QWORD **)(a2 + 32);
  if ( v3 )
  {
    v5 = (void *)v3[2];
    if ( v5 )
      LODWORD(v2) = NtDuplicateObject(SourceProcessHandle, v5, 0, 0, 0, 0, 1u);
    v6 = (void *)v3[3];
    if ( v6 )
      LODWORD(v2) = NtDuplicateObject(SourceProcessHandle, v6, 0, 0, 0, 0, 1u);
    v7 = (void *)v3[4];
    if ( v7 )
      LODWORD(v2) = NtDuplicateObject(SourceProcessHandle, v7, 0, 0, 0, 0, 1u);
    v3[2] = 0;
    v3[3] = 0;
    v3[4] = 0;
  }
  return (int)v2;
}

```

## disassembly

```asm
0x180009114  mov     rax, rsp
0x180009117  mov     [rax+8], rbx
0x18000911b  push    rdi
0x18000911c  sub     rsp, 40h
0x180009120  mov     rbx, [rdx+20h]
0x180009124  mov     rdi, rcx
0x180009127  test    rbx, rbx
0x18000912a  jz      loc_1800091C9
0x180009130  mov     rdx, [rbx+10h]; SourceHandle
0x180009134  test    rdx, rdx
0x180009137  jz      short loc_18000915A
0x180009139  mov     dword ptr [rax-18h], 1
0x180009140  xor     r9d, r9d; TargetHandle
0x180009143  and     dword ptr [rax-20h], 0
0x180009147  xor     r8d, r8d; TargetProcessHandle
0x18000914a  and     dword ptr [rax-28h], 0
0x18000914e  call    cs:__imp_NtDuplicateObject
0x180009155  nop     dword ptr [rax+rax+00h]
0x18000915a  mov     rdx, [rbx+18h]; SourceHandle
0x18000915e  test    rdx, rdx
0x180009161  jz      short loc_18000918A
0x180009163  mov     [rsp+48h+Options], 1; Options
0x18000916b  xor     r9d, r9d; TargetHandle
0x18000916e  and     [rsp+48h+var_20], 0
0x180009173  xor     r8d, r8d; TargetProcessHandle
0x180009176  and     [rsp+48h+var_28], 0
0x18000917b  mov     rcx, rdi; SourceProcessHandle
0x18000917e  call    cs:__imp_NtDuplicateObject
0x180009185  nop     dword ptr [rax+rax+00h]
0x18000918a  mov     rdx, [rbx+20h]; SourceHandle
0x18000918e  test    rdx, rdx
0x180009191  jz      short loc_1800091BA
0x180009193  mov     [rsp+48h+Options], 1; Options
0x18000919b  xor     r9d, r9d; TargetHandle
0x18000919e  and     [rsp+48h+var_20], 0
0x1800091a3  xor     r8d, r8d; TargetProcessHandle
0x1800091a6  and     [rsp+48h+var_28], 0
0x1800091ab  mov     rcx, rdi; SourceProcessHandle
0x1800091ae  call    cs:__imp_NtDuplicateObject
0x1800091b5  nop     dword ptr [rax+rax+00h]
0x1800091ba  and     qword ptr [rbx+10h], 0
0x1800091bf  and     qword ptr [rbx+18h], 0
0x1800091c4  and     qword ptr [rbx+20h], 0
0x1800091c9  mov     rbx, [rsp+48h+arg_0]
0x1800091ce  add     rsp, 40h
0x1800091d2  pop     rdi
0x1800091d3  retn
```
