# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18083cc04`
- end: `0x18083ce5d`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `601`
- prototype: `HRESULT __fastcall(ATL::CRegParser *this, wchar_t *lpszReg, wchar_t **ppszReg)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18083cfbc`

## callees

- `0x18076e110`
- `0x180839f68`
- `0x18083aee8`
- `0x18083b948`
- `0x18083c868`
- `0x18083cc04`
- `0x18083e2d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18083cd33`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18083cd33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18083cd4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18083cd4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18083cd94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18083cd94`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18083ccc9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18083cdd8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18083cdee`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18083ccc9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18083cdd8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18083cdee`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18083cd6c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18083cd6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18083cc98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18083cc98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18083cc86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18083ce27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18083cc86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18083ce27`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(ATL::CRegParser *this, wchar_t *lpszReg, wchar_t **ppszReg)
{
  wchar_t *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  wchar_t *v11; // rax
  const wchar_t *v12; // rdx
  unsigned int v13; // ebx
  wchar_t *v14; // rax
  wchar_t *v15; // rsi
  __int64 v16; // rcx
  int v17; // eax
  ATL::CRegObject *m_pRegObj; // rbx
  _RTL_CRITICAL_SECTION *p_m_sec; // r12
  ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper> *p_m_RepMap; // r14
  int i; // ebx
  const wchar_t *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  wchar_t *j; // rax
  ATL::CRegParser::CParseBuffer pb; // [rsp+20h] [rbp-49h] BYREF
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator> v27; // [rsp+30h] [rbp-39h] BYREF
  wchar_t buf[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = lpszReg;
  if ( !lpszReg || !ppszReg )
    return 2147500035LL;
  *ppszReg = 0;
  v6 = -1;
  do
    ++v6;
  while ( lpszReg[v6] );
  v7 = 2 * v6;
  pb.nPos = 0;
  if ( v7 < 100 )
    v7 = 1000;
  pb.nSize = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v9 = CoTaskMemAlloc((unsigned int)v8);
  pb.p = v9;
  if ( !v9 )
    goto LABEL_9;
  *v9 = 0;
  this->m_pchCur = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_16:
      if ( !ATL::CRegParser::CParseBuffer::Append(&pb, v12, 1) )
        goto LABEL_17;
      goto LABEL_34;
    }
    v11 = CharNextW(v4);
    this->m_pchCur = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_16;
    }
    v14 = ATL::CRegParser::StrChr(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_37;
    v16 = v14 - this->m_pchCur;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_39;
    }
    v17 = _o_wcsncpy_s(buf, 32, this->m_pchCur, (int)v16, *(_QWORD *)&pb.nPos);
    ATL::AtlCrtErrorCheck(v17);
    m_pRegObj = this->m_pRegObj;
    p_m_sec = &m_pRegObj->m_csMap.m_sec;
    EnterCriticalSection(&m_pRegObj->m_csMap.m_sec);
    p_m_RepMap = &m_pRegObj->m_RepMap;
    for ( i = 0; i < p_m_RepMap->m_nSize; ++i )
    {
      if ( !lstrcmpiW(p_m_RepMap->m_aKey[i], buf) )
      {
        if ( i != -1 )
        {
          v22 = *ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                   p_m_RepMap,
                   i);
          goto LABEL_27;
        }
        break;
      }
    }
    v22 = 0;
LABEL_27:
    LeaveCriticalSection(p_m_sec);
    if ( !v22 )
    {
LABEL_37:
      v13 = -2147352567;
      goto LABEL_39;
    }
    v27.m_pHead = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append(&pb, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v27);
    if ( !v24 )
    {
LABEL_17:
      v13 = -2147024882;
      goto LABEL_39;
    }
    for ( j = this->m_pchCur; j != v15; this->m_pchCur = j )
      j = CharNextW(j);
LABEL_34:
    v4 = CharNextW(this->m_pchCur);
    this->m_pchCur = v4;
  }
  v13 = 0;
  *ppszReg = pb.p;
  pb.p = 0;
LABEL_39:
  CoTaskMemFree(pb.p);
  return v13;
}

