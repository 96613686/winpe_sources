# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180267e90`
- end: `0x180268126`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `662`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802688c0`

## callees

- `0x180258480`
- `0x18026395c`
- `0x180264f48`
- `0x18026519c`
- `0x1802676b0`
- `0x180267e90`
- `0x180269eec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180267fd1`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180267fd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180268044`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180268044`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180267fef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180267fef`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180267f61`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18026808e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1802680aa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180267f61`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18026808e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1802680aa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180268016`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180268016`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180267f12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802680e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180267f12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802680e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180267f2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180267f2a`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(ATL::CRegParser *this, unsigned __int16 *a2, LPVOID *a3)
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
  __int64 v26; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
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
  LODWORD(v26) = 0;
  if ( v7 < 100 )
    v7 = 1000;
  HIDWORD(v26) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v9 = CoTaskMemAlloc((unsigned int)v8);
  pv = v9;
  if ( !v9 )
    goto LABEL_9;
  *v9 = 0;
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_16:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v26, v12, 1) )
        goto LABEL_17;
      goto LABEL_34;
    }
    v11 = CharNextW(v4);
    *(_QWORD *)this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_16;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_37;
    v16 = ((__int64)v14 - *(_QWORD *)this) >> 1;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_39;
    }
    v17 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v16, v26);
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
          goto LABEL_27;
        }
        break;
      }
    }
    v22 = 0;
LABEL_27:
    LeaveCriticalSection(v19);
    if ( !v22 )
    {
LABEL_37:
      v13 = -2147352567;
      goto LABEL_39;
    }
    v28 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v26, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v28);
    if ( !v24 )
    {
LABEL_17:
      v13 = -2147024882;
      goto LABEL_39;
    }
    for ( j = *(const WCHAR **)this; j != v15; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_34:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v13 = 0;
  *a3 = pv;
  pv = 0;
LABEL_39:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x180267e90  mov     [rsp-8+arg_8], rbx
0x180267e95  push    rbp
0x180267e96  push    rsi
0x180267e97  push    rdi
0x180267e98  push    r12
0x180267e9a  push    r13
0x180267e9c  push    r14
0x180267e9e  push    r15
0x180267ea0  lea     rbp, [rsp-27h]
0x180267ea5  sub     rsp, 90h
0x180267eac  mov     rax, cs:__security_cookie
0x180267eb3  xor     rax, rsp
0x180267eb6  mov     [rbp+57h+var_40], rax
0x180267eba  xor     r13d, r13d
0x180267ebd  mov     r15, r8
0x180267ec0  mov     rbx, rdx
0x180267ec3  mov     rdi, rcx
0x180267ec6  test    rdx, rdx
0x180267ec9  jz      loc_1802680F9
0x180267ecf  test    r8, r8
0x180267ed2  jz      loc_1802680F9
0x180267ed8  mov     [r8], r13
0x180267edb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180267edf  inc     rax
0x180267ee2  cmp     [rdx+rax*2], r13w
0x180267ee7  jnz     short loc_180267EDF
0x180267ee9  add     eax, eax
0x180267eeb  mov     [rbp+57h+var_A0], r13d
0x180267eef  cmp     eax, 64h ; 'd'
0x180267ef2  mov     ecx, 3E8h
0x180267ef7  cmovl   eax, ecx
0x180267efa  mov     ecx, eax
0x180267efc  mov     [rbp+57h+var_9C], eax
0x180267eff  add     rcx, rcx
0x180267f02  mov     eax, 0FFFFFFFFh
0x180267f07  cmp     rcx, rax
0x180267f0a  jbe     short loc_180267F28
0x180267f0c  mov     rax, r13
0x180267f0f  mov     rcx, rax; pv
0x180267f12  call    cs:__imp_CoTaskMemFree
0x180267f19  nop     dword ptr [rax+rax+00h]
0x180267f1e  mov     eax, 8007000Eh
0x180267f23  jmp     loc_1802680FE
0x180267f28  mov     ecx, ecx; cb
0x180267f2a  call    cs:__imp_CoTaskMemAlloc
0x180267f31  nop     dword ptr [rax+rax+00h]
0x180267f36  mov     [rbp+57h+pv], rax
0x180267f3a  test    rax, rax
0x180267f3d  jz      short loc_180267F0F
0x180267f3f  mov     [rax], r13w
0x180267f43  mov     esi, 25h ; '%'
0x180267f48  mov     [rdi], rbx
0x180267f4b  cmp     [rbx], r13w
0x180267f4f  jz      loc_1802680D7
0x180267f55  cmp     [rbx], si
0x180267f58  jnz     loc_1802680C1
0x180267f5e  mov     rcx, rbx; lpsz
0x180267f61  call    cs:__imp_CharNextW
0x180267f68  nop     dword ptr [rax+rax+00h]
0x180267f6d  mov     [rdi], rax
0x180267f70  cmp     [rax], si
0x180267f73  jnz     short loc_180267F99
0x180267f75  mov     rdx, rax; unsigned __int16 *
0x180267f78  mov     r8d, 1; int
0x180267f7e  lea     rcx, [rbp+57h+var_A0]; this
0x180267f82  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180267f87  test    eax, eax
0x180267f89  jnz     loc_1802680A7
0x180267f8f  mov     ebx, 8007000Eh
0x180267f94  jmp     loc_1802680E5
0x180267f99  mov     edx, esi; unsigned __int16
0x180267f9b  mov     rcx, rax; lpsz
0x180267f9e  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180267fa3  mov     rsi, rax
0x180267fa6  test    rax, rax
0x180267fa9  jz      loc_1802680D0
0x180267faf  mov     rcx, rax
0x180267fb2  sub     rcx, [rdi]
0x180267fb5  sar     rcx, 1
0x180267fb8  cmp     rcx, 1Fh
0x180267fbc  jg      loc_1802680C9
0x180267fc2  mov     r8, [rdi]
0x180267fc5  mov     edx, 20h ; ' '
0x180267fca  movsxd  r9, ecx
0x180267fcd  lea     rcx, [rbp+57h+String2]
0x180267fd1  call    cs:__imp__o_wcsncpy_s
0x180267fd8  nop     dword ptr [rax+rax+00h]
0x180267fdd  mov     ecx, eax; int
0x180267fdf  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180267fe4  mov     rbx, [rdi+8]
0x180267fe8  lea     r12, [rbx+20h]
0x180267fec  mov     rcx, r12; lpCriticalSection
0x180267fef  call    cs:__imp_EnterCriticalSection
0x180267ff6  nop     dword ptr [rax+rax+00h]
0x180267ffb  lea     r14, [rbx+8]
0x180267fff  mov     ebx, r13d
0x180268002  cmp     ebx, [r14+10h]
0x180268006  jge     short loc_18026803E
0x180268008  mov     rcx, [r14]
0x18026800b  lea     rdx, [rbp+57h+String2]; lpString2
0x18026800f  movsxd  rax, ebx
0x180268012  mov     rcx, [rcx+rax*8]; lpString1
0x180268016  call    cs:__imp_lstrcmpiW
0x18026801d  nop     dword ptr [rax+rax+00h]
0x180268022  test    eax, eax
0x180268024  jz      short loc_18026802A
0x180268026  inc     ebx
0x180268028  jmp     short loc_180268002
0x18026802a  cmp     ebx, 0FFFFFFFFh
0x18026802d  jz      short loc_18026803E
0x18026802f  mov     edx, ebx
0x180268031  mov     rcx, r14
0x180268034  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180268039  mov     rbx, [rax]
0x18026803c  jmp     short loc_180268041
0x18026803e  mov     rbx, r13
0x180268041  mov     rcx, r12; lpCriticalSection
0x180268044  call    cs:__imp_LeaveCriticalSection
0x18026804b  nop     dword ptr [rax+rax+00h]
0x180268050  test    rbx, rbx
0x180268053  jz      short loc_1802680D0
0x180268055  mov     [rbp+57h+var_90], r13
0x180268059  or      r8, 0FFFFFFFFFFFFFFFFh
0x18026805d  inc     r8; int
0x180268060  cmp     [rbx+r8*2], r13w
0x180268065  jnz     short loc_18026805D
0x180268067  mov     rdx, rbx; unsigned __int16 *
0x18026806a  lea     rcx, [rbp+57h+var_A0]; this
0x18026806e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180268073  lea     rcx, [rbp+57h+var_90]
0x180268077  mov     ebx, eax
0x180268079  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18026807e  test    ebx, ebx
0x180268080  jz      loc_180267F8F
0x180268086  mov     rax, [rdi]
0x180268089  jmp     short loc_18026809D
0x18026808b  mov     rcx, rax; lpsz
0x18026808e  call    cs:__imp_CharNextW
0x180268095  nop     dword ptr [rax+rax+00h]
0x18026809a  mov     [rdi], rax
0x18026809d  cmp     rax, rsi
0x1802680a0  jnz     short loc_18026808B
0x1802680a2  mov     esi, 25h ; '%'
0x1802680a7  mov     rcx, [rdi]; lpsz
0x1802680aa  call    cs:__imp_CharNextW
0x1802680b1  nop     dword ptr [rax+rax+00h]
0x1802680b6  mov     rbx, rax
0x1802680b9  mov     [rdi], rax
0x1802680bc  jmp     loc_180267F4B
0x1802680c1  mov     rdx, rbx
0x1802680c4  jmp     loc_180267F78
0x1802680c9  mov     ebx, 80004005h
0x1802680ce  jmp     short loc_1802680E5
0x1802680d0  mov     ebx, 80020009h
0x1802680d5  jmp     short loc_1802680E5
0x1802680d7  mov     rcx, [rbp+57h+pv]
0x1802680db  mov     ebx, r13d
0x1802680de  mov     [r15], rcx
0x1802680e1  mov     [rbp+57h+pv], r13
0x1802680e5  mov     rcx, [rbp+57h+pv]; pv
0x1802680e9  call    cs:__imp_CoTaskMemFree
0x1802680f0  nop     dword ptr [rax+rax+00h]
0x1802680f5  mov     eax, ebx
0x1802680f7  jmp     short loc_1802680FE
0x1802680f9  mov     eax, 80004003h
0x1802680fe  mov     rcx, [rbp+57h+var_40]
0x180268102  xor     rcx, rsp; StackCookie
0x180268105  call    __security_check_cookie
0x18026810a  mov     rbx, [rsp+0C0h+arg_8]
0x180268112  add     rsp, 90h
0x180268119  pop     r15
0x18026811b  pop     r14
0x18026811d  pop     r13
0x18026811f  pop     r12
0x180268121  pop     rdi
0x180268122  pop     rsi
0x180268123  pop     rbp
0x180268124  retn
```
