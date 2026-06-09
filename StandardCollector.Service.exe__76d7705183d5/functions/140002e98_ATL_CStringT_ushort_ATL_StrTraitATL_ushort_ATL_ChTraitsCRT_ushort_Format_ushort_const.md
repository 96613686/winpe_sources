# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)

- ea: `0x140002e98`
- end: `0x14000300d`
- name: `?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ`
- size: `373`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140001388`

## callees

- `0x1400027c4`
- `0x140002b4c`
- `0x140002e00`
- `0x140002e64`
- `0x140002e74`
- `0x140002e98`
- `0x140014c70`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf_s` at `0x140002f97`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf_s` at `0x140002f97`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x140002eeb`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x140002eeb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        wchar_t **a1,
        const wchar_t *a2,
        ...)
{
  unsigned __int64 *v4; // r14
  int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rax
  struct ATL::IAtlStringMgr *Instance; // rax
  wchar_t *v9; // rdx
  __int64 result; // rax
  wchar_t *Format; // [rsp+30h] [rbp-48h] BYREF
  va_list va; // [rsp+90h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( !a2 )
    ATL::AtlThrowImpl(-2147024809);
  v4 = _local_stdio_printf_options();
  v5 = __stdio_common_vswprintf(*v4 | 6, 0, 0, a2, 0, va);
  if ( v5 < 0 )
    v5 = -1;
  if ( v5 < 0 )
    ATL::AtlThrowImpl(-2147467259);
  _mm_lfence();
  Format = 0;
  v6 = *((_QWORD *)*a1 - 3);
  if ( !v6 || (v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))(v6)) == 0 )
  {
    Instance = ATL::CAtlStringMgr::GetInstance();
    v7 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 32LL))(Instance);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &Format,
    a2,
    v7);
  _mm_lfence();
  if ( ((*((_DWORD *)*a1 - 3) - v5) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
  {
    _mm_lfence();
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v5);
  }
  __stdio_common_vswprintf_s(*v4 | 4, *a1, v5 + 1, Format, 0, va);
  if ( v5 > *((_DWORD *)*a1 - 3) )
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)*a1 - 4) = v5;
  (*a1)[v5] = 0;
  v9 = Format - 12;
  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)Format - 2);
  if ( (int)result <= 0 )
  {
    _mm_lfence();
    return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9);
  }
  return result;
}

