# BipAddEventToPackage

- ea: `0x18002bcb8`
- end: `0x18002beaf`
- name: `BipAddEventToPackage`
- size: `503`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005df20`
- `0x18005f8f0`

## callees

- `0x18002bcb8`
- `0x18002beb8`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x18002bd40`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002bd40`
- `ntdll!RtlGetNextEntryHashTable` at `0x18002be9d`
- `ntdll!RtlGetNextEntryHashTable` at `0x18002be9d`
- `ntdll!RtlLookupEntryHashTable` at `0x18002bda6`
- `ntdll!RtlLookupEntryHashTable` at `0x18002bda6`
- `ntdll!RtlCompareUnicodeStrings` at `0x18002be83`
- `ntdll!RtlCompareUnicodeStrings` at `0x18002be83`
- `ntdll!RtlEqualSid` at `0x18002be64`
- `ntdll!RtlEqualSid` at `0x18002be64`
- `ntdll!RtlLengthSid` at `0x18002bd5d`
- `ntdll!RtlLengthSid` at `0x18002bd5d`

## pseudocode

```c
__int64 __fastcall BipAddEventToPackage(_QWORD *a1)
{
  unsigned __int8 *v1; // r14
  _WORD *v2; // r15
  __int64 v4; // rcx
  _WORD *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // ebx
  WCHAR *v8; // rsi
  __int64 v9; // r12
  unsigned int i; // ebp
  WCHAR v11; // ax
  ULONG v12; // eax
  unsigned __int64 v13; // r8
  ULONG v14; // r9d
  unsigned __int8 *j; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 k; // rax
  __int64 v19; // rbx
  __int64 result; // rax
  __int64 *m; // rax
  __int64 *n; // rcx
  __int64 v23; // rbx
  _QWORD *v24; // rcx
  int v25; // [rsp+20h] [rbp-78h]
  __int128 v26; // [rsp+30h] [rbp-68h] BYREF
  __int64 v27; // [rsp+40h] [rbp-58h]
  __int64 v28; // [rsp+A0h] [rbp+8h] BYREF

  v1 = (unsigned __int8 *)a1[21];
  v2 = a1 + 56;
  v28 = 0;
  v26 = 0;
  v27 = 0;
  if ( a1 == (_QWORD *)-448LL )
    goto LABEL_29;
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
LABEL_29:
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
  v14 = 0;
  for ( j = v1; v14 < v12; v13 = v16 + 39 * v13 )
  {
    v16 = *j;
    ++v14;
    ++j;
  }
  v17 = (v9 ^ v13) + 1;
  if ( v13 != v9 )
    v17 = v9 ^ v13;
  for ( k = RtlLookupEntryHashTable(qword_1800C4380, v17, &v26); ; k = RtlGetNextEntryHashTable(qword_1800C4380, &v26) )
  {
    v19 = k;
    if ( !k )
      break;
    if ( RtlEqualSid(*(PSID *)(k + 24), v1) )
    {
      LOBYTE(v25) = 1;
      if ( !(unsigned int)RtlCompareUnicodeStrings(v19 + 416, 65, v2, 65, v25) )
        goto LABEL_17;
    }
  }
  result = BipCreatePackageAndPackageInstance(&v28, 0, a1 + 24, v1, -1);
  if ( (int)result < 0 )
    return result;
  v19 = v28;
LABEL_17:
  for ( m = *(__int64 **)(v19 + 96); m != (__int64 *)(v19 + 96); m = (__int64 *)*m )
  {
    if ( (*((_BYTE *)m + 44) & 1) != 0 )
      return 3221225558LL;
    for ( n = (__int64 *)m[3]; n != m + 3; n = (__int64 *)*n )
    {
      if ( (n[6] & 1) != 0 )
        return 3221225558LL;
    }
  }
  a1[15] = v19;
  v23 = v19 + 64;
  v24 = *(_QWORD **)(v23 + 8);
  if ( *v24 != v23 )
    __fastfail(3u);
  a1[11] = v23;
  a1[12] = v24;
  *v24 = a1 + 11;
  *(_QWORD *)(v23 + 8) = a1 + 11;
  return 0;
}

