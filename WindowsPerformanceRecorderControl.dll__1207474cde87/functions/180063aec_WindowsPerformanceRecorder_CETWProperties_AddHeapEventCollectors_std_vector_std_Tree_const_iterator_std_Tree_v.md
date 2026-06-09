# WindowsPerformanceRecorder::CETWProperties::AddHeapEventCollectors(std::vector<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::CBaseProfileElement const * const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *,std::less<WindowsPerformanceRecorder::CBaseProfileElement const *>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>>,std::allocator<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::CBaseProfileElement const * const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *,std::less<WindowsPerformanceRecorder::CBaseProfileElement const *>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>>>> const &,ushort const *,WindowsPerformanceRecorder::CControlManager *,std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack,std::less<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement::CStack>> &)

- ea: `0x180063aec`
- end: `0x180063efa`
- name: `?AddHeapEventCollectors@CETWProperties@WindowsPerformanceRecorder@@AEAAJAEBV?$vector@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@V?$allocator@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@@2@@std@@PEBGPEAVCControlManager@2@AEAV?$set@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@U?$less@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@5@@4@@Z`
- size: `1038`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a92c`

## callees

- `0x180001d74`
- `0x180002478`
- `0x1800024d0`
- `0x180002568`
- `0x1800026e4`
- `0x18001e6b8`
- `0x18001e6e0`
- `0x180033b98`
- `0x180033c54`
- `0x180035084`
- `0x180037f64`
- `0x180039d24`
- `0x18004f904`
- `0x1800581cc`
- `0x180063aec`
- `0x180063f00`
- `0x180064880`

## string_xrefs

- `0x180063ba0`: `COMGUARD`
- `0x180063e2c`: `COMGUARD`
- `0x180063e7e`: `COMGUARD`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::AddHeapEventCollectors(
        __int64 a1,
        __int64 **a2,
        __int64 a3,
        struct WindowsPerformanceRecorder::CControlManager *a4,
        __int64 a5)
{
  __int64 v5; // r12
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v8; // rbx
  __int64 v9; // rsi
  signed int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // edx
  __int64 result; // rax
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v14; // rdx
  unsigned int v15; // r12d
  _DWORD *v16; // rdi
  unsigned int v17; // r15d
  const struct WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement *v18; // rdx
  int v19; // esi
  struct WindowsPerformanceRecorder::CETWProperties::CEventSession *v20; // r8
  unsigned int v21; // ecx
  WindowsPerformanceRecorder::CETWProperties *v22; // rcx
  __int64 v23; // rdx
  int v24; // edi
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v25; // rax
  __int64 v26; // rcx
  __int64 *v27; // r13
  __int64 *v28; // rax
  unsigned __int16 *v29; // rcx
  char *v30; // rsi
  char *v31; // r15
  const unsigned __int16 *SessionName; // rax
  __int64 **v33; // r9
  signed int v34; // eax
  unsigned int v35; // edi
  signed int v36; // eax
  unsigned int v37; // edi
  char *v38; // [rsp+28h] [rbp-80h]
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v39; // [rsp+30h] [rbp-78h] BYREF
  int v40; // [rsp+38h] [rbp-70h]
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v41; // [rsp+40h] [rbp-68h] BYREF
  void *v42[2]; // [rsp+48h] [rbp-60h] BYREF
  __int64 v43; // [rsp+58h] [rbp-50h]
  __int64 v44; // [rsp+60h] [rbp-48h]
  __int64 *v45; // [rsp+68h] [rbp-40h]
  __int64 v46; // [rsp+70h] [rbp-38h]
  ATL::CAtlException *v47; // [rsp+78h] [rbp-30h] BYREF

  v46 = -2;
  v5 = a3;
  v8 = 0;
  try
  {
    std::set<unsigned long>::set<unsigned long>(v42);
    v17 = 0;
    v26 = 0;
    v27 = *a2;
    v28 = a2[1];
    v45 = v28;
    while ( 1 )
    {
      v40 = v26;
      if ( v27 == v28 )
        break;
      v44 = *v27;
      v9 = *(_QWORD *)(v44 + 32);
      v43 = v9;
      if ( !v8 )
      {
        v39 = 0;
        LODWORD(v38) = *(_DWORD *)(a5 + 8);
        v10 = WindowsPerformanceRecorder::CETWProperties::CreateHeapEventSession(
                a1,
                v9,
                v5,
                *(unsigned int *)(a1 + 256),
                &v39);
        v11 = v10;
        if ( v10 < 0 )
        {
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            "AddHeapEventCollectors",
            (const char *)0x745,
            v10,
            "COMGUARD",
            v38);
          if ( v39 )
            WindowsPerformanceRecorder::CETWProperties::CEventSession::`scalar deleting destructor'(v39, v12);
          std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v42);
          return v11;
        }
        v8 = v39;
        v39 = 0;
        v41 = v8;
        v14 = *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(a1 + 16);
        if ( v14 == *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(a1 + 24) )
        {
          std::vector<WindowsPerformanceRecorder::CETWProperties::CEventSession *>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::CEventSession * const &>(
            a1 + 8,
            v14,
            &v41);
          v8 = v41;
        }
        else
        {
          *v14 = v8;
          *(_QWORD *)(a1 + 16) += 8LL;
        }
        *(_DWORD *)v8 = 3;
      }
      *((_QWORD *)v8 + 23) = *(_QWORD *)(v9 + 52);
      v15 = *(_DWORD *)(v9 + 36);
      v16 = (_DWORD *)(v9 + 16);
      LODWORD(v39) = WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement::get_Buffers((WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement *)(v9 + 16));
      if ( v17 < v15 )
        v17 = v15;
      if ( *(_BYTE *)(v9 + 32) )
      {
        if ( *(_DWORD *)(a1 + 256) == 1 )
        {
          std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v42);
          return 2147549183LL;
        }
        *(_DWORD *)(*((_QWORD *)v8 + 1) + 64LL) |= 0x100u;
      }
      WindowsPerformanceRecorder::CETWProperties::AddQPCDeltaTracking(
        (WindowsPerformanceRecorder::CETWProperties *)a1,
        (const struct WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement *)(v9 + 16),
        v8,
        a4);
      v19 = WindowsPerformanceRecorder::CETWProperties::AddMaxFileSize(
              (WindowsPerformanceRecorder::CETWProperties *)a1,
              (const struct WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement *)(v9 + 16),
              v8);
      if ( v19 < 0 )
      {
        std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v42);
        return (unsigned int)v19;
      }
      v21 = v16[13];
      if ( *((_DWORD *)v8 + 50) >= v21 )
        v21 = *((_DWORD *)v8 + 50);
      *((_DWORD *)v8 + 50) = v21;
      v22 = (WindowsPerformanceRecorder::CETWProperties *)(unsigned int)v16[14];
      if ( (_DWORD)v22 && v16[15] )
      {
        std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v42);
        return 3310880301LL;
      }
      *(_DWORD *)(*((_QWORD *)v8 + 1) + 68LL) = (_DWORD)v22;
      v24 = WindowsPerformanceRecorder::CETWProperties::AddFlushThreshold(v22, v18, v20);
      if ( v24 < 0 )
      {
        std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v42);
        return (unsigned int)v24;
      }
      if ( *(_BYTE *)(v43 + 88) )
        *(_DWORD *)(*((_QWORD *)v8 + 1) + 64LL) |= 0x80u;
      v25 = **(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v44 + 40);
      v41 = v25;
      while ( !*((_BYTE *)v25 + 25) )
      {
        std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<unsigned long>>>>(
          v42,
          **(_QWORD **)(*((_QWORD *)v25 + 4) + 24LL),
          *(_QWORD *)(*((_QWORD *)v25 + 4) + 24LL));
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(&v41);
        v25 = v41;
      }
      v26 = (unsigned int)v39 * v15 + v40;
      ++v27;
      v28 = v45;
      v5 = a3;
    }
    *(_DWORD *)(*((_QWORD *)v8 + 1) + 48LL) = v17;
    if ( v17 > 0x400 )
      *(_BYTE *)(a1 + 416) = 1;
    *(_DWORD *)(*((_QWORD *)v8 + 1) + 56LL) = (int)o_ceil_0(v26, v23);
    *(_DWORD *)(*((_QWORD *)v8 + 1) + 52LL) = *(_DWORD *)(*((_QWORD *)v8 + 1) + 56LL);
    v29 = (unsigned __int16 *)*((_QWORD *)v8 + 1);
    v30 = (char *)v29 + v29[36];
    v31 = (char *)v29 + *(unsigned int *)v29;
    if ( *(_QWORD *)(a5 + 8)
      && (SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v8),
          v34 = WindowsPerformanceRecorder::CETWProperties::AddSystemStacks(
                  a1,
                  a4,
                  SessionName,
                  (struct _TRACE_ENABLE_FLAG_EXT_HEADER *)v30,
                  v31,
                  v33),
          v35 = v34,
          v34 < 0) )
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        "AddHeapEventCollectors",
        (const char *)0x78D,
        v34,
        "COMGUARD",
        v38);
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v42);
      result = v35;
    }
    else if ( v42[1]
           && (v36 = WindowsPerformanceRecorder::CETWProperties::AddHeapProcessIds(
                       v29,
                       (struct _TRACE_ENABLE_FLAG_EXT_HEADER *)v30,
                       (unsigned __int64)v31,
                       (__int64)v42),
               v37 = v36,
               v36 < 0) )
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        "AddHeapEventCollectors",
        (const char *)0x792,
        v36,
        "COMGUARD",
        v38);
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v42);
      result = v37;
    }
    else
    {
      if ( !*((_WORD *)v30 + 1) )
        *(_DWORD *)(*((_QWORD *)v8 + 1) + 72LL) = 0;
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v42);
      result = 0;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( std::length_error )
  {
    return 2147942414LL;
  }
  catch ( ATL::CAtlException *v47 )
  {
    return *(unsigned int *)v47;
  }
  return result;
}

