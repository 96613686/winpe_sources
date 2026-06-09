# I_ReaderListBuildCredFromCertContext

- ea: `0x1800160c8`
- end: `0x1800163af`
- name: `I_ReaderListBuildCredFromCertContext`
- size: `743`
- prototype: `__int64 __fastcall(__int64, const CERT_CONTEXT *, const wchar_t *, int, _QWORD *)`
- caller_count: `4`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180016500`
- `0x180017544`
- `0x180017f9c`
- `0x180019250`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x180014018`
- `0x180014138`
- `0x180014278`
- `0x180014ca0`
- `0x180014f60`
- `0x180015324`
- `0x1800160c8`
- `0x18001ca98`
- `0x18001cc6c`
- `0x18001dfe2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016141`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800161d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016141`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800161d2`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001633e`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001633e`

## pseudocode

```c
__int64 __fastcall I_ReaderListBuildCredFromCertContext(
        __int64 a1,
        const CERT_CONTEXT *a2,
        const wchar_t *a3,
        int a4,
        _QWORD *a5)
{
  unsigned int UpnFromCert; // ebx
  char *v10; // rax
  __int64 v11; // rcx
  char *v12; // rdi
  PVOID v13; // rcx
  __int64 v14; // rbp
  __int64 v15; // r8
  wchar_t *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  int v20; // edx
  __int64 v21; // rcx

  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  UpnFromCert = 8;
  v10 = (char *)HeapAlloc(hHeap, 8u, 0x70u);
  v12 = v10;
  if ( v10 )
  {
    memset_0(v10, 0, 0x70u);
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( a3[v15] );
    v16 = (wchar_t *)HeapAlloc(hHeap, 8u, 2 * v15 + 2);
    *(_QWORD *)v12 = v16;
    if ( !v16 )
    {
      WppTraceIndent(v17, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          65,
          &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_31;
    }
    do
      ++v14;
    while ( a3[v14] );
    if ( StringCchCopyW(v16, v14 + 1, a3) >= 0 )
    {
      *((_DWORD *)v12 + 2) = a4;
      UpnFromCert = I_GetUpnFromCert(a2, v12 + 24, *(unsigned int *)(a1 + 12));
      if ( UpnFromCert )
      {
        WppTraceIndent(v18, 2);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_31;
        }
        v20 = 66;
      }
      else
      {
        UpnFromCert = I_GetCommonNameFromCert(a2, (WCHAR **)v12 + 2);
        if ( !UpnFromCert )
        {
          I_GetTemplateInfoFromCert((__int64)a2, (_QWORD *)v12 + 4, (_DWORD *)v12 + 10);
          I_GetPinInfoFromCertContext(a2);
          I_GetCertificate_UPN_DN_Hash(a2, v12);
          *((_QWORD *)v12 + 6) = CertDuplicateCertificateContext(a2);
          *a5 = v12;
          goto LABEL_33;
        }
        WppTraceIndent(v21, 2);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_31;
        }
        v20 = 67;
      }
      WPP_SF_sd(v19[2], v20, (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent, UpnFromCert);
    }
    else
    {
      UpnFromCert = 122;
    }
LABEL_31:
    I_FreeCredListItem((LPVOID *)v12);
    goto LABEL_33;
  }
  WppTraceIndent(v11, 2);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
LABEL_33:
  WppTraceIndent(v13, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      UpnFromCert);
  }
  return UpnFromCert;
}

```

## disassembly

