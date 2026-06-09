# ATL::CComCreator<ATL::CComObject<CImageTranscode>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180018888`
- end: `0x18001898f`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCImageTranscode@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018860`

## callees

- `0x180002800`
- `0x180018888`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800188cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800188cc`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CImageTranscode>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // eax
  int v10; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = LocalAlloc(0x40u, 0x40u);
  v8 = v7;
  if ( v7 )
  {
    v7[2] = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_BYTE *)v7 + 56) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CImageTranscode>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    v9 = ATL::CComSafeDeleteCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v8 + 4));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180018888  mov     [rsp+arg_10], r8
0x18001888d  mov     [rsp+arg_8], rdx
0x180018892  mov     [rsp+arg_0], rcx
0x180018897  push    rbx
0x180018898  push    rsi
0x180018899  push    rdi
0x18001889a  push    r14
0x18001889c  sub     rsp, 28h
0x1800188a0  mov     rsi, r8
0x1800188a3  mov     r14, rdx
0x1800188a6  test    r8, r8
0x1800188a9  jnz     short loc_1800188B5
0x1800188ab  mov     eax, 80004003h
0x1800188b0  jmp     loc_180018985
0x1800188b5  mov     qword ptr [r8], 0
0x1800188bc  mov     edi, 8007000Eh
0x1800188c1  mov     dword ptr [rsp+48h+arg_0], edi
0x1800188c5  mov     ecx, 40h ; '@'; uFlags
0x1800188ca  mov     edx, ecx; uBytes
0x1800188cc  call    cs:__imp_LocalAlloc
0x1800188d2  mov     rbx, rax
0x1800188d5  mov     [rsp+48h+arg_18], rax
0x1800188da  test    rax, rax
0x1800188dd  jz      short loc_180018919
0x1800188df  mov     dword ptr [rax+8], 0
0x1800188e6  xorps   xmm0, xmm0
0x1800188e9  xor     eax, eax
0x1800188eb  movups  xmmword ptr [rbx+10h], xmm0
0x1800188ef  movups  xmmword ptr [rbx+20h], xmm0
0x1800188f3  mov     [rbx+30h], rax
0x1800188f7  mov     [rbx+38h], al
0x1800188fa  lea     rax, ??_7?$CComObject@VCImageTranscode@@@ATL@@6B@; const ATL::CComObject<CImageTranscode>::`vftable'
0x180018901  mov     [rbx], rax
0x180018904  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001890b  mov     rax, [rcx]
0x18001890e  mov     rax, [rax+8]
0x180018912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018917  jmp     short loc_18001891B
0x180018919  xor     ebx, ebx
0x18001891b  mov     [rsp+48h+arg_18], rbx
0x180018920  jmp     short loc_180018935
0x180018922  mov     rsi, [rsp+48h+arg_10]
0x180018927  mov     r14, [rsp+48h+arg_8]
0x18001892c  mov     edi, dword ptr [rsp+48h+arg_0]
0x180018930  mov     rbx, [rsp+48h+arg_18]
0x180018935  test    rbx, rbx
0x180018938  jz      short loc_180018983
0x18001893a  lea     rcx, [rbx+10h]; this
0x18001893e  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180018943  xor     ecx, ecx
0x180018945  test    eax, eax
0x180018947  cmovs   ecx, eax
0x18001894a  xor     edi, edi
0x18001894c  test    ecx, ecx
0x18001894e  cmovs   edi, ecx
0x180018951  test    edi, edi
0x180018953  jnz     short loc_18001896F
0x180018955  mov     rax, [rbx]
0x180018958  mov     r8, rsi
0x18001895b  mov     rdx, r14
0x18001895e  mov     rcx, rbx
0x180018961  mov     rax, [rax]
0x180018964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018969  mov     edi, eax
0x18001896b  test    eax, eax
0x18001896d  jz      short loc_180018983
0x18001896f  mov     rdx, [rbx]
0x180018972  mov     rax, [rdx+20h]
0x180018976  mov     edx, 1
0x18001897b  mov     rcx, rbx
0x18001897e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018983  mov     eax, edi
0x180018985  add     rsp, 28h
0x180018989  pop     r14
0x18001898b  pop     rdi
0x18001898c  pop     rsi
0x18001898d  pop     rbx
0x18001898e  retn
```
