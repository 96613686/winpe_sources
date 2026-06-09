# SetEntriesInAclA

- ea: `0x180026d00`
- end: `0x180026f66`
- name: `SetEntriesInAclA`
- size: `614`
- prototype: `DWORD __stdcall(ULONG cCountOfExplicitEntries, PEXPLICIT_ACCESS_A pListOfExplicitEntries, PACL OldAcl, PACL *NewAcl)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180026d00`
- `0x180027084`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180026d48`
- `KERNELBASE!LocalAlloc` at `0x180026d48`
- `KERNEL32!LocalFree` at `0x180026df5`
- `KERNEL32!LocalFree` at `0x180026e26`
- `KERNEL32!LocalFree` at `0x180026e8f`
- `KERNEL32!LocalFree` at `0x180026ea9`
- `KERNEL32!LocalFree` at `0x180026ec8`
- `KERNEL32!LocalFree` at `0x180026df5`
- `KERNEL32!LocalFree` at `0x180026e26`
- `KERNEL32!LocalFree` at `0x180026e8f`
- `KERNEL32!LocalFree` at `0x180026ea9`
- `KERNEL32!LocalFree` at `0x180026ec8`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180026db6`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180026db6`

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
0x180026d00  mov     [rsp+arg_10], r8
0x180026d05  push    rbx
0x180026d06  push    rbp
0x180026d07  push    rsi
0x180026d08  push    rdi
0x180026d09  push    r12
0x180026d0b  push    r13
0x180026d0d  push    r14
0x180026d0f  push    r15
0x180026d11  sub     rsp, 38h
0x180026d15  xor     ebx, ebx
0x180026d17  mov     r15d, ecx
0x180026d1a  mov     [rsp+78h+var_58], rbx
0x180026d1f  mov     r13, r9
0x180026d22  mov     rsi, r8
0x180026d25  mov     rdi, rdx
0x180026d28  test    ecx, ecx
0x180026d2a  jz      short loc_180026DAA
0x180026d2c  xor     edx, edx
0x180026d2e  or      eax, 0FFFFFFFFh
0x180026d31  div     r15d
0x180026d34  cmp     eax, 18h
0x180026d37  jb      loc_180026E0F
0x180026d3d  lea     rdx, [r15+r15*2]
0x180026d41  shl     rdx, 3; uBytes
0x180026d45  lea     ecx, [rbx+40h]; uFlags
0x180026d48  call    cs:__imp_LocalAlloc
0x180026d4e  mov     rbx, rax
0x180026d51  test    rax, rax
0x180026d54  jz      loc_180026E0F
0x180026d5a  xor     r14d, r14d
0x180026d5d  cmp     r14d, r15d
0x180026d60  jnb     short loc_180026DA2
0x180026d62  lea     rbp, [r14+r14*2]
0x180026d66  lea     rsi, [r14+r14*2]
0x180026d6a  mov     qword ptr [rbx+rbp*8], 0
0x180026d72  add     rsi, rsi
0x180026d75  mov     qword ptr [rbx+rbp*8+8], 0
0x180026d7e  mov     qword ptr [rbx+rbp*8+10h], 0
0x180026d87  mov     ecx, [rdi+rsi*8+1Ch]
0x180026d8b  sub     ecx, 1
0x180026d8e  jz      loc_180026E37
0x180026d94  cmp     ecx, 3
0x180026d97  jz      loc_180026EDC
0x180026d9d  inc     r14d
0x180026da0  jmp     short loc_180026D5D
0x180026da2  mov     rsi, [rsp+78h+arg_10]
0x180026daa  mov     r9, r13; NewAcl
0x180026dad  mov     r8, rsi; OldAcl
0x180026db0  mov     rdx, rdi; pListOfExplicitEntries
0x180026db3  mov     ecx, r15d; cCountOfExplicitEntries
0x180026db6  call    cs:__imp_SetEntriesInAclW
0x180026dbc  mov     r12d, eax
0x180026dbf  xor     r13d, r13d
0x180026dc2  test    r15d, r15d
0x180026dc5  jz      short loc_180026DED
0x180026dc7  xor     esi, esi
0x180026dc9  lea     rbp, [rsi+rsi*2]
0x180026dcd  add     rbp, rbp
0x180026dd0  mov     ecx, [rdi+rbp*8+1Ch]
0x180026dd4  sub     ecx, 1
0x180026dd7  jz      short loc_180026E16
0x180026dd9  cmp     ecx, 3
0x180026ddc  jz      loc_180026E69
0x180026de2  inc     r13d
0x180026de5  inc     rsi
0x180026de8  cmp     r13d, r15d
0x180026deb  jb      short loc_180026DC9
0x180026ded  test    rbx, rbx
0x180026df0  jz      short loc_180026DFB
0x180026df2  mov     rcx, rbx; hMem
0x180026df5  call    cs:__imp_LocalFree
0x180026dfb  mov     eax, r12d
0x180026dfe  add     rsp, 38h
0x180026e02  pop     r15
0x180026e04  pop     r14
0x180026e06  pop     r13
0x180026e08  pop     r12
0x180026e0a  pop     rdi
0x180026e0b  pop     rsi
0x180026e0c  pop     rbp
0x180026e0d  pop     rbx
0x180026e0e  retn
0x180026e0f  mov     eax, 8
0x180026e14  jmp     short loc_180026DFE
0x180026e16  lea     r14, [rsi+rsi*2]
0x180026e1a  cmp     qword ptr [rbx+r14*8], 0
0x180026e1f  jz      short loc_180026DE2
0x180026e21  mov     rcx, [rdi+rbp*8+28h]; hMem
0x180026e26  call    cs:__imp_LocalFree
0x180026e2c  mov     rax, [rbx+r14*8]
0x180026e30  mov     [rdi+rbp*8+28h], rax
0x180026e35  jmp     short loc_180026DE2
0x180026e37  mov     rcx, [rdi+rsi*8+28h]; MultiByteString
0x180026e3c  lea     rdx, [rsp+78h+var_58]; unsigned __int16 **
0x180026e41  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x180026e46  mov     r12d, eax
0x180026e49  test    eax, eax
0x180026e4b  jnz     loc_180026DBF
0x180026e51  mov     rax, [rdi+rsi*8+28h]
0x180026e56  mov     [rbx+rbp*8], rax
0x180026e5a  mov     rax, [rsp+78h+var_58]
0x180026e5f  mov     [rdi+rsi*8+28h], rax
0x180026e64  jmp     loc_180026D9D
0x180026e69  mov     r14, [rdi+rbp*8+28h]
0x180026e6e  lea     rbp, [rsi+rsi*2]
0x180026e72  cmp     qword ptr [rbx+rbp*8], 0
0x180026e77  mov     rax, [r14+8]
0x180026e7b  mov     [rbx+rbp*8+8], rax
0x180026e80  mov     rax, [r14+10h]
0x180026e84  mov     [rbx+rbp*8+10h], rax
0x180026e89  jz      short loc_180026E9D
0x180026e8b  mov     rcx, [r14+18h]; hMem
0x180026e8f  call    cs:__imp_LocalFree
0x180026e95  mov     rax, [rbx+rbp*8]
0x180026e99  mov     [r14+18h], rax
0x180026e9d  cmp     qword ptr [rbx+rbp*8+8], 0
0x180026ea3  jz      short loc_180026EB8
0x180026ea5  mov     rcx, [r14+8]; hMem
0x180026ea9  call    cs:__imp_LocalFree
0x180026eaf  mov     rax, [rbx+rbp*8+8]
0x180026eb4  mov     [r14+8], rax
0x180026eb8  cmp     qword ptr [rbx+rbp*8+10h], 0
0x180026ebe  jz      loc_180026DE2
0x180026ec4  mov     rcx, [r14+10h]; hMem
0x180026ec8  call    cs:__imp_LocalFree
0x180026ece  mov     rax, [rbx+rbp*8+8]
0x180026ed3  mov     [r14+10h], rax
0x180026ed7  jmp     loc_180026DE2
0x180026edc  mov     rsi, [rdi+rsi*8+28h]
0x180026ee1  lea     rdx, [rsp+78h+var_58]; unsigned __int16 **
0x180026ee6  mov     rcx, [rsi+18h]; MultiByteString
0x180026eea  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x180026eef  mov     r12d, eax
0x180026ef2  test    eax, eax
0x180026ef4  jnz     loc_180026DBF
0x180026efa  mov     rax, [rsi+18h]
0x180026efe  lea     rdx, [rsp+78h+var_58]; unsigned __int16 **
0x180026f03  mov     [rbx+rbp*8], rax
0x180026f07  mov     rax, [rsp+78h+var_58]
0x180026f0c  mov     rcx, [rsi+8]; MultiByteString
0x180026f10  mov     [rsi+18h], rax
0x180026f14  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x180026f19  mov     r12d, eax
0x180026f1c  test    eax, eax
0x180026f1e  jnz     loc_180026DBF
0x180026f24  mov     rax, [rsi+8]
0x180026f28  lea     rdx, [rsp+78h+var_58]; unsigned __int16 **
0x180026f2d  mov     [rbx+rbp*8+8], rax
0x180026f32  mov     rax, [rsp+78h+var_58]
0x180026f37  mov     rcx, [rsi+10h]; MultiByteString
0x180026f3b  mov     [rsi+8], rax
0x180026f3f  call    ?ConvertStringAToStringW@@YAKPEADPEAPEAG@Z; ConvertStringAToStringW(char *,ushort * *)
0x180026f44  mov     r12d, eax
0x180026f47  test    eax, eax
0x180026f49  jnz     loc_180026DBF
0x180026f4f  mov     rax, [rsi+10h]
0x180026f53  mov     [rbx+rbp*8+10h], rax
0x180026f58  mov     rax, [rsp+78h+var_58]
0x180026f5d  mov     [rsi+10h], rax
0x180026f61  jmp     loc_180026D9D
```
