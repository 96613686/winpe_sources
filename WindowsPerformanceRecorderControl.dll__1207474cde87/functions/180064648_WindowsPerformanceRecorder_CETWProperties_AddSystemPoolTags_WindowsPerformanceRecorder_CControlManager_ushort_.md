# WindowsPerformanceRecorder::CETWProperties::AddSystemPoolTags(WindowsPerformanceRecorder::CControlManager *,ushort const *,_TRACE_ENABLE_FLAG_EXT_HEADER *,void const *,std::set<ulong,std::less<ulong>,std::allocator<ulong>> const &)

- ea: `0x180064648`
- end: `0x180064877`
- name: `?AddSystemPoolTags@CETWProperties@WindowsPerformanceRecorder@@AEBAJPEAVCControlManager@2@PEBGPEAU_TRACE_ENABLE_FLAG_EXT_HEADER@@PEBXAEBV?$set@KU?$less@K@std@@V?$allocator@K@2@@std@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(__int64, WindowsPerformanceRecorder::CControlManager *, const unsigned __int16 *, struct _TRACE_ENABLE_FLAG_EXT_HEADER *, void *, void ***)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d11c`

## callees

- `0x1800024d0`
- `0x180008330`
- `0x1800138c0`
- `0x18001c820`
- `0x18001e6e0`
- `0x1800209d0`
- `0x180030bd4`
- `0x1800351c0`
- `0x180039de4`
- `0x18004794c`
- `0x18004f964`
- `0x180056a58`
- `0x180064648`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180064863`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180064863`

## string_xrefs

