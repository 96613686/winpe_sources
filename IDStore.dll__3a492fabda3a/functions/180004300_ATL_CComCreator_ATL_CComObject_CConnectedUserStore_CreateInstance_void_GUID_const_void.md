# ATL::CComCreator<ATL::CComObject<CConnectedUserStore>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004300`
- end: `0x180004484`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCConnectedUserStore@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `388`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800042e0`

## callees

- `0x18000412c`
- `0x180004300`
- `0x180006230`
- `0x18000f088`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CConnectedUserStore>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // edi
  char *v6; // rax
  char *v7; // rbx
  signed __int32 i; // eax
  int v9; // eax
  signed __int32 j; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  v6 = (char *)operator new(0xC0u);
  v7 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 4) = 0;
    *(_OWORD *)(v6 + 24) = 0;
    *(_OWORD *)(v6 + 40) = 0;
    *((_QWORD *)v6 + 7) = 0;
    v6[64] = 0;
    *((_QWORD *)v6 + 23) = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CConnectedUserStore>::`vftable'{for `IConnectedUserStore2'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CConnectedUserStore>::`vftable'{for `IConnectedUserSite'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v7 = 0;
  }
  if ( v7 )
  {
    for ( i = *((_DWORD *)v7 + 4); i != 0x7FFFFFFF; i = *((_DWORD *)v7 + 4) )
    {
      if ( i == _InterlockedCompareExchange((volatile signed __int32 *)v7 + 4, i + 1, i) )
        break;
    }
    v9 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 24));
    if ( v9 >= 0 )
    {
      v7[64] = 1;
      v9 = CConnectedUserStore::FinalConstruct((CConnectedUserStore *)v7);
    }
    v5 = 0;
    if ( v9 < 0 )
      v5 = v9;
    for ( j = *((_DWORD *)v7 + 4); j != 0x7FFFFFFF; j = *((_DWORD *)v7 + 4) )
    {
      if ( j == _InterlockedCompareExchange((volatile signed __int32 *)v7 + 4, j - 1, j) )
        break;
    }
    if ( v5 || (v5 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v7)(v7, a2, a3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 80LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x180004300  mov     [rsp+arg_10], r8
0x180004305  mov     [rsp+arg_8], rdx
0x18000430a  mov     [rsp+arg_0], rcx
0x18000430f  push    rbx
0x180004310  push    rsi
0x180004311  push    rdi
0x180004312  push    r14
0x180004314  push    r15
0x180004316  sub     rsp, 20h
0x18000431a  mov     rsi, r8
0x18000431d  mov     r15, rdx
0x180004320  test    r8, r8
0x180004323  jz      loc_180004428
0x180004329  xor     r14d, r14d
0x18000432c  mov     [r8], r14
0x18000432f  mov     edi, 8007000Eh
0x180004334  mov     dword ptr [rsp+48h+arg_0], edi
0x180004338  mov     [rsp+48h+arg_18], r14
0x18000433d  mov     ecx, 0C0h; Size
0x180004342  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004347  mov     rbx, rax
0x18000434a  test    rax, rax
0x18000434d  jz      loc_18000440D
0x180004353  mov     [rax+10h], r14d
0x180004357  xorps   xmm0, xmm0
0x18000435a  xor     eax, eax
0x18000435c  movups  xmmword ptr [rbx+18h], xmm0
0x180004360  movups  xmmword ptr [rbx+28h], xmm0
0x180004364  mov     [rbx+38h], rax
0x180004368  mov     [rbx+40h], al
0x18000436b  mov     [rbx+0B8h], r14
0x180004372  lea     rax, ??_7?$CComObject@VCConnectedUserStore@@@ATL@@6BIConnectedUserStore2@@@; const ATL::CComObject<CConnectedUserStore>::`vftable'{for `IConnectedUserStore2'}
0x180004379  mov     [rbx], rax
0x18000437c  lea     rax, ??_7?$CComObject@VCConnectedUserStore@@@ATL@@6BIConnectedUserSite@@@; const ATL::CComObject<CConnectedUserStore>::`vftable'{for `IConnectedUserSite'}
0x180004383  mov     [rbx+8], rax
0x180004387  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000438e  mov     rax, [rcx]
0x180004391  mov     rax, [rax+8]
0x180004395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000439a  mov     [rsp+48h+arg_18], rbx
0x18000439f  test    rbx, rbx
0x1800043a2  jz      short loc_1800043FF
0x1800043a4  mov     eax, [rbx+10h]
0x1800043a7  cmp     eax, 7FFFFFFFh
0x1800043ac  jnz     loc_18000444A
0x1800043b2  lea     rcx, [rbx+18h]; this
0x1800043b6  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800043bb  test    eax, eax
0x1800043bd  js      short loc_1800043CB
0x1800043bf  mov     byte ptr [rbx+40h], 1
0x1800043c3  mov     rcx, rbx; this
0x1800043c6  call    ?FinalConstruct@CConnectedUserStore@@QEAAJXZ; CConnectedUserStore::FinalConstruct(void)
0x1800043cb  mov     edi, r14d
0x1800043ce  test    eax, eax
0x1800043d0  cmovs   edi, eax
0x1800043d3  mov     eax, [rbx+10h]
0x1800043d6  cmp     eax, 7FFFFFFFh
0x1800043db  jnz     loc_180004467
0x1800043e1  test    edi, edi
0x1800043e3  jnz     short loc_180004412
0x1800043e5  mov     rax, [rbx]
0x1800043e8  mov     r8, rsi
0x1800043eb  mov     rdx, r15
0x1800043ee  mov     rcx, rbx
0x1800043f1  mov     rax, [rax]
0x1800043f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043f9  mov     edi, eax
0x1800043fb  test    eax, eax
0x1800043fd  jnz     short loc_180004412
0x1800043ff  mov     eax, edi
0x180004401  add     rsp, 20h
0x180004405  pop     r15
0x180004407  pop     r14
0x180004409  pop     rdi
0x18000440a  pop     rsi
0x18000440b  pop     rbx
0x18000440c  retn
0x18000440d  mov     rbx, r14
0x180004410  jmp     short loc_18000439A
0x180004412  mov     rcx, [rbx]
0x180004415  mov     rax, [rcx+50h]
0x180004419  mov     edx, 1
0x18000441e  mov     rcx, rbx
0x180004421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004426  jmp     short loc_1800043FF
0x180004428  mov     eax, 80004003h
0x18000442d  jmp     short loc_180004401
0x18000442f  xor     r14d, r14d
0x180004432  mov     rsi, [rsp+48h+arg_10]
0x180004437  mov     r15, [rsp+48h+arg_8]
0x18000443c  mov     edi, dword ptr [rsp+48h+arg_0]
0x180004440  mov     rbx, [rsp+48h+arg_18]
0x180004445  jmp     loc_18000439F
0x18000444a  lea     ecx, [rax+1]
0x18000444d  lock cmpxchg [rbx+10h], ecx
0x180004452  jz      loc_1800043B2
0x180004458  mov     eax, [rbx+10h]
0x18000445b  cmp     eax, 7FFFFFFFh
0x180004460  jnz     short loc_18000444A
0x180004462  jmp     loc_1800043B2
0x180004467  lea     ecx, [rax-1]
0x18000446a  lock cmpxchg [rbx+10h], ecx
0x18000446f  jz      loc_1800043E1
0x180004475  mov     eax, [rbx+10h]
0x180004478  cmp     eax, 7FFFFFFFh
0x18000447d  jnz     short loc_180004467
0x18000447f  jmp     loc_1800043E1
```
