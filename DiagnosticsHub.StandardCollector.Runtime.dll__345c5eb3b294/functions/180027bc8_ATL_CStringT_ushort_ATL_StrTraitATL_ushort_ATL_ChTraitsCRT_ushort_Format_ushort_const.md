# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)

- ea: `0x180027bc8`
- end: `0x180027d7b`
- name: `?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ`
- size: `435`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `8`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001fbec`
- `0x180038f48`
- `0x18003b264`
- `0x18003c180`
- `0x180040e40`
- `0x18004106c`
- `0x1800412ac`
- `0x180047e0c`

## callees

- `0x180001f70`
- `0x1800020bc`
- `0x180002354`
- `0x1800023b8`
- `0x180002604`
- `0x18000288c`
- `0x180027bc8`
- `0x18004b640`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf_s` at `0x180027d0a`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf_s` at `0x180027d0a`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x180027c1b`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x180027c1b`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180027cad`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180027cad`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        wchar_t **a1,
        const wchar_t *a2,
        ...)
{
  unsigned __int64 *v4; // r14
  int v5; // edi
  __int64 v6; // rcx
  __int64 v7; // rcx
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v9; // r8
  unsigned int v10; // eax
  wchar_t *v11; // rbx
  __int64 result; // rax
  wchar_t *Format[9]; // [rsp+30h] [rbp-48h] BYREF
  __int64 ArgList; // [rsp+90h] [rbp+18h] BYREF
  va_list va; // [rsp+90h] [rbp+18h]
  va_list va1; // [rsp+98h] [rbp+20h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  ArgList = va_arg(va1, _QWORD);
  if ( !a2 )
    ATL::AtlThrowImpl(-2147024809);
  v4 = _local_stdio_printf_options();
  v5 = __stdio_common_vswprintf(*v4 | 6, 0, 0, a2, 0, va);
  if ( v5 < 0 )
    v5 = -1;
  if ( v5 < 0
    || ((v6 = *((_QWORD *)*a1 - 3)) == 0 || (v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))(v6)) == 0)
    && (Instance = ATL::CAtlStringMgr::GetInstance(),
        (v7 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 32LL))(Instance)) == 0) )
  {
    ATL::AtlThrowImpl(-2147467259);
  }
  _mm_lfence();
  Format[0] = (wchar_t *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7) + 24);
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           Format,
                           a2) )
  {
    _mm_lfence();
    _mm_lfence();
    v10 = wcslen(a2);
    ATL::CSimpleStringT<unsigned short,0>::SetString(Format, a2, v10);
  }
  _mm_lfence();
  if ( ((*((_DWORD *)*a1 - 3) - v5) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
  {
    _mm_lfence();
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v5, v9);
  }
  v11 = Format[0];
  __stdio_common_vswprintf_s(*v4 | 4, *a1, v5 + 1, Format[0], 0, va);
  if ( v5 > *((_DWORD *)*a1 - 3) )
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)*a1 - 4) = v5;
  (*a1)[v5] = 0;
  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)v11 - 2);
  if ( (int)result <= 0 )
  {
    _mm_lfence();
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
  }
  return result;
}

```

## disassembly

