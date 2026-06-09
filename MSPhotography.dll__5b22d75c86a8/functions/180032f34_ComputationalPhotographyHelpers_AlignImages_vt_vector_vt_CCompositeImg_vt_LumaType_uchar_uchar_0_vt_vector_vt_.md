# ComputationalPhotographyHelpers::AlignImages(vt::vector<vt::CCompositeImg<vt::LumaType<uchar>,uchar>,0> &,vt::vector<vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>>,0> &,Windows::Foundation::Rect *,int,int *,int *,int *,int *,vt::vector<vt::CCompositeImg<vt::LumaType<uchar>,uchar>,0> *,vt::vector<vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>>,0> *)

- ea: `0x180032f34`
- end: `0x1800332fd`
- name: `?AlignImages@ComputationalPhotographyHelpers@@YA?AW4FusionResult@1@AEAV?$vector@V?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@$0A@@vt@@AEAV?$vector@V?$CCompositeImg@V?$UVType@E@vt@@V12@@vt@@$0A@@4@PEAURect@Foundation@Windows@@HPEAH333PEAV34@PEAV54@@Z`
- size: `969`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030a8c`
- `0x180136d1c`

## callees

- `0x180001850`
- `0x180002fe0`
- `0x180031274`
- `0x1800312d8`
- `0x180032f34`
- `0x180033310`
- `0x180086dc0`
- `0x180087034`
- `0x1800886a8`
- `0x1800a3704`
- `0x1800a3834`
- `0x1800a3a94`
- `0x1800a3c58`
- `0x1800a3da8`
- `0x1800b87a0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180033040`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x1800330ac`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180033215`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180033040`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x1800330ac`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180033215`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ComputationalPhotographyHelpers::AlignImages(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        _DWORD *a6,
        _DWORD *a7,
        _DWORD *a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v12; // rsi
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rsi
  signed int v16; // eax
  signed int v17; // edi
  int v19; // eax
  __int64 v20; // rcx
  int v21; // edi
  int v22; // ebx
  double v23; // xmm0_8
  float v24; // xmm7_4
  int v25; // ebx
  int v26; // ebx
  ParallelTasks *v27; // rcx
  void *v28; // rdx
  ParallelTasks *v29; // rcx
  int v30; // ebx
  __int64 v31; // rcx
  __int64 v32; // rcx
  unsigned int v33; // ebx
  __int64 v34; // rcx
  _DWORD v35[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B8h]
  __int64 v37; // [rsp+58h] [rbp-B0h]
  _QWORD v38[3]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v39[40]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v40[40]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v41[8]; // [rsp+C8h] [rbp-40h] BYREF
  void **v42; // [rsp+D0h] [rbp-38h]
  __int64 v43; // [rsp+D8h] [rbp-30h]
  __int64 v44; // [rsp+E0h] [rbp-28h]
  __int128 v45; // [rsp+E8h] [rbp-20h]
  __int128 v46; // [rsp+F8h] [rbp-10h]
  __int128 v47; // [rsp+108h] [rbp+0h]
  __int64 v48; // [rsp+118h] [rbp+10h]

  if ( !a3 )
    return 3;
  v12 = *(_QWORD *)(a1 + 16);
  v13 = *(_QWORD *)(a1 + 8);
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a9 && a10 )
  {
    v14 = 1;
    goto LABEL_15;
  }
  v14 = 0;
  if ( a9 || a10 )
  {
LABEL_15:
    if ( v14 != 1 )
      return 3;
  }
  v15 = 0x6DB6DB6DB6DB6DB7LL * ((v12 - v13) >> 3);
  if ( !a9
    || (int)v15 <= (unsigned __int64)(0x6DB6DB6DB6DB6DB7LL * ((__int64)(*(_QWORD *)(a9 + 16) - *(_QWORD *)(a9 + 8)) >> 3))
    && (int)v15 <= (unsigned __int64)(0x6DB6DB6DB6DB6DB7LL
                                    * ((__int64)(*(_QWORD *)(a10 + 16) - *(_QWORD *)(a10 + 8)) >> 3)) )
  {
    v16 = vt::CVTSingleton<CTaskManager>::SingletonOp(0);
    v17 = v16;
    if ( v16 < 0 )
    {
      RoTransformError((unsigned int)v16, 0, 0);
      return (unsigned int)(v17 != -2147024882) + 2;
    }
    v43 = 0;
    v42 = &vt::CTypedFeaturesRollingBuffer<vt::CFeatureTrackerFrameData>::`vftable';
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    memset(&v39[8], 0, 32);
    v19 = vt::vector<vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>,0>::resize(&v39[8], (int)v15);
    v21 = v19;
    v22 = 0;
    if ( v19 >= 0 )
    {
      if ( (unsigned int)dword_18015F098 > 5 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v20,
          (unsigned __int8 *)byte_180151E03);
      v35[0] = 0;
      v35[1] = v15;
      v36 = 1;
      LOBYTE(v37) = 1;
      *(_QWORD *)v39 = 0;
      v38[0] = v35;
      v38[1] = a1;
      v38[2] = &v39[8];
      v23 = ((double (*)(void))o_logf_0)();
      v24 = *(float *)&v23;
      v25 = (int)(float)((float)(o_logf_0() / *(float *)&v23) + 0.5);
      v26 = v25 - (int)(float)((float)(o_logf_0() / v24) + 0.5);
      if ( v26 <= 0 )
        v26 = 0;
      *(_DWORD *)v39 = v26;
      ParallelTasks::ParallelTasks((ParallelTasks *)v40);
      if ( (int)ParallelTasks::GetLogicalCoreCount(v27) < (int)v15 )
        LODWORD(v15) = ParallelTasks::GetLogicalCoreCount(v29);
      if ( (int)v15 <= 1 )
      {
        ComputationalPhotographyHelpers::Apply121DownsamplesThreadProc((ComputationalPhotographyHelpers *)v38, v28);
      }
      else
      {
        v30 = 0;
        do
        {
          ParallelTasks::StartTask(
            (ParallelTasks *)v40,
            (void (*)(void *))ComputationalPhotographyHelpers::Apply121DownsamplesThreadProc,
            (__int64)v38);
          ++v30;
        }
        while ( v30 < (int)v15 );
        ParallelTasks::WaitForAll((ParallelTasks *)v40);
      }
      ParallelTasks::~ParallelTasks((ParallelTasks *)v40);
      if ( (unsigned int)dword_18015F098 > 5 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v31,
          (unsigned __int8 *)word_180151F4A);
      if ( (unsigned int)dword_18015F098 > 5 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v31,
          (unsigned __int8 *)&word_1801519EE);
      v21 = CStackAlign::AlignImages((__int64)v41, a1, (__int64)&v39[8]);
      if ( v21 >= 0 )
      {
        if ( (unsigned int)dword_18015F098 > 5 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v32,
            (unsigned __int8 *)byte_180151D65);
        if ( (unsigned int)dword_18015F098 > 5 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v32,
            (unsigned __int8 *)&dword_180151FE4);
        v21 = CStackAlign::LocalWarpImages((unsigned int)v41, a1, a2, 1, 8, a3, a9, a10);
        if ( v21 >= 0 )
        {
          if ( (unsigned int)dword_18015F098 > 5 )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              v34,
              (unsigned __int8 *)byte_1801518AB);
          v21 = vt::CVTSingleton<CTaskManager>::SingletonOp(1);
          if ( v21 >= 0 )
          {
            v33 = 0;
            goto LABEL_50;
          }
        }
      }
      RoTransformError((unsigned int)v21, 0, 0);
      v22 = 0;
    }
    else
    {
      RoTransformError((unsigned int)v19, 0, 0);
    }
    LOBYTE(v22) = v21 != -2147024882;
    v33 = v22 + 2;
LABEL_50:
    vt::vector<vt::CImg,0>::clear(&v39[8]);
    CStackAlign::~CStackAlign((CStackAlign *)v41);
    return v33;
  }
  return 3;
}

```

## disassembly

```asm
0x180032f34  mov     rax, rsp
0x180032f37  mov     [rax+10h], rdx
0x180032f3b  push    rbp
0x180032f3c  push    rbx
0x180032f3d  push    rsi
0x180032f3e  push    rdi
0x180032f3f  push    r12
0x180032f41  push    r13
0x180032f43  push    r14
0x180032f45  push    r15
0x180032f47  lea     rbp, [rax-78h]
0x180032f4b  sub     rsp, 138h
0x180032f52  movaps  xmmword ptr [rax-58h], xmm7
0x180032f56  mov     r12, r8
0x180032f59  mov     r13, rcx
0x180032f5c  xor     edx, edx
0x180032f5e  test    r8, r8
0x180032f61  jz      loc_1800332DC
0x180032f67  mov     rsi, [rcx+10h]
0x180032f6b  mov     rcx, [rcx+8]
0x180032f6f  mov     rax, [rbp+70h+arg_20]
0x180032f76  test    rax, rax
0x180032f79  jz      short loc_180032F7D
0x180032f7b  mov     [rax], edx
0x180032f7d  mov     rax, [rbp+70h+arg_28]
0x180032f84  test    rax, rax
0x180032f87  jz      short loc_180032F8B
0x180032f89  mov     [rax], edx
0x180032f8b  mov     rax, [rbp+70h+arg_30]
0x180032f92  test    rax, rax
0x180032f95  jz      short loc_180032F99
0x180032f97  mov     [rax], edx
0x180032f99  mov     rax, [rbp+70h+arg_38]
0x180032fa0  test    rax, rax
0x180032fa3  jz      short loc_180032FA7
0x180032fa5  mov     [rax], edx
0x180032fa7  mov     r15, [rbp+70h+arg_48]
0x180032fae  mov     r14, [rbp+70h+arg_40]
0x180032fb5  test    r14, r14
0x180032fb8  jz      short loc_180032FC6
0x180032fba  test    r15, r15
0x180032fbd  jz      short loc_180032FC6
0x180032fbf  mov     eax, 1
0x180032fc4  jmp     short loc_180032FD2
0x180032fc6  mov     eax, edx
0x180032fc8  test    r14, r14
0x180032fcb  jnz     short loc_180032FD2
0x180032fcd  test    r15, r15
0x180032fd0  jz      short loc_180032FDB
0x180032fd2  cmp     eax, 1
0x180032fd5  jnz     loc_1800332DC
0x180032fdb  sub     rsi, rcx
0x180032fde  sar     rsi, 3
0x180032fe2  mov     rcx, 6DB6DB6DB6DB6DB7h
0x180032fec  imul    rsi, rcx
0x180032ff0  movsxd  rbx, esi
0x180032ff3  test    r14, r14
0x180032ff6  jz      short loc_18003302A
0x180032ff8  mov     rax, [r14+10h]
0x180032ffc  sub     rax, [r14+8]
0x180033000  sar     rax, 3
0x180033004  imul    rax, rcx
0x180033008  cmp     rbx, rax
0x18003300b  ja      loc_1800332DC
0x180033011  mov     rax, [r15+10h]
0x180033015  sub     rax, [r15+8]
0x180033019  sar     rax, 3
0x18003301d  imul    rax, rcx
0x180033021  cmp     rbx, rax
0x180033024  ja      loc_1800332DC
0x18003302a  xor     ecx, ecx
0x18003302c  call    ?SingletonOp@?$CVTSingleton@VCTaskManager@@@vt@@KAJW4eSingletonOp@12@@Z; vt::CVTSingleton<CTaskManager>::SingletonOp(vt::CVTSingleton<CTaskManager>::eSingletonOp)
0x180033031  mov     edi, eax
0x180033033  xor     ecx, ecx
0x180033035  test    eax, eax
0x180033037  jns     short loc_180033059
0x180033039  xor     r8d, r8d
0x18003303c  xor     edx, edx
0x18003303e  mov     ecx, eax
0x180033040  call    cs:__imp_RoTransformError
0x180033046  xor     eax, eax
0x180033048  cmp     edi, 8007000Eh
0x18003304e  setnz   al
0x180033051  add     eax, 2
0x180033054  jmp     loc_1800332E1
0x180033059  mov     [rbp+70h+var_A0], rcx
0x18003305d  lea     rax, ??_7?$CTypedFeaturesRollingBuffer@VCFeatureTrackerFrameData@vt@@@vt@@6B@; const vt::CTypedFeaturesRollingBuffer<vt::CFeatureTrackerFrameData>::`vftable'
0x180033064  mov     [rbp+70h+var_A8], rax
0x180033068  mov     [rbp+70h+var_98], rcx
0x18003306c  xorps   xmm0, xmm0
0x18003306f  movdqa  [rbp+70h+var_90], xmm0
0x180033074  xorps   xmm1, xmm1
0x180033077  movdqa  [rbp+70h+var_80], xmm1
0x18003307c  movdqa  [rbp+70h+var_70], xmm0
0x180033081  mov     [rbp+70h+var_60], rcx
0x180033085  movdqu  [rsp+170h+var_100+8], xmm0
0x18003308b  movdqu  [rbp+70h+var_E8], xmm1
0x180033090  mov     rdx, rbx
0x180033093  lea     rcx, [rsp+170h+var_100+8]
0x180033098  call    ?resize@?$vector@V?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@$0A@@vt@@QEAAJ_K@Z; vt::vector<vt::CCompositeImg<vt::LumaType<uchar>,uchar>,0>::resize(unsigned __int64)
0x18003309d  mov     edi, eax
0x18003309f  xor     ebx, ebx
0x1800330a1  test    eax, eax
0x1800330a3  jns     short loc_1800330B8
0x1800330a5  xor     r8d, r8d
0x1800330a8  xor     edx, edx
0x1800330aa  mov     ecx, eax
0x1800330ac  call    cs:__imp_RoTransformError
0x1800330b2  nop
0x1800330b3  jmp     loc_18003321E
0x1800330b8  mov     eax, cs:dword_18015F098
0x1800330be  cmp     eax, 5
0x1800330c1  jbe     short loc_1800330CF
0x1800330c3  lea     rdx, byte_180151E03
0x1800330ca  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800330cf  mov     dword ptr [rsp+170h+var_130], ebx
0x1800330d3  mov     dword ptr [rsp+170h+var_130+4], esi
0x1800330d7  mov     [rsp+170h+var_128], 1
0x1800330e0  mov     byte ptr [rsp+170h+var_120], 1
0x1800330e5  mov     qword ptr [rsp+170h+var_100], rbx
0x1800330ea  lea     rax, [rsp+170h+var_130]
0x1800330ef  mov     [rsp+170h+var_118], rax
0x1800330f4  mov     [rsp+170h+var_110], r13
0x1800330f9  lea     rax, [rsp+170h+var_100+8]
0x1800330fe  mov     [rsp+170h+var_108], rax
0x180033103  mov     rax, [r13+8]
0x180033107  mov     edi, [rax+0Ch]
0x18003310a  mov     ebx, [rax+10h]
0x18003310d  movss   xmm0, cs:__real@40000000
0x180033115  call    _o_logf_0
0x18003311a  movaps  xmm7, xmm0
0x18003311d  cmp     edi, ebx
0x18003311f  cmovge  edi, ebx
0x180033122  movd    xmm0, edi
0x180033126  cvtdq2ps xmm0, xmm0
0x180033129  call    _o_logf_0
0x18003312e  divss   xmm0, xmm7
0x180033132  addss   xmm0, cs:__real@3f000000
0x18003313a  cvttss2si ebx, xmm0
0x18003313e  movss   xmm0, cs:__real@43f00000
0x180033146  call    _o_logf_0
0x18003314b  divss   xmm0, xmm7
0x18003314f  addss   xmm0, cs:__real@3f000000
0x180033157  cvttss2si eax, xmm0
0x18003315b  sub     ebx, eax
0x18003315d  xor     eax, eax
0x18003315f  test    ebx, ebx
0x180033161  cmovle  ebx, eax
0x180033164  mov     dword ptr [rsp+170h+var_100], ebx
0x180033168  lea     rcx, [rbp+70h+var_D8]; this
0x18003316c  call    ??0ParallelTasks@@QEAA@XZ; ParallelTasks::ParallelTasks(void)
0x180033171  nop
0x180033172  call    ?GetLogicalCoreCount@ParallelTasks@@QEAAHXZ; ParallelTasks::GetLogicalCoreCount(void)
0x180033177  cmp     eax, esi
0x180033179  jge     short loc_180033182
0x18003317b  call    ?GetLogicalCoreCount@ParallelTasks@@QEAAHXZ; ParallelTasks::GetLogicalCoreCount(void)
0x180033180  mov     esi, eax
0x180033182  cmp     esi, 1
0x180033185  jle     short loc_1800331AF
0x180033187  xor     ebx, ebx
0x180033189  lea     r8, [rsp+170h+var_118]; void *
0x18003318e  lea     rdx, ?Apply121DownsamplesThreadProc@ComputationalPhotographyHelpers@@YAXPEAX@Z; void (*)(void *)
0x180033195  lea     rcx, [rbp+70h+var_D8]; this
0x180033199  call    ?StartTask@ParallelTasks@@QEAAXP6AXPEAX@Z0@Z; ParallelTasks::StartTask(void (*)(void *),void *)
0x18003319e  inc     ebx
0x1800331a0  cmp     ebx, esi
0x1800331a2  jl      short loc_180033189
0x1800331a4  lea     rcx, [rbp+70h+var_D8]; this
0x1800331a8  call    ?WaitForAll@ParallelTasks@@QEAAXXZ; ParallelTasks::WaitForAll(void)
0x1800331ad  jmp     short loc_1800331BA
0x1800331af  lea     rcx, [rsp+170h+var_118]; this
0x1800331b4  call    ?Apply121DownsamplesThreadProc@ComputationalPhotographyHelpers@@YAXPEAX@Z; ComputationalPhotographyHelpers::Apply121DownsamplesThreadProc(void *)
0x1800331b9  nop
0x1800331ba  lea     rcx, [rbp+70h+var_D8]; this
0x1800331be  call    ??1ParallelTasks@@QEAA@XZ; ParallelTasks::~ParallelTasks(void)
0x1800331c3  mov     eax, cs:dword_18015F098
0x1800331c9  cmp     eax, 5
0x1800331cc  jbe     short loc_1800331DA
0x1800331ce  lea     rdx, word_180151F4A
0x1800331d5  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800331da  mov     eax, cs:dword_18015F098
0x1800331e0  cmp     eax, 5
0x1800331e3  jbe     short loc_1800331F1
0x1800331e5  lea     rdx, word_1801519EE
0x1800331ec  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800331f1  mov     r9d, 1
0x1800331f7  lea     r8, [rsp+170h+var_100+8]
0x1800331fc  mov     rdx, r13
0x1800331ff  lea     rcx, [rbp+70h+var_B0]
0x180033203  call    ?AlignImages@CStackAlign@@QEAAJAEBV?$vector@V?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@$0A@@vt@@AEAV23@H@Z; CStackAlign::AlignImages(vt::vector<vt::CCompositeImg<vt::LumaType<uchar>,uchar>,0> const &,vt::vector<vt::CCompositeImg<vt::LumaType<uchar>,uchar>,0> &,int)
0x180033208  mov     edi, eax
0x18003320a  test    eax, eax
0x18003320c  jns     short loc_18003322F
0x18003320e  xor     r8d, r8d
0x180033211  xor     edx, edx
0x180033213  mov     ecx, edi
0x180033215  call    cs:__imp_RoTransformError
0x18003321b  nop
0x18003321c  xor     ebx, ebx
0x18003321e  cmp     edi, 8007000Eh
0x180033224  setnz   bl
0x180033227  add     ebx, 2
0x18003322a  jmp     loc_1800332C4
0x18003322f  mov     eax, cs:dword_18015F098
0x180033235  cmp     eax, 5
0x180033238  jbe     short loc_180033246
0x18003323a  lea     rdx, byte_180151D65
0x180033241  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180033246  mov     eax, cs:dword_18015F098
0x18003324c  cmp     eax, 5
0x18003324f  jbe     short loc_18003325D
0x180033251  lea     rdx, dword_180151FE4
0x180033258  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003325d  mov     qword ptr [rsp+170h+var_138], r15
0x180033262  mov     [rsp+170h+var_140], r14
0x180033267  mov     [rsp+170h+var_148], r12
0x18003326c  mov     dword ptr [rsp+170h+var_150], 8
0x180033274  mov     r9d, 1
0x18003327a  mov     r8, [rbp+70h+arg_8]
0x180033281  mov     rdx, r13
0x180033284  lea     rcx, [rbp+70h+var_B0]
0x180033288  call    ?LocalWarpImages@CStackAlign@@QEAAJAEAV?$vector@V?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@$0A@@vt@@AEAV?$vector@V?$CCompositeImg@V?$UVType@E@vt@@V12@@vt@@$0A@@3@HHPEAURect@Foundation@Windows@@PEAV23@PEAV43@@Z; CStackAlign::LocalWarpImages(vt::vector<vt::CCompositeImg<vt::LumaType<uchar>,uchar>,0> &,vt::vector<vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>>,0> &,int,int,Windows::Foundation::Rect *,vt::vector<vt::CCompositeImg<vt::LumaType<uchar>,uchar>,0> *,vt::vector<vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>>,0> *)
0x18003328d  mov     edi, eax
0x18003328f  test    eax, eax
0x180033291  js      loc_18003320E
0x180033297  mov     eax, cs:dword_18015F098
0x18003329d  cmp     eax, 5
0x1800332a0  jbe     short loc_1800332AE
0x1800332a2  lea     rdx, byte_1801518AB
0x1800332a9  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800332ae  mov     ecx, 1
0x1800332b3  call    ?SingletonOp@?$CVTSingleton@VCTaskManager@@@vt@@KAJW4eSingletonOp@12@@Z; vt::CVTSingleton<CTaskManager>::SingletonOp(vt::CVTSingleton<CTaskManager>::eSingletonOp)
0x1800332b8  mov     edi, eax
0x1800332ba  test    eax, eax
0x1800332bc  js      loc_18003320E
0x1800332c2  xor     ebx, ebx
0x1800332c4  lea     rcx, [rsp+170h+var_100+8]
0x1800332c9  call    ?clear@?$vector@VCImg@vt@@$0A@@vt@@QEAAXXZ; vt::vector<vt::CImg,0>::clear(void)
0x1800332ce  nop
0x1800332cf  lea     rcx, [rbp+70h+var_B0]; this
0x1800332d3  call    ??1CStackAlign@@QEAA@XZ; CStackAlign::~CStackAlign(void)
0x1800332d8  mov     eax, ebx
0x1800332da  jmp     short loc_1800332E1
0x1800332dc  mov     eax, 3
0x1800332e1  movaps  xmm7, [rsp+170h+var_58+8]
0x1800332e9  add     rsp, 138h
0x1800332f0  pop     r15
0x1800332f2  pop     r14
0x1800332f4  pop     r13
0x1800332f6  pop     r12
0x1800332f8  pop     rdi
0x1800332f9  pop     rsi
0x1800332fa  pop     rbx
0x1800332fb  pop     rbp
0x1800332fc  retn
```
