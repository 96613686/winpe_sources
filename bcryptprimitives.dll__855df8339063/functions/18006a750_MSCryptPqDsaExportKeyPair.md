# MSCryptPqDsaExportKeyPair

- ea: `0x18006a750`
- end: `0x18006a938`
- name: `MSCryptPqDsaExportKeyPair`
- size: `488`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180056cf0`
- `0x180063170`
- `0x18006a750`
- `0x18006b9fc`
- `0x18006bcf8`
- `0x180073e68`
- `0x180075274`

## string_xrefs

- `0x18006a77f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptPqDsaExportKeyPair(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        unsigned int a5,
        unsigned int *a6,
        int a7)
{
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned __int16 *v12; // r8
  __int64 v13; // rbx
  __int64 PqDsaBlobInfoFromType; // rax
  __int64 v15; // rbp
  __int64 v16; // rcx
  __int64 v17; // r12
  unsigned int v18; // r14d
  __int64 v19; // rdi
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int Value; // eax

  if ( a6 )
  {
    *a6 = 0;
    if ( !a1 )
    {
      v8 = 1216;
      goto LABEL_3;
    }
    if ( a2 )
    {
      v9 = -1073741637;
      v8 = 1223;
      v10 = 3221225659LL;
      goto LABEL_4;
    }
    if ( !a3 )
    {
      v8 = 1230;
      goto LABEL_3;
    }
    if ( a4 )
    {
      if ( a5 )
      {
LABEL_13:
        if ( a7 )
        {
          v8 = 1245;
          goto LABEL_3;
        }
        v11 = validatePqDsaKey(a1, 1);
        v13 = v11;
        if ( !v11 )
        {
          v8 = 1253;
LABEL_19:
          v9 = -1073741816;
          v10 = 3221225480LL;
          goto LABEL_4;
        }
        PqDsaBlobInfoFromType = getPqDsaBlobInfoFromType(*(_QWORD *)(v11 + 16), v12);
        v15 = PqDsaBlobInfoFromType;
        if ( !PqDsaBlobInfoFromType )
        {
          v8 = 1261;
          goto LABEL_3;
        }
        v16 = *(_QWORD *)(v13 + 24);
        v17 = *(unsigned int *)(v16 + *(_QWORD *)(PqDsaBlobInfoFromType + 24));
        v18 = *(_DWORD *)(v16 + 8) + v17 + 12;
        if ( a4 )
        {
          if ( a5 < v18 )
          {
            v9 = -1073741789;
            v8 = 1282;
            v10 = 3221225507LL;
            goto LABEL_4;
          }
          v19 = *(unsigned int *)(v16 + 8);
          *a4 = *(_DWORD *)(PqDsaBlobInfoFromType + 16);
          a4[1] = *(_DWORD *)(*(_QWORD *)(v13 + 24) + 8LL);
          a4[2] = v17;
          memcpy_0(a4 + 3, **(const void ***)(v13 + 24), *(unsigned int *)(*(_QWORD *)(v13 + 24) + 8LL));
          if ( *(_DWORD *)(v13 + 8) == 196620 )
          {
            Value = SymCryptMlDsakeyGetValue(
                      *(_QWORD *)(v13 + 40),
                      (char *)a4 + v19 + 12,
                      v17,
                      *(unsigned int *)(v15 + 32));
            if ( Value )
            {
              v21 = SymcryptErrorCodeToNtStatus(Value);
              v8 = 1313;
              goto LABEL_32;
            }
          }
          else
          {
            if ( *(_DWORD *)(v13 + 8) != 196621 )
            {
              v8 = 1336;
              goto LABEL_19;
            }
            v20 = SymCryptCompositeMlDsakeyGetValue(
                    *(_QWORD *)(v13 + 40),
                    (char *)a4 + v19 + 12,
                    v17,
                    *(unsigned int *)(v15 + 32));
            if ( v20 )
            {
              v21 = SymcryptErrorCodeToNtStatus(v20);
              v8 = 1328;
LABEL_32:
              v9 = v21;
              v10 = v21;
              goto LABEL_4;
            }
          }
        }
        v9 = 0;
        *a6 = v18;
        return v9;
      }
    }
    else if ( !a5 )
    {
      goto LABEL_13;
    }
    v8 = 1238;
    goto LABEL_3;
  }
  v8 = 1207;
LABEL_3:
  v9 = -1073741811;
  v10 = 3221225485LL;
LABEL_4:
  DebugTraceError(v10, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v8);
  return v9;
}

