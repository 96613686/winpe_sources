# SetEntriesInAclA

- ea: `0x18002a0d0`
- end: `0x18002a365`
- name: `SetEntriesInAclA`
- size: `661`
- prototype: `DWORD __stdcall(ULONG cCountOfExplicitEntries, PEXPLICIT_ACCESS_A pListOfExplicitEntries, PACL OldAcl, PACL *NewAcl)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002a0d0`
- `0x18002a4a0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18002a11c`
- `KERNELBASE!LocalAlloc` at `0x18002a11c`
- `KERNEL32!LocalFree` at `0x18002a1d5`
- `KERNEL32!LocalFree` at `0x18002a20d`
- `KERNEL32!LocalFree` at `0x18002a27c`
- `KERNEL32!LocalFree` at `0x18002a29c`
- `KERNEL32!LocalFree` at `0x18002a2c1`
- `KERNEL32!LocalFree` at `0x18002a1d5`
- `KERNEL32!LocalFree` at `0x18002a20d`
- `KERNEL32!LocalFree` at `0x18002a27c`
- `KERNEL32!LocalFree` at `0x18002a29c`
- `KERNEL32!LocalFree` at `0x18002a2c1`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002a190`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002a190`

## pseudocode

```c
DWORD __stdcall SetEntriesInAclA(
        ULONG cCountOfExplicitEntries,
        PEXPLICIT_ACCESS_A pListOfExplicitEntries,
        PACL OldAcl,
        PACL *NewAcl)
{
  _QWORD *v4; // rbx
  ACL *v7; // rsi
  __int64 i; // r14
  __int64 v10; // rbp
  unsigned int v11; // r12d
  ULONG v12; // r13d
  __int64 v13; // rsi
  HLOCAL *v15; // r14
  __int64 v16; // rbp
  bool v17; // zf
  LPCH ptstrName; // rsi
  CHAR *v19; // rcx
  CHAR *v20; // rcx
  unsigned __int16 *v21[11]; // [rsp+20h] [rbp-58h] BYREF

  v4 = 0;
  v21[0] = 0;
  v7 = OldAcl;
  if ( cCountOfExplicitEntries )
  {
    if ( 0xFFFFFFFF / cCountOfExplicitEntries < 0x18 )
      return 8;
    v4 = LocalAlloc(0x40u, 24LL * cCountOfExplicitEntries);
    if ( !v4 )
      return 8;
    for ( i = 0; (unsigned int)i < cCountOfExplicitEntries; i = (unsigned int)(i + 1) )
    {
      v10 = 3 * i;
      v4[v10] = 0;
      v4[v10 + 1] = 0;
      v4[v10 + 2] = 0;
      if ( pListOfExplicitEntries[i].Trustee.TrusteeForm == TRUSTEE_IS_NAME )
      {
        v11 = ConvertStringAToStringW(pListOfExplicitEntries[i].Trustee.ptstrName, v21);
        if ( v11 )
          goto LABEL_11;
        v4[3 * i] = pListOfExplicitEntries[i].Trustee.ptstrName;
        pListOfExplicitEntries[i].Trustee.ptstrName = (LPCH)v21[0];
      }
      else if ( pListOfExplicitEntries[i].Trustee.TrusteeForm == TRUSTEE_IS_OBJECTS_AND_NAME )
      {
        ptstrName = pListOfExplicitEntries[i].Trustee.ptstrName;
        v11 = ConvertStringAToStringW(*((CHAR **)ptstrName + 3), v21);
        if ( v11 )
          goto LABEL_11;
        v4[3 * i] = *((_QWORD *)ptstrName + 3);
        v19 = (CHAR *)*((_QWORD *)ptstrName + 1);
        *((unsigned __int16 **)ptstrName + 3) = v21[0];
        v11 = ConvertStringAToStringW(v19, v21);
        if ( v11 )
          goto LABEL_11;
        v4[3 * i + 1] = *((_QWORD *)ptstrName + 1);
        v20 = (CHAR *)*((_QWORD *)ptstrName + 2);
        *((unsigned __int16 **)ptstrName + 1) = v21[0];
        v11 = ConvertStringAToStringW(v20, v21);
        if ( v11 )
          goto LABEL_11;
        v4[3 * i + 2] = *((_QWORD *)ptstrName + 2);
        *((unsigned __int16 **)ptstrName + 2) = v21[0];
      }
    }
    v7 = OldAcl;
  }
  v11 = SetEntriesInAclW(cCountOfExplicitEntries, (PEXPLICIT_ACCESS_W)pListOfExplicitEntries, v7, NewAcl);
LABEL_11:
  v12 = 0;
  if ( cCountOfExplicitEntries )
  {
    v13 = 0;
    do
    {
      if ( pListOfExplicitEntries[v13].Trustee.TrusteeForm == TRUSTEE_IS_NAME )
      {
        if ( v4[3 * v13] )
        {
          LocalFree(pListOfExplicitEntries[v13].Trustee.ptstrName);
          pListOfExplicitEntries[v13].Trustee.ptstrName = (LPCH)v4[3 * v13];
        }
      }
      else if ( pListOfExplicitEntries[v13].Trustee.TrusteeForm == TRUSTEE_IS_OBJECTS_AND_NAME )
      {
        v15 = (HLOCAL *)pListOfExplicitEntries[v13].Trustee.ptstrName;
        v16 = 3 * v13;
        v17 = v4[3 * v13] == 0;
        v4[v16 + 1] = v15[1];
        v4[v16 + 2] = v15[2];
        if ( !v17 )
        {
          LocalFree(v15[3]);
          v15[3] = (HLOCAL)v4[3 * v13];
        }
        if ( v4[3 * v13 + 1] )
        {
          LocalFree(v15[1]);
          v15[1] = (HLOCAL)v4[3 * v13 + 1];
        }
        if ( v4[3 * v13 + 2] )
        {
          LocalFree(v15[2]);
          v15[2] = (HLOCAL)v4[3 * v13 + 1];
        }
      }
      ++v12;
      ++v13;
    }
    while ( v12 < cCountOfExplicitEntries );
  }
  if ( v4 )
    LocalFree(v4);
  return v11;
}

```

