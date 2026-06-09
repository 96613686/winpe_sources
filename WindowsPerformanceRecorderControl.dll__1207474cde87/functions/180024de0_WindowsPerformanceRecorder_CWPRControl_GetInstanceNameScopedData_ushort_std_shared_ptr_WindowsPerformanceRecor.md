# WindowsPerformanceRecorder::CWPRControl::GetInstanceNameScopedData(ushort *,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData> &)

- ea: `0x180024de0`
- end: `0x180024ff3`
- name: `?GetInstanceNameScopedData@CWPRControl@WindowsPerformanceRecorder@@QEAAJPEAGAEAV?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@@Z`
- size: `531`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180025200`
- `0x180048ce0`

## callees

- `0x180008330`
- `0x18000eeb0`
- `0x18001e6e0`
- `0x180021810`
- `0x1800234f0`
- `0x180024de0`
- `0x1800251b0`
- `0x18004521c`
- `0x1800462a0`
- `0x180047170`
- `0x180047a58`
- `0x1800508b8`
- `0x1800509a0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024ebd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024ebd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024e16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024e16`

## string_xrefs

- `0x180024f3d`: `InstanceNamedScopedData(%ws)is commited`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WindowsPerformanceRecorder::CWPRControl::GetInstanceNameScopedData(__int64 a1, char *a2, __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  __int64 *v7; // rdi
  __int64 *v8; // rbx
  __int64 result; // rax
  volatile signed __int32 *v10; // rbx
  unsigned int v11; // ebx
  ATL::CAtlException *v12; // [rsp+38h] [rbp-70h] BYREF
  __int64 v13; // [rsp+40h] [rbp-68h] BYREF
  char v14; // [rsp+48h] [rbp-60h]
  _BYTE v15[8]; // [rsp+50h] [rbp-58h] BYREF
  volatile signed __int32 *v16; // [rsp+58h] [rbp-50h]
  _BYTE v17[16]; // [rsp+60h] [rbp-48h] BYREF
  __int64 v18; // [rsp+70h] [rbp-38h] BYREF
  _BYTE v19[4]; // [rsp+78h] [rbp-30h] BYREF
  int i; // [rsp+7Ch] [rbp-2Ch]
  char *v21; // [rsp+B0h] [rbp+8h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
  v13 = a1 + 128;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
  try
  {
    v14 = 1;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64 *)&v21,
      a2);
    v7 = *(__int64 **)(a1 + 168);
    v8 = (__int64 *)v7[1];
    for ( i = 0; !*((_BYTE *)v8 + 25); v8 = (__int64 *)*v8 )
    {
      if ( (int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                  v8 + 4,
                  v21) >= 0 )
        v7 = v8;
      else
        v8 += 2;
    }
    if ( *((_BYTE *)v7 + 25)
      || (int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                &v21,
                v7[4]) < 0
      || v7 == *(__int64 **)(a1 + 168) )
    {
      std::make_shared<WindowsPerformanceRecorder::CInstanceNameScopedData,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> &>(
        v15,
        &v21);
      std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>::operator=(a3, v15);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v18,
        (const void **)&v21);
      std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>(
        v19,
        a3);
      std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>,0>>::_Emplace<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>(
        a1 + 168,
        v17,
        &v18);
      std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>::~pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>((WindowsPerformanceRecorder::Status::CSessionInfo *)&v18);
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)4,
        "GetInstanceNameScopedData",
        (const char *)0x155,
        0,
        "InstanceNamedScopedData(%ws)is commited",
        v21,
        -2);
      v10 = v16;
      if ( v16 )
      {
        if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        }
      }
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v21);
      ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v13);
      result = 0;
    }
    else
    {
      std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>::operator=(a3, v7 + 5);
      ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
      LeaveCriticalSection(v6);
      v14 = 0;
      result = 0;
    }
  }
  catch ( ATL::CAtlException *v12 )
  {
    LODWORD(v21) = *(_DWORD *)v12;
    v11 = (unsigned int)v21;
    goto LABEL_16;
  }
  catch ( std::bad_alloc )
  {
    v11 = -2147024882;
LABEL_16:
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v13);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x180024de0  mov     rax, rsp
0x180024de3  push    rdi
0x180024de4  push    r14
0x180024de6  push    r15
0x180024de8  sub     rsp, 90h
0x180024def  mov     qword ptr [rax-78h], 0FFFFFFFFFFFFFFFEh
0x180024df7  mov     [rax+10h], rbx
0x180024dfb  mov     [rax+18h], rsi
0x180024dff  mov     r15, r8
0x180024e02  mov     rbx, rdx
0x180024e05  mov     r14, rcx
0x180024e08  lea     rsi, [rcx+80h]
0x180024e0f  mov     [rax-68h], rsi
0x180024e13  mov     rcx, rsi; lpCriticalSection
0x180024e16  call    cs:__imp_EnterCriticalSection
0x180024e1c  mov     [rsp+0A8h+var_60], 1
0x180024e21  mov     rdx, rbx
0x180024e24  lea     rcx, [rsp+0A8h+arg_0]
0x180024e2c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180024e31  nop
0x180024e32  mov     rdi, [r14+0A8h]
0x180024e39  mov     rbx, [rdi+8]
0x180024e3d  xor     eax, eax
0x180024e3f  mov     [rsp+0A8h+var_2C], eax
0x180024e43  cmp     [rbx+19h], al
0x180024e46  jnz     short loc_180024E73
0x180024e48  lea     rcx, [rbx+20h]
0x180024e4c  mov     rdx, [rsp+0A8h+arg_0]
0x180024e54  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x180024e59  nop
0x180024e5a  shr     eax, 1Fh
0x180024e5d  test    al, al
0x180024e5f  jz      short loc_180024E67
0x180024e61  add     rbx, 10h
0x180024e65  jmp     short loc_180024E6A
0x180024e67  mov     rdi, rbx
0x180024e6a  mov     rbx, [rbx]
0x180024e6d  cmp     byte ptr [rbx+19h], 0
0x180024e71  jz      short loc_180024E48
0x180024e73  cmp     byte ptr [rdi+19h], 0
0x180024e77  jnz     short loc_180024ECF
0x180024e79  mov     rdx, [rdi+20h]
0x180024e7d  lea     rcx, [rsp+0A8h+arg_0]
0x180024e85  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x180024e8a  nop
0x180024e8b  shr     eax, 1Fh
0x180024e8e  test    al, al
0x180024e90  jnz     short loc_180024ECF
0x180024e92  cmp     rdi, [r14+0A8h]
0x180024e99  jz      short loc_180024ECF
0x180024e9b  lea     rdx, [rdi+28h]
0x180024e9f  mov     rcx, r15
0x180024ea2  call    ??4?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>::operator=(std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData> const &)
0x180024ea7  nop
0x180024ea8  mov     rcx, [rsp+0A8h+arg_0]
0x180024eb0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180024eb4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024eb9  nop
0x180024eba  mov     rcx, rsi; lpCriticalSection
0x180024ebd  call    cs:__imp_LeaveCriticalSection
0x180024ec3  mov     [rsp+0A8h+var_60], 0
0x180024ec8  xor     eax, eax
0x180024eca  jmp     loc_180024FDA
0x180024ecf  lea     rdx, [rsp+0A8h+arg_0]
0x180024ed7  lea     rcx, [rsp+0A8h+var_58]
0x180024edc  call    ??$make_shared@UCInstanceNameScopedData@WindowsPerformanceRecorder@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@YA?AV?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@0@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::make_shared<WindowsPerformanceRecorder::CInstanceNameScopedData,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180024ee1  nop
0x180024ee2  lea     rdx, [rsp+0A8h+var_58]
0x180024ee7  mov     rcx, r15
0x180024eea  call    ??4?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>::operator=(std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData> const &)
0x180024eef  lea     rdx, [rsp+0A8h+arg_0]; void *
0x180024ef7  lea     rcx, [rsp+0A8h+var_38]; void *
0x180024efc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180024f01  mov     rdx, r15
0x180024f04  lea     rcx, [rsp+0A8h+var_30]
0x180024f09  call    ??0?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>(std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData> const &)
0x180024f0e  nop
0x180024f0f  lea     r8, [rsp+0A8h+var_38]
0x180024f14  lea     rdx, [rsp+0A8h+var_48]
0x180024f19  lea     rcx, [r14+0A8h]
0x180024f20  call    ??$_Emplace@U?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@4@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>,0>>::_Emplace<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>(std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>> &&)
0x180024f25  nop
0x180024f26  lea     rcx, [rsp+0A8h+var_38]; this
0x180024f2b  call    ??1?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@@std@@QEAA@XZ; std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>::~pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>(void)
0x180024f30  mov     rax, [rsp+0A8h+arg_0]
0x180024f38  mov     [rsp+0A8h+var_80], rax; char *
0x180024f3d  lea     rax, aInstancenameds; "InstanceNamedScopedData(%ws)is commited"
0x180024f44  mov     [rsp+0A8h+Format], rax; Format
0x180024f49  xor     r9d, r9d; unsigned int
0x180024f4c  mov     r8d, 155h; char *
0x180024f52  lea     rdx, aGetinstancenam; "GetInstanceNameScopedData"
0x180024f59  lea     ecx, [r9+4]; this
0x180024f5d  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180024f62  nop
0x180024f63  mov     rbx, [rsp+0A8h+var_50]
0x180024f68  test    rbx, rbx
0x180024f6b  jz      short loc_180024FA4
0x180024f6d  or      edi, 0FFFFFFFFh
0x180024f70  mov     eax, edi
0x180024f72  lock xadd [rbx+8], eax
0x180024f77  add     eax, edi
0x180024f79  jnz     short loc_180024FA4
0x180024f7b  mov     rax, [rbx]
0x180024f7e  mov     rcx, rbx
0x180024f81  mov     rax, [rax]
0x180024f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f89  mov     eax, edi
0x180024f8b  lock xadd [rbx+0Ch], eax
0x180024f90  add     eax, edi
0x180024f92  jnz     short loc_180024FA4
0x180024f94  mov     rax, [rbx]
0x180024f97  mov     rcx, rbx
0x180024f9a  mov     rax, [rax+8]
0x180024f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fa3  nop
0x180024fa4  lea     rcx, [rsp+0A8h+arg_0]; this
0x180024fac  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180024fb1  nop
0x180024fb2  lea     rcx, [rsp+0A8h+var_68]
0x180024fb7  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180024fbc  xor     eax, eax
0x180024fbe  jmp     short loc_180024FDA
0x180024fc0  mov     ebx, dword ptr [rsp+0A8h+arg_0]
0x180024fc7  jmp     short loc_180024FCE
0x180024fc9  mov     ebx, 8007000Eh
0x180024fce  lea     rcx, [rsp+0A8h+var_68]
0x180024fd3  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180024fd8  mov     eax, ebx
0x180024fda  lea     r11, [rsp+0A8h+var_18]
0x180024fe2  mov     rbx, [r11+28h]
0x180024fe6  mov     rsi, [r11+30h]
0x180024fea  mov     rsp, r11
0x180024fed  pop     r15
0x180024fef  pop     r14
0x180024ff1  pop     rdi
0x180024ff2  retn
```
