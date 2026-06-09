# TpmApiPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x180074fc0`
- end: `0x1800751e7`
- name: `?TpmApiPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `551`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002d518`
- `0x180074a1c`
- `0x180074a48`
- `0x180074fc0`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180075145`
- `bcrypt!BCryptCreateHash` at `0x180075145`
- `bcrypt!BCryptHashData` at `0x180075164`
- `bcrypt!BCryptHashData` at `0x180075164`
- `bcrypt!BCryptFinishHash` at `0x180075185`
- `bcrypt!BCryptFinishHash` at `0x180075185`
- `bcrypt!BCryptDestroyHash` at `0x18007519c`
- `bcrypt!BCryptDestroyHash` at `0x18007519c`
- `bcrypt!BCryptGetProperty` at `0x180075080`
- `bcrypt!BCryptGetProperty` at `0x1800750de`
- `bcrypt!BCryptGetProperty` at `0x180075080`
- `bcrypt!BCryptGetProperty` at `0x1800750de`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007503f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007503f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800751ca`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800751ca`

## pseudocode

```c
__int64 __fastcall TpmApiPlatformHash(
        LPCWSTR pszAlgId,
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbSecret,
        ULONG cbSecret,
        PUCHAR a6,
        ULONG cbOutput,
        unsigned int *a8,
        ULONG dwFlags)
{
  NTSTATUS Property; // ebx
  ULONG v13; // eax
  UCHAR v15[4]; // [rsp+40h] [rbp-38h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-34h] BYREF
  UCHAR pbOutput[8]; // [rsp+48h] [rbp-30h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-20h] BYREF
  PUCHAR pbHashObject[3]; // [rsp+60h] [rbp-18h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  pbHashObject[0] = 0;
  *(_DWORD *)v15 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  if ( (!cbOutput || a6) && a8 )
  {
    *a8 = 0;
    Property = BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, L"Microsoft Primitive Provider", dwFlags);
    if ( Property >= 0 )
    {
      pcbResult = 4;
      Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
      if ( Property >= 0 )
      {
        v13 = *(_DWORD *)pbOutput;
        *a8 = *(_DWORD *)pbOutput;
        if ( cbOutput )
        {
          if ( cbOutput >= v13 )
          {
            pcbResult = 4;
            Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", v15, 4u, &pcbResult, 0);
            if ( Property >= 0 )
            {
              if ( (unsigned int)TpmApiCallbackAlloc(-1, *(unsigned int *)v15, pbHashObject) )
              {
                Property = -1073741801;
              }
              else
              {
                memset_0(pbHashObject[0], 0, *(unsigned int *)v15);
                Property = BCryptCreateHash(phAlgorithm, &phHash, pbHashObject[0], *(ULONG *)v15, pbSecret, cbSecret, 0);
                if ( Property >= 0 )
                {
                  Property = BCryptHashData(phHash, pbInput, cbInput, 0);
                  if ( Property >= 0 )
                    Property = BCryptFinishHash(phHash, a6, cbOutput, 0);
                }
              }
            }
          }
          else
          {
            Property = -1073741789;
          }
        }
      }
    }
    if ( phHash )
      BCryptDestroyHash(phHash);
  }
  else
  {
    Property = -1073741811;
  }
  TpmApiCallbackFree(-1, *(unsigned int *)v15, pbHashObject[0]);
  *(_DWORD *)v15 = 0;
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180074fc0  push    rbp
0x180074fc2  push    rbx
0x180074fc3  push    rsi
0x180074fc4  push    r12
0x180074fc6  push    r13
0x180074fc8  push    r15
0x180074fca  mov     rbp, rsp
0x180074fcd  sub     rsp, 78h
0x180074fd1  cmp     [rbp+cbOutput], 0
0x180074fd5  mov     r13, r9
0x180074fd8  mov     r15d, r8d
0x180074fdb  mov     [rbp+phAlgorithm], 0
0x180074fe3  mov     r12, rdx
0x180074fe6  mov     [rbp+phHash], 0
0x180074fee  mov     [rbp+pbHashObject], 0
0x180074ff6  mov     dword ptr [rbp+var_38], 0
0x180074ffd  mov     dword ptr [rbp+pbOutput], 0
0x180075004  mov     [rbp+var_34], 0
0x18007500b  jz      short loc_180075014
0x18007500d  cmp     [rbp+arg_28], 0
0x180075012  jz      short loc_18007501D
0x180075014  mov     rsi, [rbp+arg_38]
0x180075018  test    rsi, rsi
0x18007501b  jnz     short loc_180075027
0x18007501d  mov     ebx, 0C000000Dh
0x180075022  jmp     loc_1800751A8
0x180075027  mov     r9d, [rbp+dwFlags]; dwFlags
0x18007502b  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180075032  mov     rdx, rcx; pszAlgId
0x180075035  mov     dword ptr [rsi], 0
0x18007503b  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18007503f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180075046  nop     dword ptr [rax+rax+00h]
0x18007504b  mov     ebx, eax
0x18007504d  test    eax, eax
0x18007504f  js      loc_180075193
0x180075055  mov     ecx, 4
0x18007505a  mov     [rsp+78h+cbSecret], 0; dwFlags
0x180075062  mov     [rbp+var_34], ecx
0x180075065  lea     rax, [rbp+var_34]
0x180075069  mov     r9d, ecx; cbOutput
0x18007506c  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180075071  mov     rcx, [rbp+phAlgorithm]; hObject
0x180075075  lea     r8, [rbp+pbOutput]; pbOutput
0x180075079  lea     rdx, pszProperty; "HashDigestLength"
0x180075080  call    cs:__imp_BCryptGetProperty
0x180075087  nop     dword ptr [rax+rax+00h]
0x18007508c  mov     ebx, eax
0x18007508e  test    eax, eax
0x180075090  js      loc_180075193
0x180075096  cmp     [rbp+cbOutput], 0
0x18007509a  mov     eax, dword ptr [rbp+pbOutput]
0x18007509d  mov     [rsi], eax
0x18007509f  jz      loc_180075193
0x1800750a5  cmp     [rbp+cbOutput], eax
0x1800750a8  jnb     short loc_1800750B4
0x1800750aa  mov     ebx, 0C0000023h
0x1800750af  jmp     loc_180075193
0x1800750b4  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800750b8  lea     rax, [rbp+var_34]
0x1800750bc  mov     r9d, 4; cbOutput
0x1800750c2  mov     [rsp+78h+cbSecret], 0; dwFlags
0x1800750ca  lea     r8, [rbp+var_38]; pbOutput
0x1800750ce  mov     [rbp+var_34], r9d
0x1800750d2  lea     rdx, aObjectlength; "ObjectLength"
0x1800750d9  mov     [rsp+78h+pcbResult], rax; pcbResult
0x1800750de  call    cs:__imp_BCryptGetProperty
0x1800750e5  nop     dword ptr [rax+rax+00h]
0x1800750ea  mov     ebx, eax
0x1800750ec  test    eax, eax
0x1800750ee  js      loc_180075193
0x1800750f4  mov     edx, dword ptr [rbp+var_38]
0x1800750f7  lea     r8, [rbp+pbHashObject]
0x1800750fb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800750ff  call    TpmApiCallbackAlloc
0x180075104  test    eax, eax
0x180075106  jz      short loc_180075112
0x180075108  mov     ebx, 0C0000017h
0x18007510d  jmp     loc_180075193
0x180075112  mov     r8d, dword ptr [rbp+var_38]; Size
0x180075116  xor     edx, edx; Val
0x180075118  mov     rcx, [rbp+pbHashObject]; void *
0x18007511c  call    memset_0
0x180075121  mov     eax, [rbp+arg_20]
0x180075124  lea     rdx, [rbp+phHash]; phHash
0x180075128  mov     r9d, dword ptr [rbp+var_38]; cbHashObject
0x18007512c  mov     r8, [rbp+pbHashObject]; pbHashObject
0x180075130  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180075134  mov     [rsp+78h+var_48], 0; dwFlags
0x18007513c  mov     [rsp+78h+cbSecret], eax; cbSecret
0x180075140  mov     [rsp+78h+pcbResult], r13; pbSecret
0x180075145  call    cs:__imp_BCryptCreateHash
0x18007514c  nop     dword ptr [rax+rax+00h]
0x180075151  mov     ebx, eax
0x180075153  test    eax, eax
0x180075155  js      short loc_180075193
0x180075157  mov     rcx, [rbp+phHash]; hHash
0x18007515b  xor     r9d, r9d; dwFlags
0x18007515e  mov     r8d, r15d; cbInput
0x180075161  mov     rdx, r12; pbInput
0x180075164  call    cs:__imp_BCryptHashData
0x18007516b  nop     dword ptr [rax+rax+00h]
0x180075170  mov     ebx, eax
0x180075172  test    eax, eax
0x180075174  js      short loc_180075193
0x180075176  mov     r8d, [rbp+cbOutput]; cbOutput
0x18007517a  xor     r9d, r9d; dwFlags
0x18007517d  mov     rdx, [rbp+arg_28]; pbOutput
0x180075181  mov     rcx, [rbp+phHash]; hHash
0x180075185  call    cs:__imp_BCryptFinishHash
0x18007518c  nop     dword ptr [rax+rax+00h]
0x180075191  mov     ebx, eax
0x180075193  mov     rcx, [rbp+phHash]; hHash
0x180075197  test    rcx, rcx
0x18007519a  jz      short loc_1800751A8
0x18007519c  call    cs:__imp_BCryptDestroyHash
0x1800751a3  nop     dword ptr [rax+rax+00h]
0x1800751a8  mov     r8, [rbp+pbHashObject]
0x1800751ac  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800751b0  mov     edx, dword ptr [rbp+var_38]
0x1800751b3  call    TpmApiCallbackFree
0x1800751b8  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800751bc  mov     dword ptr [rbp+var_38], 0
0x1800751c3  test    rcx, rcx
0x1800751c6  jz      short loc_1800751D6
0x1800751c8  xor     edx, edx; dwFlags
0x1800751ca  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800751d1  nop     dword ptr [rax+rax+00h]
0x1800751d6  mov     eax, ebx
0x1800751d8  add     rsp, 78h
0x1800751dc  pop     r15
0x1800751de  pop     r13
0x1800751e0  pop     r12
0x1800751e2  pop     rsi
0x1800751e3  pop     rbx
0x1800751e4  pop     rbp
0x1800751e5  retn
```
