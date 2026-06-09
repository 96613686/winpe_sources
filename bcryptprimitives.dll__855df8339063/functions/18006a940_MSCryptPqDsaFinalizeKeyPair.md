# MSCryptPqDsaFinalizeKeyPair

- ea: `0x18006a940`
- end: `0x18006aaa3`
- name: `MSCryptPqDsaFinalizeKeyPair`
- size: `355`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180056cf0`
- `0x18006a940`
- `0x18006bcf8`
- `0x180073cf8`
- `0x180073db8`
- `0x180073e00`
- `0x180075078`
- `0x1800750fc`
- `0x180075128`

## string_xrefs

- `0x18006a95f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`
- `0x18006aa0e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`
- `0x18006aa63`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptPqDsaFinalizeKeyPair(__int64 a1, int a2)
{
  __int64 v2; // r9
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rbx
  __int64 v9; // rdx
  _QWORD *v10; // rax
  _QWORD *v11; // rdi
  unsigned int v12; // eax
  __int64 v13; // rax
  unsigned int v14; // eax

  if ( a1 )
  {
    if ( a2 )
    {
      v2 = 1060;
      goto LABEL_3;
    }
    v5 = validatePqDsaKey(a1, 0);
    v8 = v5;
    if ( !v5 )
    {
      v2 = 1068;
LABEL_9:
      v3 = -1073741816;
      v4 = 3221225480LL;
      goto LABEL_4;
    }
    v9 = *(_QWORD *)(v5 + 24);
    if ( !v9 )
    {
      v2 = 1078;
      goto LABEL_9;
    }
    if ( *(_DWORD *)(v5 + 8) == 196620 )
    {
      v13 = SymCryptMlDsakeyAllocate(*(unsigned int *)(v9 + 24), v9, v6, v7);
      v11 = (_QWORD *)v13;
      if ( !v13 )
      {
        v2 = 1089;
        goto LABEL_17;
      }
      v14 = SymCryptMlDsakeyGenerate(v13, *(unsigned int *)(v8 + 36));
      if ( v14 )
      {
        v3 = SymcryptErrorCodeToNtStatus(v14);
        DebugTraceError(v3, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", 1097);
        SymCryptMlDsakeyFree(v11);
        return v3;
      }
    }
    else
    {
      if ( *(_DWORD *)(v5 + 8) != 196621 )
      {
        v2 = 1129;
        goto LABEL_9;
      }
      v10 = SymCryptCompositeMlDsakeyAllocate(*(unsigned int *)(v9 + 24));
      v11 = v10;
      if ( !v10 )
      {
        v2 = 1110;
LABEL_17:
        v3 = -1073741801;
        v4 = 3221225495LL;
        goto LABEL_4;
      }
      v12 = SymCryptCompositeMlDsakeyGenerate(v10, *(unsigned int *)(v8 + 36));
      if ( v12 )
      {
        v3 = SymcryptErrorCodeToNtStatus(v12);
        DebugTraceError(v3, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", 1118);
        SymCryptCompositeMlDsakeyFree(v11);
        return v3;
      }
    }
    *(_QWORD *)(v8 + 40) = v11;
    *(_DWORD *)(v8 + 32) = 1;
    return 0;
  }
  v2 = 1053;
LABEL_3:
  v3 = -1073741811;
  v4 = 3221225485LL;
LABEL_4:
  DebugTraceError(v4, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v2);
  return v3;
}

```

## disassembly

