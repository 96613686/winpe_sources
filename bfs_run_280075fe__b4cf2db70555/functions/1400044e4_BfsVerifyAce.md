# BfsVerifyAce

- ea: `0x1400044e4`
- end: `0x14000459f`
- name: `BfsVerifyAce`
- size: `187`
- prototype: `__int64 __usercall@<rax>(PACL Acl@<rcx>, PSID Sid1, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000af40`
- `0x14000e560`
- `0x14001e1a0`

## callees

- `0x1400044e4`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x14000456b`
- `ntoskrnl!RtlEqualSid` at `0x14000456b`
- `ntoskrnl!RtlGetAce` at `0x14000452f`
- `ntoskrnl!RtlGetAce` at `0x14000452f`

## pseudocode

```c
__int64 __fastcall BfsVerifyAce(PACL Acl, char a2, char a3, int a4, PSID Sid1, _BYTE *a6)
{
  _BYTE *v6; // r14
  NTSTATUS v11; // esi
  ULONG v12; // edi
  char v13; // cl
  int v14; // ebx
  PVOID Ace; // [rsp+70h] [rbp+8h] BYREF

  v6 = a6;
  Ace = 0;
  v11 = -1073741275;
  v12 = 0;
  *a6 = 0;
  while ( v12 < Acl->AceCount )
  {
    v11 = RtlGetAce(Acl, v12, &Ace);
    if ( v11 < 0 )
      break;
    v13 = *(_BYTE *)Ace;
    if ( *(_BYTE *)Ace == a2 && *((_BYTE *)Ace + 1) == a3 && (!v13 || v13 == 17) )
    {
      v14 = *((_DWORD *)Ace + 1);
      if ( RtlEqualSid(Sid1, (char *)Ace + 8) )
      {
        if ( (a4 & v14) == a4 )
        {
          *v6 = 1;
          return (unsigned int)v11;
        }
      }
    }
    ++v12;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400044e4  push    rbx
0x1400044e6  push    rbp
0x1400044e7  push    rsi
0x1400044e8  push    rdi
0x1400044e9  push    r12
0x1400044eb  push    r13
0x1400044ed  push    r14
0x1400044ef  push    r15
0x1400044f1  sub     rsp, 28h
0x1400044f5  mov     r14, [rsp+68h+arg_28]
0x1400044fd  mov     r15d, r9d
0x140004500  mov     r12b, r8b
0x140004503  mov     [rsp+68h+Ace], 0
0x14000450c  mov     r13b, dl
0x14000450f  mov     rbp, rcx
0x140004512  mov     esi, 0C0000225h
0x140004517  xor     edi, edi
0x140004519  mov     byte ptr [r14], 0
0x14000451d  movzx   eax, word ptr [rbp+4]
0x140004521  cmp     edi, eax
0x140004523  jnb     short loc_14000458B
0x140004525  lea     r8, [rsp+68h+Ace]; Ace
0x14000452a  mov     edx, edi; AceIndex
0x14000452c  mov     rcx, rbp; Acl
0x14000452f  call    cs:__imp_RtlGetAce
0x140004536  nop     dword ptr [rax+rax+00h]
0x14000453b  mov     esi, eax
0x14000453d  test    eax, eax
0x14000453f  js      short loc_14000458B
0x140004541  mov     rdx, [rsp+68h+Ace]
0x140004546  mov     cl, [rdx]
0x140004548  cmp     cl, r13b
0x14000454b  jnz     short loc_140004583
0x14000454d  cmp     [rdx+1], r12b
0x140004551  jnz     short loc_140004583
0x140004553  test    cl, cl
0x140004555  jz      short loc_14000455C
0x140004557  cmp     cl, 11h
0x14000455a  jnz     short loc_140004583
0x14000455c  mov     ebx, [rdx+4]
0x14000455f  add     rdx, 8; Sid2
0x140004563  mov     rcx, [rsp+68h+Sid1]; Sid1
0x14000456b  call    cs:__imp_RtlEqualSid
0x140004572  nop     dword ptr [rax+rax+00h]
0x140004577  test    al, al
0x140004579  jz      short loc_140004583
0x14000457b  and     ebx, r15d
0x14000457e  cmp     ebx, r15d
0x140004581  jz      short loc_140004587
0x140004583  inc     edi
0x140004585  jmp     short loc_14000451D
0x140004587  mov     byte ptr [r14], 1
0x14000458b  mov     eax, esi
0x14000458d  add     rsp, 28h
0x140004591  pop     r15
0x140004593  pop     r14
0x140004595  pop     r13
0x140004597  pop     r12
0x140004599  pop     rdi
0x14000459a  pop     rsi
0x14000459b  pop     rbp
0x14000459c  pop     rbx
0x14000459d  retn
```
