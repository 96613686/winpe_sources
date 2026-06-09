# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180018330`
- end: `0x18001856f`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `575`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018b90`

## callees

- `0x180013f48`
- `0x18001548c`
- `0x180015728`
- `0x180018330`
- `0x180019b54`
- `0x180019ba0`
- `0x18002fb50`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180018469`
- `msvcrt!wcsncpy_s` at `0x180018469`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800183be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800183be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800183de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018531`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800183de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018531`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018413`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800184c7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800184f6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018413`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800184c7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800184f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  unsigned int v6; // edi
  __int64 v7; // rax
  int v8; // eax
  unsigned __int64 v9; // rcx
  _WORD *v10; // rax
  LPWSTR v12; // rax
  const unsigned __int16 *v13; // rdx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r14
  __int64 v16; // rcx
  errno_t v17; // ecx
  const unsigned __int16 *v18; // rax
  __int64 v19; // r8
  int v20; // ebx
  const WCHAR *i; // rax
  unsigned __int16 *v22; // rcx
  _DWORD v23[2]; // [rsp+28h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-31h]
  _QWORD v25[2]; // [rsp+38h] [rbp-29h] BYREF
  wchar_t Destination[32]; // [rsp+48h] [rbp-19h] BYREF

  v25[1] = -2;
  v4 = a2;
  v6 = 0;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = 2 * v7;
  if ( v8 < 100 )
    v8 = 1000;
  v23[0] = 0;
  v23[1] = v8;
  v9 = 2LL * (unsigned int)v8;
  if ( v9 <= 0xFFFFFFFF )
  {
    v10 = CoTaskMemAlloc((unsigned int)v9);
    pv = v10;
    if ( v10 )
      *v10 = 0;
  }
  else
  {
    v10 = 0;
    pv = 0;
  }
  if ( !v10 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v13 = v4;
LABEL_29:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v23, v13, 1) )
        goto LABEL_33;
      goto LABEL_30;
    }
    v12 = CharNextW(v4);
    *(_QWORD *)this = v12;
    if ( *v12 == 37 )
    {
      v13 = v12;
      goto LABEL_29;
    }
    v14 = ATL::CRegParser::StrChrW(v12, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_32;
    v16 = ((__int64)v14 - *(_QWORD *)this) >> 1;
    if ( v16 > 31 )
    {
      v6 = -2147467259;
      goto LABEL_35;
    }
    v17 = wcsncpy_s(Destination, 0x20u, *(const wchar_t **)this, (int)v16);
    ATL::AtlCrtErrorCheck(v17);
    v18 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), Destination);
    if ( !v18 )
    {
LABEL_32:
      v6 = -2147352567;
      goto LABEL_35;
    }
    v25[0] = 0;
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
    v20 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v23, v18, v19);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v25);
    if ( !v20 )
    {
LABEL_33:
      v6 = -2147024882;
      goto LABEL_35;
    }
    for ( i = *(const WCHAR **)this; i != v15; *(_QWORD *)this = i )
      i = CharNextW(i);
LABEL_30:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v22 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v22;
LABEL_35:
  CoTaskMemFree(pv);
  return v6;
}

