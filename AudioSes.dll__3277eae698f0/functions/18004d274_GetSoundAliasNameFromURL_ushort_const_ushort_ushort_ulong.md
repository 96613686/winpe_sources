# GetSoundAliasNameFromURL(ushort const *,ushort * *,ushort * *,ulong *)

- ea: `0x18004d274`
- end: `0x18004d5cf`
- name: `?GetSoundAliasNameFromURL@@YAJPEBGPEAPEAG1PEAK@Z`
- size: `859`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004d180`

## callees

- `0x1800366fc`
- `0x18004d22c`
- `0x18004d274`
- `0x18004d664`
- `0x18004d700`
- `0x180087e80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004d540`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004d556`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004d540`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004d556`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18004d509`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18004d509`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004d2d7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004d3fa`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004d2d7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004d3fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004d2c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004d432`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004d458`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004d2c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004d432`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004d458`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004d4d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004d4d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004d4b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004d4b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d39a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d3a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d3cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d3d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d584`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d5b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d39a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d3a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d3cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d3d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d584`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d5b4`

## pseudocode

```c
__int64 __fastcall GetSoundAliasNameFromURL(
        const unsigned __int16 *a1,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  const unsigned __int16 *v6; // r12
  wchar_t *v7; // rax
  wchar_t *v8; // r14
  unsigned __int64 v9; // rdi
  int v11; // r15d
  unsigned __int16 *v12; // rbx
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // rcx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // r11
  int v17; // eax
  int v18; // edi
  unsigned __int16 **v19; // rax
  wchar_t *v20; // rsi
  __int64 v21; // rbx
  __int64 v22; // rax
  int v23; // ecx
  __int64 v24; // rbx
  HMODULE ModuleHandleW; // rax
  bool v26; // zf
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rbx
  unsigned __int64 v29; // rdx
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 **v32; // [rsp+60h] [rbp-A0h]
  unsigned int *v33; // [rsp+68h] [rbp-98h]
  wchar_t v34[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Filename[264]; // [rsp+280h] [rbp+180h] BYREF

  v32 = a3;
  v33 = a4;
  if ( (unsigned int)_o__wcsnicmp(L"ms-winsoundevent:", a1, 17) )
    return 2147942487LL;
  v6 = a1 + 17;
  v7 = wcschr(a1 + 17, 0x3Fu);
  v8 = v7;
  if ( v7 )
  {
    v9 = v7 - v6;
  }
  else
  {
    v9 = -1;
    do
      ++v9;
    while ( v6[v9] );
  }
  if ( !v9 )
    return 2147942487LL;
  v11 = 2;
  if ( v9 >= 0x104 )
    return 2147942487LL;
  while ( v8 )
  {
    v20 = v8 + 1;
    v8 = wcschr(v8 + 1, 0x26u);
    if ( v8 )
    {
      v21 = v8 - v20;
    }
    else
    {
      v21 = -1;
      do
        ++v21;
      while ( v20[v21] );
    }
    if ( (unsigned int)_o__wcsnicmp(v20, L"application", 11) )
    {
      if ( (unsigned int)_o__wcsnicmp(v20, L"sentry", 6) )
        return 2147942487LL;
      v22 = 6;
      v23 = -524289;
    }
    else
    {
      v22 = 11;
      v23 = -129;
    }
    v24 = v21 - 11;
    if ( v24 && (v20[v22] != 61 || v24 != 2 || v20[v22 + 1] != 48) )
      return 2147942487LL;
    v11 &= v23;
  }
  v12 = 0;
  pv = 0;
  if ( (v11 & 0x80u) == 0 )
    goto LABEL_10;
  v31 = 0;
  Filename[0] = 0;
  v11 &= ~0x80u;
  v34[0] = 0;
  ModuleHandleW = GetModuleHandleW(0);
  if ( GetModuleFileNameW(ModuleHandleW, Filename, 0x104u) )
    _wsplitpath_s(Filename, 0, 0, 0, 0, v34, 0x104u, 0, 0);
  if ( !v34[0] || (unsigned int)StringCchLengthW(v34, 0x104u, &v31) )
  {
LABEL_10:
    v13 = v9 + 1;
    if ( v13 )
    {
      if ( 0xFFFFFFFFFFFFFFFFuLL / v13 < 2 )
      {
        v16 = 0;
        goto LABEL_46;
      }
      v14 = 2 * v13;
    }
    else
    {
      v14 = 0;
    }
    v15 = (unsigned __int16 *)ATL::CComAllocator::Allocate(v14);
    v16 = v15;
    if ( v15 )
    {
      v17 = StringCchCopyW(v15, v13, v6);
      v18 = 0;
      if ( v17 == -2147024774 )
        v18 = -2147024774;
      if ( v18 >= 0 )
      {
        v19 = v32;
        *a2 = v16;
        *v19 = v12;
        *v33 = v11;
        CoTaskMemFree(0);
        CoTaskMemFree(0);
        return 0;
      }
LABEL_17:
      CoTaskMemFree(v16);
      CoTaskMemFree(v12);
      return (unsigned int)v18;
    }
LABEL_46:
    v18 = -2147024882;
    goto LABEL_17;
  }
  if ( !(unsigned int)_o__wcsicmp(v34, L"iexplore")
    || (v26 = (unsigned int)_o__wcsicmp(v34, L"miexplore") == 0, v27 = v31, v26) )
  {
    v27 = 8;
  }
  v28 = v27 + 1;
  if ( (unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CComAllocator>::Allocate(&pv, v27 + 1) )
  {
    v29 = v28;
    v12 = (unsigned __int16 *)pv;
    if ( StringCchCopyW((unsigned __int16 *)pv, v29, v34) )
    {
      CoTaskMemFree(v12);
      v12 = 0;
    }
    goto LABEL_10;
  }
  CoTaskMemFree(pv);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18004d274  push    rbp
0x18004d276  push    rbx
0x18004d277  push    rsi
0x18004d278  push    rdi
0x18004d279  push    r12
0x18004d27b  push    r13
0x18004d27d  push    r14
0x18004d27f  push    r15
0x18004d281  lea     rbp, [rsp-3A8h]
0x18004d289  sub     rsp, 4A8h
0x18004d290  mov     rax, cs:__security_cookie
0x18004d297  xor     rax, rsp
0x18004d29a  mov     [rbp+3E0h+var_50], rax
0x18004d2a1  mov     r13, rdx
0x18004d2a4  mov     [rsp+4E0h+var_480], r8
0x18004d2a9  mov     rdx, rcx
0x18004d2ac  mov     [rsp+4E0h+var_478], r9
0x18004d2b1  mov     rbx, rcx
0x18004d2b4  mov     r8d, 11h
0x18004d2ba  lea     rcx, aMsWinsoundeven; "ms-winsoundevent:"
0x18004d2c1  call    cs:__imp__o__wcsnicmp
0x18004d2c7  xor     esi, esi
0x18004d2c9  test    eax, eax
0x18004d2cb  jnz     short loc_18004D2FC
0x18004d2cd  lea     r12, [rbx+22h]
0x18004d2d1  mov     rcx, r12; Str
0x18004d2d4  lea     edx, [rsi+3Fh]; Ch
0x18004d2d7  call    cs:__imp_wcschr
0x18004d2dd  mov     r14, rax
0x18004d2e0  test    rax, rax
0x18004d2e3  jnz     loc_18004D3E0
0x18004d2e9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004d2ed  inc     rdi
0x18004d2f0  cmp     [r12+rdi*2], si
0x18004d2f5  jnz     short loc_18004D2ED
0x18004d2f7  test    rdi, rdi
0x18004d2fa  jnz     short loc_18004D324
0x18004d2fc  mov     eax, 80070057h
0x18004d301  mov     rcx, [rbp+3E0h+var_50]
0x18004d308  xor     rcx, rsp; StackCookie
0x18004d30b  call    __security_check_cookie
0x18004d310  add     rsp, 4A8h
0x18004d317  pop     r15
0x18004d319  pop     r14
0x18004d31b  pop     r13
0x18004d31d  pop     r12
0x18004d31f  pop     rdi
0x18004d320  pop     rsi
0x18004d321  pop     rbx
0x18004d322  pop     rbp
0x18004d323  retn
0x18004d324  mov     r15d, 2
0x18004d32a  cmp     rdi, 104h
0x18004d331  jnb     short loc_18004D2FC
0x18004d333  test    r14, r14
0x18004d336  jnz     loc_18004D3EE
0x18004d33c  mov     rbx, rsi
0x18004d33f  mov     [rsp+4E0h+pv], rbx
0x18004d344  test    r15b, r15b
0x18004d347  js      loc_18004D4A1
0x18004d34d  add     rdi, 1
0x18004d351  jz      short loc_18004D3B0
0x18004d353  xor     edx, edx
0x18004d355  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004d359  div     rdi
0x18004d35c  cmp     rax, 2
0x18004d360  jb      loc_18004D5C2
0x18004d366  lea     rcx, [rdi+rdi]; unsigned __int64
0x18004d36a  call    ?Allocate@CComAllocator@ATL@@SAPEAX_K@Z; ATL::CComAllocator::Allocate(unsigned __int64)
0x18004d36f  mov     r11, rax
0x18004d372  test    rax, rax
0x18004d375  jz      loc_18004D5C5
0x18004d37b  mov     r8, r12; unsigned __int16 *
0x18004d37e  mov     rdx, rdi; unsigned __int64
0x18004d381  mov     rcx, rax; unsigned __int16 *
0x18004d384  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004d389  cmp     eax, 8007007Ah
0x18004d38e  mov     edi, esi
0x18004d390  cmovz   edi, eax
0x18004d393  test    edi, edi
0x18004d395  jns     short loc_18004D3B5
0x18004d397  mov     rcx, r11; pv
0x18004d39a  call    cs:__imp_CoTaskMemFree
0x18004d3a0  mov     rcx, rbx; pv
0x18004d3a3  call    cs:__imp_CoTaskMemFree
0x18004d3a9  mov     eax, edi
0x18004d3ab  jmp     loc_18004D301
0x18004d3b0  mov     rcx, rsi
0x18004d3b3  jmp     short loc_18004D36A
0x18004d3b5  mov     rax, [rsp+4E0h+var_480]
0x18004d3ba  xor     ecx, ecx; pv
0x18004d3bc  mov     [r13+0], r11
0x18004d3c0  mov     [rax], rbx
0x18004d3c3  mov     rax, [rsp+4E0h+var_478]
0x18004d3c8  mov     [rax], r15d
0x18004d3cb  call    cs:__imp_CoTaskMemFree
0x18004d3d1  xor     ecx, ecx; pv
0x18004d3d3  call    cs:__imp_CoTaskMemFree
0x18004d3d9  xor     eax, eax
0x18004d3db  jmp     loc_18004D301
0x18004d3e0  mov     rdi, rax
0x18004d3e3  sub     rdi, r12
0x18004d3e6  sar     rdi, 1
0x18004d3e9  jmp     loc_18004D2F7
0x18004d3ee  lea     rsi, [r14+2]
0x18004d3f2  mov     edx, 26h ; '&'; Ch
0x18004d3f7  mov     rcx, rsi; Str
0x18004d3fa  call    cs:__imp_wcschr
0x18004d400  mov     r14, rax
0x18004d403  xor     eax, eax
0x18004d405  test    r14, r14
0x18004d408  jz      short loc_18004D415
0x18004d40a  mov     rbx, r14
0x18004d40d  sub     rbx, rsi
0x18004d410  sar     rbx, 1
0x18004d413  jmp     short loc_18004D422
0x18004d415  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004d419  inc     rbx
0x18004d41c  cmp     [rsi+rbx*2], ax
0x18004d420  jnz     short loc_18004D419
0x18004d422  mov     r8d, 0Bh
0x18004d428  lea     rdx, aApplication; "application"
0x18004d42f  mov     rcx, rsi
0x18004d432  call    cs:__imp__o__wcsnicmp
0x18004d438  test    eax, eax
0x18004d43a  jnz     short loc_18004D448
0x18004d43c  mov     eax, 16h
0x18004d441  mov     ecx, 0FFFFFF7Fh
0x18004d446  jmp     short loc_18004D470
0x18004d448  mov     r8d, 6
0x18004d44e  lea     rdx, aSentry; "sentry"
0x18004d455  mov     rcx, rsi
0x18004d458  call    cs:__imp__o__wcsnicmp
0x18004d45e  test    eax, eax
0x18004d460  jnz     loc_18004D2FC
0x18004d466  mov     eax, 0Ch
0x18004d46b  mov     ecx, 0FFF7FFFFh
0x18004d470  add     rbx, 0FFFFFFFFFFFFFFF5h
0x18004d474  jz      short loc_18004D497
0x18004d476  cmp     word ptr [rsi+rax], 3Dh ; '='
0x18004d47b  jnz     loc_18004D2FC
0x18004d481  cmp     rbx, 2
0x18004d485  jnz     loc_18004D2FC
0x18004d48b  cmp     word ptr [rsi+rax+2], 30h ; '0'
0x18004d491  jnz     loc_18004D2FC
0x18004d497  and     r15d, ecx
0x18004d49a  xor     esi, esi
0x18004d49c  jmp     loc_18004D333
0x18004d4a1  xor     ecx, ecx; lpModuleName
0x18004d4a3  mov     [rsp+4E0h+var_488], rsi
0x18004d4a8  mov     [rbp+3E0h+Filename], si
0x18004d4af  btr     r15d, 7
0x18004d4b4  mov     [rsp+4E0h+var_470], si
0x18004d4b9  call    cs:__imp_GetModuleHandleW
0x18004d4bf  mov     r14d, 104h
0x18004d4c5  lea     rdx, [rbp+3E0h+Filename]; lpFilename
0x18004d4cc  mov     rcx, rax; hModule
0x18004d4cf  mov     r8d, r14d; nSize
0x18004d4d2  call    cs:__imp_GetModuleFileNameW
0x18004d4d8  test    eax, eax
0x18004d4da  jz      short loc_18004D50F
0x18004d4dc  mov     [rsp+4E0h+ExtCount], rsi; ExtCount
0x18004d4e1  lea     rax, [rsp+4E0h+var_470]
0x18004d4e6  mov     [rsp+4E0h+Ext], rsi; Ext
0x18004d4eb  lea     rcx, [rbp+3E0h+Filename]; FullPath
0x18004d4f2  mov     [rsp+4E0h+FilenameCount], r14; FilenameCount
0x18004d4f7  xor     r9d, r9d; Dir
0x18004d4fa  mov     [rsp+4E0h+var_4B8], rax; Filename
0x18004d4ff  xor     r8d, r8d; DriveCount
0x18004d502  xor     edx, edx; Drive
0x18004d504  mov     [rsp+4E0h+DirCount], rsi; DirCount
0x18004d509  call    cs:__imp__wsplitpath_s
0x18004d50f  cmp     [rsp+4E0h+var_470], si
0x18004d514  jz      loc_18004D34D
0x18004d51a  lea     r8, [rsp+4E0h+var_488]; unsigned __int64 *
0x18004d51f  mov     rdx, r14; unsigned __int64
0x18004d522  lea     rcx, [rsp+4E0h+var_470]; unsigned __int16 *
0x18004d527  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004d52c  test    eax, eax
0x18004d52e  jnz     loc_18004D34D
0x18004d534  lea     rdx, aIexplore; "iexplore"
0x18004d53b  lea     rcx, [rsp+4E0h+var_470]
0x18004d540  call    cs:__imp__o__wcsicmp
0x18004d546  test    eax, eax
0x18004d548  jz      short loc_18004D565
0x18004d54a  lea     rdx, aMiexplore; "miexplore"
0x18004d551  lea     rcx, [rsp+4E0h+var_470]
0x18004d556  call    cs:__imp__o__wcsicmp
0x18004d55c  test    eax, eax
0x18004d55e  mov     rax, [rsp+4E0h+var_488]
0x18004d563  jnz     short loc_18004D56A
0x18004d565  mov     eax, 8
0x18004d56a  lea     rbx, [rax+1]
0x18004d56e  mov     rdx, rbx
0x18004d571  lea     rcx, [rsp+4E0h+pv]
0x18004d576  call    ?Allocate@?$CHeapPtr@GVCComAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CComAllocator>::Allocate(unsigned __int64)
0x18004d57b  test    al, al
0x18004d57d  jnz     short loc_18004D594
0x18004d57f  mov     rcx, [rsp+4E0h+pv]; pv
0x18004d584  call    cs:__imp_CoTaskMemFree
0x18004d58a  mov     eax, 8007000Eh
0x18004d58f  jmp     loc_18004D301
0x18004d594  mov     rdx, rbx; unsigned __int64
0x18004d597  lea     r8, [rsp+4E0h+var_470]; unsigned __int16 *
0x18004d59c  mov     rbx, [rsp+4E0h+pv]
0x18004d5a1  mov     rcx, rbx; unsigned __int16 *
0x18004d5a4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004d5a9  test    eax, eax
0x18004d5ab  jz      loc_18004D34D
0x18004d5b1  mov     rcx, rbx; pv
0x18004d5b4  call    cs:__imp_CoTaskMemFree
0x18004d5ba  mov     rbx, rsi
0x18004d5bd  jmp     loc_18004D34D
0x18004d5c2  mov     r11, rsi
0x18004d5c5  mov     edi, 8007000Eh
0x18004d5ca  jmp     loc_18004D397
```
