# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x180197dfc`
- end: `0x180198069`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `621`
- prototype: `int(ATL::CRegParser *__hidden this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18019878c`

## callees

- `0x180176e60`
- `0x180188d90`
- `0x180192554`
- `0x180192700`
- `0x180193db8`
- `0x180197a0c`
- `0x180197dfc`
- `0x18019a370`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180197f3f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180197f3f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180197f57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180197f57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180197fa0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180197fa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180197ea7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180198033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180197ea7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180198033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180197e8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180197e8c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180197ed5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180197fe4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180197ffa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180197ed5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180197fe4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180197ffa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180197f78`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180197f78`

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
0x180197dfc  mov     [rsp-8+arg_8], rbx
0x180197e01  push    rbp
0x180197e02  push    rsi
0x180197e03  push    rdi
0x180197e04  push    r12
0x180197e06  push    r13
0x180197e08  push    r14
0x180197e0a  push    r15
0x180197e0c  lea     rbp, [rsp-27h]
0x180197e11  sub     rsp, 90h
0x180197e18  mov     rax, cs:__security_cookie
0x180197e1f  xor     rax, rsp
0x180197e22  mov     [rbp+57h+var_40], rax
0x180197e26  mov     r15, r8
0x180197e29  mov     rbx, rdx
0x180197e2c  mov     rdi, rcx
0x180197e2f  xor     r13d, r13d
0x180197e32  test    rdx, rdx
0x180197e35  jz      loc_18019803D
0x180197e3b  test    r8, r8
0x180197e3e  jz      loc_18019803D
0x180197e44  mov     [r8], r13
0x180197e47  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180197e4b  inc     rdx
0x180197e4e  cmp     [rbx+rdx*2], r13w
0x180197e53  jnz     short loc_180197E4B
0x180197e55  add     edx, edx
0x180197e57  mov     eax, 3E8h
0x180197e5c  cmp     edx, 64h ; 'd'
0x180197e5f  cmovl   edx, eax
0x180197e62  mov     [rbp+57h+var_98], r13d
0x180197e66  mov     [rbp+57h+var_94], edx
0x180197e69  mov     dword ptr [rbp+57h+cb], r13d
0x180197e6d  mov     r8d, 2
0x180197e73  lea     rcx, [rbp+57h+cb]
0x180197e77  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x180197e7c  test    eax, eax
0x180197e7e  jns     short loc_180197E89
0x180197e80  mov     rax, r13
0x180197e83  mov     [rbp+57h+pv], r13
0x180197e87  jmp     short loc_180197E9F
0x180197e89  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180197e8c  call    cs:__imp_CoTaskMemAlloc
0x180197e92  mov     [rbp+57h+pv], rax
0x180197e96  test    rax, rax
0x180197e99  jz      short loc_180197E9F
0x180197e9b  mov     [rax], r13w
0x180197e9f  test    rax, rax
0x180197ea2  jnz     short loc_180197EB7
0x180197ea4  mov     rcx, rax; pv
0x180197ea7  call    cs:__imp_CoTaskMemFree
0x180197ead  mov     eax, 8007000Eh
0x180197eb2  jmp     loc_180198042
0x180197eb7  mov     [rdi], rbx
0x180197eba  mov     esi, 25h ; '%'
0x180197ebf  cmp     [rbx], r13w
0x180197ec3  jz      loc_180198021
0x180197ec9  cmp     [rbx], si
0x180197ecc  jnz     loc_18019800B
0x180197ed2  mov     rcx, rbx; lpsz
0x180197ed5  call    cs:__imp_CharNextW
0x180197edb  mov     [rdi], rax
0x180197ede  cmp     [rax], si
0x180197ee1  jnz     short loc_180197F07
0x180197ee3  mov     rdx, rax; wchar_t *
0x180197ee6  mov     r8d, 1; int
0x180197eec  lea     rcx, [rbp+57h+var_98]; this
0x180197ef0  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x180197ef5  test    eax, eax
0x180197ef7  jnz     loc_180197FF7
0x180197efd  mov     ebx, 8007000Eh
0x180197f02  jmp     loc_18019802F
0x180197f07  mov     edx, esi; wchar_t
0x180197f09  mov     rcx, rax; lpsz
0x180197f0c  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x180197f11  mov     rsi, rax
0x180197f14  test    rax, rax
0x180197f17  jz      loc_18019801A
0x180197f1d  mov     rcx, rax
0x180197f20  sub     rcx, [rdi]
0x180197f23  sar     rcx, 1
0x180197f26  cmp     rcx, 1Fh
0x180197f2a  jg      loc_180198013
0x180197f30  movsxd  r9, ecx
0x180197f33  mov     r8, [rdi]
0x180197f36  mov     edx, 20h ; ' '
0x180197f3b  lea     rcx, [rbp+57h+String2]
0x180197f3f  call    cs:__imp__o_wcsncpy_s
0x180197f45  mov     ecx, eax; int
0x180197f47  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180197f4c  mov     rbx, [rdi+8]
0x180197f50  lea     r12, [rbx+20h]
0x180197f54  mov     rcx, r12; lpCriticalSection
0x180197f57  call    cs:__imp_EnterCriticalSection
0x180197f5d  lea     r14, [rbx+8]
0x180197f61  mov     ebx, r13d
0x180197f64  cmp     ebx, [r14+10h]
0x180197f68  jge     short loc_180197F9A
0x180197f6a  movsxd  rax, ebx
0x180197f6d  mov     rcx, [r14]
0x180197f70  lea     rdx, [rbp+57h+String2]; lpString2
0x180197f74  mov     rcx, [rcx+rax*8]; lpString1
0x180197f78  call    cs:__imp_lstrcmpiW
0x180197f7e  test    eax, eax
0x180197f80  jz      short loc_180197F86
0x180197f82  inc     ebx
0x180197f84  jmp     short loc_180197F64
0x180197f86  cmp     ebx, 0FFFFFFFFh
0x180197f89  jz      short loc_180197F9A
0x180197f8b  mov     edx, ebx
0x180197f8d  mov     rcx, r14
0x180197f90  call    ?GetValueAt@?$CSimpleMap@PEA_WPEA_WVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEA_WH@Z; ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180197f95  mov     rbx, [rax]
0x180197f98  jmp     short loc_180197F9D
0x180197f9a  mov     rbx, r13
0x180197f9d  mov     rcx, r12; lpCriticalSection
0x180197fa0  call    cs:__imp_LeaveCriticalSection
0x180197fa6  test    rbx, rbx
0x180197fa9  jz      short loc_18019801A
0x180197fab  mov     [rbp+57h+cb], r13
0x180197faf  or      r8, 0FFFFFFFFFFFFFFFFh
0x180197fb3  inc     r8; int
0x180197fb6  cmp     [rbx+r8*2], r13w
0x180197fbb  jnz     short loc_180197FB3
0x180197fbd  mov     rdx, rbx; wchar_t *
0x180197fc0  lea     rcx, [rbp+57h+var_98]; this
0x180197fc4  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x180197fc9  mov     ebx, eax
0x180197fcb  lea     rcx, [rbp+57h+cb]
0x180197fcf  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180197fd4  test    ebx, ebx
0x180197fd6  jz      loc_180197EFD
0x180197fdc  mov     rax, [rdi]
0x180197fdf  jmp     short loc_180197FED
0x180197fe1  mov     rcx, rax; lpsz
0x180197fe4  call    cs:__imp_CharNextW
0x180197fea  mov     [rdi], rax
0x180197fed  cmp     rax, rsi
0x180197ff0  jnz     short loc_180197FE1
0x180197ff2  mov     esi, 25h ; '%'
0x180197ff7  mov     rcx, [rdi]; lpsz
0x180197ffa  call    cs:__imp_CharNextW
0x180198000  mov     rbx, rax
0x180198003  mov     [rdi], rax
0x180198006  jmp     loc_180197EBF
0x18019800b  mov     rdx, rbx
0x18019800e  jmp     loc_180197EE6
0x180198013  mov     ebx, 80004005h
0x180198018  jmp     short loc_18019802F
0x18019801a  mov     ebx, 80020009h
0x18019801f  jmp     short loc_18019802F
0x180198021  mov     ebx, r13d
0x180198024  mov     rcx, [rbp+57h+pv]
0x180198028  mov     [rbp+57h+pv], r13
0x18019802c  mov     [r15], rcx
0x18019802f  mov     rcx, [rbp+57h+pv]; pv
0x180198033  call    cs:__imp_CoTaskMemFree
0x180198039  mov     eax, ebx
0x18019803b  jmp     short loc_180198042
0x18019803d  mov     eax, 80004003h
0x180198042  mov     rcx, [rbp+57h+var_40]
0x180198046  xor     rcx, rsp; StackCookie
0x180198049  call    __security_check_cookie
0x18019804e  mov     rbx, [rsp+0C0h+arg_8]
0x180198056  add     rsp, 90h
0x18019805d  pop     r15
0x18019805f  pop     r14
0x180198061  pop     r13
0x180198063  pop     r12
0x180198065  pop     rdi
0x180198066  pop     rsi
0x180198067  pop     rbp
0x180198068  retn
```