```

## disassembly

```asm
0x180018330  mov     rax, rsp
0x180018333  push    rbp
0x180018334  push    rdi
0x180018335  push    r12
0x180018337  push    r14
0x180018339  push    r15
0x18001833b  lea     rbp, [rax-5Fh]
0x18001833f  sub     rsp, 90h
0x180018346  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x18001834e  mov     [rax+10h], rbx
0x180018352  mov     [rax+20h], rsi
0x180018356  mov     rax, cs:__security_cookie
0x18001835d  xor     rax, rsp
0x180018360  mov     [rbp+57h+var_30], rax
0x180018364  mov     r15, r8
0x180018367  mov     rbx, rdx
0x18001836a  mov     rsi, rcx
0x18001836d  xor     edi, edi
0x18001836f  test    rdx, rdx
0x180018372  jz      loc_180018541
0x180018378  test    r8, r8
0x18001837b  jz      loc_180018541
0x180018381  mov     [r8], rdi
0x180018384  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018388  inc     rax
0x18001838b  cmp     [rdx+rax*2], di
0x18001838f  jnz     short loc_180018388
0x180018391  add     eax, eax
0x180018393  mov     ecx, 3E8h
0x180018398  cmp     eax, 64h ; 'd'
0x18001839b  cmovl   eax, ecx
0x18001839e  mov     [rbp+57h+var_90], edi
0x1800183a1  mov     [rbp+57h+var_8C], eax
0x1800183a4  mov     ecx, eax
0x1800183a6  add     rcx, rcx
0x1800183a9  mov     eax, 0FFFFFFFFh
0x1800183ae  cmp     rcx, rax
0x1800183b1  jbe     short loc_1800183BC
0x1800183b3  mov     rax, rdi
0x1800183b6  mov     [rbp+57h+pv], rdi
0x1800183ba  jmp     short loc_1800183D6
0x1800183bc  mov     ecx, ecx; cb
0x1800183be  call    cs:__imp_CoTaskMemAlloc
0x1800183c5  nop     dword ptr [rax+rax+00h]
0x1800183ca  mov     [rbp+57h+pv], rax
0x1800183ce  test    rax, rax
0x1800183d1  jz      short loc_1800183D6
0x1800183d3  mov     [rax], di
0x1800183d6  test    rax, rax
0x1800183d9  jnz     short loc_1800183F4
0x1800183db  mov     rcx, rax; pv
0x1800183de  call    cs:__imp_CoTaskMemFree
0x1800183e5  nop     dword ptr [rax+rax+00h]
0x1800183ea  mov     eax, 8007000Eh
0x1800183ef  jmp     loc_180018546
0x1800183f4  mov     [rsi], rbx
0x1800183f7  mov     r12d, 25h ; '%'
0x1800183fd  cmp     [rbx], di
0x180018400  jz      loc_180018522
0x180018406  cmp     [rbx], r12w
0x18001840a  jnz     loc_1800184DD
0x180018410  mov     rcx, rbx; lpsz
0x180018413  call    cs:__imp_CharNextW
0x18001841a  nop     dword ptr [rax+rax+00h]
0x18001841f  mov     [rsi], rax
0x180018422  cmp     [rax], r12w
0x180018426  jnz     short loc_180018430
0x180018428  mov     rdx, rax
0x18001842b  jmp     loc_1800184E0
0x180018430  mov     edx, r12d; unsigned __int16
0x180018433  mov     rcx, rax; lpsz
0x180018436  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001843b  mov     r14, rax
0x18001843e  test    rax, rax
0x180018441  jz      loc_180018514
0x180018447  mov     rcx, rax
0x18001844a  sub     rcx, [rsi]
0x18001844d  sar     rcx, 1
0x180018450  cmp     rcx, 1Fh
0x180018454  jg      loc_18001850D
0x18001845a  movsxd  r9, ecx; MaxCount
0x18001845d  mov     r8, [rsi]; Source
0x180018460  mov     edx, 20h ; ' '; SizeInWords
0x180018465  lea     rcx, [rbp+57h+Destination]; Destination
0x180018469  call    cs:__imp_wcsncpy_s
0x180018470  nop     dword ptr [rax+rax+00h]
0x180018475  mov     ecx, eax; int
0x180018477  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001847c  lea     rdx, [rbp+57h+Destination]; unsigned __int16 *
0x180018480  mov     rcx, [rsi+8]; this
0x180018484  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x180018489  test    rax, rax
0x18001848c  jz      loc_180018514
0x180018492  mov     [rbp+57h+var_80], rdi
0x180018496  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001849a  inc     r8; int
0x18001849d  cmp     [rax+r8*2], di
0x1800184a2  jnz     short loc_18001849A
0x1800184a4  mov     rdx, rax; unsigned __int16 *
0x1800184a7  lea     rcx, [rbp+57h+var_90]; this
0x1800184ab  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800184b0  mov     ebx, eax
0x1800184b2  lea     rcx, [rbp+57h+var_80]
0x1800184b6  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800184bb  test    ebx, ebx
0x1800184bd  jz      short loc_18001851B
0x1800184bf  mov     rax, [rsi]
0x1800184c2  jmp     short loc_1800184D6
0x1800184c4  mov     rcx, rax; lpsz
0x1800184c7  call    cs:__imp_CharNextW
0x1800184ce  nop     dword ptr [rax+rax+00h]
0x1800184d3  mov     [rsi], rax
0x1800184d6  cmp     rax, r14
0x1800184d9  jnz     short loc_1800184C4
0x1800184db  jmp     short loc_1800184F3
0x1800184dd  mov     rdx, rbx; unsigned __int16 *
0x1800184e0  mov     r8d, 1; int
0x1800184e6  lea     rcx, [rbp+57h+var_90]; this
0x1800184ea  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800184ef  test    eax, eax
0x1800184f1  jz      short loc_18001851B
0x1800184f3  mov     rcx, [rsi]; lpsz
0x1800184f6  call    cs:__imp_CharNextW
0x1800184fd  nop     dword ptr [rax+rax+00h]
0x180018502  mov     rbx, rax
0x180018505  mov     [rsi], rax
0x180018508  jmp     loc_1800183FD
0x18001850d  mov     edi, 80004005h
0x180018512  jmp     short loc_18001852D
0x180018514  mov     edi, 80020009h
0x180018519  jmp     short loc_18001852D
0x18001851b  mov     edi, 8007000Eh
0x180018520  jmp     short loc_18001852D
0x180018522  mov     rcx, [rbp+57h+pv]
0x180018526  mov     [rbp+57h+pv], rdi
0x18001852a  mov     [r15], rcx
0x18001852d  mov     rcx, [rbp+57h+pv]; pv
0x180018531  call    cs:__imp_CoTaskMemFree
0x180018538  nop     dword ptr [rax+rax+00h]
0x18001853d  mov     eax, edi
0x18001853f  jmp     short loc_180018546
0x180018541  mov     eax, 80004003h
0x180018546  mov     rcx, [rbp+57h+var_30]
0x18001854a  xor     rcx, rsp; StackCookie
0x18001854d  call    __security_check_cookie
0x180018552  lea     r11, [rsp+0B0h+var_20]
0x18001855a  mov     rbx, [r11+38h]
0x18001855e  mov     rsi, [r11+48h]
0x180018562  mov     rsp, r11
0x180018565  pop     r15
0x180018567  pop     r14
0x180018569  pop     r12
0x18001856b  pop     rdi
0x18001856c  pop     rbp
0x18001856d  retn
```
