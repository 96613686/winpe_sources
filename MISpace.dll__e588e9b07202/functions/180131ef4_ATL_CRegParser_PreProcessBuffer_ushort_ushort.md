# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180131ef4`
- end: `0x1801320ff`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `523`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18013230c`

## callees

- `0x180006290`
- `0x18012fa80`
- `0x1801304c8`
- `0x180131ef4`
- `0x180132e64`
- `0x180132ebc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18013200f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18013200f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180131f75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801320b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180131f75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801320b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180131f87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180131f87`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180131fbf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180132060`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180132089`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180131fbf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180132060`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180132089`

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
  const unsigned __int16 *v18; // rax
  __int64 v19; // r8
  int v20; // ebx
  const WCHAR *i; // rax
  unsigned int v22; // ebx
  __int64 v23; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v25; // [rsp+30h] [rbp-29h] BYREF
  unsigned __int16 v26[32]; // [rsp+40h] [rbp-19h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  LODWORD(v23) = 0;
  if ( v7 < 100 )
    v7 = 1000;
  HIDWORD(v23) = v7;
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
    v22 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_30;
  }
  while ( v12 != 37 )
  {
    v14 = v4;
LABEL_26:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v23, v14, 1) )
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
    v22 = -2147467259;
    goto LABEL_30;
  }
  _o_wcsncpy_s(v26, 32, *(_QWORD *)this, (int)v17, v23);
  v18 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), v26);
  if ( !v18 )
  {
LABEL_32:
    v22 = -2147352567;
    goto LABEL_30;
  }
  v25 = 0;
  v19 = -1;
  do
    ++v19;
  while ( v18[v19] );
  v20 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v23, v18, v19);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v25);
  if ( v20 )
  {
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
    goto LABEL_27;
  }
LABEL_33:
  v22 = -2147024882;
LABEL_30:
  CoTaskMemFree(pv);
  return v22;
}

```

## disassembly

