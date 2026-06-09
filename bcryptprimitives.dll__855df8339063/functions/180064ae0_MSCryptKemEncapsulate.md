# MSCryptKemEncapsulate

- ea: `0x180064ae0`
- end: `0x180064c70`
- name: `MSCryptKemEncapsulate`
- size: `400`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _DWORD *, __int64, unsigned int, unsigned int *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001020`
- `0x18000ecb0`
- `0x180056cf0`
- `0x180064ae0`
- `0x180065430`
- `0x18006fa0c`

## string_xrefs

- `0x180064c4d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall MSCryptKemEncapsulate(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _DWORD *a4,
        __int64 a5,
        unsigned int a6,
        unsigned int *a7,
        int a8)
{
  __int64 v11; // r9
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rcx
  unsigned int v15; // ecx
  unsigned int v16; // eax
  _QWORD v18[9]; // [rsp+50h] [rbp-48h] BYREF

  v18[0] = 0;
  if ( a8 )
  {
    v11 = 1345;
LABEL_30:
    v13 = -1073741811;
    v14 = 3221225485LL;
    goto LABEL_31;
  }
  if ( !a4 || !a7 )
  {
    v11 = 1352;
    goto LABEL_30;
  }
  v12 = ValidateKemKey(a1, v18, 1);
  v13 = v12;
  if ( v12 < 0 )
  {
    v11 = 1359;
LABEL_7:
    v14 = (unsigned int)v12;
LABEL_31:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v11);
    return v13;
  }
  if ( *(_DWORD *)(v18[0] + 8LL) != 458753 && *(_DWORD *)(v18[0] + 8LL) != 458754 )
  {
    v11 = 1380;
LABEL_11:
    v13 = -1073741637;
    v14 = 3221225659LL;
    goto LABEL_31;
  }
  v15 = *(_DWORD *)(*(_QWORD *)(v18[0] + 24LL) + 20LL);
  if ( !a2 || !a5 )
  {
    *a4 = 32;
    *a7 = v15;
    return v13;
  }
  if ( a3 != 32 )
  {
    if ( a3 < 0x20 )
      goto LABEL_26;
    goto LABEL_25;
  }
  if ( a6 != v15 )
  {
LABEL_25:
    v13 = -1073741306;
    if ( a6 >= v15 )
    {
LABEL_27:
      v11 = 1405;
      v14 = v13;
      goto LABEL_31;
    }
LABEL_26:
    v13 = -1073741789;
    goto LABEL_27;
  }
  if ( *(_DWORD *)(v18[0] + 8LL) == 458753 )
  {
    v16 = SymCryptMlKemEncapsulate(*(_QWORD *)(v18[0] + 32LL), a2, 32, a5, a6);
  }
  else
  {
    if ( *(_DWORD *)(v18[0] + 8LL) != 458754 )
    {
      v11 = 1424;
      goto LABEL_11;
    }
    v16 = SymCryptCompositeMlKemEncapsulateEx(*(_QWORD *)(v18[0] + 32LL), 1, 458753, a5);
  }
  if ( v16 )
  {
    v12 = SymcryptErrorCodeToNtStatus(v16);
    v13 = v12;
    v11 = 1432;
    goto LABEL_7;
  }
  *a4 = 32;
  *a7 = a6;
  return v13;
}

