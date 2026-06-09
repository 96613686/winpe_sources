# ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)

- ea: `0x1800586f0`
- end: `0x180058913`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z`
- size: `547`
- prototype: `int(ATL::CRegParser *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005c174`

## callees

- `0x18003e480`
- `0x18004b648`
- `0x1800586f0`
- `0x18005f408`
- `0x18005f458`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800587ae`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180058853`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180058876`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800587ae`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180058853`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180058876`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcpynW` at `0x1800587f9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcpynW` at `0x1800587f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058763`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058763`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058775`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800588ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800588ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058775`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800588ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800588ca`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(ATL::CRegParser *this, WCHAR *a2, LPVOID *a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  LPWSTR v8; // rax
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // rax
  const unsigned __int16 *v11; // rsi
  __int64 v12; // r8
  const unsigned __int16 *v13; // rbx
  int v14; // ebx
  const WCHAR *i; // rax
  unsigned int v16; // ebx
  __int64 v17; // [rsp+20h] [rbp-39h] BYREF
  int v18; // [rsp+28h] [rbp-31h] BYREF
  int v19; // [rsp+2Ch] [rbp-2Dh]
  LPVOID pv; // [rsp+30h] [rbp-29h]
  __int64 v21; // [rsp+38h] [rbp-21h] BYREF
  WCHAR String1[32]; // [rsp+40h] [rbp-19h] BYREF

  v17 = 0;
  v4 = a2;
  if ( !a2 || !a3 )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v17);
    return 2147500035LL;
  }
  *a3 = 0;
  v6 = -1;
  v18 = 0;
  do
    ++v6;
  while ( a2[v6] );
  v19 = 2 * v6 + 2;
  pv = CoTaskMemAlloc(2LL * v19);
  if ( !pv )
  {
    CoTaskMemFree(0);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v17);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v9 = v4;
LABEL_27:
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::AddChar((ATL::CRegParser::CParseBuffer *)&v18, v9) )
        goto LABEL_32;
      goto LABEL_28;
    }
    v8 = CharNextW(v4);
    *(_QWORD *)this = v8;
    if ( *v8 == 37 )
    {
      v9 = v8;
      goto LABEL_27;
    }
    v10 = ATL::CRegParser::StrChrW(v8, 0x25u);
    v11 = v10;
    if ( !v10 )
      goto LABEL_30;
    v12 = ((__int64)v10 - *(_QWORD *)this) >> 1;
    if ( (int)v12 > 31 )
    {
      v16 = -2147467259;
LABEL_33:
      CoTaskMemFree(pv);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v17);
      return v16;
    }
    lstrcpynW(String1, *(LPCWSTR *)this, v12 + 1);
    v13 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), String1);
    if ( !v13 )
    {
LABEL_30:
      v16 = -2147352567;
      goto LABEL_33;
    }
    v21 = 0;
    while ( *v13 )
    {
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::AddChar((ATL::CRegParser::CParseBuffer *)&v18, v13) )
      {
        v14 = 0;
        goto LABEL_21;
      }
      ++v13;
    }
    v14 = 1;
LABEL_21:
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v21);
    if ( !v14 )
      goto LABEL_32;
    for ( i = *(const WCHAR **)this; i != v11; *(_QWORD *)this = i )
      i = CharNextW(i);
LABEL_28:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  if ( !(unsigned int)ATL::CRegParser::CParseBuffer::AddChar((ATL::CRegParser::CParseBuffer *)&v18, v4) )
  {
LABEL_32:
    v16 = -2147024882;
    goto LABEL_33;
  }
  *a3 = pv;
  CoTaskMemFree(0);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v17);
  return 0;
}

