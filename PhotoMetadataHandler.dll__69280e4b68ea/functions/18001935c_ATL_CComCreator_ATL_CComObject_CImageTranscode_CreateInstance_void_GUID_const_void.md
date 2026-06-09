# ATL::CComCreator<ATL::CComObject<CImageTranscode>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001935c`
- end: `0x18001946a`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCImageTranscode@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019330`

## callees

- `0x180002920`
- `0x18001935c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800193a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800193a0`

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
0x18001935c  mov     [rsp+arg_10], r8
0x180019361  mov     [rsp+arg_8], rdx
0x180019366  mov     [rsp+arg_0], rcx
0x18001936b  push    rbx
0x18001936c  push    rsi
0x18001936d  push    rdi
0x18001936e  push    r14
0x180019370  sub     rsp, 28h
0x180019374  mov     rsi, r8
0x180019377  mov     r14, rdx
0x18001937a  test    r8, r8
0x18001937d  jnz     short loc_180019389
0x18001937f  mov     eax, 80004003h
0x180019384  jmp     loc_18001945F
0x180019389  mov     qword ptr [r8], 0
0x180019390  mov     edi, 8007000Eh
0x180019395  mov     dword ptr [rsp+48h+arg_0], edi
0x180019399  mov     ecx, 40h ; '@'; uFlags
0x18001939e  mov     edx, ecx; uBytes
0x1800193a0  call    cs:__imp_LocalAlloc
0x1800193a7  nop     dword ptr [rax+rax+00h]
0x1800193ac  mov     rbx, rax
0x1800193af  mov     [rsp+48h+arg_18], rax
0x1800193b4  test    rax, rax
0x1800193b7  jz      short loc_1800193F3
0x1800193b9  mov     dword ptr [rax+8], 0
0x1800193c0  xorps   xmm0, xmm0
0x1800193c3  xor     eax, eax
0x1800193c5  movups  xmmword ptr [rbx+10h], xmm0
0x1800193c9  movups  xmmword ptr [rbx+20h], xmm0
0x1800193cd  mov     [rbx+30h], rax
0x1800193d1  mov     [rbx+38h], al
0x1800193d4  lea     rax, ??_7?$CComObject@VCImageTranscode@@@ATL@@6B@; const ATL::CComObject<CImageTranscode>::`vftable'
0x1800193db  mov     [rbx], rax
0x1800193de  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800193e5  mov     rax, [rcx]
0x1800193e8  mov     rax, [rax+8]
0x1800193ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193f1  jmp     short loc_1800193F5
0x1800193f3  xor     ebx, ebx
0x1800193f5  mov     [rsp+48h+arg_18], rbx
0x1800193fa  jmp     short loc_18001940F
0x1800193fc  mov     rsi, [rsp+48h+arg_10]
0x180019401  mov     r14, [rsp+48h+arg_8]
0x180019406  mov     edi, dword ptr [rsp+48h+arg_0]
0x18001940a  mov     rbx, [rsp+48h+arg_18]
0x18001940f  test    rbx, rbx
0x180019412  jz      short loc_18001945D
0x180019414  lea     rcx, [rbx+10h]; this
0x180019418  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001941d  xor     ecx, ecx
0x18001941f  test    eax, eax
0x180019421  cmovs   ecx, eax
0x180019424  xor     edi, edi
0x180019426  test    ecx, ecx
0x180019428  cmovs   edi, ecx
0x18001942b  test    edi, edi
0x18001942d  jnz     short loc_180019449
0x18001942f  mov     rax, [rbx]
0x180019432  mov     r8, rsi
0x180019435  mov     rdx, r14
0x180019438  mov     rcx, rbx
0x18001943b  mov     rax, [rax]
0x18001943e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019443  mov     edi, eax
0x180019445  test    eax, eax
0x180019447  jz      short loc_18001945D
0x180019449  mov     rdx, [rbx]
0x18001944c  mov     rax, [rdx+20h]
0x180019450  mov     edx, 1
0x180019455  mov     rcx, rbx
0x180019458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001945d  mov     eax, edi
0x18001945f  add     rsp, 28h
0x180019463  pop     r14
0x180019465  pop     rdi
0x180019466  pop     rsi
0x180019467  pop     rbx
0x180019468  retn
```
