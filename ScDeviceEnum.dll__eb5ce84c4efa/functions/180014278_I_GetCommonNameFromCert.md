# I_GetCommonNameFromCert

- ea: `0x180014278`
- end: `0x180014464`
- name: `I_GetCommonNameFromCert`
- size: `492`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, WCHAR **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800160c8`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x180014278`
- `0x18001cc6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014317`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800143cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014317`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800143cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001440c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001440c`
- `CRYPT32!CertGetNameStringW` at `0x1800142f1`
- `CRYPT32!CertGetNameStringW` at `0x180014387`
- `CRYPT32!CertGetNameStringW` at `0x1800143b0`
- `CRYPT32!CertGetNameStringW` at `0x1800142f1`
- `CRYPT32!CertGetNameStringW` at `0x180014387`
- `CRYPT32!CertGetNameStringW` at `0x1800143b0`

## pseudocode

```c
__int64 __fastcall I_GetCommonNameFromCert(PCCERT_CONTEXT pCertContext, WCHAR **a2)
{
  DWORD NameStringW; // eax
  DWORD LastError; // ebx
  DWORD cchNameString; // esi
  WCHAR *pszNameString; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  DWORD v11; // edx
  DWORD v12; // eax
  __int64 v13; // rcx

  WppTraceIndent(pCertContext, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  *a2 = 0;
  NameStringW = CertGetNameStringW(pCertContext, 4u, 0, 0, 0, 0);
  LastError = 8;
  cchNameString = NameStringW;
  if ( NameStringW != 1 )
  {
    pszNameString = (WCHAR *)HeapAlloc(hHeap, 8u, 2LL * (NameStringW + 1));
    *a2 = pszNameString;
    if ( !pszNameString )
    {
      WppTraceIndent(v8, 2);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 21;
LABEL_11:
        WPP_SF_s(v9[2], v10, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
        goto LABEL_23;
      }
      goto LABEL_23;
    }
    v11 = 4;
    goto LABEL_13;
  }
  v12 = CertGetNameStringW(pCertContext, 8u, 0, 0, 0, 0);
  cchNameString = v12;
  if ( v12 == 1 )
    goto LABEL_22;
  pszNameString = (WCHAR *)HeapAlloc(hHeap, 8u, 2LL * (v12 + 1));
  *a2 = pszNameString;
  if ( pszNameString )
  {
    v11 = 8;
LABEL_13:
    if ( CertGetNameStringW(pCertContext, v11, 0, 0, pszNameString, cchNameString) != 1 )
    {
      LastError = 0;
      goto LABEL_23;
    }
LABEL_22:
    LastError = GetLastError();
    goto LABEL_23;
  }
  WppTraceIndent(v13, 2);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = 22;
    goto LABEL_11;
  }
LABEL_23:
  WppTraceIndent(v9, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180014278  push    rbx
0x18001427a  push    rsi
0x18001427b  push    rdi
0x18001427c  push    r13
0x18001427e  push    r14
0x180014280  sub     rsp, 30h
0x180014284  mov     r14, rdx
0x180014287  mov     rdi, rcx
0x18001428a  xor     edx, edx
0x18001428c  call    WppTraceIndent
0x180014291  mov     rcx, cs:WPP_GLOBAL_Control
0x180014298  lea     r13, WPP_GLOBAL_Control
0x18001429f  cmp     rcx, r13
0x1800142a2  jz      short loc_1800142CC
0x1800142a4  test    byte ptr [rcx+1Ch], 2
0x1800142a8  jz      short loc_1800142CC
0x1800142aa  cmp     byte ptr [rcx+19h], 5
0x1800142ae  jb      short loc_1800142CC
0x1800142b0  mov     r9, cs:WPP_pszIndent
0x1800142b7  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800142be  mov     rcx, [rcx+10h]
0x1800142c2  mov     edx, 14h
0x1800142c7  call    WPP_SF_s
0x1800142cc  xor     r9d, r9d; pvTypePara
0x1800142cf  mov     [rsp+58h+cchNameString], 0; cchNameString
0x1800142d7  xor     r8d, r8d; dwFlags
0x1800142da  mov     qword ptr [r14], 0
0x1800142e1  mov     rcx, rdi; pCertContext
0x1800142e4  mov     [rsp+58h+pszNameString], 0; pszNameString
0x1800142ed  lea     edx, [r9+4]; dwType
0x1800142f1  call    cs:__imp_CertGetNameStringW
0x1800142f7  mov     ebx, 8
0x1800142fc  mov     esi, eax
0x1800142fe  mov     edx, ebx; dwType
0x180014300  cmp     eax, 1
0x180014303  jz      loc_180014396
0x180014309  mov     rcx, cs:hHeap; hHeap
0x180014310  lea     r8d, [rax+1]
0x180014314  add     r8, r8; dwBytes
0x180014317  call    cs:__imp_HeapAlloc
0x18001431d  mov     [r14], rax
0x180014320  test    rax, rax
0x180014323  jnz     short loc_180014370
0x180014325  lea     edx, [rbx-6]
0x180014328  call    WppTraceIndent
0x18001432d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014334  cmp     rcx, r13
0x180014337  jz      loc_180014414
0x18001433d  test    byte ptr [rcx+1Ch], 1
0x180014341  jz      loc_180014414
0x180014347  cmp     byte ptr [rcx+19h], 2
0x18001434b  jb      loc_180014414
0x180014351  lea     edx, [rbx+0Dh]
0x180014354  mov     r9, cs:WPP_pszIndent
0x18001435b  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180014362  mov     rcx, [rcx+10h]
0x180014366  call    WPP_SF_s
0x18001436b  jmp     loc_180014414
0x180014370  mov     edx, 4; dwType
0x180014375  xor     r9d, r9d; pvTypePara
0x180014378  mov     [rsp+58h+cchNameString], esi; cchNameString
0x18001437c  xor     r8d, r8d; dwFlags
0x18001437f  mov     [rsp+58h+pszNameString], rax; pszNameString
0x180014384  mov     rcx, rdi; pCertContext
0x180014387  call    cs:__imp_CertGetNameStringW
0x18001438d  cmp     eax, 1
0x180014390  jz      short loc_18001440C
0x180014392  xor     ebx, ebx
0x180014394  jmp     short loc_180014414
0x180014396  mov     [rsp+58h+cchNameString], 0; cchNameString
0x18001439e  xor     r9d, r9d; pvTypePara
0x1800143a1  xor     r8d, r8d; dwFlags
0x1800143a4  mov     [rsp+58h+pszNameString], 0; pszNameString
0x1800143ad  mov     rcx, rdi; pCertContext
0x1800143b0  call    cs:__imp_CertGetNameStringW
0x1800143b6  mov     esi, eax
0x1800143b8  cmp     eax, 1
0x1800143bb  jz      short loc_18001440C
0x1800143bd  mov     rcx, cs:hHeap; hHeap
0x1800143c4  lea     r8d, [rax+1]
0x1800143c8  add     r8, r8; dwBytes
0x1800143cb  mov     edx, ebx; dwFlags
0x1800143cd  call    cs:__imp_HeapAlloc
0x1800143d3  mov     [r14], rax
0x1800143d6  test    rax, rax
0x1800143d9  jnz     short loc_180014405
0x1800143db  lea     edx, [rax+2]
0x1800143de  call    WppTraceIndent
0x1800143e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143ea  cmp     rcx, r13
0x1800143ed  jz      short loc_180014414
0x1800143ef  test    byte ptr [rcx+1Ch], 1
0x1800143f3  jz      short loc_180014414
0x1800143f5  cmp     byte ptr [rcx+19h], 2
0x1800143f9  jb      short loc_180014414
0x1800143fb  mov     edx, 16h
0x180014400  jmp     loc_180014354
0x180014405  mov     edx, ebx
0x180014407  jmp     loc_180014375
0x18001440c  call    cs:__imp_GetLastError
0x180014412  mov     ebx, eax
0x180014414  mov     edx, 1
0x180014419  call    WppTraceIndent
0x18001441e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014425  cmp     rcx, r13
0x180014428  jz      short loc_180014456
0x18001442a  test    byte ptr [rcx+1Ch], 2
0x18001442e  jz      short loc_180014456
0x180014430  cmp     byte ptr [rcx+19h], 5
0x180014434  jb      short loc_180014456
0x180014436  mov     r9, cs:WPP_pszIndent
0x18001443d  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180014444  mov     rcx, [rcx+10h]
0x180014448  mov     edx, 17h
0x18001444d  mov     dword ptr [rsp+58h+pszNameString], ebx
0x180014451  call    WPP_SF_sd
0x180014456  mov     eax, ebx
0x180014458  add     rsp, 30h
0x18001445c  pop     r14
0x18001445e  pop     r13
0x180014460  pop     rdi
0x180014461  pop     rsi
0x180014462  pop     rbx
0x180014463  retn
```
