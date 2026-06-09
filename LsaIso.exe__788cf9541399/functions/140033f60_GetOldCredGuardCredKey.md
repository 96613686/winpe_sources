# GetOldCredGuardCredKey

- ea: `0x140033f60`
- end: `0x140034176`
- name: `GetOldCredGuardCredKey`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140034c60`

## callees

- `0x140033f60`
- `0x140038d10`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x140033ffa`
- `ntdll!RtlLengthSid` at `0x140033ffa`
- `bcrypt!BCryptFinishHash` at `0x14003402f`
- `bcrypt!BCryptFinishHash` at `0x140034106`
- `bcrypt!BCryptFinishHash` at `0x14003402f`
- `bcrypt!BCryptFinishHash` at `0x140034106`
- `bcrypt!BCryptDestroyHash` at `0x140034043`
- `bcrypt!BCryptDestroyHash` at `0x140034116`
- `bcrypt!BCryptDestroyHash` at `0x140034141`
- `bcrypt!BCryptDestroyHash` at `0x140034150`
- `bcrypt!BCryptDestroyHash` at `0x140034043`
- `bcrypt!BCryptDestroyHash` at `0x140034116`
- `bcrypt!BCryptDestroyHash` at `0x140034141`
- `bcrypt!BCryptDestroyHash` at `0x140034150`
- `bcrypt!BCryptHashData` at `0x14003400d`
- `bcrypt!BCryptHashData` at `0x140034099`
- `bcrypt!BCryptHashData` at `0x1400340b6`
- `bcrypt!BCryptHashData` at `0x1400340d0`
- `bcrypt!BCryptHashData` at `0x1400340eb`
- `bcrypt!BCryptHashData` at `0x14003400d`
- `bcrypt!BCryptHashData` at `0x140034099`
- `bcrypt!BCryptHashData` at `0x1400340b6`
- `bcrypt!BCryptHashData` at `0x1400340d0`
- `bcrypt!BCryptHashData` at `0x1400340eb`
- `bcrypt!BCryptCreateHash` at `0x140033fe7`
- `bcrypt!BCryptCreateHash` at `0x140034077`
- `bcrypt!BCryptCreateHash` at `0x140033fe7`
- `bcrypt!BCryptCreateHash` at `0x140034077`

## pseudocode

