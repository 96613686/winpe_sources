# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18002cc54`
- end: `0x18002cebf`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `619`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d03c`

## callees

- `0x1800277b0`
- `0x18002a140`
- `0x18002ae60`
- `0x18002b160`
- `0x18002c43c`
- `0x18002cc54`
- `0x18002dc34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002cd95`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002cd95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cdad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cdad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cdf6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cdf6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002cd2b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002ce3a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002ce50`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002cd2b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002ce3a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002ce50`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002cdce`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002cdce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ccfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ce89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ccfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ce89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002cce2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002cce2`

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
  LPVOID pv[2]; // [rsp+20h] [rbp-49h] BYREF
  __int64 v28; // [rsp+30h] [rbp-39h] BYREF
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
  *(_OWORD *)pv = 0;
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(pv[0]) = 0;
  HIDWORD(pv[0]) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv[1] = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv[1] = 0;
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
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v12, 1) )
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
    v17 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v16, pv[0]);
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
    v28 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v28);
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
  v26 = (unsigned __int16 *)pv[1];
  pv[1] = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv[1]);
  return v13;
}

```

## disassembly

```asm
0x18002cc54  mov     [rsp-8+arg_8], rbx
0x18002cc59  push    rbp
0x18002cc5a  push    rsi
0x18002cc5b  push    rdi
0x18002cc5c  push    r12
0x18002cc5e  push    r13
0x18002cc60  push    r14
0x18002cc62  push    r15
0x18002cc64  lea     rbp, [rsp-27h]
0x18002cc69  sub     rsp, 90h
0x18002cc70  mov     rax, cs:__security_cookie
0x18002cc77  xor     rax, rsp
0x18002cc7a  mov     [rbp+57h+var_40], rax
0x18002cc7e  mov     r15, r8
0x18002cc81  mov     rbx, rdx
0x18002cc84  mov     rdi, rcx
0x18002cc87  xor     r13d, r13d
0x18002cc8a  test    rdx, rdx
0x18002cc8d  jz      loc_18002CE93
0x18002cc93  test    r8, r8
0x18002cc96  jz      loc_18002CE93
0x18002cc9c  mov     [r8], r13
0x18002cc9f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002cca3  inc     rax
0x18002cca6  cmp     [rdx+rax*2], r13w
0x18002ccab  jnz     short loc_18002CCA3
0x18002ccad  add     eax, eax
0x18002ccaf  xorps   xmm0, xmm0
0x18002ccb2  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18002ccb6  mov     ecx, 3E8h
0x18002ccbb  cmp     eax, 64h ; 'd'
0x18002ccbe  cmovl   eax, ecx
0x18002ccc1  mov     dword ptr [rbp+57h+pv], r13d
0x18002ccc5  mov     dword ptr [rbp+57h+pv+4], eax
0x18002ccc8  mov     ecx, eax
0x18002ccca  add     rcx, rcx
0x18002cccd  mov     eax, 0FFFFFFFFh
0x18002ccd2  cmp     rcx, rax
0x18002ccd5  jbe     short loc_18002CCE0
0x18002ccd7  mov     rax, r13
0x18002ccda  mov     [rbp+57h+pv+8], r13
0x18002ccde  jmp     short loc_18002CCF5
0x18002cce0  mov     ecx, ecx; cb
0x18002cce2  call    cs:__imp_CoTaskMemAlloc
0x18002cce8  mov     [rbp+57h+pv+8], rax
0x18002ccec  test    rax, rax
0x18002ccef  jz      short loc_18002CCF5
0x18002ccf1  mov     [rax], r13w
0x18002ccf5  test    rax, rax
0x18002ccf8  jnz     short loc_18002CD0D
0x18002ccfa  mov     rcx, rax; pv
0x18002ccfd  call    cs:__imp_CoTaskMemFree
0x18002cd03  mov     eax, 8007000Eh
0x18002cd08  jmp     loc_18002CE98
0x18002cd0d  mov     [rdi], rbx
0x18002cd10  mov     esi, 25h ; '%'
0x18002cd15  cmp     [rbx], r13w
0x18002cd19  jz      loc_18002CE77
0x18002cd1f  cmp     [rbx], si
0x18002cd22  jnz     loc_18002CE61
0x18002cd28  mov     rcx, rbx; lpsz
0x18002cd2b  call    cs:__imp_CharNextW
0x18002cd31  mov     [rdi], rax
0x18002cd34  cmp     [rax], si
0x18002cd37  jnz     short loc_18002CD5D
0x18002cd39  mov     rdx, rax; unsigned __int16 *
0x18002cd3c  mov     r8d, 1; int
0x18002cd42  lea     rcx, [rbp+57h+pv]; this
0x18002cd46  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18002cd4b  test    eax, eax
0x18002cd4d  jnz     loc_18002CE4D
0x18002cd53  mov     ebx, 8007000Eh
0x18002cd58  jmp     loc_18002CE85
0x18002cd5d  mov     edx, esi; unsigned __int16
0x18002cd5f  mov     rcx, rax; lpsz
0x18002cd62  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18002cd67  mov     rsi, rax
0x18002cd6a  test    rax, rax
0x18002cd6d  jz      loc_18002CE70
0x18002cd73  mov     rcx, rax
0x18002cd76  sub     rcx, [rdi]
0x18002cd79  sar     rcx, 1
0x18002cd7c  cmp     rcx, 1Fh
0x18002cd80  jg      loc_18002CE69
0x18002cd86  movsxd  r9, ecx
0x18002cd89  mov     r8, [rdi]
0x18002cd8c  mov     edx, 20h ; ' '
0x18002cd91  lea     rcx, [rbp+57h+String2]
0x18002cd95  call    cs:__imp__o_wcsncpy_s
0x18002cd9b  mov     ecx, eax; int
0x18002cd9d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002cda2  mov     rbx, [rdi+8]
0x18002cda6  lea     r12, [rbx+20h]
0x18002cdaa  mov     rcx, r12; lpCriticalSection
0x18002cdad  call    cs:__imp_EnterCriticalSection
0x18002cdb3  lea     r14, [rbx+8]
0x18002cdb7  mov     ebx, r13d
0x18002cdba  cmp     ebx, [r14+10h]
0x18002cdbe  jge     short loc_18002CDF0
0x18002cdc0  movsxd  rax, ebx
0x18002cdc3  mov     rcx, [r14]
0x18002cdc6  lea     rdx, [rbp+57h+String2]; lpString2
0x18002cdca  mov     rcx, [rcx+rax*8]; lpString1
0x18002cdce  call    cs:__imp_lstrcmpiW
0x18002cdd4  test    eax, eax
0x18002cdd6  jz      short loc_18002CDDC
0x18002cdd8  inc     ebx
0x18002cdda  jmp     short loc_18002CDBA
0x18002cddc  cmp     ebx, 0FFFFFFFFh
0x18002cddf  jz      short loc_18002CDF0
0x18002cde1  mov     edx, ebx
0x18002cde3  mov     rcx, r14
0x18002cde6  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18002cdeb  mov     rbx, [rax]
0x18002cdee  jmp     short loc_18002CDF3
0x18002cdf0  mov     rbx, r13
0x18002cdf3  mov     rcx, r12; lpCriticalSection
0x18002cdf6  call    cs:__imp_LeaveCriticalSection
0x18002cdfc  test    rbx, rbx
0x18002cdff  jz      short loc_18002CE70
0x18002ce01  mov     [rbp+57h+var_90], r13
0x18002ce05  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002ce09  inc     r8; int
0x18002ce0c  cmp     [rbx+r8*2], r13w
0x18002ce11  jnz     short loc_18002CE09
0x18002ce13  mov     rdx, rbx; unsigned __int16 *
0x18002ce16  lea     rcx, [rbp+57h+pv]; this
0x18002ce1a  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18002ce1f  mov     ebx, eax
0x18002ce21  lea     rcx, [rbp+57h+var_90]
0x18002ce25  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002ce2a  test    ebx, ebx
0x18002ce2c  jz      loc_18002CD53
0x18002ce32  mov     rax, [rdi]
0x18002ce35  jmp     short loc_18002CE43
0x18002ce37  mov     rcx, rax; lpsz
0x18002ce3a  call    cs:__imp_CharNextW
0x18002ce40  mov     [rdi], rax
0x18002ce43  cmp     rax, rsi
0x18002ce46  jnz     short loc_18002CE37
0x18002ce48  mov     esi, 25h ; '%'
0x18002ce4d  mov     rcx, [rdi]; lpsz
0x18002ce50  call    cs:__imp_CharNextW
0x18002ce56  mov     rbx, rax
0x18002ce59  mov     [rdi], rax
0x18002ce5c  jmp     loc_18002CD15
0x18002ce61  mov     rdx, rbx
0x18002ce64  jmp     loc_18002CD3C
0x18002ce69  mov     ebx, 80004005h
0x18002ce6e  jmp     short loc_18002CE85
0x18002ce70  mov     ebx, 80020009h
0x18002ce75  jmp     short loc_18002CE85
0x18002ce77  mov     ebx, r13d
0x18002ce7a  mov     rcx, [rbp+57h+pv+8]
0x18002ce7e  mov     [rbp+57h+pv+8], r13
0x18002ce82  mov     [r15], rcx
0x18002ce85  mov     rcx, [rbp+57h+pv+8]; pv
0x18002ce89  call    cs:__imp_CoTaskMemFree
0x18002ce8f  mov     eax, ebx
0x18002ce91  jmp     short loc_18002CE98
0x18002ce93  mov     eax, 80004003h
0x18002ce98  mov     rcx, [rbp+57h+var_40]
0x18002ce9c  xor     rcx, rsp; StackCookie
0x18002ce9f  call    __security_check_cookie
0x18002cea4  mov     rbx, [rsp+0C0h+arg_8]
0x18002ceac  add     rsp, 90h
0x18002ceb3  pop     r15
0x18002ceb5  pop     r14
0x18002ceb7  pop     r13
0x18002ceb9  pop     r12
0x18002cebb  pop     rdi
0x18002cebc  pop     rsi
0x18002cebd  pop     rbp
0x18002cebe  retn
```
