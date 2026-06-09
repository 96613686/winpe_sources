# SeSddlSecurityDescriptorFromSDDL

- ea: `0x14000d52c`
- end: `0x14000d5e8`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d2a0`

## callees

- `0x1400027c0`
- `0x140002ac0`
- `0x14000d52c`
- `0x14000dd04`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5ce`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d571`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d571`

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
0x14000d52c  push    rbx
0x14000d52e  push    rbp
0x14000d52f  push    rsi
0x14000d530  push    rdi
0x14000d531  push    r14
0x14000d533  sub     rsp, 20h
0x14000d537  movzx   edx, word ptr [rcx]
0x14000d53a  xor     ebp, ebp
0x14000d53c  movzx   eax, word ptr [rcx+2]
0x14000d540  mov     rsi, r8
0x14000d543  mov     rdi, rcx
0x14000d546  lea     r9, [rdx+2]
0x14000d54a  cmp     rax, r9
0x14000d54d  jnz     short loc_14000D563
0x14000d54f  mov     rcx, [rcx+8]
0x14000d553  shr     rdx, 1
0x14000d556  cmp     [rcx+rdx*2], bp
0x14000d55a  jnz     short loc_14000D563
0x14000d55c  call    SepSddlSecurityDescriptorFromSDDLString
0x14000d561  jmp     short loc_14000D5DC
0x14000d563  mov     r8d, 73546553h; Tag
0x14000d569  mov     rdx, r9; NumberOfBytes
0x14000d56c  mov     ecx, 1; PoolType
0x14000d571  call    cs:__imp_ExAllocatePoolWithTag
0x14000d578  nop     dword ptr [rax+rax+00h]
0x14000d57d  mov     r14, rax
0x14000d580  test    rax, rax
0x14000d583  jnz     short loc_14000D58F
0x14000d585  mov     [rsi], rbp
0x14000d588  mov     eax, 0C000009Ah
0x14000d58d  jmp     short loc_14000D5DC
0x14000d58f  movzx   r8d, word ptr [rdi]
0x14000d593  xor     edx, edx; Val
0x14000d595  add     r8, 2; Size
0x14000d599  mov     rcx, r14; void *
0x14000d59c  call    memset
0x14000d5a1  movzx   r8d, word ptr [rdi]; Size
0x14000d5a5  mov     rcx, r14; void *
0x14000d5a8  mov     rdx, [rdi+8]; Src
0x14000d5ac  call    memmove
0x14000d5b1  movzx   ecx, word ptr [rdi]
0x14000d5b4  mov     r8, rsi
0x14000d5b7  shr     rcx, 1
0x14000d5ba  mov     [r14+rcx*2], bp
0x14000d5bf  mov     rcx, r14
0x14000d5c2  call    SepSddlSecurityDescriptorFromSDDLString
0x14000d5c7  xor     edx, edx; Tag
0x14000d5c9  mov     rcx, r14; P
0x14000d5cc  mov     ebx, eax
0x14000d5ce  call    cs:__imp_ExFreePoolWithTag
0x14000d5d5  nop     dword ptr [rax+rax+00h]
0x14000d5da  mov     eax, ebx
0x14000d5dc  add     rsp, 20h
0x14000d5e0  pop     r14
0x14000d5e2  pop     rdi
0x14000d5e3  pop     rsi
0x14000d5e4  pop     rbp
0x14000d5e5  pop     rbx
0x14000d5e6  retn
```
