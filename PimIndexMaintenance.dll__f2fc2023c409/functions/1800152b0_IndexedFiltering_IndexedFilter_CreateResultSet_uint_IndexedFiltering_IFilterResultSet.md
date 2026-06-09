# IndexedFiltering::IndexedFilter::CreateResultSet(uint,IndexedFiltering::IFilterResultSet * *)

- ea: `0x1800152b0`
- end: `0x18001536b`
- name: `?CreateResultSet@IndexedFilter@IndexedFiltering@@MEAAJIPEAPEAUIFilterResultSet@2@@Z`
- size: `187`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexedFilter *this, __int64, struct IndexedFiltering::IFilterResultSet **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002da8`
- `0x18000428c`
- `0x1800152b0`
- `0x1800157c0`
- `0x18001ebec`
- `0x180022010`

## string_xrefs

- `0x180015316`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexedfilter.cpp`
- `0x18001535a`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\filterresultset.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexedFilter::CreateResultSet(
        IndexedFiltering::IndexedFilter *this,
        __int64 a2,
        struct IndexedFiltering::IFilterResultSet **a3)
{
  unsigned int v4; // ebx
  int v5; // ebx
  struct IndexedFiltering::FilterResultSet *v7; // [rsp+40h] [rbp+8h] BYREF

  v4 = a2;
  if ( *((_QWORD *)this + 5) || !a3 )
  {
    Log_AssertionEvent_2(this, a2, 416);
    v7 = 0;
    if ( !a3 )
    {
      v5 = -2147024809;
      Log_HREvent(
        2147942487LL,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\filterresultset.cpp",
        123);
      goto LABEL_6;
    }
  }
  else
  {
    v7 = 0;
  }
  v5 = IndexedFiltering::FilterResultSet::CreateInstance(v4, &v7);
  if ( v5 >= 0 )
    v5 = (**(__int64 (__fastcall ***)(struct IndexedFiltering::FilterResultSet *, GUID *, struct IndexedFiltering::IFilterResultSet **))v7)(
           v7,
           &GUID_277d1957_089c_494d_8e5e_ddafade4b52a,
           a3);
LABEL_6:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v7);
  if ( v5 < 0 )
    Log_HREvent(
      (unsigned int)v5,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexedfilter.cpp",
      419);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800152b0  mov     [rsp+arg_8], rbx
0x1800152b5  push    rdi
0x1800152b6  sub     rsp, 30h
0x1800152ba  cmp     qword ptr [rcx+28h], 0
0x1800152bf  mov     rdi, r8
0x1800152c2  mov     ebx, edx
0x1800152c4  jnz     short loc_180015336
0x1800152c6  test    r8, r8
0x1800152c9  jz      short loc_180015336
0x1800152cb  mov     [rsp+38h+arg_0], 0
0x1800152d4  lea     rdx, [rsp+38h+arg_0]; struct IndexedFiltering::FilterResultSet **
0x1800152d9  mov     ecx, ebx; unsigned int
0x1800152db  call    ?CreateInstance@FilterResultSet@IndexedFiltering@@SAJIPEAPEAV12@@Z; IndexedFiltering::FilterResultSet::CreateInstance(uint,IndexedFiltering::FilterResultSet * *)
0x1800152e0  mov     ebx, eax
0x1800152e2  test    eax, eax
0x1800152e4  js      short loc_180015302
0x1800152e6  mov     rcx, [rsp+38h+arg_0]
0x1800152eb  lea     rdx, _GUID_277d1957_089c_494d_8e5e_ddafade4b52a
0x1800152f2  mov     r8, rdi
0x1800152f5  mov     rax, [rcx]
0x1800152f8  mov     rax, [rax]
0x1800152fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015300  mov     ebx, eax
0x180015302  lea     rcx, [rsp+38h+arg_0]
0x180015307  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001530c  test    ebx, ebx
0x18001530e  jns     short loc_180015329
0x180015310  mov     r9d, 1A3h
0x180015316  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001531d  mov     edx, 1
0x180015322  mov     ecx, ebx
0x180015324  call    Log_HREvent
0x180015329  mov     eax, ebx
0x18001532b  mov     rbx, [rsp+38h+arg_8]
0x180015330  add     rsp, 30h
0x180015334  pop     rdi
0x180015335  retn
0x180015336  mov     r8d, 1A0h
0x18001533c  call    Log_AssertionEvent_2
0x180015341  mov     [rsp+38h+arg_0], 0
0x18001534a  test    rdi, rdi
0x18001534d  jnz     short loc_1800152D4
0x18001534f  mov     ebx, 80070057h
0x180015354  lea     r9d, [rdi+7Bh]
0x180015358  mov     ecx, ebx
0x18001535a  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180015361  lea     edx, [rdi+1]
0x180015364  call    Log_HREvent
0x180015369  jmp     short loc_180015302
```
