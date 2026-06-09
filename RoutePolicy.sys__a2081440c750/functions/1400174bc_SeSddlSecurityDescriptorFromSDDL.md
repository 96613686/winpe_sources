# SeSddlSecurityDescriptorFromSDDL

- ea: `0x1400174bc`
- end: `0x140017578`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140017230`

## callees

- `0x14000a780`
- `0x14000aa80`
- `0x1400174bc`
- `0x140017ca4`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017501`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017501`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001755e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001755e`

## pseudocode

```c
__int64 __fastcall SeSddlSecurityDescriptorFromSDDL(unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  unsigned __int64 v3; // rdx
  SIZE_T v6; // r9
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  PVOID PoolWithTag; // rax
  void *v11; // r14
  ULONG v12; // edx
  unsigned int v13; // ebx

  v3 = *a1;
  v6 = v3 + 2;
  if ( a1[1] == v3 + 2 )
  {
    v7 = *((_QWORD *)a1 + 1);
    v8 = v3 >> 1;
    if ( !*(_WORD *)(v7 + 2 * v8) )
      return SepSddlSecurityDescriptorFromSDDLString(v7, v8, (__int64)a3);
  }
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, v6, 0x73546553u);
  v11 = PoolWithTag;
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, *a1 + 2LL);
    memmove(v11, *((const void **)a1 + 1), *a1);
    *((_WORD *)v11 + ((unsigned __int64)*a1 >> 1)) = 0;
    v13 = SepSddlSecurityDescriptorFromSDDLString((__int64)v11, v12, (__int64)a3);
    ExFreePoolWithTag(v11, 0);
    return v13;
  }
  else
  {
    *a3 = 0;
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x1400174bc  push    rbx
0x1400174be  push    rbp
0x1400174bf  push    rsi
0x1400174c0  push    rdi
0x1400174c1  push    r14
0x1400174c3  sub     rsp, 20h
0x1400174c7  movzx   edx, word ptr [rcx]
0x1400174ca  xor     ebp, ebp
0x1400174cc  movzx   eax, word ptr [rcx+2]
0x1400174d0  mov     rsi, r8
0x1400174d3  mov     rdi, rcx
0x1400174d6  lea     r9, [rdx+2]
0x1400174da  cmp     rax, r9
0x1400174dd  jnz     short loc_1400174F3
0x1400174df  mov     rcx, [rcx+8]
0x1400174e3  shr     rdx, 1
0x1400174e6  cmp     [rcx+rdx*2], bp
0x1400174ea  jnz     short loc_1400174F3
0x1400174ec  call    SepSddlSecurityDescriptorFromSDDLString
0x1400174f1  jmp     short loc_14001756C
0x1400174f3  mov     r8d, 73546553h; Tag
0x1400174f9  mov     rdx, r9; NumberOfBytes
0x1400174fc  mov     ecx, 1; PoolType
0x140017501  call    cs:__imp_ExAllocatePoolWithTag
0x140017508  nop     dword ptr [rax+rax+00h]
0x14001750d  mov     r14, rax
0x140017510  test    rax, rax
0x140017513  jnz     short loc_14001751F
0x140017515  mov     [rsi], rbp
0x140017518  mov     eax, 0C000009Ah
0x14001751d  jmp     short loc_14001756C
0x14001751f  movzx   r8d, word ptr [rdi]
0x140017523  xor     edx, edx; Val
0x140017525  add     r8, 2; Size
0x140017529  mov     rcx, r14; void *
0x14001752c  call    memset
0x140017531  movzx   r8d, word ptr [rdi]; Size
0x140017535  mov     rcx, r14; void *
0x140017538  mov     rdx, [rdi+8]; Src
0x14001753c  call    memmove
0x140017541  movzx   ecx, word ptr [rdi]
0x140017544  mov     r8, rsi
0x140017547  shr     rcx, 1
0x14001754a  mov     [r14+rcx*2], bp
0x14001754f  mov     rcx, r14
0x140017552  call    SepSddlSecurityDescriptorFromSDDLString
0x140017557  xor     edx, edx; Tag
0x140017559  mov     rcx, r14; P
0x14001755c  mov     ebx, eax
0x14001755e  call    cs:__imp_ExFreePoolWithTag
0x140017565  nop     dword ptr [rax+rax+00h]
0x14001756a  mov     eax, ebx
0x14001756c  add     rsp, 20h
0x140017570  pop     r14
0x140017572  pop     rdi
0x140017573  pop     rsi
0x140017574  pop     rbp
0x140017575  pop     rbx
0x140017576  retn
```
