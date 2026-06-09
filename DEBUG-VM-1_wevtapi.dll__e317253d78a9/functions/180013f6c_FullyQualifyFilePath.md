# FullyQualifyFilePath

- ea: `0x180013f6c`
- end: `0x1800142c3`
- name: `FullyQualifyFilePath`
- size: `855`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000cb00`
- `0x1800142d0`
- `0x18001cb20`
- `0x18001d4f0`
- `0x180025cb0`
- `0x180025f90`

## callees

- `0x18000a100`
- `0x18000c404`
- `0x18000f378`
- `0x180013cc4`
- `0x180013d60`
- `0x180013f6c`
- `0x180023548`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001409c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001409c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141af`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180014090`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800141a5`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180014090`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800141a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FullyQualifyFilePath(__int64 a1, const WCHAR *a2)
{
  unsigned int v3; // eax
  int v4; // edi
  DWORD FullPathNameW; // eax
  __int64 v6; // rdi
  DWORD LastError; // ebx
  DWORD v8; // eax
  DWORD v9; // ebx
  LPWSTR lpBuffer[2]; // [rsp+20h] [rbp-58h] BYREF
  char v11; // [rsp+30h] [rbp-48h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-38h] BYREF
  __int64 v13; // [rsp+50h] [rbp-28h]
  int v14; // [rsp+58h] [rbp-20h]
  __int64 v15; // [rsp+5Ch] [rbp-1Ch]
  char v16; // [rsp+64h] [rbp-14h]

  if ( !a2 || !*a2 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
    }
    pExceptionObject = 0;
    v13 = 0;
    v14 = 87;
    v15 = 0x46FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  v3 = ExpandEnvStringNoThrow(a2);
  v4 = v3;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, v3);
    }
    *(_QWORD *)&pExceptionObject = &word_18004024A;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v13 = 0;
    v14 = v4;
    v15 = -1;
    v16 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( (unsigned __int64)((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 1) <= 1 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
    }
    pExceptionObject = 0;
    v13 = 0;
    v14 = 87;
    v15 = 0x4EFFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  FullPathNameW = GetFullPathNameW(*(LPCWSTR *)a1, 0, 0, 0);
  v6 = FullPathNameW;
  if ( !FullPathNameW )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v13 = 0;
    v14 = LastError;
    v15 = 0x54FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpBuffer);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                           lpBuffer,
                           v6) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 14);
    }
    pExceptionObject = 0;
    v13 = 0;
    v14 = 14;
    v15 = 0x5AFFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  v8 = GetFullPathNameW(*(LPCWSTR *)a1, v6, lpBuffer[0], 0);
  if ( !v8 )
  {
    v9 = GetLastError();
    if ( !v9 )
      v9 = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, v9);
    }
    pExceptionObject = 0;
    v13 = 0;
    v14 = v9;
    v15 = 0x60FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(lpBuffer, v8);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a1, lpBuffer);
  if ( (char *)lpBuffer[0] != &v11 )
    operator delete(lpBuffer[0]);
}

```

## disassembly

