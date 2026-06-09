# std::_Med3_unchecked<StringToFontIndex *,std::less<void>>(StringToFontIndex *,StringToFontIndex *,StringToFontIndex *,std::less<void>)

- ea: `0x180028d88`
- end: `0x180028f42`
- name: `??$_Med3_unchecked@PEAUStringToFontIndex@@U?$less@X@std@@@std@@YAXPEAUStringToFontIndex@@00U?$less@X@0@@Z`
- size: `442`
- prototype: `int __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180070920`

## callees

- `0x180028c50`
- `0x180028d88`
- `0x1800543c0`
- `0x180072094`
- `0x18009e420`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180028df6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180028eaa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180028df6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180028eaa`

## pseudocode

```c
int __fastcall std::_Med3_unchecked<StringToFontIndex *,std::less<void>>(__int64 a1, __int64 a2, _DWORD *a3)
{
  volatile signed __int32 *v6; // rcx
  volatile signed __int32 *v7; // r9
  const WCHAR *v8; // r8
  int v9; // ebp
  unsigned int cchCount2; // edx
  unsigned int v11; // r9d
  int v12; // eax
  int *v13; // rsi
  volatile signed __int32 *v14; // rdi
  int v15; // ebx
  volatile signed __int32 *v16; // rcx
  const WCHAR *lpString2; // rax
  unsigned int v18; // r9d

  v6 = *(volatile signed __int32 **)a1;
  v7 = *(volatile signed __int32 **)a2;
  v8 = (const WCHAR *)(*(_QWORD *)a2 + 8LL);
  v9 = -1;
  if ( *(_QWORD *)a2 == -8 )
  {
    if ( v6 != (volatile signed __int32 *)-8LL )
    {
      v12 = -1;
      goto LABEL_6;
    }
  }
  else
  {
    if ( v6 == (volatile signed __int32 *)-8LL )
    {
      v12 = 1;
      goto LABEL_6;
    }
    cchCount2 = *((_DWORD *)v6 + 1);
    if ( cchCount2 > 0x7FFFFFFF || (v11 = *((_DWORD *)v7 + 1), v11 > 0x7FFFFFFF) )
LABEL_27:
      SafeIntExceptionHandler<Exception>::SafeIntOnOverflow();
    v12 = CompareStringW(0x7Fu, 1u, v8, v11, (PCNZWCH)v6 + 4, cchCount2) - 2;
    if ( v12 )
    {
LABEL_6:
      v13 = (int *)(a2 + 8);
      if ( v12 >= 0 )
        goto LABEL_8;
      goto LABEL_7;
    }
  }
  v13 = (int *)(a2 + 8);
  if ( *(_DWORD *)(a2 + 8) < *(_DWORD *)(a1 + 8) )
  {
LABEL_7:
    v14 = *(volatile signed __int32 **)a2;
    _InterlockedAdd(*(volatile signed __int32 **)a2, 1u);
    v15 = *v13;
    _InterlockedAdd(*(volatile signed __int32 **)a1, 1u);
    DWrite::RefString::DecrementRef(*(struct DWrite::RefString::Data **)a2);
    *(_QWORD *)a2 = *(_QWORD *)a1;
    *v13 = *(_DWORD *)(a1 + 8);
    _InterlockedAdd(v14, 1u);
    DWrite::RefString::DecrementRef(*(struct DWrite::RefString::Data **)a1);
    *(_QWORD *)a1 = v14;
    *(_DWORD *)(a1 + 8) = v15;
    DWrite::RefString::DecrementRef((struct DWrite::RefString::Data *)v14);
  }
LABEL_8:
  v16 = *(volatile signed __int32 **)a2;
  lpString2 = (const WCHAR *)(*(_QWORD *)a2 + 8LL);
  if ( *(_QWORD *)a3 == -8 )
  {
    if ( *(_QWORD *)a2 == -8 )
      goto LABEL_16;
LABEL_13:
    if ( v9 >= 0 )
      return (int)lpString2;
    goto LABEL_17;
  }
  if ( *(_QWORD *)a2 == -8 )
  {
    v9 = 1;
    goto LABEL_13;
  }
  if ( *((_DWORD *)v16 + 1) > 0x7FFFFFFFu )
    goto LABEL_27;
  v18 = *(_DWORD *)(*(_QWORD *)a3 + 4LL);
  if ( v18 > 0x7FFFFFFF )
    goto LABEL_27;
  LODWORD(lpString2) = CompareStringW(0x7Fu, 1u, (PCNZWCH)(*(_QWORD *)a3 + 8LL), v18, lpString2, *((_DWORD *)v16 + 1));
  v9 = (_DWORD)lpString2 - 2;
  if ( (_DWORD)lpString2 != 2 )
    goto LABEL_13;
  v13 = (int *)(a2 + 8);
LABEL_16:
  LODWORD(lpString2) = *v13;
  if ( a3[2] >= (unsigned int)*v13 )
    return (int)lpString2;
LABEL_17:
  std::swap<StringToFontIndex,0>(a3, a2);
  LODWORD(lpString2) = operator<(a2, a1);
  if ( (_BYTE)lpString2 )
    LODWORD(lpString2) = std::swap<StringToFontIndex,0>(a2, a1);
  return (int)lpString2;
}