- `0x180064836`: `COMGUARD`
- `0x180064733`: `AddSystemPoolTags`
- `0x18006484b`: `AddSystemPoolTags`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::AddSystemPoolTags(
        __int64 a1,
        WindowsPerformanceRecorder::CControlManager *a2,
        const unsigned __int16 *a3,
        struct _TRACE_ENABLE_FLAG_EXT_HEADER *a4,
        void *a5,
        void ***a6)
{
  bool IsWin7AndUp; // al
  __int64 v11; // r8
  __int64 v12; // r9
  void *v13; // rdx
  __int64 v14; // rdx
  const struct _GUID *v15; // r8
  unsigned __int8 i; // bl
  unsigned __int16 *v17; // rbx
  __int64 result; // rax
  unsigned __int64 v19; // rax
  __int64 v20; // rsi
  char Bytes; // al
  _DWORD *v22; // rbx
  signed int v23; // edi
  __int64 v24; // r8
  unsigned __int16 *v25; // rdx
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  char *v30; // [rsp+28h] [rbp-70h]
  struct IControlErrorInfo *v31; // [rsp+38h] [rbp-60h]
  _DWORD v32[2]; // [rsp+40h] [rbp-58h]
  unsigned __int16 *v33; // [rsp+48h] [rbp-50h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-48h] BYREF
  ATL::CAtlException *v35; // [rsp+60h] [rbp-38h] BYREF

  Block[1] = (void *)-2LL;
  IsWin7AndUp = Performance::COSVersionInfo::IsWin7AndUp();
  try
  {
    if ( IsWin7AndUp )
    {
      v19 = (unsigned __int64)a6[1];
      if ( v19 <= 4 )
      {
        Block[0] = 0;
        v20 = 4 * v19;
        Bytes = ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(Block, 4 * v19);
        v22 = Block[0];
        if ( Bytes )
        {
          memset_0(Block[0], 0, v20);
          v33 = (unsigned __int16 *)**a6;
          if ( (unsigned __int8)std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(
                                  &v33,
                                  v33,
                                  v24,
                                  0) )
          {
            while ( 1 )
            {
              v22[v26] = *((_DWORD *)v25 + 7);
              std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(&v33);
              if ( !(unsigned __int8)std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(
                                       &v33,
                                       v27,
                                       v28,
                                       v29) )
                break;
              v25 = v33;
            }
          }
          v23 = WindowsPerformanceRecorder::CETWProperties::AddExtendedFlagEntry(a4, a5, 4u, v22, v20);
          if ( v23 >= 0 )
            v23 = 0;
          else
            WindowsPerformanceRecorder::TraceHR(
              (WindowsPerformanceRecorder *)2,
              (unsigned __int8)"AddSystemPoolTags",
              (const char *)0x3ED,
              v23,
              "COMGUARD",
              v30);
        }
        else
        {
          v23 = -2147024882;
        }
        free(v22);
        result = (unsigned int)v23;
      }
      else
      {
        result = 3310895123LL;
      }
    }
    else
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v33);
      v13 = **a6;
      Block[0] = v13;
      while ( (unsigned __int8)std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(
                                 Block,
                                 v13,
                                 v11,
                                 v12) )
      {
        v32[0] = *(_DWORD *)(v14 + 28);
        ATL::CSimpleStringT<unsigned short,0>::Empty(&v33);
        for ( i = 0; i < 4u; ++i )
          ATL::CSimpleStringT<unsigned short,0>::AppendChar(&v33, *((unsigned __int8 *)v32 + i));
        if ( a2 )
        {
          v17 = v33;
          WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(
            a2,
            -984080382,
            v15,
            0,
            a3,
            *(const unsigned __int16 **)(a1 + 320),
            v33,
            v31);
          v31 = (struct IControlErrorInfo *)v17;
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)3,
            (unsigned __int8)"AddSystemPoolTags",
            (const char *)0x3CA,
            0xC5582002,
            "%ws: %ws, %ws",
            (const char *)a3,
            *(_QWORD *)(a1 + 320));
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(Block);
        v13 = Block[0];
      }
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v33);
      result = 0;
    }
  }
  catch ( ATL::CAtlException *v35 )
  {
    return *(unsigned int *)v35;
  }
  if ( IsWin7AndUp )
  {
    v19 = (unsigned __int64)a6[1];
    if ( v19 <= 4 )
    {
      Block[0] = 0;
      v20 = 4 * v19;
      Bytes = ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(Block, 4 * v19);
      v22 = Block[0];
      if ( Bytes )
      {
        memset_0(Block[0], 0, v20);
        v33 = (unsigned __int16 *)**a6;
        if ( (unsigned __int8)std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(
                                &v33,
                                v33,
                                v24,
                                0) )
        {
          while ( 1 )
          {
            v22[v26] = *((_DWORD *)v25 + 7);
            std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(&v33);
            if ( !(unsigned __int8)std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(
                                     &v33,
                                     v27,
                                     v28,
                                     v29) )
              break;
            v25 = v33;
          }
        }
        v23 = WindowsPerformanceRecorder::CETWProperties::AddExtendedFlagEntry(a4, a5, 4u, v22, v20);
        if ( v23 >= 0 )
          v23 = 0;
        else
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            (unsigned __int8)"AddSystemPoolTags",
            (const char *)0x3ED,
            v23,
            "COMGUARD",
            v30);
      }
      else
      {
        v23 = -2147024882;
      }
      free(v22);
      result = (unsigned int)v23;
    }
    else
    {
      result = 3310895123LL;
    }
  }
  else
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v33);
    v13 = **a6;
    Block[0] = v13;
    while ( (unsigned __int8)std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(
                               Block,
                               v13,
                               v11,
                               v12) )
    {
      v32[0] = *(_DWORD *)(v14 + 28);
      ATL::CSimpleStringT<unsigned short,0>::Empty(&v33);
      for ( i = 0; i < 4u; ++i )
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(&v33, *((unsigned __int8 *)v32 + i));
      if ( a2 )
      {
        v17 = v33;
        WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(
          a2,
          -984080382,
          v15,
          0,
          a3,
          *(const unsigned __int16 **)(a1 + 320),
          v33,
          v31);
        v31 = (struct IControlErrorInfo *)v17;
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)3,
          (unsigned __int8)"AddSystemPoolTags",
          (const char *)0x3CA,
          0xC5582002,
          "%ws: %ws, %ws",
          (const char *)a3,
          *(_QWORD *)(a1 + 320));
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(Block);
      v13 = Block[0];
    }
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v33);
    result = 0;
  }
}

