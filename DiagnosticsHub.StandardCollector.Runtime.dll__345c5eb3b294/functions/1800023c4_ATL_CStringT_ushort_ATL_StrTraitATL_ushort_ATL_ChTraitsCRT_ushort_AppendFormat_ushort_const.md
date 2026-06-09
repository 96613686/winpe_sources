# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)

- ea: `0x1800023c4`
- end: `0x18000259f`
- name: `?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ`
- size: `475`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `15`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180001460`
- `0x180004298`
- `0x180005530`
- `0x18000b150`
- `0x18001b320`
- `0x18001c3b0`
- `0x18001fbec`
- `0x180020004`
- `0x180020338`
- `0x18002a80c`
- `0x18002d780`
- `0x18002dfd0`
- `0x180032470`
- `0x180037eb4`
- `0x180044198`

## callees

- `0x180001f70`
- `0x1800020bc`
- `0x180002354`
- `0x1800023b8`
- `0x1800023c4`
- `0x180002604`
- `0x18000288c`
- `0x18004b640`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf_s` at `0x18000252b`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf_s` at `0x18000252b`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x180002421`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x180002421`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800024b5`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800024b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        _QWORD *a1,
        const wchar_t *a2,
        ...)
{
  __int64 v4; // rbp
  unsigned __int64 *v5; // r15
  int v6; // r14d
  __int64 v7; // rcx
  __int64 v8; // rcx
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v10; // r8
  unsigned int v11; // eax
  unsigned int v12; // edi
  wchar_t *v13; // rbx
  __int64 result; // rax
  wchar_t *Format[11]; // [rsp+30h] [rbp-58h] BYREF
  __int64 ArgList; // [rsp+A0h] [rbp+18h] BYREF
  va_list va; // [rsp+A0h] [rbp+18h]
  va_list va1; // [rsp+A8h] [rbp+20h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  ArgList = va_arg(va1, _QWORD);
  if ( !a2 )
    ATL::AtlThrowImpl(-2147024809);
  v4 = *(int *)(*a1 - 16LL);
  v5 = _local_stdio_printf_options();
  v6 = __stdio_common_vswprintf(*v5 | 6, 0, 0, a2, 0, va);
  if ( v6 < 0 )
    v6 = -1;
  if ( v6 < 0
    || ((v7 = *(_QWORD *)(*a1 - 24LL)) == 0
     || (v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 32LL))(v7)) == 0)
    && (Instance = ATL::CAtlStringMgr::GetInstance(),
        (v8 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 32LL))(Instance)) == 0) )
  {
    ATL::AtlThrowImpl(-2147467259);
  }
  _mm_lfence();
  Format[0] = (wchar_t *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8) + 24);
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           Format,
                           a2) )
  {
    _mm_lfence();
    _mm_lfence();
    v11 = wcslen(a2);
    ATL::CSimpleStringT<unsigned short,0>::SetString(Format, a2, v11);
  }
  v12 = v6 + v4;
  if ( v6 + (int)v4 < 0 )
    goto LABEL_17;
  _mm_lfence();
  if ( (((*(_DWORD *)(*a1 - 12LL) - v12) | (1 - *(_DWORD *)(*a1 - 8LL))) & 0x80000000) != 0 )
  {
    _mm_lfence();
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v12, v10);
  }
  v13 = Format[0];
  __stdio_common_vswprintf_s(*v5 | 4, (wchar_t *)(*a1 + 2 * v4), v6 + 1, Format[0], 0, va);
  if ( (signed int)v12 > *(_DWORD *)(*a1 - 12LL) )
LABEL_17:
    ATL::AtlThrowImpl(-2147024809);
  *(_DWORD *)(*a1 - 16LL) = v12;
  *(_WORD *)(*a1 + 2LL * (int)v12) = 0;
  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)v13 - 2);
  if ( (int)result <= 0 )
  {
    _mm_lfence();
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v13 - 3) + 8LL))(*((_QWORD *)v13 - 3));
  }
  return result;
}

