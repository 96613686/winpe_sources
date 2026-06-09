# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18009c0e0`
- end: `0x18009c34d`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `621`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009c96c`

## callees

- `0x180087e80`
- `0x18008bf38`
- `0x18008c518`
- `0x180099068`
- `0x18009b0b8`
- `0x18009b870`
- `0x18009c0e0`
- `0x18009d670`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18009c223`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18009c223`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009c23b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009c23b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009c284`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009c284`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18009c1b9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18009c2c8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18009c2de`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18009c1b9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18009c2c8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18009c2de`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009c25c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009c25c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c170`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c170`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c18b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c317`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c18b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c317`

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
0x18009c0e0  mov     [rsp-8+arg_8], rbx
0x18009c0e5  push    rbp
0x18009c0e6  push    rsi
0x18009c0e7  push    rdi
0x18009c0e8  push    r12
0x18009c0ea  push    r13
0x18009c0ec  push    r14
0x18009c0ee  push    r15
0x18009c0f0  lea     rbp, [rsp-27h]
0x18009c0f5  sub     rsp, 90h
0x18009c0fc  mov     rax, cs:__security_cookie
0x18009c103  xor     rax, rsp
0x18009c106  mov     [rbp+57h+var_40], rax
0x18009c10a  mov     r15, r8
0x18009c10d  mov     rbx, rdx
0x18009c110  mov     rdi, rcx
0x18009c113  xor     r13d, r13d
0x18009c116  test    rdx, rdx
0x18009c119  jz      loc_18009C321
0x18009c11f  test    r8, r8
0x18009c122  jz      loc_18009C321
0x18009c128  mov     [r8], r13
0x18009c12b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18009c12f  inc     rdx
0x18009c132  cmp     [rbx+rdx*2], r13w
0x18009c137  jnz     short loc_18009C12F
0x18009c139  add     edx, edx
0x18009c13b  mov     eax, 3E8h
0x18009c140  cmp     edx, 64h ; 'd'
0x18009c143  cmovl   edx, eax
0x18009c146  mov     [rbp+57h+var_98], r13d
0x18009c14a  mov     [rbp+57h+var_94], edx
0x18009c14d  mov     dword ptr [rbp+57h+cb], r13d
0x18009c151  mov     r8d, 2
0x18009c157  lea     rcx, [rbp+57h+cb]
0x18009c15b  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18009c160  test    eax, eax
0x18009c162  jns     short loc_18009C16D
0x18009c164  mov     rax, r13
0x18009c167  mov     [rbp+57h+pv], r13
0x18009c16b  jmp     short loc_18009C183
0x18009c16d  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18009c170  call    cs:__imp_CoTaskMemAlloc
0x18009c176  mov     [rbp+57h+pv], rax
0x18009c17a  test    rax, rax
0x18009c17d  jz      short loc_18009C183
0x18009c17f  mov     [rax], r13w
0x18009c183  test    rax, rax
0x18009c186  jnz     short loc_18009C19B
0x18009c188  mov     rcx, rax; pv
0x18009c18b  call    cs:__imp_CoTaskMemFree
0x18009c191  mov     eax, 8007000Eh
0x18009c196  jmp     loc_18009C326
0x18009c19b  mov     [rdi], rbx
0x18009c19e  mov     esi, 25h ; '%'
0x18009c1a3  cmp     [rbx], r13w
0x18009c1a7  jz      loc_18009C305
0x18009c1ad  cmp     [rbx], si
0x18009c1b0  jnz     loc_18009C2EF
0x18009c1b6  mov     rcx, rbx; lpsz
0x18009c1b9  call    cs:__imp_CharNextW
0x18009c1bf  mov     [rdi], rax
0x18009c1c2  cmp     [rax], si
0x18009c1c5  jnz     short loc_18009C1EB
0x18009c1c7  mov     rdx, rax; unsigned __int16 *
0x18009c1ca  mov     r8d, 1; int
0x18009c1d0  lea     rcx, [rbp+57h+var_98]; this
0x18009c1d4  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18009c1d9  test    eax, eax
0x18009c1db  jnz     loc_18009C2DB
0x18009c1e1  mov     ebx, 8007000Eh
0x18009c1e6  jmp     loc_18009C313
0x18009c1eb  mov     edx, esi; unsigned __int16
0x18009c1ed  mov     rcx, rax; lpsz
0x18009c1f0  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18009c1f5  mov     rsi, rax
0x18009c1f8  test    rax, rax
0x18009c1fb  jz      loc_18009C2FE
0x18009c201  mov     rcx, rax
0x18009c204  sub     rcx, [rdi]
0x18009c207  sar     rcx, 1
0x18009c20a  cmp     rcx, 1Fh
0x18009c20e  jg      loc_18009C2F7
0x18009c214  movsxd  r9, ecx
0x18009c217  mov     r8, [rdi]
0x18009c21a  mov     edx, 20h ; ' '
0x18009c21f  lea     rcx, [rbp+57h+String2]
0x18009c223  call    cs:__imp__o_wcsncpy_s
0x18009c229  mov     ecx, eax; int
0x18009c22b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18009c230  mov     rbx, [rdi+8]
0x18009c234  lea     r12, [rbx+20h]
0x18009c238  mov     rcx, r12; lpCriticalSection
0x18009c23b  call    cs:__imp_EnterCriticalSection
0x18009c241  lea     r14, [rbx+8]
0x18009c245  mov     ebx, r13d
0x18009c248  cmp     ebx, [r14+10h]
0x18009c24c  jge     short loc_18009C27E
0x18009c24e  movsxd  rax, ebx
0x18009c251  mov     rcx, [r14]
0x18009c254  lea     rdx, [rbp+57h+String2]; lpString2
0x18009c258  mov     rcx, [rcx+rax*8]; lpString1
0x18009c25c  call    cs:__imp_lstrcmpiW
0x18009c262  test    eax, eax
0x18009c264  jz      short loc_18009C26A
0x18009c266  inc     ebx
0x18009c268  jmp     short loc_18009C248
0x18009c26a  cmp     ebx, 0FFFFFFFFh
0x18009c26d  jz      short loc_18009C27E
0x18009c26f  mov     edx, ebx
0x18009c271  mov     rcx, r14
0x18009c274  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18009c279  mov     rbx, [rax]
0x18009c27c  jmp     short loc_18009C281
0x18009c27e  mov     rbx, r13
0x18009c281  mov     rcx, r12; lpCriticalSection
0x18009c284  call    cs:__imp_LeaveCriticalSection
0x18009c28a  test    rbx, rbx
0x18009c28d  jz      short loc_18009C2FE
0x18009c28f  mov     [rbp+57h+cb], r13
0x18009c293  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009c297  inc     r8; int
0x18009c29a  cmp     [rbx+r8*2], r13w
0x18009c29f  jnz     short loc_18009C297
0x18009c2a1  mov     rdx, rbx; unsigned __int16 *
0x18009c2a4  lea     rcx, [rbp+57h+var_98]; this
0x18009c2a8  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18009c2ad  mov     ebx, eax
0x18009c2af  lea     rcx, [rbp+57h+cb]
0x18009c2b3  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18009c2b8  test    ebx, ebx
0x18009c2ba  jz      loc_18009C1E1
0x18009c2c0  mov     rax, [rdi]
0x18009c2c3  jmp     short loc_18009C2D1
0x18009c2c5  mov     rcx, rax; lpsz
0x18009c2c8  call    cs:__imp_CharNextW
0x18009c2ce  mov     [rdi], rax
0x18009c2d1  cmp     rax, rsi
0x18009c2d4  jnz     short loc_18009C2C5
0x18009c2d6  mov     esi, 25h ; '%'
0x18009c2db  mov     rcx, [rdi]; lpsz
0x18009c2de  call    cs:__imp_CharNextW
0x18009c2e4  mov     rbx, rax
0x18009c2e7  mov     [rdi], rax
0x18009c2ea  jmp     loc_18009C1A3
0x18009c2ef  mov     rdx, rbx
0x18009c2f2  jmp     loc_18009C1CA
0x18009c2f7  mov     ebx, 80004005h
0x18009c2fc  jmp     short loc_18009C313
0x18009c2fe  mov     ebx, 80020009h
0x18009c303  jmp     short loc_18009C313
0x18009c305  mov     ebx, r13d
0x18009c308  mov     rcx, [rbp+57h+pv]
0x18009c30c  mov     [rbp+57h+pv], r13
0x18009c310  mov     [r15], rcx
0x18009c313  mov     rcx, [rbp+57h+pv]; pv
0x18009c317  call    cs:__imp_CoTaskMemFree
0x18009c31d  mov     eax, ebx
0x18009c31f  jmp     short loc_18009C326
0x18009c321  mov     eax, 80004003h
0x18009c326  mov     rcx, [rbp+57h+var_40]
0x18009c32a  xor     rcx, rsp; StackCookie
0x18009c32d  call    __security_check_cookie
0x18009c332  mov     rbx, [rsp+0C0h+arg_8]
0x18009c33a  add     rsp, 90h
0x18009c341  pop     r15
0x18009c343  pop     r14
0x18009c345  pop     r13
0x18009c347  pop     r12
0x18009c349  pop     rdi
0x18009c34a  pop     rsi
0x18009c34b  pop     rbp
0x18009c34c  retn
```
