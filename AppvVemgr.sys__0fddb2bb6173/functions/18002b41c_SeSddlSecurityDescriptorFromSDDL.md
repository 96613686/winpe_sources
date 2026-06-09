# SeSddlSecurityDescriptorFromSDDL

- ea: `0x18002b41c`
- end: `0x18002b4d8`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002b190`

## callees

- `0x18001bc00`
- `0x18001bf00`
- `0x18002b41c`
- `0x18002bc04`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18002b4be`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002b4be`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18002b461`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18002b461`

## pseudocode

```c
__int64 __fastcall SeSddlSecurityDescriptorFromSDDL(unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  unsigned __int64 v3; // rdx
  SIZE_T v6; // r9
  _WORD *v7; // rcx
  unsigned __int64 v8; // rdx
  _WORD *PoolWithTag; // rax
  _WORD *v11; // r14
  ULONG v12; // edx
  unsigned int v13; // ebx

  v3 = *a1;
  v6 = v3 + 2;
  if ( a1[1] == v3 + 2 )
  {
    v7 = (_WORD *)*((_QWORD *)a1 + 1);
    v8 = v3 >> 1;
    if ( !v7[v8] )
      return SepSddlSecurityDescriptorFromSDDLString(v7, v8, (__int64)a3);
  }
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, v6, 0x73546553u);
  v11 = PoolWithTag;
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, *a1 + 2LL);
    memmove(v11, *((const void **)a1 + 1), *a1);
    v11[(unsigned __int64)*a1 >> 1] = 0;
    v13 = SepSddlSecurityDescriptorFromSDDLString(v11, v12, (__int64)a3);
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
0x18002b41c  push    rbx
0x18002b41e  push    rbp
0x18002b41f  push    rsi
0x18002b420  push    rdi
0x18002b421  push    r14
0x18002b423  sub     rsp, 20h
0x18002b427  movzx   edx, word ptr [rcx]
0x18002b42a  xor     ebp, ebp
0x18002b42c  movzx   eax, word ptr [rcx+2]
0x18002b430  mov     rsi, r8
0x18002b433  mov     rdi, rcx
0x18002b436  lea     r9, [rdx+2]
0x18002b43a  cmp     rax, r9
0x18002b43d  jnz     short loc_18002B453
0x18002b43f  mov     rcx, [rcx+8]
0x18002b443  shr     rdx, 1
0x18002b446  cmp     [rcx+rdx*2], bp
0x18002b44a  jnz     short loc_18002B453
0x18002b44c  call    SepSddlSecurityDescriptorFromSDDLString
0x18002b451  jmp     short loc_18002B4CC
0x18002b453  mov     r8d, 73546553h; Tag
0x18002b459  mov     rdx, r9; NumberOfBytes
0x18002b45c  mov     ecx, 1; PoolType
0x18002b461  call    cs:__imp_ExAllocatePoolWithTag
0x18002b468  nop     dword ptr [rax+rax+00h]
0x18002b46d  mov     r14, rax
0x18002b470  test    rax, rax
0x18002b473  jnz     short loc_18002B47F
0x18002b475  mov     [rsi], rbp
0x18002b478  mov     eax, 0C000009Ah
0x18002b47d  jmp     short loc_18002B4CC
0x18002b47f  movzx   r8d, word ptr [rdi]
0x18002b483  xor     edx, edx; Val
0x18002b485  add     r8, 2; Size
0x18002b489  mov     rcx, r14; void *
0x18002b48c  call    memset
0x18002b491  movzx   r8d, word ptr [rdi]; Size
0x18002b495  mov     rcx, r14; void *
0x18002b498  mov     rdx, [rdi+8]; Src
0x18002b49c  call    memmove
0x18002b4a1  movzx   ecx, word ptr [rdi]
0x18002b4a4  mov     r8, rsi
0x18002b4a7  shr     rcx, 1
0x18002b4aa  mov     [r14+rcx*2], bp
0x18002b4af  mov     rcx, r14
0x18002b4b2  call    SepSddlSecurityDescriptorFromSDDLString
0x18002b4b7  xor     edx, edx; Tag
0x18002b4b9  mov     rcx, r14; P
0x18002b4bc  mov     ebx, eax
0x18002b4be  call    cs:__imp_ExFreePoolWithTag
0x18002b4c5  nop     dword ptr [rax+rax+00h]
0x18002b4ca  mov     eax, ebx
0x18002b4cc  add     rsp, 20h
0x18002b4d0  pop     r14
0x18002b4d2  pop     rdi
0x18002b4d3  pop     rsi
0x18002b4d4  pop     rbp
0x18002b4d5  pop     rbx
0x18002b4d6  retn
```
