# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)

- ea: `0x18007fb4c`
- end: `0x18007ff76`
- name: `?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z`
- size: `1066`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *this, struct IQueryRecentWinSATAssessment *, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002, char, unsigned __int16 *, union _LARGE_INTEGER, unsigned int, __int16)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007ff7c`

## callees

- `0x180008330`
- `0x18001c458`
- `0x18001c820`
- `0x1800351c0`
- `0x180040a04`
- `0x18004aad0`
- `0x18004ece0`
- `0x18004f964`
- `0x18007e8cc`
- `0x18007fb4c`
- `0x180082d3c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007fd7d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007fe34`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007fd7d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007fe34`
- `OLEAUT32!__imp_SysFreeString` at `0x18007fbea`
- `OLEAUT32!__imp_SysFreeString` at `0x18007fce5`
- `OLEAUT32!__imp_SysFreeString` at `0x18007fd28`
- `OLEAUT32!__imp_SysFreeString` at `0x18007fbea`
- `OLEAUT32!__imp_SysFreeString` at `0x18007fce5`
- `OLEAUT32!__imp_SysFreeString` at `0x18007fd28`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
        Microsoft::Windows::Performance::CWinSATEventTraceExtender *this,
        struct IQueryRecentWinSATAssessment *a2,
        enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 a3,
        char a4,
        unsigned __int16 *a5,
        union _LARGE_INTEGER a6,
        unsigned int a7,
        __int16 a8)
{
  HRESULT (__stdcall *get_XML)(IQueryRecentWinSATAssessment *, BSTR, BSTR, IXMLDOMNodeList **); // rsi
  _QWORD *v14; // rax
  int v15; // ebx
  int v16; // ebx
  void *v17; // rbx
  unsigned int v18; // edi
  unsigned int v19; // r12d
  void **v20; // rsi
  unsigned int v21; // ebx
  _DWORD *v22; // rax
  unsigned int v23; // ebx
  unsigned int v24; // r12d
  _DWORD *v25; // rcx
  void *v26; // rdi
  __int64 v27; // [rsp+58h] [rbp-E0h] BYREF
  void *Src; // [rsp+60h] [rbp-D8h] BYREF
  __int64 v29; // [rsp+68h] [rbp-D0h] BYREF
  BSTR v30; // [rsp+70h] [rbp-C8h] BYREF
  BSTR bstrString[3]; // [rsp+78h] [rbp-C0h] BYREF
  _WORD v32[2]; // [rsp+90h] [rbp-A8h] BYREF
  char v33; // [rsp+94h] [rbp-A4h]
  char v34; // [rsp+95h] [rbp-A3h]
  __int16 v35; // [rsp+96h] [rbp-A2h]
  union _LARGE_INTEGER v36; // [rsp+A0h] [rbp-98h]
  __int128 v37; // [rsp+A8h] [rbp-90h]
  void *v38; // [rsp+D8h] [rbp-60h]
  unsigned int v39; // [rsp+E0h] [rbp-58h]
  unsigned int v40; // [rsp+E4h] [rbp-54h]

  bstrString[1] = (BSTR)-2LL;
  if ( !a2 )
    return 2147500035LL;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&Src);
  v29 = 0;
  v27 = 0;
  get_XML = a2->lpVtbl->get_XML;
  v14 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, a5);
  v15 = ((__int64 (__fastcall *)(struct IQueryRecentWinSATAssessment *, _QWORD, _QWORD, __int64 *))get_XML)(
          a2,
          *v14,
          0,
          &v29);
  SysFreeString(bstrString[0]);
  if ( v15 < 0 )
    goto LABEL_4;
  if ( !v29 )
    goto LABEL_6;
  v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 72LL))(v29, &v27);
  if ( v15 < 0 )
  {
LABEL_4:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Src);
    return (unsigned int)v15;
  }
  if ( !v27 )
  {
LABEL_6:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Src);
    return 1;
  }
  v30 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v27 + 272LL))(v27, &v30);
  if ( v16 < 0 )
  {
    SysFreeString(v30);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Src);
    return (unsigned int)v16;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&Src, v30);
  SysFreeString(v30);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  v17 = Src;
  v18 = 2 * *((_DWORD *)Src - 4) + 2;
  if ( v18 >= 8 && !*((_BYTE *)this + 33) )
  {
    v19 = 2 * *((_DWORD *)Src - 4) - 6;
    v20 = (void **)((char *)this + 72);
    if ( *((_DWORD *)this + 20) < v19 )
    {
      free(*v20);
      *v20 = 0;
      *((_DWORD *)this + 20) = 0;
      if ( !(unsigned __int8)ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(
                               (char *)this + 72,
                               v18) )
      {
LABEL_27:
        v21 = -2147024882;
        goto LABEL_32;
      }
      *((_DWORD *)this + 20) = v18;
    }
    if ( !(unsigned int)Performance::RtlCompression::CRtlCompressBuffer::operator()(
                          (int)this + 40,
                          *(_DWORD *)v20 + 8,
                          (_DWORD)v17,
                          v18,
                          (__int64)*v20 + 8,
                          v19) )
    {
      switch ( a4 )
      {
        case ' ':
          a4 = 33;
          goto LABEL_24;
        case '"':
          a4 = 35;
          goto LABEL_24;
        case '$':
          a4 = 37;
LABEL_24:
          v22 = *v20;
          *v22 = a3;
          v22[1] = v18;
          v23 = 8;
          goto LABEL_30;
      }
      v21 = -2147467263;
LABEL_32:
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Src);
      return v21;
    }
  }
  v24 = v18 + 4;
  v20 = (void **)((char *)this + 88);
  if ( *((_DWORD *)this + 24) < v18 + 4 )
  {
    free(*v20);
    *v20 = 0;
    *((_DWORD *)this + 24) = 0;
    if ( !(unsigned __int8)ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(
                             (char *)this + 88,
                             v24) )
      goto LABEL_27;
    *((_DWORD *)this + 24) = v24;
  }
  v25 = *v20;
  *v25 = a3;
  memcpy_0(v25 + 1, v17, v18);
  v23 = *((_DWORD *)this + 24);