```

## disassembly

```asm
0x1800586f0  mov     [rsp-8+arg_8], rbx
0x1800586f5  mov     [rsp-8+arg_18], rsi
0x1800586fa  push    rbp
0x1800586fb  push    rdi
0x1800586fc  push    r12
0x1800586fe  push    r14
0x180058700  push    r15
0x180058702  lea     rbp, [rsp-37h]
0x180058707  sub     rsp, 90h
0x18005870e  mov     rax, cs:__security_cookie
0x180058715  xor     rax, rsp
0x180058718  mov     [rbp+57h+var_30], rax
0x18005871c  xor     r15d, r15d
0x18005871f  mov     r14, r8
0x180058722  mov     [rbp+57h+var_90], r15
0x180058726  mov     rbx, rdx
0x180058729  mov     rdi, rcx
0x18005872c  test    rdx, rdx
0x18005872f  jz      loc_1800588DD
0x180058735  test    r8, r8
0x180058738  jz      loc_1800588DD
0x18005873e  mov     [r8], r15
0x180058741  or      rax, 0FFFFFFFFFFFFFFFFh
0x180058745  mov     [rbp+57h+var_88], r15d
0x180058749  inc     rax
0x18005874c  cmp     [rdx+rax*2], r15w
0x180058751  jnz     short loc_180058749
0x180058753  lea     eax, ds:2[rax*2]
0x18005875a  movsxd  rcx, eax
0x18005875d  add     rcx, rcx; cb
0x180058760  mov     [rbp+57h+var_84], eax
0x180058763  call    cs:__imp_CoTaskMemAlloc
0x180058769  mov     [rbp+57h+pv], rax
0x18005876d  test    rax, rax
0x180058770  jnz     short loc_18005878E
0x180058772  mov     rcx, rax; pv
0x180058775  call    cs:__imp_CoTaskMemFree
0x18005877b  lea     rcx, [rbp+57h+var_90]
0x18005877f  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180058784  mov     eax, 8007000Eh
0x180058789  jmp     loc_1800588EB
0x18005878e  mov     [rdi], rbx
0x180058791  mov     r12d, 25h ; '%'
0x180058797  cmp     [rbx], r15w
0x18005879b  jz      loc_180058895
0x1800587a1  cmp     [rbx], r12w
0x1800587a5  jnz     loc_180058863
0x1800587ab  mov     rcx, rbx; lpsz
0x1800587ae  call    cs:__imp_CharNextW
0x1800587b4  mov     [rdi], rax
0x1800587b7  cmp     [rax], r12w
0x1800587bb  jnz     short loc_1800587C5
0x1800587bd  mov     rdx, rax
0x1800587c0  jmp     loc_180058866
0x1800587c5  mov     edx, r12d; unsigned __int16
0x1800587c8  mov     rcx, rax; lpsz
0x1800587cb  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x1800587d0  mov     rsi, rax
0x1800587d3  test    rax, rax
0x1800587d6  jz      loc_18005888E
0x1800587dc  mov     r8, rax
0x1800587df  sub     r8, [rdi]
0x1800587e2  sar     r8, 1
0x1800587e5  cmp     r8d, 1Fh
0x1800587e9  jg      loc_180058887
0x1800587ef  mov     rdx, [rdi]; lpString2
0x1800587f2  lea     rcx, [rbp+57h+String1]; lpString1
0x1800587f6  inc     r8d; iMaxLength
0x1800587f9  call    cs:__imp_lstrcpynW
0x1800587ff  mov     rcx, [rdi+8]; this
0x180058803  lea     rdx, [rbp+57h+String1]; unsigned __int16 *
0x180058807  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x18005880c  mov     rbx, rax
0x18005880f  test    rax, rax
0x180058812  jz      short loc_18005888E
0x180058814  mov     [rbp+57h+var_78], r15
0x180058818  cmp     [rbx], r15w
0x18005881c  jz      short loc_180058839
0x18005881e  mov     rdx, rbx; unsigned __int16 *
0x180058821  lea     rcx, [rbp+57h+var_88]; this
0x180058825  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x18005882a  test    eax, eax
0x18005882c  jz      short loc_180058834
0x18005882e  add     rbx, 2
0x180058832  jmp     short loc_180058818
0x180058834  mov     ebx, r15d
0x180058837  jmp     short loc_18005883E
0x180058839  mov     ebx, 1
0x18005883e  lea     rcx, [rbp+57h+var_78]
0x180058842  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180058847  test    ebx, ebx
0x180058849  jz      short loc_1800588A5
0x18005884b  mov     rax, [rdi]
0x18005884e  jmp     short loc_18005885C
0x180058850  mov     rcx, rax; lpsz
0x180058853  call    cs:__imp_CharNextW
0x180058859  mov     [rdi], rax
0x18005885c  cmp     rax, rsi
0x18005885f  jnz     short loc_180058850
0x180058861  jmp     short loc_180058873
0x180058863  mov     rdx, rbx; unsigned __int16 *
0x180058866  lea     rcx, [rbp+57h+var_88]; this
0x18005886a  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x18005886f  test    eax, eax
0x180058871  jz      short loc_1800588A5
0x180058873  mov     rcx, [rdi]; lpsz
0x180058876  call    cs:__imp_CharNextW
0x18005887c  mov     rbx, rax
0x18005887f  mov     [rdi], rax
0x180058882  jmp     loc_180058797
0x180058887  mov     ebx, 80004005h
0x18005888c  jmp     short loc_1800588AA
0x18005888e  mov     ebx, 80020009h
0x180058893  jmp     short loc_1800588AA
0x180058895  mov     rdx, rbx; unsigned __int16 *
0x180058898  lea     rcx, [rbp+57h+var_88]; this
0x18005889c  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x1800588a1  test    eax, eax
0x1800588a3  jnz     short loc_1800588C1
0x1800588a5  mov     ebx, 8007000Eh
0x1800588aa  mov     rcx, [rbp+57h+pv]; pv
0x1800588ae  call    cs:__imp_CoTaskMemFree
0x1800588b4  lea     rcx, [rbp+57h+var_90]
0x1800588b8  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800588bd  mov     eax, ebx
0x1800588bf  jmp     short loc_1800588EB
0x1800588c1  mov     rax, [rbp+57h+pv]
0x1800588c5  xor     ecx, ecx; pv
0x1800588c7  mov     [r14], rax
0x1800588ca  call    cs:__imp_CoTaskMemFree
0x1800588d0  lea     rcx, [rbp+57h+var_90]
0x1800588d4  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800588d9  xor     eax, eax
0x1800588db  jmp     short loc_1800588EB
0x1800588dd  lea     rcx, [rbp+57h+var_90]
0x1800588e1  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800588e6  mov     eax, 80004003h
0x1800588eb  mov     rcx, [rbp+57h+var_30]
0x1800588ef  xor     rcx, rsp; StackCookie
0x1800588f2  call    __security_check_cookie
0x1800588f7  lea     r11, [rsp+0B0h+var_20]
0x1800588ff  mov     rbx, [r11+38h]
0x180058903  mov     rsi, [r11+48h]
0x180058907  mov     rsp, r11
0x18005890a  pop     r15
0x18005890c  pop     r14
0x18005890e  pop     r12
0x180058910  pop     rdi
0x180058911  pop     rbp
0x180058912  retn
```
