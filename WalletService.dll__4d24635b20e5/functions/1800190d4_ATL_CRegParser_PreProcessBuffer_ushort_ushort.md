# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800190d4`
- end: `0x18001932d`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `601`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019514`

## callees

- `0x18000dd14`
- `0x180017530`
- `0x180018024`
- `0x1800186e0`
- `0x1800190d4`
- `0x18001a1d8`
- `0x180043090`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180019203`
- `msvcrt!wcsncpy_s` at `0x180019203`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019264`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019264`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001921b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001921b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019199`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800192a8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800192be`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019199`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800192a8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800192be`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001923c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001923c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019156`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800192f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019156`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800192f7`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, LPVOID *a3)
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
  _DWORD v26[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v28; // [rsp+30h] [rbp-39h] BYREF
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
  v26[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v26[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v9 = CoTaskMemAlloc((unsigned int)v8);
  pv = v9;
  if ( !v9 )
    goto LABEL_9;
  *v9 = 0;
  *this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_16:
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v12, 1) )
        goto LABEL_17;
      goto LABEL_34;
    }
    v11 = CharNextW(v4);
    *this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_16;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_37;
    v16 = v14 - *this;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_39;
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
          goto LABEL_27;
        }
        break;
      }
    }
    v22 = 0;
LABEL_27:
    LeaveCriticalSection(v19);
    if ( !v22 )
    {
LABEL_37:
      v13 = -2147352567;
      goto LABEL_39;
    }
    v28 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v28);
    if ( !v24 )
    {
LABEL_17:
      v13 = -2147024882;
      goto LABEL_39;
    }
    for ( j = *this; j != v15; *this = j )
      j = CharNextW(j);
LABEL_34:
    v4 = CharNextW(*this);
    *this = v4;
  }
  v13 = 0;
  *a3 = pv;
  pv = 0;
LABEL_39:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x1800190d4  mov     [rsp-8+arg_8], rbx
0x1800190d9  push    rbp
0x1800190da  push    rsi
0x1800190db  push    rdi
0x1800190dc  push    r12
0x1800190de  push    r13
0x1800190e0  push    r14
0x1800190e2  push    r15
0x1800190e4  lea     rbp, [rsp-27h]
0x1800190e9  sub     rsp, 90h
0x1800190f0  mov     rax, cs:__security_cookie
0x1800190f7  xor     rax, rsp
0x1800190fa  mov     [rbp+57h+var_40], rax
0x1800190fe  xor     r13d, r13d
0x180019101  mov     r15, r8
0x180019104  mov     rbx, rdx
0x180019107  mov     rdi, rcx
0x18001910a  test    rdx, rdx
0x18001910d  jz      loc_180019301
0x180019113  test    r8, r8
0x180019116  jz      loc_180019301
0x18001911c  mov     [r8], r13
0x18001911f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019123  inc     rax
0x180019126  cmp     [rdx+rax*2], r13w
0x18001912b  jnz     short loc_180019123
0x18001912d  add     eax, eax
0x18001912f  mov     [rbp+57h+var_A0], r13d
0x180019133  cmp     eax, 64h ; 'd'
0x180019136  mov     ecx, 3E8h
0x18001913b  cmovl   eax, ecx
0x18001913e  mov     ecx, eax
0x180019140  mov     [rbp+57h+var_9C], eax
0x180019143  add     rcx, rcx
0x180019146  mov     eax, 0FFFFFFFFh
0x18001914b  cmp     rcx, rax
0x18001914e  jbe     short loc_180019166
0x180019150  mov     rax, r13
0x180019153  mov     rcx, rax; pv
0x180019156  call    cs:__imp_CoTaskMemFree
0x18001915c  mov     eax, 8007000Eh
0x180019161  jmp     loc_180019306
0x180019166  mov     ecx, ecx; cb
0x180019168  call    cs:__imp_CoTaskMemAlloc
0x18001916e  mov     [rbp+57h+pv], rax
0x180019172  test    rax, rax
0x180019175  jz      short loc_180019153
0x180019177  mov     [rax], r13w
0x18001917b  mov     esi, 25h ; '%'
0x180019180  mov     [rdi], rbx
0x180019183  cmp     [rbx], r13w
0x180019187  jz      loc_1800192E5
0x18001918d  cmp     [rbx], si
0x180019190  jnz     loc_1800192CF
0x180019196  mov     rcx, rbx; lpsz
0x180019199  call    cs:__imp_CharNextW
0x18001919f  mov     [rdi], rax
0x1800191a2  cmp     [rax], si
0x1800191a5  jnz     short loc_1800191CB
0x1800191a7  mov     rdx, rax; unsigned __int16 *
0x1800191aa  mov     r8d, 1; int
0x1800191b0  lea     rcx, [rbp+57h+var_A0]; this
0x1800191b4  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800191b9  test    eax, eax
0x1800191bb  jnz     loc_1800192BB
0x1800191c1  mov     ebx, 8007000Eh
0x1800191c6  jmp     loc_1800192F3
0x1800191cb  mov     edx, esi; unsigned __int16
0x1800191cd  mov     rcx, rax; lpsz
0x1800191d0  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800191d5  mov     rsi, rax
0x1800191d8  test    rax, rax
0x1800191db  jz      loc_1800192DE
0x1800191e1  mov     rcx, rax
0x1800191e4  sub     rcx, [rdi]
0x1800191e7  sar     rcx, 1
0x1800191ea  cmp     rcx, 1Fh
0x1800191ee  jg      loc_1800192D7
0x1800191f4  mov     r8, [rdi]; Source
0x1800191f7  mov     edx, 20h ; ' '; SizeInWords
0x1800191fc  movsxd  r9, ecx; MaxCount
0x1800191ff  lea     rcx, [rbp+57h+Destination]; Destination
0x180019203  call    cs:__imp_wcsncpy_s
0x180019209  mov     ecx, eax; int
0x18001920b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180019210  mov     rbx, [rdi+8]
0x180019214  lea     r12, [rbx+20h]
0x180019218  mov     rcx, r12; lpCriticalSection
0x18001921b  call    cs:__imp_EnterCriticalSection
0x180019221  lea     r14, [rbx+8]
0x180019225  mov     ebx, r13d
0x180019228  cmp     ebx, [r14+10h]
0x18001922c  jge     short loc_18001925E
0x18001922e  mov     rcx, [r14]
0x180019231  lea     rdx, [rbp+57h+Destination]; lpString2
0x180019235  movsxd  rax, ebx
0x180019238  mov     rcx, [rcx+rax*8]; lpString1
0x18001923c  call    cs:__imp_lstrcmpiW
0x180019242  test    eax, eax
0x180019244  jz      short loc_18001924A
0x180019246  inc     ebx
0x180019248  jmp     short loc_180019228
0x18001924a  cmp     ebx, 0FFFFFFFFh
0x18001924d  jz      short loc_18001925E
0x18001924f  mov     edx, ebx
0x180019251  mov     rcx, r14
0x180019254  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180019259  mov     rbx, [rax]
0x18001925c  jmp     short loc_180019261
0x18001925e  mov     rbx, r13
0x180019261  mov     rcx, r12; lpCriticalSection
0x180019264  call    cs:__imp_LeaveCriticalSection
0x18001926a  test    rbx, rbx
0x18001926d  jz      short loc_1800192DE
0x18001926f  mov     [rbp+57h+var_90], r13
0x180019273  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019277  inc     r8; int
0x18001927a  cmp     [rbx+r8*2], r13w
0x18001927f  jnz     short loc_180019277
0x180019281  mov     rdx, rbx; unsigned __int16 *
0x180019284  lea     rcx, [rbp+57h+var_A0]; this
0x180019288  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18001928d  lea     rcx, [rbp+57h+var_90]
0x180019291  mov     ebx, eax
0x180019293  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180019298  test    ebx, ebx
0x18001929a  jz      loc_1800191C1
0x1800192a0  mov     rax, [rdi]
0x1800192a3  jmp     short loc_1800192B1
0x1800192a5  mov     rcx, rax; lpsz
0x1800192a8  call    cs:__imp_CharNextW
0x1800192ae  mov     [rdi], rax
0x1800192b1  cmp     rax, rsi
0x1800192b4  jnz     short loc_1800192A5
0x1800192b6  mov     esi, 25h ; '%'
0x1800192bb  mov     rcx, [rdi]; lpsz
0x1800192be  call    cs:__imp_CharNextW
0x1800192c4  mov     rbx, rax
0x1800192c7  mov     [rdi], rax
0x1800192ca  jmp     loc_180019183
0x1800192cf  mov     rdx, rbx
0x1800192d2  jmp     loc_1800191AA
0x1800192d7  mov     ebx, 80004005h
0x1800192dc  jmp     short loc_1800192F3
0x1800192de  mov     ebx, 80020009h
0x1800192e3  jmp     short loc_1800192F3
0x1800192e5  mov     rcx, [rbp+57h+pv]
0x1800192e9  mov     ebx, r13d
0x1800192ec  mov     [r15], rcx
0x1800192ef  mov     [rbp+57h+pv], r13
0x1800192f3  mov     rcx, [rbp+57h+pv]; pv
0x1800192f7  call    cs:__imp_CoTaskMemFree
0x1800192fd  mov     eax, ebx
0x1800192ff  jmp     short loc_180019306
0x180019301  mov     eax, 80004003h
0x180019306  mov     rcx, [rbp+57h+var_40]
0x18001930a  xor     rcx, rsp; StackCookie
0x18001930d  call    __security_check_cookie
0x180019312  mov     rbx, [rsp+0C0h+arg_8]
0x18001931a  add     rsp, 90h
0x180019321  pop     r15
0x180019323  pop     r14
0x180019325  pop     r13
0x180019327  pop     r12
0x180019329  pop     rdi
0x18001932a  pop     rsi
0x18001932b  pop     rbp
0x18001932c  retn
```
