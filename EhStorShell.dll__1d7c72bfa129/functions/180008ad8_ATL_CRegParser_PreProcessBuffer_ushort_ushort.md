# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180008ad8`
- end: `0x180008d1a`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `578`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180008e9c`

## callees

- `0x1800065fc`
- `0x180006774`
- `0x1800084a8`
- `0x180008570`
- `0x1800089a8`
- `0x180008ad8`
- `0x18000b630`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180008bfa`
- `msvcrt!wcsncpy_s` at `0x180008bfa`
- `KERNEL32!lstrcmpiW` at `0x180008c27`
- `KERNEL32!lstrcmpiW` at `0x180008c27`
- `USER32!CharNextW` at `0x180008baa`
- `USER32!CharNextW` at `0x180008c83`
- `USER32!CharNextW` at `0x180008cac`
- `USER32!CharNextW` at `0x180008baa`
- `USER32!CharNextW` at `0x180008c83`
- `USER32!CharNextW` at `0x180008cac`
- `ole32!CoTaskMemFree` at `0x180008b7a`
- `ole32!CoTaskMemFree` at `0x180008ce4`
- `ole32!CoTaskMemFree` at `0x180008b7a`
- `ole32!CoTaskMemFree` at `0x180008ce4`
- `ole32!CoTaskMemAlloc` at `0x180008b5f`
- `ole32!CoTaskMemAlloc` at `0x180008b5f`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  LPWSTR v11; // rax
  const unsigned __int16 *v12; // rdx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rsi
  __int64 v15; // rcx
  errno_t v16; // eax
  LPCWSTR v17; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v19; // rdx
  __int64 v20; // r8
  int v21; // ebx
  const WCHAR *j; // rax
  unsigned int v23; // ebx
  unsigned __int16 *v24; // rcx
  _DWORD v25[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  _QWORD *v27; // [rsp+30h] [rbp-39h] BYREF
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
  v25[0] = 0;
  v25[1] = v7;
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
  for ( *this = v4; ; *this = v4 )
  {
    if ( !*v4 )
    {
      v23 = 0;
      v24 = (unsigned __int16 *)pv;
      pv = 0;
      *a3 = v24;
      goto LABEL_40;
    }
    if ( *v4 == 37 )
      break;
    v12 = v4;
LABEL_34:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v12, 1) )
    {
LABEL_38:
      v23 = -2147024882;
      goto LABEL_40;
    }
LABEL_35:
    v4 = CharNextW(*this);
  }
  v11 = CharNextW(v4);
  *this = v11;
  if ( *v11 == 37 )
  {
    v12 = v11;
    goto LABEL_34;
  }
  v13 = ATL::CRegParser::StrChrW(v11, 0x25u);
  v14 = v13;
  if ( v13 )
  {
    v15 = v13 - *this;
    if ( v15 > 31 )
    {
      v23 = -2147467259;
      goto LABEL_40;
    }
    v16 = wcsncpy_s(Destination, 0x20u, *this, (int)v15);
    ATL::AtlCrtErrorCheck(v16);
    v17 = this[1];
    for ( i = 0; (signed int)i < *((_DWORD *)v17 + 6); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v17 + 1) + 8LL * (int)i), Destination) )
      {
        if ( i == -1 )
          break;
        v19 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                            v17 + 4,
                                            i);
        if ( !v19 )
          break;
        v27 = 0;
        v20 = -1;
        do
          ++v20;
        while ( v19[v20] );
        v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v19, v20);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v27);
        if ( v21 )
        {
          for ( j = *this; j != v14; *this = j )
            j = CharNextW(j);
          goto LABEL_35;
        }
        goto LABEL_38;
      }
    }
  }
  v23 = -2147352567;
