# DIS11::DIS11Keywords::Parse(ushort const *)

- ea: `0x180020f20`
- end: `0x180021172`
- name: `?Parse@DIS11Keywords@DIS11@@AEAAJPEBG@Z`
- size: `594`
- prototype: `__int64 __fastcall(DIS11::DIS11Keywords *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001eb74`

## callees

- `0x180007804`
- `0x18000b3bc`
- `0x18000bac0`
- `0x18000beb0`
- `0x18001009c`
- `0x180013e34`
- `0x180020768`
- `0x1800209e4`
- `0x180020a30`
- `0x180020f20`
- `0x180028010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020f50`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020f84`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020f50`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020f84`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021023`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021023`
- `OLEAUT32!__imp_SysAllocString` at `0x1800210c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800210c8`
- `OLEAUT32!__imp_VariantClear` at `0x1800210b6`
- `OLEAUT32!__imp_VariantClear` at `0x180021114`
- `OLEAUT32!__imp_VariantClear` at `0x1800210b6`
- `OLEAUT32!__imp_VariantClear` at `0x180021114`

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
  __int64 v10; // rcx
  OLECHAR *v11; // rdi
  VARIANTARG pvarg; // [rsp+30h] [rbp-39h] BYREF
  VARIANTARG v13; // [rsp+50h] [rbp-19h] BYREF
  void **v14; // [rsp+70h] [rbp+7h] BYREF
  signed __int32 v15; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v16; // [rsp+80h] [rbp+17h]
  __int128 v17; // [rsp+90h] [rbp+27h]
  __int64 v18; // [rsp+A0h] [rbp+37h]
  char v19; // [rsp+A8h] [rbp+3Fh]
  LPVOID ppv; // [rsp+D0h] [rbp+67h] BYREF
  OLECHAR *psz; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v22; // [rsp+E8h] [rbp+7Fh] BYREF

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
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v14 = &ATL::CComObject<DIS11::ErrHandler>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  do
    v6 = v15;
  while ( v15 != 0x7FFFFFFF && v6 != _InterlockedCompareExchange(&v15, v15 + 1, v15) );
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
      v9 = (*(__int64 (__fastcall **)(LPVOID, void ***))(*(_QWORD *)ppv + 112LL))(ppv, &v14);
      if ( v9 >= 0 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v22,
          a2);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&psz);
        DIS11::DIS11Keywords::FixXML(v10, &v22, &psz);
        v11 = psz;
        pvarg.vt = 0;
        VariantClear(&pvarg);
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)SysAllocString(v11);
        if ( !pvarg.llVal )
        {
          if ( v11 )
          {
            pvarg.vt = 10;
            pvarg.lVal = -2147024882;
            ATL::AtlThrowImpl(-2147024882);
          }
        }
        v13 = pvarg;
        v9 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *))(*(_QWORD *)ppv + 152LL))(ppv, &v13);
        VariantClear(&pvarg);
        ATL::CStringData::Release((ATL::CStringData *)(v11 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    ATL::CComObject<DIS11::ErrHandler>::~CComObject<DIS11::ErrHandler>(&v14);
    return (unsigned int)v9;
  }
  else
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    ATL::CComObject<DIS11::ErrHandler>::~CComObject<DIS11::ErrHandler>(&v14);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x180020f20  mov     [rsp-8+arg_8], rbx
0x180020f25  push    rbp
0x180020f26  push    rsi
0x180020f27  push    rdi
0x180020f28  lea     rbp, [rsp-47h]
0x180020f2d  sub     rsp, 0B0h
0x180020f34  mov     rsi, rdx
0x180020f37  mov     rbx, rcx
0x180020f3a  mov     rcx, [rcx+40h]
0x180020f3e  test    rcx, rcx
0x180020f41  jz      short loc_180020F5E
0x180020f43  mov     rdx, [rbx+48h]
0x180020f47  call    ?CallDestructors@?$CAtlArray@UTitle@DIS11@@V?$CElementTraits@UTitle@DIS11@@@ATL@@@ATL@@CAXPEAUTitle@DIS11@@_K@Z; ATL::CAtlArray<DIS11::Title,ATL::CElementTraits<DIS11::Title>>::CallDestructors(DIS11::Title *,unsigned __int64)
0x180020f4c  mov     rcx, [rbx+40h]; Block
0x180020f50  call    cs:__imp_free
0x180020f56  mov     qword ptr [rbx+40h], 0
0x180020f5e  mov     qword ptr [rbx+48h], 0
0x180020f66  mov     qword ptr [rbx+50h], 0
0x180020f6e  mov     rcx, [rbx+60h]
0x180020f72  test    rcx, rcx
0x180020f75  jz      short loc_180020F92
0x180020f77  mov     rdx, [rbx+68h]
0x180020f7b  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x180020f80  mov     rcx, [rbx+60h]; Block
0x180020f84  call    cs:__imp_free
0x180020f8a  mov     qword ptr [rbx+60h], 0
0x180020f92  mov     qword ptr [rbx+68h], 0
0x180020f9a  mov     qword ptr [rbx+70h], 0
0x180020fa2  mov     dword ptr [rbx+80h], 0
0x180020fac  mov     [rbp+57h+var_48], 0
0x180020fb3  xorps   xmm0, xmm0
0x180020fb6  xor     eax, eax
0x180020fb8  movups  [rbp+57h+var_40], xmm0
0x180020fbc  movups  [rbp+57h+var_30], xmm0
0x180020fc0  mov     [rbp+57h+var_20], rax
0x180020fc4  mov     [rbp+57h+var_18], al
0x180020fc7  lea     rax, ??_7?$CComObject@VErrHandler@DIS11@@@ATL@@6B@; const ATL::CComObject<DIS11::ErrHandler>::`vftable'
0x180020fce  mov     [rbp+57h+var_50], rax
0x180020fd2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180020fd9  mov     rax, [rcx]
0x180020fdc  mov     rax, [rax+8]
0x180020fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fe5  nop
0x180020fe6  mov     edx, 7FFFFFFFh
0x180020feb  jmp     short loc_180020FF7
0x180020fed  lea     ecx, [rax+1]
0x180020ff0  lock cmpxchg [rbp+57h+var_48], ecx
0x180020ff5  jz      short loc_180020FFE
0x180020ff7  mov     eax, [rbp+57h+var_48]
0x180020ffa  cmp     eax, edx
0x180020ffc  jnz     short loc_180020FED
0x180020ffe  mov     [rbp+57h+arg_0], 0
0x180021006  lea     rax, [rbp+57h+arg_0]
0x18002100a  mov     [rsp+0C0h+ppv], rax; ppv
0x18002100f  lea     r9, _GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802; riid
0x180021016  xor     edx, edx; pUnkOuter
0x180021018  lea     r8d, [rdx+17h]; dwClsContext
0x18002101c  lea     rcx, _GUID_88d96a0c_f192_11d4_a65f_0040963251e5; rclsid
0x180021023  call    cs:__imp_CoCreateInstance
0x180021029  mov     edi, eax
0x18002102b  test    eax, eax
0x18002102d  jns     short loc_180021049
0x18002102f  lea     rcx, [rbp+57h+arg_0]
0x180021033  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021038  nop
0x180021039  lea     rcx, [rbp+57h+var_50]
0x18002103d  call    ??1?$CComObject@VErrHandler@DIS11@@@ATL@@UEAA@XZ; ATL::CComObject<DIS11::ErrHandler>::~CComObject<DIS11::ErrHandler>(void)
0x180021042  mov     eax, edi
0x180021044  jmp     loc_180021148
0x180021049  mov     rcx, [rbp+57h+arg_0]
0x18002104d  mov     rax, [rcx]
0x180021050  mov     rdx, rbx
0x180021053  mov     rax, [rax+50h]
0x180021057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002105c  mov     ebx, eax
0x18002105e  test    eax, eax
0x180021060  js      loc_180021133
0x180021066  mov     rcx, [rbp+57h+arg_0]
0x18002106a  mov     rax, [rcx]
0x18002106d  lea     rdx, [rbp+57h+var_50]
0x180021071  mov     rax, [rax+70h]
0x180021075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002107a  mov     ebx, eax
0x18002107c  test    eax, eax
0x18002107e  js      loc_180021133
0x180021084  mov     rdx, rsi
0x180021087  lea     rcx, [rbp+57h+arg_18]
0x18002108b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180021090  nop
0x180021091  lea     rcx, [rbp+57h+psz]
0x180021095  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002109a  nop
0x18002109b  lea     r8, [rbp+57h+psz]
0x18002109f  lea     rdx, [rbp+57h+arg_18]
0x1800210a3  call    ?FixXML@DIS11Keywords@DIS11@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; DIS11::DIS11Keywords::FixXML(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800210a8  mov     rdi, [rbp+57h+psz]
0x1800210ac  xor     eax, eax
0x1800210ae  mov     word ptr [rbp+57h+pvarg], ax
0x1800210b2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800210b6  call    cs:__imp_VariantClear
0x1800210bc  mov     eax, 8
0x1800210c1  mov     word ptr [rbp+57h+pvarg], ax
0x1800210c5  mov     rcx, rdi; psz
0x1800210c8  call    cs:__imp_SysAllocString
0x1800210ce  mov     dword ptr [rbp+57h+pvarg+8], eax
0x1800210d1  mov     rcx, rax
0x1800210d4  sar     rcx, 20h
0x1800210d8  mov     dword ptr [rbp+57h+pvarg+0Ch], ecx
0x1800210db  test    rax, rax
0x1800210de  jnz     short loc_1800210E5
0x1800210e0  test    rdi, rdi
0x1800210e3  jnz     short loc_18002115B
0x1800210e5  mov     rcx, [rbp+57h+arg_0]
0x1800210e9  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800210ed  movaps  [rbp+57h+var_70], xmm0
0x1800210f1  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800210f6  movsd   [rbp+57h+var_60], xmm1
0x1800210fb  mov     rax, [rcx]
0x1800210fe  lea     rdx, [rbp+57h+var_70]
0x180021102  mov     rax, [rax+98h]
0x180021109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002110e  mov     ebx, eax
0x180021110  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180021114  call    cs:__imp_VariantClear
0x18002111a  nop
0x18002111b  lea     rcx, [rdi-18h]; this
0x18002111f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021124  nop
0x180021125  mov     rcx, [rbp+57h+arg_18]
0x180021129  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002112d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021132  nop
0x180021133  lea     rcx, [rbp+57h+arg_0]
0x180021137  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002113c  nop
0x18002113d  lea     rcx, [rbp+57h+var_50]
0x180021141  call    ??1?$CComObject@VErrHandler@DIS11@@@ATL@@UEAA@XZ; ATL::CComObject<DIS11::ErrHandler>::~CComObject<DIS11::ErrHandler>(void)
0x180021146  mov     eax, ebx
0x180021148  mov     rbx, [rsp+0C0h+arg_8]
0x180021150  add     rsp, 0B0h
0x180021157  pop     rdi
0x180021158  pop     rsi
0x180021159  pop     rbp
0x18002115a  retn
0x18002115b  mov     eax, 0Ah
0x180021160  mov     word ptr [rbp+57h+pvarg], ax
0x180021164  mov     ecx, 8007000Eh; int
0x180021169  mov     dword ptr [rbp+57h+pvarg+8], ecx
0x18002116c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
