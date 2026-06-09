# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180018d5c`
- end: `0x180018fc9`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `621`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001916c`

## callees

- `0x180010e60`
- `0x180016020`
- `0x18001755c`
- `0x1800175c0`
- `0x180018098`
- `0x180018b3c`
- `0x180018d5c`
- `0x180019cf4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180018e9f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180018e9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018eb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018eb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018dec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018dec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018f93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018f93`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018e35`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018f44`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018f5a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018e35`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018f44`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018f5a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180018ed8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180018ed8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // rdx
  _WORD *v8; // rax
  LPWSTR v10; // rax
  const unsigned __int16 *v11; // rdx
  unsigned int v12; // ebx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rsi
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // r12
  __int64 v19; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  int v23; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v25; // rcx
  SIZE_T cb; // [rsp+20h] [rbp-49h] BYREF
  _DWORD v27[2]; // [rsp+28h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-39h]
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  v7 = (unsigned int)(2 * v6);
  if ( (int)v7 < 100 )
    v7 = 1000;
  v27[0] = 0;
  v27[1] = v7;
  LODWORD(cb) = 0;
  if ( (int)ATL::AtlMultiply<unsigned long>(&cb, v7, 2) >= 0 )
  {
    v8 = CoTaskMemAlloc((unsigned int)cb);
    pv = v8;
    if ( v8 )
      *v8 = 0;
  }
  else
  {
    v8 = 0;
    pv = 0;
  }
  if ( !v8 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v11 = v4;
LABEL_18:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v11, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v10 = CharNextW(v4);
    *(_QWORD *)this = v10;
    if ( *v10 == 37 )
    {
      v11 = v10;
      goto LABEL_18;
    }
    v13 = ATL::CRegParser::StrChrW(v10, 0x25u);
    v14 = v13;
    if ( !v13 )
      goto LABEL_39;
    v15 = ((__int64)v13 - *(_QWORD *)this) >> 1;
    if ( v15 > 31 )
    {
      v12 = -2147467259;
      goto LABEL_41;
    }
    v16 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v15);
    ATL::AtlCrtErrorCheck(v16);
    v17 = *((_QWORD *)this + 1);
    v18 = (struct _RTL_CRITICAL_SECTION *)(v17 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 32));
    v19 = v17 + 8;
    for ( i = 0; (signed int)i < *(_DWORD *)(v19 + 16); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v19 + 8LL * (int)i), String2) )
      {
        if ( i != -1 )
        {
          v21 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                              v19,
                                              i);
          goto LABEL_29;
        }
        break;
      }
    }
    v21 = 0;
LABEL_29:
    LeaveCriticalSection(v18);
    if ( !v21 )
    {
LABEL_39:
      v12 = -2147352567;
      goto LABEL_41;
    }
    cb = 0;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    v23 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v21, v22);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&cb);
    if ( !v23 )
    {
LABEL_19:
      v12 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *(const WCHAR **)this; j != v14; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v12 = 0;
  v25 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v25;
LABEL_41:
  CoTaskMemFree(pv);
  return v12;
}

```

## disassembly

