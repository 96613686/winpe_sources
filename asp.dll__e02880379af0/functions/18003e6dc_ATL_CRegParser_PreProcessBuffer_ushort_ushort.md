# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18003e6dc`
- end: `0x18003e8ee`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `530`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18003ecec`

## callees

- `0x180023dd0`
- `0x180030bd0`
- `0x18003d62c`
- `0x18003d770`
- `0x18003e6dc`
- `0x18003fc90`
- `0x18003fce8`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18003e7f7`
- `msvcrt!wcsncpy_s` at `0x18003e7f7`
- `USER32!CharNextW` at `0x18003e7a7`
- `USER32!CharNextW` at `0x18003e84f`
- `USER32!CharNextW` at `0x18003e878`
- `USER32!CharNextW` at `0x18003e7a7`
- `USER32!CharNextW` at `0x18003e84f`
- `USER32!CharNextW` at `0x18003e878`
- `ole32!CoTaskMemAlloc` at `0x18003e76f`
- `ole32!CoTaskMemAlloc` at `0x18003e76f`
- `ole32!CoTaskMemFree` at `0x18003e75d`
- `ole32!CoTaskMemFree` at `0x18003e8a2`
- `ole32!CoTaskMemFree` at `0x18003e75d`
- `ole32!CoTaskMemFree` at `0x18003e8a2`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  void *v9; // rcx
  _WORD *v11; // rax
  WCHAR v12; // ax
  LPWSTR v13; // rax
  const unsigned __int16 *v14; // rdx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rsi
  __int64 v17; // rcx
  errno_t v18; // eax
  const unsigned __int16 *v19; // rax
  __int64 v20; // r8
  int v21; // ebx
  const WCHAR *i; // rax
  unsigned int v23; // ebx
  _DWORD v24[2]; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v26; // [rsp+30h] [rbp-29h] BYREF
  wchar_t Destination[32]; // [rsp+40h] [rbp-19h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  v24[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v24[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v11 = CoTaskMemAlloc((unsigned int)v8);
  pv = v11;
  v9 = v11;
  if ( !v11 )
    goto LABEL_9;
  *v11 = 0;
  *(_QWORD *)this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_29:
    v23 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_30;
  }
  while ( v12 != 37 )
  {
    v14 = v4;
LABEL_26:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v14, 1) )
      goto LABEL_33;
LABEL_27:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_29;
    }
  }
  v13 = CharNextW(v4);
  *(_QWORD *)this = v13;
  if ( *v13 == 37 )
  {
    v14 = v13;
    goto LABEL_26;
  }
  v15 = ATL::CRegParser::StrChrW(v13, 0x25u);
  v16 = v15;
  if ( !v15 )
    goto LABEL_32;
  v17 = ((__int64)v15 - *(_QWORD *)this) >> 1;
  if ( v17 > 31 )
  {
    v23 = -2147467259;
    goto LABEL_30;
  }
  v18 = wcsncpy_s(Destination, 0x20u, *(const wchar_t **)this, (int)v17);
  ATL::AtlCrtErrorCheck(v18);
  v19 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), Destination);
  if ( !v19 )
  {
LABEL_32:
    v23 = -2147352567;
    goto LABEL_30;
  }
  v26 = 0;
  v20 = -1;
  do
    ++v20;
  while ( v19[v20] );
  v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v19, v20);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v26);
  if ( v21 )
  {
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
    goto LABEL_27;
  }
LABEL_33:
  v23 = -2147024882;