```

## disassembly

```asm
0x18006a750  push    rbx
0x18006a752  push    rbp
0x18006a753  push    rsi
0x18006a754  push    rdi
0x18006a755  push    r12
0x18006a757  push    r14
0x18006a759  push    r15
0x18006a75b  sub     rsp, 30h
0x18006a75f  mov     rsi, [rsp+68h+arg_28]
0x18006a767  mov     r15, r9
0x18006a76a  test    rsi, rsi
0x18006a76d  jnz     short loc_18006A797
0x18006a76f  mov     r9d, 4B7h
0x18006a775  mov     ebx, 0C000000Dh
0x18006a77a  mov     ecx, 0C000000Dh
0x18006a77f  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006a786  lea     rdx, aStatus_0; "status"
0x18006a78d  call    DebugTraceError
0x18006a792  jmp     loc_18006A926
0x18006a797  mov     dword ptr [rsi], 0
0x18006a79d  test    rcx, rcx
0x18006a7a0  jnz     short loc_18006A7AA
0x18006a7a2  mov     r9d, 4C0h
0x18006a7a8  jmp     short loc_18006A775
0x18006a7aa  test    rdx, rdx
0x18006a7ad  jz      short loc_18006A7C1
0x18006a7af  mov     ebx, 0C00000BBh
0x18006a7b4  mov     r9d, 4C7h
0x18006a7ba  mov     ecx, 0C00000BBh
0x18006a7bf  jmp     short loc_18006A77F
0x18006a7c1  test    r8, r8
0x18006a7c4  jnz     short loc_18006A7CE
0x18006a7c6  mov     r9d, 4CEh
0x18006a7cc  jmp     short loc_18006A775
0x18006a7ce  mov     edi, [rsp+68h+arg_20]
0x18006a7d5  test    r15, r15
0x18006a7d8  jnz     short loc_18006A7F0
0x18006a7da  test    edi, edi
0x18006a7dc  jnz     short loc_18006A7F4
0x18006a7de  cmp     [rsp+68h+arg_30], 0
0x18006a7e6  jz      short loc_18006A7FF
0x18006a7e8  mov     r9d, 4DDh
0x18006a7ee  jmp     short loc_18006A775
0x18006a7f0  test    edi, edi
0x18006a7f2  jnz     short loc_18006A7DE
0x18006a7f4  mov     r9d, 4D6h
0x18006a7fa  jmp     loc_18006A775
0x18006a7ff  mov     edx, 1
0x18006a804  call    validatePqDsaKey
0x18006a809  mov     rbx, rax
0x18006a80c  test    rax, rax
0x18006a80f  jnz     short loc_18006A826
0x18006a811  mov     r9d, 4E5h
0x18006a817  mov     ebx, 0C0000008h
0x18006a81c  mov     ecx, 0C0000008h
0x18006a821  jmp     loc_18006A77F
0x18006a826  mov     rcx, [rax+10h]
0x18006a82a  mov     rdx, r8
0x18006a82d  call    getPqDsaBlobInfoFromType
0x18006a832  mov     rbp, rax
0x18006a835  test    rax, rax
0x18006a838  jnz     short loc_18006A845
0x18006a83a  mov     r9d, 4EDh
0x18006a840  jmp     loc_18006A775
0x18006a845  mov     rcx, [rbx+18h]
0x18006a849  mov     rax, [rax+18h]
0x18006a84d  mov     r12d, [rcx+rax]
0x18006a851  mov     eax, [rcx+8]
0x18006a854  lea     r14d, [r12+0Ch]
0x18006a859  add     r14d, eax
0x18006a85c  test    r15, r15
0x18006a85f  jz      loc_18006A921
0x18006a865  cmp     edi, r14d
0x18006a868  jnb     short loc_18006A87F
0x18006a86a  mov     ebx, 0C0000023h
0x18006a86f  mov     r9d, 502h
0x18006a875  mov     ecx, 0C0000023h
0x18006a87a  jmp     loc_18006A77F
0x18006a87f  mov     rdi, rax
0x18006a882  mov     eax, [rbp+10h]
0x18006a885  mov     [r15], eax
0x18006a888  mov     rax, [rbx+18h]
0x18006a88c  mov     ecx, [rax+8]
0x18006a88f  mov     [r15+4], ecx
0x18006a893  lea     rcx, [r15+0Ch]; void *
0x18006a897  mov     [r15+8], r12d
0x18006a89b  mov     rdx, [rbx+18h]
0x18006a89f  mov     r8d, [rdx+8]; Size
0x18006a8a3  mov     rdx, [rdx]; Src
0x18006a8a6  call    memcpy_0
0x18006a8ab  mov     ecx, [rbx+8]
0x18006a8ae  sub     ecx, 3000Ch
0x18006a8b4  jz      short loc_18006A8F0
0x18006a8b6  cmp     ecx, 1
0x18006a8b9  jz      short loc_18006A8C6
0x18006a8bb  mov     r9d, 538h
0x18006a8c1  jmp     loc_18006A817
0x18006a8c6  mov     r9d, [rbp+20h]
0x18006a8ca  lea     rdx, [r15+0Ch]
0x18006a8ce  mov     rcx, [rbx+28h]
0x18006a8d2  add     rdx, rdi
0x18006a8d5  mov     r8, r12
0x18006a8d8  call    SymCryptCompositeMlDsakeyGetValue
0x18006a8dd  test    eax, eax
0x18006a8df  jz      short loc_18006A921
0x18006a8e1  mov     ecx, eax
0x18006a8e3  call    SymcryptErrorCodeToNtStatus
0x18006a8e8  mov     r9d, 530h
0x18006a8ee  jmp     short loc_18006A918
0x18006a8f0  mov     r9d, [rbp+20h]
0x18006a8f4  lea     rdx, [r15+0Ch]
0x18006a8f8  mov     rcx, [rbx+28h]
0x18006a8fc  add     rdx, rdi
0x18006a8ff  mov     r8, r12
0x18006a902  call    SymCryptMlDsakeyGetValue
0x18006a907  test    eax, eax
0x18006a909  jz      short loc_18006A921
0x18006a90b  mov     ecx, eax
0x18006a90d  call    SymcryptErrorCodeToNtStatus
0x18006a912  mov     r9d, 521h
0x18006a918  mov     ebx, eax
0x18006a91a  mov     ecx, eax
0x18006a91c  jmp     loc_18006A77F
0x18006a921  xor     ebx, ebx
0x18006a923  mov     [rsi], r14d
0x18006a926  mov     eax, ebx
0x18006a928  add     rsp, 30h
0x18006a92c  pop     r15
0x18006a92e  pop     r14
0x18006a930  pop     r12
0x18006a932  pop     rdi
0x18006a933  pop     rsi
0x18006a934  pop     rbp
0x18006a935  pop     rbx
0x18006a936  retn
```
