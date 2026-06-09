# SavedStateRepository::GetNode(ushort const *,tagVARIANT &)

- ea: `0x1401eb320`
- end: `0x1401eb5ce`
- name: `?GetNode@SavedStateRepository@@UEBAJPEBGAEAUtagVARIANT@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(SavedStateRepository *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1401eb5d4`

## callees

- `0x140031c88`
- `0x140132940`
- `0x1401eb320`
- `0x1401eb900`
- `0x1402c2010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1401eb53d`
- `OLEAUT32!__imp_SysAllocString` at `0x1401eb53d`
- `OLEAUT32!__imp_SysStringLen` at `0x1401eb550`
- `OLEAUT32!__imp_SysStringLen` at `0x1401eb550`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1401eb409`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1401eb409`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1401eb470`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1401eb470`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401eb430`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401eb430`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401eb454`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401eb454`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SavedStateRepository::GetNode(
        SavedStateRepository *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  int v6; // eax
  int Array; // ebx
  SAFEARRAY *v8; // rax
  SAFEARRAY *v9; // rsi
  SHORT v10; // ax
  const OLECHAR *v11; // rcx
  OLECHAR *v12; // rax
  VARTYPE v14[2]; // [rsp+20h] [rbp-40h] BYREF
  unsigned int v15; // [rsp+24h] [rbp-3Ch] BYREF
  void *ppvData; // [rsp+28h] [rbp-38h] BYREF
  OLECHAR *psz[2]; // [rsp+30h] [rbp-30h] BYREF
  __m128i si128; // [rsp+40h] [rbp-20h]
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp-10h] BYREF

  v6 = *((_DWORD *)this + 32);
  if ( (v6 & 1) == 0 && (v6 & 0xFFFFFFFC) == 0 )
    return (unsigned int)-2147418113;
  v14[0] = 0;
  Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, VARTYPE *))(**((_QWORD **)this + 13) + 176LL))(
            *((_QWORD *)this + 13),
            a2,
            v14);
  if ( Array < 0 )
    return (unsigned int)Array;
  if ( v14[0] == 5 )
  {
    ppvData = 0;
    Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, void **))(**((_QWORD **)this + 13) + 120LL))(
              *((_QWORD *)this + 13),
              a2,
              &ppvData);
    if ( Array < 0 )
      return (unsigned int)Array;
    a3->llVal = (LONGLONG)ppvData;
    goto LABEL_32;
  }
  if ( v14[0] != 8 )
  {
    switch ( v14[0] )
    {
      case 0xBu:
        v15 = 0;
        Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 13)
                                                                                            + 104LL))(
                  *((_QWORD *)this + 13),
                  a2,
                  &v15);
        if ( Array < 0 )
          return (unsigned int)Array;
        if ( v15 )
          v10 = -1;
        else
          v10 = 0;
        a3->iVal = v10;
        break;
      case 0x14u:
        ppvData = 0;
        Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, void **))(**((_QWORD **)this + 13) + 80LL))(
                  *((_QWORD *)this + 13),
                  a2,
                  &ppvData);
        if ( Array < 0 )
          return (unsigned int)Array;
        a3->llVal = (LONGLONG)ppvData;
        break;
      case 0x2011u:
        v15 = 0;
        Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 13)
                                                                                            + 160LL))(
                  *((_QWORD *)this + 13),
                  a2,
                  &v15);
        if ( Array < 0 )
          return (unsigned int)Array;
        rgsabound.cElements = v15;
        rgsabound.lLbound = 0;
        v8 = SafeArrayCreate(0x11u, 1u, &rgsabound);
        v9 = v8;
        if ( v8 )
        {
          ppvData = 0;
          SafeArrayAccessData(v8, &ppvData);
          Array = SavedStateRepository::ReadArray(this, a2, ppvData, v15);
          SafeArrayUnaccessData(v9);
          if ( Array < 0 )
          {
            SafeArrayDestroy(v9);
            return (unsigned int)Array;
          }
          a3->llVal = (LONGLONG)v9;
        }
        break;
      default:
        return (unsigned int)-2147024809;
    }
LABEL_32:
    a3->vt = v14[0];
    return (unsigned int)Array;
  }
  *(_OWORD *)psz = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(psz[0]) = 0;
  Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, OLECHAR **))(**((_QWORD **)this + 13) + 136LL))(
            *((_QWORD *)this + 13),
            a2,
            psz);
  if ( Array >= 0 )
  {
    v11 = (const OLECHAR *)psz;
    if ( si128.m128i_i64[1] > 7uLL )
      v11 = psz[0];
    v12 = SysAllocString(v11);
    a3->llVal = (LONGLONG)v12;
    if ( !SysStringLen(v12) )
      Array = -2147024882;
  }
  std::wstring::_Tidy_deallocate(psz);
  if ( Array >= 0 )
    goto LABEL_32;
  return (unsigned int)Array;
}

