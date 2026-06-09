# WkstGenerateHMACWithSHA512

- ea: `0x18002fa20`
- end: `0x18002fbd7`
- name: `WkstGenerateHMACWithSHA512`
- size: `439`
- prototype: `__int64 __usercall@<rax>(BCRYPT_ALG_HANDLE hAlgorithm@<rcx>, ULONG cbInput, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002f730`

## callees

- `0x18002fa20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002faba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fb15`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002faba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fb15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fbae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fbb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fbae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fbb7`
- `bcrypt!BCryptHashData` at `0x18002fb62`
- `bcrypt!BCryptHashData` at `0x18002fb62`
- `bcrypt!BCryptFinishHash` at `0x18002fb7c`
- `bcrypt!BCryptFinishHash` at `0x18002fb7c`
- `bcrypt!BCryptCreateHash` at `0x18002fb47`
- `bcrypt!BCryptCreateHash` at `0x18002fb47`
- `bcrypt!BCryptDestroyHash` at `0x18002fba5`
- `bcrypt!BCryptDestroyHash` at `0x18002fba5`
- `bcrypt!BCryptGetProperty` at `0x18002fa9a`
- `bcrypt!BCryptGetProperty` at `0x18002faf3`
- `bcrypt!BCryptGetProperty` at `0x18002fa9a`
- `bcrypt!BCryptGetProperty` at `0x18002faf3`

## pseudocode

```c
__int64 __fastcall WkstGenerateHMACWithSHA512(
        BCRYPT_ALG_HANDLE hAlgorithm,
        UCHAR *a2,
        ULONG a3,
        UCHAR *a4,
        ULONG cbInput,
        UCHAR **a6,
        _DWORD *a7)
{
  UCHAR *v9; // rsi
  UCHAR *v10; // rdi
  NTSTATUS Property; // ebx
  int v12; // eax
  ULONG pcbResult; // [rsp+40h] [rbp-20h] BYREF
  UCHAR v15[4]; // [rsp+44h] [rbp-1Ch] BYREF
  UCHAR pbOutput[4]; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-10h] BYREF

  phHash = 0;
  v9 = 0;
  *(_DWORD *)pbOutput = 0;
  v10 = 0;
  *a6 = 0;
  *a7 = 0;
  *(_DWORD *)v15 = 0;
  pcbResult = 0;
  if ( !cbInput || !a3 )
    goto LABEL_14;
  Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_15;
  if ( pcbResult != 4 )
    goto LABEL_14;
  v9 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)pbOutput);
  if ( !v9 )
  {
LABEL_6:
    Property = -1073741670;
    goto LABEL_15;
  }
  Property = BCryptGetProperty(hAlgorithm, L"HashDigestLength", v15, 4u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    if ( pcbResult == 4 )
    {
      v10 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)v15);
      if ( !v10 )
        goto LABEL_6;
      Property = BCryptCreateHash(hAlgorithm, &phHash, v9, *(ULONG *)pbOutput, a2, a3, 0);
      if ( Property >= 0 )
      {
        Property = BCryptHashData(phHash, a4, cbInput, 0);
        if ( Property >= 0 )
        {
          Property = BCryptFinishHash(phHash, v10, *(ULONG *)v15, 0);
          if ( Property >= 0 )
          {
            v12 = *(_DWORD *)v15;
            *a6 = v10;
            v10 = 0;
            *a7 = v12;
          }
        }
      }
      goto LABEL_15;
    }
LABEL_14:
    Property = -1073741811;
  }
LABEL_15:
  if ( phHash )
    BCryptDestroyHash(phHash);
  LocalFree(v9);
  LocalFree(v10);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18002fa20  mov     rax, rsp
