# I_ReaderListPopulateCredsViaContainerEnumeration

- ea: `0x180017954`
- end: `0x180017d9f`
- name: `I_ReaderListPopulateCredsViaContainerEnumeration`
- size: `1099`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18001317c`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x180015c10`
- `0x180017954`
- `0x180018edc`
- `0x18001ca98`
- `0x18001cc6c`
- `0x18001dd7c`
- `0x18001e020`
- `0x18001e0e0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017d38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017d38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a0e`
- `ntdll!RtlInitAnsiString` at `0x180017ade`
- `ntdll!RtlInitAnsiString` at `0x180017ade`
- `ntdll!RtlFreeUnicodeString` at `0x180017aac`
- `ntdll!RtlFreeUnicodeString` at `0x180017d04`
- `ntdll!RtlFreeUnicodeString` at `0x180017aac`
- `ntdll!RtlFreeUnicodeString` at `0x180017d04`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180017aef`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180017aef`
- `ntdll!RtlNtStatusToDosError` at `0x180017cc3`
- `ntdll!RtlNtStatusToDosError` at `0x180017cc3`
- `CRYPT32!CertCloseStore` at `0x180017ced`
- `CRYPT32!CertCloseStore` at `0x180017ced`
- `CRYPT32!CertOpenStore` at `0x1800179fc`
- `CRYPT32!CertOpenStore` at `0x1800179fc`

## pseudocode

```c
__int64 __fastcall I_ReaderListPopulateCredsViaContainerEnumeration(__int64 a1, __int64 a2, _DWORD *a3)
{
  char *v4; // r14
  wchar_t *p_SourceString; // rbx
  HCERTSTORE v8; // rax
  unsigned int ContainerData; // edi
  const char *i; // rsi
  NTSTATUS v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdi
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  wchar_t *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  wchar_t *v24; // rcx
  __int64 v26; // [rsp+0h] [rbp-30h] BYREF
  PCSZ SourceString; // [rsp+30h] [rbp+0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp+8h] BYREF
  struct _STRING DestinationString; // [rsp+48h] [rbp+18h] BYREF

  SourceString = 0;
  DestinationString = 0;
  v4 = 0;
  p_SourceString = 0;
  UnicodeString = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  *a3 = 0;
  DestinationString = 0;
  UnicodeString = 0;
  v8 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
  *(_QWORD *)(a2 + 168) = v8;
  if ( v8 )
  {
    ContainerData = I_ReaderListBuildContainerList((__int64 *)a2, (const void **)&SourceString);
    if ( ContainerData )
    {
      WppTraceIndent(0, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          95,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          ContainerData);
      }
      v4 = (char *)SourceString;
    }
    else
    {
      if ( *(_DWORD *)(a1 + 16) )
        *(_DWORD *)(a2 + 148) = 1;
      v4 = (char *)SourceString;
      for ( i = SourceString; i && *i; i += v23 + 1 )
      {
        if ( UnicodeString.Buffer )
        {
          RtlFreeUnicodeString(&UnicodeString);
          UnicodeString.Buffer = 0;
        }
        if ( p_SourceString )
        {
          if ( *((_DWORD *)p_SourceString - 2) == 1885431112 )
            ((void (*)(void))g_pfnFree)();
          p_SourceString = 0;
        }
        RtlInitAnsiString(&DestinationString, i);
        v11 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
        if ( v11 )
        {
          ContainerData = RtlNtStatusToDosError(v11);
          break;
        }
        v13 = -1;
        do
          ++v13;
        while ( UnicodeString.Buffer[v13] );
        v14 = 2 * v13 + 2;
        p_SourceString = 0;
        if ( !v14 )
          goto LABEL_35;
        if ( v14 > g_ulMaxStackAllocSize )
          goto LABEL_35;
        v15 = v14 + g_ulAdditionalProbeSize + 8;
        if ( v15 < v14 || !(unsigned int)VerifyStackAvailable(v15, v12) )
          goto LABEL_35;
        v16 = v14 + 23;
        if ( v14 + 23 <= v14 + 8 )
          v16 = 0xFFFFFFFFFFFFFF0LL;
        v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
        v18 = alloca(v17);
        v19 = alloca(v17);
        p_SourceString = (wchar_t *)&SourceString;
        if ( &v26 == (__int64 *)-48LL
          || (LODWORD(SourceString) = 1801679955, (p_SourceString = (wchar_t *)&UnicodeString) == 0) )
        {
LABEL_35:
          v17 = v14 + 8;
          if ( v14 + 8 >= v14 )
          {
            v20 = (wchar_t *)((__int64 (__fastcall *)(unsigned __int64, __int64, _QWORD))g_pfnAllocate)(v17, v12, 0);
            p_SourceString = v20;
            if ( v20 )
            {
              *(_DWORD *)v20 = 1885431112;
              p_SourceString = v20 + 4;
            }
          }
        }
        if ( !p_SourceString )
        {
          WppTraceIndent(v17, 2);
          ContainerData = 8;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              96,
              &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
              WPP_pszIndent);
          }
          break;
        }
        v21 = -1;
        do
          ++v21;
        while ( UnicodeString.Buffer[v21] );
        if ( StringCchCopyW(p_SourceString, v21 + 1, UnicodeString.Buffer) < 0 )
        {
          ContainerData = 122;
          break;
        }
        ContainerData = I_ReaderListReadContainerData(a1, a2, p_SourceString, a3);
        if ( ContainerData == 8 )
        {
          WppTraceIndent(v22, 2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              97,
              (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
              WPP_pszIndent,
              8);
          }
          break;
        }
        ContainerData = 0;
        v23 = -1;
        do
          ++v23;
        while ( i[v23] );
      }
    }
  }
  else
  {
    ContainerData = GetLastError();
  }
  v24 = *(wchar_t **)(a2 + 168);
  if ( v24 && (ContainerData || !*a3) )
  {
    CertCloseStore(v24, 0);
    *(_QWORD *)(a2 + 168) = 0;
  }
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( p_SourceString )
  {
    v24 = p_SourceString - 4;
    if ( *((_DWORD *)p_SourceString - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  if ( v4 )
    HeapFree(hHeap, 0, v4);
  WppTraceIndent(v24, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      98,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      ContainerData);
  }
  return ContainerData;
}

```