```

## disassembly

```asm
0x180064ae0  push    rbx
0x180064ae2  push    rbp
0x180064ae3  push    rsi
0x180064ae4  push    rdi
0x180064ae5  push    r14
0x180064ae7  push    r15
0x180064ae9  sub     rsp, 68h
0x180064aed  cmp     [rsp+98h+arg_38], 0
0x180064af5  mov     r15, r9
0x180064af8  mov     esi, r8d
0x180064afb  mov     rbp, rdx
0x180064afe  mov     [rsp+98h+var_48], 0
0x180064b07  jz      short loc_180064B14
0x180064b09  mov     r9d, 541h
0x180064b0f  jmp     loc_180064C43
0x180064b14  test    r15, r15
0x180064b17  jz      loc_180064C3D
0x180064b1d  mov     r14, [rsp+98h+arg_30]
0x180064b25  test    r14, r14
0x180064b28  jz      loc_180064C3D
0x180064b2e  mov     r8d, 1
0x180064b34  lea     rdx, [rsp+98h+var_48]
0x180064b39  call    ValidateKemKey
0x180064b3e  mov     ebx, eax
0x180064b40  test    eax, eax
0x180064b42  jns     short loc_180064B51
0x180064b44  mov     r9d, 54Fh
0x180064b4a  mov     ecx, eax
0x180064b4c  jmp     loc_180064C4D
0x180064b51  mov     r10, [rsp+98h+var_48]
0x180064b56  mov     r8d, 70001h
0x180064b5c  mov     edx, [r10+8]
0x180064b60  mov     eax, edx
0x180064b62  sub     eax, r8d
0x180064b65  jz      short loc_180064B81
0x180064b67  cmp     eax, 1
0x180064b6a  jz      short loc_180064B81
0x180064b6c  mov     r9d, 564h
0x180064b72  mov     ebx, 0C00000BBh
0x180064b77  mov     ecx, 0C00000BBh
0x180064b7c  jmp     loc_180064C4D
0x180064b81  mov     rax, [r10+18h]
0x180064b85  mov     ecx, [rax+14h]
0x180064b88  test    rbp, rbp
0x180064b8b  jz      loc_180064C31
0x180064b91  mov     r9, [rsp+98h+arg_20]
0x180064b99  test    r9, r9
0x180064b9c  jz      loc_180064C31
0x180064ba2  mov     edi, [rsp+98h+arg_28]
0x180064ba9  cmp     esi, 20h ; ' '
0x180064bac  jnz     short loc_180064C17
0x180064bae  cmp     edi, ecx
0x180064bb0  jnz     short loc_180064C19
0x180064bb2  sub     edx, r8d
0x180064bb5  jz      short loc_180064BE3
0x180064bb7  cmp     edx, 1
0x180064bba  jz      short loc_180064BC4
0x180064bbc  mov     r9d, 590h
0x180064bc2  jmp     short loc_180064B72
0x180064bc4  mov     rcx, [r10+20h]
0x180064bc8  mov     [rsp+98h+var_58], rdi
0x180064bcd  mov     [rsp+98h+var_60], r9
0x180064bd2  mov     [rsp+98h+var_68], rsi
0x180064bd7  mov     [rsp+98h+var_70], rbp
0x180064bdc  call    SymCryptCompositeMlKemEncapsulateEx
0x180064be1  jmp     short loc_180064BF7
0x180064be3  mov     rcx, [r10+20h]
0x180064be7  mov     r8, rsi
0x180064bea  mov     rdx, rbp
0x180064bed  mov     [rsp+98h+var_78], rdi
0x180064bf2  call    SymCryptMlKemEncapsulate
0x180064bf7  test    eax, eax
0x180064bf9  jz      short loc_180064C0F
0x180064bfb  mov     ecx, eax
0x180064bfd  call    SymcryptErrorCodeToNtStatus
0x180064c02  mov     ebx, eax
0x180064c04  mov     r9d, 598h
0x180064c0a  jmp     loc_180064B4A
0x180064c0f  mov     [r15], esi
0x180064c12  mov     [r14], edi
0x180064c15  jmp     short loc_180064C60
0x180064c17  jb      short loc_180064C22
0x180064c19  mov     ebx, 0C0000206h
0x180064c1e  cmp     edi, ecx
0x180064c20  jnb     short loc_180064C27
0x180064c22  mov     ebx, 0C0000023h
0x180064c27  mov     r9d, 57Dh
0x180064c2d  mov     ecx, ebx
0x180064c2f  jmp     short loc_180064C4D
0x180064c31  mov     dword ptr [r15], 20h ; ' '
0x180064c38  mov     [r14], ecx
0x180064c3b  jmp     short loc_180064C60
0x180064c3d  mov     r9d, 548h
0x180064c43  mov     ebx, 0C000000Dh
0x180064c48  mov     ecx, 0C000000Dh
0x180064c4d  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180064c54  lea     rdx, aStatus; "Status"
0x180064c5b  call    DebugTraceError
0x180064c60  mov     eax, ebx
0x180064c62  add     rsp, 68h
0x180064c66  pop     r15
0x180064c68  pop     r14
0x180064c6a  pop     rdi
0x180064c6b  pop     rsi
0x180064c6c  pop     rbp
0x180064c6d  pop     rbx
0x180064c6e  retn
```
