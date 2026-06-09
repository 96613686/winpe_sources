# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800433c0`
- end: `0x180043624`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180043a30`

## callees

- `0x1800046f8`
- `0x180038944`
- `0x18003f800`
- `0x180041fd4`
- `0x18004316c`
- `0x1800433c0`
- `0x1800448bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800434fa`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800434fa`
- `KERNEL32!lstrcmpiW` at `0x180043533`
- `KERNEL32!lstrcmpiW` at `0x180043533`
- `KERNEL32!LeaveCriticalSection` at `0x18004355b`
- `KERNEL32!LeaveCriticalSection` at `0x18004355b`
- `KERNEL32!EnterCriticalSection` at `0x180043512`
- `KERNEL32!EnterCriticalSection` at `0x180043512`
- `USER32!CharNextW` at `0x180043490`
- `USER32!CharNextW` at `0x18004359f`
- `USER32!CharNextW` at `0x1800435b5`
- `USER32!CharNextW` at `0x180043490`
- `USER32!CharNextW` at `0x18004359f`
- `USER32!CharNextW` at `0x1800435b5`
- `ole32!CoTaskMemFree` at `0x180043462`
- `ole32!CoTaskMemFree` at `0x1800435ee`
- `ole32!CoTaskMemFree` at `0x180043462`
- `ole32!CoTaskMemFree` at `0x1800435ee`
- `ole32!CoTaskMemAlloc` at `0x180043447`
- `ole32!CoTaskMemAlloc` at `0x180043447`

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
0x1800433c0  mov     [rsp-8+arg_8], rbx
0x1800433c5  push    rbp
0x1800433c6  push    rsi
0x1800433c7  push    rdi
0x1800433c8  push    r12
0x1800433ca  push    r13
0x1800433cc  push    r14
0x1800433ce  push    r15
0x1800433d0  lea     rbp, [rsp-27h]
0x1800433d5  sub     rsp, 90h
0x1800433dc  mov     rax, cs:__security_cookie
0x1800433e3  xor     rax, rsp
0x1800433e6  mov     [rbp+57h+var_40], rax
0x1800433ea  mov     r15, r8
0x1800433ed  mov     rbx, rdx
0x1800433f0  mov     rdi, rcx
0x1800433f3  xor     r13d, r13d
0x1800433f6  test    rdx, rdx
0x1800433f9  jz      loc_1800435F8
0x1800433ff  test    r8, r8
0x180043402  jz      loc_1800435F8
0x180043408  mov     [r8], r13
0x18004340b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004340f  inc     rax
0x180043412  cmp     [rdx+rax*2], r13w
0x180043417  jnz     short loc_18004340F
0x180043419  add     eax, eax
0x18004341b  mov     ecx, 3E8h
0x180043420  cmp     eax, 64h ; 'd'
0x180043423  cmovl   eax, ecx
0x180043426  mov     [rbp+57h+var_A0], r13d
0x18004342a  mov     [rbp+57h+var_9C], eax
0x18004342d  mov     ecx, eax
0x18004342f  add     rcx, rcx
0x180043432  mov     eax, 0FFFFFFFFh
0x180043437  cmp     rcx, rax
0x18004343a  jbe     short loc_180043445
0x18004343c  mov     rax, r13
0x18004343f  mov     [rbp+57h+pv], r13
0x180043443  jmp     short loc_18004345A
0x180043445  mov     ecx, ecx; cb
0x180043447  call    cs:__imp_CoTaskMemAlloc
0x18004344d  mov     [rbp+57h+pv], rax
0x180043451  test    rax, rax
0x180043454  jz      short loc_18004345A
0x180043456  mov     [rax], r13w
0x18004345a  test    rax, rax
0x18004345d  jnz     short loc_180043472
0x18004345f  mov     rcx, rax; pv
0x180043462  call    cs:__imp_CoTaskMemFree
0x180043468  mov     eax, 8007000Eh
0x18004346d  jmp     loc_1800435FD
0x180043472  mov     [rdi], rbx
0x180043475  mov     esi, 25h ; '%'
0x18004347a  cmp     [rbx], r13w
0x18004347e  jz      loc_1800435DC
0x180043484  cmp     [rbx], si
0x180043487  jnz     loc_1800435C6
0x18004348d  mov     rcx, rbx; lpsz
0x180043490  call    cs:__imp_CharNextW
0x180043496  mov     [rdi], rax
0x180043499  cmp     [rax], si
0x18004349c  jnz     short loc_1800434C2
0x18004349e  mov     rdx, rax; unsigned __int16 *
0x1800434a1  mov     r8d, 1; int
0x1800434a7  lea     rcx, [rbp+57h+var_A0]; this
0x1800434ab  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800434b0  test    eax, eax
0x1800434b2  jnz     loc_1800435B2
0x1800434b8  mov     ebx, 8007000Eh
0x1800434bd  jmp     loc_1800435EA
0x1800434c2  mov     edx, esi; unsigned __int16
0x1800434c4  mov     rcx, rax; lpsz
0x1800434c7  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800434cc  mov     rsi, rax
0x1800434cf  test    rax, rax
0x1800434d2  jz      loc_1800435D5
0x1800434d8  mov     rcx, rax
0x1800434db  sub     rcx, [rdi]
0x1800434de  sar     rcx, 1
0x1800434e1  cmp     rcx, 1Fh
0x1800434e5  jg      loc_1800435CE
0x1800434eb  movsxd  r9, ecx
0x1800434ee  mov     r8, [rdi]
0x1800434f1  mov     edx, 20h ; ' '
0x1800434f6  lea     rcx, [rbp+57h+String2]
0x1800434fa  call    cs:__imp__o_wcsncpy_s
0x180043500  mov     ecx, eax; int
0x180043502  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180043507  mov     rbx, [rdi+8]
0x18004350b  lea     r12, [rbx+20h]
0x18004350f  mov     rcx, r12; lpCriticalSection
0x180043512  call    cs:__imp_EnterCriticalSection
0x180043518  lea     r14, [rbx+8]
0x18004351c  mov     ebx, r13d
0x18004351f  cmp     ebx, [r14+10h]
0x180043523  jge     short loc_180043555
0x180043525  movsxd  rax, ebx
0x180043528  mov     rcx, [r14]
0x18004352b  lea     rdx, [rbp+57h+String2]; lpString2
0x18004352f  mov     rcx, [rcx+rax*8]; lpString1
0x180043533  call    cs:__imp_lstrcmpiW
0x180043539  test    eax, eax
0x18004353b  jz      short loc_180043541
0x18004353d  inc     ebx
0x18004353f  jmp     short loc_18004351F
0x180043541  cmp     ebx, 0FFFFFFFFh
0x180043544  jz      short loc_180043555
0x180043546  mov     edx, ebx
0x180043548  mov     rcx, r14
0x18004354b  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180043550  mov     rbx, [rax]
0x180043553  jmp     short loc_180043558
0x180043555  mov     rbx, r13
0x180043558  mov     rcx, r12; lpCriticalSection
0x18004355b  call    cs:__imp_LeaveCriticalSection
0x180043561  test    rbx, rbx
0x180043564  jz      short loc_1800435D5
0x180043566  mov     [rbp+57h+var_90], r13
0x18004356a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004356e  inc     r8; int
0x180043571  cmp     [rbx+r8*2], r13w
0x180043576  jnz     short loc_18004356E
0x180043578  mov     rdx, rbx; unsigned __int16 *
0x18004357b  lea     rcx, [rbp+57h+var_A0]; this
0x18004357f  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180043584  mov     ebx, eax
0x180043586  lea     rcx, [rbp+57h+var_90]
0x18004358a  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18004358f  test    ebx, ebx
0x180043591  jz      loc_1800434B8
0x180043597  mov     rax, [rdi]
0x18004359a  jmp     short loc_1800435A8
0x18004359c  mov     rcx, rax; lpsz
0x18004359f  call    cs:__imp_CharNextW
0x1800435a5  mov     [rdi], rax
0x1800435a8  cmp     rax, rsi
0x1800435ab  jnz     short loc_18004359C
0x1800435ad  mov     esi, 25h ; '%'
0x1800435b2  mov     rcx, [rdi]; lpsz
0x1800435b5  call    cs:__imp_CharNextW
0x1800435bb  mov     rbx, rax
0x1800435be  mov     [rdi], rax
0x1800435c1  jmp     loc_18004347A
0x1800435c6  mov     rdx, rbx
0x1800435c9  jmp     loc_1800434A1
0x1800435ce  mov     ebx, 80004005h
0x1800435d3  jmp     short loc_1800435EA
0x1800435d5  mov     ebx, 80020009h
0x1800435da  jmp     short loc_1800435EA
0x1800435dc  mov     ebx, r13d
0x1800435df  mov     rcx, [rbp+57h+pv]
0x1800435e3  mov     [rbp+57h+pv], r13
0x1800435e7  mov     [r15], rcx
0x1800435ea  mov     rcx, [rbp+57h+pv]; pv
0x1800435ee  call    cs:__imp_CoTaskMemFree
0x1800435f4  mov     eax, ebx
0x1800435f6  jmp     short loc_1800435FD
0x1800435f8  mov     eax, 80004003h
0x1800435fd  mov     rcx, [rbp+57h+var_40]
0x180043601  xor     rcx, rsp; StackCookie
0x180043604  call    __security_check_cookie
0x180043609  mov     rbx, [rsp+0C0h+arg_8]
0x180043611  add     rsp, 90h
0x180043618  pop     r15
0x18004361a  pop     r14
0x18004361c  pop     r13
0x18004361e  pop     r12
0x180043620  pop     rdi
0x180043621  pop     rsi
0x180043622  pop     rbp
0x180043623  retn
```