```

## disassembly

```asm
0x140002e98  mov     rax, rsp
0x140002e9b  mov     [rax+10h], rdx
0x140002e9f  mov     [rax+18h], r8
0x140002ea3  mov     [rax+20h], r9
0x140002ea7  push    rbx
0x140002ea8  push    rbp
0x140002ea9  push    rsi
0x140002eaa  push    rdi
0x140002eab  push    r12
0x140002ead  push    r14
0x140002eaf  push    r15
0x140002eb1  sub     rsp, 40h
0x140002eb5  mov     rsi, rdx
0x140002eb8  mov     rdi, rcx
0x140002ebb  lea     r12, [rax+18h]
0x140002ebf  xor     ebp, ebp
0x140002ec1  test    rdx, rdx
0x140002ec4  jz      loc_140003002
0x140002eca  call    __local_stdio_printf_options
0x140002ecf  mov     r14, rax
0x140002ed2  mov     rcx, [rax]
0x140002ed5  or      rcx, 6; Options
0x140002ed9  mov     [rsp+78h+ArgList], r12; ArgList
0x140002ede  mov     [rsp+78h+Locale], rbp; Locale
0x140002ee3  mov     r9, rsi; Format
0x140002ee6  xor     r8d, r8d; BufferCount
0x140002ee9  xor     edx, edx; Buffer
0x140002eeb  call    cs:__imp___stdio_common_vswprintf
0x140002ef1  mov     ebx, eax
0x140002ef3  or      r15d, 0FFFFFFFFh
0x140002ef7  test    eax, eax
0x140002ef9  cmovs   ebx, r15d
0x140002efd  test    ebx, ebx
0x140002eff  js      loc_140002FEC
0x140002f05  lfence
0x140002f08  mov     [rsp+78h+Format], rbp
0x140002f0d  mov     rax, [rdi]
0x140002f10  mov     rcx, [rax-18h]
0x140002f14  test    rcx, rcx
0x140002f17  jz      short loc_140002F2B
0x140002f19  mov     rax, [rcx]
0x140002f1c  mov     rax, [rax+20h]
0x140002f20  call    cs:__guard_dispatch_icall_fptr
0x140002f26  test    rax, rax
0x140002f29  jnz     short loc_140002F43
0x140002f2b  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140002f30  mov     r8, rax
0x140002f33  mov     rcx, [rax]
0x140002f36  mov     rax, [rcx+20h]
0x140002f3a  mov     rcx, r8
0x140002f3d  call    cs:__guard_dispatch_icall_fptr
0x140002f43  mov     r8, rax
0x140002f46  mov     rdx, rsi
0x140002f49  lea     rcx, [rsp+78h+Format]
0x140002f4e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGPEAUIAtlStringMgr@1@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,ATL::IAtlStringMgr *)
0x140002f53  nop
0x140002f54  lfence
0x140002f57  mov     rax, [rdi]
0x140002f5a  mov     edx, 1
0x140002f5f  sub     edx, [rax-8]
0x140002f62  mov     ecx, [rax-0Ch]
0x140002f65  sub     ecx, ebx
0x140002f67  or      edx, ecx
0x140002f69  jge     short loc_140002F78
0x140002f6b  lfence
0x140002f6e  mov     edx, ebx
0x140002f70  mov     rcx, rdi
0x140002f73  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140002f78  lea     eax, [rbx+1]
0x140002f7b  movsxd  r8, eax; BufferCount
0x140002f7e  mov     rcx, [r14]
0x140002f81  or      rcx, 4; Options
0x140002f85  mov     [rsp+78h+ArgList], r12; ArgList
0x140002f8a  mov     [rsp+78h+Locale], rbp; Locale
0x140002f8f  mov     r9, [rsp+78h+Format]; Format
0x140002f94  mov     rdx, [rdi]; Buffer
0x140002f97  call    cs:__imp___stdio_common_vswprintf_s
0x140002f9d  mov     rax, [rdi]
0x140002fa0  cmp     ebx, [rax-0Ch]
0x140002fa3  jg      short loc_140002FF7
0x140002fa5  mov     [rax-10h], ebx
0x140002fa8  movsxd  rcx, ebx
0x140002fab  mov     rax, [rdi]
0x140002fae  mov     [rax+rcx*2], bp
0x140002fb2  mov     rdx, [rsp+78h+Format]
0x140002fb7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140002fbb  mov     eax, r15d
0x140002fbe  lock xadd [rdx+10h], eax
0x140002fc3  add     eax, r15d
0x140002fc6  test    eax, eax
0x140002fc8  jg      short loc_140002FDD
0x140002fca  lfence
0x140002fcd  mov     rcx, [rdx]
0x140002fd0  mov     rax, [rcx]
0x140002fd3  mov     rax, [rax+8]
0x140002fd7  call    cs:__guard_dispatch_icall_fptr
0x140002fdd  add     rsp, 40h
0x140002fe1  pop     r15
0x140002fe3  pop     r14
0x140002fe5  pop     r12
0x140002fe7  pop     rdi
0x140002fe8  pop     rsi
0x140002fe9  pop     rbp
0x140002fea  pop     rbx
0x140002feb  retn
0x140002fec  mov     ecx, 80004005h; int
0x140002ff1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140002ff7  mov     ecx, 80070057h; int
0x140002ffc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140003002  mov     ecx, 80070057h; int
0x140003007  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
