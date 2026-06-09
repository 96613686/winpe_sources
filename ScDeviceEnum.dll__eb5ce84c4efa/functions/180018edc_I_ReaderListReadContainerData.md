# I_ReaderListReadContainerData

- ea: `0x180018edc`
- end: `0x180019247`
- name: `I_ReaderListReadContainerData`
- size: `875`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180017954`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x180018edc`
- `0x180019250`
- `0x18001cb0c`
- `0x18001cc6c`
- `0x18001dd7c`
- `0x18001e020`
- `0x18001e0e0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190be`
- `CRYPTSP!CryptReleaseContext` at `0x180019192`
- `CRYPTSP!CryptReleaseContext` at `0x180019192`
- `CRYPTSP!CryptAcquireContextW` at `0x1800190b3`
- `CRYPTSP!CryptAcquireContextW` at `0x1800190b3`

## pseudocode

```c
__int64 __fastcall I_ReaderListReadContainerData(__int64 a1, __int64 *a2, __int64 a3, _DWORD *a4)
{
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rdx
  wchar_t *p_phProv; // rbx
  size_t v13; // r15
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rcx
  __int64 v16; // rcx
  void *v17; // rsp
  void *v18; // rsp
  unsigned __int64 v19; // rcx
  wchar_t *v20; // rax
  DWORD LastError; // edi
  __int64 v22; // rcx
  _QWORD *v23; // rcx
  int v24; // edx
  DWORD ContainerDataPerKeyType; // eax
  __int64 v26; // rcx
  HCRYPTPROV v27; // rcx
  __int64 v29; // [rsp+0h] [rbp-30h] BYREF
  DWORD dwFlags[4]; // [rsp+20h] [rbp-10h]
  HCRYPTPROV phProv; // [rsp+30h] [rbp+0h] BYREF
  __int64 v32; // [rsp+38h] [rbp+8h] BYREF

  phProv = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  v8 = -1;
  v9 = -1;
  v10 = 0;
  do
    ++v9;
  while ( *(_WORD *)(a3 + 2 * v9) );
  v11 = *a2;
  do
    ++v8;
  while ( *(_WORD *)(v11 + 2 * v8) );
  p_phProv = 0;
  v13 = v8 + v9 + 6;
  v14 = 2 * v13;
  if ( 2 * v13 )
  {
    if ( v14 <= g_ulMaxStackAllocSize )
    {
      v15 = v14 + g_ulAdditionalProbeSize + 8;
      if ( v15 >= v14 )
      {
        if ( (unsigned int)VerifyStackAvailable(v15, v11) )
        {
          v16 = v14 + 23;
          if ( v14 + 23 <= v14 + 8 )
            v16 = 0xFFFFFFFFFFFFFF0LL;
          v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
          v18 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
          p_phProv = (wchar_t *)&phProv;
          if ( &v29 != (__int64 *)-48LL )
          {
            LODWORD(phProv) = 1801679955;
            p_phProv = (wchar_t *)&v32;
            if ( &v32 )
              goto LABEL_25;
          }
        }
      }
    }
  }
  v19 = v14 + 8;
  if ( v14 + 8 < v14 )
  {
LABEL_20:
    if ( !p_phProv )
      goto LABEL_21;
LABEL_25:
    if ( StringCchPrintfW(p_phProv, v13, L"\\\\.\\%s\\%s", *a2, a3) < 0 )
    {
      LastError = 122;
      goto LABEL_38;
    }
    if ( !CryptAcquireContextW(&phProv, p_phProv, (LPCWSTR)a2[10], *((_DWORD *)a2 + 30), 0x40u) )
    {
      LastError = GetLastError();
      WppTraceIndent(v22, 2);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_38;
      }
      v24 = 83;
      dwFlags[0] = LastError;
      goto LABEL_32;
    }
    if ( *(_DWORD *)(a1 + 16) )
    {
      ContainerDataPerKeyType = I_ReaderListReadContainerDataPerKeyType(a1, a2, phProv, a3, 2);
      LastError = ContainerDataPerKeyType;
      if ( ContainerDataPerKeyType )
      {
        if ( ContainerDataPerKeyType == 8 )
        {
          WppTraceIndent(v26, 2);
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_38;
          }
          v24 = 84;
          dwFlags[0] = 8;
LABEL_32:
          WPP_SF_sd(
            v23[2],
            v24,
            (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent,
            dwFlags[0]);
          goto LABEL_38;
        }
      }
      else
      {
        ++*a4;
      }
    }
    LastError = I_ReaderListReadContainerDataPerKeyType(a1, a2, phProv, a3, 1);
    if ( !LastError )
      ++*a4;
    goto LABEL_38;
  }
  v20 = (wchar_t *)((__int64 (__fastcall *)(unsigned __int64, __int64, __int64))g_pfnAllocate)(v19, v11, v10);
  p_phProv = v20;
  if ( v20 )
  {
    *(_DWORD *)v20 = 1885431112;
    p_phProv = v20 + 4;
    goto LABEL_20;
  }
LABEL_21:
  WppTraceIndent(v19, 2);
  LastError = 8;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_41;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
LABEL_38:
  if ( p_phProv && *((_DWORD *)p_phProv - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_41:
  v27 = phProv;
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  WppTraceIndent(v27, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      85,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180018edc  push    rbp
0x180018ede  push    rbx
0x180018edf  push    rsi
0x180018ee0  push    rdi
0x180018ee1  push    r12
0x180018ee3  push    r13
0x180018ee5  push    r14
0x180018ee7  push    r15
0x180018ee9  sub     rsp, 58h
0x180018eed  lea     rbp, [rsp+30h]
0x180018ef2  mov     rax, cs:__security_cookie
0x180018ef9  xor     rax, rbp
0x180018efc  mov     [rbp+60h+var_50], rax
0x180018f00  mov     r14, rdx
0x180018f03  xor     r15d, r15d
0x180018f06  xor     edx, edx
0x180018f08  mov     [rbp+60h+phProv], r15
0x180018f0c  mov     rsi, r9
0x180018f0f  mov     r12, r8
0x180018f12  mov     r13, rcx
0x180018f15  call    WppTraceIndent
0x180018f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f21  lea     rax, WPP_GLOBAL_Control
0x180018f28  cmp     rcx, rax
0x180018f2b  jz      short loc_180018F54
0x180018f2d  test    byte ptr [rcx+1Ch], 2
0x180018f31  jz      short loc_180018F54
0x180018f33  cmp     byte ptr [rcx+19h], 5
0x180018f37  jb      short loc_180018F54
0x180018f39  mov     r9, cs:WPP_pszIndent
0x180018f40  lea     edx, [r15+51h]
0x180018f44  mov     rcx, [rcx+10h]
0x180018f48  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180018f4f  call    WPP_SF_s
0x180018f54  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018f58  mov     rcx, rax
0x180018f5b  xor     r8d, r8d
0x180018f5e  inc     rcx
0x180018f61  cmp     [r12+rcx*2], r8w
0x180018f66  jnz     short loc_180018F5E
0x180018f68  mov     rdx, [r14]
0x180018f6b  inc     rax
0x180018f6e  cmp     [rdx+rax*2], r8w
0x180018f73  jnz     short loc_180018F6B
0x180018f75  lea     r15, [rcx+6]
0x180018f79  mov     rbx, r8
0x180018f7c  add     r15, rax
0x180018f7f  lea     rdi, [r15+r15]
0x180018f83  test    rdi, rdi
0x180018f86  jz      short loc_180018FED
0x180018f88  cmp     rdi, cs:g_ulMaxStackAllocSize
0x180018f8f  ja      short loc_180018FED
0x180018f91  mov     rcx, cs:g_ulAdditionalProbeSize
0x180018f98  add     rcx, 8
0x180018f9c  add     rcx, rdi
0x180018f9f  cmp     rcx, rdi
0x180018fa2  jb      short loc_180018FED
0x180018fa4  call    VerifyStackAvailable
0x180018fa9  test    eax, eax
0x180018fab  jz      short loc_180018FED
0x180018fad  lea     rax, [rdi+8]
0x180018fb1  lea     rcx, [rax+0Fh]
0x180018fb5  cmp     rcx, rax
0x180018fb8  ja      short loc_180018FC4
0x180018fba  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180018fc4  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180018fc8  mov     rax, rcx
0x180018fcb  call    _alloca_probe
0x180018fd0  sub     rsp, rcx
0x180018fd3  lea     rbx, [rsp+90h+phProv]
0x180018fd8  test    rbx, rbx
0x180018fdb  jz      short loc_180018FED
0x180018fdd  mov     dword ptr [rbx], 6B637453h
0x180018fe3  add     rbx, 8
0x180018fe7  jnz     loc_180019072
0x180018fed  lea     rcx, [rdi+8]
0x180018ff1  cmp     rcx, rdi
0x180018ff4  jb      short loc_180019014
0x180018ff6  mov     rax, cs:g_pfnAllocate
0x180018ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019002  mov     rbx, rax
0x180019005  test    rax, rax
0x180019008  jz      short loc_180019019
0x18001900a  mov     dword ptr [rax], 70616548h
0x180019010  add     rbx, 8
0x180019014  test    rbx, rbx
0x180019017  jnz     short loc_180019072
0x180019019  mov     edx, 2
0x18001901e  call    WppTraceIndent
0x180019023  mov     edi, 8
0x180019028  mov     rcx, cs:WPP_GLOBAL_Control
0x18001902f  lea     rsi, WPP_GLOBAL_Control
0x180019036  cmp     rcx, rsi
0x180019039  jz      loc_180019187
0x18001903f  test    byte ptr [rcx+1Ch], 1
0x180019043  jz      loc_18001916A
0x180019049  cmp     byte ptr [rcx+19h], 2
0x18001904d  jb      loc_18001916A
0x180019053  mov     r9, cs:WPP_pszIndent
0x18001905a  lea     edx, [rdi+4Ah]
0x18001905d  mov     rcx, [rcx+10h]
0x180019061  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180019068  call    WPP_SF_s
0x18001906d  jmp     loc_18001916A
0x180019072  mov     r9, [r14]
0x180019075  lea     r8, aSS; "\\\\.\\%s\\%s"
0x18001907c  mov     rdx, r15; cchDest
0x18001907f  mov     qword ptr [rsp+90h+dwFlags], r12
0x180019084  mov     rcx, rbx; pszDest
0x180019087  call    StringCchPrintfW
0x18001908c  xor     r15d, r15d
0x18001908f  test    eax, eax
0x180019091  jns     short loc_18001909C
0x180019093  lea     edi, [r15+7Ah]
0x180019097  jmp     loc_180019163
0x18001909c  mov     r9d, [r14+78h]; dwProvType
0x1800190a0  lea     rcx, [rbp+60h+phProv]; phProv
0x1800190a4  mov     r8, [r14+50h]; szProvider
0x1800190a8  mov     rdx, rbx; szContainer
0x1800190ab  mov     [rsp+90h+dwFlags], 40h ; '@'; dwFlags
0x1800190b3  call    cs:__imp_CryptAcquireContextW
0x1800190b9  cmp     eax, 1
0x1800190bc  jz      short loc_180019115
0x1800190be  call    cs:__imp_GetLastError
0x1800190c4  mov     edx, 2
0x1800190c9  mov     edi, eax
0x1800190cb  call    WppTraceIndent
0x1800190d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190d7  lea     rsi, WPP_GLOBAL_Control
0x1800190de  cmp     rcx, rsi
0x1800190e1  jz      loc_18001916A
0x1800190e7  test    byte ptr [rcx+1Ch], 1
0x1800190eb  jz      short loc_18001916A
0x1800190ed  cmp     byte ptr [rcx+19h], 2
0x1800190f1  jb      short loc_18001916A
0x1800190f3  mov     edx, 53h ; 'S'
0x1800190f8  mov     [rsp+90h+dwFlags], edi
0x1800190fc  mov     r9, cs:WPP_pszIndent
0x180019103  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001910a  mov     rcx, [rcx+10h]
0x18001910e  call    WPP_SF_sd
0x180019113  jmp     short loc_18001916A
0x180019115  cmp     [r13+10h], r15d
0x180019119  jz      short loc_180019141
0x18001911b  mov     r8, [rbp+60h+phProv]
0x18001911f  mov     r9, r12
0x180019122  mov     rdx, r14
0x180019125  mov     [rsp+90h+dwFlags], 2
0x18001912d  mov     rcx, r13
0x180019130  call    I_ReaderListReadContainerDataPerKeyType
0x180019135  mov     edi, eax
0x180019137  test    eax, eax
0x180019139  jnz     loc_1800191F9
0x18001913f  inc     dword ptr [rsi]
0x180019141  mov     r8, [rbp+60h+phProv]
0x180019145  mov     r9, r12
0x180019148  mov     rdx, r14
0x18001914b  mov     [rsp+90h+dwFlags], 1
0x180019153  mov     rcx, r13
0x180019156  call    I_ReaderListReadContainerDataPerKeyType
0x18001915b  mov     edi, eax
0x18001915d  test    eax, eax
0x18001915f  jnz     short loc_180019163
0x180019161  inc     dword ptr [rsi]
0x180019163  lea     rsi, WPP_GLOBAL_Control
0x18001916a  test    rbx, rbx
0x18001916d  jz      short loc_180019187
0x18001916f  lea     rcx, [rbx-8]
0x180019173  cmp     dword ptr [rcx], 70616548h
0x180019179  jnz     short loc_180019187
0x18001917b  mov     rax, cs:g_pfnFree
0x180019182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019187  mov     rcx, [rbp+60h+phProv]; hProv
0x18001918b  test    rcx, rcx
0x18001918e  jz      short loc_180019198
0x180019190  xor     edx, edx; dwFlags
0x180019192  call    cs:__imp_CryptReleaseContext
0x180019198  mov     edx, 1
0x18001919d  call    WppTraceIndent
0x1800191a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800191a9  cmp     rcx, rsi
0x1800191ac  jz      short loc_1800191DA
0x1800191ae  test    byte ptr [rcx+1Ch], 2
0x1800191b2  jz      short loc_1800191DA
0x1800191b4  cmp     byte ptr [rcx+19h], 5
0x1800191b8  jb      short loc_1800191DA
0x1800191ba  mov     r9, cs:WPP_pszIndent
0x1800191c1  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800191c8  mov     rcx, [rcx+10h]
0x1800191cc  mov     edx, 55h ; 'U'
0x1800191d1  mov     [rsp+90h+dwFlags], edi
0x1800191d5  call    WPP_SF_sd
0x1800191da  mov     eax, edi
0x1800191dc  mov     rcx, [rbp+60h+var_50]
0x1800191e0  xor     rcx, rbp; StackCookie
0x1800191e3  call    __security_check_cookie
0x1800191e8  lea     rsp, [rbp+28h]
0x1800191ec  pop     r15
0x1800191ee  pop     r14
0x1800191f0  pop     r13
0x1800191f2  pop     r12
0x1800191f4  pop     rdi
0x1800191f5  pop     rsi
0x1800191f6  pop     rbx
0x1800191f7  pop     rbp
0x1800191f8  retn
0x1800191f9  cmp     eax, 8
0x1800191fc  jnz     loc_180019141
0x180019202  lea     edx, [rax-6]
0x180019205  call    WppTraceIndent
0x18001920a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019211  lea     rsi, WPP_GLOBAL_Control
0x180019218  cmp     rcx, rsi
0x18001921b  jz      loc_18001916A
0x180019221  test    byte ptr [rcx+1Ch], 1
0x180019225  jz      loc_18001916A
0x18001922b  cmp     byte ptr [rcx+19h], 2
0x18001922f  jb      loc_18001916A
0x180019235  mov     edx, 54h ; 'T'
0x18001923a  mov     [rsp+90h+dwFlags], 8
0x180019242  jmp     loc_1800190FC
```
