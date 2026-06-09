# GetSecretAgreementInterface

- ea: `0x18004be20`
- end: `0x18004beeb`
- name: `GetSecretAgreementInterface`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18004be20`
- `0x18007f765`

## string_xrefs

- `0x18004becc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\msprim\interface.c`

## pseudocode

```c
__int64 __fastcall GetSecretAgreementInterface(__int64 a1, const wchar_t *a2, __int64 **a3)
{
  int v5; // r9d
  __int64 *v6; // rax
  unsigned int v7; // ebx

  v5 = *a2 - 68;
  if ( *a2 == 68 )
  {
    v5 = a2[1] - 72;
    if ( a2[1] == 72 )
      v5 = a2[2];
  }
  if ( v5 )
  {
    if ( wcscmp_0(a2, L"ECDH") && wcscmp_0(a2, L"ECDH_P256") && wcscmp_0(a2, L"ECDH_P384") && wcscmp_0(a2, L"ECDH_P521") )
    {
      v7 = -1073741637;
      DebugTraceError(
        3221225659LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\msprim\\interface.c",
        135);
      return v7;
    }
    v6 = &MSECDHSecretAgreementTable;
  }
  else
  {
    v6 = &MSDHSecretAgreementTable;
  }
  *a3 = v6;
  return 0;
}

```

## disassembly

```asm
0x18004be20  mov     [rsp+arg_0], rbx
0x18004be25  push    rdi
0x18004be26  sub     rsp, 20h
0x18004be2a  movzx   r9d, word ptr [rdx]
0x18004be2e  mov     rdi, r8
0x18004be31  mov     rbx, rdx
0x18004be34  sub     r9d, 44h ; 'D'
0x18004be38  jnz     short loc_18004BE52
0x18004be3a  movzx   r9d, word ptr [rdx+2]
0x18004be3f  sub     r9d, 48h ; 'H'
0x18004be43  jnz     short loc_18004BE52
0x18004be45  movzx   r9d, word ptr [rdx+4]
0x18004be4a  xor     eax, eax
0x18004be4c  movzx   ecx, ax
0x18004be4f  sub     r9d, ecx
0x18004be52  test    r9d, r9d
0x18004be55  jz      short loc_18004BE84
0x18004be57  lea     rdx, aEcdh; "ECDH"
0x18004be5e  mov     rcx, rbx; String1
0x18004be61  call    wcscmp_0
0x18004be66  test    eax, eax
0x18004be68  jnz     short loc_18004BE8D
0x18004be6a  lea     rax, MSECDHSecretAgreementTable
0x18004be71  mov     [rdi], rax
0x18004be74  xor     ebx, ebx
0x18004be76  mov     eax, ebx
0x18004be78  mov     rbx, [rsp+28h+arg_0]
0x18004be7d  add     rsp, 20h
0x18004be81  pop     rdi
0x18004be82  retn
0x18004be84  lea     rax, MSDHSecretAgreementTable
0x18004be8b  jmp     short loc_18004BE71
0x18004be8d  lea     rdx, aEcdhP256; "ECDH_P256"
0x18004be94  mov     rcx, rbx; String1
0x18004be97  call    wcscmp_0
0x18004be9c  test    eax, eax
0x18004be9e  jz      short loc_18004BE6A
0x18004bea0  lea     rdx, aEcdhP384; "ECDH_P384"
0x18004bea7  mov     rcx, rbx; String1
0x18004beaa  call    wcscmp_0
0x18004beaf  test    eax, eax
0x18004beb1  jz      short loc_18004BE6A
0x18004beb3  lea     rdx, aEcdhP521; "ECDH_P521"
0x18004beba  mov     rcx, rbx; String1
0x18004bebd  call    wcscmp_0
0x18004bec2  test    eax, eax
0x18004bec4  jz      short loc_18004BE6A
0x18004bec6  mov     r9d, 87h
0x18004becc  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004bed3  lea     rdx, aStatus; "Status"
0x18004beda  mov     ecx, 0C00000BBh
0x18004bedf  mov     ebx, 0C00000BBh
0x18004bee4  call    DebugTraceError
0x18004bee9  jmp     short loc_18004BE76
```