## disassembly

```asm
0x180017954  push    rbp
0x180017956  push    rbx
0x180017957  push    rsi
0x180017958  push    rdi
0x180017959  push    r12
0x18001795b  push    r13
0x18001795d  push    r14
0x18001795f  push    r15
0x180017961  sub     rsp, 68h
0x180017965  lea     rbp, [rsp+30h]
0x18001796a  mov     rax, cs:__security_cookie
0x180017971  xor     rax, rbp
0x180017974  mov     [rbp+70h+var_48], rax
0x180017978  xor     edi, edi
0x18001797a  mov     r15, rdx
0x18001797d  xorps   xmm0, xmm0
0x180017980  mov     [rbp+70h+SourceString], rdi
0x180017984  xorps   xmm1, xmm1
0x180017987  xor     edx, edx
0x180017989  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x18001798d  mov     r14d, edi
0x180017990  mov     ebx, edi
0x180017992  movups  xmmword ptr [rbp+70h+UnicodeString.Length], xmm1
0x180017996  mov     r13, r8
0x180017999  mov     r12, rcx
0x18001799c  call    WppTraceIndent
0x1800179a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179a8  lea     rsi, WPP_GLOBAL_Control
0x1800179af  cmp     rcx, rsi
0x1800179b2  jz      short loc_1800179DA
0x1800179b4  test    byte ptr [rcx+1Ch], 2
0x1800179b8  jz      short loc_1800179DA
0x1800179ba  cmp     byte ptr [rcx+19h], 5
0x1800179be  jb      short loc_1800179DA
0x1800179c0  mov     r9, cs:WPP_pszIndent
0x1800179c7  lea     edx, [rdi+5Eh]
0x1800179ca  mov     rcx, [rcx+10h]
0x1800179ce  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800179d5  call    WPP_SF_s
0x1800179da  xor     edx, edx; dwEncodingType
0x1800179dc  mov     [r13+0], edi
0x1800179e0  xorps   xmm0, xmm0
0x1800179e3  mov     [rsp+0A0h+pvPara], rdi; pvPara
0x1800179e8  xorps   xmm1, xmm1
0x1800179eb  xor     r9d, r9d; dwFlags
0x1800179ee  xor     r8d, r8d; hCryptProv
0x1800179f1  lea     ecx, [rdx+2]; lpszStoreProvider
0x1800179f4  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x1800179f8  movups  xmmword ptr [rbp+70h+UnicodeString.Length], xmm1
0x1800179fc  call    cs:__imp_CertOpenStore
0x180017a02  mov     [r15+0A8h], rax
0x180017a09  test    rax, rax
0x180017a0c  jnz     short loc_180017A1B
0x180017a0e  call    cs:__imp_GetLastError
0x180017a14  mov     edi, eax
0x180017a16  jmp     loc_180017CD2
0x180017a1b  lea     rdx, [rbp+70h+SourceString]
0x180017a1f  mov     rcx, r15
0x180017a22  call    I_ReaderListBuildContainerList
0x180017a27  xor     ecx, ecx
0x180017a29  mov     edi, eax
0x180017a2b  test    eax, eax
0x180017a2d  jz      short loc_180017A78
0x180017a2f  lea     edx, [rcx+2]
0x180017a32  call    WppTraceIndent
0x180017a37  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a3e  cmp     rcx, rsi
0x180017a41  jz      short loc_180017A6F
0x180017a43  test    byte ptr [rcx+1Ch], 1
0x180017a47  jz      short loc_180017A6F
0x180017a49  cmp     byte ptr [rcx+19h], 2
0x180017a4d  jb      short loc_180017A6F
0x180017a4f  mov     r9, cs:WPP_pszIndent
0x180017a56  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180017a5d  mov     rcx, [rcx+10h]
0x180017a61  mov     edx, 5Fh ; '_'
0x180017a66  mov     dword ptr [rsp+0A0h+pvPara], edi
0x180017a6a  call    WPP_SF_sd
0x180017a6f  mov     r14, [rbp+70h+SourceString]
0x180017a73  jmp     loc_180017CD2
0x180017a78  cmp     [r12+10h], ecx
0x180017a7d  jz      short loc_180017A8A
0x180017a7f  mov     dword ptr [r15+94h], 1
0x180017a8a  mov     r14, [rbp+70h+SourceString]
0x180017a8e  mov     rsi, r14
0x180017a91  test    rsi, rsi
0x180017a94  jz      loc_180017CCB
0x180017a9a  cmp     [rsi], cl
0x180017a9c  jz      loc_180017CCB
0x180017aa2  cmp     [rbp+70h+UnicodeString.Buffer], rcx
0x180017aa6  jz      short loc_180017AB8
0x180017aa8  lea     rcx, [rbp+70h+UnicodeString]; UnicodeString
0x180017aac  call    cs:__imp_RtlFreeUnicodeString
0x180017ab2  xor     ecx, ecx
0x180017ab4  mov     [rbp+70h+UnicodeString.Buffer], rcx
0x180017ab8  test    rbx, rbx
0x180017abb  jz      short loc_180017AD7
0x180017abd  lea     rcx, [rbx-8]
0x180017ac1  cmp     dword ptr [rcx], 70616548h
0x180017ac7  jnz     short loc_180017AD5
0x180017ac9  mov     rax, cs:g_pfnFree
0x180017ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ad5  xor     ebx, ebx
0x180017ad7  mov     rdx, rsi; SourceString
0x180017ada  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x180017ade  call    cs:__imp_RtlInitAnsiString
0x180017ae4  mov     r8b, 1; AllocateDestinationString
0x180017ae7  lea     rdx, [rbp+70h+DestinationString]; SourceString
0x180017aeb  lea     rcx, [rbp+70h+UnicodeString]; DestinationString
0x180017aef  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180017af5  xor     r8d, r8d
0x180017af8  test    eax, eax
0x180017afa  jnz     loc_180017CC1
0x180017b00  mov     rax, [rbp+70h+UnicodeString.Buffer]
0x180017b04  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017b08  inc     rdi
0x180017b0b  cmp     [rax+rdi*2], r8w
0x180017b10  jnz     short loc_180017B08
0x180017b12  lea     rdi, ds:2[rdi*2]
0x180017b1a  mov     rbx, r8
0x180017b1d  test    rdi, rdi
0x180017b20  jz      short loc_180017B86
0x180017b22  cmp     rdi, cs:g_ulMaxStackAllocSize
0x180017b29  ja      short loc_180017B86
0x180017b2b  mov     rcx, cs:g_ulAdditionalProbeSize
0x180017b32  add     rcx, 8
0x180017b36  add     rcx, rdi
0x180017b39  cmp     rcx, rdi
0x180017b3c  jb      short loc_180017B86
0x180017b3e  call    VerifyStackAvailable
0x180017b43  xor     r8d, r8d
0x180017b46  test    eax, eax
0x180017b48  jz      short loc_180017B86
0x180017b4a  lea     rax, [rdi+8]
0x180017b4e  lea     rcx, [rax+0Fh]
0x180017b52  cmp     rcx, rax
0x180017b55  ja      short loc_180017B61
0x180017b57  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180017b61  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180017b65  mov     rax, rcx
0x180017b68  call    _alloca_probe
0x180017b6d  sub     rsp, rcx
0x180017b70  lea     rbx, [rsp+0A0h+SourceString]
0x180017b75  test    rbx, rbx
0x180017b78  jz      short loc_180017B86
0x180017b7a  mov     dword ptr [rbx], 6B637453h
0x180017b80  add     rbx, 8
0x180017b84  jnz     short loc_180017BB0
0x180017b86  lea     rcx, [rdi+8]
0x180017b8a  cmp     rcx, rdi
0x180017b8d  jb      short loc_180017BB0
0x180017b8f  mov     rax, cs:g_pfnAllocate
0x180017b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b9b  xor     r8d, r8d
0x180017b9e  mov     rbx, rax
0x180017ba1  test    rax, rax
0x180017ba4  jz      short loc_180017BB0
0x180017ba6  mov     dword ptr [rax], 70616548h
0x180017bac  add     rbx, 8
0x180017bb0  test    rbx, rbx
0x180017bb3  jz      loc_180017C77
0x180017bb9  mov     rax, [rbp+70h+UnicodeString.Buffer]
0x180017bbd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180017bc1  inc     rdx
0x180017bc4  cmp     [rax+rdx*2], r8w
0x180017bc9  jnz     short loc_180017BC1
0x180017bcb  mov     r8, [rbp+70h+UnicodeString.Buffer]; pszSrc
0x180017bcf  inc     rdx; cchDest
0x180017bd2  mov     rcx, rbx; pszDest
0x180017bd5  call    StringCchCopyW
0x180017bda  test    eax, eax
0x180017bdc  js      loc_180017C70
0x180017be2  mov     r9, r13
0x180017be5  mov     r8, rbx
0x180017be8  mov     rdx, r15
0x180017beb  mov     rcx, r12
0x180017bee  call    I_ReaderListReadContainerData
0x180017bf3  mov     edi, eax
0x180017bf5  cmp     eax, 8
0x180017bf8  jz      short loc_180017C15
0x180017bfa  xor     ecx, ecx
0x180017bfc  mov     edi, ecx
0x180017bfe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017c02  inc     rax
0x180017c05  cmp     [rsi+rax], cl
0x180017c08  jnz     short loc_180017C02
0x180017c0a  inc     rsi
0x180017c0d  add     rsi, rax
0x180017c10  jmp     loc_180017A91
0x180017c15  mov     edx, 2
0x180017c1a  call    WppTraceIndent
0x180017c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c26  lea     rsi, WPP_GLOBAL_Control
0x180017c2d  cmp     rcx, rsi
0x180017c30  jz      loc_180017CD2
0x180017c36  test    byte ptr [rcx+1Ch], 1
0x180017c3a  jz      loc_180017CD2
0x180017c40  cmp     byte ptr [rcx+19h], 2
0x180017c44  jb      loc_180017CD2
0x180017c4a  mov     r9, cs:WPP_pszIndent
0x180017c51  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180017c58  mov     rcx, [rcx+10h]
0x180017c5c  mov     edx, 61h ; 'a'
0x180017c61  mov     dword ptr [rsp+0A0h+pvPara], 8
0x180017c69  call    WPP_SF_sd
0x180017c6e  jmp     short loc_180017CD2
0x180017c70  mov     edi, 7Ah ; 'z'
0x180017c75  jmp     short loc_180017CCB
0x180017c77  mov     edx, 2
0x180017c7c  call    WppTraceIndent
0x180017c81  mov     edi, 8
0x180017c86  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c8d  lea     rsi, WPP_GLOBAL_Control
0x180017c94  cmp     rcx, rsi
0x180017c97  jz      short loc_180017CD2
0x180017c99  test    byte ptr [rcx+1Ch], 1
0x180017c9d  jz      short loc_180017CD2
0x180017c9f  cmp     byte ptr [rcx+19h], 2
0x180017ca3  jb      short loc_180017CD2
0x180017ca5  mov     r9, cs:WPP_pszIndent
0x180017cac  lea     edx, [rdi+58h]
0x180017caf  mov     rcx, [rcx+10h]
0x180017cb3  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180017cba  call    WPP_SF_s
0x180017cbf  jmp     short loc_180017CD2
0x180017cc1  mov     ecx, eax; Status
0x180017cc3  call    cs:__imp_RtlNtStatusToDosError
0x180017cc9  mov     edi, eax
0x180017ccb  lea     rsi, WPP_GLOBAL_Control
0x180017cd2  mov     rcx, [r15+0A8h]; hCertStore
0x180017cd9  xor     r12d, r12d
0x180017cdc  test    rcx, rcx
0x180017cdf  jz      short loc_180017CFA
0x180017ce1  test    edi, edi
0x180017ce3  jnz     short loc_180017CEB
0x180017ce5  cmp     [r13+0], r12d
0x180017ce9  jnz     short loc_180017CFA
0x180017ceb  xor     edx, edx; dwFlags
0x180017ced  call    cs:__imp_CertCloseStore
0x180017cf3  mov     [r15+0A8h], r12
0x180017cfa  cmp     [rbp+70h+UnicodeString.Buffer], r12
0x180017cfe  jz      short loc_180017D0A
0x180017d00  lea     rcx, [rbp+70h+UnicodeString]; UnicodeString
0x180017d04  call    cs:__imp_RtlFreeUnicodeString
0x180017d0a  test    rbx, rbx
0x180017d0d  jz      short loc_180017D27
0x180017d0f  lea     rcx, [rbx-8]
0x180017d13  cmp     dword ptr [rcx], 70616548h
0x180017d19  jnz     short loc_180017D27
0x180017d1b  mov     rax, cs:g_pfnFree
0x180017d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d27  test    r14, r14
0x180017d2a  jz      short loc_180017D3E
0x180017d2c  mov     rcx, cs:hHeap; hHeap
0x180017d33  mov     r8, r14; lpMem
0x180017d36  xor     edx, edx; dwFlags
0x180017d38  call    cs:__imp_HeapFree
0x180017d3e  mov     edx, 1
0x180017d43  call    WppTraceIndent
0x180017d48  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d4f  cmp     rcx, rsi
0x180017d52  jz      short loc_180017D80
0x180017d54  test    byte ptr [rcx+1Ch], 2
0x180017d58  jz      short loc_180017D80
0x180017d5a  cmp     byte ptr [rcx+19h], 5
0x180017d5e  jb      short loc_180017D80
0x180017d60  mov     r9, cs:WPP_pszIndent
0x180017d67  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180017d6e  mov     rcx, [rcx+10h]
0x180017d72  mov     edx, 62h ; 'b'
0x180017d77  mov     dword ptr [rsp+0A0h+pvPara], edi
0x180017d7b  call    WPP_SF_sd
0x180017d80  mov     eax, edi
0x180017d82  mov     rcx, [rbp+70h+var_48]
0x180017d86  xor     rcx, rbp; StackCookie
0x180017d89  call    __security_check_cookie
0x180017d8e  lea     rsp, [rbp+38h]
0x180017d92  pop     r15
0x180017d94  pop     r14
0x180017d96  pop     r13
0x180017d98  pop     r12
0x180017d9a  pop     rdi
0x180017d9b  pop     rsi
0x180017d9c  pop     rbx
0x180017d9d  pop     rbp
0x180017d9e  retn
```