```asm
0x1800160c8  push    rbx
0x1800160ca  push    rbp
0x1800160cb  push    rsi
0x1800160cc  push    rdi
0x1800160cd  push    r12
0x1800160cf  push    r13
0x1800160d1  push    r14
0x1800160d3  push    r15
0x1800160d5  sub     rsp, 38h
0x1800160d9  mov     rsi, rdx
0x1800160dc  mov     r15d, r9d
0x1800160df  xor     edx, edx
0x1800160e1  mov     r14, r8
0x1800160e4  mov     r13, rcx
0x1800160e7  call    WppTraceIndent
0x1800160ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160f3  lea     rax, WPP_GLOBAL_Control
0x1800160fa  mov     r12d, 2
0x180016100  cmp     rcx, rax
0x180016103  jz      short loc_18001612D
0x180016105  test    [rcx+1Ch], r12b
0x180016109  jz      short loc_18001612D
0x18001610b  cmp     byte ptr [rcx+19h], 5
0x18001610f  jb      short loc_18001612D
0x180016111  mov     r9, cs:WPP_pszIndent
0x180016118  lea     edx, [r12+3Dh]
0x18001611d  mov     rcx, [rcx+10h]
0x180016121  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180016128  call    WPP_SF_s
0x18001612d  mov     rcx, cs:hHeap; hHeap
0x180016134  mov     ebp, 70h ; 'p'
0x180016139  mov     r8d, ebp; dwBytes
0x18001613c  lea     ebx, [rbp-68h]
0x18001613f  mov     edx, ebx; dwFlags
0x180016141  call    cs:__imp_HeapAlloc
0x180016147  mov     rdi, rax
0x18001614a  test    rax, rax
0x18001614d  jnz     short loc_1800161A1
0x18001614f  mov     edx, r12d
0x180016152  call    WppTraceIndent
0x180016157  mov     rcx, cs:WPP_GLOBAL_Control
0x18001615e  lea     rsi, WPP_GLOBAL_Control
0x180016165  cmp     rcx, rsi
0x180016168  jz      loc_18001635A
0x18001616e  test    byte ptr [rcx+1Ch], 1
0x180016172  jz      loc_18001635A
0x180016178  cmp     [rcx+19h], r12b
0x18001617c  jb      loc_18001635A
0x180016182  mov     r9, cs:WPP_pszIndent
0x180016189  lea     edx, [rbp-30h]
0x18001618c  mov     rcx, [rcx+10h]
0x180016190  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180016197  call    WPP_SF_s
0x18001619c  jmp     loc_18001635A
0x1800161a1  mov     r8, rbp; Size
0x1800161a4  xor     edx, edx; Val
0x1800161a6  mov     rcx, rdi; void *
0x1800161a9  call    memset_0
0x1800161ae  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800161b2  mov     r8, rbp
0x1800161b5  xor     eax, eax
0x1800161b7  inc     r8
0x1800161ba  cmp     [r14+r8*2], ax
0x1800161bf  jnz     short loc_1800161B7
0x1800161c1  mov     rcx, cs:hHeap; hHeap
0x1800161c8  lea     r8, ds:2[r8*2]; dwBytes
0x1800161d0  mov     edx, ebx; dwFlags
0x1800161d2  call    cs:__imp_HeapAlloc
0x1800161d8  xor     r11d, r11d
0x1800161db  mov     [rdi], rax
0x1800161de  test    rax, rax
0x1800161e1  jnz     short loc_180016237
0x1800161e3  mov     edx, r12d
0x1800161e6  call    WppTraceIndent
0x1800161eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800161f2  lea     rsi, WPP_GLOBAL_Control
0x1800161f9  cmp     rcx, rsi
0x1800161fc  jz      loc_180016306
0x180016202  test    byte ptr [rcx+1Ch], 1
0x180016206  jz      loc_180016306
0x18001620c  cmp     [rcx+19h], r12b
0x180016210  jb      loc_180016306
0x180016216  mov     r9, cs:WPP_pszIndent
0x18001621d  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180016224  mov     rcx, [rcx+10h]
0x180016228  mov     edx, 41h ; 'A'
0x18001622d  call    WPP_SF_s
0x180016232  jmp     loc_180016306
0x180016237  inc     rbp
0x18001623a  cmp     [r14+rbp*2], r11w
0x18001623f  jnz     short loc_180016237
0x180016241  lea     rdx, [rbp+1]; cchDest
0x180016245  mov     r8, r14; pszSrc
0x180016248  mov     rcx, rax; pszDest
0x18001624b  call    StringCchCopyW
0x180016250  test    eax, eax
0x180016252  jns     short loc_180016265
0x180016254  mov     ebx, 7Ah ; 'z'
0x180016259  lea     rsi, WPP_GLOBAL_Control
0x180016260  jmp     loc_180016306
0x180016265  mov     [rdi+8], r15d
0x180016269  lea     rdx, [rdi+18h]
0x18001626d  mov     r8d, [r13+0Ch]
0x180016271  mov     rcx, rsi
0x180016274  call    I_GetUpnFromCert
0x180016279  xor     ebp, ebp
0x18001627b  mov     ebx, eax
0x18001627d  test    eax, eax
0x18001627f  jz      short loc_1800162AD
0x180016281  mov     edx, r12d
0x180016284  call    WppTraceIndent
0x180016289  mov     rcx, cs:WPP_GLOBAL_Control
0x180016290  lea     rsi, WPP_GLOBAL_Control
0x180016297  cmp     rcx, rsi
0x18001629a  jz      short loc_180016306
0x18001629c  test    byte ptr [rcx+1Ch], 1
0x1800162a0  jz      short loc_180016306
0x1800162a2  cmp     [rcx+19h], r12b
0x1800162a6  jb      short loc_180016306
0x1800162a8  lea     edx, [rbp+42h]
0x1800162ab  jmp     short loc_1800162EB
0x1800162ad  lea     rdx, [rdi+10h]
0x1800162b1  mov     rcx, rsi; pCertContext
0x1800162b4  call    I_GetCommonNameFromCert
0x1800162b9  mov     ebx, eax
0x1800162bb  test    eax, eax
0x1800162bd  jz      short loc_180016310
0x1800162bf  mov     edx, r12d
0x1800162c2  call    WppTraceIndent
0x1800162c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162ce  lea     rsi, WPP_GLOBAL_Control
0x1800162d5  cmp     rcx, rsi
0x1800162d8  jz      short loc_180016306
0x1800162da  test    byte ptr [rcx+1Ch], 1
0x1800162de  jz      short loc_180016306
0x1800162e0  cmp     [rcx+19h], r12b
0x1800162e4  jb      short loc_180016306
0x1800162e6  mov     edx, 43h ; 'C'
0x1800162eb  mov     r9, cs:WPP_pszIndent
0x1800162f2  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800162f9  mov     rcx, [rcx+10h]
0x1800162fd  mov     [rsp+78h+var_58], ebx
0x180016301  call    WPP_SF_sd
0x180016306  mov     rcx, rdi; lpMem
0x180016309  call    I_FreeCredListItem
0x18001630e  jmp     short loc_18001635A
0x180016310  lea     r8, [rdi+28h]
0x180016314  mov     rcx, rsi
0x180016317  lea     rdx, [rdi+20h]
0x18001631b  call    I_GetTemplateInfoFromCert
0x180016320  lea     r8, [rdi+40h]
0x180016324  mov     rcx, rsi; pCertContext
0x180016327  lea     rdx, [rdi+38h]
0x18001632b  call    I_GetPinInfoFromCertContext
0x180016330  mov     rdx, rdi
0x180016333  mov     rcx, rsi
0x180016336  call    I_GetCertificate_UPN_DN_Hash
0x18001633b  mov     rcx, rsi; pCertContext
0x18001633e  call    cs:__imp_CertDuplicateCertificateContext
0x180016344  mov     [rdi+30h], rax
0x180016348  lea     rsi, WPP_GLOBAL_Control
0x18001634f  mov     rax, [rsp+78h+arg_20]
0x180016357  mov     [rax], rdi
0x18001635a  mov     edx, 1
0x18001635f  call    WppTraceIndent
0x180016364  mov     rcx, cs:WPP_GLOBAL_Control
0x18001636b  cmp     rcx, rsi
0x18001636e  jz      short loc_18001639C
0x180016370  test    [rcx+1Ch], r12b
0x180016374  jz      short loc_18001639C
0x180016376  cmp     byte ptr [rcx+19h], 5
0x18001637a  jb      short loc_18001639C
0x18001637c  mov     r9, cs:WPP_pszIndent
0x180016383  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001638a  mov     rcx, [rcx+10h]
0x18001638e  mov     edx, 44h ; 'D'
0x180016393  mov     [rsp+78h+var_58], ebx
0x180016397  call    WPP_SF_sd
0x18001639c  mov     eax, ebx
0x18001639e  add     rsp, 38h
0x1800163a2  pop     r15
0x1800163a4  pop     r14
0x1800163a6  pop     r13
0x1800163a8  pop     r12
0x1800163aa  pop     rdi
0x1800163ab  pop     rsi
0x1800163ac  pop     rbp
0x1800163ad  pop     rbx
0x1800163ae  retn
```
