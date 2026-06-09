# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18001ff5c`
- end: `0x18002019c`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `576`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800202fc`

## callees

- `0x18001ea30`
- `0x18001ec8c`
- `0x18001f588`
- `0x18001f664`
- `0x18001fc60`
- `0x18001ff5c`
- `0x180021794`
- `0x1800582e0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18002007c`
- `msvcrt!wcsncpy_s` at `0x18002007c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ffe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020166`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ffe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020166`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001fff9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001fff9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002002c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020105`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002012e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002002c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020105`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002012e`
- `KERNEL32!lstrcmpiW` at `0x1800200a9`
- `KERNEL32!lstrcmpiW` at `0x1800200a9`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, LPVOID *a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // rdx
  _WORD *v8; // rax
  LPWSTR v10; // rax
  const unsigned __int16 *v11; // rdx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rsi
  __int64 v14; // rcx
  errno_t v15; // eax
  LPCWSTR v16; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v18; // rdx
  __int64 v19; // r8
  int v20; // ebx
  const WCHAR *j; // rax
  unsigned int v22; // ebx
  SIZE_T cb; // [rsp+20h] [rbp-49h] BYREF
  _DWORD v24[2]; // [rsp+28h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-39h]
  wchar_t Destination[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  v7 = (unsigned int)(2 * v6);
  v24[0] = 0;
  LODWORD(cb) = 0;
  if ( (int)v7 < 100 )
    v7 = 1000;
  v24[1] = v7;
  if ( (int)ATL::AtlMultiply<unsigned long>(&cb, v7, 2) < 0 )
  {
    v8 = 0;
LABEL_9:
    CoTaskMemFree(v8);
    return 2147942414LL;
  }
  v8 = CoTaskMemAlloc((unsigned int)cb);
  pv = v8;
  if ( !v8 )
    goto LABEL_9;
  *v8 = 0;
  for ( *this = v4; ; *this = v4 )
  {
    if ( !*v4 )
    {
      v22 = 0;
      *a3 = pv;
      pv = 0;
      goto LABEL_38;
    }
    if ( *v4 == 37 )
      break;
    v11 = v4;
LABEL_32:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v11, 1) )
    {
LABEL_36:
      v22 = -2147024882;
      goto LABEL_38;
    }
LABEL_33:
    v4 = CharNextW(*this);
  }
  v10 = CharNextW(v4);
  *this = v10;
  if ( *v10 == 37 )
  {
    v11 = v10;
    goto LABEL_32;
  }
  v12 = ATL::CRegParser::StrChrW(v10, 0x25u);
  v13 = v12;
  if ( v12 )
  {
    v14 = v12 - *this;
    if ( v14 > 31 )
    {
      v22 = -2147467259;
      goto LABEL_38;
    }
    v15 = wcsncpy_s(Destination, 0x20u, *this, (int)v14);
    ATL::AtlCrtErrorCheck(v15);
    v16 = this[1];
    for ( i = 0; (signed int)i < *((_DWORD *)v16 + 6); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v16 + 1) + 8LL * (int)i), Destination) )
      {
        if ( i == -1 )
          break;
        v18 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                            v16 + 4,
                                            i);
        if ( !v18 )
          break;
        cb = 0;
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        v20 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v18, v19);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&cb);
        if ( v20 )
        {
          for ( j = *this; j != v13; *this = j )
            j = CharNextW(j);
          goto LABEL_33;
        }
        goto LABEL_36;
      }
    }
  }
  v22 = -2147352567;
LABEL_38:
  CoTaskMemFree(pv);
  return v22;
}

```

## disassembly

