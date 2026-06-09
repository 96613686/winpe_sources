# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)

- ea: `0x14000f1d0`
- end: `0x14000f361`
- name: `?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ`
- size: `401`
- prototype: `__int64(_QWORD *, const wchar_t *, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000f098`

## callees

- `0x1400027c4`
- `0x140002b4c`
- `0x140002e00`
- `0x140002e64`
- `0x140002e74`
- `0x14000f1d0`
- `0x140014c70`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf_s` at `0x14000f2e8`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf_s` at `0x14000f2e8`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x14000f22d`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x14000f22d`

## pseudocode

```c
__int64 ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        _QWORD *a1,
        const wchar_t *a2,
        ...)
{
  __int64 v4; // rbp
  unsigned __int64 *v5; // r14
  int v6; // esi
  __int64 v7; // rcx
  __int64 v8; // rax
  struct ATL::IAtlStringMgr *Instance; // rax
  unsigned int v10; // ebx
  wchar_t *v11; // rdx
  __int64 result; // rax
  wchar_t *Format; // [rsp+30h] [rbp-58h] BYREF
  va_list va; // [rsp+A0h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( !a2 )
    ATL::AtlThrowImpl(-2147024809);
  v4 = *(int *)(*a1 - 16LL);
  v5 = _local_stdio_printf_options();
  v6 = __stdio_common_vswprintf(*v5 | 6, 0, 0, a2, 0, va);
  if ( v6 < 0 )
    v6 = -1;
  if ( v6 < 0 )
    ATL::AtlThrowImpl(-2147467259);
  _mm_lfence();
  Format = 0;
  v7 = *(_QWORD *)(*a1 - 24LL);
  if ( !v7 || (v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 32LL))(v7)) == 0 )
  {
    Instance = ATL::CAtlStringMgr::GetInstance();
    v8 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 32LL))(Instance);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &Format,
    a2,
    v8);
  v10 = v6 + v4;
  if ( v6 + (int)v4 < 0 )
    goto LABEL_16;
  _mm_lfence();
  if ( (((*(_DWORD *)(*a1 - 12LL) - v10) | (1 - *(_DWORD *)(*a1 - 8LL))) & 0x80000000) != 0 )
  {
    _mm_lfence();
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v10);
  }
  __stdio_common_vswprintf_s(*v5 | 4, (wchar_t *)(*a1 + 2 * v4), v6 + 1, Format, 0, va);
  if ( (signed int)v10 > *(_DWORD *)(*a1 - 12LL) )
LABEL_16:
    ATL::AtlThrowImpl(-2147024809);
  *(_DWORD *)(*a1 - 16LL) = v10;
  *(_WORD *)(*a1 + 2LL * (int)v10) = 0;
  v11 = Format - 12;
  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)Format - 2);
  if ( (int)result <= 0 )
  {
    _mm_lfence();
    return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
  }
  return result;
}

```

## disassembly

