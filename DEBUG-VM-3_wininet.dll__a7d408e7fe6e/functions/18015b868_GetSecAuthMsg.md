# GetSecAuthMsg

- ea: `0x18015b868`
- end: `0x18015bbde`
- name: `GetSecAuthMsg`
- size: `886`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, SIZE_T dwBytes, char *, __int64, __int64, int, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800e79c4`
- `0x180158e90`
- `0x1801591f4`

## callees

- `0x18000b8b4`
- `0x1800353ec`
- `0x1800e5a6c`
- `0x18014a7a0`
- `0x180159798`
- `0x18015b868`
- `0x18015bbe4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015bb36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015bb36`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18015b946`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18015b9b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18015b946`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18015b9b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18015bb98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18015bbaf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18015bb98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18015bbaf`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18015ba28`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18015ba50`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18015ba28`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18015ba50`
- `SspiCli!InitializeSecurityContextW` at `0x18015bae4`
- `SspiCli!InitializeSecurityContextW` at `0x18015bae4`
- `ext-ms-win-security-credui-l1-1-0!SspiIsPromptingNeeded` at `0x18015bb24`
- `ext-ms-win-security-credui-l1-1-0!SspiIsPromptingNeeded` at `0x18015bb24`

## pseudocode

```c
__int64 __fastcall GetSecAuthMsg(
        __int64 a1,
        unsigned int a2,
        struct _SecHandle *a3,
        __int64 a4,
        __int64 a5,
        SIZE_T dwBytes,
        char *a7,
        _DWORD *a8,
        SEC_WCHAR *a9,
        int a10,
        const CHAR *a11,
        const CHAR *a12,
        SECURITY_STATUS *a13)
{
  unsigned int v13; // r14d
  unsigned int PkgMaxToken; // r12d
  LPVOID v17; // rax
  unsigned int v18; // ebx
  void *v19; // r15
  __int64 v20; // rax
  HANDLE v21; // rcx
  __int64 v22; // rbx
  LPVOID v23; // rax
  int v24; // ecx
  __int64 v25; // rdi
  int v26; // r12d
  int v27; // r14d
  unsigned int v28; // r9d
  SECURITY_STATUS v29; // r14d
  int v30; // eax
  void *lpMem; // [rsp+A0h] [rbp-60h]
  _DWORD v34[2]; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v35; // [rsp+B0h] [rbp-50h]
  __int128 v36; // [rsp+B8h] [rbp-48h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int pfContextAttr; // [rsp+D8h] [rbp-28h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+E0h] [rbp-20h] BYREF
  int v40; // [rsp+E8h] [rbp-18h] BYREF
  int v41; // [rsp+ECh] [rbp-14h]
  _QWORD v42[3]; // [rsp+F0h] [rbp-10h]

  v13 = 0;
  ptsExpiry.QuadPart = 0;
  v35 = 0;
  pfContextAttr = 0;
  v36 = 0;
  if ( !a7 )
    return 1;
  pOutput.ulVersion = 0;
  pOutput.pBuffers = (PSecBuffer)v34;
  pOutput.cBuffers = 1;
  v34[0] = 10000;
  v34[1] = 2;
  PkgMaxToken = GetPkgMaxToken(a2);
  v17 = HeapAlloc(g_hWxProcessHeap, 0, PkgMaxToken);
  lpMem = v17;
  if ( v17 )
  {
    v35 = v17;
    v19 = 0;
    v20 = *(_QWORD *)(a1 + 120);
    v34[0] = PkgMaxToken;
    if ( v20 )
    {
      v42[0] = v20;
      v13 = 1;
      v40 = *(_DWORD *)(a1 + 128);
      v41 = 14;
    }
    if ( a5 && (_DWORD)dwBytes )
    {
      v21 = g_hWxProcessHeap;
      v22 = 2LL * v13;
      *(&v41 + 4 * v13) = 2;
      v23 = HeapAlloc(v21, 0, (unsigned int)dwBytes);
      v19 = v23;
      if ( !v23 )
      {
        v18 = 3;
LABEL_32:
        HeapFree(g_hWxProcessHeap, 0, lpMem);
        if ( v19 )
          HeapFree(g_hWxProcessHeap, 0, v19);
        return v18;
      }
      *(&v40 + 4 * v13++) = HTUU_decode(v24, a5, dwBytes, (_DWORD)v23, dwBytes);
      v42[v22] = v19;
    }
    LODWORD(v36) = 0;
    *((_QWORD *)&v36 + 1) = &v40;
    v25 = -1;
    v26 = 1;
    DWORD1(v36) = v13;
    v18 = 3;
    if ( a11
      && (CompareStringA(0x7Fu, 1u, a11, -1, "Negotiate", -1) == 2
       || CompareStringA(0x7Fu, 1u, a11, -1, "Nego2", -1) == 2) )
    {
      v26 = 3;
    }
    if ( (unsigned int)GetZoneFromUrl(a12) - 1 > 1 )
      v26 &= ~1u;
    v27 = -v13;
    v28 = v26 | 0x20000000;
    if ( a10 )
      v28 = v26;
    v29 = InitializeSecurityContextW(
            *(PCredHandle *)(a1 + 72),
            a3,
            a9,
            v28,
            0,
            0x10u,
            (PSecBufferDesc)((unsigned __int64)&v36 & -(__int64)(v27 != 0)),
            0,
            (PCtxtHandle)(a1 + 80),
            &pOutput,
            &pfContextAttr,
            &ptsExpiry);
    *a13 = v29;
    if ( v29 >= 0 )
    {
      if ( (int)StringCchPrintfA(a7, (unsigned int)*a8, "%s ", a11) >= 0 )
      {
        do
          ++v25;
        while ( a7[v25] );
        v30 = HTUU_encode(0, (_DWORD)v35, v34[0], (int)v25 + (int)a7, *a8 - (int)v25);
        if ( v30 > 0 )
        {
          v18 = 0;
          *a8 = v25 + v30;
        }
      }
    }
    else
    {
      if ( v29 == -2146893042
        || v29 == -2146893048 && *(_DWORD *)(a1 + 52)
        || v29 == -2146893044
        || (v18 = 1, SspiIsPromptingNeeded(v29)) )
      {
        v18 = 2;
      }
      SetLastError(v29);
    }
    goto LABEL_32;
  }
  return 3;
}

```

