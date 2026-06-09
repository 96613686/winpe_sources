# CDsmDeviceTree::_PurgeTree(void)

- ea: `0x180003ec0`
- end: `0x180004028`
- name: `?_PurgeTree@CDsmDeviceTree@@AEAAXXZ`
- size: `360`
- prototype: `void __fastcall(CDsmDeviceTree *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180002c90`
- `0x180019518`

## callees

- `0x180003ec0`
- `0x180004030`
- `0x1800041c4`
- `0x180016b58`
- `0x180016c18`
- `0x18001b410`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003fa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003fa8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
void __fastcall CDsmDeviceTree::_PurgeTree(CDsmDeviceTree *this)
{
  __int64 i; // rax
  __int64 v3; // rbx
  _QWORD *v4; // rsi
  __int64 *v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rcx
  volatile signed __int32 *v8; // rdx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  __int64 v12; // rdx

  while ( *((_QWORD *)this + 3) )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= *((_DWORD *)this + 8) )
        ATL::AtlThrowImpl(-2147467259);
      v3 = *(_QWORD *)(*((_QWORD *)this + 2) + 8 * i);
      if ( v3 )
        break;
    }
    v4 = *(_QWORD **)(v3 + 8);
    if ( v4 )
    {
      v9 = (void *)v4[3];
      if ( v9 )
        CoTaskMemFree(v9);
      v10 = (void *)v4[2];
      if ( v10 )
        CoTaskMemFree(v10);
      v11 = (void *)v4[1];
      if ( v11 )
        CoTaskMemFree(v11);
      operator delete(v4);
    }
    v5 = (__int64 *)(*((_QWORD *)this + 2) + 8LL * (unsigned int)(*(_DWORD *)(v3 + 24) % *((_DWORD *)this + 8)));
    v6 = *v5;
    if ( v3 == *v5 )
    {
      v6 = 0;
    }
    else
    {
      for ( ; *(_QWORD *)(v6 + 16) != v3; v6 = *(_QWORD *)(v6 + 16) )
        ;
    }
    v7 = *(_QWORD *)(v3 + 16);
    if ( v6 )
      *(_QWORD *)(v6 + 16) = v7;
    else
      *v5 = v7;
    v8 = (volatile signed __int32 *)(*(_QWORD *)v3 - 24LL);
    if ( _InterlockedExchangeAdd(v8 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
    *(_QWORD *)(v3 + 16) = *((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = v3;
    if ( --*((_QWORD *)this + 3) < *((_QWORD *)this + 7) && !*((_DWORD *)this + 16) )
    {
      v12 = (unsigned int)ATL::CAtlMap<_GUID,unsigned int,ATL::CElementTraits<_GUID>,ATL::CElementTraits<unsigned int>>::PickSize((char *)this + 16);
      ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CDeviceTreeElement *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CDeviceTreeElement *>>::Rehash(
        (char *)this + 16,
        v12);
    }
    if ( !*((_QWORD *)this + 3) )
      ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::FreePlexes((char *)this + 16);
  }
  *((_DWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x180003ec0  mov     [rsp+arg_0], rcx
0x180003ec5  push    rbx
0x180003ec6  push    rsi
0x180003ec7  push    rdi
0x180003ec8  push    r14
0x180003eca  sub     rsp, 38h
0x180003ece  mov     r14, rcx
0x180003ed1  cmp     qword ptr [r14+18h], 0
0x180003ed6  jz      loc_180003FCB
0x180003edc  xor     eax, eax
0x180003ede  mov     r8d, [r14+20h]
0x180003ee2  cmp     eax, r8d
0x180003ee5  jnb     loc_180003FFD
0x180003eeb  mov     rcx, [r14+10h]
0x180003eef  mov     rbx, [rcx+rax*8]
0x180003ef3  test    rbx, rbx
0x180003ef6  jnz     short loc_180003EFC
0x180003ef8  inc     eax
0x180003efa  jmp     short loc_180003EE2
0x180003efc  mov     rsi, [rbx+8]
0x180003f00  test    rsi, rsi
0x180003f03  jnz     short loc_180003F81
0x180003f05  xor     edx, edx
0x180003f07  mov     eax, [rbx+18h]
0x180003f0a  div     dword ptr [r14+20h]
0x180003f0e  mov     rax, [r14+10h]
0x180003f12  lea     rdx, [rax+rdx*8]
0x180003f16  mov     rax, [rdx]
0x180003f19  cmp     rbx, rax
0x180003f1c  jnz     loc_180004008
0x180003f22  xor     eax, eax
0x180003f24  mov     rcx, [rbx+10h]
0x180003f28  test    rax, rax
0x180003f2b  jnz     short loc_180003F7B
0x180003f2d  mov     [rdx], rcx
0x180003f30  mov     rdx, [rbx]
0x180003f33  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180003f37  mov     eax, 0FFFFFFFFh
0x180003f3c  lock xadd [rdx+10h], eax
0x180003f41  sub     eax, 1
0x180003f44  jg      short loc_180003F55
0x180003f46  mov     rcx, [rdx]
0x180003f49  mov     rax, [rcx]
0x180003f4c  mov     rax, [rax+8]
0x180003f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f55  mov     rax, [r14+50h]
0x180003f59  mov     [rbx+10h], rax
0x180003f5d  mov     [r14+50h], rbx
0x180003f61  dec     qword ptr [r14+18h]
0x180003f65  mov     rdx, [r14+18h]
0x180003f69  cmp     rdx, [r14+38h]
0x180003f6d  jb      short loc_180003FDD
0x180003f6f  cmp     qword ptr [r14+18h], 0
0x180003f74  jz      short loc_180003FC0
0x180003f76  jmp     loc_180003ED1
0x180003f7b  mov     [rax+10h], rcx
0x180003f7f  jmp     short loc_180003F30
0x180003f81  mov     rcx, [rsi+18h]; pv
0x180003f85  test    rcx, rcx
0x180003f88  jz      short loc_180003F90
0x180003f8a  call    cs:__imp_CoTaskMemFree
0x180003f90  mov     rcx, [rsi+10h]; pv
0x180003f94  test    rcx, rcx
0x180003f97  jz      short loc_180003F9F
0x180003f99  call    cs:__imp_CoTaskMemFree
0x180003f9f  mov     rcx, [rsi+8]; pv
0x180003fa3  test    rcx, rcx
0x180003fa6  jz      short loc_180003FAE
0x180003fa8  call    cs:__imp_CoTaskMemFree
0x180003fae  mov     edx, 28h ; '('
0x180003fb3  mov     rcx, rsi; Block
0x180003fb6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003fbb  jmp     loc_180003F05
0x180003fc0  lea     rcx, [r14+10h]
0x180003fc4  call    ?FreePlexes@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_NV?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@_N@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<bool>>::FreePlexes(void)
0x180003fc9  jmp     short loc_180003F76
0x180003fcb  mov     dword ptr [r14+8], 0
0x180003fd3  add     rsp, 38h
0x180003fd7  pop     r14
0x180003fd9  pop     rdi
0x180003fda  pop     rsi
0x180003fdb  pop     rbx
0x180003fdc  retn
0x180003fdd  cmp     dword ptr [r14+40h], 0
0x180003fe2  jnz     short loc_180003F6F
0x180003fe4  lea     rcx, [r14+10h]
0x180003fe8  call    ?PickSize@?$CAtlMap@U_GUID@@IV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@I@3@@ATL@@AEBAI_K@Z; ATL::CAtlMap<_GUID,uint,ATL::CElementTraits<_GUID>,ATL::CElementTraits<uint>>::PickSize(unsigned __int64)
0x180003fed  mov     edx, eax
0x180003fef  lea     rcx, [r14+10h]
0x180003ff3  call    ?Rehash@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCDeviceTreeElement@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCDeviceTreeElement@@@2@@ATL@@QEAAXI@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CDeviceTreeElement *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CDeviceTreeElement *>>::Rehash(uint)
0x180003ff8  jmp     loc_180003F6F
0x180003ffd  mov     ecx, 80004005h; int
0x180004002  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004008  cmp     [rax+10h], rbx
0x18000400c  jz      loc_180003F24
0x180004012  mov     rax, [rax+10h]
0x180004016  cmp     [rax+10h], rbx
0x18000401a  jnz     short loc_180004012
0x18000401c  jmp     loc_180003F24
0x180004021  mov     r14, [rsp+58h+arg_0]
0x180004026  jmp     short loc_180003FCB
```