```asm
0x14000f1d0  mov     rax, rsp
0x14000f1d3  mov     [rax+10h], rdx
0x14000f1d7  mov     [rax+18h], r8
0x14000f1db  mov     [rax+20h], r9
0x14000f1df  push    rbx
0x14000f1e0  push    rbp
0x14000f1e1  push    rsi
0x14000f1e2  push    rdi
0x14000f1e3  push    r12
0x14000f1e5  push    r13
0x14000f1e7  push    r14
0x14000f1e9  push    r15
0x14000f1eb  sub     rsp, 48h
0x14000f1ef  mov     rbx, rdx
0x14000f1f2  mov     rdi, rcx
0x14000f1f5  lea     r13, [rax+18h]
0x14000f1f9  xor     r15d, r15d
0x14000f1fc  test    rdx, rdx
0x14000f1ff  jz      loc_14000F356
0x14000f205  mov     rax, [rcx]
0x14000f208  movsxd  rbp, dword ptr [rax-10h]
0x14000f20c  call    __local_stdio_printf_options
0x14000f211  mov     r14, rax
0x14000f214  mov     rcx, [rax]
0x14000f217  or      rcx, 6; Options
0x14000f21b  mov     [rsp+88h+ArgList], r13; ArgList
0x14000f220  mov     [rsp+88h+Locale], r15; Locale
0x14000f225  mov     r9, rbx; Format
0x14000f228  xor     r8d, r8d; BufferCount
0x14000f22b  xor     edx, edx; Buffer
0x14000f22d  call    cs:__imp___stdio_common_vswprintf
0x14000f233  mov     esi, eax
0x14000f235  or      r12d, 0FFFFFFFFh
0x14000f239  test    eax, eax
0x14000f23b  cmovs   esi, r12d
0x14000f23f  test    esi, esi
0x14000f241  js      loc_14000F340
0x14000f247  lfence
0x14000f24a  mov     [rsp+88h+Format], r15
0x14000f24f  mov     rax, [rdi]
0x14000f252  mov     rcx, [rax-18h]
0x14000f256  test    rcx, rcx
0x14000f259  jz      short loc_14000F26D
0x14000f25b  mov     rax, [rcx]
0x14000f25e  mov     rax, [rax+20h]
0x14000f262  call    cs:__guard_dispatch_icall_fptr
0x14000f268  test    rax, rax
0x14000f26b  jnz     short loc_14000F285
0x14000f26d  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14000f272  mov     r8, rax
0x14000f275  mov     rcx, [rax]
0x14000f278  mov     rax, [rcx+20h]
0x14000f27c  mov     rcx, r8
0x14000f27f  call    cs:__guard_dispatch_icall_fptr
0x14000f285  mov     r8, rax
0x14000f288  mov     rdx, rbx
0x14000f28b  lea     rcx, [rsp+88h+Format]
0x14000f290  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGPEAUIAtlStringMgr@1@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,ATL::IAtlStringMgr *)
0x14000f295  nop
0x14000f296  lea     ebx, [rsi+rbp]
0x14000f299  test    ebx, ebx
0x14000f29b  js      loc_14000F34B
0x14000f2a1  lfence
0x14000f2a4  mov     rax, [rdi]
0x14000f2a7  mov     edx, 1
0x14000f2ac  sub     edx, [rax-8]
0x14000f2af  mov     ecx, [rax-0Ch]
0x14000f2b2  sub     ecx, ebx
0x14000f2b4  or      edx, ecx
0x14000f2b6  jge     short loc_14000F2C5
0x14000f2b8  lfence
0x14000f2bb  mov     edx, ebx
0x14000f2bd  mov     rcx, rdi
0x14000f2c0  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14000f2c5  lea     eax, [rsi+1]
0x14000f2c8  movsxd  r8, eax; BufferCount
0x14000f2cb  mov     rax, [rdi]
0x14000f2ce  lea     rdx, [rax+rbp*2]; Buffer
0x14000f2d2  mov     rcx, [r14]
0x14000f2d5  or      rcx, 4; Options
0x14000f2d9  mov     [rsp+88h+ArgList], r13; ArgList
0x14000f2de  mov     [rsp+88h+Locale], r15; Locale
0x14000f2e3  mov     r9, [rsp+88h+Format]; Format
0x14000f2e8  call    cs:__imp___stdio_common_vswprintf_s
0x14000f2ee  mov     rax, [rdi]
0x14000f2f1  cmp     ebx, [rax-0Ch]
0x14000f2f4  jg      short loc_14000F34B
0x14000f2f6  mov     [rax-10h], ebx
0x14000f2f9  movsxd  rcx, ebx
0x14000f2fc  mov     rax, [rdi]
0x14000f2ff  mov     [rax+rcx*2], r15w
0x14000f304  mov     rdx, [rsp+88h+Format]
0x14000f309  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000f30d  mov     eax, r12d
0x14000f310  lock xadd [rdx+10h], eax
0x14000f315  add     eax, r12d
0x14000f318  test    eax, eax
0x14000f31a  jg      short loc_14000F32F
0x14000f31c  lfence
0x14000f31f  mov     rcx, [rdx]
0x14000f322  mov     rax, [rcx]
0x14000f325  mov     rax, [rax+8]
0x14000f329  call    cs:__guard_dispatch_icall_fptr
0x14000f32f  add     rsp, 48h
0x14000f333  pop     r15
0x14000f335  pop     r14
0x14000f337  pop     r13
0x14000f339  pop     r12
0x14000f33b  pop     rdi
0x14000f33c  pop     rsi
0x14000f33d  pop     rbp
0x14000f33e  pop     rbx
0x14000f33f  retn
0x14000f340  mov     ecx, 80004005h; int
0x14000f345  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000f34b  mov     ecx, 80070057h; int
0x14000f350  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000f356  mov     ecx, 80070057h; int
0x14000f35b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