```

## disassembly

```asm
0x180063aec  mov     rax, rsp
0x180063aef  mov     [rax+20h], r9
0x180063af3  mov     [rax+18h], r8
0x180063af7  push    rdi
0x180063af8  push    r12
0x180063afa  push    r13
0x180063afc  push    r14
0x180063afe  push    r15
0x180063b00  sub     rsp, 80h
0x180063b07  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180063b0f  mov     [rax+8], rbx
0x180063b13  mov     [rax+10h], rsi
0x180063b17  mov     r12, r8
0x180063b1a  mov     rdi, rdx
0x180063b1d  mov     r14, rcx
0x180063b20  xor     esi, esi
0x180063b22  mov     ebx, esi
0x180063b24  lea     rcx, [rax-60h]
0x180063b28  call    ??0?$set@KU?$less@K@std@@V?$allocator@K@2@@std@@QEAA@XZ; std::set<ulong>::set<ulong>(void)
0x180063b2d  nop
0x180063b2e  mov     r15d, esi
0x180063b31  mov     ecx, esi
0x180063b33  mov     r13, [rdi]
0x180063b36  mov     rax, [rdi+8]
0x180063b3a  mov     [rsp+0A8h+var_40], rax
0x180063b3f  mov     [rsp+0A8h+var_70], ecx
0x180063b43  cmp     r13, rax
0x180063b46  jz      loc_180063D8F
0x180063b4c  mov     rax, [r13+0]
0x180063b50  mov     [rsp+0A8h+var_48], rax
0x180063b55  mov     rsi, [rax+20h]
0x180063b59  mov     [rsp+0A8h+var_50], rsi
0x180063b5e  test    rbx, rbx
0x180063b61  jnz     loc_180063C28
0x180063b67  mov     [rsp+0A8h+var_78], rbx
0x180063b6c  mov     rax, [rsp+0A8h+arg_20]
0x180063b74  mov     eax, [rax+8]
0x180063b77  mov     dword ptr [rsp+0A8h+var_80], eax; char *
0x180063b7b  lea     rax, [rsp+0A8h+var_78]
0x180063b80  mov     [rsp+0A8h+Format], rax
0x180063b85  mov     r9d, [r14+100h]
0x180063b8c  mov     r8, r12
0x180063b8f  mov     rdx, rsi
0x180063b92  mov     rcx, r14
0x180063b95  call    ?CreateHeapEventSession@CETWProperties@WindowsPerformanceRecorder@@AEBAJPEBVCHeapEventCollectorElement@2@PEBGW4__MIDL_IProfile_0001@@PEAPEAUCEventSession@12@K@Z; WindowsPerformanceRecorder::CETWProperties::CreateHeapEventSession(WindowsPerformanceRecorder::CHeapEventCollectorElement const *,ushort const *,__MIDL_IProfile_0001,WindowsPerformanceRecorder::CETWProperties::CEventSession * *,ulong)
0x180063b9a  mov     ebx, eax
0x180063b9c  test    eax, eax
0x180063b9e  jns     short loc_180063BE8
0x180063ba0  lea     rcx, aComguard; "COMGUARD"
0x180063ba7  mov     [rsp+0A8h+Format], rcx; Format
0x180063bac  mov     r9d, eax; unsigned int
0x180063baf  mov     r8d, 745h; char *
0x180063bb5  lea     rdx, aAddheapeventco; "AddHeapEventCollectors"
0x180063bbc  mov     ecx, 2; this
0x180063bc1  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180063bc6  nop
0x180063bc7  mov     rcx, [rsp+0A8h+var_78]; this
0x180063bcc  test    rcx, rcx
0x180063bcf  jz      short loc_180063BD7
0x180063bd1  call    ??_GCEventSession@CETWProperties@WindowsPerformanceRecorder@@QEAAPEAXI@Z; WindowsPerformanceRecorder::CETWProperties::CEventSession::`scalar deleting destructor'(uint)
0x180063bd6  nop
0x180063bd7  lea     rcx, [rsp+0A8h+var_60]
0x180063bdc  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x180063be1  mov     eax, ebx
0x180063be3  jmp     loc_180063EDC
0x180063be8  mov     rbx, [rsp+0A8h+var_78]
0x180063bed  mov     [rsp+0A8h+var_78], 0
0x180063bf6  mov     [rsp+0A8h+var_68], rbx
0x180063bfb  lea     rcx, [r14+8]
0x180063bff  mov     rdx, [rcx+8]
0x180063c03  cmp     rdx, [rcx+10h]
0x180063c07  jz      short loc_180063C13
0x180063c09  mov     [rdx], rbx
0x180063c0c  add     qword ptr [rcx+8], 8
0x180063c11  jmp     short loc_180063C22
0x180063c13  lea     r8, [rsp+0A8h+var_68]
0x180063c18  call    ??$_Emplace_reallocate@AEBQEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@@?$vector@PEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@V?$allocator@PEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@AEAAPEAPEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@QEAPEAU234@AEBQEAU234@@Z; std::vector<WindowsPerformanceRecorder::CETWProperties::CEventSession *>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::CEventSession * const &>(WindowsPerformanceRecorder::CETWProperties::CEventSession * * const,WindowsPerformanceRecorder::CETWProperties::CEventSession * const &)
0x180063c1d  mov     rbx, [rsp+0A8h+var_68]
0x180063c22  mov     dword ptr [rbx], 3
0x180063c28  mov     rax, [rsi+34h]
0x180063c2c  mov     [rbx+0B8h], eax
0x180063c32  shr     rax, 20h
0x180063c36  mov     [rbx+0BCh], eax
0x180063c3c  mov     r12d, [rsi+24h]
0x180063c40  lea     rdi, [rsi+10h]
0x180063c44  mov     rcx, rdi; this
0x180063c47  call    ?get_Buffers@CBaseSystemAndEventCollectorElement@WindowsPerformanceRecorder@@QEBAKXZ; WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement::get_Buffers(void)
0x180063c4c  mov     dword ptr [rsp+0A8h+var_78], eax
0x180063c50  cmp     r15d, r12d
0x180063c53  cmovb   r15d, r12d
0x180063c57  cmp     byte ptr [rsi+20h], 0
0x180063c5b  jz      short loc_180063C84
0x180063c5d  cmp     dword ptr [r14+100h], 1
0x180063c65  jnz     short loc_180063C7B
0x180063c67  lea     rcx, [rsp+0A8h+var_60]
0x180063c6c  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x180063c71  mov     eax, 8000FFFFh
0x180063c76  jmp     loc_180063EDC
0x180063c7b  mov     rax, [rbx+8]
0x180063c7f  bts     dword ptr [rax+40h], 8
0x180063c84  mov     r9, [rsp+0A8h+arg_18]; struct WindowsPerformanceRecorder::CControlManager *
0x180063c8c  mov     r8, rbx; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x180063c8f  mov     rdx, rdi; struct WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement *
0x180063c92  mov     rcx, r14; this
0x180063c95  call    ?AddQPCDeltaTracking@CETWProperties@WindowsPerformanceRecorder@@AEAAJPEBVCBaseSystemAndEventCollectorElement@2@PEAUCEventSession@12@PEAVCControlManager@2@@Z; WindowsPerformanceRecorder::CETWProperties::AddQPCDeltaTracking(WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement const *,WindowsPerformanceRecorder::CETWProperties::CEventSession *,WindowsPerformanceRecorder::CControlManager *)
0x180063c9a  mov     r8, rbx; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x180063c9d  mov     rdx, rdi; struct WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement *
0x180063ca0  mov     rcx, r14; this
0x180063ca3  call    ?AddMaxFileSize@CETWProperties@WindowsPerformanceRecorder@@AEAAJPEBVCBaseSystemAndEventCollectorElement@2@PEAUCEventSession@12@@Z; WindowsPerformanceRecorder::CETWProperties::AddMaxFileSize(WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement const *,WindowsPerformanceRecorder::CETWProperties::CEventSession *)
0x180063ca8  mov     esi, eax
0x180063caa  test    eax, eax
0x180063cac  jns     short loc_180063CBF
0x180063cae  lea     rcx, [rsp+0A8h+var_60]
0x180063cb3  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x180063cb8  mov     eax, esi
0x180063cba  jmp     loc_180063EDC
0x180063cbf  mov     ecx, [rdi+34h]
0x180063cc2  mov     eax, [rbx+0C8h]
0x180063cc8  cmp     eax, ecx
0x180063cca  cmovnb  ecx, eax
0x180063ccd  mov     [rbx+0C8h], ecx
0x180063cd3  mov     ecx, [rdi+38h]; this
0x180063cd6  xor     esi, esi
0x180063cd8  test    ecx, ecx
0x180063cda  jz      short loc_180063CF5
0x180063cdc  cmp     [rdi+3Ch], esi
0x180063cdf  jz      short loc_180063CF5
0x180063ce1  lea     rcx, [rsp+0A8h+var_60]
0x180063ce6  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x180063ceb  mov     eax, 0C558062Dh
0x180063cf0  jmp     loc_180063EDC
0x180063cf5  mov     rax, [rbx+8]
0x180063cf9  mov     [rax+44h], ecx
0x180063cfc  call    ?AddFlushThreshold@CETWProperties@WindowsPerformanceRecorder@@AEAAJPEBVCBaseSystemAndEventCollectorElement@2@PEAUCEventSession@12@@Z; WindowsPerformanceRecorder::CETWProperties::AddFlushThreshold(WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement const *,WindowsPerformanceRecorder::CETWProperties::CEventSession *)
0x180063d01  mov     edi, eax
0x180063d03  test    eax, eax
0x180063d05  jns     short loc_180063D18
0x180063d07  lea     rcx, [rsp+0A8h+var_60]
0x180063d0c  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x180063d11  mov     eax, edi
0x180063d13  jmp     loc_180063EDC
0x180063d18  mov     rax, [rsp+0A8h+var_50]
0x180063d1d  cmp     [rax+58h], sil
0x180063d21  jz      short loc_180063D2C
0x180063d23  mov     rax, [rbx+8]
0x180063d27  bts     dword ptr [rax+40h], 7
0x180063d2c  mov     rax, [rsp+0A8h+var_48]
0x180063d31  mov     rax, [rax+28h]
0x180063d35  mov     rax, [rax]
0x180063d38  mov     [rsp+0A8h+var_68], rax
0x180063d3d  cmp     [rax+19h], sil
0x180063d41  jnz     short loc_180063D6C
0x180063d43  mov     rcx, [rax+20h]
0x180063d47  mov     rdx, [rcx+18h]
0x180063d4b  mov     r8, rdx
0x180063d4e  mov     rdx, [rdx]
0x180063d51  lea     rcx, [rsp+0A8h+var_60]
0x180063d56  call    ??$insert@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@std@@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAAXV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@1@0@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ulong>>>>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ulong>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ulong>>>)
0x180063d5b  lea     rcx, [rsp+0A8h+var_68]
0x180063d60  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UCCounter@CHardwareCounterElement@WindowsPerformanceRecorder@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(void)
0x180063d65  mov     rax, [rsp+0A8h+var_68]
0x180063d6a  jmp     short loc_180063D3D
0x180063d6c  imul    r12d, dword ptr [rsp+0A8h+var_78]
0x180063d72  mov     ecx, [rsp+0A8h+var_70]
0x180063d76  add     ecx, r12d
0x180063d79  add     r13, 8
0x180063d7d  mov     rax, [rsp+0A8h+var_40]
0x180063d82  mov     r12, [rsp+0A8h+arg_10]
0x180063d8a  jmp     loc_180063B3F
0x180063d8f  mov     rax, [rbx+8]
0x180063d93  mov     [rax+30h], r15d
0x180063d97  cmp     r15d, 400h
0x180063d9e  jbe     short loc_180063DA8
0x180063da0  mov     byte ptr [r14+1A0h], 1
0x180063da8  mov     eax, ecx
0x180063daa  xorps   xmm0, xmm0
0x180063dad  cvtsi2sd xmm0, rax
0x180063db2  mov     eax, r15d
0x180063db5  xorps   xmm1, xmm1
0x180063db8  cvtsi2sd xmm1, rax
0x180063dbd  divsd   xmm0, xmm1
0x180063dc1  call    _o_ceil_0
0x180063dc6  cvttsd2si rcx, xmm0
0x180063dcb  mov     rax, [rbx+8]
0x180063dcf  mov     [rax+38h], ecx
0x180063dd2  mov     rcx, [rbx+8]
0x180063dd6  mov     eax, [rcx+38h]
0x180063dd9  mov     [rcx+34h], eax
0x180063ddc  mov     rcx, [rbx+8]
0x180063de0  movzx   esi, word ptr [rcx+48h]
0x180063de4  add     rsi, rcx
0x180063de7  mov     r15d, [rcx]
0x180063dea  add     r15, rcx
0x180063ded  mov     r9, [rsp+0A8h+arg_20]
0x180063df5  xor     r12d, r12d
0x180063df8  cmp     [r9+8], r12
0x180063dfc  jz      short loc_180063E61
0x180063dfe  mov     rcx, rbx; this
0x180063e01  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180063e06  mov     r8, rax; int
0x180063e09  mov     [rsp+0A8h+var_80], r9; char *
0x180063e0e  mov     [rsp+0A8h+Format], r15; void *
0x180063e13  mov     r9, rsi; int
0x180063e16  mov     rdx, [rsp+0A8h+arg_18]; int
0x180063e1e  mov     rcx, r14; int
0x180063e21  call    ?AddSystemStacks@CETWProperties@WindowsPerformanceRecorder@@AEBAJPEAVCControlManager@2@PEBGPEAU_TRACE_ENABLE_FLAG_EXT_HEADER@@PEBXAEBV?$set@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@U?$less@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@5@@std@@@Z; WindowsPerformanceRecorder::CETWProperties::AddSystemStacks(WindowsPerformanceRecorder::CControlManager *,ushort const *,_TRACE_ENABLE_FLAG_EXT_HEADER *,void const *,std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack> const &)
0x180063e26  mov     edi, eax
0x180063e28  test    eax, eax
0x180063e2a  jns     short loc_180063E61
0x180063e2c  lea     rcx, aComguard; "COMGUARD"
0x180063e33  mov     [rsp+0A8h+Format], rcx; Format
0x180063e38  mov     r9d, eax; unsigned int
0x180063e3b  mov     r8d, 78Dh; char *
0x180063e41  lea     rdx, aAddheapeventco; "AddHeapEventCollectors"
0x180063e48  lea     ecx, [r12+2]; this
0x180063e4d  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180063e52  nop
0x180063e53  lea     rcx, [rsp+0A8h+var_60]
0x180063e58  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x180063e5d  mov     eax, edi
0x180063e5f  jmp     short loc_180063EDC
0x180063e61  cmp     [rsp+0A8h+var_58], r12
0x180063e66  jz      short loc_180063EB3
0x180063e68  lea     r9, [rsp+0A8h+var_60]
0x180063e6d  mov     r8, r15
0x180063e70  mov     rdx, rsi
0x180063e73  call    ?AddHeapProcessIds@CETWProperties@WindowsPerformanceRecorder@@AEBAJPEAU_TRACE_ENABLE_FLAG_EXT_HEADER@@PEBXAEBV?$set@KU?$less@K@std@@V?$allocator@K@2@@std@@@Z; WindowsPerformanceRecorder::CETWProperties::AddHeapProcessIds(_TRACE_ENABLE_FLAG_EXT_HEADER *,void const *,std::set<ulong> const &)
0x180063e78  mov     edi, eax
0x180063e7a  test    eax, eax
0x180063e7c  jns     short loc_180063EB3
0x180063e7e  lea     rcx, aComguard; "COMGUARD"
0x180063e85  mov     [rsp+0A8h+Format], rcx; Format
0x180063e8a  mov     r9d, eax; unsigned int
0x180063e8d  mov     r8d, 792h; char *
0x180063e93  lea     rdx, aAddheapeventco; "AddHeapEventCollectors"
0x180063e9a  mov     ecx, 2; this
0x180063e9f  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180063ea4  nop
0x180063ea5  lea     rcx, [rsp+0A8h+var_60]
0x180063eaa  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x180063eaf  mov     eax, edi
0x180063eb1  jmp     short loc_180063EDC
0x180063eb3  cmp     [rsi+2], r12w
0x180063eb8  jnz     short loc_180063EC2
0x180063eba  mov     rax, [rbx+8]
0x180063ebe  mov     [rax+48h], r12d
0x180063ec2  lea     rcx, [rsp+0A8h+var_60]
0x180063ec7  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x180063ecc  nop
0x180063ecd  xor     eax, eax
0x180063ecf  jmp     short loc_180063EDC
0x180063ed1  mov     eax, 8007000Eh
0x180063ed6  jmp     short loc_180063EDC
0x180063ed8  mov     eax, dword ptr [rsp+0A8h+var_78]
0x180063edc  lea     r11, [rsp+0A8h+var_28]
0x180063ee4  mov     rbx, [r11+30h]
0x180063ee8  mov     rsi, [r11+38h]
0x180063eec  mov     rsp, r11
0x180063eef  pop     r15
0x180063ef1  pop     r14
0x180063ef3  pop     r13
0x180063ef5  pop     r12
0x180063ef7  pop     rdi
0x180063ef8  retn
```
