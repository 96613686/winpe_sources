# DIS11::DIS11Keywords::Parse(ushort const *)

- ea: `0x180021fac`
- end: `0x180022223`
- name: `?Parse@DIS11Keywords@DIS11@@AEAAJPEBG@Z`
- size: `631`
- prototype: `__int64 __fastcall(DIS11::DIS11Keywords *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001fa00`

## callees

- `0x180008b54`
- `0x18000b90c`
- `0x18000c048`
- `0x18000c458`
- `0x1800108a4`
- `0x1800147f8`
- `0x1800217c8`
- `0x180021a4c`
- `0x180021a98`
- `0x180021fac`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021fdc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180022016`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021fdc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180022016`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800220bb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800220bb`
- `OLEAUT32!__imp_SysAllocString` at `0x18002216c`
- `OLEAUT32!__imp_SysAllocString` at `0x18002216c`
- `OLEAUT32!__imp_VariantClear` at `0x180022154`
- `OLEAUT32!__imp_VariantClear` at `0x1800221be`
- `OLEAUT32!__imp_VariantClear` at `0x180022154`
- `OLEAUT32!__imp_VariantClear` at `0x1800221be`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DIS11::DIS11Keywords::Parse(DIS11::DIS11Keywords *this, const unsigned __int16 *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  signed __int32 v6; // eax
  HRESULT v7; // edi
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // rcx
  OLECHAR *v12; // rdi
  VARIANTARG pvarg; // [rsp+30h] [rbp-39h] BYREF
  VARIANTARG v14; // [rsp+50h] [rbp-19h] BYREF
  void **v15; // [rsp+70h] [rbp+7h] BYREF
  signed __int32 v16; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v17; // [rsp+80h] [rbp+17h]
  __int128 v18; // [rsp+90h] [rbp+27h]
  __int64 v19; // [rsp+A0h] [rbp+37h]
  char v20; // [rsp+A8h] [rbp+3Fh]
  LPVOID ppv; // [rsp+D0h] [rbp+67h] BYREF
  OLECHAR *psz; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = *((_QWORD *)this + 8);
  if ( v4 )
  {
    ATL::CAtlArray<DIS11::Title,ATL::CElementTraits<DIS11::Title>>::CallDestructors(v4, *((_QWORD *)this + 9));
    free(*((void **)this + 8));
    *((_QWORD *)this + 8) = 0;
  }
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  v5 = *((_QWORD *)this + 12);
  if ( v5 )
  {
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CallDestructors(
      v5,
      *((_QWORD *)this + 13));
    free(*((void **)this + 12));
    *((_QWORD *)this + 12) = 0;
  }
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 32) = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v15 = &ATL::CComObject<DIS11::ErrHandler>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  do
    v6 = v16;
  while ( v16 != 0x7FFFFFFF && v6 != _InterlockedCompareExchange(&v16, v16 + 1, v16) );
  ppv = 0;
  v7 = CoCreateInstance(
         &GUID_88d96a0c_f192_11d4_a65f_0040963251e5,
         0,
         0x17u,
         &GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802,
         &ppv);
  if ( v7 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(LPVOID, DIS11::DIS11Keywords *))(*(_QWORD *)ppv + 80LL))(ppv, this);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(LPVOID, void ***))(*(_QWORD *)ppv + 112LL))(ppv, &v15);
      if ( v9 >= 0 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v23,
          a2,
          v10);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&psz);
        DIS11::DIS11Keywords::FixXML(v11, &v23, &psz);
        v12 = psz;
        pvarg.vt = 0;
        VariantClear(&pvarg);
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)SysAllocString(v12);
        if ( !pvarg.llVal )
        {
          if ( v12 )
          {
            pvarg.vt = 10;
            pvarg.lVal = -2147024882;
            ATL::AtlThrowImpl(-2147024882);
          }
        }
        v14 = pvarg;
        v9 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *))(*(_QWORD *)ppv + 152LL))(ppv, &v14);
        VariantClear(&pvarg);
        ATL::CStringData::Release((ATL::CStringData *)(v12 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    ATL::CComObject<DIS11::ErrHandler>::~CComObject<DIS11::ErrHandler>(&v15);
    return (unsigned int)v9;
  }
  else
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    ATL::CComObject<DIS11::ErrHandler>::~CComObject<DIS11::ErrHandler>(&v15);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x180021fac  mov     [rsp-8+arg_8], rbx
0x180021fb1  push    rbp
0x180021fb2  push    rsi
0x180021fb3  push    rdi
0x180021fb4  lea     rbp, [rsp-47h]
0x180021fb9  sub     rsp, 0B0h
0x180021fc0  mov     rsi, rdx
0x180021fc3  mov     rbx, rcx
0x180021fc6  mov     rcx, [rcx+40h]
0x180021fca  test    rcx, rcx
0x180021fcd  jz      short loc_180021FF0
0x180021fcf  mov     rdx, [rbx+48h]
0x180021fd3  call    ?CallDestructors@?$CAtlArray@UTitle@DIS11@@V?$CElementTraits@UTitle@DIS11@@@ATL@@@ATL@@CAXPEAUTitle@DIS11@@_K@Z; ATL::CAtlArray<DIS11::Title,ATL::CElementTraits<DIS11::Title>>::CallDestructors(DIS11::Title *,unsigned __int64)
0x180021fd8  mov     rcx, [rbx+40h]; Block
0x180021fdc  call    cs:__imp_free
0x180021fe3  nop     dword ptr [rax+rax+00h]
0x180021fe8  mov     qword ptr [rbx+40h], 0
0x180021ff0  mov     qword ptr [rbx+48h], 0
0x180021ff8  mov     qword ptr [rbx+50h], 0
0x180022000  mov     rcx, [rbx+60h]
0x180022004  test    rcx, rcx
0x180022007  jz      short loc_18002202A
0x180022009  mov     rdx, [rbx+68h]
0x18002200d  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x180022012  mov     rcx, [rbx+60h]; Block
0x180022016  call    cs:__imp_free
0x18002201d  nop     dword ptr [rax+rax+00h]
0x180022022  mov     qword ptr [rbx+60h], 0
0x18002202a  mov     qword ptr [rbx+68h], 0
0x180022032  mov     qword ptr [rbx+70h], 0
0x18002203a  mov     dword ptr [rbx+80h], 0
0x180022044  mov     [rbp+57h+var_48], 0
0x18002204b  xorps   xmm0, xmm0
0x18002204e  xor     eax, eax
0x180022050  movups  [rbp+57h+var_40], xmm0
0x180022054  movups  [rbp+57h+var_30], xmm0
0x180022058  mov     [rbp+57h+var_20], rax
0x18002205c  mov     [rbp+57h+var_18], al
0x18002205f  lea     rax, ??_7?$CComObject@VErrHandler@DIS11@@@ATL@@6B@; const ATL::CComObject<DIS11::ErrHandler>::`vftable'
0x180022066  mov     [rbp+57h+var_50], rax
0x18002206a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180022071  mov     rax, [rcx]
0x180022074  mov     rax, [rax+8]
0x180022078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002207d  nop
0x18002207e  mov     edx, 7FFFFFFFh
0x180022083  jmp     short loc_18002208F
0x180022085  lea     ecx, [rax+1]
0x180022088  lock cmpxchg [rbp+57h+var_48], ecx
0x18002208d  jz      short loc_180022096
0x18002208f  mov     eax, [rbp+57h+var_48]
0x180022092  cmp     eax, edx
0x180022094  jnz     short loc_180022085
0x180022096  mov     [rbp+57h+arg_0], 0
0x18002209e  lea     rax, [rbp+57h+arg_0]
0x1800220a2  mov     [rsp+0C0h+ppv], rax; ppv
0x1800220a7  lea     r9, _GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802; riid
0x1800220ae  xor     edx, edx; pUnkOuter
0x1800220b0  lea     r8d, [rdx+17h]; dwClsContext
0x1800220b4  lea     rcx, _GUID_88d96a0c_f192_11d4_a65f_0040963251e5; rclsid
0x1800220bb  call    cs:__imp_CoCreateInstance
0x1800220c2  nop     dword ptr [rax+rax+00h]
0x1800220c7  mov     edi, eax
0x1800220c9  test    eax, eax
0x1800220cb  jns     short loc_1800220E7
0x1800220cd  lea     rcx, [rbp+57h+arg_0]
0x1800220d1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800220d6  nop
0x1800220d7  lea     rcx, [rbp+57h+var_50]
0x1800220db  call    ??1?$CComObject@VErrHandler@DIS11@@@ATL@@UEAA@XZ; ATL::CComObject<DIS11::ErrHandler>::~CComObject<DIS11::ErrHandler>(void)
0x1800220e0  mov     eax, edi
0x1800220e2  jmp     loc_1800221F8
0x1800220e7  mov     rcx, [rbp+57h+arg_0]
0x1800220eb  mov     rax, [rcx]
0x1800220ee  mov     rdx, rbx
0x1800220f1  mov     rax, [rax+50h]
0x1800220f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220fa  mov     ebx, eax
0x1800220fc  test    eax, eax
0x1800220fe  js      loc_1800221E3
0x180022104  mov     rcx, [rbp+57h+arg_0]
0x180022108  mov     rax, [rcx]
0x18002210b  lea     rdx, [rbp+57h+var_50]
0x18002210f  mov     rax, [rax+70h]
0x180022113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022118  mov     ebx, eax
0x18002211a  test    eax, eax
0x18002211c  js      loc_1800221E3
0x180022122  mov     rdx, rsi
0x180022125  lea     rcx, [rbp+57h+arg_18]
0x180022129  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002212e  nop
0x18002212f  lea     rcx, [rbp+57h+psz]
0x180022133  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180022138  nop
0x180022139  lea     r8, [rbp+57h+psz]
0x18002213d  lea     rdx, [rbp+57h+arg_18]
0x180022141  call    ?FixXML@DIS11Keywords@DIS11@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; DIS11::DIS11Keywords::FixXML(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180022146  mov     rdi, [rbp+57h+psz]
0x18002214a  xor     eax, eax
0x18002214c  mov     word ptr [rbp+57h+pvarg], ax
0x180022150  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180022154  call    cs:__imp_VariantClear
0x18002215b  nop     dword ptr [rax+rax+00h]
0x180022160  mov     eax, 8
0x180022165  mov     word ptr [rbp+57h+pvarg], ax
0x180022169  mov     rcx, rdi; psz
0x18002216c  call    cs:__imp_SysAllocString
0x180022173  nop     dword ptr [rax+rax+00h]
0x180022178  mov     dword ptr [rbp+57h+pvarg+8], eax
0x18002217b  mov     rcx, rax
0x18002217e  sar     rcx, 20h
0x180022182  mov     dword ptr [rbp+57h+pvarg+0Ch], ecx
0x180022185  test    rax, rax
0x180022188  jnz     short loc_18002218F
0x18002218a  test    rdi, rdi
0x18002218d  jnz     short loc_18002220C
0x18002218f  mov     rcx, [rbp+57h+arg_0]
0x180022193  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180022197  movaps  [rbp+57h+var_70], xmm0
0x18002219b  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800221a0  movsd   [rbp+57h+var_60], xmm1
0x1800221a5  mov     rax, [rcx]
0x1800221a8  lea     rdx, [rbp+57h+var_70]
0x1800221ac  mov     rax, [rax+98h]
0x1800221b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221b8  mov     ebx, eax
0x1800221ba  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800221be  call    cs:__imp_VariantClear
0x1800221c5  nop     dword ptr [rax+rax+00h]
0x1800221ca  nop
0x1800221cb  lea     rcx, [rdi-18h]; this
0x1800221cf  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800221d4  nop
0x1800221d5  mov     rcx, [rbp+57h+arg_18]
0x1800221d9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800221dd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800221e2  nop
0x1800221e3  lea     rcx, [rbp+57h+arg_0]
0x1800221e7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800221ec  nop
0x1800221ed  lea     rcx, [rbp+57h+var_50]
0x1800221f1  call    ??1?$CComObject@VErrHandler@DIS11@@@ATL@@UEAA@XZ; ATL::CComObject<DIS11::ErrHandler>::~CComObject<DIS11::ErrHandler>(void)
0x1800221f6  mov     eax, ebx
0x1800221f8  mov     rbx, [rsp+0C0h+arg_8]
0x180022200  add     rsp, 0B0h
0x180022207  pop     rdi
0x180022208  pop     rsi
0x180022209  pop     rbp
0x18002220a  retn
0x18002220c  mov     eax, 0Ah
0x180022211  mov     word ptr [rbp+57h+pvarg], ax
0x180022215  mov     ecx, 8007000Eh; int
0x18002221a  mov     dword ptr [rbp+57h+pvarg+8], ecx
0x18002221d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
