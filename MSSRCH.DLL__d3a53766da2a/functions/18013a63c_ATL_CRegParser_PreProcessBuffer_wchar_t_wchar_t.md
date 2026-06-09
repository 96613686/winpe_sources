# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x18013a63c`
- end: `0x18013a8a9`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `621`
- prototype: `int(ATL::CRegParser *__hidden this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18013b670`

## callees

- `0x18005bf7c`
- `0x1800c155c`
- `0x1801244c0`
- `0x180132bb0`
- `0x180135278`
- `0x1801396f0`
- `0x18013a63c`
- `0x18013dca4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18013a77f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18013a77f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18013a7e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18013a7e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013a797`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013a797`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18013a715`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18013a824`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18013a83a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18013a715`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18013a824`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18013a83a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013a7b8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013a7b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18013a6cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18013a6cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a6e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a873`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a6e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013a873`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(ATL::CRegParser *this, wchar_t *a2, wchar_t **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // rdx
  _WORD *v8; // rax
  LPWSTR v10; // rax
  const wchar_t *v11; // rdx
  unsigned int v12; // ebx
  wchar_t *v13; // rax
  wchar_t *v14; // rsi
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // r12
  __int64 v19; // r14
  unsigned int i; // ebx
  const wchar_t *v21; // rbx
  __int64 v22; // r8
  int v23; // ebx
  const WCHAR *j; // rax
  wchar_t *v25; // rcx
  SIZE_T cb; // [rsp+20h] [rbp-49h] BYREF
  _DWORD v27[2]; // [rsp+28h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-39h]
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  v7 = (unsigned int)(2 * v6);
  if ( (int)v7 < 100 )
    v7 = 1000;
  v27[0] = 0;
  v27[1] = v7;
  LODWORD(cb) = 0;
  if ( (int)ATL::AtlMultiply<unsigned long>(&cb, v7, 2) >= 0 )
  {
    v8 = CoTaskMemAlloc((unsigned int)cb);
    pv = v8;
    if ( v8 )
      *v8 = 0;
  }
  else
  {
    v8 = 0;
    pv = 0;
  }
  if ( !v8 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v11 = v4;
LABEL_18:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v11, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v10 = CharNextW(v4);
    *(_QWORD *)this = v10;
    if ( *v10 == 37 )
    {
      v11 = v10;
      goto LABEL_18;
    }
    v13 = ATL::CRegParser::StrChrW(v10, 0x25u);
    v14 = v13;
    if ( !v13 )
      goto LABEL_39;
    v15 = ((__int64)v13 - *(_QWORD *)this) >> 1;
    if ( v15 > 31 )
    {
      v12 = -2147467259;
      goto LABEL_41;
    }
    v16 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v15);
    ATL::AtlCrtErrorCheck(v16);
    v17 = *((_QWORD *)this + 1);
    v18 = (struct _RTL_CRITICAL_SECTION *)(v17 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 32));
    v19 = v17 + 8;
    for ( i = 0; (signed int)i < *(_DWORD *)(v19 + 16); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v19 + 8LL * (int)i), String2) )
      {
        if ( i != -1 )
        {
          v21 = *(const wchar_t **)ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                     v19,
                                     i);
          goto LABEL_29;
        }
        break;
      }
    }
    v21 = 0;
LABEL_29:
    LeaveCriticalSection(v18);
    if ( !v21 )
    {
LABEL_39:
      v12 = -2147352567;
      goto LABEL_41;
    }
    cb = 0;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    v23 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v21, v22);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&cb);
    if ( !v23 )
    {
LABEL_19:
      v12 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *(const WCHAR **)this; j != v14; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v12 = 0;
  v25 = (wchar_t *)pv;
  pv = 0;
  *a3 = v25;
LABEL_41:
  CoTaskMemFree(pv);
  return v12;
}

```

## disassembly

