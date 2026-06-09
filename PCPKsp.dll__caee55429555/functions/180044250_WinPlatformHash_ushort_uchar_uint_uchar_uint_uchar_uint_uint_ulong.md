# WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x180044250`
- end: `0x1800444b3`
- name: `?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `611`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180044250`
- `0x1800769e0`
- `0x180076e70`
- `0x18007704c`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1800443ff`
- `bcrypt!BCryptFinishHash` at `0x1800443ff`
- `bcrypt!BCryptCreateHash` at `0x1800443bf`
- `bcrypt!BCryptCreateHash` at `0x1800443bf`
- `bcrypt!BCryptGetProperty` at `0x180044305`
- `bcrypt!BCryptGetProperty` at `0x18004435e`
- `bcrypt!BCryptGetProperty` at `0x180044305`
- `bcrypt!BCryptGetProperty` at `0x18004435e`
- `bcrypt!BCryptHashData` at `0x1800443df`
- `bcrypt!BCryptHashData` at `0x1800443df`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180044467`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180044467`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800442c1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800442c1`
- `bcrypt!BCryptDestroyHash` at `0x18004441d`
- `bcrypt!BCryptDestroyHash` at `0x18004441d`

## pseudocode

```c
__int64 __fastcall WinPlatformHash(
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
  NTSTATUS Property; // r13d
  ULONG v13; // eax
  void *v14; // rdi
  __int64 v15; // rdx
  _BYTE *v16; // rax
  UCHAR v18[4]; // [rsp+40h] [rbp-30h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-2Ch] BYREF
  UCHAR pbOutput[8]; // [rsp+48h] [rbp-28h] BYREF
  void *v21; // [rsp+50h] [rbp-20h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp-10h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  *(_DWORD *)v18 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  if ( cbOutput && !a6 || !a8 )
    return 2147942487LL;
  v21 = 0;
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
        if ( cbOutput < v13 )
        {
          Property = -1073741789;
        }
        else
        {
          pcbResult = 4;
          Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", v18, 4u, &pcbResult, 0);
          if ( Property >= 0 )
          {
            v14 = operator new(*(unsigned int *)v18);
            memset_0(v14, 0, *(unsigned int *)v18);
            memset_0(v14, 0, *(unsigned int *)v18);
            Property = BCryptCreateHash(phAlgorithm, &phHash, (PUCHAR)v14, *(ULONG *)v18, pbSecret, cbSecret, 0);
            if ( Property >= 0 )
            {
              Property = BCryptHashData(phHash, pbInput, cbInput, 0);
              if ( Property >= 0 )
                Property = BCryptFinishHash(phHash, a6, cbOutput, 0);
            }
            goto LABEL_12;
          }
        }
      }
    }
  }
  v14 = v21;
LABEL_12:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v14 )
  {
    v15 = *(unsigned int *)v18;
    v16 = v14;
    if ( *(_DWORD *)v18 )
    {
      do
      {
        *v16++ = 0;
        --v15;
      }
      while ( v15 );
    }
    operator delete(v14);
  }
  *(_DWORD *)v18 = 0;
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180044250  mov     [rsp-28h+arg_8], rbx
0x180044255  mov     [rsp-28h+arg_10], rsi
0x18004425a  push    rbp
0x18004425b  push    rdi
0x18004425c  push    r12
0x18004425e  push    r14
0x180044260  push    r15
0x180044262  mov     rbp, rsp
0x180044265  sub     rsp, 70h
0x180044269  mov     ebx, [rbp+cbOutput]
0x18004426c  xor     eax, eax
0x18004426e  mov     rsi, [rbp+arg_28]
0x180044272  mov     r12, r9
0x180044275  mov     [rbp+phAlgorithm], rax
0x180044279  mov     r14d, r8d
0x18004427c  mov     [rbp+phHash], rax
0x180044280  mov     r15, rdx
0x180044283  mov     dword ptr [rbp+var_30], eax
0x180044286  mov     dword ptr [rbp+pbOutput], eax
0x180044289  mov     [rbp+var_2C], eax
0x18004428c  test    ebx, ebx
0x18004428e  jnz     loc_180044498
0x180044294  mov     rdi, [rbp+arg_38]
0x180044298  test    rdi, rdi
0x18004429b  jz      loc_1800444A1
0x1800442a1  mov     r9d, [rbp+dwFlags]; dwFlags
0x1800442a5  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800442ac  mov     rdx, rcx; pszAlgId
0x1800442af  mov     [rsp+70h+arg_0], r13
0x1800442b7  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800442bb  mov     [rbp+var_20], rax
0x1800442bf  mov     [rdi], eax
0x1800442c1  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800442c8  nop     dword ptr [rax+rax+00h]
0x1800442cd  mov     r13d, eax
0x1800442d0  test    eax, eax
0x1800442d2  js      loc_180044410
0x1800442d8  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800442dc  lea     rax, [rbp+var_2C]
0x1800442e0  mov     [rsp+70h+cbSecret], 0; dwFlags
0x1800442e8  lea     r8, [rbp+pbOutput]; pbOutput
0x1800442ec  mov     r9d, 4; cbOutput
0x1800442f2  mov     [rsp+70h+pcbResult], rax; pcbResult
0x1800442f7  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800442fe  mov     [rbp+var_2C], 4
0x180044305  call    cs:__imp_BCryptGetProperty
0x18004430c  nop     dword ptr [rax+rax+00h]
0x180044311  mov     r13d, eax
0x180044314  test    eax, eax
0x180044316  js      loc_180044410
0x18004431c  mov     eax, dword ptr [rbp+pbOutput]
0x18004431f  mov     [rdi], eax
0x180044321  test    ebx, ebx
0x180044323  jz      loc_180044410
0x180044329  cmp     ebx, eax
0x18004432b  jb      loc_1800444A8
0x180044331  mov     rcx, [rbp+phAlgorithm]; hObject
0x180044335  lea     rax, [rbp+var_2C]
0x180044339  mov     [rsp+70h+cbSecret], 0; dwFlags
0x180044341  lea     r8, [rbp+var_30]; pbOutput
0x180044345  mov     r9d, 4; cbOutput
0x18004434b  mov     [rsp+70h+pcbResult], rax; pcbResult
0x180044350  lea     rdx, aObjectlength; "ObjectLength"
0x180044357  mov     [rbp+var_2C], 4
0x18004435e  call    cs:__imp_BCryptGetProperty
0x180044365  nop     dword ptr [rax+rax+00h]
0x18004436a  mov     r13d, eax
0x18004436d  test    eax, eax
0x18004436f  js      loc_180044410
0x180044375  mov     ecx, dword ptr [rbp+var_30]; Size
0x180044378  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004437d  mov     r8d, dword ptr [rbp+var_30]; Size
0x180044381  xor     edx, edx; Val
0x180044383  mov     rcx, rax; void *
0x180044386  mov     rdi, rax
0x180044389  call    memset_0
0x18004438e  mov     r8d, dword ptr [rbp+var_30]; Size
0x180044392  xor     edx, edx; Val
0x180044394  mov     rcx, rdi; void *
0x180044397  call    memset_0
0x18004439c  mov     eax, [rbp+arg_20]
0x18004439f  lea     rdx, [rbp+phHash]; phHash
0x1800443a3  mov     r9d, dword ptr [rbp+var_30]; cbHashObject
0x1800443a7  mov     r8, rdi; pbHashObject
0x1800443aa  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800443ae  mov     [rsp+70h+var_40], 0; dwFlags
0x1800443b6  mov     [rsp+70h+cbSecret], eax; cbSecret
0x1800443ba  mov     [rsp+70h+pcbResult], r12; pbSecret
0x1800443bf  call    cs:__imp_BCryptCreateHash
0x1800443c6  nop     dword ptr [rax+rax+00h]
0x1800443cb  mov     r13d, eax
0x1800443ce  test    eax, eax
0x1800443d0  js      short loc_180044414
0x1800443d2  mov     rcx, [rbp+phHash]; hHash
0x1800443d6  xor     r9d, r9d; dwFlags
0x1800443d9  mov     r8d, r14d; cbInput
0x1800443dc  mov     rdx, r15; pbInput
0x1800443df  call    cs:__imp_BCryptHashData
0x1800443e6  nop     dword ptr [rax+rax+00h]
0x1800443eb  mov     r13d, eax
0x1800443ee  test    eax, eax
0x1800443f0  js      short loc_180044414
0x1800443f2  mov     rcx, [rbp+phHash]; hHash
0x1800443f6  xor     r9d, r9d; dwFlags
0x1800443f9  mov     r8d, ebx; cbOutput
0x1800443fc  mov     rdx, rsi; pbOutput
0x1800443ff  call    cs:__imp_BCryptFinishHash
0x180044406  nop     dword ptr [rax+rax+00h]
0x18004440b  mov     r13d, eax
0x18004440e  jmp     short loc_180044414
0x180044410  mov     rdi, [rbp+var_20]
0x180044414  mov     rcx, [rbp+phHash]; hHash
0x180044418  test    rcx, rcx
0x18004441b  jz      short loc_180044429
0x18004441d  call    cs:__imp_BCryptDestroyHash
0x180044424  nop     dword ptr [rax+rax+00h]
0x180044429  test    rdi, rdi
0x18004442c  jz      short loc_180044455
0x18004442e  mov     edx, dword ptr [rbp+var_30]
0x180044431  mov     rax, rdi
0x180044434  test    rdx, rdx
0x180044437  jz      short loc_18004444D
0x180044439  nop     dword ptr [rax+00000000h]
0x180044440  mov     byte ptr [rax], 0
0x180044443  lea     rax, [rax+1]
0x180044447  sub     rdx, 1
0x18004444b  jnz     short loc_180044440
0x18004444d  mov     rcx, rdi; Block
0x180044450  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180044455  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180044459  mov     dword ptr [rbp+var_30], 0
0x180044460  test    rcx, rcx
0x180044463  jz      short loc_180044473
0x180044465  xor     edx, edx; dwFlags
0x180044467  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18004446e  nop     dword ptr [rax+rax+00h]
0x180044473  mov     eax, r13d
0x180044476  mov     r13, [rsp+70h+arg_0]
0x18004447e  lea     r11, [rsp+70h+var_s0]
0x180044483  mov     rbx, [r11+38h]
0x180044487  mov     rsi, [r11+40h]
0x18004448b  mov     rsp, r11
0x18004448e  pop     r15
0x180044490  pop     r14
0x180044492  pop     r12
0x180044494  pop     rdi
0x180044495  pop     rbp
0x180044496  retn
0x180044498  test    rsi, rsi
0x18004449b  jnz     loc_180044294
0x1800444a1  mov     eax, 80070057h
0x1800444a6  jmp     short loc_18004447E
0x1800444a8  mov     r13d, 0C0000023h
0x1800444ae  jmp     loc_180044410
```
