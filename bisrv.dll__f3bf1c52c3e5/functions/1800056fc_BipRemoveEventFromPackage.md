# BipRemoveEventFromPackage

- ea: `0x1800056fc`
- end: `0x1800058ab`
- name: `BipRemoveEventFromPackage`
- size: `431`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005df20`
- `0x1800603d0`

## callees

- `0x1800056fc`
- `0x1800058b4`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x180005781`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180005781`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000587e`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000587e`
- `ntdll!RtlLookupEntryHashTable` at `0x1800057e7`
- `ntdll!RtlLookupEntryHashTable` at `0x1800057e7`
- `ntdll!RtlCompareUnicodeStrings` at `0x180005831`
- `ntdll!RtlCompareUnicodeStrings` at `0x180005831`
- `ntdll!RtlEqualSid` at `0x180005812`
- `ntdll!RtlEqualSid` at `0x180005812`
- `ntdll!RtlLengthSid` at `0x18000579e`
- `ntdll!RtlLengthSid` at `0x18000579e`

## pseudocode

```c
__int64 __fastcall BipRemoveEventFromPackage(_QWORD *a1)
{
  unsigned __int8 *v1; // r12
  _WORD *v2; // rsi
  __int64 v4; // rcx
  _WORD *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // ebx
  WCHAR *v8; // r14
  __int64 v9; // r15
  unsigned int i; // ebp
  WCHAR v11; // ax
  ULONG v12; // eax
  unsigned __int64 v13; // r8
  unsigned __int8 *v14; // rdx
  ULONG j; // r9d
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 result; // rax
  __int64 v19; // rbx
  _QWORD *v20; // rdx
  _QWORD *v21; // rcx
  __int64 v22; // rax
  _QWORD *v23; // rdx
  int v24; // [rsp+20h] [rbp-78h]
  __int128 v25; // [rsp+30h] [rbp-68h] BYREF
  __int64 v26; // [rsp+40h] [rbp-58h]

  v1 = (unsigned __int8 *)a1[21];
  v2 = a1 + 56;
  v26 = 0;
  v25 = 0;
  if ( a1 == (_QWORD *)-448LL )
    goto LABEL_23;
  v4 = 65;
  v5 = v2;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  if ( !v4 )
LABEL_23:
    LODWORD(v6) = 0;
  else
    v6 = (2 * (65 - v4)) & ((unsigned __int128)-(__int128)(unsigned __int64)v4 >> 64);
  v7 = (unsigned int)v6 >> 1;
  v8 = v2;
  v9 = qword_1800C4148;
  for ( i = 0; i < v7; ++i )
  {
    v11 = RtlUpcaseUnicodeChar(*v8++);
    v9 = v11 + 39 * v9;
  }
  v12 = RtlLengthSid(v1);
  v13 = qword_1800C4148;
  v14 = v1;
  for ( j = 0; j < v12; v13 = v16 + 39 * v13 )
  {
    v16 = *v14;
    ++j;
    ++v14;
  }
  v17 = (v9 ^ v13) + 1;
  if ( v13 != v9 )
    v17 = v9 ^ v13;
  for ( result = RtlLookupEntryHashTable(qword_1800C4380, v17, &v25);
        ;
        result = RtlGetNextEntryHashTable(qword_1800C4380, &v25) )
  {
    v19 = result;
    if ( !result )
      break;
    if ( RtlEqualSid(*(PSID *)(result + 24), v1) )
    {
      LOBYTE(v24) = 1;
      if ( !(unsigned int)RtlCompareUnicodeStrings(v19 + 416, 65, v2, 65, v24) )
      {
        v20 = *(_QWORD **)(v19 + 80);
        v21 = a1 + 11;
        while ( v20 != (_QWORD *)(v19 + 80) )
        {
          if ( (_QWORD *)v20[2] == v21 )
            v20[2] = a1[12];
          v20 = (_QWORD *)*v20;
        }
        v22 = *v21;
        if ( *(_QWORD **)(*v21 + 8LL) != v21 || (v23 = (_QWORD *)a1[12], (_QWORD *)*v23 != v21) )
          __fastfail(3u);
        *v23 = v22;
        *(_QWORD *)(v22 + 8) = v23;
        a1[15] = 0;
        return BipConditionallyDeletePackage(v19);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800056fc  push    rbx
0x1800056fe  push    rbp
0x1800056ff  push    rsi
0x180005700  push    rdi
0x180005701  push    r12
0x180005703  push    r13
0x180005705  push    r14
0x180005707  push    r15
0x180005709  sub     rsp, 58h
0x18000570d  mov     r12, [rcx+0A8h]
0x180005714  lea     rsi, [rcx+1C0h]
0x18000571b  xor     eax, eax
0x18000571d  xor     r13d, r13d
0x180005720  mov     [rsp+98h+var_58], rax
0x180005725  xorps   xmm0, xmm0
0x180005728  mov     rdi, rcx
0x18000572b  movups  [rsp+98h+var_68], xmm0
0x180005730  lea     edx, [rax+41h]
0x180005733  test    rsi, rsi
0x180005736  jz      loc_180005889
0x18000573c  mov     ecx, edx
0x18000573e  mov     rax, rsi
0x180005741  cmp     [rax], r13w
0x180005745  jz      short loc_180005751
0x180005747  add     rax, 2
0x18000574b  sub     rcx, 1
0x18000574f  jnz     short loc_180005741
0x180005751  test    rcx, rcx
0x180005754  jz      loc_180005889
0x18000575a  mov     rax, rdx
0x18000575d  sub     rax, rcx
0x180005760  add     rax, rax
0x180005763  neg     rcx
0x180005766  sbb     rbx, rbx
0x180005769  and     rbx, rax
0x18000576c  shr     ebx, 1
0x18000576e  mov     r14, rsi
0x180005771  mov     r15, cs:qword_1800C4148
0x180005778  mov     ebp, r13d
0x18000577b  jz      short loc_18000579B
0x18000577d  movzx   ecx, word ptr [r14]; Source
0x180005781  call    cs:__imp_RtlUpcaseUnicodeChar
0x180005787  imul    r15, 27h ; '''
0x18000578b  movzx   ecx, ax
0x18000578e  lea     r14, [r14+2]
0x180005792  add     r15, rcx
0x180005795  inc     ebp
0x180005797  cmp     ebp, ebx
0x180005799  jb      short loc_18000577D
0x18000579b  mov     rcx, r12; Sid
0x18000579e  call    cs:__imp_RtlLengthSid
0x1800057a4  mov     r8, cs:qword_1800C4148
0x1800057ab  mov     rdx, r12
0x1800057ae  mov     r9d, r13d
0x1800057b1  test    eax, eax
0x1800057b3  jz      short loc_1800057CA
0x1800057b5  movzx   ecx, byte ptr [rdx]
0x1800057b8  inc     r9d
0x1800057bb  imul    r8, 27h ; '''
0x1800057bf  inc     rdx
0x1800057c2  add     r8, rcx
0x1800057c5  cmp     r9d, eax
0x1800057c8  jb      short loc_1800057B5
0x1800057ca  mov     rcx, cs:qword_1800C4380
0x1800057d1  mov     rax, r8
0x1800057d4  xor     rax, r15
0x1800057d7  cmp     r8, r15
0x1800057da  lea     r8, [rsp+98h+var_68]
0x1800057df  lea     rdx, [rax+1]
0x1800057e3  cmovnz  rdx, rax
0x1800057e7  call    cs:__imp_RtlLookupEntryHashTable
0x1800057ed  mov     ebp, 41h ; 'A'
0x1800057f2  mov     rbx, rax
0x1800057f5  test    rax, rax
0x1800057f8  jnz     short loc_18000580B
0x1800057fa  add     rsp, 58h
0x1800057fe  pop     r15
0x180005800  pop     r14
0x180005802  pop     r13
0x180005804  pop     r12
0x180005806  pop     rdi
0x180005807  pop     rsi
0x180005808  pop     rbp
0x180005809  pop     rbx
0x18000580a  retn
0x18000580b  mov     rcx, [rbx+18h]; Sid1
0x18000580f  mov     rdx, r12; Sid2
0x180005812  call    cs:__imp_RtlEqualSid
0x180005818  test    al, al
0x18000581a  jz      short loc_180005872
0x18000581c  lea     rcx, [rbx+1A0h]
0x180005823  mov     byte ptr [rsp+98h+var_78], 1
0x180005828  mov     r9, rbp
0x18000582b  mov     r8, rsi
0x18000582e  mov     rdx, rbp
0x180005831  call    cs:__imp_RtlCompareUnicodeStrings
0x180005837  test    eax, eax
0x180005839  jnz     short loc_180005872
0x18000583b  lea     r8, [rbx+50h]
0x18000583f  mov     rdx, [r8]
0x180005842  lea     rcx, [rdi+58h]
0x180005846  cmp     rdx, r8
0x180005849  jnz     short loc_180005891
0x18000584b  mov     rax, [rcx]
0x18000584e  cmp     [rax+8], rcx
0x180005852  jnz     short loc_1800058A4
0x180005854  mov     rdx, [rcx+8]
0x180005858  cmp     [rdx], rcx
0x18000585b  jnz     short loc_1800058A4
0x18000585d  mov     [rdx], rax
0x180005860  mov     rcx, rbx
0x180005863  mov     [rax+8], rdx
0x180005867  mov     [rdi+78h], r13
0x18000586b  call    BipConditionallyDeletePackage
0x180005870  jmp     short loc_1800057FA
0x180005872  mov     rcx, cs:qword_1800C4380
0x180005879  lea     rdx, [rsp+98h+var_68]
0x18000587e  call    cs:__imp_RtlGetNextEntryHashTable
0x180005884  jmp     loc_1800057F2
0x180005889  mov     rbx, r13
0x18000588c  jmp     loc_18000576C
0x180005891  cmp     [rdx+10h], rcx
0x180005895  jnz     short loc_18000589F
0x180005897  mov     rax, [rdi+60h]
0x18000589b  mov     [rdx+10h], rax
0x18000589f  mov     rdx, [rdx]
0x1800058a2  jmp     short loc_180005846
0x1800058a4  mov     ecx, 3
0x1800058a9  int     29h; Win8: RtlFailFast(ecx)
```
