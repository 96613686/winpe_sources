# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180092ae8`
- end: `0x180092d4c`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180092f6c`

## callees

- `0x18005d14c`
- `0x180061320`
- `0x18006afd4`
- `0x180091854`
- `0x180092390`
- `0x180092ae8`
- `0x180093bf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180092c22`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180092c22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092c83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092c83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180092c3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180092c3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092b8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092d16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092b8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092d16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180092b6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180092b6f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180092bb8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180092cc7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180092cdd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180092bb8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180092cc7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180092cdd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180092c5b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180092c5b`

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
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x180092ae8  mov     [rsp-8+arg_8], rbx
0x180092aed  push    rbp
0x180092aee  push    rsi
0x180092aef  push    rdi
0x180092af0  push    r12
0x180092af2  push    r13
0x180092af4  push    r14
0x180092af6  push    r15
0x180092af8  lea     rbp, [rsp-27h]
0x180092afd  sub     rsp, 90h
0x180092b04  mov     rax, cs:__security_cookie
0x180092b0b  xor     rax, rsp
0x180092b0e  mov     [rbp+57h+var_40], rax
0x180092b12  mov     r15, r8
0x180092b15  mov     rbx, rdx
0x180092b18  mov     rdi, rcx
0x180092b1b  xor     r13d, r13d
0x180092b1e  test    rdx, rdx
0x180092b21  jz      loc_180092D20
0x180092b27  test    r8, r8
0x180092b2a  jz      loc_180092D20
0x180092b30  mov     [r8], r13
0x180092b33  or      rax, 0FFFFFFFFFFFFFFFFh
0x180092b37  inc     rax
0x180092b3a  cmp     [rdx+rax*2], r13w
0x180092b3f  jnz     short loc_180092B37
0x180092b41  add     eax, eax
0x180092b43  mov     ecx, 3E8h
0x180092b48  cmp     eax, 64h ; 'd'
0x180092b4b  cmovl   eax, ecx
0x180092b4e  mov     [rbp+57h+var_A0], r13d
0x180092b52  mov     [rbp+57h+var_9C], eax
0x180092b55  mov     ecx, eax
0x180092b57  add     rcx, rcx
0x180092b5a  mov     eax, 0FFFFFFFFh
0x180092b5f  cmp     rcx, rax
0x180092b62  jbe     short loc_180092B6D
0x180092b64  mov     rax, r13
0x180092b67  mov     [rbp+57h+pv], r13
0x180092b6b  jmp     short loc_180092B82
0x180092b6d  mov     ecx, ecx; cb
0x180092b6f  call    cs:__imp_CoTaskMemAlloc
0x180092b75  mov     [rbp+57h+pv], rax
0x180092b79  test    rax, rax
0x180092b7c  jz      short loc_180092B82
0x180092b7e  mov     [rax], r13w
0x180092b82  test    rax, rax
0x180092b85  jnz     short loc_180092B9A
0x180092b87  mov     rcx, rax; pv
0x180092b8a  call    cs:__imp_CoTaskMemFree
0x180092b90  mov     eax, 8007000Eh
0x180092b95  jmp     loc_180092D25
0x180092b9a  mov     [rdi], rbx
0x180092b9d  mov     esi, 25h ; '%'
0x180092ba2  cmp     [rbx], r13w
0x180092ba6  jz      loc_180092D04
0x180092bac  cmp     [rbx], si
0x180092baf  jnz     loc_180092CEE
0x180092bb5  mov     rcx, rbx; lpsz
0x180092bb8  call    cs:__imp_CharNextW
0x180092bbe  mov     [rdi], rax
0x180092bc1  cmp     [rax], si
0x180092bc4  jnz     short loc_180092BEA
0x180092bc6  mov     rdx, rax; unsigned __int16 *
0x180092bc9  mov     r8d, 1; int
0x180092bcf  lea     rcx, [rbp+57h+var_A0]; this
0x180092bd3  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180092bd8  test    eax, eax
0x180092bda  jnz     loc_180092CDA
0x180092be0  mov     ebx, 8007000Eh
0x180092be5  jmp     loc_180092D12
0x180092bea  mov     edx, esi; unsigned __int16
0x180092bec  mov     rcx, rax; lpsz
0x180092bef  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180092bf4  mov     rsi, rax
0x180092bf7  test    rax, rax
0x180092bfa  jz      loc_180092CFD
0x180092c00  mov     rcx, rax
0x180092c03  sub     rcx, [rdi]
0x180092c06  sar     rcx, 1
0x180092c09  cmp     rcx, 1Fh
0x180092c0d  jg      loc_180092CF6
0x180092c13  movsxd  r9, ecx
0x180092c16  mov     r8, [rdi]
0x180092c19  mov     edx, 20h ; ' '
0x180092c1e  lea     rcx, [rbp+57h+String2]
0x180092c22  call    cs:__imp__o_wcsncpy_s
0x180092c28  mov     ecx, eax; int
0x180092c2a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180092c2f  mov     rbx, [rdi+8]
0x180092c33  lea     r12, [rbx+20h]
0x180092c37  mov     rcx, r12; lpCriticalSection
0x180092c3a  call    cs:__imp_EnterCriticalSection
0x180092c40  lea     r14, [rbx+8]
0x180092c44  mov     ebx, r13d
0x180092c47  cmp     ebx, [r14+10h]
0x180092c4b  jge     short loc_180092C7D
0x180092c4d  movsxd  rax, ebx
0x180092c50  mov     rcx, [r14]
0x180092c53  lea     rdx, [rbp+57h+String2]; lpString2
0x180092c57  mov     rcx, [rcx+rax*8]; lpString1
0x180092c5b  call    cs:__imp_lstrcmpiW
0x180092c61  test    eax, eax
0x180092c63  jz      short loc_180092C69
0x180092c65  inc     ebx
0x180092c67  jmp     short loc_180092C47
0x180092c69  cmp     ebx, 0FFFFFFFFh
0x180092c6c  jz      short loc_180092C7D
0x180092c6e  mov     edx, ebx
0x180092c70  mov     rcx, r14
0x180092c73  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180092c78  mov     rbx, [rax]
0x180092c7b  jmp     short loc_180092C80
0x180092c7d  mov     rbx, r13
0x180092c80  mov     rcx, r12; lpCriticalSection
0x180092c83  call    cs:__imp_LeaveCriticalSection
0x180092c89  test    rbx, rbx
0x180092c8c  jz      short loc_180092CFD
0x180092c8e  mov     [rbp+57h+var_90], r13
0x180092c92  or      r8, 0FFFFFFFFFFFFFFFFh
0x180092c96  inc     r8; int
0x180092c99  cmp     [rbx+r8*2], r13w
0x180092c9e  jnz     short loc_180092C96
0x180092ca0  mov     rdx, rbx; unsigned __int16 *
0x180092ca3  lea     rcx, [rbp+57h+var_A0]; this
0x180092ca7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180092cac  mov     ebx, eax
0x180092cae  lea     rcx, [rbp+57h+var_90]
0x180092cb2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180092cb7  test    ebx, ebx
0x180092cb9  jz      loc_180092BE0
0x180092cbf  mov     rax, [rdi]
0x180092cc2  jmp     short loc_180092CD0
0x180092cc4  mov     rcx, rax; lpsz
0x180092cc7  call    cs:__imp_CharNextW
0x180092ccd  mov     [rdi], rax
0x180092cd0  cmp     rax, rsi
0x180092cd3  jnz     short loc_180092CC4
0x180092cd5  mov     esi, 25h ; '%'
0x180092cda  mov     rcx, [rdi]; lpsz
0x180092cdd  call    cs:__imp_CharNextW
0x180092ce3  mov     rbx, rax
0x180092ce6  mov     [rdi], rax
0x180092ce9  jmp     loc_180092BA2
0x180092cee  mov     rdx, rbx
0x180092cf1  jmp     loc_180092BC9
0x180092cf6  mov     ebx, 80004005h
0x180092cfb  jmp     short loc_180092D12
0x180092cfd  mov     ebx, 80020009h
0x180092d02  jmp     short loc_180092D12
0x180092d04  mov     ebx, r13d
0x180092d07  mov     rcx, [rbp+57h+pv]
0x180092d0b  mov     [rbp+57h+pv], r13
0x180092d0f  mov     [r15], rcx
0x180092d12  mov     rcx, [rbp+57h+pv]; pv
0x180092d16  call    cs:__imp_CoTaskMemFree
0x180092d1c  mov     eax, ebx
0x180092d1e  jmp     short loc_180092D25
0x180092d20  mov     eax, 80004003h
0x180092d25  mov     rcx, [rbp+57h+var_40]
0x180092d29  xor     rcx, rsp; StackCookie
0x180092d2c  call    __security_check_cookie
0x180092d31  mov     rbx, [rsp+0C0h+arg_8]
0x180092d39  add     rsp, 90h
0x180092d40  pop     r15
0x180092d42  pop     r14
0x180092d44  pop     r13
0x180092d46  pop     r12
0x180092d48  pop     rdi
0x180092d49  pop     rsi
0x180092d4a  pop     rbp
0x180092d4b  retn
```
