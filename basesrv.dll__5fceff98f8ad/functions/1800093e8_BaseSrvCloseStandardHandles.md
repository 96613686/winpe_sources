# BaseSrvCloseStandardHandles

- ea: `0x1800093e8`
- end: `0x1800094c4`
- name: `BaseSrvCloseStandardHandles`
- size: `220`
- prototype: `__int64 __fastcall(HANDLE SourceProcessHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008938`
- `0x18000c434`

## callees

- `0x1800093e8`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x180009428`
- `ntdll!NtDuplicateObject` at `0x18000945e`
- `ntdll!NtDuplicateObject` at `0x180009494`
- `ntdll!NtDuplicateObject` at `0x180009428`
- `ntdll!NtDuplicateObject` at `0x18000945e`
- `ntdll!NtDuplicateObject` at `0x180009494`

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
0x1800093e8  mov     rax, rsp
0x1800093eb  mov     [rax+8], rbx
0x1800093ef  push    rdi
0x1800093f0  sub     rsp, 40h
0x1800093f4  mov     rbx, [rdx+20h]
0x1800093f8  mov     rdi, rcx
0x1800093fb  test    rbx, rbx
0x1800093fe  jz      loc_1800094B8
0x180009404  mov     rdx, [rbx+10h]; SourceHandle
0x180009408  test    rdx, rdx
0x18000940b  jz      short loc_180009434
0x18000940d  mov     dword ptr [rax-18h], 1
0x180009414  xor     r9d, r9d; TargetHandle
0x180009417  mov     dword ptr [rax-20h], 0
0x18000941e  xor     r8d, r8d; TargetProcessHandle
0x180009421  mov     dword ptr [rax-28h], 0
0x180009428  call    cs:__imp_NtDuplicateObject
0x18000942f  nop     dword ptr [rax+rax+00h]
0x180009434  mov     rdx, [rbx+18h]; SourceHandle
0x180009438  test    rdx, rdx
0x18000943b  jz      short loc_18000946A
0x18000943d  mov     [rsp+48h+Options], 1; Options
0x180009445  xor     r9d, r9d; TargetHandle
0x180009448  mov     [rsp+48h+HandleAttributes], 0; HandleAttributes
0x180009450  xor     r8d, r8d; TargetProcessHandle
0x180009453  mov     rcx, rdi; SourceProcessHandle
0x180009456  mov     [rsp+48h+DesiredAccess], 0; DesiredAccess
0x18000945e  call    cs:__imp_NtDuplicateObject
0x180009465  nop     dword ptr [rax+rax+00h]
0x18000946a  mov     rdx, [rbx+20h]; SourceHandle
0x18000946e  test    rdx, rdx
0x180009471  jz      short loc_1800094A0
0x180009473  mov     [rsp+48h+Options], 1; Options
0x18000947b  xor     r9d, r9d; TargetHandle
0x18000947e  mov     [rsp+48h+HandleAttributes], 0; HandleAttributes
0x180009486  xor     r8d, r8d; TargetProcessHandle
0x180009489  mov     rcx, rdi; SourceProcessHandle
0x18000948c  mov     [rsp+48h+DesiredAccess], 0; DesiredAccess
0x180009494  call    cs:__imp_NtDuplicateObject
0x18000949b  nop     dword ptr [rax+rax+00h]
0x1800094a0  mov     qword ptr [rbx+10h], 0
0x1800094a8  mov     qword ptr [rbx+18h], 0
0x1800094b0  mov     qword ptr [rbx+20h], 0
0x1800094b8  mov     rbx, [rsp+48h+arg_0]
0x1800094bd  add     rsp, 40h
0x1800094c1  pop     rdi
0x1800094c2  retn
```