```

## disassembly

```asm
0x180064648  push    rbx
0x18006464a  push    rsi
0x18006464b  push    rdi
0x18006464c  push    r14
0x18006464e  push    r15
0x180064650  sub     rsp, 70h
0x180064654  mov     [rsp+98h+var_40], 0FFFFFFFFFFFFFFFEh
0x18006465d  mov     r15, r9
0x180064660  mov     rsi, r8
0x180064663  mov     rdi, rdx
0x180064666  mov     r14, rcx
0x180064669  call    ?IsWin7AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin7AndUp(void)
0x18006466e  test    al, al
0x180064670  jnz     loc_180064773
0x180064676  lea     rcx, [rsp+98h+var_50]; void *
0x18006467b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180064680  nop
0x180064681  mov     rax, [rsp+98h+arg_28]
0x180064689  mov     rdx, [rax]
0x18006468c  mov     rdx, [rdx]
0x18006468f  mov     [rsp+98h+Block], rdx
0x180064694  mov     r15d, 0C5582002h
0x18006469a  lea     rcx, [rsp+98h+Block]
0x18006469f  call    ??9?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEBA_NU_Default_sentinel@1@@Z; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(std::_Default_sentinel)
0x1800646a4  test    al, al
0x1800646a6  jz      loc_180064758
0x1800646ac  mov     eax, [rdx+1Ch]
0x1800646af  mov     [rsp+98h+var_58], eax
0x1800646b3  lea     rcx, [rsp+98h+var_50]
0x1800646b8  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800646bd  xor     bl, bl
0x1800646bf  cmp     bl, 4
0x1800646c2  jnb     short loc_1800646DA
0x1800646c4  movzx   eax, bl
0x1800646c7  movzx   edx, byte ptr [rsp+rax+98h+var_58]
0x1800646cc  lea     rcx, [rsp+98h+var_50]
0x1800646d1  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800646d6  inc     bl
0x1800646d8  jmp     short loc_1800646BF
0x1800646da  test    rdi, rdi
0x1800646dd  jz      short loc_180064744
0x1800646df  mov     rbx, [rsp+98h+var_50]
0x1800646e4  mov     [rsp+98h+var_68], rbx; unsigned __int16 *
0x1800646e9  mov     rax, [r14+140h]
0x1800646f0  mov     [rsp+98h+var_70], rax; unsigned __int16 *
0x1800646f5  mov     [rsp+98h+Format], rsi; unsigned __int16 *
0x1800646fa  xor     r9d, r9d; struct _GUID *
0x1800646fd  mov     edx, r15d; int
0x180064700  mov     rcx, rdi; this
0x180064703  call    ?AddProviderControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBU3@PEBG22PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(long,_GUID const &,_GUID const *,ushort const *,ushort const *,ushort const *,IControlErrorInfo *)
0x180064708  mov     [rsp+98h+var_60], rbx
0x18006470d  mov     rax, [r14+140h]
0x180064714  mov     [rsp+98h+var_68], rax
0x180064719  mov     [rsp+98h+var_70], rsi; char *
0x18006471e  lea     rax, aWsWsWs; "%ws: %ws, %ws"
0x180064725  mov     [rsp+98h+Format], rax; Format
0x18006472a  mov     r9d, r15d; unsigned int
0x18006472d  mov     r8d, 3CAh; char *
0x180064733  lea     rdx, aAddsystempoolt; "AddSystemPoolTags"
0x18006473a  mov     ecx, 3; this
0x18006473f  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180064744  lea     rcx, [rsp+98h+Block]
0x180064749  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UCCounter@CHardwareCounterElement@WindowsPerformanceRecorder@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(void)
0x18006474e  mov     rdx, [rsp+98h+Block]
0x180064753  jmp     loc_18006469A
0x180064758  lea     rcx, [rsp+98h+var_50]; this
0x18006475d  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180064762  nop
0x180064763  xor     eax, eax
0x180064765  jmp     loc_18006486B
0x18006476a  mov     eax, [rsp+98h+var_58]
0x18006476e  jmp     loc_18006486B
0x180064773  mov     rdi, [rsp+98h+arg_28]
0x18006477b  mov     rax, [rdi+8]
0x18006477f  cmp     rax, 4
0x180064783  jbe     short loc_18006478F
0x180064785  mov     eax, 0C5584013h
0x18006478a  jmp     loc_18006486B
0x18006478f  mov     [rsp+98h+Block], 0
0x180064798  lea     rsi, ds:0[rax*4]
0x1800647a0  mov     rdx, rsi
0x1800647a3  lea     rcx, [rsp+98h+Block]
0x1800647a8  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x1800647ad  mov     rbx, [rsp+98h+Block]
0x1800647b2  test    al, al
0x1800647b4  jnz     short loc_1800647C0
0x1800647b6  mov     edi, 8007000Eh
0x1800647bb  jmp     loc_180064860
0x1800647c0  mov     r8, rsi; Size
0x1800647c3  xor     edx, edx; Val
0x1800647c5  mov     rcx, rbx; void *
0x1800647c8  call    memset_0
0x1800647cd  xor     r9d, r9d
0x1800647d0  mov     rdx, [rdi]
0x1800647d3  mov     rdx, [rdx]
0x1800647d6  mov     [rsp+98h+var_50], rdx
0x1800647db  lea     rcx, [rsp+98h+var_50]
0x1800647e0  call    ??9?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEBA_NU_Default_sentinel@1@@Z; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(std::_Default_sentinel)
0x1800647e5  test    al, al
0x1800647e7  jz      short loc_180064812
0x1800647e9  mov     eax, [rdx+1Ch]
0x1800647ec  mov     [rbx+r9*4], eax
0x1800647f0  inc     r9
0x1800647f3  lea     rcx, [rsp+98h+var_50]
0x1800647f8  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UCCounter@CHardwareCounterElement@WindowsPerformanceRecorder@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(void)
0x1800647fd  lea     rcx, [rsp+98h+var_50]
0x180064802  call    ??9?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEBA_NU_Default_sentinel@1@@Z; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(std::_Default_sentinel)
0x180064807  test    al, al
0x180064809  jz      short loc_180064812
0x18006480b  mov     rdx, [rsp+98h+var_50]
0x180064810  jmp     short loc_1800647E9
0x180064812  mov     r8d, 4; unsigned __int16
0x180064818  mov     word ptr [rsp+98h+Format], si; unsigned __int16
0x18006481d  mov     r9, rbx; void *
0x180064820  mov     rdx, [rsp+98h+arg_20]; void *
0x180064828  mov     rcx, r15; struct _TRACE_ENABLE_FLAG_EXT_HEADER *
0x18006482b  call    ?AddExtendedFlagEntry@CETWProperties@WindowsPerformanceRecorder@@CAJPEAU_TRACE_ENABLE_FLAG_EXT_HEADER@@PEBXG1G@Z; WindowsPerformanceRecorder::CETWProperties::AddExtendedFlagEntry(_TRACE_ENABLE_FLAG_EXT_HEADER *,void const *,ushort,void const *,ushort)
0x180064830  mov     edi, eax
0x180064832  test    eax, eax
0x180064834  jns     short loc_18006485E
0x180064836  lea     rax, aComguard; "COMGUARD"
0x18006483d  mov     [rsp+98h+Format], rax; Format
0x180064842  mov     r9d, edi; unsigned int
0x180064845  mov     r8d, 3EDh; char *
0x18006484b  lea     rdx, aAddsystempoolt; "AddSystemPoolTags"
0x180064852  mov     ecx, 2; this
0x180064857  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18006485c  jmp     short loc_180064860
0x18006485e  xor     edi, edi
0x180064860  mov     rcx, rbx; Block
0x180064863  call    cs:__imp_free
0x180064869  mov     eax, edi
0x18006486b  add     rsp, 70h
0x18006486f  pop     r15
0x180064871  pop     r14
0x180064873  pop     rdi
0x180064874  pop     rsi
0x180064875  pop     rbx
0x180064876  retn
```
