# WindowsPerformanceRecorder::CETWProperties::AddHeapProcessIds(_TRACE_ENABLE_FLAG_EXT_HEADER *,void const *,std::set<ulong,std::less<ulong>,std::allocator<ulong>> const &)

- ea: `0x180063f00`
- end: `0x18006401e`
- name: `?AddHeapProcessIds@CETWProperties@WindowsPerformanceRecorder@@AEBAJPEAU_TRACE_ENABLE_FLAG_EXT_HEADER@@PEBXAEBV?$set@KU?$less@K@std@@V?$allocator@K@2@@std@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(void *, struct _TRACE_ENABLE_FLAG_EXT_HEADER *, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180063aec`

## callees

- `0x1800024d0`
- `0x18001e6e0`
- `0x1800351c0`
- `0x18004794c`
- `0x18004f964`
- `0x180056a58`
- `0x180063f00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180064003`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180064003`

## string_xrefs

- `0x180063fd6`: `COMGUARD`
- `0x180063feb`: `AddHeapProcessIds`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::AddHeapProcessIds(
        void *a1,
        struct _TRACE_ENABLE_FLAG_EXT_HEADER *a2,
        unsigned __int64 a3,
        __int64 a4)
{
  unsigned __int64 v4; // rax
  __int64 v9; // rsi
  char v10; // al
  _DWORD *v11; // rbx
  signed int v12; // edi
  __int64 v13; // r8
  _DWORD *v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  const char *v19; // [rsp+28h] [rbp-20h]
  void *Block; // [rsp+50h] [rbp+8h] BYREF

  Block = a1;
  v4 = *(_QWORD *)(a4 + 8);
  if ( v4 > 2 )
    return 2147549183LL;
  v9 = 4 * v4;
  Block = 0;
  v10 = ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(&Block, 4 * v4);
  v11 = Block;
  if ( v10 )
  {
    memset_0(Block, 0, v9);
    Block = **(void ***)a4;
    if ( (unsigned __int8)std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(
                            &Block,
                            Block,
                            v13,
                            0) )
    {
      while ( 1 )
      {
        v11[v15] = v14[7];
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(&Block);
        if ( !(unsigned __int8)std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(
                                 &Block,
                                 v16,
                                 v17,
                                 v18) )
          break;
        v14 = Block;
      }
    }
    v12 = WindowsPerformanceRecorder::CETWProperties::AddExtendedFlagEntry(a2, a3, 2u, v11, v9);
    if ( v12 >= 0 )
      v12 = 0;
    else
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        (unsigned __int8)"AddHeapProcessIds",
        (const char *)0x7E0,
        v12,
        "COMGUARD",
        v19);
  }
  else
  {
    v12 = -2147024882;
  }
  free(v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180063f00  mov     [rsp+arg_8], rbx
0x180063f05  mov     [rsp+arg_10], rbp
0x180063f0a  mov     [rsp+Block], rcx
0x180063f0f  push    rsi
0x180063f10  push    rdi
0x180063f11  push    r14
0x180063f13  sub     rsp, 30h
0x180063f17  mov     rax, [r9+8]
0x180063f1b  mov     rdi, r9
0x180063f1e  mov     rbp, r8
0x180063f21  mov     r14, rdx
0x180063f24  cmp     rax, 2
0x180063f28  jbe     short loc_180063F34
0x180063f2a  mov     eax, 8000FFFFh
0x180063f2f  jmp     loc_18006400B
0x180063f34  lea     rsi, ds:0[rax*4]
0x180063f3c  mov     [rsp+48h+Block], 0
0x180063f45  mov     rdx, rsi
0x180063f48  lea     rcx, [rsp+48h+Block]
0x180063f4d  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x180063f52  mov     rbx, [rsp+48h+Block]
0x180063f57  test    al, al
0x180063f59  jnz     short loc_180063F65
0x180063f5b  mov     edi, 8007000Eh
0x180063f60  jmp     loc_180064000
0x180063f65  mov     r8, rsi; Size
0x180063f68  xor     edx, edx; Val
0x180063f6a  mov     rcx, rbx; void *
0x180063f6d  call    memset_0
0x180063f72  mov     rdx, [rdi]
0x180063f75  lea     rcx, [rsp+48h+Block]
0x180063f7a  xor     r9d, r9d
0x180063f7d  mov     rdx, [rdx]
0x180063f80  mov     [rsp+48h+Block], rdx
0x180063f85  call    ??9?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEBA_NU_Default_sentinel@1@@Z; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(std::_Default_sentinel)
0x180063f8a  test    al, al
0x180063f8c  jz      short loc_180063FB7
0x180063f8e  mov     eax, [rdx+1Ch]
0x180063f91  lea     rcx, [rsp+48h+Block]
0x180063f96  mov     [rbx+r9*4], eax
0x180063f9a  inc     r9
0x180063f9d  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UCCounter@CHardwareCounterElement@WindowsPerformanceRecorder@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(void)
0x180063fa2  lea     rcx, [rsp+48h+Block]
0x180063fa7  call    ??9?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEBA_NU_Default_sentinel@1@@Z; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(std::_Default_sentinel)
0x180063fac  test    al, al
0x180063fae  jz      short loc_180063FB7
0x180063fb0  mov     rdx, [rsp+48h+Block]
0x180063fb5  jmp     short loc_180063F8E
0x180063fb7  mov     r8d, 2; unsigned __int16
0x180063fbd  mov     word ptr [rsp+48h+Format], si; unsigned __int16
0x180063fc2  mov     r9, rbx; void *
0x180063fc5  mov     rdx, rbp; void *
0x180063fc8  mov     rcx, r14; struct _TRACE_ENABLE_FLAG_EXT_HEADER *
0x180063fcb  call    ?AddExtendedFlagEntry@CETWProperties@WindowsPerformanceRecorder@@CAJPEAU_TRACE_ENABLE_FLAG_EXT_HEADER@@PEBXG1G@Z; WindowsPerformanceRecorder::CETWProperties::AddExtendedFlagEntry(_TRACE_ENABLE_FLAG_EXT_HEADER *,void const *,ushort,void const *,ushort)
0x180063fd0  mov     edi, eax
0x180063fd2  test    eax, eax
0x180063fd4  jns     short loc_180063FFE
0x180063fd6  lea     rax, aComguard; "COMGUARD"
0x180063fdd  mov     r9d, edi; unsigned int
0x180063fe0  mov     r8d, 7E0h; char *
0x180063fe6  mov     [rsp+48h+Format], rax; Format
0x180063feb  lea     rdx, aAddheapprocess; "AddHeapProcessIds"
0x180063ff2  mov     ecx, 2; this
0x180063ff7  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180063ffc  jmp     short loc_180064000
0x180063ffe  xor     edi, edi
0x180064000  mov     rcx, rbx; Block
0x180064003  call    cs:__imp_free
0x180064009  mov     eax, edi
0x18006400b  mov     rbx, [rsp+48h+arg_8]
0x180064010  mov     rbp, [rsp+48h+arg_10]
0x180064015  add     rsp, 30h
0x180064019  pop     r14
0x18006401b  pop     rdi
0x18006401c  pop     rsi
0x18006401d  retn
```