0x18002fa23  mov     [rax+8], rbx
0x18002fa27  mov     [rax+20h], r9
0x18002fa2b  mov     [rax+10h], rdx
0x18002fa2f  push    rbp
0x18002fa30  push    rsi
0x18002fa31  push    rdi
0x18002fa32  push    r12
0x18002fa34  push    r13
0x18002fa36  push    r14
0x18002fa38  push    r15
0x18002fa3a  mov     rbp, rsp
0x18002fa3d  sub     rsp, 60h
0x18002fa41  mov     r12, [rbp+arg_28]
0x18002fa45  mov     r15, rcx
0x18002fa48  mov     r13, [rbp+arg_30]
0x18002fa4c  xor     ecx, ecx
0x18002fa4e  mov     r14d, r8d
0x18002fa51  mov     [rbp+phHash], rcx
0x18002fa55  mov     esi, ecx
0x18002fa57  mov     dword ptr [rbp+pbOutput], ecx
0x18002fa5a  mov     edi, ecx
0x18002fa5c  mov     [r12], rcx
0x18002fa60  mov     [r13+0], ecx
0x18002fa64  mov     dword ptr [rbp+var_1C], ecx
0x18002fa67  mov     [rbp+var_20], ecx
0x18002fa6a  cmp     [rbp+cbInput], ecx
0x18002fa6d  jz      loc_18002FB97
0x18002fa73  test    r8d, r8d
0x18002fa76  jz      loc_18002FB97
0x18002fa7c  mov     [rax-70h], ecx
0x18002fa7f  lea     r9d, [rcx+4]; cbOutput
0x18002fa83  lea     rax, [rbp+var_20]
0x18002fa87  mov     rcx, r15; hObject
0x18002fa8a  lea     r8, [rbp+pbOutput]; pbOutput
0x18002fa8e  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18002fa93  lea     rdx, aObjectlength; "ObjectLength"
0x18002fa9a  call    cs:__imp_BCryptGetProperty
0x18002faa0  mov     ebx, eax
0x18002faa2  test    eax, eax
0x18002faa4  js      loc_18002FB9C
0x18002faaa  cmp     [rbp+var_20], 4
0x18002faae  jnz     loc_18002FB97
0x18002fab4  mov     edx, dword ptr [rbp+pbOutput]; uBytes
0x18002fab7  lea     ecx, [rdi+40h]; uFlags
0x18002faba  call    cs:__imp_LocalAlloc
0x18002fac0  mov     rsi, rax
0x18002fac3  test    rax, rax
0x18002fac6  jnz     short loc_18002FAD2
0x18002fac8  mov     ebx, 0C000009Ah
0x18002facd  jmp     loc_18002FB9C
0x18002fad2  lea     rax, [rbp+var_20]
0x18002fad6  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18002fada  mov     r9d, 4; cbOutput
0x18002fae0  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18002fae5  lea     r8, [rbp+var_1C]; pbOutput
0x18002fae9  mov     rcx, r15; hObject
0x18002faec  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18002faf3  call    cs:__imp_BCryptGetProperty
0x18002faf9  mov     ebx, eax
0x18002fafb  test    eax, eax
0x18002fafd  js      loc_18002FB9C
0x18002fb03  cmp     [rbp+var_20], 4
0x18002fb07  jnz     loc_18002FB97
0x18002fb0d  mov     edx, dword ptr [rbp+var_1C]; uBytes
0x18002fb10  mov     ecx, 40h ; '@'; uFlags
0x18002fb15  call    cs:__imp_LocalAlloc
0x18002fb1b  mov     rdi, rax
0x18002fb1e  test    rax, rax
0x18002fb21  jz      short loc_18002FAC8
0x18002fb23  mov     rax, [rbp+pbSecret]
0x18002fb27  lea     rdx, [rbp+phHash]; phHash
0x18002fb2b  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x18002fb2f  mov     r8, rsi; pbHashObject
0x18002fb32  mov     [rsp+60h+var_30], 0; dwFlags
0x18002fb3a  mov     rcx, r15; hAlgorithm
0x18002fb3d  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x18002fb42  mov     [rsp+60h+pcbResult], rax; pbSecret
0x18002fb47  call    cs:__imp_BCryptCreateHash
0x18002fb4d  mov     ebx, eax
0x18002fb4f  test    eax, eax
0x18002fb51  js      short loc_18002FB9C
0x18002fb53  mov     r8d, [rbp+cbInput]; cbInput
0x18002fb57  xor     r9d, r9d; dwFlags
0x18002fb5a  mov     rdx, [rbp+pbInput]; pbInput
0x18002fb5e  mov     rcx, [rbp+phHash]; hHash
0x18002fb62  call    cs:__imp_BCryptHashData
0x18002fb68  mov     ebx, eax
0x18002fb6a  test    eax, eax
0x18002fb6c  js      short loc_18002FB9C
0x18002fb6e  mov     r8d, dword ptr [rbp+var_1C]; cbOutput
0x18002fb72  xor     r9d, r9d; dwFlags
0x18002fb75  mov     rcx, [rbp+phHash]; hHash
0x18002fb79  mov     rdx, rdi; pbOutput
0x18002fb7c  call    cs:__imp_BCryptFinishHash
0x18002fb82  mov     ebx, eax
0x18002fb84  test    eax, eax
0x18002fb86  js      short loc_18002FB9C
0x18002fb88  mov     eax, dword ptr [rbp+var_1C]
0x18002fb8b  mov     [r12], rdi
0x18002fb8f  xor     edi, edi
0x18002fb91  mov     [r13+0], eax
0x18002fb95  jmp     short loc_18002FB9C
0x18002fb97  mov     ebx, 0C000000Dh
0x18002fb9c  mov     rcx, [rbp+phHash]; hHash
0x18002fba0  test    rcx, rcx
0x18002fba3  jz      short loc_18002FBAB
0x18002fba5  call    cs:__imp_BCryptDestroyHash
0x18002fbab  mov     rcx, rsi; hMem
0x18002fbae  call    cs:__imp_LocalFree
0x18002fbb4  mov     rcx, rdi; hMem
0x18002fbb7  call    cs:__imp_LocalFree
0x18002fbbd  mov     eax, ebx
0x18002fbbf  mov     rbx, [rsp+60h+arg_0]
0x18002fbc7  add     rsp, 60h
0x18002fbcb  pop     r15
0x18002fbcd  pop     r14
0x18002fbcf  pop     r13
0x18002fbd1  pop     r12
0x18002fbd3  pop     rdi
0x18002fbd4  pop     rsi
0x18002fbd5  pop     rbp
0x18002fbd6  retn
```
