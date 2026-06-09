# SeSddlSecurityDescriptorFromSDDL

- ea: `0x140024a1c`
- end: `0x140024ad8`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140024790`

## callees

- `0x140013d00`
- `0x140014000`
- `0x140024a1c`
- `0x140025204`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024a61`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024a61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024abe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024abe`

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
0x140024a1c  push    rbx
0x140024a1e  push    rbp
0x140024a1f  push    rsi
0x140024a20  push    rdi
0x140024a21  push    r14
0x140024a23  sub     rsp, 20h
0x140024a27  movzx   edx, word ptr [rcx]
0x140024a2a  xor     ebp, ebp
0x140024a2c  movzx   eax, word ptr [rcx+2]
0x140024a30  mov     rsi, r8
0x140024a33  mov     rdi, rcx
0x140024a36  lea     r9, [rdx+2]
0x140024a3a  cmp     rax, r9
0x140024a3d  jnz     short loc_140024A53
0x140024a3f  mov     rcx, [rcx+8]
0x140024a43  shr     rdx, 1
0x140024a46  cmp     [rcx+rdx*2], bp
0x140024a4a  jnz     short loc_140024A53
0x140024a4c  call    SepSddlSecurityDescriptorFromSDDLString
0x140024a51  jmp     short loc_140024ACC
0x140024a53  mov     r8d, 73546553h; Tag
0x140024a59  mov     rdx, r9; NumberOfBytes
0x140024a5c  mov     ecx, 1; PoolType
0x140024a61  call    cs:__imp_ExAllocatePoolWithTag
0x140024a68  nop     dword ptr [rax+rax+00h]
0x140024a6d  mov     r14, rax
0x140024a70  test    rax, rax
0x140024a73  jnz     short loc_140024A7F
0x140024a75  mov     [rsi], rbp
0x140024a78  mov     eax, 0C000009Ah
0x140024a7d  jmp     short loc_140024ACC
0x140024a7f  movzx   r8d, word ptr [rdi]
0x140024a83  xor     edx, edx; Val
0x140024a85  add     r8, 2; Size
0x140024a89  mov     rcx, r14; void *
0x140024a8c  call    memset
0x140024a91  movzx   r8d, word ptr [rdi]; Size
0x140024a95  mov     rcx, r14; void *
0x140024a98  mov     rdx, [rdi+8]; Src
0x140024a9c  call    memmove
0x140024aa1  movzx   ecx, word ptr [rdi]
0x140024aa4  mov     r8, rsi
0x140024aa7  shr     rcx, 1
0x140024aaa  mov     [r14+rcx*2], bp
0x140024aaf  mov     rcx, r14
0x140024ab2  call    SepSddlSecurityDescriptorFromSDDLString
0x140024ab7  xor     edx, edx; Tag
0x140024ab9  mov     rcx, r14; P
0x140024abc  mov     ebx, eax
0x140024abe  call    cs:__imp_ExFreePoolWithTag
0x140024ac5  nop     dword ptr [rax+rax+00h]
0x140024aca  mov     eax, ebx
0x140024acc  add     rsp, 20h
0x140024ad0  pop     r14
0x140024ad2  pop     rdi
0x140024ad3  pop     rsi
0x140024ad4  pop     rbp
0x140024ad5  pop     rbx
0x140024ad6  retn
```
