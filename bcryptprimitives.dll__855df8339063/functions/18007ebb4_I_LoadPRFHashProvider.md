# I_LoadPRFHashProvider

- ea: `0x18007ebb4`
- end: `0x18007eccc`
- name: `I_LoadPRFHashProvider`
- size: `280`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180054188`
- `0x18007ecd4`

## callees

- `0x18000ecb0`
- `0x18000ef70`
- `0x18000f810`
- `0x18007eb80`
- `0x18007ebb4`

## string_xrefs

- `0x18007ec9d`: `onecore\ds\security\cryptoapi\ncrypt\kdf\tls1.c`

## pseudocode

```c
__int64 __fastcall I_LoadPRFHashProvider(const wchar_t *a1, __int64 *a2)
{
  int HashProperty; // ebx
  __int64 v4; // r9
  unsigned int v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  HashProperty = MSCryptOpenHashProvider(a2, a1, 0);
  if ( HashProperty >= 0 )
  {
    HashProperty = MSCryptGetHashProperty(*a2, L"ObjectLength", a2 + 1, 4u, &v6, 0);
    if ( HashProperty >= 0 )
    {
      HashProperty = MSCryptGetHashProperty(*a2, L"HashDigestLength", (__int64 *)((char *)a2 + 12), 4u, &v6, 0);
      if ( HashProperty >= 0 )
      {
        HashProperty = MSCryptGetHashProperty(*a2, L"HashBlockLength", a2 + 2, 4u, &v6, 0);
        if ( HashProperty >= 0 )
          return 0;
        v4 = 158;
      }
      else
      {
        v4 = 144;
      }
    }
    else
    {
      v4 = 130;
    }
  }
  else
  {
    v4 = 116;
  }
  DebugTraceError((unsigned int)HashProperty, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\tls1.c", v4);
  I_ClosePRFHashEntry(a2);
  return (unsigned int)HashProperty;
}

```

## disassembly

```asm
0x18007ebb4  mov     [rsp+arg_0], rbx
0x18007ebb9  push    rdi
0x18007ebba  sub     rsp, 30h
0x18007ebbe  mov     rdi, rdx
0x18007ebc1  mov     [rsp+38h+arg_8], 0
0x18007ebc9  xorps   xmm0, xmm0
0x18007ebcc  xor     eax, eax
0x18007ebce  movups  xmmword ptr [rdx], xmm0
0x18007ebd1  mov     [rdx+10h], rax
0x18007ebd5  xor     r8d, r8d
0x18007ebd8  mov     rdx, rcx
0x18007ebdb  mov     rcx, rdi
0x18007ebde  call    MSCryptOpenHashProvider
0x18007ebe3  mov     ebx, eax
0x18007ebe5  test    eax, eax
0x18007ebe7  jns     short loc_18007EBF4
0x18007ebe9  mov     r9d, 74h ; 't'
0x18007ebef  jmp     loc_18007EC9D
0x18007ebf4  mov     rcx, [rdi]
0x18007ebf7  lea     rax, [rsp+38h+arg_8]
0x18007ebfc  lea     r8, [rdi+8]
0x18007ec00  mov     [rsp+38h+var_10], 0
0x18007ec08  mov     r9d, 4
0x18007ec0e  mov     [rsp+38h+var_18], rax
0x18007ec13  lea     rdx, aObjectlength; "ObjectLength"
0x18007ec1a  call    MSCryptGetHashProperty
0x18007ec1f  mov     ebx, eax
0x18007ec21  test    eax, eax
0x18007ec23  jns     short loc_18007EC2D
0x18007ec25  mov     r9d, 82h
0x18007ec2b  jmp     short loc_18007EC9D
0x18007ec2d  mov     rcx, [rdi]
0x18007ec30  lea     rax, [rsp+38h+arg_8]
0x18007ec35  lea     r8, [rdi+0Ch]
0x18007ec39  mov     [rsp+38h+var_10], 0
0x18007ec41  mov     r9d, 4
0x18007ec47  mov     [rsp+38h+var_18], rax
0x18007ec4c  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18007ec53  call    MSCryptGetHashProperty
0x18007ec58  mov     ebx, eax
0x18007ec5a  test    eax, eax
0x18007ec5c  jns     short loc_18007EC66
0x18007ec5e  mov     r9d, 90h
0x18007ec64  jmp     short loc_18007EC9D
0x18007ec66  mov     rcx, [rdi]
0x18007ec69  lea     rax, [rsp+38h+arg_8]
0x18007ec6e  lea     r8, [rdi+10h]
0x18007ec72  mov     [rsp+38h+var_10], 0
0x18007ec7a  mov     r9d, 4
0x18007ec80  mov     [rsp+38h+var_18], rax
0x18007ec85  lea     rdx, aHashblocklengt; "HashBlockLength"
0x18007ec8c  call    MSCryptGetHashProperty
0x18007ec91  mov     ebx, eax
0x18007ec93  test    eax, eax
0x18007ec95  jns     short loc_18007ECBC
0x18007ec97  mov     r9d, 9Eh
0x18007ec9d  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007eca4  mov     ecx, ebx
0x18007eca6  lea     rdx, aStatus; "Status"
0x18007ecad  call    DebugTraceError
0x18007ecb2  mov     rcx, rdi
0x18007ecb5  call    I_ClosePRFHashEntry
0x18007ecba  jmp     short loc_18007ECBE
0x18007ecbc  xor     ebx, ebx
0x18007ecbe  mov     eax, ebx
0x18007ecc0  mov     rbx, [rsp+38h+arg_0]
0x18007ecc5  add     rsp, 30h
0x18007ecc9  pop     rdi
0x18007ecca  retn
```