```asm
0x180027bc8  mov     rax, rsp
0x180027bcb  mov     [rax+10h], rdx
0x180027bcf  mov     [rax+18h], r8
0x180027bd3  mov     [rax+20h], r9
0x180027bd7  push    rbx
0x180027bd8  push    rbp
0x180027bd9  push    rsi
0x180027bda  push    rdi
0x180027bdb  push    r12
0x180027bdd  push    r14
0x180027bdf  push    r15
0x180027be1  sub     rsp, 40h
0x180027be5  mov     rbx, rdx
0x180027be8  mov     rsi, rcx
0x180027beb  lea     r12, [rax+18h]
0x180027bef  xor     ebp, ebp
0x180027bf1  test    rdx, rdx
0x180027bf4  jz      loc_180027D70
0x180027bfa  call    __local_stdio_printf_options
0x180027bff  mov     r14, rax
0x180027c02  mov     rcx, [rax]
0x180027c05  or      rcx, 6; Options
0x180027c09  mov     [rsp+78h+ArgList], r12; ArgList
0x180027c0e  mov     [rsp+78h+Locale], rbp; Locale
0x180027c13  mov     r9, rbx; Format
0x180027c16  xor     r8d, r8d; BufferCount
0x180027c19  xor     edx, edx; Buffer
0x180027c1b  call    cs:__imp___stdio_common_vswprintf
0x180027c21  mov     edi, eax
0x180027c23  or      r15d, 0FFFFFFFFh
0x180027c27  test    eax, eax
0x180027c29  cmovs   edi, r15d
0x180027c2d  test    edi, edi
0x180027c2f  js      loc_180027D65
0x180027c35  mov     rcx, [rsi]
0x180027c38  mov     rcx, [rcx-18h]
0x180027c3c  test    rcx, rcx
0x180027c3f  jz      short loc_180027C56
0x180027c41  mov     rax, [rcx]
0x180027c44  mov     rax, [rax+20h]
0x180027c48  call    cs:__guard_dispatch_icall_fptr
0x180027c4e  mov     rcx, rax
0x180027c51  test    rax, rax
0x180027c54  jnz     short loc_180027C7A
0x180027c56  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x180027c5b  mov     rdx, rax
0x180027c5e  mov     rcx, [rax]
0x180027c61  mov     rax, [rcx+20h]
0x180027c65  mov     rcx, rdx
0x180027c68  call    cs:__guard_dispatch_icall_fptr
0x180027c6e  mov     rcx, rax
0x180027c71  test    rax, rax
0x180027c74  jz      loc_180027D65
0x180027c7a  lfence
0x180027c7d  mov     rax, [rcx]
0x180027c80  mov     rax, [rax+18h]
0x180027c84  call    cs:__guard_dispatch_icall_fptr
0x180027c8a  add     rax, 18h
0x180027c8e  mov     [rsp+78h+Format], rax
0x180027c93  mov     rdx, rbx
0x180027c96  lea     rcx, [rsp+78h+Format]
0x180027c9b  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x180027ca0  test    al, al
0x180027ca2  jnz     short loc_180027CC4
0x180027ca4  lfence
0x180027ca7  lfence
0x180027caa  mov     rcx, rbx; String
0x180027cad  call    cs:__imp_wcslen
0x180027cb3  mov     r8d, eax
0x180027cb6  mov     rdx, rbx
0x180027cb9  lea     rcx, [rsp+78h+Format]
0x180027cbe  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180027cc3  nop
0x180027cc4  lfence
0x180027cc7  mov     rax, [rsi]
0x180027cca  mov     edx, 1
0x180027ccf  sub     edx, [rax-8]
0x180027cd2  mov     ecx, [rax-0Ch]
0x180027cd5  sub     ecx, edi
0x180027cd7  or      edx, ecx
0x180027cd9  jge     short loc_180027CE8
0x180027cdb  lfence
0x180027cde  mov     edx, edi
0x180027ce0  mov     rcx, rsi
0x180027ce3  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180027ce8  lea     eax, [rdi+1]
0x180027ceb  movsxd  r8, eax; BufferCount
0x180027cee  mov     rcx, [r14]
0x180027cf1  or      rcx, 4; Options
0x180027cf5  mov     [rsp+78h+ArgList], r12; ArgList
0x180027cfa  mov     [rsp+78h+Locale], rbp; Locale
0x180027cff  mov     rbx, [rsp+78h+Format]
0x180027d04  mov     r9, rbx; Format
0x180027d07  mov     rdx, [rsi]; Buffer
0x180027d0a  call    cs:__imp___stdio_common_vswprintf_s
0x180027d10  mov     rax, [rsi]
0x180027d13  cmp     edi, [rax-0Ch]
0x180027d16  jg      short loc_180027D5A
0x180027d18  mov     [rax-10h], edi
0x180027d1b  movsxd  rcx, edi
0x180027d1e  mov     rax, [rsi]
0x180027d21  mov     [rax+rcx*2], bp
0x180027d25  lea     rdx, [rbx-18h]
0x180027d29  mov     eax, r15d
0x180027d2c  lock xadd [rdx+10h], eax
0x180027d31  add     eax, r15d
0x180027d34  test    eax, eax
0x180027d36  jg      short loc_180027D4B
0x180027d38  lfence
0x180027d3b  mov     rcx, [rdx]
0x180027d3e  mov     rax, [rcx]
0x180027d41  mov     rax, [rax+8]
0x180027d45  call    cs:__guard_dispatch_icall_fptr
0x180027d4b  add     rsp, 40h
0x180027d4f  pop     r15
0x180027d51  pop     r14
0x180027d53  pop     r12
0x180027d55  pop     rdi
0x180027d56  pop     rsi
0x180027d57  pop     rbp
0x180027d58  pop     rbx
0x180027d59  retn
0x180027d5a  mov     ecx, 80070057h; int
0x180027d5f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180027d65  mov     ecx, 80004005h; int
0x180027d6a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180027d70  mov     ecx, 80070057h; int
0x180027d75  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
