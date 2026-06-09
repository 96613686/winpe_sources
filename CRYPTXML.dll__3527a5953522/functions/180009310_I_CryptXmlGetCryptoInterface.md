# I_CryptXmlGetCryptoInterface

- ea: `0x180009310`
- end: `0x180009470`
- name: `I_CryptXmlGetCryptoInterface`
- size: `352`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009180`
- `0x1800094a0`
- `0x18000b3b0`

## callees

- `0x180009310`
- `0x18000f200`
- `0x180014ce0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000937e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800093e0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000937e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800093e0`

## string_xrefs

- `0x18000941c`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlGetCryptoInterface(__int64 a1, int a2, _QWORD *a3)
{
  __int64 i; // rbx
  __int64 result; // rax
  __int64 j; // rbx
  const char *v9; // r8
  char v10; // dl
  const char *v11; // r9
  bool v12; // zf

  v12 = dword_180022FC8 == 0;
  *a3 = 0;
  if ( v12 )
    LoadRegExtensions();
  if ( (a2 & 0x10000000) == 0 )
  {
    for ( i = 0; (unsigned int)i < dword_180022FC0; i = (unsigned int)(i + 1) )
    {
      if ( CompareStringW(0, 1u, *(PCNZWCH *)(a1 + 8), -1, *(PCNZWCH *)(*((_QWORD *)qword_180022FD8 + i) + 8LL), -1) == 2 )
      {
        result = 0;
        *a3 = *((_QWORD *)qword_180022FD8 + i) + 88LL;
        return result;
      }
    }
  }
  for ( j = 0; (unsigned int)j < 0x11; j = (unsigned int)(j + 1) )
  {
    if ( CompareStringW(0, 1u, *(PCNZWCH *)(a1 + 8), -1, off_180022188[9 * j], -1) == 2 )
    {
      *a3 = &g_CryptXmlCNG;
      return 0;
    }
  }
  v9 = "";
  while ( 1 )
  {
    v10 = *(v9 - 1);
    v11 = v9--;
    v12 = v10 == 92;
    if ( v10 == 92 )
      break;
    if ( v9 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp" )
    {
      v12 = v10 == 92;
      break;
    }
  }
  if ( v12 )
    v9 = v11;
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %S", -2146885372, v9, 1712, *(const wchar_t **)(a1 + 8));
  return 2148081924LL;
}

```

## disassembly

```asm
0x180009310  push    rbx
0x180009312  push    rbp
0x180009313  push    rdi
0x180009314  push    r14
0x180009316  sub     rsp, 38h
0x18000931a  xor     ebp, ebp
0x18000931c  mov     r14, r8
0x18000931f  cmp     cs:dword_180022FC8, ebp
0x180009325  mov     ebx, edx
0x180009327  mov     rdi, rcx
0x18000932a  mov     [r8], rbp
0x18000932d  jnz     short loc_180009334
0x18000932f  call    _LoadRegExtensions
0x180009334  mov     [rsp+58h+arg_0], rsi
0x180009339  bt      ebx, 1Ch
0x18000933d  jb      short loc_1800093AC
0x18000933f  xor     ebx, ebx
0x180009341  cmp     ebx, cs:dword_180022FC0
0x180009347  jnb     short loc_1800093AC
0x180009349  mov     rax, cs:qword_180022FD8
0x180009350  lea     rsi, ds:0[rbx*8]
0x180009358  mov     r8, [rdi+8]; lpString1
0x18000935c  mov     r9d, 0FFFFFFFFh; cchCount1
0x180009362  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000936a  mov     edx, 1; dwCmpFlags
0x18000936f  xor     ecx, ecx; Locale
0x180009371  mov     rax, [rsi+rax]
0x180009375  mov     rax, [rax+8]
0x180009379  mov     [rsp+58h+lpString2], rax; lpString2
0x18000937e  call    cs:__imp_CompareStringW
0x180009385  nop     dword ptr [rax+rax+00h]
0x18000938a  cmp     eax, 2
0x18000938d  jz      short loc_180009393
0x18000938f  inc     ebx
0x180009391  jmp     short loc_180009341
0x180009393  mov     rcx, cs:qword_180022FD8
0x18000939a  mov     eax, ebp
0x18000939c  mov     rdx, [rsi+rcx]
0x1800093a0  add     rdx, 58h ; 'X'
0x1800093a4  mov     [r14], rdx
0x1800093a7  jmp     loc_180009460
0x1800093ac  xor     ebx, ebx
0x1800093ae  lea     rsi, off_180022188; "http://www.w3.org/2000/09/xmldsig#sha1"
0x1800093b5  cmp     ebx, 11h
0x1800093b8  jnb     short loc_180009411
0x1800093ba  mov     r8, [rdi+8]; lpString1
0x1800093be  lea     rax, [rbx+rbx*8]
0x1800093c2  mov     rax, [rsi+rax*8]
0x1800093c6  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800093cc  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800093d4  mov     edx, 1; dwCmpFlags
0x1800093d9  xor     ecx, ecx; Locale
0x1800093db  mov     [rsp+58h+lpString2], rax; lpString2
0x1800093e0  call    cs:__imp_CompareStringW
0x1800093e7  nop     dword ptr [rax+rax+00h]
0x1800093ec  cmp     eax, 2
0x1800093ef  jz      short loc_1800093F5
0x1800093f1  inc     ebx
0x1800093f3  jmp     short loc_1800093B5
0x1800093f5  lea     rax, ?g_CryptXmlCNG@@3U_CRYPT_XML_CRYPTOGRAPHIC_INTERFACE@@A; "H"
0x1800093fc  mov     [r14], rax
0x1800093ff  mov     eax, ebp
0x180009401  mov     rsi, [rsp+58h+arg_0]
0x180009406  add     rsp, 38h
0x18000940a  pop     r14
0x18000940c  pop     rdi
0x18000940d  pop     rbp
0x18000940e  pop     rbx
0x18000940f  retn
0x180009411  mov     rcx, [rdi+8]
0x180009415  lea     r8, aOnecoreDsSecur_6+30h; ""
0x18000941c  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180009423  movzx   edx, byte ptr [r8-1]
0x180009428  mov     r9, r8
0x18000942b  dec     r8
0x18000942e  cmp     dl, 5Ch ; '\'
0x180009431  jz      short loc_18000943B
0x180009433  cmp     r8, rax
0x180009436  ja      short loc_180009423
0x180009438  cmp     dl, 5Ch ; '\'
0x18000943b  cmovz   r8, r9
0x18000943f  mov     [rsp+58h+lpString2], rcx
0x180009444  mov     r9d, 6B0h
0x18000944a  lea     rcx, aError0x08xSUS_0; "ERROR  : (0x%08x) %s:%u : %S"
0x180009451  mov     edx, 80092104h
0x180009456  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000945b  mov     eax, 80092104h
0x180009460  mov     rsi, [rsp+58h+arg_0]
0x180009465  add     rsp, 38h
0x180009469  pop     r14
0x18000946b  pop     rdi
0x18000946c  pop     rbp
0x18000946d  pop     rbx
0x18000946e  retn
```
