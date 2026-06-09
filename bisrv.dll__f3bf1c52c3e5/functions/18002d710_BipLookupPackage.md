# BipLookupPackage

- ea: `0x18002d710`
- end: `0x18002d888`
- name: `BipLookupPackage`
- size: `376`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d5e0`
- `0x18004fc90`
- `0x180055c70`
- `0x180057614`
- `0x180076fe0`
- `0x1800770a8`
- `0x1800777a4`
- `0x18007ee14`
- `0x18007f010`
- `0x18007f170`

## callees

- `0x18002d710`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x18002d793`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002d793`
- `ntdll!RtlGetNextEntryHashTable` at `0x18002d864`
- `ntdll!RtlGetNextEntryHashTable` at `0x18002d864`
- `ntdll!RtlLookupEntryHashTable` at `0x18002d803`
- `ntdll!RtlLookupEntryHashTable` at `0x18002d803`
- `ntdll!RtlCompareUnicodeStrings` at `0x18002d84e`
- `ntdll!RtlCompareUnicodeStrings` at `0x18002d84e`
- `ntdll!RtlEqualSid` at `0x18002d82c`
- `ntdll!RtlEqualSid` at `0x18002d82c`
- `ntdll!RtlLengthSid` at `0x18002d7b0`
- `ntdll!RtlLengthSid` at `0x18002d7b0`

## pseudocode

```c
__int64 __fastcall BipLookupPackage(__int64 *a1, __int64 a2, unsigned __int8 *a3)
{
  _WORD *v3; // r14
  __int64 v6; // rdx
  _WORD *v7; // rax
  unsigned int v8; // esi
  unsigned int v9; // esi
  WCHAR *v10; // rbx
  __int64 v11; // rbp
  unsigned int i; // edi
  WCHAR v13; // ax
  ULONG v14; // eax
  ULONG v15; // r8d
  unsigned __int8 *v16; // rdx
  ULONG v17; // r9d
  unsigned __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 j; // rax
  __int64 v22; // rbx
  int v24; // [rsp+20h] [rbp-68h]
  __int128 v25; // [rsp+30h] [rbp-58h] BYREF
  __int64 v26; // [rsp+40h] [rbp-48h]

  v3 = (_WORD *)(a2 + 256);
  v26 = 0;
  v25 = 0;
  if ( a2 == -256 )
    goto LABEL_21;
  v6 = 65;
  v7 = v3;
  while ( *v7 )
  {
    ++v7;
    if ( !--v6 )
    {
      v8 = 0;
      goto LABEL_7;
    }
  }
  v8 = 2 * (65 - v6);
LABEL_7:
  if ( !v6 )
LABEL_21:
    v8 = 0;
  v9 = v8 >> 1;
  v10 = v3;
  v11 = qword_1800C4148;
  for ( i = 0; i < v9; ++i )
  {
    v13 = RtlUpcaseUnicodeChar(*v10++);
    v11 = v13 + 39 * v11;
  }
  v14 = RtlLengthSid(a3);
  v15 = 0;
  v16 = a3;
  v17 = v14;
  v18 = qword_1800C4148;
  if ( v17 )
  {
    do
    {
      v19 = *v16++;
      ++v15;
      v18 = v19 + 39 * v18;
    }
    while ( v15 < v17 );
  }
  v20 = (v11 ^ v18) + 1;
  if ( v18 != v11 )
    v20 = v11 ^ v18;
  for ( j = RtlLookupEntryHashTable(qword_1800C4380, v20, &v25); ; j = RtlGetNextEntryHashTable(qword_1800C4380, &v25) )
  {
    v22 = j;
    if ( !j )
      return 3221226021LL;
    if ( RtlEqualSid(*(PSID *)(j + 24), a3) )
    {
      LOBYTE(v24) = 1;
      if ( !(unsigned int)RtlCompareUnicodeStrings(v22 + 416, 65, v3, 65, v24) )
        break;
    }
  }
  *a1 = v22;
  return 0;
}