```

## disassembly

```asm
0x1401eb320  mov     [rsp-28h+arg_18], rbx
0x1401eb325  push    rbp
0x1401eb326  push    rsi
0x1401eb327  push    rdi
0x1401eb328  push    r14
0x1401eb32a  push    r15
0x1401eb32c  mov     rbp, rsp
0x1401eb32f  sub     rsp, 60h
0x1401eb333  mov     rax, cs:__security_cookie
0x1401eb33a  xor     rax, rsp
0x1401eb33d  mov     [rbp+var_8], rax
0x1401eb341  mov     rdi, r8
0x1401eb344  mov     r15, rdx
0x1401eb347  mov     r14, rcx
0x1401eb34a  mov     eax, [rcx+80h]
0x1401eb350  test    al, 1
0x1401eb352  jnz     short loc_1401EB365
0x1401eb354  test    eax, 0FFFFFFFCh
0x1401eb359  ja      short loc_1401EB365
0x1401eb35b  mov     ebx, 8000FFFFh
0x1401eb360  jmp     loc_1401EB5AB
0x1401eb365  xor     eax, eax
0x1401eb367  mov     [rbp+var_40], ax
0x1401eb36b  mov     rcx, [rcx+68h]
0x1401eb36f  mov     rax, [rcx]
0x1401eb372  lea     r8, [rbp+var_40]
0x1401eb376  mov     rax, [rax+0B0h]
0x1401eb37d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401eb382  mov     ebx, eax
0x1401eb384  test    eax, eax
0x1401eb386  js      loc_1401EB5AB
0x1401eb38c  movzx   eax, [rbp+var_40]
0x1401eb390  cmp     eax, 5
0x1401eb393  jz      loc_1401EB575
0x1401eb399  cmp     eax, 8
0x1401eb39c  jz      loc_1401EB4F5
0x1401eb3a2  cmp     eax, 0Bh
0x1401eb3a5  jz      loc_1401EB4B7
0x1401eb3ab  cmp     eax, 14h
0x1401eb3ae  jz      loc_1401EB481
0x1401eb3b4  cmp     eax, 2011h
0x1401eb3b9  jz      short loc_1401EB3C5
0x1401eb3bb  mov     ebx, 80070057h
0x1401eb3c0  jmp     loc_1401EB5AB
0x1401eb3c5  mov     [rbp+var_3C], 0
0x1401eb3cc  mov     rcx, [r14+68h]
0x1401eb3d0  mov     rax, [rcx]
0x1401eb3d3  lea     r8, [rbp+var_3C]
0x1401eb3d7  mov     rdx, r15
0x1401eb3da  mov     rax, [rax+0A0h]
0x1401eb3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401eb3e6  mov     ebx, eax
0x1401eb3e8  test    eax, eax
0x1401eb3ea  js      loc_1401EB5AB
0x1401eb3f0  mov     eax, [rbp+var_3C]
0x1401eb3f3  mov     [rbp+rgsabound.cElements], eax
0x1401eb3f6  mov     [rbp+rgsabound.lLbound], 0
0x1401eb3fd  mov     ecx, 11h; vt
0x1401eb402  lea     r8, [rbp+rgsabound]; rgsabound
0x1401eb406  lea     edx, [rcx-10h]; cDims
0x1401eb409  call    cs:__imp_SafeArrayCreate
0x1401eb410  nop     dword ptr [rax+rax+00h]
0x1401eb415  mov     rsi, rax
0x1401eb418  test    rax, rax
0x1401eb41b  jz      loc_1401EB5A4
0x1401eb421  mov     [rbp+ppvData], 0
0x1401eb429  lea     rdx, [rbp+ppvData]; ppvData
0x1401eb42d  mov     rcx, rax; psa
0x1401eb430  call    cs:__imp_SafeArrayAccessData
0x1401eb437  nop     dword ptr [rax+rax+00h]
0x1401eb43c  mov     r9d, [rbp+var_3C]; unsigned int
0x1401eb440  mov     r8, [rbp+ppvData]; void *
0x1401eb444  mov     rdx, r15; unsigned __int16 *
0x1401eb447  mov     rcx, r14; this
0x1401eb44a  call    ?ReadArray@SavedStateRepository@@UEBAJPEBGPEAXI@Z; SavedStateRepository::ReadArray(ushort const *,void *,uint)
0x1401eb44f  mov     ebx, eax
0x1401eb451  mov     rcx, rsi; psa
0x1401eb454  call    cs:__imp_SafeArrayUnaccessData
0x1401eb45b  nop     dword ptr [rax+rax+00h]
0x1401eb460  test    ebx, ebx
0x1401eb462  js      short loc_1401EB46D
0x1401eb464  mov     [rdi+8], rsi
0x1401eb468  jmp     loc_1401EB5A4
0x1401eb46d  mov     rcx, rsi; psa
0x1401eb470  call    cs:__imp_SafeArrayDestroy
0x1401eb477  nop     dword ptr [rax+rax+00h]
0x1401eb47c  jmp     loc_1401EB5AB
0x1401eb481  mov     [rbp+ppvData], 0
0x1401eb489  mov     rcx, [r14+68h]
0x1401eb48d  mov     rax, [rcx]
0x1401eb490  lea     r8, [rbp+ppvData]
0x1401eb494  mov     rdx, r15
0x1401eb497  mov     rax, [rax+50h]
0x1401eb49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401eb4a0  mov     ebx, eax
0x1401eb4a2  test    eax, eax
0x1401eb4a4  js      loc_1401EB5AB
0x1401eb4aa  mov     rax, [rbp+ppvData]
0x1401eb4ae  mov     [rdi+8], rax
0x1401eb4b2  jmp     loc_1401EB5A4
0x1401eb4b7  mov     [rbp+var_3C], 0
0x1401eb4be  mov     rcx, [r14+68h]
0x1401eb4c2  mov     rax, [rcx]
0x1401eb4c5  lea     r8, [rbp+var_3C]
0x1401eb4c9  mov     rdx, r15
0x1401eb4cc  mov     rax, [rax+68h]
0x1401eb4d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401eb4d5  mov     ebx, eax
0x1401eb4d7  test    eax, eax
0x1401eb4d9  js      loc_1401EB5AB
0x1401eb4df  cmp     [rbp+var_3C], 0
0x1401eb4e3  jz      short loc_1401EB4EA
0x1401eb4e5  or      eax, 0FFFFFFFFh
0x1401eb4e8  jmp     short loc_1401EB4EC
0x1401eb4ea  xor     eax, eax
0x1401eb4ec  mov     [rdi+8], ax
0x1401eb4f0  jmp     loc_1401EB5A4
0x1401eb4f5  xorps   xmm0, xmm0
0x1401eb4f8  movups  xmmword ptr [rbp+psz], xmm0
0x1401eb4fc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1401eb504  movdqu  [rbp+var_20], xmm1
0x1401eb509  xor     eax, eax
0x1401eb50b  mov     word ptr [rbp+psz], ax
0x1401eb50f  mov     rcx, [r14+68h]
0x1401eb513  mov     rax, [rcx]
0x1401eb516  lea     r8, [rbp+psz]
0x1401eb51a  mov     rdx, r15
0x1401eb51d  mov     rax, [rax+88h]
0x1401eb524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401eb529  mov     ebx, eax
0x1401eb52b  test    eax, eax
0x1401eb52d  js      short loc_1401EB566
0x1401eb52f  lea     rcx, [rbp+psz]
0x1401eb533  cmp     qword ptr [rbp+var_20+8], 7
0x1401eb538  cmova   rcx, [rbp+psz]; psz
0x1401eb53d  call    cs:__imp_SysAllocString
0x1401eb544  nop     dword ptr [rax+rax+00h]
0x1401eb549  mov     [rdi+8], rax
0x1401eb54d  mov     rcx, rax; pbstr
0x1401eb550  call    cs:__imp_SysStringLen
0x1401eb557  nop     dword ptr [rax+rax+00h]
0x1401eb55c  mov     ecx, 8007000Eh
0x1401eb561  test    eax, eax
0x1401eb563  cmovz   ebx, ecx
0x1401eb566  lea     rcx, [rbp+psz]
0x1401eb56a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1401eb56f  test    ebx, ebx
0x1401eb571  js      short loc_1401EB5AB
0x1401eb573  jmp     short loc_1401EB5A4
0x1401eb575  xorps   xmm0, xmm0
0x1401eb578  movsd   [rbp+ppvData], xmm0
0x1401eb57d  mov     rcx, [r14+68h]
0x1401eb581  mov     rax, [rcx]
0x1401eb584  lea     r8, [rbp+ppvData]
0x1401eb588  mov     rdx, r15
0x1401eb58b  mov     rax, [rax+78h]
0x1401eb58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401eb594  mov     ebx, eax
0x1401eb596  test    eax, eax
0x1401eb598  js      short loc_1401EB5AB
0x1401eb59a  movsd   xmm0, [rbp+ppvData]
0x1401eb59f  movsd   qword ptr [rdi+8], xmm0
0x1401eb5a4  movzx   eax, [rbp+var_40]
0x1401eb5a8  mov     [rdi], ax
0x1401eb5ab  mov     eax, ebx
0x1401eb5ad  mov     rcx, [rbp+var_8]
0x1401eb5b1  xor     rcx, rsp; StackCookie
0x1401eb5b4  call    __security_check_cookie
0x1401eb5b9  mov     rbx, [rsp+60h+arg_18]
0x1401eb5c1  add     rsp, 60h
0x1401eb5c5  pop     r15
0x1401eb5c7  pop     r14
0x1401eb5c9  pop     rdi
0x1401eb5ca  pop     rsi
0x1401eb5cb  pop     rbp
0x1401eb5cc  retn
```