```c
__int64 __fastcall GetOldCredGuardCredKey(__int64 a1, __int64 a2, ULONG a3, UCHAR *a4, PSID Sid, __int64 a6)
{
  NTSTATUS v9; // ebx
  ULONG v10; // eax
  int v11; // eax
  BCRYPT_HASH_HANDLE v12; // rcx
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-59h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-51h] BYREF
  UCHAR pbOutput[16]; // [rsp+50h] [rbp-49h] BYREF
  __int128 v17; // [rsp+60h] [rbp-39h]
  UCHAR v18[16]; // [rsp+70h] [rbp-29h] BYREF
  _OWORD v19[2]; // [rsp+80h] [rbp-19h] BYREF

  phHash = 0;
  hHash = 0;
  *(_OWORD *)pbOutput = 0;
  v17 = 0;
  *(_OWORD *)v18 = 0;
  memset(v19, 0, sizeof(v19));
  v9 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
  if ( v9 < 0 )
    goto LABEL_11;
  v10 = RtlLengthSid(Sid);
  v9 = BCryptHashData(phHash, (PUCHAR)Sid, v10, 0);
  if ( v9 < 0 )
    goto LABEL_11;
  v9 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
  if ( v9 < 0 )
    goto LABEL_11;
  BCryptDestroyHash(phHash);
  phHash = 0;
  v9 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x51, &hHash, 0, 0, 0, 0, 0);
  if ( v9 < 0
    || (v9 = BCryptHashData(hHash, (PUCHAR)"NtlmStrongCredentialKey", 0x18u, 0), v9 < 0)
    || (v9 = BCryptHashData(hHash, a4, a3, 0), v9 < 0)
    || (v9 = BCryptHashData(hHash, pbOutput, 0x20u, 0), v9 < 0)
    || (v9 = BCryptHashData(hHash, (PUCHAR)(a2 + 38), 0x10u, 0), v9 < 0)
    || (v9 = BCryptFinishHash(hHash, v18, 0x30u, 0), v9 < 0) )
  {
LABEL_11:
    v12 = hHash;
  }
  else
  {
    BCryptDestroyHash(hHash);
    v11 = DWORD1(v19[1]);
    v12 = 0;
    hHash = 0;
    *(_OWORD *)(a6 + 4) = *(_OWORD *)((char *)v19 + 4);
    *(_DWORD *)(a6 + 20) = v11;
    *(_DWORD *)a6 = 20;
  }
  if ( v12 )
    BCryptDestroyHash(v12);
  if ( phHash )
    BCryptDestroyHash(phHash);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140033f60  push    rbp
0x140033f62  push    rbx
0x140033f63  push    rsi
0x140033f64  push    rdi
0x140033f65  push    r13
0x140033f67  push    r14
0x140033f69  push    r15
0x140033f6b  lea     rbp, [rsp-17h]
0x140033f70  sub     rsp, 0B0h
0x140033f77  mov     rax, cs:__security_cookie
0x140033f7e  xor     rax, rsp
0x140033f81  mov     [rbp+47h+var_40], rax
0x140033f85  mov     rdi, [rbp+47h+arg_28]
0x140033f89  xorps   xmm1, xmm1
0x140033f8c  mov     rsi, [rbp+47h+Sid]
0x140033f90  xorps   xmm0, xmm0
0x140033f93  mov     r15, r9
0x140033f96  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x140033f9e  xor     r9d, r9d; cbHashObject
0x140033fa1  mov     [rsp+0E0h+cbSecret], 0; cbSecret
0x140033fa9  mov     r14d, r8d
0x140033fac  mov     [rbp+47h+phHash], 0
0x140033fb4  mov     r13, rdx
0x140033fb7  mov     [rbp+47h+hHash], 0
0x140033fbf  xor     r8d, r8d; pbHashObject
0x140033fc2  mov     [rsp+0E0h+pbSecret], 0; pbSecret
0x140033fcb  lea     ecx, [r9+41h]; hAlgorithm
0x140033fcf  lea     rdx, [rbp+47h+phHash]; phHash
0x140033fd3  movups  xmmword ptr [rbp+47h+pbOutput], xmm0
0x140033fd7  movups  [rbp+47h+var_80], xmm0
0x140033fdb  movups  xmmword ptr [rbp+47h+var_70], xmm1
0x140033fdf  movups  [rbp+47h+var_60], xmm1
0x140033fe3  movups  [rbp+47h+var_50], xmm1
0x140033fe7  call    cs:__imp_BCryptCreateHash
0x140033fed  mov     ebx, eax
0x140033fef  test    eax, eax
0x140033ff1  js      loc_140034138
0x140033ff7  mov     rcx, rsi; Sid
0x140033ffa  call    cs:__imp_RtlLengthSid
0x140034000  mov     rcx, [rbp+47h+phHash]; hHash
0x140034004  xor     r9d, r9d; dwFlags
0x140034007  mov     r8d, eax; cbInput
0x14003400a  mov     rdx, rsi; pbInput
0x14003400d  call    cs:__imp_BCryptHashData
0x140034013  mov     ebx, eax
0x140034015  test    eax, eax
0x140034017  js      loc_140034138
0x14003401d  mov     rcx, [rbp+47h+phHash]; hHash
0x140034021  lea     rdx, [rbp+47h+pbOutput]; pbOutput
0x140034025  xor     r9d, r9d; dwFlags
0x140034028  lea     esi, [r9+20h]
0x14003402c  mov     r8d, esi; cbOutput
0x14003402f  call    cs:__imp_BCryptFinishHash
0x140034035  mov     ebx, eax
0x140034037  test    eax, eax
0x140034039  js      loc_140034138
0x14003403f  mov     rcx, [rbp+47h+phHash]; hHash
0x140034043  call    cs:__imp_BCryptDestroyHash
0x140034049  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x140034051  lea     rdx, [rbp+47h+hHash]; phHash
0x140034055  mov     [rsp+0E0h+cbSecret], 0; cbSecret
0x14003405d  lea     ecx, [rsi+31h]; hAlgorithm
0x140034060  xor     r9d, r9d; cbHashObject
0x140034063  mov     [rsp+0E0h+pbSecret], 0; pbSecret
0x14003406c  xor     r8d, r8d; pbHashObject
0x14003406f  mov     [rbp+47h+phHash], 0
0x140034077  call    cs:__imp_BCryptCreateHash
0x14003407d  mov     ebx, eax
0x14003407f  test    eax, eax
0x140034081  js      loc_140034138
0x140034087  mov     rcx, [rbp+47h+hHash]; hHash
0x14003408b  lea     r8d, [rsi-8]; cbInput
0x14003408f  xor     r9d, r9d; dwFlags
0x140034092  lea     rdx, pbInput; "NtlmStrongCredentialKey"
0x140034099  call    cs:__imp_BCryptHashData
0x14003409f  mov     ebx, eax
0x1400340a1  test    eax, eax
0x1400340a3  js      loc_140034138
0x1400340a9  mov     rcx, [rbp+47h+hHash]; hHash
0x1400340ad  xor     r9d, r9d; dwFlags
0x1400340b0  mov     r8d, r14d; cbInput
0x1400340b3  mov     rdx, r15; pbInput
0x1400340b6  call    cs:__imp_BCryptHashData
0x1400340bc  mov     ebx, eax
0x1400340be  test    eax, eax
0x1400340c0  js      short loc_140034138
0x1400340c2  mov     rcx, [rbp+47h+hHash]; hHash
0x1400340c6  lea     rdx, [rbp+47h+pbOutput]; pbInput
0x1400340ca  xor     r9d, r9d; dwFlags
0x1400340cd  mov     r8d, esi; cbInput
0x1400340d0  call    cs:__imp_BCryptHashData
0x1400340d6  mov     ebx, eax
0x1400340d8  test    eax, eax
0x1400340da  js      short loc_140034138
0x1400340dc  mov     rcx, [rbp+47h+hHash]; hHash
0x1400340e0  lea     rdx, [r13+26h]; pbInput
0x1400340e4  xor     r9d, r9d; dwFlags
0x1400340e7  lea     r8d, [rsi-10h]; cbInput
0x1400340eb  call    cs:__imp_BCryptHashData
0x1400340f1  mov     ebx, eax
0x1400340f3  test    eax, eax
0x1400340f5  js      short loc_140034138
0x1400340f7  mov     rcx, [rbp+47h+hHash]; hHash
0x1400340fb  lea     r8d, [rsi+10h]; cbOutput
0x1400340ff  xor     r9d, r9d; dwFlags
0x140034102  lea     rdx, [rbp+47h+var_70]; pbOutput
0x140034106  call    cs:__imp_BCryptFinishHash
0x14003410c  mov     ebx, eax
0x14003410e  test    eax, eax
0x140034110  js      short loc_140034138
0x140034112  mov     rcx, [rbp+47h+hHash]; hHash
0x140034116  call    cs:__imp_BCryptDestroyHash
0x14003411c  movups  xmm0, [rbp+47h+var_60+4]
0x140034120  mov     eax, dword ptr [rbp+47h+var_50+4]
0x140034123  xor     ecx, ecx
0x140034125  mov     [rbp+47h+hHash], rcx
0x140034129  movups  xmmword ptr [rdi+4], xmm0
0x14003412d  mov     [rdi+14h], eax
0x140034130  mov     dword ptr [rdi], 14h
0x140034136  jmp     short loc_14003413C
0x140034138  mov     rcx, [rbp+47h+hHash]; hHash
0x14003413c  test    rcx, rcx
0x14003413f  jz      short loc_140034147
0x140034141  call    cs:__imp_BCryptDestroyHash
0x140034147  mov     rcx, [rbp+47h+phHash]; hHash
0x14003414b  test    rcx, rcx
0x14003414e  jz      short loc_140034156
0x140034150  call    cs:__imp_BCryptDestroyHash
0x140034156  mov     eax, ebx
0x140034158  mov     rcx, [rbp+47h+var_40]
0x14003415c  xor     rcx, rsp; StackCookie
0x14003415f  call    __security_check_cookie
0x140034164  add     rsp, 0B0h
0x14003416b  pop     r15
0x14003416d  pop     r14
0x14003416f  pop     r13
0x140034171  pop     rdi
0x140034172  pop     rsi
0x140034173  pop     rbx
0x140034174  pop     rbp
0x140034175  retn
```