```asm
0x18013a63c  mov     [rsp-8+arg_8], rbx
0x18013a641  push    rbp
0x18013a642  push    rsi
0x18013a643  push    rdi
0x18013a644  push    r12
0x18013a646  push    r13
0x18013a648  push    r14
0x18013a64a  push    r15
0x18013a64c  lea     rbp, [rsp-27h]
0x18013a651  sub     rsp, 90h
0x18013a658  mov     rax, cs:__security_cookie
0x18013a65f  xor     rax, rsp
0x18013a662  mov     [rbp+57h+var_40], rax
0x18013a666  mov     r15, r8
0x18013a669  mov     rbx, rdx
0x18013a66c  mov     rdi, rcx
0x18013a66f  xor     r13d, r13d
0x18013a672  test    rdx, rdx
0x18013a675  jz      loc_18013A87D
0x18013a67b  test    r8, r8
0x18013a67e  jz      loc_18013A87D
0x18013a684  mov     [r8], r13
0x18013a687  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18013a68b  inc     rdx
0x18013a68e  cmp     [rbx+rdx*2], r13w
0x18013a693  jnz     short loc_18013A68B
0x18013a695  add     edx, edx
0x18013a697  mov     eax, 3E8h
0x18013a69c  cmp     edx, 64h ; 'd'
0x18013a69f  cmovl   edx, eax
0x18013a6a2  mov     [rbp+57h+var_98], r13d
0x18013a6a6  mov     [rbp+57h+var_94], edx
0x18013a6a9  mov     dword ptr [rbp+57h+cb], r13d
0x18013a6ad  mov     r8d, 2
0x18013a6b3  lea     rcx, [rbp+57h+cb]
0x18013a6b7  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18013a6bc  test    eax, eax
0x18013a6be  jns     short loc_18013A6C9
0x18013a6c0  mov     rax, r13
0x18013a6c3  mov     [rbp+57h+pv], r13
0x18013a6c7  jmp     short loc_18013A6DF
0x18013a6c9  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18013a6cc  call    cs:__imp_CoTaskMemAlloc
0x18013a6d2  mov     [rbp+57h+pv], rax
0x18013a6d6  test    rax, rax
0x18013a6d9  jz      short loc_18013A6DF
0x18013a6db  mov     [rax], r13w
0x18013a6df  test    rax, rax
0x18013a6e2  jnz     short loc_18013A6F7
0x18013a6e4  mov     rcx, rax; pv
0x18013a6e7  call    cs:__imp_CoTaskMemFree
0x18013a6ed  mov     eax, 8007000Eh
0x18013a6f2  jmp     loc_18013A882
0x18013a6f7  mov     [rdi], rbx
0x18013a6fa  mov     esi, 25h ; '%'
0x18013a6ff  cmp     [rbx], r13w
0x18013a703  jz      loc_18013A861
0x18013a709  cmp     [rbx], si
0x18013a70c  jnz     loc_18013A84B
0x18013a712  mov     rcx, rbx; lpsz
0x18013a715  call    cs:__imp_CharNextW
0x18013a71b  mov     [rdi], rax
0x18013a71e  cmp     [rax], si
0x18013a721  jnz     short loc_18013A747
0x18013a723  mov     rdx, rax; wchar_t *
0x18013a726  mov     r8d, 1; int
0x18013a72c  lea     rcx, [rbp+57h+var_98]; this
0x18013a730  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18013a735  test    eax, eax
0x18013a737  jnz     loc_18013A837
0x18013a73d  mov     ebx, 8007000Eh
0x18013a742  jmp     loc_18013A86F
0x18013a747  mov     edx, esi; wchar_t
0x18013a749  mov     rcx, rax; lpsz
0x18013a74c  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x18013a751  mov     rsi, rax
0x18013a754  test    rax, rax
0x18013a757  jz      loc_18013A85A
0x18013a75d  mov     rcx, rax
0x18013a760  sub     rcx, [rdi]
0x18013a763  sar     rcx, 1
0x18013a766  cmp     rcx, 1Fh
0x18013a76a  jg      loc_18013A853
0x18013a770  movsxd  r9, ecx
0x18013a773  mov     r8, [rdi]
0x18013a776  mov     edx, 20h ; ' '
0x18013a77b  lea     rcx, [rbp+57h+String2]
0x18013a77f  call    cs:__imp__o_wcsncpy_s
0x18013a785  mov     ecx, eax; int
0x18013a787  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18013a78c  mov     rbx, [rdi+8]
0x18013a790  lea     r12, [rbx+20h]
0x18013a794  mov     rcx, r12; lpCriticalSection
0x18013a797  call    cs:__imp_EnterCriticalSection
0x18013a79d  lea     r14, [rbx+8]
0x18013a7a1  mov     ebx, r13d
0x18013a7a4  cmp     ebx, [r14+10h]
0x18013a7a8  jge     short loc_18013A7DA
0x18013a7aa  movsxd  rax, ebx
0x18013a7ad  mov     rcx, [r14]
0x18013a7b0  lea     rdx, [rbp+57h+String2]; lpString2
0x18013a7b4  mov     rcx, [rcx+rax*8]; lpString1
0x18013a7b8  call    cs:__imp_lstrcmpiW
0x18013a7be  test    eax, eax
0x18013a7c0  jz      short loc_18013A7C6
0x18013a7c2  inc     ebx
0x18013a7c4  jmp     short loc_18013A7A4
0x18013a7c6  cmp     ebx, 0FFFFFFFFh
0x18013a7c9  jz      short loc_18013A7DA
0x18013a7cb  mov     edx, ebx
0x18013a7cd  mov     rcx, r14
0x18013a7d0  call    ?GetValueAt@?$CSimpleMap@PEA_WPEA_WVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEA_WH@Z; ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18013a7d5  mov     rbx, [rax]
0x18013a7d8  jmp     short loc_18013A7DD
0x18013a7da  mov     rbx, r13
0x18013a7dd  mov     rcx, r12; lpCriticalSection
0x18013a7e0  call    cs:__imp_LeaveCriticalSection
0x18013a7e6  test    rbx, rbx
0x18013a7e9  jz      short loc_18013A85A
0x18013a7eb  mov     [rbp+57h+cb], r13
0x18013a7ef  or      r8, 0FFFFFFFFFFFFFFFFh
0x18013a7f3  inc     r8; int
0x18013a7f6  cmp     [rbx+r8*2], r13w
0x18013a7fb  jnz     short loc_18013A7F3
0x18013a7fd  mov     rdx, rbx; wchar_t *
0x18013a800  lea     rcx, [rbp+57h+var_98]; this
0x18013a804  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18013a809  mov     ebx, eax
0x18013a80b  lea     rcx, [rbp+57h+cb]
0x18013a80f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18013a814  test    ebx, ebx
0x18013a816  jz      loc_18013A73D
0x18013a81c  mov     rax, [rdi]
0x18013a81f  jmp     short loc_18013A82D
0x18013a821  mov     rcx, rax; lpsz
0x18013a824  call    cs:__imp_CharNextW
0x18013a82a  mov     [rdi], rax
0x18013a82d  cmp     rax, rsi
0x18013a830  jnz     short loc_18013A821
0x18013a832  mov     esi, 25h ; '%'
0x18013a837  mov     rcx, [rdi]; lpsz
0x18013a83a  call    cs:__imp_CharNextW
0x18013a840  mov     rbx, rax
0x18013a843  mov     [rdi], rax
0x18013a846  jmp     loc_18013A6FF
0x18013a84b  mov     rdx, rbx
0x18013a84e  jmp     loc_18013A726
0x18013a853  mov     ebx, 80004005h
0x18013a858  jmp     short loc_18013A86F
0x18013a85a  mov     ebx, 80020009h
0x18013a85f  jmp     short loc_18013A86F
0x18013a861  mov     ebx, r13d
0x18013a864  mov     rcx, [rbp+57h+pv]
0x18013a868  mov     [rbp+57h+pv], r13
0x18013a86c  mov     [r15], rcx
0x18013a86f  mov     rcx, [rbp+57h+pv]; pv
0x18013a873  call    cs:__imp_CoTaskMemFree
0x18013a879  mov     eax, ebx
0x18013a87b  jmp     short loc_18013A882
0x18013a87d  mov     eax, 80004003h
0x18013a882  mov     rcx, [rbp+57h+var_40]
0x18013a886  xor     rcx, rsp; StackCookie
0x18013a889  call    __security_check_cookie
0x18013a88e  mov     rbx, [rsp+0C0h+arg_8]
0x18013a896  add     rsp, 90h
0x18013a89d  pop     r15
0x18013a89f  pop     r14
0x18013a8a1  pop     r13
0x18013a8a3  pop     r12
0x18013a8a5  pop     rdi
0x18013a8a6  pop     rsi
0x18013a8a7  pop     rbp
0x18013a8a8  retn
```