```asm
0x180013f6c  push    rbp
0x180013f6e  push    rbx
0x180013f6f  push    rsi
0x180013f70  push    rdi
0x180013f71  mov     rbp, rsp
0x180013f74  sub     rsp, 78h
0x180013f78  mov     rax, rdx
0x180013f7b  mov     rbx, rcx
0x180013f7e  xor     esi, esi
0x180013f80  test    rdx, rdx
0x180013f83  jz      loc_18001425B
0x180013f89  cmp     [rdx], si
0x180013f8c  jz      loc_18001425B
0x180013f92  mov     rdx, rcx
0x180013f95  mov     rcx, rax; lpSrc
0x180013f98  call    ?ExpandEnvStringNoThrow@@YAKPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; ExpandEnvStringNoThrow(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180013f9d  mov     edi, eax
0x180013f9f  test    eax, eax
0x180013fa1  jz      short loc_18001400D
0x180013fa3  lea     rcx, WPP_GLOBAL_Control
0x180013faa  mov     r10, cs:WPP_GLOBAL_Control
0x180013fb1  cmp     r10, rcx
0x180013fb4  jz      short loc_180013FDA
0x180013fb6  test    byte ptr [r10+1Ch], 1
0x180013fbb  jz      short loc_180013FDA
0x180013fbd  cmp     byte ptr [r10+19h], 2
0x180013fc2  jb      short loc_180013FDA
0x180013fc4  lea     edx, [rsi+0Ch]
0x180013fc7  mov     r9d, eax
0x180013fca  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x180013fd1  mov     rcx, [r10+10h]
0x180013fd5  call    WPP_SF_D
0x180013fda  lea     rax, word_18004024A
0x180013fe1  mov     qword ptr [rbp+pExceptionObject], rax
0x180013fe5  mov     qword ptr [rbp+pExceptionObject+8], rsi
0x180013fe9  mov     [rbp+var_28], rsi
0x180013fed  mov     [rbp+var_20], edi
0x180013ff0  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x180013ff8  mov     [rbp+var_14], sil
0x180013ffc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180014003  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180014007  call    _CxxThrowException_0
0x18001400d  mov     rax, [rbx+8]
0x180014011  sub     rax, [rbx]
0x180014014  sar     rax, 1
0x180014017  cmp     rax, 1
0x18001401b  ja      short loc_180014085
0x18001401d  lea     rcx, WPP_GLOBAL_Control
0x180014024  mov     ebx, 57h ; 'W'
0x180014029  mov     rax, cs:WPP_GLOBAL_Control
0x180014030  cmp     rax, rcx
0x180014033  jz      short loc_180014057
0x180014035  test    byte ptr [rax+1Ch], 1
0x180014039  jz      short loc_180014057
0x18001403b  cmp     byte ptr [rax+19h], 2
0x18001403f  jb      short loc_180014057
0x180014041  lea     edx, [rbx-4Ah]
0x180014044  mov     r9d, ebx
0x180014047  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001404e  mov     rcx, [rax+10h]
0x180014052  call    WPP_SF_D
0x180014057  xorps   xmm0, xmm0
0x18001405a  movdqu  [rbp+pExceptionObject], xmm0
0x18001405f  mov     [rbp+var_28], rsi
0x180014063  mov     [rbp+var_20], ebx
0x180014066  mov     dword ptr [rbp+var_1C], 0FFFFFFFFh
0x18001406d  mov     dword ptr [rbp+var_1C+4], 4Eh ; 'N'
0x180014074  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001407b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001407f  call    _CxxThrowException_0
0x180014085  xor     r9d, r9d; lpFilePart
0x180014088  xor     r8d, r8d; lpBuffer
0x18001408b  xor     edx, edx; nBufferLength
0x18001408d  mov     rcx, [rbx]; lpFileName
0x180014090  call    cs:__imp_GetFullPathNameW
0x180014096  mov     edi, eax
0x180014098  test    eax, eax
0x18001409a  jnz     short loc_180014115
0x18001409c  call    cs:__imp_GetLastError
0x1800140a2  mov     ebx, eax
0x1800140a4  mov     eax, 507h
0x1800140a9  test    ebx, ebx
0x1800140ab  cmovz   ebx, eax
0x1800140ae  lea     rcx, WPP_GLOBAL_Control
0x1800140b5  mov     r10, cs:WPP_GLOBAL_Control
0x1800140bc  cmp     r10, rcx
0x1800140bf  jz      short loc_1800140E7
0x1800140c1  test    byte ptr [r10+1Ch], 1
0x1800140c6  jz      short loc_1800140E7
0x1800140c8  cmp     byte ptr [r10+19h], 2
0x1800140cd  jb      short loc_1800140E7
0x1800140cf  mov     edx, 0Eh
0x1800140d4  mov     r9d, ebx
0x1800140d7  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x1800140de  mov     rcx, [r10+10h]
0x1800140e2  call    WPP_SF_D
0x1800140e7  xorps   xmm0, xmm0
0x1800140ea  movdqu  [rbp+pExceptionObject], xmm0
0x1800140ef  mov     [rbp+var_28], rsi
0x1800140f3  mov     [rbp+var_20], ebx
0x1800140f6  mov     dword ptr [rbp+var_1C], 0FFFFFFFFh
0x1800140fd  mov     dword ptr [rbp+var_1C+4], 54h ; 'T'
0x180014104  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001410b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001410f  call    _CxxThrowException_0
0x180014115  lea     rcx, [rbp+lpBuffer]
0x180014119  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001411e  nop
0x18001411f  mov     rdx, rdi
0x180014122  lea     rcx, [rbp+lpBuffer]
0x180014126  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18001412b  test    al, al
0x18001412d  jnz     short loc_180014199
0x18001412f  lea     rcx, WPP_GLOBAL_Control
0x180014136  mov     rax, cs:WPP_GLOBAL_Control
0x18001413d  cmp     rax, rcx
0x180014140  jz      short loc_180014167
0x180014142  test    byte ptr [rax+1Ch], 1
0x180014146  jz      short loc_180014167
0x180014148  cmp     byte ptr [rax+19h], 2
0x18001414c  jb      short loc_180014167
0x18001414e  mov     edx, 0Fh
0x180014153  lea     r9d, [rdx-1]
0x180014157  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001415e  mov     rcx, [rax+10h]
0x180014162  call    WPP_SF_D
0x180014167  xorps   xmm0, xmm0
0x18001416a  movdqu  [rbp+pExceptionObject], xmm0
0x18001416f  mov     [rbp+var_28], rsi
0x180014173  mov     [rbp+var_20], 0Eh
0x18001417a  mov     dword ptr [rbp+var_1C], 0FFFFFFFFh
0x180014181  mov     dword ptr [rbp+var_1C+4], 5Ah ; 'Z'
0x180014188  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001418f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180014193  call    _CxxThrowException_0
0x180014199  xor     r9d, r9d; lpFilePart
0x18001419c  mov     r8, [rbp+lpBuffer]; lpBuffer
0x1800141a0  mov     edx, edi; nBufferLength
0x1800141a2  mov     rcx, [rbx]; lpFileName
0x1800141a5  call    cs:__imp_GetFullPathNameW
0x1800141ab  test    eax, eax
0x1800141ad  jnz     short loc_180014228
0x1800141af  call    cs:__imp_GetLastError
0x1800141b5  mov     ebx, eax
0x1800141b7  mov     eax, 507h
0x1800141bc  test    ebx, ebx
0x1800141be  cmovz   ebx, eax
0x1800141c1  lea     rcx, WPP_GLOBAL_Control
0x1800141c8  mov     r10, cs:WPP_GLOBAL_Control
0x1800141cf  cmp     r10, rcx
0x1800141d2  jz      short loc_1800141FA
0x1800141d4  test    byte ptr [r10+1Ch], 1
0x1800141d9  jz      short loc_1800141FA
0x1800141db  cmp     byte ptr [r10+19h], 2
0x1800141e0  jb      short loc_1800141FA
0x1800141e2  mov     edx, 10h
0x1800141e7  mov     r9d, ebx
0x1800141ea  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x1800141f1  mov     rcx, [r10+10h]
0x1800141f5  call    WPP_SF_D
0x1800141fa  xorps   xmm0, xmm0
0x1800141fd  movdqu  [rbp+pExceptionObject], xmm0
0x180014202  mov     [rbp+var_28], rsi
0x180014206  mov     [rbp+var_20], ebx
0x180014209  mov     dword ptr [rbp+var_1C], 0FFFFFFFFh
0x180014210  mov     dword ptr [rbp+var_1C+4], 60h ; '`'
0x180014217  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001421e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180014222  call    _CxxThrowException_0
0x180014228  mov     edx, eax
0x18001422a  lea     rcx, [rbp+lpBuffer]
0x18001422e  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x180014233  lea     rdx, [rbp+lpBuffer]
0x180014237  mov     rcx, rbx
0x18001423a  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18001423f  nop
0x180014240  lea     rax, [rbp+var_48]
0x180014244  mov     rcx, [rbp+lpBuffer]; void *
0x180014248  cmp     rcx, rax
0x18001424b  jz      short loc_180014252
0x18001424d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014252  add     rsp, 78h
0x180014256  pop     rdi
0x180014257  pop     rsi
0x180014258  pop     rbx
0x180014259  pop     rbp
0x18001425a  retn
0x18001425b  lea     rcx, WPP_GLOBAL_Control
0x180014262  mov     ebx, 57h ; 'W'
0x180014267  mov     rax, cs:WPP_GLOBAL_Control
0x18001426e  cmp     rax, rcx
0x180014271  jz      short loc_180014295
0x180014273  test    byte ptr [rax+1Ch], 1
0x180014277  jz      short loc_180014295
0x180014279  cmp     byte ptr [rax+19h], 2
0x18001427d  jb      short loc_180014295
0x18001427f  lea     edx, [rbx-4Ch]
0x180014282  mov     r9d, ebx
0x180014285  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001428c  mov     rcx, [rax+10h]
0x180014290  call    WPP_SF_D
0x180014295  xorps   xmm0, xmm0
0x180014298  movdqu  [rbp+pExceptionObject], xmm0
0x18001429d  mov     [rbp+var_28], rsi
0x1800142a1  mov     [rbp+var_20], ebx
0x1800142a4  mov     dword ptr [rbp+var_1C], 0FFFFFFFFh
0x1800142ab  mov     dword ptr [rbp+var_1C+4], 46h ; 'F'
0x1800142b2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800142b9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800142bd  call    _CxxThrowException_0
```