```asm
0x18001ff5c  mov     [rsp-8+arg_8], rbx
0x18001ff61  push    rbp
0x18001ff62  push    rsi
0x18001ff63  push    rdi
0x18001ff64  push    r12
0x18001ff66  push    r13
0x18001ff68  push    r14
0x18001ff6a  push    r15
0x18001ff6c  lea     rbp, [rsp-27h]
0x18001ff71  sub     rsp, 90h
0x18001ff78  mov     rax, cs:__security_cookie
0x18001ff7f  xor     rax, rsp
0x18001ff82  mov     [rbp+57h+var_40], rax
0x18001ff86  xor     r12d, r12d
0x18001ff89  mov     r15, r8
0x18001ff8c  mov     rbx, rdx
0x18001ff8f  mov     rdi, rcx
0x18001ff92  test    rdx, rdx
0x18001ff95  jz      loc_180020170
0x18001ff9b  test    r8, r8
0x18001ff9e  jz      loc_180020170
0x18001ffa4  mov     [r8], r12
0x18001ffa7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001ffab  inc     rdx
0x18001ffae  cmp     [rbx+rdx*2], r12w
0x18001ffb3  jnz     short loc_18001FFAB
0x18001ffb5  add     edx, edx
0x18001ffb7  mov     [rbp+57h+var_98], r12d
0x18001ffbb  mov     eax, 3E8h
0x18001ffc0  mov     dword ptr [rbp+57h+cb], r12d
0x18001ffc4  cmp     edx, 64h ; 'd'
0x18001ffc7  lea     rcx, [rbp+57h+cb]
0x18001ffcb  mov     r8d, 2
0x18001ffd1  cmovl   edx, eax
0x18001ffd4  mov     [rbp+57h+var_94], edx
0x18001ffd7  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18001ffdc  test    eax, eax
0x18001ffde  jns     short loc_18001FFF6
0x18001ffe0  mov     rax, r12
0x18001ffe3  mov     rcx, rax; pv
0x18001ffe6  call    cs:__imp_CoTaskMemFree
0x18001ffec  mov     eax, 8007000Eh
0x18001fff1  jmp     loc_180020175
0x18001fff6  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18001fff9  call    cs:__imp_CoTaskMemAlloc
0x18001ffff  mov     [rbp+57h+pv], rax
0x180020003  test    rax, rax
0x180020006  jz      short loc_18001FFE3
0x180020008  mov     [rax], r12w
0x18002000c  mov     r13d, 25h ; '%'
0x180020012  mov     [rdi], rbx
0x180020015  cmp     [rbx], r12w
0x180020019  jz      loc_180020154
0x18002001f  cmp     [rbx], r13w
0x180020023  jnz     loc_180020115
0x180020029  mov     rcx, rbx; lpsz
0x18002002c  call    cs:__imp_CharNextW
0x180020032  mov     [rdi], rax
0x180020035  cmp     [rax], r13w
0x180020039  jnz     short loc_180020043
0x18002003b  mov     rdx, rax
0x18002003e  jmp     loc_180020118
0x180020043  mov     edx, r13d; unsigned __int16
0x180020046  mov     rcx, rax; lpsz
0x180020049  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18002004e  mov     rsi, rax
0x180020051  test    rax, rax
0x180020054  jz      loc_180020146
0x18002005a  mov     rcx, rax
0x18002005d  sub     rcx, [rdi]
0x180020060  sar     rcx, 1
0x180020063  cmp     rcx, 1Fh
0x180020067  jg      loc_18002013F
0x18002006d  mov     r8, [rdi]; Source
0x180020070  mov     edx, 20h ; ' '; SizeInWords
0x180020075  movsxd  r9, ecx; MaxCount
0x180020078  lea     rcx, [rbp+57h+Destination]; Destination
0x18002007c  call    cs:__imp_wcsncpy_s
0x180020082  mov     ecx, eax; int
0x180020084  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180020089  mov     r14, [rdi+8]
0x18002008d  mov     ebx, r12d
0x180020090  cmp     ebx, [r14+18h]
0x180020094  jge     loc_180020146
0x18002009a  mov     rcx, [r14+8]
0x18002009e  lea     rdx, [rbp+57h+Destination]; lpString2
0x1800200a2  movsxd  rax, ebx
0x1800200a5  mov     rcx, [rcx+rax*8]; lpString1
0x1800200a9  call    cs:__imp_lstrcmpiW
0x1800200af  test    eax, eax
0x1800200b1  jz      short loc_1800200B7
0x1800200b3  inc     ebx
0x1800200b5  jmp     short loc_180020090
0x1800200b7  cmp     ebx, 0FFFFFFFFh
0x1800200ba  jz      loc_180020146
0x1800200c0  mov     edx, ebx
0x1800200c2  lea     rcx, [r14+8]
0x1800200c6  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1800200cb  mov     rdx, [rax]; unsigned __int16 *
0x1800200ce  test    rdx, rdx
0x1800200d1  jz      short loc_180020146
0x1800200d3  mov     [rbp+57h+cb], r12
0x1800200d7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800200db  inc     r8; int
0x1800200de  cmp     [rdx+r8*2], r12w
0x1800200e3  jnz     short loc_1800200DB
0x1800200e5  lea     rcx, [rbp+57h+var_98]; this
0x1800200e9  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800200ee  lea     rcx, [rbp+57h+cb]
0x1800200f2  mov     ebx, eax
0x1800200f4  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800200f9  test    ebx, ebx
0x1800200fb  jz      short loc_18002014D
0x1800200fd  mov     rax, [rdi]
0x180020100  jmp     short loc_18002010E
0x180020102  mov     rcx, rax; lpsz
0x180020105  call    cs:__imp_CharNextW
0x18002010b  mov     [rdi], rax
0x18002010e  cmp     rax, rsi
0x180020111  jnz     short loc_180020102
0x180020113  jmp     short loc_18002012B
0x180020115  mov     rdx, rbx; unsigned __int16 *
0x180020118  mov     r8d, 1; int
0x18002011e  lea     rcx, [rbp+57h+var_98]; this
0x180020122  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180020127  test    eax, eax
0x180020129  jz      short loc_18002014D
0x18002012b  mov     rcx, [rdi]; lpsz
0x18002012e  call    cs:__imp_CharNextW
0x180020134  mov     rbx, rax
0x180020137  mov     [rdi], rax
0x18002013a  jmp     loc_180020015
0x18002013f  mov     ebx, 80004005h
0x180020144  jmp     short loc_180020162
0x180020146  mov     ebx, 80020009h
0x18002014b  jmp     short loc_180020162
0x18002014d  mov     ebx, 8007000Eh
0x180020152  jmp     short loc_180020162
0x180020154  mov     rcx, [rbp+57h+pv]
0x180020158  mov     ebx, r12d
0x18002015b  mov     [r15], rcx
0x18002015e  mov     [rbp+57h+pv], r12
0x180020162  mov     rcx, [rbp+57h+pv]; pv
0x180020166  call    cs:__imp_CoTaskMemFree
0x18002016c  mov     eax, ebx
0x18002016e  jmp     short loc_180020175
0x180020170  mov     eax, 80004003h
0x180020175  mov     rcx, [rbp+57h+var_40]
0x180020179  xor     rcx, rsp; StackCookie
0x18002017c  call    __security_check_cookie
0x180020181  mov     rbx, [rsp+0C0h+arg_8]
0x180020189  add     rsp, 90h
0x180020190  pop     r15
0x180020192  pop     r14
0x180020194  pop     r13
0x180020196  pop     r12
0x180020198  pop     rdi
0x180020199  pop     rsi
0x18002019a  pop     rbp
0x18002019b  retn
```