```asm
0x18006a940  mov     [rsp+arg_0], rbx
0x18006a945  push    rdi
0x18006a946  sub     rsp, 20h
0x18006a94a  test    rcx, rcx
0x18006a94d  jnz     short loc_18006A977
0x18006a94f  mov     r9d, 41Dh
0x18006a955  mov     ebx, 0C000000Dh
0x18006a95a  mov     ecx, 0C000000Dh
0x18006a95f  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006a966  lea     rdx, aStatus_0; "status"
0x18006a96d  call    DebugTraceError
0x18006a972  jmp     loc_18006AA95
0x18006a977  test    edx, edx
0x18006a979  jz      short loc_18006A983
0x18006a97b  mov     r9d, 424h
0x18006a981  jmp     short loc_18006A955
0x18006a983  xor     edx, edx
0x18006a985  call    validatePqDsaKey
0x18006a98a  mov     rbx, rax
0x18006a98d  test    rax, rax
0x18006a990  jnz     short loc_18006A9A4
0x18006a992  mov     r9d, 42Ch
0x18006a998  mov     ebx, 0C0000008h
0x18006a99d  mov     ecx, 0C0000008h
0x18006a9a2  jmp     short loc_18006A95F
0x18006a9a4  mov     rdx, [rax+18h]
0x18006a9a8  test    rdx, rdx
0x18006a9ab  jnz     short loc_18006A9B5
0x18006a9ad  mov     r9d, 436h
0x18006a9b3  jmp     short loc_18006A998
0x18006a9b5  mov     ecx, [rax+8]
0x18006a9b8  sub     ecx, 3000Ch
0x18006a9be  jz      short loc_18006AA33
0x18006a9c0  cmp     ecx, 1
0x18006a9c3  jz      short loc_18006A9CD
0x18006a9c5  mov     r9d, 469h
0x18006a9cb  jmp     short loc_18006A998
0x18006a9cd  mov     ecx, [rdx+18h]
0x18006a9d0  call    SymCryptCompositeMlDsakeyAllocate
0x18006a9d5  mov     rdi, rax
0x18006a9d8  test    rax, rax
0x18006a9db  jnz     short loc_18006A9F2
0x18006a9dd  mov     r9d, 456h
0x18006a9e3  mov     ebx, 0C0000017h
0x18006a9e8  mov     ecx, 0C0000017h
0x18006a9ed  jmp     loc_18006A95F
0x18006a9f2  mov     edx, [rbx+24h]
0x18006a9f5  mov     rcx, rdi
0x18006a9f8  call    SymCryptCompositeMlDsakeyGenerate
0x18006a9fd  test    eax, eax
0x18006a9ff  jz      loc_18006AA88
0x18006aa05  mov     ecx, eax
0x18006aa07  call    SymcryptErrorCodeToNtStatus
0x18006aa0c  mov     ecx, eax
0x18006aa0e  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006aa15  mov     r9d, 45Eh
0x18006aa1b  lea     rdx, aStatus_0; "status"
0x18006aa22  mov     ebx, eax
0x18006aa24  call    DebugTraceError
0x18006aa29  mov     rcx, rdi
0x18006aa2c  call    SymCryptCompositeMlDsakeyFree
0x18006aa31  jmp     short loc_18006AA95
0x18006aa33  mov     ecx, [rdx+18h]
0x18006aa36  call    SymCryptMlDsakeyAllocate
0x18006aa3b  mov     rdi, rax
0x18006aa3e  test    rax, rax
0x18006aa41  jnz     short loc_18006AA4B
0x18006aa43  mov     r9d, 441h
0x18006aa49  jmp     short loc_18006A9E3
0x18006aa4b  mov     edx, [rbx+24h]
0x18006aa4e  mov     rcx, rdi
0x18006aa51  call    SymCryptMlDsakeyGenerate
0x18006aa56  test    eax, eax
0x18006aa58  jz      short loc_18006AA88
0x18006aa5a  mov     ecx, eax
0x18006aa5c  call    SymcryptErrorCodeToNtStatus
0x18006aa61  mov     ecx, eax
0x18006aa63  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006aa6a  mov     r9d, 449h
0x18006aa70  lea     rdx, aStatus_0; "status"
0x18006aa77  mov     ebx, eax
0x18006aa79  call    DebugTraceError
0x18006aa7e  mov     rcx, rdi
0x18006aa81  call    SymCryptMlDsakeyFree
0x18006aa86  jmp     short loc_18006AA95
0x18006aa88  mov     [rbx+28h], rdi
0x18006aa8c  mov     dword ptr [rbx+20h], 1
0x18006aa93  xor     ebx, ebx
0x18006aa95  mov     eax, ebx
0x18006aa97  mov     rbx, [rsp+28h+arg_0]
0x18006aa9c  add     rsp, 20h
0x18006aaa0  pop     rdi
0x18006aaa1  retn
```