```

## disassembly

```asm
0x180028d88  push    rbx
0x180028d8a  push    rbp
0x180028d8b  push    rsi
0x180028d8c  push    rdi
0x180028d8d  push    r12
0x180028d8f  push    r13
0x180028d91  push    r14
0x180028d93  push    r15
0x180028d95  sub     rsp, 48h
0x180028d99  mov     r12, r8
0x180028d9c  mov     r14, rdx
0x180028d9f  mov     r15, rcx
0x180028da2  mov     rcx, [rcx]
0x180028da5  lea     rax, [rcx+8]
0x180028da9  mov     r9, [rdx]
0x180028dac  lea     r8, [r9+8]; lpString1
0x180028db0  or      ebp, 0FFFFFFFFh
0x180028db3  mov     ebx, 7FFFFFFFh
0x180028db8  lea     r13d, [rbp+2]
0x180028dbc  test    r8, r8
0x180028dbf  jz      loc_180028F19
0x180028dc5  test    rax, rax
0x180028dc8  jz      loc_180028F2C
0x180028dce  mov     edx, [rcx+4]
0x180028dd1  cmp     edx, ebx
0x180028dd3  ja      loc_180028F3C
0x180028dd9  mov     r9d, [r9+4]; cchCount1
0x180028ddd  cmp     r9d, ebx
0x180028de0  ja      loc_180028F3C
0x180028de6  mov     [rsp+88h+cchCount2], edx; cchCount2
0x180028dea  mov     [rsp+88h+lpString2], rax; lpString2
0x180028def  mov     edx, r13d; dwCmpFlags
0x180028df2  lea     ecx, [r13+7Eh]; Locale
0x180028df6  call    cs:__imp_CompareStringW
0x180028dfc  add     eax, 0FFFFFFFEh
0x180028dff  jz      loc_180028F04
0x180028e05  shr     eax, 1Fh
0x180028e08  lea     rsi, [r14+8]
0x180028e0c  test    al, al
0x180028e0e  jz      short loc_180028E5D
0x180028e10  mov     rdi, [r14]
0x180028e13  mov     [rsp+88h+var_58], rdi
0x180028e18  lock add [rdi], r13d
0x180028e1c  mov     ebx, [rsi]
0x180028e1e  mov     [rsp+88h+var_50], ebx
0x180028e22  mov     rax, [r15]
0x180028e25  lock add [rax], r13d
0x180028e29  mov     rcx, [r14]; struct DWrite::RefString::Data *
0x180028e2c  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180028e31  mov     rax, [r15]
0x180028e34  mov     [r14], rax
0x180028e37  mov     eax, [r15+8]
0x180028e3b  mov     [rsi], eax
0x180028e3d  lock add [rdi], r13d
0x180028e41  mov     rcx, [r15]; struct DWrite::RefString::Data *
0x180028e44  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180028e49  mov     [r15], rdi
0x180028e4c  mov     [r15+8], ebx
0x180028e50  mov     rcx, rdi; struct DWrite::RefString::Data *
0x180028e53  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180028e58  mov     ebx, 7FFFFFFFh
0x180028e5d  mov     rcx, [r14]
0x180028e60  lea     rax, [rcx+8]
0x180028e64  mov     rdx, [r12]
0x180028e68  lea     r8, [rdx+8]; lpString1
0x180028e6c  test    r8, r8
0x180028e6f  jz      loc_180028F25
0x180028e75  test    rax, rax
0x180028e78  jz      loc_180028F34
0x180028e7e  mov     r10d, [rcx+4]
0x180028e82  cmp     r10d, ebx
0x180028e85  ja      loc_180028F3C
0x180028e8b  mov     r9d, [rdx+4]; cchCount1
0x180028e8f  cmp     r9d, ebx
0x180028e92  ja      loc_180028F3C
0x180028e98  mov     [rsp+88h+cchCount2], r10d; cchCount2
0x180028e9d  mov     [rsp+88h+lpString2], rax; lpString2
0x180028ea2  mov     edx, r13d; dwCmpFlags
0x180028ea5  mov     ecx, 7Fh; Locale
0x180028eaa  call    cs:__imp_CompareStringW
0x180028eb0  lea     ebp, [rax-2]
0x180028eb3  test    ebp, ebp
0x180028eb5  jz      short loc_180028ED0
0x180028eb7  shr     ebp, 1Fh
0x180028eba  test    bpl, bpl
0x180028ebd  jnz     short loc_180028EDD
0x180028ebf  add     rsp, 48h
0x180028ec3  pop     r15
0x180028ec5  pop     r14
0x180028ec7  pop     r13
0x180028ec9  pop     r12
0x180028ecb  pop     rdi
0x180028ecc  pop     rsi
0x180028ecd  pop     rbp
0x180028ece  pop     rbx
0x180028ecf  retn
0x180028ed0  lea     rsi, [r14+8]
0x180028ed4  mov     eax, [rsi]
0x180028ed6  cmp     [r12+8], eax
0x180028edb  jnb     short loc_180028EBF
0x180028edd  mov     rdx, r14
0x180028ee0  mov     rcx, r12
0x180028ee3  call    ??$swap@UStringToFontIndex@@$0A@@std@@YAXAEAUStringToFontIndex@@0@Z; std::swap<StringToFontIndex,0>(StringToFontIndex &,StringToFontIndex &)
0x180028ee8  mov     rdx, r15
0x180028eeb  mov     rcx, r14
0x180028eee  call    ??M@YA_NAEBUStringToFontIndex@@0@Z; operator<(StringToFontIndex const &,StringToFontIndex const &)
0x180028ef3  test    al, al
0x180028ef5  jz      short loc_180028EBF
0x180028ef7  mov     rdx, r15
0x180028efa  mov     rcx, r14
0x180028efd  call    ??$swap@UStringToFontIndex@@$0A@@std@@YAXAEAUStringToFontIndex@@0@Z; std::swap<StringToFontIndex,0>(StringToFontIndex &,StringToFontIndex &)
0x180028f02  jmp     short loc_180028EBF
0x180028f04  lea     rsi, [r14+8]
0x180028f08  mov     eax, [r15+8]
0x180028f0c  cmp     [rsi], eax
0x180028f0e  jnb     loc_180028E5D
0x180028f14  jmp     loc_180028E10
0x180028f19  test    rax, rax
0x180028f1c  jz      short loc_180028F04
0x180028f1e  mov     eax, ebp
0x180028f20  jmp     loc_180028E05
0x180028f25  test    rax, rax
0x180028f28  jnz     short loc_180028EB7
0x180028f2a  jmp     short loc_180028ED4
0x180028f2c  mov     eax, r13d
0x180028f2f  jmp     loc_180028E05
0x180028f34  mov     ebp, r13d
0x180028f37  jmp     loc_180028EB7
0x180028f3c  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
```
