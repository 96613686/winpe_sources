# BipLookupOrCreatePackage

- ea: `0x18002b95c`
- end: `0x18002ba52`
- name: `BipLookupOrCreatePackage`
- size: `246`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180076edc`
- `0x180077994`

## callees

- `0x18002b95c`
- `0x18002beb8`
- `0x18002c0b0`

## import_xrefs

- `ntdll!RtlGetNextEntryHashTable` at `0x18002ba43`
- `ntdll!RtlGetNextEntryHashTable` at `0x18002ba43`
- `ntdll!RtlLookupEntryHashTable` at `0x18002b9d2`
- `ntdll!RtlLookupEntryHashTable` at `0x18002b9d2`
- `ntdll!RtlCompareUnicodeStrings` at `0x18002ba2d`
- `ntdll!RtlCompareUnicodeStrings` at `0x18002ba2d`
- `ntdll!RtlEqualSid` at `0x18002ba08`
- `ntdll!RtlEqualSid` at `0x18002ba08`
- `ntdll!RtlLengthSid` at `0x18002b98b`
- `ntdll!RtlLengthSid` at `0x18002b98b`

## pseudocode

```c
__int64 __fastcall BipLookupOrCreatePackage(__int64 *a1, __int64 a2, unsigned __int8 *a3)
{
  __int64 v6; // rbx
  ULONG v7; // eax
  unsigned __int64 v8; // r8
  ULONG v9; // edx
  unsigned __int8 *i; // r9
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 j; // rax
  __int64 v14; // rbx
  int v16; // [rsp+20h] [rbp-58h]
  __int128 v17; // [rsp+30h] [rbp-48h] BYREF
  __int64 v18; // [rsp+40h] [rbp-38h]

  v17 = 0;
  v18 = 0;
  v6 = BipPackageIdToHashSignature(a2);
  v7 = RtlLengthSid(a3);
  v8 = qword_1800C4148;
  v9 = 0;
  for ( i = a3; v9 < v7; v8 = v11 + 39 * v8 )
  {
    v11 = *i;
    ++v9;
    ++i;
  }
  v12 = (v6 ^ v8) + 1;
  if ( v8 != v6 )
    v12 = v6 ^ v8;
  for ( j = RtlLookupEntryHashTable(qword_1800C4380, v12, &v17); ; j = RtlGetNextEntryHashTable(qword_1800C4380, &v17) )
  {
    v14 = j;
    if ( !j )
      return BipCreatePackageAndPackageInstance(a1, 0, a2, a3, -1);
    if ( RtlEqualSid(*(PSID *)(j + 24), a3) )
    {
      LOBYTE(v16) = 1;
      if ( !(unsigned int)RtlCompareUnicodeStrings(v14 + 416, 65, a2 + 256, 65, v16) )
        break;
    }
  }
  *a1 = v14;
  return 0;
}

```

## disassembly

```asm
0x18002b95c  push    rbx
0x18002b95e  push    rbp
0x18002b95f  push    rsi
0x18002b960  push    rdi
0x18002b961  sub     rsp, 58h
0x18002b965  mov     rsi, rcx
0x18002b968  xorps   xmm0, xmm0
0x18002b96b  xor     eax, eax
0x18002b96d  mov     rcx, rdx
0x18002b970  movups  [rsp+78h+var_48], xmm0
0x18002b975  mov     [rsp+78h+var_38], rax
0x18002b97a  mov     rdi, r8
0x18002b97d  mov     rbp, rdx
0x18002b980  call    BipPackageIdToHashSignature
0x18002b985  mov     rcx, rdi; Sid
0x18002b988  mov     rbx, rax
0x18002b98b  call    cs:__imp_RtlLengthSid
0x18002b991  mov     r8, cs:qword_1800C4148
0x18002b998  xor     edx, edx
0x18002b99a  mov     r9, rdi
0x18002b99d  test    eax, eax
0x18002b99f  jz      short loc_18002B9B5
0x18002b9a1  movzx   ecx, byte ptr [r9]
0x18002b9a5  inc     edx
0x18002b9a7  imul    r8, 27h ; '''
0x18002b9ab  inc     r9
0x18002b9ae  add     r8, rcx
0x18002b9b1  cmp     edx, eax
0x18002b9b3  jb      short loc_18002B9A1
0x18002b9b5  mov     rcx, cs:qword_1800C4380
0x18002b9bc  mov     rax, r8
0x18002b9bf  xor     rax, rbx
0x18002b9c2  cmp     r8, rbx
0x18002b9c5  lea     r8, [rsp+78h+var_48]
0x18002b9ca  lea     rdx, [rax+1]
0x18002b9ce  cmovnz  rdx, rax
0x18002b9d2  call    cs:__imp_RtlLookupEntryHashTable
0x18002b9d8  mov     rbx, rax
0x18002b9db  test    rax, rax
0x18002b9de  jnz     short loc_18002BA01
0x18002b9e0  mov     r9, rdi
0x18002b9e3  mov     [rsp+78h+var_58], 0FFFFFFFFh
0x18002b9eb  mov     r8, rbp
0x18002b9ee  xor     edx, edx
0x18002b9f0  mov     rcx, rsi
0x18002b9f3  call    BipCreatePackageAndPackageInstance
0x18002b9f8  add     rsp, 58h
0x18002b9fc  pop     rdi
0x18002b9fd  pop     rsi
0x18002b9fe  pop     rbp
0x18002b9ff  pop     rbx
0x18002ba00  retn
0x18002ba01  mov     rcx, [rbx+18h]; Sid1
0x18002ba05  mov     rdx, rdi; Sid2
0x18002ba08  call    cs:__imp_RtlEqualSid
0x18002ba0e  test    al, al
0x18002ba10  jz      short loc_18002BA37
0x18002ba12  mov     edx, 41h ; 'A'
0x18002ba17  mov     byte ptr [rsp+78h+var_58], 1
0x18002ba1c  mov     r9d, edx
0x18002ba1f  lea     r8, [rbp+100h]
0x18002ba26  lea     rcx, [rbx+1A0h]
0x18002ba2d  call    cs:__imp_RtlCompareUnicodeStrings
0x18002ba33  test    eax, eax
0x18002ba35  jz      short loc_18002BA4B
0x18002ba37  mov     rcx, cs:qword_1800C4380
0x18002ba3e  lea     rdx, [rsp+78h+var_48]
0x18002ba43  call    cs:__imp_RtlGetNextEntryHashTable
0x18002ba49  jmp     short loc_18002B9D8
0x18002ba4b  mov     [rsi], rbx
0x18002ba4e  xor     eax, eax
0x18002ba50  jmp     short loc_18002B9F8
```
