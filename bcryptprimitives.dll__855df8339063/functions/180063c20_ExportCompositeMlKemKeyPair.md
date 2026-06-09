# ExportCompositeMlKemKeyPair

- ea: `0x180063c20`
- end: `0x180063d26`
- name: `ExportCompositeMlKemKeyPair`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180064c80`

## callees

- `0x18000ecb0`
- `0x180056cf0`
- `0x180063170`
- `0x180063c20`
- `0x180063fdc`
- `0x180070004`

## string_xrefs

- `0x180063c68`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall ExportCompositeMlKemKeyPair(__int64 a1, char *a2, _DWORD *a3, unsigned int a4, unsigned int *a5)
{
  int CompositeMlKemBlobInfo; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rcx
  wchar_t **v13; // r14
  __int64 v14; // r12
  __int64 v15; // r15
  unsigned int v16; // edi
  unsigned int Value; // eax
  wchar_t **v19; // [rsp+30h] [rbp-58h] BYREF

  v19 = 0;
  CompositeMlKemBlobInfo = GetCompositeMlKemBlobInfo(a2, &v19);
  v9 = CompositeMlKemBlobInfo;
  if ( CompositeMlKemBlobInfo >= 0 )
  {
    v12 = *(_QWORD *)(a1 + 24);
    v13 = v19;
    v14 = *(unsigned int *)(v12 + 8);
    v15 = *(unsigned int *)((char *)v19[3] + v12);
    v16 = v14 + v15 + 12;
    if ( !a3 )
      goto LABEL_10;
    if ( a4 < v16 )
    {
      v9 = -1073741789;
      v10 = 1989;
      v11 = 3221225507LL;
      goto LABEL_4;
    }
    *a3 = *((_DWORD *)v19 + 4);
    a3[1] = *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8LL);
    a3[2] = v15;
    memcpy_0(a3 + 3, **(const void ***)(a1 + 24), *(unsigned int *)(*(_QWORD *)(a1 + 24) + 8LL));
    Value = SymCryptCompositeMlKemkeyGetValue(
              *(unsigned int ***)(a1 + 32),
              (_DWORD *)((char *)a3 + v14 + 12),
              v15,
              *((_DWORD *)v13 + 5));
    if ( !Value )
    {
LABEL_10:
      *a5 = v16;
      return v9;
    }
    CompositeMlKemBlobInfo = SymcryptErrorCodeToNtStatus(Value);
    v9 = CompositeMlKemBlobInfo;
    v10 = 2010;
  }
  else
  {
    v10 = 1973;
  }
  v11 = (unsigned int)CompositeMlKemBlobInfo;
LABEL_4:
  DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v10);
  return v9;
}

```

## disassembly

```asm
0x180063c20  push    rbx
0x180063c22  push    rbp
0x180063c23  push    rsi
0x180063c24  push    rdi
0x180063c25  push    r12
0x180063c27  push    r13
0x180063c29  push    r14
0x180063c2b  push    r15
0x180063c2d  sub     rsp, 48h
0x180063c31  mov     rax, rdx
0x180063c34  mov     [rsp+88h+var_58], 0
0x180063c3d  mov     rbp, rcx
0x180063c40  lea     rdx, [rsp+88h+var_58]
0x180063c45  mov     rcx, rax
0x180063c48  mov     r13d, r9d
0x180063c4b  mov     rsi, r8
0x180063c4e  call    GetCompositeMlKemBlobInfo
0x180063c53  mov     ebx, eax
0x180063c55  test    eax, eax
0x180063c57  jns     short loc_180063C79
0x180063c59  mov     r9d, 7B5h
0x180063c5f  mov     ecx, eax
0x180063c61  lea     rdx, aStatus; "Status"
0x180063c68  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180063c6f  call    DebugTraceError
0x180063c74  jmp     loc_180063D12
0x180063c79  mov     rcx, [rbp+18h]
0x180063c7d  mov     r14, [rsp+88h+var_58]
0x180063c82  mov     r12d, [rcx+8]
0x180063c86  mov     rax, [r14+18h]
0x180063c8a  mov     r15d, [rcx+rax]
0x180063c8e  lea     edi, [r15+0Ch]
0x180063c92  add     edi, r12d
0x180063c95  test    rsi, rsi
0x180063c98  jz      short loc_180063D08
0x180063c9a  cmp     r13d, edi
0x180063c9d  jnb     short loc_180063CB1
0x180063c9f  mov     ebx, 0C0000023h
0x180063ca4  mov     r9d, 7C5h
0x180063caa  mov     ecx, 0C0000023h
0x180063caf  jmp     short loc_180063C61
0x180063cb1  mov     eax, [r14+10h]
0x180063cb5  mov     [rsi], eax
0x180063cb7  mov     rax, [rbp+18h]
0x180063cbb  mov     ecx, [rax+8]
0x180063cbe  mov     [rsi+4], ecx
0x180063cc1  lea     rcx, [rsi+0Ch]; void *
0x180063cc5  mov     [rsi+8], r15d
0x180063cc9  mov     rdx, [rbp+18h]
0x180063ccd  mov     r8d, [rdx+8]; Size
0x180063cd1  mov     rdx, [rdx]; Src
0x180063cd4  call    memcpy_0
0x180063cd9  mov     r9d, [r14+14h]
0x180063cdd  lea     rdx, [rsi+0Ch]
0x180063ce1  mov     rcx, [rbp+20h]
0x180063ce5  add     rdx, r12
0x180063ce8  mov     r8, r15
0x180063ceb  call    SymCryptCompositeMlKemkeyGetValue
0x180063cf0  test    eax, eax
0x180063cf2  jz      short loc_180063D08
0x180063cf4  mov     ecx, eax
0x180063cf6  call    SymcryptErrorCodeToNtStatus
0x180063cfb  mov     ebx, eax
0x180063cfd  mov     r9d, 7DAh
0x180063d03  jmp     loc_180063C5F
0x180063d08  mov     rax, [rsp+88h+arg_20]
0x180063d10  mov     [rax], edi
0x180063d12  mov     eax, ebx
0x180063d14  add     rsp, 48h
0x180063d18  pop     r15
0x180063d1a  pop     r14
0x180063d1c  pop     r13
0x180063d1e  pop     r12
0x180063d20  pop     rdi
0x180063d21  pop     rsi
0x180063d22  pop     rbp
0x180063d23  pop     rbx
0x180063d24  retn
```
