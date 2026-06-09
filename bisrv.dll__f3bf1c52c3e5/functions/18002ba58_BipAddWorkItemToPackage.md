# BipAddWorkItemToPackage

- ea: `0x18002ba58`
- end: `0x18002bcb1`
- name: `BipAddWorkItemToPackage`
- size: `601`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008598`

## callees

- `0x18002ba58`
- `0x18002beb8`
- `0x18006d364`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x18002bb1e`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002bb1e`
- `ntdll!RtlGetNextEntryHashTable` at `0x18002bc8b`
- `ntdll!RtlGetNextEntryHashTable` at `0x18002bc8b`
- `ntdll!RtlLookupEntryHashTable` at `0x18002bb84`
- `ntdll!RtlLookupEntryHashTable` at `0x18002bb84`
- `ntdll!RtlCompareUnicodeStrings` at `0x18002bc71`
- `ntdll!RtlCompareUnicodeStrings` at `0x18002bc71`
- `ntdll!RtlEqualSid` at `0x18002bc52`
- `ntdll!RtlEqualSid` at `0x18002bc52`
- `ntdll!RtlLengthSid` at `0x18002bb3b`
- `ntdll!RtlLengthSid` at `0x18002bb3b`

## pseudocode

```c
__int64 __fastcall BipAddWorkItemToPackage(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdx
  int v5; // ecx
  __int64 v6; // rcx
  __int64 v7; // rax
  unsigned __int8 *v8; // r12
  WCHAR *v9; // r14
  __int64 v10; // rcx
  _WORD *v11; // rax
  __int64 v12; // rbx
  unsigned int v13; // ebx
  WCHAR *v14; // rsi
  __int64 v15; // r15
  unsigned int i; // ebp
  WCHAR v17; // ax
  ULONG v18; // eax
  unsigned __int64 v19; // r8
  unsigned __int8 *v20; // rdx
  ULONG j; // r9d
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 k; // rax
  __int64 v25; // rbx
  __int64 result; // rax
  __int64 *n; // rcx
  __int64 *v28; // r8
  __int64 v29; // rdx
  __int64 *m; // rax
  __int64 v31; // rbx
  _QWORD *v32; // rcx
  int v33; // [rsp+20h] [rbp-78h]
  __int128 v34; // [rsp+30h] [rbp-68h] BYREF
  __int64 v35; // [rsp+40h] [rbp-58h]
  __int64 v36; // [rsp+A0h] [rbp+8h] BYREF

  v3 = *(unsigned int *)(a1 + 400);
  v36 = 0;
  if ( (_DWORD)v3 )
  {
    v3 = (unsigned int)(v3 - 1);
    if ( (_DWORD)v3 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(a1, v3, a3);
  }
  v5 = *(_DWORD *)(a1 + 400);
  if ( v5 )
  {
    v6 = (unsigned int)(v5 - 1);
    if ( (_DWORD)v6 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v6, v3, a3);
  }
  v7 = *(_QWORD *)(a1 + 72);
  v35 = 0;
  v34 = 0;
  v8 = *(unsigned __int8 **)(v7 + 168);
  v9 = (WCHAR *)(v7 + 448);
  if ( v7 == -448 )
    goto LABEL_34;
  v10 = 65;
  v11 = (_WORD *)(v7 + 448);
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  if ( !v10 )
LABEL_34:
    LODWORD(v12) = 0;
  else
    v12 = (2 * (65 - v10)) & ((unsigned __int128)-(__int128)(unsigned __int64)v10 >> 64);
  v13 = (unsigned int)v12 >> 1;
  v14 = v9;
  v15 = qword_1800C4148;
  for ( i = 0; i < v13; ++i )
  {
    v17 = RtlUpcaseUnicodeChar(*v14++);
    v15 = v17 + 39 * v15;
  }
  v18 = RtlLengthSid(v8);
  v19 = qword_1800C4148;
  v20 = v8;
  for ( j = 0; j < v18; v19 = v22 + 39 * v19 )
  {
    v22 = *v20;
    ++j;
    ++v20;
  }
  v23 = (v15 ^ v19) + 1;
  if ( v19 != v15 )
    v23 = v15 ^ v19;
  for ( k = RtlLookupEntryHashTable(qword_1800C4380, v23, &v34); ; k = RtlGetNextEntryHashTable(qword_1800C4380, &v34) )
  {
    v25 = k;
    if ( !k )
      break;
    if ( RtlEqualSid(*(PSID *)(k + 24), v8) )
    {
      LOBYTE(v33) = 1;
      if ( !(unsigned int)RtlCompareUnicodeStrings(v25 + 416, 65, v9, 65, v33) )
        goto LABEL_23;
    }
  }
  result = BipCreatePackageAndPackageInstance(
             &v36,
             0,
             *(_QWORD *)(a1 + 72) + 192LL,
             *(_QWORD *)(*(_QWORD *)(a1 + 72) + 168LL),
             -1);
  if ( (int)result < 0 )
    return result;
  v25 = v36;
LABEL_23:
  v29 = v25 + 96;
  for ( m = *(__int64 **)(v25 + 96); m != (__int64 *)v29; m = (__int64 *)*m )
  {
    if ( (*((_BYTE *)m + 44) & 1) != 0 )
    {
LABEL_29:
      MicrosoftTelemetryAssertTriggeredNoArgs(n, v29, v28);
      break;
    }
    v28 = m + 3;
    for ( n = (__int64 *)m[3]; n != v28; n = (__int64 *)*n )
    {
      if ( (n[6] & 1) != 0 )
        goto LABEL_29;
    }
  }
  *(_QWORD *)(a1 + 80) = v25;
  v31 = v25 + 32;
  v32 = *(_QWORD **)(v31 + 8);
  if ( *v32 != v31 )
    __fastfail(3u);
  *(_QWORD *)(a1 + 160) = v31;
  *(_QWORD *)(a1 + 168) = v32;
  *v32 = a1 + 160;
  *(_QWORD *)(v31 + 8) = a1 + 160;
  return 0;
}

```

## disassembly

```asm
0x18002ba58  mov     rax, rsp
0x18002ba5b  push    rbx
0x18002ba5c  push    rbp
0x18002ba5d  push    rsi
0x18002ba5e  push    rdi
0x18002ba5f  push    r12
0x18002ba61  push    r13
0x18002ba63  push    r14
0x18002ba65  push    r15
0x18002ba67  sub     rsp, 58h
0x18002ba6b  mov     edx, [rcx+190h]
0x18002ba71  xor     r13d, r13d
0x18002ba74  mov     [rax+8], r13
0x18002ba78  mov     rdi, rcx
0x18002ba7b  test    edx, edx
0x18002ba7d  jz      short loc_18002BA91
0x18002ba7f  sub     edx, 1
0x18002ba82  jz      loc_18002BC96
0x18002ba88  cmp     edx, 1
0x18002ba8b  jnz     loc_18002BC96
0x18002ba91  mov     ecx, [rdi+190h]
0x18002ba97  test    ecx, ecx
0x18002ba99  jz      short loc_18002BAAD
0x18002ba9b  sub     ecx, 1
0x18002ba9e  jz      loc_18002BCA0
0x18002baa4  cmp     ecx, 1
0x18002baa7  jnz     loc_18002BCA0
0x18002baad  mov     rax, [rdi+48h]
0x18002bab1  xor     ecx, ecx
0x18002bab3  xorps   xmm0, xmm0
0x18002bab6  mov     [rsp+98h+var_58], rcx
0x18002babb  movups  [rsp+98h+var_68], xmm0
0x18002bac0  mov     r12, [rax+0A8h]
0x18002bac7  lea     r14, [rax+1C0h]
0x18002bace  lea     edx, [rcx+41h]
0x18002bad1  test    r14, r14
0x18002bad4  jz      loc_18002BC43
0x18002bada  mov     ecx, edx
0x18002badc  mov     rax, r14
0x18002badf  cmp     [rax], r13w
0x18002bae3  jz      short loc_18002BAEF
0x18002bae5  add     rax, 2
0x18002bae9  sub     rcx, 1
0x18002baed  jnz     short loc_18002BADF
0x18002baef  test    rcx, rcx
0x18002baf2  jz      loc_18002BC43
0x18002baf8  mov     rax, rdx
0x18002bafb  sub     rax, rcx
0x18002bafe  add     rax, rax
0x18002bb01  neg     rcx
0x18002bb04  sbb     rbx, rbx
0x18002bb07  and     rbx, rax
0x18002bb0a  shr     ebx, 1
0x18002bb0c  mov     rsi, r14
0x18002bb0f  mov     r15, cs:qword_1800C4148
0x18002bb16  mov     ebp, r13d
0x18002bb19  jz      short loc_18002BB38
0x18002bb1b  movzx   ecx, word ptr [rsi]; Source
0x18002bb1e  call    cs:__imp_RtlUpcaseUnicodeChar
0x18002bb24  imul    r15, 27h ; '''
0x18002bb28  movzx   ecx, ax
0x18002bb2b  lea     rsi, [rsi+2]
0x18002bb2f  add     r15, rcx
0x18002bb32  inc     ebp
0x18002bb34  cmp     ebp, ebx
0x18002bb36  jb      short loc_18002BB1B
0x18002bb38  mov     rcx, r12; Sid
0x18002bb3b  call    cs:__imp_RtlLengthSid
0x18002bb41  mov     r8, cs:qword_1800C4148
0x18002bb48  mov     rdx, r12
0x18002bb4b  mov     r9d, r13d
0x18002bb4e  test    eax, eax
0x18002bb50  jz      short loc_18002BB67
0x18002bb52  movzx   ecx, byte ptr [rdx]
0x18002bb55  inc     r9d
0x18002bb58  imul    r8, 27h ; '''
0x18002bb5c  inc     rdx
0x18002bb5f  add     r8, rcx
0x18002bb62  cmp     r9d, eax
0x18002bb65  jb      short loc_18002BB52
0x18002bb67  mov     rcx, cs:qword_1800C4380
0x18002bb6e  mov     rax, r8
0x18002bb71  xor     rax, r15
0x18002bb74  cmp     r8, r15
0x18002bb77  lea     r8, [rsp+98h+var_68]
0x18002bb7c  lea     rdx, [rax+1]
0x18002bb80  cmovnz  rdx, rax
0x18002bb84  call    cs:__imp_RtlLookupEntryHashTable
0x18002bb8a  mov     esi, 41h ; 'A'
0x18002bb8f  mov     rbx, rax
0x18002bb92  test    rax, rax
0x18002bb95  jnz     loc_18002BC4B
0x18002bb9b  mov     r9, [rdi+48h]
0x18002bb9f  lea     rcx, [rsp+98h+arg_0]
0x18002bba7  xor     edx, edx
0x18002bba9  mov     [rsp+98h+var_78], 0FFFFFFFFh
0x18002bbb1  lea     r8, [r9+0C0h]
0x18002bbb8  mov     r9, [r9+0A8h]
0x18002bbbf  call    BipCreatePackageAndPackageInstance
0x18002bbc4  test    eax, eax
0x18002bbc6  jns     short loc_18002BBD9
0x18002bbc8  add     rsp, 58h
0x18002bbcc  pop     r15
0x18002bbce  pop     r14
0x18002bbd0  pop     r13
0x18002bbd2  pop     r12
0x18002bbd4  pop     rdi
0x18002bbd5  pop     rsi
0x18002bbd6  pop     rbp
0x18002bbd7  pop     rbx
0x18002bbd8  retn
0x18002bbd9  mov     rbx, [rsp+98h+arg_0]
0x18002bbe1  lea     rdx, [rbx+60h]
0x18002bbe5  mov     rax, [rdx]
0x18002bbe8  cmp     rax, rdx
0x18002bbeb  jz      short loc_18002BC0A
0x18002bbed  test    byte ptr [rax+2Ch], 1
0x18002bbf1  jnz     short loc_18002BC05
0x18002bbf3  lea     r8, [rax+18h]
0x18002bbf7  mov     rcx, [r8]
0x18002bbfa  cmp     rcx, r8
0x18002bbfd  jz      short loc_18002BC3E
0x18002bbff  test    byte ptr [rcx+30h], 1
0x18002bc03  jz      short loc_18002BC39
0x18002bc05  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002bc0a  mov     [rdi+50h], rbx
0x18002bc0e  add     rbx, 20h ; ' '
0x18002bc12  mov     rcx, [rbx+8]
0x18002bc16  cmp     [rcx], rbx
0x18002bc19  jnz     loc_18002BCAA
0x18002bc1f  lea     rax, [rdi+0A0h]
0x18002bc26  mov     [rax], rbx
0x18002bc29  mov     [rax+8], rcx
0x18002bc2d  mov     [rcx], rax
0x18002bc30  mov     [rbx+8], rax
0x18002bc34  mov     eax, r13d
0x18002bc37  jmp     short loc_18002BBC8
0x18002bc39  mov     rcx, [rcx]
0x18002bc3c  jmp     short loc_18002BBFA
0x18002bc3e  mov     rax, [rax]
0x18002bc41  jmp     short loc_18002BBE8
0x18002bc43  mov     rbx, r13
0x18002bc46  jmp     loc_18002BB0A
0x18002bc4b  mov     rcx, [rbx+18h]; Sid1
0x18002bc4f  mov     rdx, r12; Sid2
0x18002bc52  call    cs:__imp_RtlEqualSid
0x18002bc58  test    al, al
0x18002bc5a  jz      short loc_18002BC7F
0x18002bc5c  lea     rcx, [rbx+1A0h]
0x18002bc63  mov     byte ptr [rsp+98h+var_78], 1
0x18002bc68  mov     r9, rsi
0x18002bc6b  mov     r8, r14
0x18002bc6e  mov     rdx, rsi
0x18002bc71  call    cs:__imp_RtlCompareUnicodeStrings
0x18002bc77  test    eax, eax
0x18002bc79  jz      loc_18002BBE1
0x18002bc7f  mov     rcx, cs:qword_1800C4380
0x18002bc86  lea     rdx, [rsp+98h+var_68]
0x18002bc8b  call    cs:__imp_RtlGetNextEntryHashTable
0x18002bc91  jmp     loc_18002BB8F
0x18002bc96  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002bc9b  jmp     loc_18002BA91
0x18002bca0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002bca5  jmp     loc_18002BAAD
0x18002bcaa  mov     ecx, 3
0x18002bcaf  int     29h; Win8: RtlFailFast(ecx)
```