```

## disassembly

```asm
0x18002d710  push    rbx
0x18002d712  push    rbp
0x18002d713  push    rsi
0x18002d714  push    rdi
0x18002d715  push    r12
0x18002d717  push    r14
0x18002d719  push    r15
0x18002d71b  sub     rsp, 50h
0x18002d71f  xor     eax, eax
0x18002d721  lea     r14, [rdx+100h]
0x18002d728  mov     [rsp+88h+var_48], rax
0x18002d72d  xorps   xmm0, xmm0
0x18002d730  mov     r15, r8
0x18002d733  mov     r12, rcx
0x18002d736  movups  [rsp+88h+var_58], xmm0
0x18002d73b  test    r14, r14
0x18002d73e  jz      loc_18002D881
0x18002d744  mov     edx, 41h ; 'A'
0x18002d749  mov     rax, r14
0x18002d74c  nop     dword ptr [rax+00h]
0x18002d750  cmp     word ptr [rax], 0
0x18002d754  jz      short loc_18002D764
0x18002d756  add     rax, 2
0x18002d75a  sub     rdx, 1
0x18002d75e  jnz     short loc_18002D750
0x18002d760  xor     esi, esi
0x18002d762  jmp     short loc_18002D76F
0x18002d764  mov     esi, 41h ; 'A'
0x18002d769  sub     rsi, rdx
0x18002d76c  add     rsi, rsi
0x18002d76f  test    rdx, rdx
0x18002d772  jz      loc_18002D881
0x18002d778  shr     esi, 1
0x18002d77a  mov     rbx, r14
0x18002d77d  mov     rbp, cs:qword_1800C4148
0x18002d784  mov     edi, 0
0x18002d789  jz      short loc_18002D7AD
0x18002d78b  nop     dword ptr [rax+rax+00h]
0x18002d790  movzx   ecx, word ptr [rbx]; Source
0x18002d793  call    cs:__imp_RtlUpcaseUnicodeChar
0x18002d799  imul    rbp, 27h ; '''
0x18002d79d  movzx   ecx, ax
0x18002d7a0  lea     rbx, [rbx+2]
0x18002d7a4  add     rbp, rcx
0x18002d7a7  inc     edi
0x18002d7a9  cmp     edi, esi
0x18002d7ab  jb      short loc_18002D790
0x18002d7ad  mov     rcx, r15; Sid
0x18002d7b0  call    cs:__imp_RtlLengthSid
0x18002d7b6  xor     r8d, r8d
0x18002d7b9  mov     rdx, r15
0x18002d7bc  mov     r9d, eax
0x18002d7bf  mov     rax, cs:qword_1800C4148
0x18002d7c6  test    r9d, r9d
0x18002d7c9  jz      short loc_18002D7E6
0x18002d7cb  nop     dword ptr [rax+rax+00h]
0x18002d7d0  movzx   ecx, byte ptr [rdx]
0x18002d7d3  lea     rdx, [rdx+1]
0x18002d7d7  imul    rax, 27h ; '''
0x18002d7db  inc     r8d
0x18002d7de  add     rax, rcx
0x18002d7e1  cmp     r8d, r9d
0x18002d7e4  jb      short loc_18002D7D0
0x18002d7e6  mov     rcx, rax
0x18002d7e9  lea     r8, [rsp+88h+var_58]
0x18002d7ee  xor     rcx, rbp
0x18002d7f1  cmp     rax, rbp
0x18002d7f4  lea     rdx, [rcx+1]
0x18002d7f8  cmovnz  rdx, rcx
0x18002d7fc  mov     rcx, cs:qword_1800C4380
0x18002d803  call    cs:__imp_RtlLookupEntryHashTable
0x18002d809  mov     rbx, rax
0x18002d80c  test    rax, rax
0x18002d80f  jnz     short loc_18002D825
0x18002d811  mov     eax, 0C0000225h
0x18002d816  add     rsp, 50h
0x18002d81a  pop     r15
0x18002d81c  pop     r14
0x18002d81e  pop     r12
0x18002d820  pop     rdi
0x18002d821  pop     rsi
0x18002d822  pop     rbp
0x18002d823  pop     rbx
0x18002d824  retn
0x18002d825  mov     rcx, [rbx+18h]; Sid1
0x18002d829  mov     rdx, r15; Sid2
0x18002d82c  call    cs:__imp_RtlEqualSid
0x18002d832  test    al, al
0x18002d834  jz      short loc_18002D858
0x18002d836  mov     r9d, 41h ; 'A'
0x18002d83c  mov     byte ptr [rsp+88h+var_68], 1
0x18002d841  mov     edx, r9d
0x18002d844  lea     rcx, [rbx+1A0h]
0x18002d84b  mov     r8, r14
0x18002d84e  call    cs:__imp_RtlCompareUnicodeStrings
0x18002d854  test    eax, eax
0x18002d856  jz      short loc_18002D86C
0x18002d858  mov     rcx, cs:qword_1800C4380
0x18002d85f  lea     rdx, [rsp+88h+var_58]
0x18002d864  call    cs:__imp_RtlGetNextEntryHashTable
0x18002d86a  jmp     short loc_18002D809
0x18002d86c  mov     [r12], rbx
0x18002d870  xor     eax, eax
0x18002d872  add     rsp, 50h
0x18002d876  pop     r15
0x18002d878  pop     r14
0x18002d87a  pop     r12
0x18002d87c  pop     rdi
0x18002d87d  pop     rsi
0x18002d87e  pop     rbp
0x18002d87f  pop     rbx
0x18002d880  retn
0x18002d881  xor     esi, esi
0x18002d883  jmp     loc_18002D778
```