```asm
0x180131ef4  mov     [rsp-8+arg_8], rbx
0x180131ef9  mov     [rsp-8+arg_18], rsi
0x180131efe  push    rbp
0x180131eff  push    rdi
0x180131f00  push    r12
0x180131f02  push    r14
0x180131f04  push    r15
0x180131f06  lea     rbp, [rsp-37h]
0x180131f0b  sub     rsp, 90h
0x180131f12  mov     rax, cs:__security_cookie
0x180131f19  xor     rax, rsp
0x180131f1c  mov     [rbp+57h+var_30], rax
0x180131f20  xor     r15d, r15d
0x180131f23  mov     r14, r8
0x180131f26  mov     rbx, rdx
0x180131f29  mov     rdi, rcx
0x180131f2c  test    rdx, rdx
0x180131f2f  jz      loc_1801320D2
0x180131f35  test    r8, r8
0x180131f38  jz      loc_1801320D2
0x180131f3e  mov     [r8], r15
0x180131f41  or      rax, 0FFFFFFFFFFFFFFFFh
0x180131f45  inc     rax
0x180131f48  cmp     [rdx+rax*2], r15w
0x180131f4d  jnz     short loc_180131F45
0x180131f4f  add     eax, eax
0x180131f51  mov     [rbp+57h+var_90], r15d
0x180131f55  cmp     eax, 64h ; 'd'
0x180131f58  mov     ecx, 3E8h
0x180131f5d  cmovl   eax, ecx
0x180131f60  mov     ecx, eax
0x180131f62  mov     [rbp+57h+var_8C], eax
0x180131f65  add     rcx, rcx
0x180131f68  mov     eax, 0FFFFFFFFh
0x180131f6d  cmp     rcx, rax
0x180131f70  jbe     short loc_180131F85
0x180131f72  mov     rcx, r15; pv
0x180131f75  call    cs:__imp_CoTaskMemFree
0x180131f7b  mov     eax, 8007000Eh
0x180131f80  jmp     loc_1801320D7
0x180131f85  mov     ecx, ecx; cb
0x180131f87  call    cs:__imp_CoTaskMemAlloc
0x180131f8d  mov     [rbp+57h+pv], rax
0x180131f91  mov     rcx, rax
0x180131f94  test    rax, rax
0x180131f97  jz      short loc_180131F75
0x180131f99  mov     [rax], r15w
0x180131f9d  mov     [rdi], rbx
0x180131fa0  movzx   eax, word ptr [rbx]
0x180131fa3  test    ax, ax
0x180131fa6  jz      loc_1801320A5
0x180131fac  mov     r12d, 25h ; '%'
0x180131fb2  cmp     ax, r12w
0x180131fb6  jnz     loc_180132070
0x180131fbc  mov     rcx, rbx; lpsz
0x180131fbf  call    cs:__imp_CharNextW
0x180131fc5  mov     [rdi], rax
0x180131fc8  cmp     [rax], r12w
0x180131fcc  jnz     short loc_180131FD6
0x180131fce  mov     rdx, rax
0x180131fd1  jmp     loc_180132073
0x180131fd6  mov     edx, r12d; unsigned __int16
0x180131fd9  mov     rcx, rax; lpsz
0x180131fdc  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180131fe1  mov     rsi, rax
0x180131fe4  test    rax, rax
0x180131fe7  jz      loc_1801320C4
0x180131fed  mov     rcx, rax
0x180131ff0  sub     rcx, [rdi]
0x180131ff3  sar     rcx, 1
0x180131ff6  cmp     rcx, 1Fh
0x180131ffa  jg      loc_1801320BD
0x180132000  mov     r8, [rdi]
0x180132003  mov     edx, 20h ; ' '
0x180132008  movsxd  r9, ecx
0x18013200b  lea     rcx, [rbp+57h+var_70]
0x18013200f  call    cs:__imp__o_wcsncpy_s
0x180132015  mov     rcx, [rdi+8]; this
0x180132019  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x18013201d  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x180132022  test    rax, rax
0x180132025  jz      loc_1801320C4
0x18013202b  mov     [rbp+57h+var_80], r15
0x18013202f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180132033  inc     r8; int
0x180132036  cmp     [rax+r8*2], r15w
0x18013203b  jnz     short loc_180132033
0x18013203d  mov     rdx, rax; unsigned __int16 *
0x180132040  lea     rcx, [rbp+57h+var_90]; this
0x180132044  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180132049  lea     rcx, [rbp+57h+var_80]
0x18013204d  mov     ebx, eax
0x18013204f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180132054  test    ebx, ebx
0x180132056  jz      short loc_1801320CB
0x180132058  mov     rax, [rdi]
0x18013205b  jmp     short loc_180132069
0x18013205d  mov     rcx, rax; lpsz
0x180132060  call    cs:__imp_CharNextW
0x180132066  mov     [rdi], rax
0x180132069  cmp     rax, rsi
0x18013206c  jnz     short loc_18013205D
0x18013206e  jmp     short loc_180132086
0x180132070  mov     rdx, rbx; unsigned __int16 *
0x180132073  mov     r8d, 1; int
0x180132079  lea     rcx, [rbp+57h+var_90]; this
0x18013207d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180132082  test    eax, eax
0x180132084  jz      short loc_1801320CB
0x180132086  mov     rcx, [rdi]; lpsz
0x180132089  call    cs:__imp_CharNextW
0x18013208f  mov     rbx, rax
0x180132092  mov     [rdi], rax
0x180132095  movzx   eax, word ptr [rax]
0x180132098  test    ax, ax
0x18013209b  jnz     loc_180131FB2
0x1801320a1  mov     rcx, [rbp+57h+pv]
0x1801320a5  mov     ebx, r15d
0x1801320a8  mov     [rbp+57h+pv], r15
0x1801320ac  mov     [r14], rcx
0x1801320af  mov     rcx, [rbp+57h+pv]; pv
0x1801320b3  call    cs:__imp_CoTaskMemFree
0x1801320b9  mov     eax, ebx
0x1801320bb  jmp     short loc_1801320D7
0x1801320bd  mov     ebx, 80004005h
0x1801320c2  jmp     short loc_1801320AF
0x1801320c4  mov     ebx, 80020009h
0x1801320c9  jmp     short loc_1801320AF
0x1801320cb  mov     ebx, 8007000Eh
0x1801320d0  jmp     short loc_1801320AF
0x1801320d2  mov     eax, 80004003h
0x1801320d7  mov     rcx, [rbp+57h+var_30]
0x1801320db  xor     rcx, rsp; StackCookie
0x1801320de  call    __security_check_cookie
0x1801320e3  lea     r11, [rsp+0B0h+var_20]
0x1801320eb  mov     rbx, [r11+38h]
0x1801320ef  mov     rsi, [r11+48h]
0x1801320f3  mov     rsp, r11
0x1801320f6  pop     r15
0x1801320f8  pop     r14
0x1801320fa  pop     r12
0x1801320fc  pop     rdi
0x1801320fd  pop     rbp
0x1801320fe  retn
```
