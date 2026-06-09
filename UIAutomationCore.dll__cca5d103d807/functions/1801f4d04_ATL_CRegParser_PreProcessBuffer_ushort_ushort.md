# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1801f4d04`
- end: `0x1801f4f46`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `578`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801f52f8`

## callees

- `0x1801e8320`
- `0x1801f1dfc`
- `0x1801f3020`
- `0x1801f3274`
- `0x1801f46f8`
- `0x1801f4d04`
- `0x1801f647c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1801f4e26`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1801f4e26`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801f4dd6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801f4eaf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801f4ed8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801f4dd6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801f4eaf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801f4ed8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801f4e53`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801f4e53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f4da6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f4f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f4da6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f4f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801f4d8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801f4d8b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  int v16; // eax
  LPCWSTR v17; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v19; // rdx
  __int64 v20; // r8
  int v21; // ebx
  const WCHAR *j; // rax
  unsigned int v23; // ebx
  unsigned __int16 *v24; // rcx
  __int64 v25; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v27; // [rsp+30h] [rbp-39h] BYREF
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
  LODWORD(v25) = 0;
  HIDWORD(v25) = v7;
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
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v25, v12, 1) )
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
    v16 = _o_wcsncpy_s(String2, 32, *this, (int)v15, v25);
    ATL::AtlCrtErrorCheck(v16);
    v17 = this[1];
    for ( i = 0; (signed int)i < *((_DWORD *)v17 + 6); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v17 + 1) + 8LL * (int)i), String2) )
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
        v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v25, v19, v20);
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
0x1801f4d04  mov     [rsp-8+arg_8], rbx
0x1801f4d09  push    rbp
0x1801f4d0a  push    rsi
0x1801f4d0b  push    rdi
0x1801f4d0c  push    r12
0x1801f4d0e  push    r13
0x1801f4d10  push    r14
0x1801f4d12  push    r15
0x1801f4d14  lea     rbp, [rsp-27h]
0x1801f4d19  sub     rsp, 90h
0x1801f4d20  mov     rax, cs:__security_cookie
0x1801f4d27  xor     rax, rsp
0x1801f4d2a  mov     [rbp+57h+var_40], rax
0x1801f4d2e  mov     r15, r8
0x1801f4d31  mov     rbx, rdx
0x1801f4d34  mov     rdi, rcx
0x1801f4d37  xor     r12d, r12d
0x1801f4d3a  test    rdx, rdx
0x1801f4d3d  jz      loc_1801F4F1A
0x1801f4d43  test    r8, r8
0x1801f4d46  jz      loc_1801F4F1A
0x1801f4d4c  mov     [r8], r12
0x1801f4d4f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801f4d53  inc     rax
0x1801f4d56  cmp     [rdx+rax*2], r12w
0x1801f4d5b  jnz     short loc_1801F4D53
0x1801f4d5d  add     eax, eax
0x1801f4d5f  mov     ecx, 3E8h
0x1801f4d64  cmp     eax, 64h ; 'd'
0x1801f4d67  cmovl   eax, ecx
0x1801f4d6a  mov     [rbp+57h+var_A0], r12d
0x1801f4d6e  mov     [rbp+57h+var_9C], eax
0x1801f4d71  mov     ecx, eax
0x1801f4d73  add     rcx, rcx
0x1801f4d76  mov     eax, 0FFFFFFFFh
0x1801f4d7b  cmp     rcx, rax
0x1801f4d7e  jbe     short loc_1801F4D89
0x1801f4d80  mov     rax, r12
0x1801f4d83  mov     [rbp+57h+pv], r12
0x1801f4d87  jmp     short loc_1801F4D9E
0x1801f4d89  mov     ecx, ecx; cb
0x1801f4d8b  call    cs:__imp_CoTaskMemAlloc
0x1801f4d91  mov     [rbp+57h+pv], rax
0x1801f4d95  test    rax, rax
0x1801f4d98  jz      short loc_1801F4D9E
0x1801f4d9a  mov     [rax], r12w
0x1801f4d9e  test    rax, rax
0x1801f4da1  jnz     short loc_1801F4DB6
0x1801f4da3  mov     rcx, rax; pv
0x1801f4da6  call    cs:__imp_CoTaskMemFree
0x1801f4dac  mov     eax, 8007000Eh
0x1801f4db1  jmp     loc_1801F4F1F
0x1801f4db6  mov     [rdi], rbx
0x1801f4db9  mov     r13d, 25h ; '%'
0x1801f4dbf  cmp     [rbx], r12w
0x1801f4dc3  jz      loc_1801F4EFE
0x1801f4dc9  cmp     [rbx], r13w
0x1801f4dcd  jnz     loc_1801F4EBF
0x1801f4dd3  mov     rcx, rbx; lpsz
0x1801f4dd6  call    cs:__imp_CharNextW
0x1801f4ddc  mov     [rdi], rax
0x1801f4ddf  cmp     [rax], r13w
0x1801f4de3  jnz     short loc_1801F4DED
0x1801f4de5  mov     rdx, rax
0x1801f4de8  jmp     loc_1801F4EC2
0x1801f4ded  mov     edx, r13d; unsigned __int16
0x1801f4df0  mov     rcx, rax; lpsz
0x1801f4df3  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1801f4df8  mov     rsi, rax
0x1801f4dfb  test    rax, rax
0x1801f4dfe  jz      loc_1801F4EF0
0x1801f4e04  mov     rcx, rax
0x1801f4e07  sub     rcx, [rdi]
0x1801f4e0a  sar     rcx, 1
0x1801f4e0d  cmp     rcx, 1Fh
0x1801f4e11  jg      loc_1801F4EE9
0x1801f4e17  movsxd  r9, ecx
0x1801f4e1a  mov     r8, [rdi]
0x1801f4e1d  mov     edx, 20h ; ' '
0x1801f4e22  lea     rcx, [rbp+57h+String2]
0x1801f4e26  call    cs:__imp__o_wcsncpy_s
0x1801f4e2c  mov     ecx, eax; int
0x1801f4e2e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1801f4e33  mov     r14, [rdi+8]
0x1801f4e37  mov     ebx, r12d
0x1801f4e3a  cmp     ebx, [r14+18h]
0x1801f4e3e  jge     loc_1801F4EF0
0x1801f4e44  movsxd  rax, ebx
0x1801f4e47  mov     rcx, [r14+8]
0x1801f4e4b  lea     rdx, [rbp+57h+String2]; lpString2
0x1801f4e4f  mov     rcx, [rcx+rax*8]; lpString1
0x1801f4e53  call    cs:__imp_lstrcmpiW
0x1801f4e59  test    eax, eax
0x1801f4e5b  jz      short loc_1801F4E61
0x1801f4e5d  inc     ebx
0x1801f4e5f  jmp     short loc_1801F4E3A
0x1801f4e61  cmp     ebx, 0FFFFFFFFh
0x1801f4e64  jz      loc_1801F4EF0
0x1801f4e6a  mov     edx, ebx
0x1801f4e6c  lea     rcx, [r14+8]
0x1801f4e70  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1801f4e75  mov     rdx, [rax]; unsigned __int16 *
0x1801f4e78  test    rdx, rdx
0x1801f4e7b  jz      short loc_1801F4EF0
0x1801f4e7d  mov     [rbp+57h+var_90], r12
0x1801f4e81  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801f4e85  inc     r8; int
0x1801f4e88  cmp     [rdx+r8*2], r12w
0x1801f4e8d  jnz     short loc_1801F4E85
0x1801f4e8f  lea     rcx, [rbp+57h+var_A0]; this
0x1801f4e93  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1801f4e98  mov     ebx, eax
0x1801f4e9a  lea     rcx, [rbp+57h+var_90]
0x1801f4e9e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1801f4ea3  test    ebx, ebx
0x1801f4ea5  jz      short loc_1801F4EF7
0x1801f4ea7  mov     rax, [rdi]
0x1801f4eaa  jmp     short loc_1801F4EB8
0x1801f4eac  mov     rcx, rax; lpsz
0x1801f4eaf  call    cs:__imp_CharNextW
0x1801f4eb5  mov     [rdi], rax
0x1801f4eb8  cmp     rax, rsi
0x1801f4ebb  jnz     short loc_1801F4EAC
0x1801f4ebd  jmp     short loc_1801F4ED5
0x1801f4ebf  mov     rdx, rbx; unsigned __int16 *
0x1801f4ec2  mov     r8d, 1; int
0x1801f4ec8  lea     rcx, [rbp+57h+var_A0]; this
0x1801f4ecc  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1801f4ed1  test    eax, eax
0x1801f4ed3  jz      short loc_1801F4EF7
0x1801f4ed5  mov     rcx, [rdi]; lpsz
0x1801f4ed8  call    cs:__imp_CharNextW
0x1801f4ede  mov     rbx, rax
0x1801f4ee1  mov     [rdi], rax
0x1801f4ee4  jmp     loc_1801F4DBF
0x1801f4ee9  mov     ebx, 80004005h
0x1801f4eee  jmp     short loc_1801F4F0C
0x1801f4ef0  mov     ebx, 80020009h
0x1801f4ef5  jmp     short loc_1801F4F0C
0x1801f4ef7  mov     ebx, 8007000Eh
0x1801f4efc  jmp     short loc_1801F4F0C
0x1801f4efe  mov     ebx, r12d
0x1801f4f01  mov     rcx, [rbp+57h+pv]
0x1801f4f05  mov     [rbp+57h+pv], r12
0x1801f4f09  mov     [r15], rcx
0x1801f4f0c  mov     rcx, [rbp+57h+pv]; pv
0x1801f4f10  call    cs:__imp_CoTaskMemFree
0x1801f4f16  mov     eax, ebx
0x1801f4f18  jmp     short loc_1801F4F1F
0x1801f4f1a  mov     eax, 80004003h
0x1801f4f1f  mov     rcx, [rbp+57h+var_40]
0x1801f4f23  xor     rcx, rsp; StackCookie
0x1801f4f26  call    __security_check_cookie
0x1801f4f2b  mov     rbx, [rsp+0C0h+arg_8]
0x1801f4f33  add     rsp, 90h
0x1801f4f3a  pop     r15
0x1801f4f3c  pop     r14
0x1801f4f3e  pop     r13
0x1801f4f40  pop     r12
0x1801f4f42  pop     rdi
0x1801f4f43  pop     rsi
0x1801f4f44  pop     rbp
0x1801f4f45  retn
```
