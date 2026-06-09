# MSCryptKemFinalizeKeyPair

- ea: `0x180064dc0`
- end: `0x180064ede`
- name: `MSCryptKemFinalizeKeyPair`
- size: `286`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180063e40`
- `0x180063f38`
- `0x180064dc0`
- `0x180065430`

## string_xrefs

- `0x180064ebd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall MSCryptKemFinalizeKeyPair(_DWORD *a1, int a2)
{
  __int64 v3; // rdi
  __int64 v4; // r9
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  int SymCryptMlKemKey; // eax
  __int64 v9; // rcx
  __int64 v11; // [rsp+40h] [rbp+18h] BYREF

  v11 = 0;
  if ( (int)ValidateKemKey(a1, &v11, 0) < 0 || (v3 = v11) == 0 )
  {
    v4 = 1241;
    goto LABEL_21;
  }
  if ( *(_DWORD *)(v11 + 16) )
  {
    v4 = 1248;
LABEL_21:
    v5 = -1073741816;
    v6 = 3221225480LL;
    goto LABEL_22;
  }
  if ( a2 )
  {
    v5 = -1073741811;
    v4 = 1256;
    v6 = 3221225485LL;
LABEL_22:
    DebugTraceError(v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v4);
    return v5;
  }
  if ( *(_DWORD *)(v11 + 8) == 458753 )
  {
    v9 = *(_QWORD *)(v11 + 24);
    if ( !v9 )
    {
      v4 = 1269;
      goto LABEL_21;
    }
    SymCryptMlKemKey = GenerateSymCryptMlKemKey(
                         *(unsigned int *)(v9 + 28),
                         (__int64 *)(v11 + 32),
                         *(_DWORD *)(v11 + 12));
    v5 = SymCryptMlKemKey;
    if ( SymCryptMlKemKey < 0 )
    {
      v4 = 1276;
      goto LABEL_14;
    }
  }
  else
  {
    if ( *(_DWORD *)(v11 + 8) != 458754 )
    {
      v5 = -1073741637;
      v4 = 1305;
      v6 = 3221225659LL;
      goto LABEL_22;
    }
    v7 = *(_QWORD *)(v11 + 24);
    if ( !v7 )
    {
      v4 = 1289;
      goto LABEL_21;
    }
    SymCryptMlKemKey = GenerateSymCryptCompositeMlKemKey(
                         *(_DWORD *)(v7 + 28),
                         (unsigned int ***)(v11 + 32),
                         *(_DWORD *)(v11 + 12));
    v5 = SymCryptMlKemKey;
    if ( SymCryptMlKemKey < 0 )
    {
      v4 = 1296;
LABEL_14:
      v6 = (unsigned int)SymCryptMlKemKey;
      goto LABEL_22;
    }
  }
  *(_DWORD *)(v3 + 16) = 1;
  return v5;
}

```

## disassembly

```asm
0x180064dc0  mov     [rsp+arg_0], rbx
0x180064dc5  push    rdi
0x180064dc6  sub     rsp, 20h
0x180064dca  mov     ebx, edx
0x180064dcc  mov     [rsp+28h+arg_10], 0
0x180064dd5  lea     rdx, [rsp+28h+arg_10]
0x180064dda  xor     r8d, r8d
0x180064ddd  call    ValidateKemKey
0x180064de2  test    eax, eax
0x180064de4  js      loc_180064EAD
0x180064dea  mov     rdi, [rsp+28h+arg_10]
0x180064def  test    rdi, rdi
0x180064df2  jz      loc_180064EAD
0x180064df8  cmp     dword ptr [rdi+10h], 0
0x180064dfc  jz      short loc_180064E09
0x180064dfe  mov     r9d, 4E0h
0x180064e04  jmp     loc_180064EB3
0x180064e09  test    ebx, ebx
0x180064e0b  jz      short loc_180064E22
0x180064e0d  mov     ebx, 0C000000Dh
0x180064e12  mov     r9d, 4E8h
0x180064e18  mov     ecx, 0C000000Dh
0x180064e1d  jmp     loc_180064EBD
0x180064e22  mov     ecx, [rdi+8]
0x180064e25  sub     ecx, 70001h
0x180064e2b  jz      short loc_180064E75
0x180064e2d  cmp     ecx, 1
0x180064e30  jz      short loc_180064E44
0x180064e32  mov     ebx, 0C00000BBh
0x180064e37  mov     r9d, 519h
0x180064e3d  mov     ecx, 0C00000BBh
0x180064e42  jmp     short loc_180064EBD
0x180064e44  mov     rcx, [rdi+18h]
0x180064e48  test    rcx, rcx
0x180064e4b  jnz     short loc_180064E55
0x180064e4d  mov     r9d, 509h
0x180064e53  jmp     short loc_180064EB3
0x180064e55  mov     r8d, [rdi+0Ch]
0x180064e59  lea     rdx, [rdi+20h]
0x180064e5d  mov     ecx, [rcx+1Ch]
0x180064e60  call    GenerateSymCryptCompositeMlKemKey
0x180064e65  mov     ebx, eax
0x180064e67  test    eax, eax
0x180064e69  jns     short loc_180064EA4
0x180064e6b  mov     r9d, 510h
0x180064e71  mov     ecx, eax
0x180064e73  jmp     short loc_180064EBD
0x180064e75  mov     rcx, [rdi+18h]
0x180064e79  test    rcx, rcx
0x180064e7c  jnz     short loc_180064E86
0x180064e7e  mov     r9d, 4F5h
0x180064e84  jmp     short loc_180064EB3
0x180064e86  mov     r8d, [rdi+0Ch]
0x180064e8a  lea     rdx, [rdi+20h]
0x180064e8e  mov     ecx, [rcx+1Ch]
0x180064e91  call    GenerateSymCryptMlKemKey
0x180064e96  mov     ebx, eax
0x180064e98  test    eax, eax
0x180064e9a  jns     short loc_180064EA4
0x180064e9c  mov     r9d, 4FCh
0x180064ea2  jmp     short loc_180064E71
0x180064ea4  mov     dword ptr [rdi+10h], 1
0x180064eab  jmp     short loc_180064ED0
0x180064ead  mov     r9d, 4D9h
0x180064eb3  mov     ebx, 0C0000008h
0x180064eb8  mov     ecx, 0C0000008h
0x180064ebd  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180064ec4  lea     rdx, aStatus; "Status"
0x180064ecb  call    DebugTraceError
0x180064ed0  mov     eax, ebx
0x180064ed2  mov     rbx, [rsp+28h+arg_0]
0x180064ed7  add     rsp, 20h
0x180064edb  pop     rdi
0x180064edc  retn
```
