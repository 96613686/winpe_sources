# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000e330`
- end: `0x18000e598`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `616`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e74c`

## callees

- `0x180002ab0`
- `0x180008e98`
- `0x18000a5cc`
- `0x18000a754`
- `0x18000bf2c`
- `0x18000e330`
- `0x180010330`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000e46a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000e46a`
- `KERNEL32!lstrcmpiW` at `0x18000e4a3`
- `KERNEL32!lstrcmpiW` at `0x18000e4a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e482`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e482`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e4cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e4cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e3b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e3b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e3d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e562`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e3d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e562`
- `USER32!CharNextW` at `0x18000e400`
- `USER32!CharNextW` at `0x18000e50f`
- `USER32!CharNextW` at `0x18000e525`
- `USER32!CharNextW` at `0x18000e400`
- `USER32!CharNextW` at `0x18000e50f`
- `USER32!CharNextW` at `0x18000e525`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  LPWSTR v11; // rax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // ebx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  __int64 v20; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v29; // [rsp+30h] [rbp-39h] BYREF
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(v27) = 0;
  HIDWORD(v27) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_18:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v12, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v11 = CharNextW(v4);
    *(_QWORD *)this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_18;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_39;
    v16 = ((__int64)v14 - *(_QWORD *)this) >> 1;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_41;
    }
    v17 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v16, v27);
    ATL::AtlCrtErrorCheck(v17);
    v18 = *((_QWORD *)this + 1);
    v19 = (struct _RTL_CRITICAL_SECTION *)(v18 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 32));
    v20 = v18 + 8;
    for ( i = 0; (signed int)i < *(_DWORD *)(v20 + 16); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v20 + 8LL * (int)i), String2) )
      {
        if ( i != -1 )
        {
          v22 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                              v20,
                                              i);
          goto LABEL_29;
        }
        break;
      }
    }
    v22 = 0;
LABEL_29:
    LeaveCriticalSection(v19);
    if ( !v22 )
    {
LABEL_39:
      v13 = -2147352567;
      goto LABEL_41;
    }
    v29 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v29);
    if ( !v24 )
    {
LABEL_19:
      v13 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *(const WCHAR **)this; j != v15; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v13 = 0;
  v26 = (unsigned __int16 *)pv;
  pv = 0;
  v27 = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x18000e330  mov     [rsp-8+arg_8], rbx
0x18000e335  push    rbp
0x18000e336  push    rsi
0x18000e337  push    rdi
0x18000e338  push    r12
0x18000e33a  push    r13
0x18000e33c  push    r14
0x18000e33e  push    r15
0x18000e340  lea     rbp, [rsp-27h]
0x18000e345  sub     rsp, 90h
0x18000e34c  mov     rax, cs:__security_cookie
0x18000e353  xor     rax, rsp
0x18000e356  mov     [rbp+57h+var_40], rax
0x18000e35a  mov     r15, r8
0x18000e35d  mov     rbx, rdx
0x18000e360  mov     rdi, rcx
0x18000e363  xor     r13d, r13d
0x18000e366  test    rdx, rdx
0x18000e369  jz      loc_18000E56C
0x18000e36f  test    r8, r8
0x18000e372  jz      loc_18000E56C
0x18000e378  mov     [r8], r13
0x18000e37b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e37f  inc     rax
0x18000e382  cmp     [rdx+rax*2], r13w
0x18000e387  jnz     short loc_18000E37F
0x18000e389  add     eax, eax
0x18000e38b  mov     ecx, 3E8h
0x18000e390  cmp     eax, 64h ; 'd'
0x18000e393  cmovl   eax, ecx
0x18000e396  mov     dword ptr [rbp+57h+var_A0], r13d
0x18000e39a  mov     dword ptr [rbp+57h+var_A0+4], eax
0x18000e39d  mov     ecx, eax
0x18000e39f  add     rcx, rcx
0x18000e3a2  mov     eax, 0FFFFFFFFh
0x18000e3a7  cmp     rcx, rax
0x18000e3aa  jbe     short loc_18000E3B5
0x18000e3ac  mov     rax, r13
0x18000e3af  mov     [rbp+57h+pv], r13
0x18000e3b3  jmp     short loc_18000E3CA
0x18000e3b5  mov     ecx, ecx; cb
0x18000e3b7  call    cs:__imp_CoTaskMemAlloc
0x18000e3bd  mov     [rbp+57h+pv], rax
0x18000e3c1  test    rax, rax
0x18000e3c4  jz      short loc_18000E3CA
0x18000e3c6  mov     [rax], r13w
0x18000e3ca  test    rax, rax
0x18000e3cd  jnz     short loc_18000E3E2
0x18000e3cf  mov     rcx, rax; pv
0x18000e3d2  call    cs:__imp_CoTaskMemFree
0x18000e3d8  mov     eax, 8007000Eh
0x18000e3dd  jmp     loc_18000E571
0x18000e3e2  mov     [rdi], rbx
0x18000e3e5  mov     esi, 25h ; '%'
0x18000e3ea  cmp     [rbx], r13w
0x18000e3ee  jz      loc_18000E54C
0x18000e3f4  cmp     [rbx], si
0x18000e3f7  jnz     loc_18000E536
0x18000e3fd  mov     rcx, rbx; lpsz
0x18000e400  call    cs:__imp_CharNextW
0x18000e406  mov     [rdi], rax
0x18000e409  cmp     [rax], si
0x18000e40c  jnz     short loc_18000E432
0x18000e40e  mov     rdx, rax; unsigned __int16 *
0x18000e411  mov     r8d, 1; int
0x18000e417  lea     rcx, [rbp+57h+var_A0]; this
0x18000e41b  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000e420  test    eax, eax
0x18000e422  jnz     loc_18000E522
0x18000e428  mov     ebx, 8007000Eh
0x18000e42d  jmp     loc_18000E55E
0x18000e432  mov     edx, esi; unsigned __int16
0x18000e434  mov     rcx, rax; lpsz
0x18000e437  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000e43c  mov     rsi, rax
0x18000e43f  test    rax, rax
0x18000e442  jz      loc_18000E545
0x18000e448  mov     rcx, rax
0x18000e44b  sub     rcx, [rdi]
0x18000e44e  sar     rcx, 1
0x18000e451  cmp     rcx, 1Fh
0x18000e455  jg      loc_18000E53E
0x18000e45b  movsxd  r9, ecx
0x18000e45e  mov     r8, [rdi]
0x18000e461  mov     edx, 20h ; ' '
0x18000e466  lea     rcx, [rbp+57h+String2]
0x18000e46a  call    cs:__imp__o_wcsncpy_s
0x18000e470  mov     ecx, eax; int
0x18000e472  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000e477  mov     rbx, [rdi+8]
0x18000e47b  lea     r12, [rbx+20h]
0x18000e47f  mov     rcx, r12; lpCriticalSection
0x18000e482  call    cs:__imp_EnterCriticalSection
0x18000e488  lea     r14, [rbx+8]
0x18000e48c  mov     ebx, r13d
0x18000e48f  cmp     ebx, [r14+10h]
0x18000e493  jge     short loc_18000E4C5
0x18000e495  movsxd  rax, ebx
0x18000e498  mov     rcx, [r14]
0x18000e49b  lea     rdx, [rbp+57h+String2]; lpString2
0x18000e49f  mov     rcx, [rcx+rax*8]; lpString1
0x18000e4a3  call    cs:__imp_lstrcmpiW
0x18000e4a9  test    eax, eax
0x18000e4ab  jz      short loc_18000E4B1
0x18000e4ad  inc     ebx
0x18000e4af  jmp     short loc_18000E48F
0x18000e4b1  cmp     ebx, 0FFFFFFFFh
0x18000e4b4  jz      short loc_18000E4C5
0x18000e4b6  mov     edx, ebx
0x18000e4b8  mov     rcx, r14
0x18000e4bb  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000e4c0  mov     rbx, [rax]
0x18000e4c3  jmp     short loc_18000E4C8
0x18000e4c5  mov     rbx, r13
0x18000e4c8  mov     rcx, r12; lpCriticalSection
0x18000e4cb  call    cs:__imp_LeaveCriticalSection
0x18000e4d1  test    rbx, rbx
0x18000e4d4  jz      short loc_18000E545
0x18000e4d6  mov     [rbp+57h+var_90], r13
0x18000e4da  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000e4de  inc     r8; int
0x18000e4e1  cmp     [rbx+r8*2], r13w
0x18000e4e6  jnz     short loc_18000E4DE
0x18000e4e8  mov     rdx, rbx; unsigned __int16 *
0x18000e4eb  lea     rcx, [rbp+57h+var_A0]; this
0x18000e4ef  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000e4f4  mov     ebx, eax
0x18000e4f6  lea     rcx, [rbp+57h+var_90]
0x18000e4fa  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000e4ff  test    ebx, ebx
0x18000e501  jz      loc_18000E428
0x18000e507  mov     rax, [rdi]
0x18000e50a  jmp     short loc_18000E518
0x18000e50c  mov     rcx, rax; lpsz
0x18000e50f  call    cs:__imp_CharNextW
0x18000e515  mov     [rdi], rax
0x18000e518  cmp     rax, rsi
0x18000e51b  jnz     short loc_18000E50C
0x18000e51d  mov     esi, 25h ; '%'
0x18000e522  mov     rcx, [rdi]; lpsz
0x18000e525  call    cs:__imp_CharNextW
0x18000e52b  mov     rbx, rax
0x18000e52e  mov     [rdi], rax
0x18000e531  jmp     loc_18000E3EA
0x18000e536  mov     rdx, rbx
0x18000e539  jmp     loc_18000E411
0x18000e53e  mov     ebx, 80004005h
0x18000e543  jmp     short loc_18000E55E
0x18000e545  mov     ebx, 80020009h
0x18000e54a  jmp     short loc_18000E55E
0x18000e54c  mov     ebx, r13d
0x18000e54f  mov     rcx, [rbp+57h+pv]
0x18000e553  mov     [rbp+57h+pv], r13
0x18000e557  mov     [rbp+57h+var_A0], r13
0x18000e55b  mov     [r15], rcx
0x18000e55e  mov     rcx, [rbp+57h+pv]; pv
0x18000e562  call    cs:__imp_CoTaskMemFree
0x18000e568  mov     eax, ebx
0x18000e56a  jmp     short loc_18000E571
0x18000e56c  mov     eax, 80004003h
0x18000e571  mov     rcx, [rbp+57h+var_40]
0x18000e575  xor     rcx, rsp; StackCookie
0x18000e578  call    __security_check_cookie
0x18000e57d  mov     rbx, [rsp+0C0h+arg_8]
0x18000e585  add     rsp, 90h
0x18000e58c  pop     r15
0x18000e58e  pop     r14
0x18000e590  pop     r13
0x18000e592  pop     r12
0x18000e594  pop     rdi
0x18000e595  pop     rsi
0x18000e596  pop     rbp
0x18000e597  retn
```
