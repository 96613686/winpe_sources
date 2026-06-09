# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x18000c8f8`
- end: `0x18000cb65`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `621`
- prototype: `int(ATL::CRegParser *__hidden this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ccfc`

## callees

- `0x180002300`
- `0x18000a9bc`
- `0x18000ac10`
- `0x18000b7b4`
- `0x18000b9a4`
- `0x18000c58c`
- `0x18000c8f8`
- `0x18000d930`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000ca3b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000ca3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ca9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ca9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ca53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ca53`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ca74`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ca74`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000c9d1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cae0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000caf6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000c9d1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cae0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000caf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c9a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c9a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb2f`

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
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v11, 1) )
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
0x18000c8f8  mov     [rsp-8+arg_8], rbx
0x18000c8fd  push    rbp
0x18000c8fe  push    rsi
0x18000c8ff  push    rdi
0x18000c900  push    r12
0x18000c902  push    r13
0x18000c904  push    r14
0x18000c906  push    r15
0x18000c908  lea     rbp, [rsp-27h]
0x18000c90d  sub     rsp, 90h
0x18000c914  mov     rax, cs:__security_cookie
0x18000c91b  xor     rax, rsp
0x18000c91e  mov     [rbp+57h+var_40], rax
0x18000c922  mov     r15, r8
0x18000c925  mov     rbx, rdx
0x18000c928  mov     rdi, rcx
0x18000c92b  xor     r13d, r13d
0x18000c92e  test    rdx, rdx
0x18000c931  jz      loc_18000CB39
0x18000c937  test    r8, r8
0x18000c93a  jz      loc_18000CB39
0x18000c940  mov     [r8], r13
0x18000c943  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000c947  inc     rdx
0x18000c94a  cmp     [rbx+rdx*2], r13w
0x18000c94f  jnz     short loc_18000C947
0x18000c951  add     edx, edx
0x18000c953  mov     eax, 3E8h
0x18000c958  cmp     edx, 64h ; 'd'
0x18000c95b  cmovl   edx, eax
0x18000c95e  mov     [rbp+57h+var_98], r13d
0x18000c962  mov     [rbp+57h+var_94], edx
0x18000c965  mov     dword ptr [rbp+57h+cb], r13d
0x18000c969  mov     r8d, 2
0x18000c96f  lea     rcx, [rbp+57h+cb]
0x18000c973  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18000c978  test    eax, eax
0x18000c97a  jns     short loc_18000C985
0x18000c97c  mov     rax, r13
0x18000c97f  mov     [rbp+57h+pv], r13
0x18000c983  jmp     short loc_18000C99B
0x18000c985  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18000c988  call    cs:__imp_CoTaskMemAlloc
0x18000c98e  mov     [rbp+57h+pv], rax
0x18000c992  test    rax, rax
0x18000c995  jz      short loc_18000C99B
0x18000c997  mov     [rax], r13w
0x18000c99b  test    rax, rax
0x18000c99e  jnz     short loc_18000C9B3
0x18000c9a0  mov     rcx, rax; pv
0x18000c9a3  call    cs:__imp_CoTaskMemFree
0x18000c9a9  mov     eax, 8007000Eh
0x18000c9ae  jmp     loc_18000CB3E
0x18000c9b3  mov     [rdi], rbx
0x18000c9b6  mov     esi, 25h ; '%'
0x18000c9bb  cmp     [rbx], r13w
0x18000c9bf  jz      loc_18000CB1D
0x18000c9c5  cmp     [rbx], si
0x18000c9c8  jnz     loc_18000CB07
0x18000c9ce  mov     rcx, rbx; lpsz
0x18000c9d1  call    cs:__imp_CharNextW
0x18000c9d7  mov     [rdi], rax
0x18000c9da  cmp     [rax], si
0x18000c9dd  jnz     short loc_18000CA03
0x18000c9df  mov     rdx, rax; wchar_t *
0x18000c9e2  mov     r8d, 1; int
0x18000c9e8  lea     rcx, [rbp+57h+var_98]; this
0x18000c9ec  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18000c9f1  test    eax, eax
0x18000c9f3  jnz     loc_18000CAF3
0x18000c9f9  mov     ebx, 8007000Eh
0x18000c9fe  jmp     loc_18000CB2B
0x18000ca03  mov     edx, esi; wchar_t
0x18000ca05  mov     rcx, rax; lpsz
0x18000ca08  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x18000ca0d  mov     rsi, rax
0x18000ca10  test    rax, rax
0x18000ca13  jz      loc_18000CB16
0x18000ca19  mov     rcx, rax
0x18000ca1c  sub     rcx, [rdi]
0x18000ca1f  sar     rcx, 1
0x18000ca22  cmp     rcx, 1Fh
0x18000ca26  jg      loc_18000CB0F
0x18000ca2c  movsxd  r9, ecx
0x18000ca2f  mov     r8, [rdi]
0x18000ca32  mov     edx, 20h ; ' '
0x18000ca37  lea     rcx, [rbp+57h+String2]
0x18000ca3b  call    cs:__imp__o_wcsncpy_s
0x18000ca41  mov     ecx, eax; int
0x18000ca43  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000ca48  mov     rbx, [rdi+8]
0x18000ca4c  lea     r12, [rbx+20h]
0x18000ca50  mov     rcx, r12; lpCriticalSection
0x18000ca53  call    cs:__imp_EnterCriticalSection
0x18000ca59  lea     r14, [rbx+8]
0x18000ca5d  mov     ebx, r13d
0x18000ca60  cmp     ebx, [r14+10h]
0x18000ca64  jge     short loc_18000CA96
0x18000ca66  movsxd  rax, ebx
0x18000ca69  mov     rcx, [r14]
0x18000ca6c  lea     rdx, [rbp+57h+String2]; lpString2
0x18000ca70  mov     rcx, [rcx+rax*8]; lpString1
0x18000ca74  call    cs:__imp_lstrcmpiW
0x18000ca7a  test    eax, eax
0x18000ca7c  jz      short loc_18000CA82
0x18000ca7e  inc     ebx
0x18000ca80  jmp     short loc_18000CA60
0x18000ca82  cmp     ebx, 0FFFFFFFFh
0x18000ca85  jz      short loc_18000CA96
0x18000ca87  mov     edx, ebx
0x18000ca89  mov     rcx, r14
0x18000ca8c  call    ?GetValueAt@?$CSimpleMap@PEA_WPEA_WVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEA_WH@Z; ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000ca91  mov     rbx, [rax]
0x18000ca94  jmp     short loc_18000CA99
0x18000ca96  mov     rbx, r13
0x18000ca99  mov     rcx, r12; lpCriticalSection
0x18000ca9c  call    cs:__imp_LeaveCriticalSection
0x18000caa2  test    rbx, rbx
0x18000caa5  jz      short loc_18000CB16
0x18000caa7  mov     [rbp+57h+cb], r13
0x18000caab  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000caaf  inc     r8; int
0x18000cab2  cmp     [rbx+r8*2], r13w
0x18000cab7  jnz     short loc_18000CAAF
0x18000cab9  mov     rdx, rbx; wchar_t *
0x18000cabc  lea     rcx, [rbp+57h+var_98]; this
0x18000cac0  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18000cac5  mov     ebx, eax
0x18000cac7  lea     rcx, [rbp+57h+cb]
0x18000cacb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000cad0  test    ebx, ebx
0x18000cad2  jz      loc_18000C9F9
0x18000cad8  mov     rax, [rdi]
0x18000cadb  jmp     short loc_18000CAE9
0x18000cadd  mov     rcx, rax; lpsz
0x18000cae0  call    cs:__imp_CharNextW
0x18000cae6  mov     [rdi], rax
0x18000cae9  cmp     rax, rsi
0x18000caec  jnz     short loc_18000CADD
0x18000caee  mov     esi, 25h ; '%'
0x18000caf3  mov     rcx, [rdi]; lpsz
0x18000caf6  call    cs:__imp_CharNextW
0x18000cafc  mov     rbx, rax
0x18000caff  mov     [rdi], rax
0x18000cb02  jmp     loc_18000C9BB
0x18000cb07  mov     rdx, rbx
0x18000cb0a  jmp     loc_18000C9E2
0x18000cb0f  mov     ebx, 80004005h
0x18000cb14  jmp     short loc_18000CB2B
0x18000cb16  mov     ebx, 80020009h
0x18000cb1b  jmp     short loc_18000CB2B
0x18000cb1d  mov     ebx, r13d
0x18000cb20  mov     rcx, [rbp+57h+pv]
0x18000cb24  mov     [rbp+57h+pv], r13
0x18000cb28  mov     [r15], rcx
0x18000cb2b  mov     rcx, [rbp+57h+pv]; pv
0x18000cb2f  call    cs:__imp_CoTaskMemFree
0x18000cb35  mov     eax, ebx
0x18000cb37  jmp     short loc_18000CB3E
0x18000cb39  mov     eax, 80004003h
0x18000cb3e  mov     rcx, [rbp+57h+var_40]
0x18000cb42  xor     rcx, rsp; StackCookie
0x18000cb45  call    __security_check_cookie
0x18000cb4a  mov     rbx, [rsp+0C0h+arg_8]
0x18000cb52  add     rsp, 90h
0x18000cb59  pop     r15
0x18000cb5b  pop     r14
0x18000cb5d  pop     r13
0x18000cb5f  pop     r12
0x18000cb61  pop     rdi
0x18000cb62  pop     rsi
0x18000cb63  pop     rbp
0x18000cb64  retn
```