```

## disassembly

```asm
0x18002bcb8  mov     r11, rsp
0x18002bcbb  push    rbx
0x18002bcbc  push    rbp
0x18002bcbd  push    rsi
0x18002bcbe  push    rdi
0x18002bcbf  push    r12
0x18002bcc1  push    r13
0x18002bcc3  push    r14
0x18002bcc5  push    r15
0x18002bcc7  sub     rsp, 58h
0x18002bccb  mov     r14, [rcx+0A8h]
0x18002bcd2  lea     r15, [rcx+1C0h]
0x18002bcd9  xor     edx, edx
0x18002bcdb  xor     eax, eax
0x18002bcdd  mov     [r11+8], rdx
0x18002bce1  xorps   xmm0, xmm0
0x18002bce4  mov     rdi, rcx
0x18002bce7  movups  [rsp+98h+var_68], xmm0
0x18002bcec  mov     [r11-58h], rax
0x18002bcf0  lea     r8d, [rdx+41h]
0x18002bcf4  test    r15, r15
0x18002bcf7  jz      loc_18002BE55
0x18002bcfd  mov     ecx, r8d
0x18002bd00  mov     rax, r15
0x18002bd03  cmp     [rax], dx
0x18002bd06  jz      short loc_18002BD12
0x18002bd08  add     rax, 2
0x18002bd0c  sub     rcx, 1
0x18002bd10  jnz     short loc_18002BD03
0x18002bd12  test    rcx, rcx
0x18002bd15  jz      loc_18002BE55
0x18002bd1b  mov     rax, r8
0x18002bd1e  sub     rax, rcx
0x18002bd21  add     rax, rax
0x18002bd24  neg     rcx
0x18002bd27  sbb     rbx, rbx
0x18002bd2a  and     rbx, rax
0x18002bd2d  shr     ebx, 1
0x18002bd2f  mov     rsi, r15
0x18002bd32  mov     r12, cs:qword_1800C4148
0x18002bd39  mov     ebp, edx
0x18002bd3b  jz      short loc_18002BD5A
0x18002bd3d  movzx   ecx, word ptr [rsi]; Source
0x18002bd40  call    cs:__imp_RtlUpcaseUnicodeChar
0x18002bd46  imul    r12, 27h ; '''
0x18002bd4a  movzx   ecx, ax
0x18002bd4d  lea     rsi, [rsi+2]
0x18002bd51  add     r12, rcx
0x18002bd54  inc     ebp
0x18002bd56  cmp     ebp, ebx
0x18002bd58  jb      short loc_18002BD3D
0x18002bd5a  mov     rcx, r14; Sid
0x18002bd5d  call    cs:__imp_RtlLengthSid
0x18002bd63  mov     r8, cs:qword_1800C4148
0x18002bd6a  xor     r9d, r9d
0x18002bd6d  mov     rdx, r14
0x18002bd70  test    eax, eax
0x18002bd72  jz      short loc_18002BD89
0x18002bd74  movzx   ecx, byte ptr [rdx]
0x18002bd77  inc     r9d
0x18002bd7a  imul    r8, 27h ; '''
0x18002bd7e  inc     rdx
0x18002bd81  add     r8, rcx
0x18002bd84  cmp     r9d, eax
0x18002bd87  jb      short loc_18002BD74
0x18002bd89  mov     rcx, cs:qword_1800C4380
0x18002bd90  mov     rax, r8
0x18002bd93  xor     rax, r12
0x18002bd96  cmp     r8, r12
0x18002bd99  lea     r8, [rsp+98h+var_68]
0x18002bd9e  lea     rdx, [rax+1]
0x18002bda2  cmovnz  rdx, rax
0x18002bda6  call    cs:__imp_RtlLookupEntryHashTable
0x18002bdac  mov     esi, 41h ; 'A'
0x18002bdb1  mov     rbx, rax
0x18002bdb4  test    rax, rax
0x18002bdb7  jnz     loc_18002BE5D
0x18002bdbd  mov     r9, r14
0x18002bdc0  mov     [rsp+98h+var_78], 0FFFFFFFFh
0x18002bdc8  lea     r8, [rdi+0C0h]
0x18002bdcf  xor     edx, edx
0x18002bdd1  lea     rcx, [rsp+98h+arg_0]
0x18002bdd9  call    BipCreatePackageAndPackageInstance
0x18002bdde  test    eax, eax
0x18002bde0  js      short loc_18002BE13
0x18002bde2  mov     rbx, [rsp+98h+arg_0]
0x18002bdea  lea     rdx, [rbx+60h]
0x18002bdee  mov     rax, [rdx]
0x18002bdf1  cmp     rax, rdx
0x18002bdf4  jz      short loc_18002BE2E
0x18002bdf6  test    byte ptr [rax+2Ch], 1
0x18002bdfa  jnz     short loc_18002BE0E
0x18002bdfc  lea     r8, [rax+18h]
0x18002be00  mov     rcx, [r8]
0x18002be03  cmp     rcx, r8
0x18002be06  jz      short loc_18002BE29
0x18002be08  test    byte ptr [rcx+30h], 1
0x18002be0c  jz      short loc_18002BE24
0x18002be0e  mov     eax, 0C0000056h
0x18002be13  add     rsp, 58h
0x18002be17  pop     r15
0x18002be19  pop     r14
0x18002be1b  pop     r13
0x18002be1d  pop     r12
0x18002be1f  pop     rdi
0x18002be20  pop     rsi
0x18002be21  pop     rbp
0x18002be22  pop     rbx
0x18002be23  retn
0x18002be24  mov     rcx, [rcx]
0x18002be27  jmp     short loc_18002BE03
0x18002be29  mov     rax, [rax]
0x18002be2c  jmp     short loc_18002BDF1
0x18002be2e  mov     [rdi+78h], rbx
0x18002be32  add     rbx, 40h ; '@'
0x18002be36  mov     rcx, [rbx+8]
0x18002be3a  cmp     [rcx], rbx
0x18002be3d  jnz     short loc_18002BEA8
0x18002be3f  lea     rax, [rdi+58h]
0x18002be43  mov     [rax], rbx
0x18002be46  mov     [rax+8], rcx
0x18002be4a  mov     [rcx], rax
0x18002be4d  mov     [rbx+8], rax
0x18002be51  xor     eax, eax
0x18002be53  jmp     short loc_18002BE13
0x18002be55  mov     rbx, rdx
0x18002be58  jmp     loc_18002BD2D
0x18002be5d  mov     rcx, [rbx+18h]; Sid1
0x18002be61  mov     rdx, r14; Sid2
0x18002be64  call    cs:__imp_RtlEqualSid
0x18002be6a  test    al, al
0x18002be6c  jz      short loc_18002BE91
0x18002be6e  lea     rcx, [rbx+1A0h]
0x18002be75  mov     byte ptr [rsp+98h+var_78], 1
0x18002be7a  mov     r9, rsi
0x18002be7d  mov     r8, r15
0x18002be80  mov     rdx, rsi
0x18002be83  call    cs:__imp_RtlCompareUnicodeStrings
0x18002be89  test    eax, eax
0x18002be8b  jz      loc_18002BDEA
0x18002be91  mov     rcx, cs:qword_1800C4380
0x18002be98  lea     rdx, [rsp+98h+var_68]
0x18002be9d  call    cs:__imp_RtlGetNextEntryHashTable
0x18002bea3  jmp     loc_18002BDB1
0x18002bea8  mov     ecx, 3
0x18002bead  int     29h; Win8: RtlFailFast(ecx)
```
