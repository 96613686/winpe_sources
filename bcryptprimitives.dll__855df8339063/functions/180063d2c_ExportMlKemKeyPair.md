# ExportMlKemKeyPair

- ea: `0x180063d2c`
- end: `0x180063e3a`
- name: `ExportMlKemKeyPair`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180064c80`

## callees

- `0x180001280`
- `0x18000ecb0`
- `0x180056cf0`
- `0x180063170`
- `0x180063d2c`
- `0x180064130`

## string_xrefs

- `0x180063d74`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall ExportMlKemKeyPair(__int64 a1, char *a2, _DWORD *a3, unsigned int a4, unsigned int *a5)
{
  int MlKemBlobInfo; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r12
  __int64 v14; // r15
  unsigned int v15; // edi
  unsigned int Value; // eax
  wchar_t **v18; // [rsp+30h] [rbp-58h] BYREF

  v18 = 0;
  MlKemBlobInfo = GetMlKemBlobInfo(a2, &v18);
  v9 = MlKemBlobInfo;
  if ( MlKemBlobInfo >= 0 )
  {
    v12 = *(_QWORD *)(a1 + 24);
    v13 = *(unsigned int *)(v12 + 8);
    v14 = *(unsigned int *)((char *)v18[3] + v12);
    v15 = v13 + v14 + 12;
    if ( !a3 )
      goto LABEL_10;
    if ( a4 < v15 )
    {
      v9 = -1073741789;
      v10 = 1920;
      v11 = 3221225507LL;
      goto LABEL_4;
    }
    *a3 = *((_DWORD *)v18 + 4);
    a3[1] = *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8LL);
    a3[2] = v14;
    memcpy_0(a3 + 3, **(const void ***)(a1 + 24), *(unsigned int *)(*(_QWORD *)(a1 + 24) + 8LL));
    Value = SymCryptMlKemkeyGetValue(*(_QWORD *)(a1 + 32), (char *)a3 + v13 + 12, v14);
    if ( !Value )
    {
LABEL_10:
      *a5 = v15;
      return v9;
    }
    MlKemBlobInfo = SymcryptErrorCodeToNtStatus(Value);
    v9 = MlKemBlobInfo;
    v10 = 1941;
  }
  else
  {
    v10 = 1903;
  }
  v11 = (unsigned int)MlKemBlobInfo;
LABEL_4:
  DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v10);
  return v9;
}

```

## disassembly

```asm
0x180063d2c  push    rbx
0x180063d2e  push    rbp
0x180063d2f  push    rsi
0x180063d30  push    rdi
0x180063d31  push    r12
0x180063d33  push    r13
0x180063d35  push    r14
0x180063d37  push    r15
0x180063d39  sub     rsp, 48h
0x180063d3d  mov     rax, rdx
0x180063d40  mov     [rsp+88h+var_58], 0
0x180063d49  mov     rbp, rcx
0x180063d4c  lea     rdx, [rsp+88h+var_58]
0x180063d51  mov     rcx, rax
0x180063d54  mov     r13d, r9d
0x180063d57  mov     rsi, r8
0x180063d5a  call    GetMlKemBlobInfo
0x180063d5f  mov     ebx, eax
0x180063d61  test    eax, eax
0x180063d63  jns     short loc_180063D85
0x180063d65  mov     r9d, 76Fh
0x180063d6b  mov     ecx, eax
0x180063d6d  lea     rdx, aStatus; "Status"
0x180063d74  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180063d7b  call    DebugTraceError
0x180063d80  jmp     loc_180063E26
0x180063d85  mov     rcx, [rbp+18h]
0x180063d89  mov     r14, [rsp+88h+var_58]
0x180063d8e  mov     r12d, [rcx+8]
0x180063d92  mov     rax, [r14+18h]
0x180063d96  mov     r15d, [rcx+rax]
0x180063d9a  lea     edi, [r15+0Ch]
0x180063d9e  add     edi, r12d
0x180063da1  test    rsi, rsi
0x180063da4  jz      short loc_180063E1C
0x180063da6  cmp     r13d, edi
0x180063da9  jnb     short loc_180063DBD
0x180063dab  mov     ebx, 0C0000023h
0x180063db0  mov     r9d, 780h
0x180063db6  mov     ecx, 0C0000023h
0x180063dbb  jmp     short loc_180063D6D
0x180063dbd  mov     eax, [r14+10h]
0x180063dc1  mov     [rsi], eax
0x180063dc3  mov     rax, [rbp+18h]
0x180063dc7  mov     ecx, [rax+8]
0x180063dca  mov     [rsi+4], ecx
0x180063dcd  lea     rcx, [rsi+0Ch]; void *
0x180063dd1  mov     [rsi+8], r15d
0x180063dd5  mov     rdx, [rbp+18h]
0x180063dd9  mov     r8d, [rdx+8]; Size
0x180063ddd  mov     rdx, [rdx]; Src
0x180063de0  call    memcpy_0
0x180063de5  mov     r9d, [r14+14h]
0x180063de9  lea     rdx, [rsi+0Ch]
0x180063ded  mov     rcx, [rbp+20h]
0x180063df1  add     rdx, r12
0x180063df4  mov     r8, r15
0x180063df7  mov     [rsp+88h+var_68], 0
0x180063dff  call    SymCryptMlKemkeyGetValue
0x180063e04  test    eax, eax
0x180063e06  jz      short loc_180063E1C
0x180063e08  mov     ecx, eax
0x180063e0a  call    SymcryptErrorCodeToNtStatus
0x180063e0f  mov     ebx, eax
0x180063e11  mov     r9d, 795h
0x180063e17  jmp     loc_180063D6B
0x180063e1c  mov     rax, [rsp+88h+arg_20]
0x180063e24  mov     [rax], edi
0x180063e26  mov     eax, ebx
0x180063e28  add     rsp, 48h
0x180063e2c  pop     r15
0x180063e2e  pop     r14
0x180063e30  pop     r13
0x180063e32  pop     r12
0x180063e34  pop     rdi
0x180063e35  pop     rsi
0x180063e36  pop     rbp
0x180063e37  pop     rbx
0x180063e38  retn
```