LABEL_40:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x180008ad8  mov     [rsp-8+arg_8], rbx
0x180008add  push    rbp
0x180008ade  push    rsi
0x180008adf  push    rdi
0x180008ae0  push    r12
0x180008ae2  push    r13
0x180008ae4  push    r14
0x180008ae6  push    r15
0x180008ae8  lea     rbp, [rsp-27h]
0x180008aed  sub     rsp, 90h
0x180008af4  mov     rax, cs:__security_cookie
0x180008afb  xor     rax, rsp
0x180008afe  mov     [rbp+57h+var_40], rax
0x180008b02  mov     r15, r8
0x180008b05  mov     rbx, rdx
0x180008b08  mov     rdi, rcx
0x180008b0b  xor     r12d, r12d
0x180008b0e  test    rdx, rdx
0x180008b11  jz      loc_180008CEE
0x180008b17  test    r8, r8
0x180008b1a  jz      loc_180008CEE
0x180008b20  mov     [r8], r12
0x180008b23  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008b27  inc     rax
0x180008b2a  cmp     [rdx+rax*2], r12w
0x180008b2f  jnz     short loc_180008B27
0x180008b31  add     eax, eax
0x180008b33  mov     ecx, 3E8h
0x180008b38  cmp     eax, 64h ; 'd'
0x180008b3b  cmovl   eax, ecx
0x180008b3e  mov     [rbp+57h+var_A0], r12d
0x180008b42  mov     [rbp+57h+var_9C], eax
0x180008b45  mov     ecx, eax
0x180008b47  add     rcx, rcx
0x180008b4a  mov     eax, 0FFFFFFFFh
0x180008b4f  cmp     rcx, rax
0x180008b52  jbe     short loc_180008B5D
0x180008b54  mov     rax, r12
0x180008b57  mov     [rbp+57h+pv], r12
0x180008b5b  jmp     short loc_180008B72
0x180008b5d  mov     ecx, ecx; cb
0x180008b5f  call    cs:__imp_CoTaskMemAlloc
0x180008b65  mov     [rbp+57h+pv], rax
0x180008b69  test    rax, rax
0x180008b6c  jz      short loc_180008B72
0x180008b6e  mov     [rax], r12w
0x180008b72  test    rax, rax
0x180008b75  jnz     short loc_180008B8A
0x180008b77  mov     rcx, rax; pv
0x180008b7a  call    cs:__imp_CoTaskMemFree
0x180008b80  mov     eax, 8007000Eh
0x180008b85  jmp     loc_180008CF3
0x180008b8a  mov     [rdi], rbx
0x180008b8d  mov     r13d, 25h ; '%'
0x180008b93  cmp     [rbx], r12w
0x180008b97  jz      loc_180008CD2
0x180008b9d  cmp     [rbx], r13w
0x180008ba1  jnz     loc_180008C93
0x180008ba7  mov     rcx, rbx; lpsz
0x180008baa  call    cs:__imp_CharNextW
0x180008bb0  mov     [rdi], rax
0x180008bb3  cmp     [rax], r13w
0x180008bb7  jnz     short loc_180008BC1
0x180008bb9  mov     rdx, rax
0x180008bbc  jmp     loc_180008C96
0x180008bc1  mov     edx, r13d; unsigned __int16
0x180008bc4  mov     rcx, rax; lpsz
0x180008bc7  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180008bcc  mov     rsi, rax
0x180008bcf  test    rax, rax
0x180008bd2  jz      loc_180008CC4
0x180008bd8  mov     rcx, rax
0x180008bdb  sub     rcx, [rdi]
0x180008bde  sar     rcx, 1
0x180008be1  cmp     rcx, 1Fh
0x180008be5  jg      loc_180008CBD
0x180008beb  movsxd  r9, ecx; MaxCount
0x180008bee  mov     r8, [rdi]; Source
0x180008bf1  mov     edx, 20h ; ' '; SizeInWords
0x180008bf6  lea     rcx, [rbp+57h+Destination]; Destination
0x180008bfa  call    cs:__imp_wcsncpy_s
0x180008c00  mov     ecx, eax; int
0x180008c02  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180008c07  mov     r14, [rdi+8]
0x180008c0b  mov     ebx, r12d
0x180008c0e  cmp     ebx, [r14+18h]
0x180008c12  jge     loc_180008CC4
0x180008c18  movsxd  rax, ebx
0x180008c1b  mov     rcx, [r14+8]
0x180008c1f  lea     rdx, [rbp+57h+Destination]; lpString2
0x180008c23  mov     rcx, [rcx+rax*8]; lpString1
0x180008c27  call    cs:__imp_lstrcmpiW
0x180008c2d  test    eax, eax
0x180008c2f  jz      short loc_180008C35
0x180008c31  inc     ebx
0x180008c33  jmp     short loc_180008C0E
0x180008c35  cmp     ebx, 0FFFFFFFFh
0x180008c38  jz      loc_180008CC4
0x180008c3e  mov     edx, ebx
0x180008c40  lea     rcx, [r14+8]
0x180008c44  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180008c49  mov     rdx, [rax]; unsigned __int16 *
0x180008c4c  test    rdx, rdx
0x180008c4f  jz      short loc_180008CC4
0x180008c51  mov     [rbp+57h+var_90], r12
0x180008c55  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008c59  inc     r8; int
0x180008c5c  cmp     [rdx+r8*2], r12w
0x180008c61  jnz     short loc_180008C59
0x180008c63  lea     rcx, [rbp+57h+var_A0]; this
0x180008c67  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180008c6c  mov     ebx, eax
0x180008c6e  lea     rcx, [rbp+57h+var_90]
0x180008c72  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008c77  test    ebx, ebx
0x180008c79  jz      short loc_180008CCB
0x180008c7b  mov     rax, [rdi]
0x180008c7e  jmp     short loc_180008C8C
0x180008c80  mov     rcx, rax; lpsz
0x180008c83  call    cs:__imp_CharNextW
0x180008c89  mov     [rdi], rax
0x180008c8c  cmp     rax, rsi
0x180008c8f  jnz     short loc_180008C80
0x180008c91  jmp     short loc_180008CA9
0x180008c93  mov     rdx, rbx; unsigned __int16 *
0x180008c96  mov     r8d, 1; int
0x180008c9c  lea     rcx, [rbp+57h+var_A0]; this
0x180008ca0  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180008ca5  test    eax, eax
0x180008ca7  jz      short loc_180008CCB
0x180008ca9  mov     rcx, [rdi]; lpsz
0x180008cac  call    cs:__imp_CharNextW
0x180008cb2  mov     rbx, rax
0x180008cb5  mov     [rdi], rax
0x180008cb8  jmp     loc_180008B93
0x180008cbd  mov     ebx, 80004005h
0x180008cc2  jmp     short loc_180008CE0
0x180008cc4  mov     ebx, 80020009h
0x180008cc9  jmp     short loc_180008CE0
0x180008ccb  mov     ebx, 8007000Eh
0x180008cd0  jmp     short loc_180008CE0
0x180008cd2  mov     ebx, r12d
0x180008cd5  mov     rcx, [rbp+57h+pv]
0x180008cd9  mov     [rbp+57h+pv], r12
0x180008cdd  mov     [r15], rcx
0x180008ce0  mov     rcx, [rbp+57h+pv]; pv
0x180008ce4  call    cs:__imp_CoTaskMemFree
0x180008cea  mov     eax, ebx
0x180008cec  jmp     short loc_180008CF3
0x180008cee  mov     eax, 80004003h
0x180008cf3  mov     rcx, [rbp+57h+var_40]
0x180008cf7  xor     rcx, rsp; StackCookie
0x180008cfa  call    __security_check_cookie
0x180008cff  mov     rbx, [rsp+0C0h+arg_8]
0x180008d07  add     rsp, 90h
0x180008d0e  pop     r15
0x180008d10  pop     r14
0x180008d12  pop     r13
0x180008d14  pop     r12
0x180008d16  pop     rdi
0x180008d17  pop     rsi
0x180008d18  pop     rbp
0x180008d19  retn
```
