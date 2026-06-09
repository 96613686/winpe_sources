# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x140008428`
- end: `0x14000868c`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `__int64 __fastcall(const wchar_t **this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140009430`

## callees

- `0x140003340`
- `0x140004c68`
- `0x140004d30`
- `0x140006f0c`
- `0x140008428`
- `0x14000a974`
- `0x140015aa0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1400085c3`
- `KERNEL32!LeaveCriticalSection` at `0x1400085c3`
- `KERNEL32!lstrcmpiW` at `0x14000859b`
- `KERNEL32!lstrcmpiW` at `0x14000859b`
- `KERNEL32!EnterCriticalSection` at `0x14000857a`
- `KERNEL32!EnterCriticalSection` at `0x14000857a`
- `USER32!CharNextW` at `0x1400084f8`
- `USER32!CharNextW` at `0x140008607`
- `USER32!CharNextW` at `0x14000861d`
- `USER32!CharNextW` at `0x1400084f8`
- `USER32!CharNextW` at `0x140008607`
- `USER32!CharNextW` at `0x14000861d`
- `msvcrt!wcsncpy_s` at `0x140008562`
- `msvcrt!wcsncpy_s` at `0x140008562`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400084ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400084ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400084af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400084af`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, unsigned __int16 **a3)
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
  errno_t v17; // eax
  const wchar_t *v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  const wchar_t *v20; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v26; // rcx
  _DWORD v27[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  _QWORD *v29; // [rsp+30h] [rbp-39h] BYREF
  wchar_t Destination[32]; // [rsp+40h] [rbp-29h] BYREF

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
  v27[0] = 0;
  v27[1] = v7;
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
  *this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_18:
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v12, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v11 = CharNextW(v4);
    *this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_18;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_39;
    v16 = v14 - *this;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_41;
    }
    v17 = wcsncpy_s(Destination, 0x20u, *this, (int)v16);
    ATL::AtlCrtErrorCheck(v17);
    v18 = this[1];
    v19 = (struct _RTL_CRITICAL_SECTION *)(v18 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
    v20 = v18 + 4;
    for ( i = 0; (signed int)i < *((_DWORD *)v20 + 4); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v20 + 8LL * (int)i), Destination) )
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
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v29);
    if ( !v24 )
    {
LABEL_19:
      v13 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *this; j != v15; *this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*this);
    *this = v4;
  }
  v13 = 0;
  v26 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x140008428  mov     [rsp-8+arg_8], rbx
0x14000842d  push    rbp
0x14000842e  push    rsi
0x14000842f  push    rdi
0x140008430  push    r12
0x140008432  push    r13
0x140008434  push    r14
0x140008436  push    r15
0x140008438  lea     rbp, [rsp-27h]
0x14000843d  sub     rsp, 90h
0x140008444  mov     rax, cs:__security_cookie
0x14000844b  xor     rax, rsp
0x14000844e  mov     [rbp+57h+var_40], rax
0x140008452  mov     r15, r8
0x140008455  mov     rbx, rdx
0x140008458  mov     rdi, rcx
0x14000845b  xor     r13d, r13d
0x14000845e  test    rdx, rdx
0x140008461  jz      loc_140008660
0x140008467  test    r8, r8
0x14000846a  jz      loc_140008660
0x140008470  mov     [r8], r13
0x140008473  or      rax, 0FFFFFFFFFFFFFFFFh
0x140008477  inc     rax
0x14000847a  cmp     [rdx+rax*2], r13w
0x14000847f  jnz     short loc_140008477
0x140008481  add     eax, eax
0x140008483  mov     ecx, 3E8h
0x140008488  cmp     eax, 64h ; 'd'
0x14000848b  cmovl   eax, ecx
0x14000848e  mov     [rbp+57h+var_A0], r13d
0x140008492  mov     [rbp+57h+var_9C], eax
0x140008495  mov     ecx, eax
0x140008497  add     rcx, rcx
0x14000849a  mov     eax, 0FFFFFFFFh
0x14000849f  cmp     rcx, rax
0x1400084a2  jbe     short loc_1400084AD
0x1400084a4  mov     rax, r13
0x1400084a7  mov     [rbp+57h+pv], r13
0x1400084ab  jmp     short loc_1400084C2
0x1400084ad  mov     ecx, ecx; cb
0x1400084af  call    cs:__imp_CoTaskMemAlloc
0x1400084b5  mov     [rbp+57h+pv], rax
0x1400084b9  test    rax, rax
0x1400084bc  jz      short loc_1400084C2
0x1400084be  mov     [rax], r13w
0x1400084c2  test    rax, rax
0x1400084c5  jnz     short loc_1400084DA
0x1400084c7  mov     rcx, rax; pv
0x1400084ca  call    cs:__imp_CoTaskMemFree
0x1400084d0  mov     eax, 8007000Eh
0x1400084d5  jmp     loc_140008665
0x1400084da  mov     [rdi], rbx
0x1400084dd  mov     esi, 25h ; '%'
0x1400084e2  cmp     [rbx], r13w
0x1400084e6  jz      loc_140008644
0x1400084ec  cmp     [rbx], si
0x1400084ef  jnz     loc_14000862E
0x1400084f5  mov     rcx, rbx; lpsz
0x1400084f8  call    cs:__imp_CharNextW
0x1400084fe  mov     [rdi], rax
0x140008501  cmp     [rax], si
0x140008504  jnz     short loc_14000852A
0x140008506  mov     rdx, rax; unsigned __int16 *
0x140008509  mov     r8d, 1; int
0x14000850f  lea     rcx, [rbp+57h+var_A0]; this
0x140008513  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140008518  test    eax, eax
0x14000851a  jnz     loc_14000861A
0x140008520  mov     ebx, 8007000Eh
0x140008525  jmp     loc_140008652
0x14000852a  mov     edx, esi; unsigned __int16
0x14000852c  mov     rcx, rax; lpsz
0x14000852f  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x140008534  mov     rsi, rax
0x140008537  test    rax, rax
0x14000853a  jz      loc_14000863D
0x140008540  mov     rcx, rax
0x140008543  sub     rcx, [rdi]
0x140008546  sar     rcx, 1
0x140008549  cmp     rcx, 1Fh
0x14000854d  jg      loc_140008636
0x140008553  movsxd  r9, ecx; MaxCount
0x140008556  mov     r8, [rdi]; Source
0x140008559  mov     edx, 20h ; ' '; SizeInWords
0x14000855e  lea     rcx, [rbp+57h+Destination]; Destination
0x140008562  call    cs:__imp_wcsncpy_s
0x140008568  mov     ecx, eax; int
0x14000856a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000856f  mov     rbx, [rdi+8]
0x140008573  lea     r12, [rbx+20h]
0x140008577  mov     rcx, r12; lpCriticalSection
0x14000857a  call    cs:__imp_EnterCriticalSection
0x140008580  lea     r14, [rbx+8]
0x140008584  mov     ebx, r13d
0x140008587  cmp     ebx, [r14+10h]
0x14000858b  jge     short loc_1400085BD
0x14000858d  movsxd  rax, ebx
0x140008590  mov     rcx, [r14]
0x140008593  lea     rdx, [rbp+57h+Destination]; lpString2
0x140008597  mov     rcx, [rcx+rax*8]; lpString1
0x14000859b  call    cs:__imp_lstrcmpiW
0x1400085a1  test    eax, eax
0x1400085a3  jz      short loc_1400085A9
0x1400085a5  inc     ebx
0x1400085a7  jmp     short loc_140008587
0x1400085a9  cmp     ebx, 0FFFFFFFFh
0x1400085ac  jz      short loc_1400085BD
0x1400085ae  mov     edx, ebx
0x1400085b0  mov     rcx, r14
0x1400085b3  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1400085b8  mov     rbx, [rax]
0x1400085bb  jmp     short loc_1400085C0
0x1400085bd  mov     rbx, r13
0x1400085c0  mov     rcx, r12; lpCriticalSection
0x1400085c3  call    cs:__imp_LeaveCriticalSection
0x1400085c9  test    rbx, rbx
0x1400085cc  jz      short loc_14000863D
0x1400085ce  mov     [rbp+57h+var_90], r13
0x1400085d2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400085d6  inc     r8; int
0x1400085d9  cmp     [rbx+r8*2], r13w
0x1400085de  jnz     short loc_1400085D6
0x1400085e0  mov     rdx, rbx; unsigned __int16 *
0x1400085e3  lea     rcx, [rbp+57h+var_A0]; this
0x1400085e7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1400085ec  mov     ebx, eax
0x1400085ee  lea     rcx, [rbp+57h+var_90]
0x1400085f2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1400085f7  test    ebx, ebx
0x1400085f9  jz      loc_140008520
0x1400085ff  mov     rax, [rdi]
0x140008602  jmp     short loc_140008610
0x140008604  mov     rcx, rax; lpsz
0x140008607  call    cs:__imp_CharNextW
0x14000860d  mov     [rdi], rax
0x140008610  cmp     rax, rsi
0x140008613  jnz     short loc_140008604
0x140008615  mov     esi, 25h ; '%'
0x14000861a  mov     rcx, [rdi]; lpsz
0x14000861d  call    cs:__imp_CharNextW
0x140008623  mov     rbx, rax
0x140008626  mov     [rdi], rax
0x140008629  jmp     loc_1400084E2
0x14000862e  mov     rdx, rbx
0x140008631  jmp     loc_140008509
0x140008636  mov     ebx, 80004005h
0x14000863b  jmp     short loc_140008652
0x14000863d  mov     ebx, 80020009h
0x140008642  jmp     short loc_140008652
0x140008644  mov     ebx, r13d
0x140008647  mov     rcx, [rbp+57h+pv]
0x14000864b  mov     [rbp+57h+pv], r13
0x14000864f  mov     [r15], rcx
0x140008652  mov     rcx, [rbp+57h+pv]; pv
0x140008656  call    cs:__imp_CoTaskMemFree
0x14000865c  mov     eax, ebx
0x14000865e  jmp     short loc_140008665
0x140008660  mov     eax, 80004003h
0x140008665  mov     rcx, [rbp+57h+var_40]
0x140008669  xor     rcx, rsp; StackCookie
0x14000866c  call    __security_check_cookie
0x140008671  mov     rbx, [rsp+0C0h+arg_8]
0x140008679  add     rsp, 90h
0x140008680  pop     r15
0x140008682  pop     r14
0x140008684  pop     r13
0x140008686  pop     r12
0x140008688  pop     rdi
0x140008689  pop     rsi
0x14000868a  pop     rbp
0x14000868b  retn
```