```asm
0x180018d5c  mov     [rsp-8+arg_8], rbx
0x180018d61  push    rbp
0x180018d62  push    rsi
0x180018d63  push    rdi
0x180018d64  push    r12
0x180018d66  push    r13
0x180018d68  push    r14
0x180018d6a  push    r15
0x180018d6c  lea     rbp, [rsp-27h]
0x180018d71  sub     rsp, 90h
0x180018d78  mov     rax, cs:__security_cookie
0x180018d7f  xor     rax, rsp
0x180018d82  mov     [rbp+57h+var_40], rax
0x180018d86  mov     r15, r8
0x180018d89  mov     rbx, rdx
0x180018d8c  mov     rdi, rcx
0x180018d8f  xor     r13d, r13d
0x180018d92  test    rdx, rdx
0x180018d95  jz      loc_180018F9D
0x180018d9b  test    r8, r8
0x180018d9e  jz      loc_180018F9D
0x180018da4  mov     [r8], r13
0x180018da7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180018dab  inc     rdx
0x180018dae  cmp     [rbx+rdx*2], r13w
0x180018db3  jnz     short loc_180018DAB
0x180018db5  add     edx, edx
0x180018db7  mov     eax, 3E8h
0x180018dbc  cmp     edx, 64h ; 'd'
0x180018dbf  cmovl   edx, eax
0x180018dc2  mov     [rbp+57h+var_98], r13d
0x180018dc6  mov     [rbp+57h+var_94], edx
0x180018dc9  mov     dword ptr [rbp+57h+cb], r13d
0x180018dcd  mov     r8d, 2
0x180018dd3  lea     rcx, [rbp+57h+cb]
0x180018dd7  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x180018ddc  test    eax, eax
0x180018dde  jns     short loc_180018DE9
0x180018de0  mov     rax, r13
0x180018de3  mov     [rbp+57h+pv], r13
0x180018de7  jmp     short loc_180018DFF
0x180018de9  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180018dec  call    cs:__imp_CoTaskMemAlloc
0x180018df2  mov     [rbp+57h+pv], rax
0x180018df6  test    rax, rax
0x180018df9  jz      short loc_180018DFF
0x180018dfb  mov     [rax], r13w
0x180018dff  test    rax, rax
0x180018e02  jnz     short loc_180018E17
0x180018e04  mov     rcx, rax; pv
0x180018e07  call    cs:__imp_CoTaskMemFree
0x180018e0d  mov     eax, 8007000Eh
0x180018e12  jmp     loc_180018FA2
0x180018e17  mov     [rdi], rbx
0x180018e1a  mov     esi, 25h ; '%'
0x180018e1f  cmp     [rbx], r13w
0x180018e23  jz      loc_180018F81
0x180018e29  cmp     [rbx], si
0x180018e2c  jnz     loc_180018F6B
0x180018e32  mov     rcx, rbx; lpsz
0x180018e35  call    cs:__imp_CharNextW
0x180018e3b  mov     [rdi], rax
0x180018e3e  cmp     [rax], si
0x180018e41  jnz     short loc_180018E67
0x180018e43  mov     rdx, rax; unsigned __int16 *
0x180018e46  mov     r8d, 1; int
0x180018e4c  lea     rcx, [rbp+57h+var_98]; this
0x180018e50  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180018e55  test    eax, eax
0x180018e57  jnz     loc_180018F57
0x180018e5d  mov     ebx, 8007000Eh
0x180018e62  jmp     loc_180018F8F
0x180018e67  mov     edx, esi; unsigned __int16
0x180018e69  mov     rcx, rax; lpsz
0x180018e6c  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180018e71  mov     rsi, rax
0x180018e74  test    rax, rax
0x180018e77  jz      loc_180018F7A
0x180018e7d  mov     rcx, rax
0x180018e80  sub     rcx, [rdi]
0x180018e83  sar     rcx, 1
0x180018e86  cmp     rcx, 1Fh
0x180018e8a  jg      loc_180018F73
0x180018e90  movsxd  r9, ecx
0x180018e93  mov     r8, [rdi]
0x180018e96  mov     edx, 20h ; ' '
0x180018e9b  lea     rcx, [rbp+57h+String2]
0x180018e9f  call    cs:__imp__o_wcsncpy_s
0x180018ea5  mov     ecx, eax; int
0x180018ea7  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180018eac  mov     rbx, [rdi+8]
0x180018eb0  lea     r12, [rbx+20h]
0x180018eb4  mov     rcx, r12; lpCriticalSection
0x180018eb7  call    cs:__imp_EnterCriticalSection
0x180018ebd  lea     r14, [rbx+8]
0x180018ec1  mov     ebx, r13d
0x180018ec4  cmp     ebx, [r14+10h]
0x180018ec8  jge     short loc_180018EFA
0x180018eca  movsxd  rax, ebx
0x180018ecd  mov     rcx, [r14]
0x180018ed0  lea     rdx, [rbp+57h+String2]; lpString2
0x180018ed4  mov     rcx, [rcx+rax*8]; lpString1
0x180018ed8  call    cs:__imp_lstrcmpiW
0x180018ede  test    eax, eax
0x180018ee0  jz      short loc_180018EE6
0x180018ee2  inc     ebx
0x180018ee4  jmp     short loc_180018EC4
0x180018ee6  cmp     ebx, 0FFFFFFFFh
0x180018ee9  jz      short loc_180018EFA
0x180018eeb  mov     edx, ebx
0x180018eed  mov     rcx, r14
0x180018ef0  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180018ef5  mov     rbx, [rax]
0x180018ef8  jmp     short loc_180018EFD
0x180018efa  mov     rbx, r13
0x180018efd  mov     rcx, r12; lpCriticalSection
0x180018f00  call    cs:__imp_LeaveCriticalSection
0x180018f06  test    rbx, rbx
0x180018f09  jz      short loc_180018F7A
0x180018f0b  mov     [rbp+57h+cb], r13
0x180018f0f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180018f13  inc     r8; int
0x180018f16  cmp     [rbx+r8*2], r13w
0x180018f1b  jnz     short loc_180018F13
0x180018f1d  mov     rdx, rbx; unsigned __int16 *
0x180018f20  lea     rcx, [rbp+57h+var_98]; this
0x180018f24  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180018f29  mov     ebx, eax
0x180018f2b  lea     rcx, [rbp+57h+cb]
0x180018f2f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180018f34  test    ebx, ebx
0x180018f36  jz      loc_180018E5D
0x180018f3c  mov     rax, [rdi]
0x180018f3f  jmp     short loc_180018F4D
0x180018f41  mov     rcx, rax; lpsz
0x180018f44  call    cs:__imp_CharNextW
0x180018f4a  mov     [rdi], rax
0x180018f4d  cmp     rax, rsi
0x180018f50  jnz     short loc_180018F41
0x180018f52  mov     esi, 25h ; '%'
0x180018f57  mov     rcx, [rdi]; lpsz
0x180018f5a  call    cs:__imp_CharNextW
0x180018f60  mov     rbx, rax
0x180018f63  mov     [rdi], rax
0x180018f66  jmp     loc_180018E1F
0x180018f6b  mov     rdx, rbx
0x180018f6e  jmp     loc_180018E46
0x180018f73  mov     ebx, 80004005h
0x180018f78  jmp     short loc_180018F8F
0x180018f7a  mov     ebx, 80020009h
0x180018f7f  jmp     short loc_180018F8F
0x180018f81  mov     ebx, r13d
0x180018f84  mov     rcx, [rbp+57h+pv]
0x180018f88  mov     [rbp+57h+pv], r13
0x180018f8c  mov     [r15], rcx
0x180018f8f  mov     rcx, [rbp+57h+pv]; pv
0x180018f93  call    cs:__imp_CoTaskMemFree
0x180018f99  mov     eax, ebx
0x180018f9b  jmp     short loc_180018FA2
0x180018f9d  mov     eax, 80004003h
0x180018fa2  mov     rcx, [rbp+57h+var_40]
0x180018fa6  xor     rcx, rsp; StackCookie
0x180018fa9  call    __security_check_cookie
0x180018fae  mov     rbx, [rsp+0C0h+arg_8]
0x180018fb6  add     rsp, 90h
0x180018fbd  pop     r15
0x180018fbf  pop     r14
0x180018fc1  pop     r13
0x180018fc3  pop     r12
0x180018fc5  pop     rdi
0x180018fc6  pop     rsi
0x180018fc7  pop     rbp
0x180018fc8  retn
```
