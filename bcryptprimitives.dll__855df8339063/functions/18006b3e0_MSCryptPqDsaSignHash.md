# MSCryptPqDsaSignHash

- ea: `0x18006b3e0`
- end: `0x18006b69e`
- name: `MSCryptPqDsaSignHash`
- size: `702`
- prototype: `__int64 __fastcall(__int64, __int64, const void *, unsigned int, __int64, unsigned int, unsigned int *, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180056cf0`
- `0x18006b3e0`
- `0x18006bb20`
- `0x18006bcf8`
- `0x180073758`
- `0x1800740d8`
- `0x180074220`
- `0x180074660`

## string_xrefs

- `0x18006b432`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptPqDsaSignHash(
        __int64 a1,
        __int64 a2,
        const void *a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        unsigned int *a7,
        int a8)
{
  unsigned int *v8; // rsi
  size_t v10; // rbp
  __int64 v12; // r9
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdi
  int PqDsaVariant; // eax
  int v18; // r9d
  unsigned int v19; // edx
  void *v20; // r11
  unsigned int v21; // r8d
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v27; // [rsp+30h] [rbp-68h]
  int v28; // [rsp+50h] [rbp-48h] BYREF
  _QWORD v29[8]; // [rsp+58h] [rbp-40h] BYREF
  int v30; // [rsp+A8h] [rbp+10h] BYREF

  v8 = a7;
  v10 = a4;
  v29[0] = 0;
  v30 = 0;
  v28 = 0;
  if ( a7 )
  {
    *a7 = 0;
    if ( !a1 )
    {
      v12 = 1608;
      goto LABEL_3;
    }
    v15 = validatePqDsaKey(a1, 1);
    v16 = v15;
    if ( !v15 )
    {
      v12 = 1616;
LABEL_9:
      v13 = -1073741816;
      v14 = 3221225480LL;
      goto LABEL_4;
    }
    PqDsaVariant = validateInputAndGetPqDsaVariant(v15, (__int64)a3, v10, a2, a8, &v30, &v28);
    v13 = PqDsaVariant;
    if ( PqDsaVariant < 0 )
    {
      v12 = 1623;
LABEL_12:
      v14 = (unsigned int)PqDsaVariant;
      goto LABEL_4;
    }
    if ( a5 )
    {
      if ( a6 )
      {
LABEL_15:
        v19 = *(_DWORD *)(*(_QWORD *)(v16 + 24) + 20LL);
        if ( a5 )
        {
          if ( a6 < v19 )
          {
            v13 = -1073741789;
            v12 = 1649;
            v14 = 3221225507LL;
            goto LABEL_4;
          }
          if ( a2 )
          {
            v20 = *(void **)a2;
            v21 = *(_DWORD *)(a2 + 8);
          }
          else
          {
            v20 = 0;
            v21 = 0;
          }
          if ( *(_DWORD *)(v16 + 8) == 196620 )
          {
            if ( v30 )
            {
              if ( v30 == 1 )
              {
                v24 = SymCryptExternalMuMlDsaSign(*(_QWORD *)(v16 + 40), (_DWORD)a3, v10, v18, a5, a6);
                if ( v24 )
                {
                  PqDsaVariant = SymcryptErrorCodeToNtStatus(v24);
                  v13 = PqDsaVariant;
                  v12 = 1698;
                  goto LABEL_12;
                }
              }
              else
              {
                if ( v30 != 2 )
                {
                  v12 = 1725;
                  goto LABEL_3;
                }
                v23 = SymCryptHashMlDsaSign(*(_QWORD *)(v16 + 40), v28, (_DWORD)a3, v10, (__int64)v20, v21, v27, a5, a6);
                if ( v23 )
                {
                  PqDsaVariant = SymcryptErrorCodeToNtStatus(v23);
                  v13 = PqDsaVariant;
                  v12 = 1717;
                  goto LABEL_12;
                }
              }
            }
            else
            {
              v25 = SymCryptMlDsaSign(*(_QWORD *)(v16 + 40), (_DWORD)a3, v10, (_DWORD)v20, v21);
              if ( v25 )
              {
                PqDsaVariant = SymcryptErrorCodeToNtStatus(v25);
                v13 = PqDsaVariant;
                v12 = 1682;
                goto LABEL_12;
              }
            }
            *v8 = *(_DWORD *)(*(_QWORD *)(v16 + 24) + 20LL);
          }
          else
          {
            if ( *(_DWORD *)(v16 + 8) != 196621 )
            {
              v12 = 1757;
              goto LABEL_9;
            }
            v22 = SymCryptCompositeMlDsaSign(*(_QWORD **)(v16 + 40), a3, v10, v20, v21, v30 == 2, a5, a6, v29);
            if ( v22 )
            {
              PqDsaVariant = SymcryptErrorCodeToNtStatus(v22);
              v13 = PqDsaVariant;
              v12 = 1747;
              goto LABEL_12;
            }
            *v8 = v29[0];
          }
        }
        else
        {
          *v8 = v19;
        }
        return 0;
      }
    }
    else if ( !a6 )
    {
      goto LABEL_15;
    }
    v12 = 1631;
    goto LABEL_3;
  }
  v12 = 1599;
LABEL_3:
  v13 = -1073741811;
  v14 = 3221225485LL;
LABEL_4:
  DebugTraceError(v14, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v12);
  return v13;
}