```

## disassembly

```asm
0x18083cc04  mov     [rsp-8+arg_8], rbx
0x18083cc09  push    rbp
0x18083cc0a  push    rsi
0x18083cc0b  push    rdi
0x18083cc0c  push    r12
0x18083cc0e  push    r13
0x18083cc10  push    r14
0x18083cc12  push    r15
0x18083cc14  lea     rbp, [rsp-27h]
0x18083cc19  sub     rsp, 90h
0x18083cc20  mov     rax, cs:__security_cookie
0x18083cc27  xor     rax, rsp
0x18083cc2a  mov     [rbp+57h+var_40], rax
0x18083cc2e  xor     r13d, r13d
0x18083cc31  mov     r15, ppszReg
0x18083cc34  mov     rbx, lpszReg
0x18083cc37  mov     rdi, this
0x18083cc3a  test    lpszReg, lpszReg
0x18083cc3d  jz      loc_18083CE31
0x18083cc43  test    ppszReg, ppszReg
0x18083cc46  jz      loc_18083CE31
0x18083cc4c  mov     [ppszReg], r13
0x18083cc4f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18083cc53  inc     rax
0x18083cc56  cmp     [lpszReg+rax*2], r13w
0x18083cc5b  jnz     short loc_18083CC53
0x18083cc5d  add     eax, eax
0x18083cc5f  mov     [rbp+57h+pb.nPos], r13d
0x18083cc63  cmp     eax, 64h ; 'd'
0x18083cc66  mov     ecx, 3E8h
0x18083cc6b  cmovl   eax, ecx
0x18083cc6e  mov     ecx, eax
0x18083cc70  mov     [rbp+57h+pb.nSize], eax
0x18083cc73  add     this, this
0x18083cc76  mov     eax, 0FFFFFFFFh
0x18083cc7b  cmp     this, rax
0x18083cc7e  jbe     short loc_18083CC96
0x18083cc80  mov     rax, r13
0x18083cc83  mov     this, rax; pv
0x18083cc86  call    cs:__imp_CoTaskMemFree
0x18083cc8c  mov     eax, 8007000Eh
0x18083cc91  jmp     loc_18083CE36
0x18083cc96  mov     ecx, ecx; cb
0x18083cc98  call    cs:__imp_CoTaskMemAlloc
0x18083cc9e  mov     [rbp+57h+pb.p], rax
0x18083cca2  test    rax, rax
0x18083cca5  jz      short loc_18083CC83
0x18083cca7  mov     [rax], r13w
0x18083ccab  mov     esi, 25h ; '%'
0x18083ccb0  mov     [rdi], rbx
0x18083ccb3  cmp     [rbx], r13w
0x18083ccb7  jz      loc_18083CE15
0x18083ccbd  cmp     [rbx], si
0x18083ccc0  jnz     loc_18083CDFF
0x18083ccc6  mov     this, rbx; lpsz
0x18083ccc9  call    cs:__imp_CharNextW
0x18083cccf  mov     [rdi], rax
0x18083ccd2  cmp     [rax], si
0x18083ccd5  jnz     short loc_18083CCFB
0x18083ccd7  mov     lpszReg, rax; pch
0x18083ccda  mov     r8d, 1; nChars
0x18083cce0  lea     this, [rbp+57h+pb]; this
0x18083cce4  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18083cce9  test    eax, eax
0x18083cceb  jnz     loc_18083CDEB
0x18083ccf1  mov     ebx, 8007000Eh
0x18083ccf6  jmp     loc_18083CE23
0x18083ccfb  mov     edx, esi; ch
0x18083ccfd  mov     this, rax; lpsz
0x18083cd00  call    ?StrChr@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChr(ushort *,ushort)
0x18083cd05  mov     rsi, rax
0x18083cd08  test    rax, rax
0x18083cd0b  jz      loc_18083CE0E
0x18083cd11  mov     this, rax
0x18083cd14  sub     this, [rdi]
0x18083cd17  sar     this, 1
0x18083cd1a  cmp     this, 1Fh
0x18083cd1e  jg      loc_18083CE07
0x18083cd24  mov     ppszReg, [rdi]
0x18083cd27  mov     edx, 20h ; ' '
0x18083cd2c  movsxd  r9, ecx
0x18083cd2f  lea     this, [rbp+57h+buf]
0x18083cd33  call    cs:__imp__o_wcsncpy_s
0x18083cd39  mov     ecx, eax; nError
0x18083cd3b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18083cd40  mov     rbx, [rdi+8]
0x18083cd44  lea     r12, [rbx+20h]
0x18083cd48  mov     this, r12; lpCriticalSection
0x18083cd4b  call    cs:__imp_EnterCriticalSection
0x18083cd51  lea     r14, [rbx+8]
0x18083cd55  mov     ebx, r13d
0x18083cd58  cmp     ebx, [r14+10h]
0x18083cd5c  jge     short loc_18083CD8E
0x18083cd5e  mov     this, [r14]
0x18083cd61  lea     lpszReg, [rbp+57h+buf]; lpString2
0x18083cd65  movsxd  rax, ebx
0x18083cd68  mov     this, [this+rax*8]; lpString1
0x18083cd6c  call    cs:__imp_lstrcmpiW
0x18083cd72  test    eax, eax
0x18083cd74  jz      short loc_18083CD7A
0x18083cd76  inc     ebx
0x18083cd78  jmp     short loc_18083CD58
0x18083cd7a  cmp     ebx, 0FFFFFFFFh
0x18083cd7d  jz      short loc_18083CD8E
0x18083cd7f  mov     edx, ebx; nIndex
0x18083cd81  mov     this, r14; this
0x18083cd84  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18083cd89  mov     rbx, [rax]
0x18083cd8c  jmp     short loc_18083CD91
0x18083cd8e  mov     rbx, r13
0x18083cd91  mov     this, r12; lpCriticalSection
0x18083cd94  call    cs:__imp_LeaveCriticalSection
0x18083cd9a  test    rbx, rbx
0x18083cd9d  jz      short loc_18083CE0E
0x18083cd9f  mov     [rbp+57h+var_90.m_pHead], r13
0x18083cda3  or      ppszReg, 0FFFFFFFFFFFFFFFFh
0x18083cda7  inc     ppszReg; nChars
0x18083cdaa  cmp     [rbx+ppszReg*2], r13w
0x18083cdaf  jnz     short loc_18083CDA7
0x18083cdb1  mov     lpszReg, rbx; pch
0x18083cdb4  lea     this, [rbp+57h+pb]; this
0x18083cdb8  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18083cdbd  lea     this, [rbp+57h+var_90]; this
0x18083cdc1  mov     ebx, eax
0x18083cdc3  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18083cdc8  test    ebx, ebx
0x18083cdca  jz      loc_18083CCF1
0x18083cdd0  mov     rax, [rdi]
0x18083cdd3  jmp     short loc_18083CDE1
0x18083cdd5  mov     this, rax; lpsz
0x18083cdd8  call    cs:__imp_CharNextW
0x18083cdde  mov     [rdi], rax
0x18083cde1  cmp     rax, rsi
0x18083cde4  jnz     short loc_18083CDD5
0x18083cde6  mov     esi, 25h ; '%'
0x18083cdeb  mov     this, [rdi]; lpsz
0x18083cdee  call    cs:__imp_CharNextW
0x18083cdf4  mov     rbx, rax
0x18083cdf7  mov     [rdi], rax
0x18083cdfa  jmp     loc_18083CCB3
0x18083cdff  mov     lpszReg, rbx
0x18083ce02  jmp     loc_18083CCDA
0x18083ce07  mov     ebx, 80004005h
0x18083ce0c  jmp     short loc_18083CE23
0x18083ce0e  mov     ebx, 80020009h
0x18083ce13  jmp     short loc_18083CE23
0x18083ce15  mov     this, [rbp+57h+pb.p]
0x18083ce19  mov     ebx, r13d
0x18083ce1c  mov     [r15], this
0x18083ce1f  mov     [rbp+57h+pb.p], r13
0x18083ce23  mov     this, [rbp+57h+pb.p]; pv
0x18083ce27  call    cs:__imp_CoTaskMemFree
0x18083ce2d  mov     eax, ebx
0x18083ce2f  jmp     short loc_18083CE36
0x18083ce31  mov     eax, 80004003h
0x18083ce36  mov     this, [rbp+57h+var_40]
0x18083ce3a  xor     this, rsp; StackCookie
0x18083ce3d  call    __security_check_cookie
0x18083ce42  mov     rbx, [rsp+0C0h+arg_8]
0x18083ce4a  add     rsp, 90h
0x18083ce51  pop     r15
0x18083ce53  pop     r14
0x18083ce55  pop     r13
0x18083ce57  pop     r12
0x18083ce59  pop     rdi
0x18083ce5a  pop     rsi
0x18083ce5b  pop     rbp
0x18083ce5c  retn
```