## disassembly

```asm
0x18002a0d0  mov     [rsp+arg_10], r8
0x18002a0d5  push    rbx
0x18002a0d6  push    rbp
0x18002a0d7  push    rsi
0x18002a0d8  push    rdi
0x18002a0d9  push    r12
0x18002a0db  push    r13
0x18002a0dd  push    r14
0x18002a0df  push    r15
0x18002a0e1  sub     rsp, 38h
0x18002a0e5  xor     ebx, ebx
0x18002a0e7  mov     r15d, ecx
0x18002a0ea  mov     [rsp+78h+var_58], rbx
0x18002a0ef  mov     r13, r9
0x18002a0f2  mov     rsi, r8
0x18002a0f5  mov     rdi, rdx
0x18002a0f8  test    ecx, ecx
0x18002a0fa  jz      loc_18002A184
0x18002a100  xor     edx, edx
0x18002a102  or      eax, 0FFFFFFFFh
0x18002a105  div     r15d
0x18002a108  cmp     eax, 18h
0x18002a10b  jb      loc_18002A1F6
0x18002a111  lea     rdx, [r15+r15*2]
0x18002a115  shl     rdx, 3; uBytes
0x18002a119  lea     ecx, [rbx+40h]; uFlags
0x18002a11c  call    cs:__imp_LocalAlloc
0x18002a123  nop     dword ptr [rax+rax+00h]
0x18002a128  mov     rbx, rax
0x18002a12b  test    rax, rax
0x18002a12e  jz      loc_18002A1F6
0x18002a134  xor     r14d, r14d
0x18002a137  cmp     r14d, r15d
0x18002a13a  jnb     short loc_18002A17C
0x18002a13c  lea     rbp, [r14+r14*2]
0x18002a140  lea     rsi, [r14+r14*2]
0x18002a144  mov     qword ptr [rbx+rbp*8], 0
0x18002a14c  add     rsi, rsi
0x18002a14f  mov     qword ptr [rbx+rbp*8+8], 0
0x18002a158  mov     qword ptr [rbx+rbp*8+10h], 0
0x18002a161  mov     ecx, [rdi+rsi*8+1Ch]
0x18002a165  sub     ecx, 1
0x18002a168  jz      loc_18002A224
0x18002a16e  cmp     ecx, 3
0x18002a171  jz      loc_18002A2DB
0x18002a177  inc     r14d
0x18002a17a  jmp     short loc_18002A137
0x18002a17c  mov     rsi, [rsp+78h+arg_10]
0x18002a184  mov     r9, r13; NewAcl
0x18002a187  mov     r8, rsi; OldAcl
0x18002a18a  mov     rdx, rdi; pListOfExplicitEntries
0x18002a18d  mov     ecx, r15d; cCountOfExplicitEntries
0x18002a190  call    cs:__imp_SetEntriesInAclW
0x18002a197  nop     dword ptr [rax+rax+00h]
0x18002a19c  mov     r12d, eax
0x18002a19f  xor     r13d, r13d
0x18002a1a2  test    r15d, r15d
0x18002a1a5  jz      short loc_18002A1CD
0x18002a1a7  xor     esi, esi
0x18002a1a9  lea     rbp, [rsi+rsi*2]
0x18002a1ad  add     rbp, rbp
0x18002a1b0  mov     ecx, [rdi+rbp*8+1Ch]
0x18002a1b4  sub     ecx, 1
0x18002a1b7  jz      short loc_18002A1FD
0x18002a1b9  cmp     ecx, 3
0x18002a1bc  jz      loc_18002A256
0x18002a1c2  inc     r13d
0x18002a1c5  inc     rsi
0x18002a1c8  cmp     r13d, r15d
0x18002a1cb  jb      short loc_18002A1A9
0x18002a1cd  test    rbx, rbx
0x18002a1d0  jz      short loc_18002A1E1
0x18002a1d2  mov     rcx, rbx; hMem
0x18002a1d5  call    cs:__imp_LocalFree
0x18002a1dc  nop     dword ptr [rax+rax+00h]
0x18002a1e1  mov     eax, r12d
0x18002a1e4  add     rsp, 38h
0x18002a1e8  pop     r15
0x18002a1ea  pop     r14
0x18002a1ec  pop     r13
0x18002a1ee  pop     r12
0x18002a1f0  pop     rdi
0x18002a1f1  pop     rsi
0x18002a1f2  pop     rbp
0x18002a1f3  pop     rbx
0x18002a1f4  retn
0x18002a1f6  mov     eax, 8
0x18002a1fb  jmp     short loc_18002A1E4
0x18002a1fd  lea     r14, [rsi+rsi*2]
0x18002a201  cmp     qword ptr [rbx+r14*8], 0
0x18002a206  jz      short loc_18002A1C2
0x18002a208  mov     rcx, [rdi+rbp*8+28h]; hMem
0x18002a20d  call    cs:__imp_LocalFree
0x18002a214  nop     dword ptr [rax+rax+00h]
0x18002a219  mov     rax, [rbx+r14*8]
0x18002a21d  mov     [rdi+rbp*8+28h], rax
0x18002a222  jmp     short loc_18002A1C2
0x18002a224  mov     rcx, [rdi+rsi*8+28h]; MultiByteString
0x18002a229  lea     rdx, [rsp+78h+var_58]; unsigned __int16 **
0x18002a22e  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x18002a233  mov     r12d, eax
0x18002a236  test    eax, eax
0x18002a238  jnz     loc_18002A19F
0x18002a23e  mov     rax, [rdi+rsi*8+28h]
0x18002a243  mov     [rbx+rbp*8], rax
0x18002a247  mov     rax, [rsp+78h+var_58]
0x18002a24c  mov     [rdi+rsi*8+28h], rax
0x18002a251  jmp     loc_18002A177
0x18002a256  mov     r14, [rdi+rbp*8+28h]
0x18002a25b  lea     rbp, [rsi+rsi*2]
0x18002a25f  cmp     qword ptr [rbx+rbp*8], 0
0x18002a264  mov     rax, [r14+8]
0x18002a268  mov     [rbx+rbp*8+8], rax
0x18002a26d  mov     rax, [r14+10h]
0x18002a271  mov     [rbx+rbp*8+10h], rax
0x18002a276  jz      short loc_18002A290
0x18002a278  mov     rcx, [r14+18h]; hMem
0x18002a27c  call    cs:__imp_LocalFree
0x18002a283  nop     dword ptr [rax+rax+00h]
0x18002a288  mov     rax, [rbx+rbp*8]
0x18002a28c  mov     [r14+18h], rax
0x18002a290  cmp     qword ptr [rbx+rbp*8+8], 0
0x18002a296  jz      short loc_18002A2B1
0x18002a298  mov     rcx, [r14+8]; hMem
0x18002a29c  call    cs:__imp_LocalFree
0x18002a2a3  nop     dword ptr [rax+rax+00h]
0x18002a2a8  mov     rax, [rbx+rbp*8+8]
0x18002a2ad  mov     [r14+8], rax
0x18002a2b1  cmp     qword ptr [rbx+rbp*8+10h], 0
0x18002a2b7  jz      loc_18002A1C2
0x18002a2bd  mov     rcx, [r14+10h]; hMem
0x18002a2c1  call    cs:__imp_LocalFree
0x18002a2c8  nop     dword ptr [rax+rax+00h]
0x18002a2cd  mov     rax, [rbx+rbp*8+8]
0x18002a2d2  mov     [r14+10h], rax
0x18002a2d6  jmp     loc_18002A1C2
0x18002a2db  mov     rsi, [rdi+rsi*8+28h]
0x18002a2e0  lea     rdx, [rsp+78h+var_58]; unsigned __int16 **
0x18002a2e5  mov     rcx, [rsi+18h]; MultiByteString
0x18002a2e9  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x18002a2ee  mov     r12d, eax
0x18002a2f1  test    eax, eax
0x18002a2f3  jnz     loc_18002A19F
0x18002a2f9  mov     rax, [rsi+18h]
0x18002a2fd  lea     rdx, [rsp+78h+var_58]; unsigned __int16 **
0x18002a302  mov     [rbx+rbp*8], rax
0x18002a306  mov     rax, [rsp+78h+var_58]
0x18002a30b  mov     rcx, [rsi+8]; MultiByteString
0x18002a30f  mov     [rsi+18h], rax
0x18002a313  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x18002a318  mov     r12d, eax
0x18002a31b  test    eax, eax
0x18002a31d  jnz     loc_18002A19F
0x18002a323  mov     rax, [rsi+8]
0x18002a327  lea     rdx, [rsp+78h+var_58]; unsigned __int16 **
0x18002a32c  mov     [rbx+rbp*8+8], rax
0x18002a331  mov     rax, [rsp+78h+var_58]
0x18002a336  mov     rcx, [rsi+10h]; MultiByteString
0x18002a33a  mov     [rsi+8], rax
0x18002a33e  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x18002a343  mov     r12d, eax
0x18002a346  test    eax, eax
0x18002a348  jnz     loc_18002A19F
0x18002a34e  mov     rax, [rsi+10h]
0x18002a352  mov     [rbx+rbp*8+10h], rax
0x18002a357  mov     rax, [rsp+78h+var_58]
0x18002a35c  mov     [rsi+10h], rax
0x18002a360  jmp     loc_18002A177
```
