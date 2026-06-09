# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180019890`
- end: `0x180019b3a`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `682`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019cec`

## callees

- `0x180011698`
- `0x180016a40`
- `0x180018014`
- `0x180018078`
- `0x180018ad0`
- `0x180019644`
- `0x180019890`
- `0x18001a8e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800199e5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800199e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019a03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019a03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019920`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019920`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019afd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019afd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019975`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019aa2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019abe`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019975`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019aa2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019abe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180019a2a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180019a2a`

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
0x180019890  mov     [rsp-8+arg_8], rbx
0x180019895  push    rbp
0x180019896  push    rsi
0x180019897  push    rdi
0x180019898  push    r12
0x18001989a  push    r13
0x18001989c  push    r14
0x18001989e  push    r15
0x1800198a0  lea     rbp, [rsp-27h]
0x1800198a5  sub     rsp, 90h
0x1800198ac  mov     rax, cs:__security_cookie
0x1800198b3  xor     rax, rsp
0x1800198b6  mov     [rbp+57h+var_40], rax
0x1800198ba  mov     r15, r8
0x1800198bd  mov     rbx, rdx
0x1800198c0  mov     rdi, rcx
0x1800198c3  xor     r13d, r13d
0x1800198c6  test    rdx, rdx
0x1800198c9  jz      loc_180019B0D
0x1800198cf  test    r8, r8
0x1800198d2  jz      loc_180019B0D
0x1800198d8  mov     [r8], r13
0x1800198db  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800198df  inc     rdx
0x1800198e2  cmp     [rbx+rdx*2], r13w
0x1800198e7  jnz     short loc_1800198DF
0x1800198e9  add     edx, edx
0x1800198eb  mov     eax, 3E8h
0x1800198f0  cmp     edx, 64h ; 'd'
0x1800198f3  cmovl   edx, eax
0x1800198f6  mov     [rbp+57h+var_98], r13d
0x1800198fa  mov     [rbp+57h+var_94], edx
0x1800198fd  mov     dword ptr [rbp+57h+cb], r13d
0x180019901  mov     r8d, 2
0x180019907  lea     rcx, [rbp+57h+cb]
0x18001990b  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x180019910  test    eax, eax
0x180019912  jns     short loc_18001991D
0x180019914  mov     rax, r13
0x180019917  mov     [rbp+57h+pv], r13
0x18001991b  jmp     short loc_180019939
0x18001991d  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180019920  call    cs:__imp_CoTaskMemAlloc
0x180019927  nop     dword ptr [rax+rax+00h]
0x18001992c  mov     [rbp+57h+pv], rax
0x180019930  test    rax, rax
0x180019933  jz      short loc_180019939
0x180019935  mov     [rax], r13w
0x180019939  test    rax, rax
0x18001993c  jnz     short loc_180019957
0x18001993e  mov     rcx, rax; pv
0x180019941  call    cs:__imp_CoTaskMemFree
0x180019948  nop     dword ptr [rax+rax+00h]
0x18001994d  mov     eax, 8007000Eh
0x180019952  jmp     loc_180019B12
0x180019957  mov     [rdi], rbx
0x18001995a  mov     esi, 25h ; '%'
0x18001995f  cmp     [rbx], r13w
0x180019963  jz      loc_180019AEB
0x180019969  cmp     [rbx], si
0x18001996c  jnz     loc_180019AD5
0x180019972  mov     rcx, rbx; lpsz
0x180019975  call    cs:__imp_CharNextW
0x18001997c  nop     dword ptr [rax+rax+00h]
0x180019981  mov     [rdi], rax
0x180019984  cmp     [rax], si
0x180019987  jnz     short loc_1800199AD
0x180019989  mov     rdx, rax; unsigned __int16 *
0x18001998c  mov     r8d, 1; int
0x180019992  lea     rcx, [rbp+57h+var_98]; this
0x180019996  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18001999b  test    eax, eax
0x18001999d  jnz     loc_180019ABB
0x1800199a3  mov     ebx, 8007000Eh
0x1800199a8  jmp     loc_180019AF9
0x1800199ad  mov     edx, esi; unsigned __int16
0x1800199af  mov     rcx, rax; lpsz
0x1800199b2  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800199b7  mov     rsi, rax
0x1800199ba  test    rax, rax
0x1800199bd  jz      loc_180019AE4
0x1800199c3  mov     rcx, rax
0x1800199c6  sub     rcx, [rdi]
0x1800199c9  sar     rcx, 1
0x1800199cc  cmp     rcx, 1Fh
0x1800199d0  jg      loc_180019ADD
0x1800199d6  movsxd  r9, ecx
0x1800199d9  mov     r8, [rdi]
0x1800199dc  mov     edx, 20h ; ' '
0x1800199e1  lea     rcx, [rbp+57h+String2]
0x1800199e5  call    cs:__imp__o_wcsncpy_s
0x1800199ec  nop     dword ptr [rax+rax+00h]
0x1800199f1  mov     ecx, eax; int
0x1800199f3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800199f8  mov     rbx, [rdi+8]
0x1800199fc  lea     r12, [rbx+20h]
0x180019a00  mov     rcx, r12; lpCriticalSection
0x180019a03  call    cs:__imp_EnterCriticalSection
0x180019a0a  nop     dword ptr [rax+rax+00h]
0x180019a0f  lea     r14, [rbx+8]
0x180019a13  mov     ebx, r13d
0x180019a16  cmp     ebx, [r14+10h]
0x180019a1a  jge     short loc_180019A52
0x180019a1c  movsxd  rax, ebx
0x180019a1f  mov     rcx, [r14]
0x180019a22  lea     rdx, [rbp+57h+String2]; lpString2
0x180019a26  mov     rcx, [rcx+rax*8]; lpString1
0x180019a2a  call    cs:__imp_lstrcmpiW
0x180019a31  nop     dword ptr [rax+rax+00h]
0x180019a36  test    eax, eax
0x180019a38  jz      short loc_180019A3E
0x180019a3a  inc     ebx
0x180019a3c  jmp     short loc_180019A16
0x180019a3e  cmp     ebx, 0FFFFFFFFh
0x180019a41  jz      short loc_180019A52
0x180019a43  mov     edx, ebx
0x180019a45  mov     rcx, r14
0x180019a48  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180019a4d  mov     rbx, [rax]
0x180019a50  jmp     short loc_180019A55
0x180019a52  mov     rbx, r13
0x180019a55  mov     rcx, r12; lpCriticalSection
0x180019a58  call    cs:__imp_LeaveCriticalSection
0x180019a5f  nop     dword ptr [rax+rax+00h]
0x180019a64  test    rbx, rbx
0x180019a67  jz      short loc_180019AE4
0x180019a69  mov     [rbp+57h+cb], r13
0x180019a6d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019a71  inc     r8; int
0x180019a74  cmp     [rbx+r8*2], r13w
0x180019a79  jnz     short loc_180019A71
0x180019a7b  mov     rdx, rbx; unsigned __int16 *
0x180019a7e  lea     rcx, [rbp+57h+var_98]; this
0x180019a82  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180019a87  mov     ebx, eax
0x180019a89  lea     rcx, [rbp+57h+cb]
0x180019a8d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180019a92  test    ebx, ebx
0x180019a94  jz      loc_1800199A3
0x180019a9a  mov     rax, [rdi]
0x180019a9d  jmp     short loc_180019AB1
0x180019a9f  mov     rcx, rax; lpsz
0x180019aa2  call    cs:__imp_CharNextW
0x180019aa9  nop     dword ptr [rax+rax+00h]
0x180019aae  mov     [rdi], rax
0x180019ab1  cmp     rax, rsi
0x180019ab4  jnz     short loc_180019A9F
0x180019ab6  mov     esi, 25h ; '%'
0x180019abb  mov     rcx, [rdi]; lpsz
0x180019abe  call    cs:__imp_CharNextW
0x180019ac5  nop     dword ptr [rax+rax+00h]
0x180019aca  mov     rbx, rax
0x180019acd  mov     [rdi], rax
0x180019ad0  jmp     loc_18001995F
0x180019ad5  mov     rdx, rbx
0x180019ad8  jmp     loc_18001998C
0x180019add  mov     ebx, 80004005h
0x180019ae2  jmp     short loc_180019AF9
0x180019ae4  mov     ebx, 80020009h
0x180019ae9  jmp     short loc_180019AF9
0x180019aeb  mov     ebx, r13d
0x180019aee  mov     rcx, [rbp+57h+pv]
0x180019af2  mov     [rbp+57h+pv], r13
0x180019af6  mov     [r15], rcx
0x180019af9  mov     rcx, [rbp+57h+pv]; pv
0x180019afd  call    cs:__imp_CoTaskMemFree
0x180019b04  nop     dword ptr [rax+rax+00h]
0x180019b09  mov     eax, ebx
0x180019b0b  jmp     short loc_180019B12
0x180019b0d  mov     eax, 80004003h
0x180019b12  mov     rcx, [rbp+57h+var_40]
0x180019b16  xor     rcx, rsp; StackCookie
0x180019b19  call    __security_check_cookie
0x180019b1e  mov     rbx, [rsp+0C0h+arg_8]
0x180019b26  add     rsp, 90h
0x180019b2d  pop     r15
0x180019b2f  pop     r14
0x180019b31  pop     r13
0x180019b33  pop     r12
0x180019b35  pop     rdi
0x180019b36  pop     rsi
0x180019b37  pop     rbp
0x180019b38  retn
```