## disassembly

```asm
0x18015b868  mov     [rsp-8+arg_18], rbx
0x18015b86d  push    rbp
0x18015b86e  push    rsi
0x18015b86f  push    rdi
0x18015b870  push    r12
0x18015b872  push    r13
0x18015b874  push    r14
0x18015b876  push    r15
0x18015b878  lea     rbp, [rsp-10h]
0x18015b87d  sub     rsp, 110h
0x18015b884  mov     rax, cs:__security_cookie
0x18015b88b  xor     rax, rsp
0x18015b88e  mov     [rbp+40h+var_38], rax
0x18015b892  mov     rax, [rbp+40h+arg_20]
0x18015b896  xor     r14d, r14d
0x18015b899  mov     r13, [rbp+40h+arg_30]
0x18015b8a0  xorps   xmm0, xmm0
0x18015b8a3  mov     edi, dword ptr [rbp+40h+dwBytes]
0x18015b8a6  mov     rbx, rcx
0x18015b8a9  mov     [rsp+140h+var_D0], rax
0x18015b8ae  mov     rax, [rbp+40h+arg_38]
0x18015b8b5  mov     [rbp+40h+var_A8], rax
0x18015b8b9  mov     rax, [rbp+40h+arg_40]
0x18015b8c0  mov     [rbp+40h+pszTargetName], rax
0x18015b8c4  mov     rax, [rbp+40h+arg_50]
0x18015b8cb  mov     [rsp+140h+lpString1], rax
0x18015b8d0  mov     rax, [rbp+40h+arg_58]
0x18015b8d7  mov     [rsp+140h+lpMultiByteStr], rax
0x18015b8dc  mov     rax, [rbp+40h+arg_60]
0x18015b8e3  mov     [rbp+40h+var_B0], rax
0x18015b8e7  mov     [rbp+40h+phContext], r8
0x18015b8eb  mov     [rsp+140h+var_D8], rcx
0x18015b8f0  mov     qword ptr [rbp+40h+var_60], r14
0x18015b8f4  mov     [rbp+40h+var_90], r14
0x18015b8f8  mov     [rbp+40h+var_68], r14d
0x18015b8fc  movups  [rbp+40h+var_88], xmm0
0x18015b900  test    r13, r13
0x18015b903  jnz     short loc_18015B90E
0x18015b905  lea     eax, [r13+1]
0x18015b909  jmp     loc_18015BBB7
0x18015b90e  lea     rax, [rbp+40h+var_98]
0x18015b912  mov     [rbp+40h+var_78.ulVersion], r14d
0x18015b916  mov     esi, 1
0x18015b91b  mov     [rbp+40h+var_78.pBuffers], rax
0x18015b91f  mov     ecx, edx
0x18015b921  mov     [rbp+40h+var_78.cBuffers], esi
0x18015b924  mov     [rbp+40h+var_98], 2710h
0x18015b92b  mov     [rbp+40h+var_94], 2
0x18015b932  call    GetPkgMaxToken
0x18015b937  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18015b93e  xor     edx, edx; dwFlags
0x18015b940  mov     r8d, eax; dwBytes
0x18015b943  mov     r12d, eax
0x18015b946  call    cs:__imp_HeapAlloc
0x18015b94c  mov     [rbp+40h+lpMem], rax
0x18015b950  test    rax, rax
0x18015b953  jnz     short loc_18015B95D
0x18015b955  lea     ebx, [rsi+2]
0x18015b958  jmp     loc_18015BBB5
0x18015b95d  mov     [rbp+40h+var_90], rax
0x18015b961  mov     r15, r14
0x18015b964  mov     rax, [rbx+78h]
0x18015b968  mov     [rbp+40h+var_98], r12d
0x18015b96c  test    rax, rax
0x18015b96f  jz      short loc_18015B988
0x18015b971  mov     [rbp+40h+var_50], rax
0x18015b975  mov     r14d, esi
0x18015b978  mov     eax, [rbx+80h]
0x18015b97e  mov     [rbp+40h+var_58], eax
0x18015b981  mov     [rbp+40h+var_54], 0Eh
0x18015b988  mov     r12, [rsp+140h+var_D0]
0x18015b98d  test    r12, r12
0x18015b990  jz      short loc_18015B9E4
0x18015b992  test    edi, edi
0x18015b994  jz      short loc_18015B9E4
0x18015b996  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18015b99d  mov     r8, rdi; dwBytes
0x18015b9a0  mov     ebx, r14d
0x18015b9a3  xor     edx, edx; dwFlags
0x18015b9a5  add     rbx, rbx
0x18015b9a8  mov     [rbp+rbx*8+40h+var_54], 2
0x18015b9b0  call    cs:__imp_HeapAlloc
0x18015b9b6  mov     r15, rax
0x18015b9b9  test    rax, rax
0x18015b9bc  jnz     short loc_18015B9C6
0x18015b9be  lea     ebx, [rax+3]
0x18015b9c1  jmp     loc_18015BB8B
0x18015b9c6  mov     r9, r15
0x18015b9c9  mov     dword ptr [rsp+140h+lpString2], edi
0x18015b9cd  mov     r8d, edi
0x18015b9d0  mov     rdx, r12
0x18015b9d3  call    HTUU_decode
0x18015b9d8  mov     [rbp+rbx*8+40h+var_58], eax
0x18015b9dc  add     r14d, esi
0x18015b9df  mov     [rbp+rbx*8+40h+var_50], r15
0x18015b9e4  lea     rax, [rbp+40h+var_58]
0x18015b9e8  mov     dword ptr [rbp+40h+var_88], 0
0x18015b9ef  mov     qword ptr [rbp+40h+var_88+8], rax
0x18015b9f3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18015b9f7  mov     rax, [rsp+140h+lpString1]
0x18015b9fc  mov     r12d, esi
0x18015b9ff  mov     dword ptr [rbp+40h+var_88+4], r14d
0x18015ba03  mov     ebx, 3
0x18015ba08  test    rax, rax
0x18015ba0b  jz      short loc_18015BA5E
0x18015ba0d  lea     rcx, aNegotiate_1; "Negotiate"
0x18015ba14  mov     [rsp+140h+cchCount2], edi; cchCount2
0x18015ba18  mov     [rsp+140h+lpString2], rcx; lpString2
0x18015ba1d  mov     r9d, edi; cchCount1
0x18015ba20  lea     ecx, [rbx+7Ch]; Locale
0x18015ba23  mov     r8, rax; lpString1
0x18015ba26  mov     edx, esi; dwCmpFlags
0x18015ba28  call    cs:__imp_CompareStringA
0x18015ba2e  cmp     eax, 2
0x18015ba31  jz      short loc_18015BA5B
0x18015ba33  mov     r8, [rsp+140h+lpString1]; lpString1
0x18015ba38  lea     rax, aNego2; "Nego2"
0x18015ba3f  mov     [rsp+140h+cchCount2], edi; cchCount2
0x18015ba43  lea     ecx, [rbx+7Ch]; Locale
0x18015ba46  mov     r9d, edi; cchCount1
0x18015ba49  mov     [rsp+140h+lpString2], rax; lpString2
0x18015ba4e  mov     edx, esi; dwCmpFlags
0x18015ba50  call    cs:__imp_CompareStringA
0x18015ba56  cmp     eax, 2
0x18015ba59  jnz     short loc_18015BA5E
0x18015ba5b  mov     r12d, ebx
0x18015ba5e  mov     rcx, [rsp+140h+lpMultiByteStr]; lpMultiByteStr
0x18015ba63  call    GetZoneFromUrl
0x18015ba68  dec     eax
0x18015ba6a  cmp     eax, esi
0x18015ba6c  jbe     short loc_18015BA72
0x18015ba6e  and     r12d, 0FFFFFFFEh
0x18015ba72  mov     r10, [rsp+140h+var_D8]
0x18015ba77  lea     rdx, [rbp+40h+var_88]
0x18015ba7b  mov     r8, [rbp+40h+pszTargetName]; pszTargetName
0x18015ba7f  neg     r14d
0x18015ba82  mov     r9d, r12d
0x18015ba85  sbb     rax, rax
0x18015ba88  bts     r9d, 1Dh
0x18015ba8d  and     rax, rdx
0x18015ba90  lea     rcx, [r10+50h]
0x18015ba94  cmp     [rbp+40h+arg_48], 0
0x18015ba9b  lea     rdx, [rbp+40h+var_60]
0x18015ba9f  mov     [rsp+140h+ptsExpiry], rdx; ptsExpiry
0x18015baa4  lea     rdx, [rbp+40h+var_68]
0x18015baa8  mov     [rsp+140h+pfContextAttr], rdx; pfContextAttr
0x18015baad  cmovnz  r9d, r12d; fContextReq
0x18015bab1  lea     rdx, [rbp+40h+var_78]
0x18015bab5  mov     [rsp+140h+pOutput], rdx; pOutput
0x18015baba  mov     rdx, [rbp+40h+phContext]; phContext
0x18015babe  mov     [rsp+140h+phNewContext], rcx; phNewContext
0x18015bac3  mov     rcx, [r10+48h]; phCredential
0x18015bac7  mov     [rsp+140h+Reserved2], 0; Reserved2
0x18015bacf  mov     [rsp+140h+pInput], rax; pInput
0x18015bad4  mov     [rsp+140h+cchCount2], 10h; TargetDataRep
0x18015badc  mov     dword ptr [rsp+140h+lpString2], 0; Reserved1
0x18015bae4  call    cs:__imp_InitializeSecurityContextW
0x18015baea  mov     r14d, eax
0x18015baed  mov     rax, [rbp+40h+var_B0]
0x18015baf1  mov     [rax], r14d
0x18015baf4  test    r14d, r14d
0x18015baf7  jns     short loc_18015BB3E
0x18015baf9  cmp     r14d, 8009030Eh
0x18015bb00  jz      short loc_18015BB2E
0x18015bb02  cmp     r14d, 80090308h
0x18015bb09  jnz     short loc_18015BB16
0x18015bb0b  mov     rax, [rsp+140h+var_D8]
0x18015bb10  cmp     dword ptr [rax+34h], 0
0x18015bb14  jnz     short loc_18015BB2E
0x18015bb16  cmp     r14d, 8009030Ch
0x18015bb1d  jz      short loc_18015BB2E
0x18015bb1f  mov     ecx, r14d; ErrorOrNtStatus
0x18015bb22  mov     ebx, esi
0x18015bb24  call    cs:__imp_SspiIsPromptingNeeded
0x18015bb2a  test    al, al
0x18015bb2c  jz      short loc_18015BB33
0x18015bb2e  mov     ebx, 2
0x18015bb33  mov     ecx, r14d; dwErrCode
0x18015bb36  call    cs:__imp_SetLastError
0x18015bb3c  jmp     short loc_18015BB8B
0x18015bb3e  mov     rsi, [rbp+40h+var_A8]
0x18015bb42  lea     r8, aS; "%s "
0x18015bb49  mov     r9, [rsp+140h+lpString1]
0x18015bb4e  mov     rcx, r13; char *
0x18015bb51  mov     edx, [rsi]; unsigned __int64
0x18015bb53  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18015bb58  test    eax, eax
0x18015bb5a  js      short loc_18015BB8B
0x18015bb5c  inc     rdi
0x18015bb5f  cmp     byte ptr [rdi+r13], 0
0x18015bb64  jnz     short loc_18015BB5C
0x18015bb66  mov     eax, [rsi]
0x18015bb68  lea     r9, [rdi+r13]
0x18015bb6c  mov     r8d, [rbp+40h+var_98]
0x18015bb70  sub     eax, edi
0x18015bb72  mov     rdx, [rbp+40h+var_90]
0x18015bb76  xor     ecx, ecx
0x18015bb78  mov     dword ptr [rsp+140h+lpString2], eax
0x18015bb7c  call    HTUU_encode
0x18015bb81  test    eax, eax
0x18015bb83  jle     short loc_18015BB8B
0x18015bb85  xor     ebx, ebx
0x18015bb87  add     eax, edi
0x18015bb89  mov     [rsi], eax
0x18015bb8b  mov     r8, [rbp+40h+lpMem]; lpMem
0x18015bb8f  xor     edx, edx; dwFlags
0x18015bb91  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18015bb98  call    cs:__imp_HeapFree
0x18015bb9e  test    r15, r15
0x18015bba1  jz      short loc_18015BBB5
0x18015bba3  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18015bbaa  mov     r8, r15; lpMem
0x18015bbad  xor     edx, edx; dwFlags
0x18015bbaf  call    cs:__imp_HeapFree
0x18015bbb5  mov     eax, ebx
0x18015bbb7  mov     rcx, [rbp+40h+var_38]
0x18015bbbb  xor     rcx, rsp; StackCookie
0x18015bbbe  call    __security_check_cookie
0x18015bbc3  mov     rbx, [rsp+140h+arg_18]
0x18015bbcb  add     rsp, 110h
0x18015bbd2  pop     r15
0x18015bbd4  pop     r14
0x18015bbd6  pop     r13
0x18015bbd8  pop     r12
0x18015bbda  pop     rdi
0x18015bbdb  pop     rsi
0x18015bbdc  pop     rbp
0x18015bbdd  retn
```