LABEL_30:
  v26 = *v20;
  if ( v23 >= 0xFFFF )
  {
    v21 = 1;
    goto LABEL_32;
  }
  memset_0(v32, 0, 0x58u);
  v32[0] = a8;
  v36 = a6;
  v37 = *(_OWORD *)WinSATAssessmentGuid;
  v33 = a4;
  v35 = 0;
  v34 = 0;
  v38 = v26;
  v39 = v23;
  v40 = a7;
  (*(void (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
    *((_QWORD *)this + 2),
    v32,
    0,
    0);
  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Src);
  return 0;
}

```

## disassembly

```asm
0x18007fb4c  push    rbx
0x18007fb4e  push    rsi
0x18007fb4f  push    rdi
0x18007fb50  push    r12
0x18007fb52  push    r13
0x18007fb54  push    r14
0x18007fb56  push    r15
0x18007fb58  sub     rsp, 100h
0x18007fb5f  mov     [rsp+138h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18007fb6b  mov     rax, cs:__security_cookie
0x18007fb72  xor     rax, rsp
0x18007fb75  mov     [rsp+138h+var_48], rax
0x18007fb7d  mov     r15b, r9b
0x18007fb80  mov     r13d, r8d
0x18007fb83  mov     rbx, rdx
0x18007fb86  mov     r14, rcx
0x18007fb89  mov     rdi, [rsp+138h+arg_20]
0x18007fb91  xor     r12d, r12d
0x18007fb94  test    rdx, rdx
0x18007fb97  jnz     short loc_18007FBA3
0x18007fb99  mov     eax, 80004003h
0x18007fb9e  jmp     loc_18007FF53
0x18007fba3  lea     rcx, [rsp+138h+Src]; void *
0x18007fba8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18007fbad  nop
0x18007fbae  mov     [rsp+138h+var_D0], r12
0x18007fbb3  mov     [rsp+138h+var_E0], r12
0x18007fbb8  mov     rax, [rbx]
0x18007fbbb  mov     rsi, [rax+38h]
0x18007fbbf  mov     rdx, rdi; unsigned __int16 *
0x18007fbc2  lea     rcx, [rsp+138h+bstrString]; this
0x18007fbc7  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18007fbcc  nop
0x18007fbcd  lea     r9, [rsp+138h+var_D0]
0x18007fbd2  xor     r8d, r8d
0x18007fbd5  mov     rdx, [rax]
0x18007fbd8  mov     rcx, rbx
0x18007fbdb  mov     rax, rsi
0x18007fbde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fbe3  mov     ebx, eax
0x18007fbe5  mov     rcx, [rsp+138h+bstrString]; bstrString
0x18007fbea  call    cs:__imp_SysFreeString
0x18007fbf0  test    ebx, ebx
0x18007fbf2  jns     short loc_18007FC1B
0x18007fbf4  lea     rcx, [rsp+138h+var_E0]
0x18007fbf9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007fbfe  nop
0x18007fbff  lea     rcx, [rsp+138h+var_D0]
0x18007fc04  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007fc09  nop
0x18007fc0a  lea     rcx, [rsp+138h+Src]; this
0x18007fc0f  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18007fc14  mov     eax, ebx
0x18007fc16  jmp     loc_18007FF53
0x18007fc1b  mov     rcx, [rsp+138h+var_D0]
0x18007fc20  test    rcx, rcx
0x18007fc23  jnz     short loc_18007FC4F
0x18007fc25  lea     rcx, [rsp+138h+var_E0]
0x18007fc2a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007fc2f  nop
0x18007fc30  lea     rcx, [rsp+138h+var_D0]
0x18007fc35  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007fc3a  nop
0x18007fc3b  lea     rcx, [rsp+138h+Src]; this
0x18007fc40  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18007fc45  mov     eax, 1
0x18007fc4a  jmp     loc_18007FF53
0x18007fc4f  mov     rax, [rcx]
0x18007fc52  lea     rdx, [rsp+138h+var_E0]
0x18007fc57  mov     rax, [rax+48h]
0x18007fc5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fc60  mov     ebx, eax
0x18007fc62  test    eax, eax
0x18007fc64  jns     short loc_18007FC8D
0x18007fc66  lea     rcx, [rsp+138h+var_E0]
0x18007fc6b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007fc70  nop
0x18007fc71  lea     rcx, [rsp+138h+var_D0]
0x18007fc76  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007fc7b  nop
0x18007fc7c  lea     rcx, [rsp+138h+Src]; this
0x18007fc81  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18007fc86  mov     eax, ebx
0x18007fc88  jmp     loc_18007FF53
0x18007fc8d  mov     rcx, [rsp+138h+var_E0]
0x18007fc92  test    rcx, rcx
0x18007fc95  jnz     short loc_18007FCC1
0x18007fc97  lea     rcx, [rsp+138h+var_E0]
0x18007fc9c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007fca1  nop
0x18007fca2  lea     rcx, [rsp+138h+var_D0]
0x18007fca7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007fcac  nop
0x18007fcad  lea     rcx, [rsp+138h+Src]; this
0x18007fcb2  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18007fcb7  mov     eax, 1
0x18007fcbc  jmp     loc_18007FF53
0x18007fcc1  mov     [rsp+138h+var_C8], r12
0x18007fcc6  mov     rax, [rcx]
0x18007fcc9  lea     rdx, [rsp+138h+var_C8]
0x18007fcce  mov     rax, [rax+110h]
0x18007fcd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fcda  mov     ebx, eax
0x18007fcdc  test    eax, eax
0x18007fcde  jns     short loc_18007FD13
0x18007fce0  mov     rcx, [rsp+138h+var_C8]; bstrString
0x18007fce5  call    cs:__imp_SysFreeString
0x18007fceb  nop
0x18007fcec  lea     rcx, [rsp+138h+var_E0]
0x18007fcf1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007fcf6  nop
0x18007fcf7  lea     rcx, [rsp+138h+var_D0]
0x18007fcfc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007fd01  nop
0x18007fd02  lea     rcx, [rsp+138h+Src]; this
0x18007fd07  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18007fd0c  mov     eax, ebx
0x18007fd0e  jmp     loc_18007FF53
0x18007fd13  mov     rdx, [rsp+138h+var_C8]
0x18007fd18  lea     rcx, [rsp+138h+Src]
0x18007fd1d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18007fd22  nop
0x18007fd23  mov     rcx, [rsp+138h+var_C8]; bstrString
0x18007fd28  call    cs:__imp_SysFreeString
0x18007fd2e  nop
0x18007fd2f  lea     rcx, [rsp+138h+var_E0]
0x18007fd34  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007fd39  nop
0x18007fd3a  lea     rcx, [rsp+138h+var_D0]
0x18007fd3f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007fd44  nop
0x18007fd45  mov     rbx, [rsp+138h+Src]
0x18007fd4a  mov     eax, [rbx-10h]
0x18007fd4d  lea     edi, ds:2[rax*2]
0x18007fd54  mov     [rsp+138h+var_E8], r12d
0x18007fd59  cmp     edi, 8
0x18007fd5c  jb      loc_18007FE23
0x18007fd62  cmp     [r14+21h], r12b
0x18007fd66  jnz     loc_18007FE23
0x18007fd6c  lea     r12d, [rdi-8]
0x18007fd70  lea     rsi, [r14+48h]
0x18007fd74  cmp     [rsi+8], r12d
0x18007fd78  jnb     short loc_18007FDA7
0x18007fd7a  mov     rcx, [rsi]; Block
0x18007fd7d  call    cs:__imp_free
0x18007fd83  mov     qword ptr [rsi], 0
0x18007fd8a  mov     dword ptr [rsi+8], 0
0x18007fd91  mov     edx, edi
0x18007fd93  mov     rcx, rsi
0x18007fd96  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x18007fd9b  test    al, al
0x18007fd9d  jz      loc_18007FE57
0x18007fda3  mov     [r14+50h], edi
0x18007fda7  mov     rdx, [rsi]
0x18007fdaa  add     rdx, 8
0x18007fdae  lea     rcx, [r14+28h]
0x18007fdb2  mov     rax, [r14+38h]
0x18007fdb6  mov     [rsp+138h+var_F8], rax
0x18007fdbb  lea     rax, [rsp+138h+var_E8]
0x18007fdc0  mov     [rsp+138h+var_100], rax
0x18007fdc5  mov     [rsp+138h+var_110], r12d
0x18007fdca  mov     [rsp+138h+var_118], rdx
0x18007fdcf  mov     r9d, edi
0x18007fdd2  mov     r8, rbx
0x18007fdd5  call    ??RCRtlCompressBuffer@RtlCompression@Performance@@QEBAJGPEBXKPEAXKKPEAK1@Z; Performance::RtlCompression::CRtlCompressBuffer::operator()(ushort,void const *,ulong,void *,ulong,ulong,ulong *,void *)
0x18007fdda  test    eax, eax
0x18007fddc  jnz     short loc_18007FE23
0x18007fdde  mov     eax, [rsp+138h+var_E8]
0x18007fde2  cmp     eax, r12d
0x18007fde5  ja      short loc_18007FE23
0x18007fde7  add     eax, 8
0x18007fdea  mov     [rsp+138h+var_E8], eax
0x18007fdee  cmp     r15b, 20h ; ' '
0x18007fdf2  jz      short loc_18007FE11
0x18007fdf4  cmp     r15b, 22h ; '"'
0x18007fdf8  jz      short loc_18007FE0C
0x18007fdfa  cmp     r15b, 24h ; '$'
0x18007fdfe  jnz     short loc_18007FE05
0x18007fe00  mov     r15b, 25h ; '%'
0x18007fe03  jmp     short loc_18007FE14
0x18007fe05  mov     ebx, 80004001h
0x18007fe0a  jmp     short loc_18007FE8B
0x18007fe0c  mov     r15b, 23h ; '#'
0x18007fe0f  jmp     short loc_18007FE14
0x18007fe11  mov     r15b, 21h ; '!'
0x18007fe14  mov     rax, [rsi]
0x18007fe17  mov     [rax], r13d
0x18007fe1a  mov     [rax+4], edi
0x18007fe1d  mov     ebx, [rsp+138h+var_E8]
0x18007fe21  jmp     short loc_18007FE7B
0x18007fe23  lea     r12d, [rdi+4]
0x18007fe27  lea     rsi, [r14+58h]
0x18007fe2b  cmp     [rsi+8], r12d
0x18007fe2f  jnb     short loc_18007FE62
0x18007fe31  mov     rcx, [rsi]; Block
0x18007fe34  call    cs:__imp_free
0x18007fe3a  mov     qword ptr [rsi], 0
0x18007fe41  mov     dword ptr [rsi+8], 0
0x18007fe48  mov     edx, r12d
0x18007fe4b  mov     rcx, rsi
0x18007fe4e  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x18007fe53  test    al, al
0x18007fe55  jnz     short loc_18007FE5E
0x18007fe57  mov     ebx, 8007000Eh
0x18007fe5c  jmp     short loc_18007FE8B
0x18007fe5e  mov     [r14+60h], r12d
0x18007fe62  mov     rcx, [rsi]
0x18007fe65  mov     [rcx], r13d
0x18007fe68  mov     r8d, edi; Size
0x18007fe6b  add     rcx, 4; void *
0x18007fe6f  mov     rdx, rbx; Src
0x18007fe72  call    memcpy_0
0x18007fe77  mov     ebx, [r14+60h]
0x18007fe7b  mov     rdi, [rsi]
0x18007fe7e  cmp     ebx, 0FFFFh
0x18007fe84  jb      short loc_18007FE9C
0x18007fe86  mov     ebx, 1
0x18007fe8b  lea     rcx, [rsp+138h+Src]; this
0x18007fe90  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18007fe95  mov     eax, ebx
0x18007fe97  jmp     loc_18007FF53
0x18007fe9c  xor     edx, edx; Val
0x18007fe9e  lea     r8d, [rdx+58h]; Size
0x18007fea2  lea     rcx, [rsp+138h+var_A8]; void *
0x18007feaa  call    memset_0
0x18007feaf  movzx   eax, word ptr [rsp+138h+arg_38]
0x18007feb7  mov     [rsp+138h+var_A8], ax
0x18007febf  mov     rax, qword ptr [rsp+138h+arg_28]
0x18007fec7  mov     [rsp+138h+var_98], rax
0x18007fecf  movups  xmm0, xmmword ptr cs:WinSATAssessmentGuid
0x18007fed6  movdqu  [rsp+138h+var_90], xmm0
0x18007fedf  mov     [rsp+138h+var_A4], r15b
0x18007fee7  xor     eax, eax
0x18007fee9  mov     [rsp+138h+var_A2], ax
0x18007fef1  mov     [rsp+138h+var_A3], al
0x18007fef8  mov     [rsp+138h+var_60], rdi
0x18007ff00  mov     [rsp+138h+var_58], ebx
0x18007ff07  mov     eax, [rsp+138h+arg_30]
0x18007ff0e  mov     [rsp+138h+var_54], eax
0x18007ff15  mov     rcx, [r14+10h]
0x18007ff19  mov     rax, [rcx]
0x18007ff1c  xor     r9d, r9d
0x18007ff1f  xor     r8d, r8d
0x18007ff22  lea     rdx, [rsp+138h+var_A8]
0x18007ff2a  mov     rax, [rax+0C0h]
0x18007ff31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ff36  nop
0x18007ff37  lea     rcx, [rsp+138h+Src]; this
0x18007ff3c  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18007ff41  xor     eax, eax
0x18007ff43  jmp     short loc_18007FF53
0x18007ff45  lea     rcx, [rsp+138h+Src]; this
0x18007ff4a  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18007ff4f  mov     eax, dword ptr [rsp+138h+var_E0]
0x18007ff53  mov     rcx, [rsp+138h+var_48]
0x18007ff5b  xor     rcx, rsp; StackCookie
0x18007ff5e  call    __security_check_cookie
0x18007ff63  add     rsp, 100h
0x18007ff6a  pop     r15
0x18007ff6c  pop     r14
0x18007ff6e  pop     r13
0x18007ff70  pop     r12
0x18007ff72  pop     rdi
0x18007ff73  pop     rsi
0x18007ff74  pop     rbx
0x18007ff75  retn
```