LABEL_30:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x18003e6dc  mov     [rsp-8+arg_8], rbx
0x18003e6e1  mov     [rsp-8+arg_18], rsi
0x18003e6e6  push    rbp
0x18003e6e7  push    rdi
0x18003e6e8  push    r12
0x18003e6ea  push    r14
0x18003e6ec  push    r15
0x18003e6ee  lea     rbp, [rsp-37h]
0x18003e6f3  sub     rsp, 90h
0x18003e6fa  mov     rax, cs:__security_cookie
0x18003e701  xor     rax, rsp
0x18003e704  mov     [rbp+57h+var_30], rax
0x18003e708  xor     r15d, r15d
0x18003e70b  mov     r14, r8
0x18003e70e  mov     rbx, rdx
0x18003e711  mov     rdi, rcx
0x18003e714  test    rdx, rdx
0x18003e717  jz      loc_18003E8C1
0x18003e71d  test    r8, r8
0x18003e720  jz      loc_18003E8C1
0x18003e726  mov     [r8], r15
0x18003e729  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003e72d  inc     rax
0x18003e730  cmp     [rdx+rax*2], r15w
0x18003e735  jnz     short loc_18003E72D
0x18003e737  add     eax, eax
0x18003e739  mov     [rbp+57h+var_90], r15d
0x18003e73d  cmp     eax, 64h ; 'd'
0x18003e740  mov     ecx, 3E8h
0x18003e745  cmovl   eax, ecx
0x18003e748  mov     ecx, eax
0x18003e74a  mov     [rbp+57h+var_8C], eax
0x18003e74d  add     rcx, rcx
0x18003e750  mov     eax, 0FFFFFFFFh
0x18003e755  cmp     rcx, rax
0x18003e758  jbe     short loc_18003E76D
0x18003e75a  mov     rcx, r15; pv
0x18003e75d  call    cs:__imp_CoTaskMemFree
0x18003e763  mov     eax, 8007000Eh
0x18003e768  jmp     loc_18003E8C6
0x18003e76d  mov     ecx, ecx; cb
0x18003e76f  call    cs:__imp_CoTaskMemAlloc
0x18003e775  mov     [rbp+57h+pv], rax
0x18003e779  mov     rcx, rax
0x18003e77c  test    rax, rax
0x18003e77f  jz      short loc_18003E75D
0x18003e781  mov     [rax], r15w
0x18003e785  mov     [rdi], rbx
0x18003e788  movzx   eax, word ptr [rbx]
0x18003e78b  test    ax, ax
0x18003e78e  jz      loc_18003E894
0x18003e794  mov     r12d, 25h ; '%'
0x18003e79a  cmp     ax, r12w
0x18003e79e  jnz     loc_18003E85F
0x18003e7a4  mov     rcx, rbx; lpsz
0x18003e7a7  call    cs:__imp_CharNextW
0x18003e7ad  mov     [rdi], rax
0x18003e7b0  cmp     [rax], r12w
0x18003e7b4  jnz     short loc_18003E7BE
0x18003e7b6  mov     rdx, rax
0x18003e7b9  jmp     loc_18003E862
0x18003e7be  mov     edx, r12d; unsigned __int16
0x18003e7c1  mov     rcx, rax; lpsz
0x18003e7c4  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18003e7c9  mov     rsi, rax
0x18003e7cc  test    rax, rax
0x18003e7cf  jz      loc_18003E8B3
0x18003e7d5  mov     rcx, rax
0x18003e7d8  sub     rcx, [rdi]
0x18003e7db  sar     rcx, 1
0x18003e7de  cmp     rcx, 1Fh
0x18003e7e2  jg      loc_18003E8AC
0x18003e7e8  mov     r8, [rdi]; Source
0x18003e7eb  mov     edx, 20h ; ' '; SizeInWords
0x18003e7f0  movsxd  r9, ecx; MaxCount
0x18003e7f3  lea     rcx, [rbp+57h+Destination]; Destination
0x18003e7f7  call    cs:__imp_wcsncpy_s
0x18003e7fd  mov     ecx, eax; int
0x18003e7ff  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003e804  mov     rcx, [rdi+8]; this
0x18003e808  lea     rdx, [rbp+57h+Destination]; unsigned __int16 *
0x18003e80c  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x18003e811  test    rax, rax
0x18003e814  jz      loc_18003E8B3
0x18003e81a  mov     [rbp+57h+var_80], r15
0x18003e81e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003e822  inc     r8; int
0x18003e825  cmp     [rax+r8*2], r15w
0x18003e82a  jnz     short loc_18003E822
0x18003e82c  mov     rdx, rax; unsigned __int16 *
0x18003e82f  lea     rcx, [rbp+57h+var_90]; this
0x18003e833  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18003e838  lea     rcx, [rbp+57h+var_80]
0x18003e83c  mov     ebx, eax
0x18003e83e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003e843  test    ebx, ebx
0x18003e845  jz      short loc_18003E8BA
0x18003e847  mov     rax, [rdi]
0x18003e84a  jmp     short loc_18003E858
0x18003e84c  mov     rcx, rax; lpsz
0x18003e84f  call    cs:__imp_CharNextW
0x18003e855  mov     [rdi], rax
0x18003e858  cmp     rax, rsi
0x18003e85b  jnz     short loc_18003E84C
0x18003e85d  jmp     short loc_18003E875
0x18003e85f  mov     rdx, rbx; unsigned __int16 *
0x18003e862  mov     r8d, 1; int
0x18003e868  lea     rcx, [rbp+57h+var_90]; this
0x18003e86c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18003e871  test    eax, eax
0x18003e873  jz      short loc_18003E8BA
0x18003e875  mov     rcx, [rdi]; lpsz
0x18003e878  call    cs:__imp_CharNextW
0x18003e87e  mov     rbx, rax
0x18003e881  mov     [rdi], rax
0x18003e884  movzx   eax, word ptr [rax]
0x18003e887  test    ax, ax
0x18003e88a  jnz     loc_18003E79A
0x18003e890  mov     rcx, [rbp+57h+pv]
0x18003e894  mov     ebx, r15d
0x18003e897  mov     [rbp+57h+pv], r15
0x18003e89b  mov     [r14], rcx
0x18003e89e  mov     rcx, [rbp+57h+pv]; pv
0x18003e8a2  call    cs:__imp_CoTaskMemFree
0x18003e8a8  mov     eax, ebx
0x18003e8aa  jmp     short loc_18003E8C6
0x18003e8ac  mov     ebx, 80004005h
0x18003e8b1  jmp     short loc_18003E89E
0x18003e8b3  mov     ebx, 80020009h
0x18003e8b8  jmp     short loc_18003E89E
0x18003e8ba  mov     ebx, 8007000Eh
0x18003e8bf  jmp     short loc_18003E89E
0x18003e8c1  mov     eax, 80004003h
0x18003e8c6  mov     rcx, [rbp+57h+var_30]
0x18003e8ca  xor     rcx, rsp; StackCookie
0x18003e8cd  call    __security_check_cookie
0x18003e8d2  lea     r11, [rsp+0B0h+var_20]
0x18003e8da  mov     rbx, [r11+38h]
0x18003e8de  mov     rsi, [r11+48h]
0x18003e8e2  mov     rsp, r11
0x18003e8e5  pop     r15
0x18003e8e7  pop     r14
0x18003e8e9  pop     r12
0x18003e8eb  pop     rdi
0x18003e8ec  pop     rbp
0x18003e8ed  retn
```