```

## disassembly

```asm
0x18006b3e0  mov     rax, rsp
0x18006b3e3  push    rbx
0x18006b3e4  push    rbp
0x18006b3e5  push    rsi
0x18006b3e6  push    rdi
0x18006b3e7  push    r14
0x18006b3e9  push    r15
0x18006b3eb  sub     rsp, 68h
0x18006b3ef  mov     rsi, [rsp+98h+arg_30]
0x18006b3f7  mov     r15, r8
0x18006b3fa  mov     ebp, r9d
0x18006b3fd  mov     r14, rdx
0x18006b400  mov     qword ptr [rax-40h], 0
0x18006b408  mov     dword ptr [rax+10h], 0
0x18006b40f  mov     dword ptr [rax-48h], 0
0x18006b416  test    rsi, rsi
0x18006b419  jnz     short loc_18006B443
0x18006b41b  mov     r9d, 63Fh
0x18006b421  mov     ebx, 0C000000Dh
0x18006b426  mov     ecx, 0C000000Dh
0x18006b42b  lea     rdx, aStatus_0; "status"
0x18006b432  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006b439  call    DebugTraceError
0x18006b43e  jmp     loc_18006B68E
0x18006b443  mov     dword ptr [rsi], 0
0x18006b449  test    rcx, rcx
0x18006b44c  jnz     short loc_18006B456
0x18006b44e  mov     r9d, 648h
0x18006b454  jmp     short loc_18006B421
0x18006b456  mov     edx, 1
0x18006b45b  call    validatePqDsaKey
0x18006b460  mov     rdi, rax
0x18006b463  test    rax, rax
0x18006b466  jnz     short loc_18006B47A
0x18006b468  mov     r9d, 650h
0x18006b46e  mov     ebx, 0C0000008h
0x18006b473  mov     ecx, 0C0000008h
0x18006b478  jmp     short loc_18006B42B
0x18006b47a  lea     rax, [rsp+98h+var_48]
0x18006b47f  mov     r9, r14
0x18006b482  mov     [rsp+98h+var_68], rax
0x18006b487  mov     r8d, ebp
0x18006b48a  lea     rax, [rsp+98h+arg_8]
0x18006b492  mov     rdx, r15
0x18006b495  mov     [rsp+98h+var_70], rax
0x18006b49a  mov     rcx, rdi
0x18006b49d  mov     eax, [rsp+98h+arg_38]
0x18006b4a4  mov     dword ptr [rsp+98h+var_78], eax
0x18006b4a8  call    validateInputAndGetPqDsaVariant
0x18006b4ad  mov     ebx, eax
0x18006b4af  test    eax, eax
0x18006b4b1  jns     short loc_18006B4C0
0x18006b4b3  mov     r9d, 657h
0x18006b4b9  mov     ecx, eax
0x18006b4bb  jmp     loc_18006B42B
0x18006b4c0  mov     r10, [rsp+98h+arg_20]
0x18006b4c8  mov     ecx, [rsp+98h+arg_28]
0x18006b4cf  test    r10, r10
0x18006b4d2  jnz     short loc_18006B4EB
0x18006b4d4  test    ecx, ecx
0x18006b4d6  jnz     short loc_18006B4EF
0x18006b4d8  mov     rax, [rdi+18h]
0x18006b4dc  mov     edx, [rax+14h]
0x18006b4df  test    r10, r10
0x18006b4e2  jnz     short loc_18006B4FA
0x18006b4e4  mov     [rsi], edx
0x18006b4e6  jmp     loc_18006B68C
0x18006b4eb  test    ecx, ecx
0x18006b4ed  jnz     short loc_18006B4D8
0x18006b4ef  mov     r9d, 65Fh
0x18006b4f5  jmp     loc_18006B421
0x18006b4fa  cmp     ecx, edx
0x18006b4fc  jnb     short loc_18006B513
0x18006b4fe  mov     ebx, 0C0000023h
0x18006b503  mov     r9d, 671h
0x18006b509  mov     ecx, 0C0000023h
0x18006b50e  jmp     loc_18006B42B
0x18006b513  test    r14, r14
0x18006b516  jnz     short loc_18006B520
0x18006b518  xor     r11d, r11d
0x18006b51b  xor     r8d, r8d
0x18006b51e  jmp     short loc_18006B527
0x18006b520  mov     r11, [r14]
0x18006b523  mov     r8d, [r14+8]
0x18006b527  mov     edx, [rdi+8]
0x18006b52a  sub     edx, 3000Ch
0x18006b530  jz      short loc_18006B5A6
0x18006b532  cmp     edx, 1
0x18006b535  jz      short loc_18006B542
0x18006b537  mov     r9d, 6DDh
0x18006b53d  jmp     loc_18006B46E
0x18006b542  xor     edx, edx
0x18006b544  mov     eax, ecx
0x18006b546  cmp     [rsp+98h+arg_8], 2
0x18006b54e  lea     r9, [rsp+98h+var_40]
0x18006b553  mov     [rsp+98h+var_58], r9
0x18006b558  mov     r9, r11
0x18006b55b  mov     [rsp+98h+var_60], rax
0x18006b560  setz    dl
0x18006b563  mov     ecx, r8d
0x18006b566  mov     r8, rbp
0x18006b569  mov     [rsp+98h+var_68], r10
0x18006b56e  mov     dword ptr [rsp+98h+var_70], edx
0x18006b572  mov     rdx, r15
0x18006b575  mov     [rsp+98h+var_78], rcx
0x18006b57a  mov     rcx, [rdi+28h]
0x18006b57e  call    SymCryptCompositeMlDsaSign
0x18006b583  test    eax, eax
0x18006b585  jz      short loc_18006B59B
0x18006b587  mov     ecx, eax
0x18006b589  call    SymcryptErrorCodeToNtStatus
0x18006b58e  mov     ebx, eax
0x18006b590  mov     r9d, 6D3h
0x18006b596  jmp     loc_18006B4B9
0x18006b59b  mov     eax, dword ptr [rsp+98h+var_40]
0x18006b59f  mov     [rsi], eax
0x18006b5a1  jmp     loc_18006B68C
0x18006b5a6  mov     edx, [rsp+98h+arg_8]
0x18006b5ad  test    edx, edx
0x18006b5af  jz      loc_18006B645
0x18006b5b5  sub     edx, 1
0x18006b5b8  jz      short loc_18006B612
0x18006b5ba  cmp     edx, 1
0x18006b5bd  jz      short loc_18006B5CA
0x18006b5bf  mov     r9d, 6BDh
0x18006b5c5  jmp     loc_18006B421
0x18006b5ca  mov     edx, [rsp+98h+var_48]
0x18006b5ce  mov     r9, rbp
0x18006b5d1  mov     eax, ecx
0x18006b5d3  mov     [rsp+98h+var_58], rax
0x18006b5d8  mov     ecx, r8d
0x18006b5db  mov     r8, r15
0x18006b5de  mov     [rsp+98h+var_60], r10
0x18006b5e3  mov     [rsp+98h+var_70], rcx
0x18006b5e8  mov     rcx, [rdi+28h]
0x18006b5ec  mov     [rsp+98h+var_78], r11
0x18006b5f1  call    SymCryptHashMlDsaSign
0x18006b5f6  test    eax, eax
0x18006b5f8  jz      loc_18006B683
0x18006b5fe  mov     ecx, eax
0x18006b600  call    SymcryptErrorCodeToNtStatus
0x18006b605  mov     ebx, eax
0x18006b607  mov     r9d, 6B5h
0x18006b60d  jmp     loc_18006B4B9
0x18006b612  mov     eax, ecx
0x18006b614  mov     r8, rbp
0x18006b617  mov     rcx, [rdi+28h]
0x18006b61b  mov     rdx, r15
0x18006b61e  mov     [rsp+98h+var_70], rax
0x18006b623  mov     [rsp+98h+var_78], r10
0x18006b628  call    SymCryptExternalMuMlDsaSign
0x18006b62d  test    eax, eax
0x18006b62f  jz      short loc_18006B683
0x18006b631  mov     ecx, eax
0x18006b633  call    SymcryptErrorCodeToNtStatus
0x18006b638  mov     ebx, eax
0x18006b63a  mov     r9d, 6A2h
0x18006b640  jmp     loc_18006B4B9
0x18006b645  mov     eax, ecx
0x18006b647  mov     r9, r11
0x18006b64a  mov     ecx, r8d
0x18006b64d  mov     rdx, r15
0x18006b650  mov     [rsp+98h+var_60], rax
0x18006b655  mov     r8, rbp
0x18006b658  mov     [rsp+98h+var_68], r10
0x18006b65d  mov     [rsp+98h+var_78], rcx
0x18006b662  mov     rcx, [rdi+28h]
0x18006b666  call    SymCryptMlDsaSign
0x18006b66b  test    eax, eax
0x18006b66d  jz      short loc_18006B683
0x18006b66f  mov     ecx, eax
0x18006b671  call    SymcryptErrorCodeToNtStatus
0x18006b676  mov     ebx, eax
0x18006b678  mov     r9d, 692h
0x18006b67e  jmp     loc_18006B4B9
0x18006b683  mov     rax, [rdi+18h]
0x18006b687  mov     ecx, [rax+14h]
0x18006b68a  mov     [rsi], ecx
0x18006b68c  xor     ebx, ebx
0x18006b68e  mov     eax, ebx
0x18006b690  add     rsp, 68h
0x18006b694  pop     r15
0x18006b696  pop     r14
0x18006b698  pop     rdi
0x18006b699  pop     rsi
0x18006b69a  pop     rbp
0x18006b69b  pop     rbx
0x18006b69c  retn
```
