# DnsGrantZtAccessToAllPrivateKeys

- ea: `0x18000c788`
- end: `0x18000c8a1`
- name: `DnsGrantZtAccessToAllPrivateKeys`
- size: `281`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800092d0`

## callees

- `0x18000bbbc`
- `0x18000bf64`
- `0x18000bfac`
- `0x18000c788`
- `0x180015008`

## import_xrefs

- `CRYPT32!CertFreeCertificateChainList` at `0x18000c88c`
- `CRYPT32!CertFreeCertificateChainList` at `0x18000c88c`

## pseudocode

```c
__int64 __fastcall DnsGrantZtAccessToAllPrivateKeys(__int64 a1)
{
  PCCERT_CHAIN_CONTEXT *v1; // rdi
  unsigned int v3; // ebx
  unsigned int CertChainContext; // eax
  __int64 i; // rsi
  PCERT_SIMPLE_CHAIN v6; // rdx
  unsigned int v7; // eax
  unsigned int v9; // [rsp+40h] [rbp+8h] BYREF
  PCCERT_CHAIN_CONTEXT *prgpSelection; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  prgpSelection = 0;
  v9 = 0;
  if ( a1 )
  {
    CertChainContext = GetCertChainContext(a1, &prgpSelection, &v9);
    v3 = CertChainContext;
    if ( CertChainContext )
    {
      if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
        WPP_SF_d(1035, 56, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, CertChainContext);
      v1 = prgpSelection;
    }
    else
    {
      v1 = prgpSelection;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= v9 )
        {
          v3 = 0;
          goto LABEL_20;
        }
        v6 = *v1[i]->rgpChain;
        if ( v6 )
        {
          if ( v6->cElement )
          {
            v7 = CertGrantAccessToMatchingCert(a1);
            v3 = v7;
            if ( v7 )
            {
              if ( v7 != 1168 && v7 != -2146893802 )
                break;
            }
          }
        }
      }
      if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
        goto LABEL_20;
      WPP_SF_d(1035, 57, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, v7);
    }
  }
  else
  {
    v3 = 87;
  }
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 58, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, v3);
LABEL_20:
  FreeCertChain(v1, v9);
  if ( v1 )
    CertFreeCertificateChainList(v1);
  return v3;
}

```

## disassembly

```asm
0x18000c788  mov     [rsp+arg_10], rbx
0x18000c78d  push    rbp
0x18000c78e  push    rsi
0x18000c78f  push    rdi
0x18000c790  sub     rsp, 20h
0x18000c794  xor     edi, edi
0x18000c796  mov     rbp, rcx
0x18000c799  mov     [rsp+38h+prgpSelection], rdi
0x18000c79e  mov     [rsp+38h+arg_0], edi
0x18000c7a2  test    rcx, rcx
0x18000c7a5  jnz     short loc_18000C7AF
0x18000c7a7  lea     ebx, [rcx+57h]
0x18000c7aa  jmp     loc_18000C856
0x18000c7af  lea     r8, [rsp+38h+arg_0]
0x18000c7b4  lea     rdx, [rsp+38h+prgpSelection]
0x18000c7b9  call    GetCertChainContext
0x18000c7be  mov     ebx, eax
0x18000c7c0  test    eax, eax
0x18000c7c2  jnz     short loc_18000C82F
0x18000c7c4  mov     rdi, [rsp+38h+prgpSelection]
0x18000c7c9  xor     esi, esi
0x18000c7cb  cmp     esi, [rsp+38h+arg_0]
0x18000c7cf  jnb     short loc_18000C82B
0x18000c7d1  mov     rcx, [rdi+rsi*8]
0x18000c7d5  mov     rax, [rcx+10h]
0x18000c7d9  mov     rdx, [rax]
0x18000c7dc  test    rdx, rdx
0x18000c7df  jz      short loc_18000C803
0x18000c7e1  cmp     dword ptr [rdx+0Ch], 0
0x18000c7e5  jz      short loc_18000C803
0x18000c7e7  mov     rcx, rbp
0x18000c7ea  call    CertGrantAccessToMatchingCert
0x18000c7ef  mov     ebx, eax
0x18000c7f1  test    eax, eax
0x18000c7f3  jz      short loc_18000C803
0x18000c7f5  cmp     eax, 490h
0x18000c7fa  jz      short loc_18000C803
0x18000c7fc  cmp     eax, 80090016h
0x18000c801  jnz     short loc_18000C807
0x18000c803  inc     esi
0x18000c805  jmp     short loc_18000C7CB
0x18000c807  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000c80e  jz      short loc_18000C878
0x18000c810  mov     edx, 39h ; '9'
0x18000c815  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000c81c  mov     ecx, 40Bh
0x18000c821  mov     r9d, eax
0x18000c824  call    WPP_SF_d
0x18000c829  jmp     short loc_18000C856
0x18000c82b  xor     ebx, ebx
0x18000c82d  jmp     short loc_18000C878
0x18000c82f  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000c836  jz      short loc_18000C851
0x18000c838  mov     edx, 38h ; '8'
0x18000c83d  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000c844  mov     ecx, 40Bh
0x18000c849  mov     r9d, eax
0x18000c84c  call    WPP_SF_d
0x18000c851  mov     rdi, [rsp+38h+prgpSelection]
0x18000c856  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000c85d  jz      short loc_18000C878
0x18000c85f  mov     edx, 3Ah ; ':'
0x18000c864  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000c86b  mov     ecx, 40Bh
0x18000c870  mov     r9d, ebx
0x18000c873  call    WPP_SF_d
0x18000c878  mov     edx, [rsp+38h+arg_0]
0x18000c87c  mov     rcx, rdi
0x18000c87f  call    FreeCertChain
0x18000c884  test    rdi, rdi
0x18000c887  jz      short loc_18000C892
0x18000c889  mov     rcx, rdi; prgpSelection
0x18000c88c  call    cs:__imp_CertFreeCertificateChainList
0x18000c892  mov     eax, ebx
0x18000c894  mov     rbx, [rsp+38h+arg_10]
0x18000c899  add     rsp, 20h
0x18000c89d  pop     rdi
0x18000c89e  pop     rsi
0x18000c89f  pop     rbp
0x18000c8a0  retn
```