```

## disassembly

```asm
0x1800023c4  mov     rax, rsp
0x1800023c7  mov     [rax+10h], rdx
0x1800023cb  mov     [rax+18h], r8
0x1800023cf  mov     [rax+20h], r9
0x1800023d3  push    rbx
0x1800023d4  push    rbp
0x1800023d5  push    rsi
0x1800023d6  push    rdi
0x1800023d7  push    r12
0x1800023d9  push    r13
0x1800023db  push    r14
0x1800023dd  push    r15
0x1800023df  sub     rsp, 48h
0x1800023e3  mov     rbx, rdx
0x1800023e6  mov     rsi, rcx
0x1800023e9  lea     rdi, [rax+18h]
0x1800023ed  xor     r12d, r12d
0x1800023f0  test    rdx, rdx
0x1800023f3  jz      loc_180002594
0x1800023f9  mov     rax, [rcx]
0x1800023fc  movsxd  rbp, dword ptr [rax-10h]
0x180002400  call    __local_stdio_printf_options
0x180002405  mov     r15, rax
0x180002408  mov     rcx, [rax]
0x18000240b  or      rcx, 6; Options
0x18000240f  mov     [rsp+88h+ArgList], rdi; ArgList
0x180002414  mov     [rsp+88h+Locale], r12; Locale
0x180002419  mov     r9, rbx; Format
0x18000241c  xor     r8d, r8d; BufferCount
0x18000241f  xor     edx, edx; Buffer
0x180002421  call    cs:__imp___stdio_common_vswprintf
0x180002427  mov     r14d, eax
0x18000242a  or      r13d, 0FFFFFFFFh
0x18000242e  test    eax, eax
0x180002430  cmovs   r14d, r13d
0x180002434  test    r14d, r14d
0x180002437  js      loc_180002589
0x18000243d  mov     rcx, [rsi]
0x180002440  mov     rcx, [rcx-18h]
0x180002444  test    rcx, rcx
0x180002447  jz      short loc_18000245E
0x180002449  mov     rax, [rcx]
0x18000244c  mov     rax, [rax+20h]
0x180002450  call    cs:__guard_dispatch_icall_fptr
0x180002456  mov     rcx, rax
0x180002459  test    rax, rax
0x18000245c  jnz     short loc_180002482
0x18000245e  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x180002463  mov     rdx, rax
0x180002466  mov     rcx, [rax]
0x180002469  mov     rax, [rcx+20h]
0x18000246d  mov     rcx, rdx
0x180002470  call    cs:__guard_dispatch_icall_fptr
0x180002476  mov     rcx, rax
0x180002479  test    rax, rax
0x18000247c  jz      loc_180002589
0x180002482  lfence
0x180002485  mov     rax, [rcx]
0x180002488  mov     rax, [rax+18h]
0x18000248c  call    cs:__guard_dispatch_icall_fptr
0x180002492  add     rax, 18h
0x180002496  mov     [rsp+88h+Format], rax
0x18000249b  mov     rdx, rbx
0x18000249e  lea     rcx, [rsp+88h+Format]
0x1800024a3  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1800024a8  test    al, al
0x1800024aa  jnz     short loc_1800024CC
0x1800024ac  lfence
0x1800024af  lfence
0x1800024b2  mov     rcx, rbx; String
0x1800024b5  call    cs:__imp_wcslen
0x1800024bb  mov     r8d, eax
0x1800024be  mov     rdx, rbx
0x1800024c1  lea     rcx, [rsp+88h+Format]
0x1800024c6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800024cb  nop
0x1800024cc  lea     edi, [r14+rbp]
0x1800024d0  test    edi, edi
0x1800024d2  js      loc_18000257E
0x1800024d8  lfence
0x1800024db  mov     rax, [rsi]
0x1800024de  mov     edx, 1
0x1800024e3  sub     edx, [rax-8]
0x1800024e6  mov     ecx, [rax-0Ch]
0x1800024e9  sub     ecx, edi
0x1800024eb  or      edx, ecx
0x1800024ed  jge     short loc_1800024FC
0x1800024ef  lfence
0x1800024f2  mov     edx, edi
0x1800024f4  mov     rcx, rsi
0x1800024f7  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800024fc  lea     eax, [r14+1]
0x180002500  movsxd  r8, eax; BufferCount
0x180002503  mov     rax, [rsi]
0x180002506  lea     rdx, [rax+rbp*2]; Buffer
0x18000250a  mov     rcx, [r15]
0x18000250d  or      rcx, 4; Options
0x180002511  lea     rax, [rsp+88h+arg_10]
0x180002519  mov     [rsp+88h+ArgList], rax; ArgList
0x18000251e  mov     [rsp+88h+Locale], r12; Locale
0x180002523  mov     rbx, [rsp+88h+Format]
0x180002528  mov     r9, rbx; Format
0x18000252b  call    cs:__imp___stdio_common_vswprintf_s
0x180002531  mov     rax, [rsi]
0x180002534  cmp     edi, [rax-0Ch]
0x180002537  jg      short loc_18000257E
0x180002539  mov     [rax-10h], edi
0x18000253c  movsxd  rcx, edi
0x18000253f  mov     rax, [rsi]
0x180002542  mov     [rax+rcx*2], r12w
0x180002547  lea     rdx, [rbx-18h]
0x18000254b  mov     eax, r13d
0x18000254e  lock xadd [rdx+10h], eax
0x180002553  add     eax, r13d
0x180002556  test    eax, eax
0x180002558  jg      short loc_18000256D
0x18000255a  lfence
0x18000255d  mov     rcx, [rdx]
0x180002560  mov     rax, [rcx]
0x180002563  mov     rax, [rax+8]
0x180002567  call    cs:__guard_dispatch_icall_fptr
0x18000256d  add     rsp, 48h
0x180002571  pop     r15
0x180002573  pop     r14
0x180002575  pop     r13
0x180002577  pop     r12
0x180002579  pop     rdi
0x18000257a  pop     rsi
0x18000257b  pop     rbp
0x18000257c  pop     rbx
0x18000257d  retn
0x18000257e  mov     ecx, 80070057h; int
0x180002583  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002589  mov     ecx, 80004005h; int
0x18000258e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002594  mov     ecx, 80070057h; int
0x180002599  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
