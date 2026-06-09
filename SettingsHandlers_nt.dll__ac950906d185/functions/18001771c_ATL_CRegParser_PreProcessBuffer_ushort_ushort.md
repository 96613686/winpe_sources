# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18001771c`
- end: `0x1800179c6`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `682`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018a44`

## callees

- `0x18000c840`
- `0x180011db0`
- `0x180012df8`
- `0x180014574`
- `0x180014658`
- `0x18001634c`
- `0x18001771c`
- `0x18001a524`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180017871`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180017871`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800178e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800178e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001788f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001788f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800177cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017989`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800177cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017989`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800177ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800177ac`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180017801`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001792e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001794a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180017801`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001792e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001794a`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x1800178b6`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x1800178b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // rdx
  _WORD *v8; // rax
  LPWSTR v10; // rax
  const unsigned __int16 *v11; // rdx
  unsigned int v12; // ebx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rsi
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // r12
  __int64 v19; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  int v23; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v25; // rcx
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
          v21 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
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
  v25 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v25;
LABEL_41:
  CoTaskMemFree(pv);
  return v12;
}

```

## disassembly

```asm
0x18001771c  mov     [rsp-8+arg_8], rbx
0x180017721  push    rbp
0x180017722  push    rsi
0x180017723  push    rdi
0x180017724  push    r12
0x180017726  push    r13
0x180017728  push    r14
0x18001772a  push    r15
0x18001772c  lea     rbp, [rsp-27h]
0x180017731  sub     rsp, 90h
0x180017738  mov     rax, cs:__security_cookie
0x18001773f  xor     rax, rsp
0x180017742  mov     [rbp+57h+var_40], rax
0x180017746  mov     r15, r8
0x180017749  mov     rbx, rdx
0x18001774c  mov     rdi, rcx
0x18001774f  xor     r13d, r13d
0x180017752  test    rdx, rdx
0x180017755  jz      loc_180017999
0x18001775b  test    r8, r8
0x18001775e  jz      loc_180017999
0x180017764  mov     [r8], r13
0x180017767  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001776b  inc     rdx
0x18001776e  cmp     [rbx+rdx*2], r13w
0x180017773  jnz     short loc_18001776B
0x180017775  add     edx, edx
0x180017777  mov     eax, 3E8h
0x18001777c  cmp     edx, 64h ; 'd'
0x18001777f  cmovl   edx, eax
0x180017782  mov     [rbp+57h+var_98], r13d
0x180017786  mov     [rbp+57h+var_94], edx
0x180017789  mov     dword ptr [rbp+57h+cb], r13d
0x18001778d  mov     r8d, 2
0x180017793  lea     rcx, [rbp+57h+cb]
0x180017797  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18001779c  test    eax, eax
0x18001779e  jns     short loc_1800177A9
0x1800177a0  mov     rax, r13
0x1800177a3  mov     [rbp+57h+pv], r13
0x1800177a7  jmp     short loc_1800177C5
0x1800177a9  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x1800177ac  call    cs:__imp_CoTaskMemAlloc
0x1800177b3  nop     dword ptr [rax+rax+00h]
0x1800177b8  mov     [rbp+57h+pv], rax
0x1800177bc  test    rax, rax
0x1800177bf  jz      short loc_1800177C5
0x1800177c1  mov     [rax], r13w
0x1800177c5  test    rax, rax
0x1800177c8  jnz     short loc_1800177E3
0x1800177ca  mov     rcx, rax; pv
0x1800177cd  call    cs:__imp_CoTaskMemFree
0x1800177d4  nop     dword ptr [rax+rax+00h]
0x1800177d9  mov     eax, 8007000Eh
0x1800177de  jmp     loc_18001799E
0x1800177e3  mov     [rdi], rbx
0x1800177e6  mov     esi, 25h ; '%'
0x1800177eb  cmp     [rbx], r13w
0x1800177ef  jz      loc_180017977
0x1800177f5  cmp     [rbx], si
0x1800177f8  jnz     loc_180017961
0x1800177fe  mov     rcx, rbx; lpsz
0x180017801  call    cs:__imp_CharNextW
0x180017808  nop     dword ptr [rax+rax+00h]
0x18001780d  mov     [rdi], rax
0x180017810  cmp     [rax], si
0x180017813  jnz     short loc_180017839
0x180017815  mov     rdx, rax; unsigned __int16 *
0x180017818  mov     r8d, 1; int
0x18001781e  lea     rcx, [rbp+57h+var_98]; this
0x180017822  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180017827  test    eax, eax
0x180017829  jnz     loc_180017947
0x18001782f  mov     ebx, 8007000Eh
0x180017834  jmp     loc_180017985
0x180017839  mov     edx, esi; unsigned __int16
0x18001783b  mov     rcx, rax; lpsz
0x18001783e  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180017843  mov     rsi, rax
0x180017846  test    rax, rax
0x180017849  jz      loc_180017970
0x18001784f  mov     rcx, rax
0x180017852  sub     rcx, [rdi]
0x180017855  sar     rcx, 1
0x180017858  cmp     rcx, 1Fh
0x18001785c  jg      loc_180017969
0x180017862  movsxd  r9, ecx
0x180017865  mov     r8, [rdi]
0x180017868  mov     edx, 20h ; ' '
0x18001786d  lea     rcx, [rbp+57h+String2]
0x180017871  call    cs:__imp__o_wcsncpy_s
0x180017878  nop     dword ptr [rax+rax+00h]
0x18001787d  mov     ecx, eax; int
0x18001787f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180017884  mov     rbx, [rdi+8]
0x180017888  lea     r12, [rbx+20h]
0x18001788c  mov     rcx, r12; lpCriticalSection
0x18001788f  call    cs:__imp_EnterCriticalSection
0x180017896  nop     dword ptr [rax+rax+00h]
0x18001789b  lea     r14, [rbx+8]
0x18001789f  mov     ebx, r13d
0x1800178a2  cmp     ebx, [r14+10h]
0x1800178a6  jge     short loc_1800178DE
0x1800178a8  movsxd  rax, ebx
0x1800178ab  mov     rcx, [r14]
0x1800178ae  lea     rdx, [rbp+57h+String2]; lpString2
0x1800178b2  mov     rcx, [rcx+rax*8]; lpString1
0x1800178b6  call    cs:__imp_lstrcmpiW
0x1800178bd  nop     dword ptr [rax+rax+00h]
0x1800178c2  test    eax, eax
0x1800178c4  jz      short loc_1800178CA
0x1800178c6  inc     ebx
0x1800178c8  jmp     short loc_1800178A2
0x1800178ca  cmp     ebx, 0FFFFFFFFh
0x1800178cd  jz      short loc_1800178DE
0x1800178cf  mov     edx, ebx
0x1800178d1  mov     rcx, r14
0x1800178d4  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1800178d9  mov     rbx, [rax]
0x1800178dc  jmp     short loc_1800178E1
0x1800178de  mov     rbx, r13
0x1800178e1  mov     rcx, r12; lpCriticalSection
0x1800178e4  call    cs:__imp_LeaveCriticalSection
0x1800178eb  nop     dword ptr [rax+rax+00h]
0x1800178f0  test    rbx, rbx
0x1800178f3  jz      short loc_180017970
0x1800178f5  mov     [rbp+57h+cb], r13
0x1800178f9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800178fd  inc     r8; int
0x180017900  cmp     [rbx+r8*2], r13w
0x180017905  jnz     short loc_1800178FD
0x180017907  mov     rdx, rbx; unsigned __int16 *
0x18001790a  lea     rcx, [rbp+57h+var_98]; this
0x18001790e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180017913  mov     ebx, eax
0x180017915  lea     rcx, [rbp+57h+cb]
0x180017919  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001791e  test    ebx, ebx
0x180017920  jz      loc_18001782F
0x180017926  mov     rax, [rdi]
0x180017929  jmp     short loc_18001793D
0x18001792b  mov     rcx, rax; lpsz
0x18001792e  call    cs:__imp_CharNextW
0x180017935  nop     dword ptr [rax+rax+00h]
0x18001793a  mov     [rdi], rax
0x18001793d  cmp     rax, rsi
0x180017940  jnz     short loc_18001792B
0x180017942  mov     esi, 25h ; '%'
0x180017947  mov     rcx, [rdi]; lpsz
0x18001794a  call    cs:__imp_CharNextW
0x180017951  nop     dword ptr [rax+rax+00h]
0x180017956  mov     rbx, rax
0x180017959  mov     [rdi], rax
0x18001795c  jmp     loc_1800177EB
0x180017961  mov     rdx, rbx
0x180017964  jmp     loc_180017818
0x180017969  mov     ebx, 80004005h
0x18001796e  jmp     short loc_180017985
0x180017970  mov     ebx, 80020009h
0x180017975  jmp     short loc_180017985
0x180017977  mov     ebx, r13d
0x18001797a  mov     rcx, [rbp+57h+pv]
0x18001797e  mov     [rbp+57h+pv], r13
0x180017982  mov     [r15], rcx
0x180017985  mov     rcx, [rbp+57h+pv]; pv
0x180017989  call    cs:__imp_CoTaskMemFree
0x180017990  nop     dword ptr [rax+rax+00h]
0x180017995  mov     eax, ebx
0x180017997  jmp     short loc_18001799E
0x180017999  mov     eax, 80004003h
0x18001799e  mov     rcx, [rbp+57h+var_40]
0x1800179a2  xor     rcx, rsp; StackCookie
0x1800179a5  call    __security_check_cookie
0x1800179aa  mov     rbx, [rsp+0C0h+arg_8]
0x1800179b2  add     rsp, 90h
0x1800179b9  pop     r15
0x1800179bb  pop     r14
0x1800179bd  pop     r13
0x1800179bf  pop     r12
0x1800179c1  pop     rdi
0x1800179c2  pop     rsi
0x1800179c3  pop     rbp
0x1800179c4  retn
```
