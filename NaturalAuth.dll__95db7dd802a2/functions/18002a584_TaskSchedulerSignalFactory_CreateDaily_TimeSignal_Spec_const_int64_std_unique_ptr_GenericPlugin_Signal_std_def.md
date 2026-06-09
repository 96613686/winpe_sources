# TaskSchedulerSignalFactory::CreateDaily(TimeSignal::Spec const &,__int64,std::unique_ptr<GenericPlugin::Signal,std::default_delete<GenericPlugin::Signal>> *)

- ea: `0x18002a584`
- end: `0x18002a8dc`
- name: `?CreateDaily@TaskSchedulerSignalFactory@@AEAAJAEBUSpec@TimeSignal@@_JPEAV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@Z`
- size: `856`
- prototype: `__int64 __fastcall(__int64, __int64, IRecordInfo *, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a400`

## callees

- `0x180004880`
- `0x180012b0c`
- `0x180014e7c`
- `0x18001fb2c`
- `0x18002072c`
- `0x180028a1c`
- `0x180028da0`
- `0x1800295b0`
- `0x180029a08`
- `0x18002a01c`
- `0x18002a584`
- `0x18002b17c`
- `0x18002bbac`
- `0x18002be88`
- `0x18002bfac`
- `0x18002cda8`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18002a6a2`
- `OLEAUT32!__imp_VariantClear` at `0x18002a6c1`
- `OLEAUT32!__imp_VariantClear` at `0x18002a6a2`
- `OLEAUT32!__imp_VariantClear` at `0x18002a6c1`

## string_xrefs

- `0x18002a750`: `taskService->Connect({}, {}, {}, {})`
- `0x18002a78a`: `GetTaskFolder(&folder)`
- `0x18002a7ee`: `RegisterTask( specification.daily.startTime, TimeSignal::Repeat::Daily, TaskSchedulerSignal::NO_DAY_BIT, folder, taskNames[0])`
- `0x18002a856`: `RegisterTask( specification.daily.endTime, TimeSignal::Repeat::Daily, TaskSchedulerSignal::NO_DAY_BIT, folder, taskNames[1])`

## pseudocode

```c
__int64 __fastcall TaskSchedulerSignalFactory::CreateDaily(__int64 a1, __int64 a2, IRecordInfo *a3, __int64 a4)
{
  _bstr_t *v8; // rbx
  _bstr_t *v9; // rax
  _bstr_t *v10; // rbx
  _bstr_t *v11; // rax
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // ebx
  int TaskFolder; // eax
  __int64 **v16; // rbx
  int v17; // eax
  __int64 **v18; // rbx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rax
  __m256i v23; // [rsp+30h] [rbp-D8h] BYREF
  __int64 *v24; // [rsp+50h] [rbp-B8h] BYREF
  char v25[8]; // [rsp+58h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+78h] [rbp-90h]
  VARIANTARG v28; // [rsp+88h] [rbp-80h] BYREF
  __int64 **v29; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v30[8]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v31[8]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v32[8]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v33[16]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v34; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v35; // [rsp+E8h] [rbp-20h]
  __int128 v36; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v37; // [rsp+108h] [rbp+0h]
  VARIANTARG *v38; // [rsp+168h] [rbp+60h] BYREF
  VARIANTARG *p_pvarg; // [rsp+178h] [rbp+70h] BYREF

  v38 = 0;
  v8 = _bstr_t::_bstr_t((_bstr_t *)v33, L"Timer_Begin_");
  v28.vt = 20;
  v28.llVal = (LONGLONG)a3;
  v9 = _bstr_t::_bstr_t((_bstr_t *)v32, (const struct _variant_t *)&v28);
  _bstr_t::operator+(v8, &v24, v9);
  v10 = _bstr_t::_bstr_t((_bstr_t *)v31, L"Timer_End_");
  pvarg.iVal = 20;
  pvarg.pRecInfo = a3;
  v11 = _bstr_t::_bstr_t((_bstr_t *)v30, (const struct _variant_t *)&pvarg.decVal.8);
  _bstr_t::operator+(v10, v25, v11);
  memset(&v23.m256i_u64[1], 0, 24);
  p_pvarg = &pvarg;
  v29 = &v24;
  std::vector<_bstr_t>::_Construct_n<_bstr_t const *,_bstr_t const *>(&v23.m256i_u64[1], 2, &v29, &p_pvarg);
  `eh vector destructor iterator'(&v24, 8u, 2u, (void (*)(void *))_bstr_t::~_bstr_t);
  _bstr_t::_Free((_bstr_t *)v30);
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  _bstr_t::_Free((_bstr_t *)v31);
  _bstr_t::_Free((_bstr_t *)v32);
  VariantClear(&v28);
  _bstr_t::_Free((_bstr_t *)v33);
  v24 = &v23.m256i_i64[1];
  v25[0] = 1;
  v12 = *(_QWORD *)(a1 + 8);
  memset(&v28, 0, sizeof(v28));
  *(_OWORD *)&pvarg.decVal.Lo32 = 0;
  v27 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int128 *, CY *, VARIANTARG *))(*(_QWORD *)v12 + 80LL))(
          v12,
          &v36,
          &v34,
          &pvarg.cyVal,
          &v28);
  v14 = v13;
  if ( v13 >= 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    TaskFolder = TaskSchedulerSignalFactory::GetTaskFolder(a1, &v38);
    v14 = TaskFolder;
    if ( TaskFolder >= 0 )
    {
      v16 = (__int64 **)v23.m256i_i64[1];
      p_pvarg = v38;
      if ( v38 )
        (*(void (__fastcall **)(VARIANTARG *))(*(_QWORD *)&v38->vt + 8LL))(v38);
      v17 = TaskSchedulerSignalFactory::RegisterTask(a1, a2 + 8, 0, 0, (__int64 *)&p_pvarg, v16);
      v14 = v17;
      if ( v17 >= 0 )
      {
        v18 = (__int64 **)(v23.m256i_i64[1] + 8);
        p_pvarg = v38;
        if ( v38 )
          (*(void (__fastcall **)(VARIANTARG *))(*(_QWORD *)&v38->vt + 8LL))(v38);
        v19 = TaskSchedulerSignalFactory::RegisterTask(a1, a2 + 28, 0, 0, (__int64 *)&p_pvarg, v18);
        v14 = v19;
        if ( v19 >= 0 )
        {
          v21 = TaskSchedulerSignalFactory::ConstructSignal(v20, &p_pvarg, a3, a2, &v23.m256i_u64[1]);
          std::unique_ptr<GenericPlugin::Signal>::operator=<TaskSchedulerSignal,std::default_delete<TaskSchedulerSignal>,0>(
            a4,
            v21);
          std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(&p_pvarg);
          v14 = 0;
        }
        else
        {
          LogOpFailure(
            "RegisterTask( specification.daily.endTime, TimeSignal::Repeat::Daily, TaskSchedulerSignal::NO_DAY_BIT, folde"
            "r, taskNames[1])",
            (unsigned int)v19);
          DeleteTasks((__int64 ***)&v23.m256i_i64[1]);
        }
      }
      else
      {
        LogOpFailure(
          "RegisterTask( specification.daily.startTime, TimeSignal::Repeat::Daily, TaskSchedulerSignal::NO_DAY_BIT, folde"
          "r, taskNames[0])",
          (unsigned int)v17);
        DeleteTasks((__int64 ***)&v23.m256i_i64[1]);
      }
    }
    else
    {
      LogOpFailure("GetTaskFolder(&folder)", (unsigned int)TaskFolder);
      DeleteTasks((__int64 ***)&v23.m256i_i64[1]);
    }
  }
  else
  {
    LogOpFailure("taskService->Connect({}, {}, {}, {})", (unsigned int)v13);
    DeleteTasks((__int64 ***)&v23.m256i_i64[1]);
  }
  std::vector<_bstr_t>::_Tidy(&v23.m256i_u64[1]);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  return v14;
}

```

## disassembly

```asm
0x18002a584  mov     rax, rsp
0x18002a587  mov     [rax+10h], rbx
0x18002a58b  mov     [rax+20h], rsi
0x18002a58f  push    rbp
0x18002a590  push    rdi
0x18002a591  push    r12
0x18002a593  push    r14
0x18002a595  push    r15
0x18002a597  lea     rbp, [rax-58h]
0x18002a59b  sub     rsp, 130h
0x18002a5a2  movaps  xmmword ptr [rax-38h], xmm6
0x18002a5a6  movaps  xmmword ptr [rax-48h], xmm7
0x18002a5aa  mov     r15, r9
0x18002a5ad  mov     r14, r8
0x18002a5b0  mov     rsi, rdx
0x18002a5b3  mov     rdi, rcx
0x18002a5b6  mov     [rbp+50h+arg_0], 0
0x18002a5be  lea     rdx, aTimerBegin; "Timer_Begin_"
0x18002a5c5  lea     rcx, [rbp+50h+var_90]; this
0x18002a5c9  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002a5ce  mov     rbx, rax
0x18002a5d1  mov     r12d, 14h
0x18002a5d7  mov     word ptr [rbp+50h+var_D0], r12w
0x18002a5dc  mov     qword ptr [rbp+50h+var_D0+8], r14
0x18002a5e0  lea     rdx, [rbp+50h+var_D0]; struct _variant_t *
0x18002a5e4  lea     rcx, [rbp+50h+var_98]; this
0x18002a5e8  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x18002a5ed  nop
0x18002a5ee  mov     r8, rax
0x18002a5f1  lea     rdx, [rsp+150h+var_108]
0x18002a5f6  mov     rcx, rbx
0x18002a5f9  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18002a5fe  nop
0x18002a5ff  lea     rdx, aTimerEnd; "Timer_End_"
0x18002a606  lea     rcx, [rbp+50h+var_A0]; this
0x18002a60a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002a60f  mov     rbx, rax
0x18002a612  mov     word ptr [rsp+150h+pvarg+8], r12w
0x18002a618  mov     qword ptr [rsp+150h+pvarg+10h], r14
0x18002a61d  lea     rdx, [rsp+150h+pvarg+8]; struct _variant_t *
0x18002a622  lea     rcx, [rbp+50h+var_A8]; this
0x18002a626  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x18002a62b  nop
0x18002a62c  mov     r8, rax
0x18002a62f  lea     rdx, [rsp+150h+var_100]
0x18002a634  mov     rcx, rbx
0x18002a637  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18002a63c  nop
0x18002a63d  xorps   xmm0, xmm0
0x18002a640  movdqu  xmmword ptr [rsp+150h+var_128+8], xmm0
0x18002a646  mov     [rsp+150h+var_110], 0
0x18002a64f  lea     rax, [rsp+150h+pvarg]
0x18002a654  mov     [rbp+50h+arg_10], rax
0x18002a658  lea     rax, [rsp+150h+var_108]
0x18002a65d  mov     [rbp+50h+var_B0], rax
0x18002a661  lea     r9, [rbp+50h+arg_10]
0x18002a665  lea     r8, [rbp+50h+var_B0]
0x18002a669  lea     ebx, [r12-12h]
0x18002a66e  mov     edx, ebx
0x18002a670  lea     rcx, [rsp+150h+var_128+8]
0x18002a675  call    ??$_Construct_n@PEBV_bstr_t@@PEBV1@@?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@AEAAX_K$$QEAPEBV_bstr_t@@1@Z; std::vector<_bstr_t>::_Construct_n<_bstr_t const *,_bstr_t const *>(unsigned __int64,_bstr_t const * &&,_bstr_t const * &&)
0x18002a67a  nop
0x18002a67b  lea     r9, ??1_bstr_t@@QEAA@XZ; void (*)(void *)
0x18002a682  mov     r8d, ebx; unsigned __int64
0x18002a685  lea     edx, [rbx+6]; unsigned __int64
0x18002a688  lea     rcx, [rsp+150h+var_108]; void *
0x18002a68d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002a692  nop
0x18002a693  lea     rcx, [rbp+50h+var_A8]; this
0x18002a697  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002a69c  nop
0x18002a69d  lea     rcx, [rsp+150h+pvarg+8]; pvarg
0x18002a6a2  call    cs:__imp_VariantClear
0x18002a6a8  nop
0x18002a6a9  lea     rcx, [rbp+50h+var_A0]; this
0x18002a6ad  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002a6b2  nop
0x18002a6b3  lea     rcx, [rbp+50h+var_98]; this
0x18002a6b7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002a6bc  nop
0x18002a6bd  lea     rcx, [rbp+50h+var_D0]; pvarg
0x18002a6c1  call    cs:__imp_VariantClear
0x18002a6c7  nop
0x18002a6c8  lea     rcx, [rbp+50h+var_90]; this
0x18002a6cc  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002a6d1  lea     rax, [rsp+150h+var_128+8]
0x18002a6d6  mov     [rsp+150h+var_108], rax
0x18002a6db  mov     [rsp+150h+var_100], 1
0x18002a6e0  mov     rcx, [rdi+8]
0x18002a6e4  xorps   xmm7, xmm7
0x18002a6e7  xor     eax, eax
0x18002a6e9  movq    xmm6, rax
0x18002a6ee  xorps   xmm5, xmm5
0x18002a6f1  movq    xmm4, rax
0x18002a6f6  xorps   xmm3, xmm3
0x18002a6f9  movq    xmm2, rax
0x18002a6fe  xorps   xmm1, xmm1
0x18002a701  movaps  xmmword ptr [rbp+50h+var_D0], xmm7
0x18002a705  movsd   qword ptr [rbp+50h+var_D0+10h], xmm6
0x18002a70a  movaps  xmmword ptr [rsp+150h+pvarg+8], xmm5
0x18002a70f  movsd   [rsp+150h+var_E0], xmm4
0x18002a715  movaps  [rbp+50h+var_80], xmm3
0x18002a719  movsd   [rbp+50h+var_70], xmm2
0x18002a71e  movaps  [rbp+50h+var_60], xmm1
0x18002a722  mov     [rbp+50h+var_50], rax
0x18002a726  mov     rax, [rcx]
0x18002a729  lea     rdx, [rbp+50h+var_D0]
0x18002a72d  mov     [rsp+150h+var_130], rdx
0x18002a732  lea     r9, [rsp+150h+pvarg+8]
0x18002a737  lea     r8, [rbp+50h+var_80]
0x18002a73b  lea     rdx, [rbp+50h+var_60]
0x18002a73f  mov     rax, [rax+50h]
0x18002a743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a748  mov     ebx, eax
0x18002a74a  test    eax, eax
0x18002a74c  jns     short loc_18002A76D
0x18002a74e  mov     edx, eax
0x18002a750  lea     rcx, aTaskserviceCon; "taskService->Connect({}, {}, {}, {})"
0x18002a757  call    LogOpFailure
0x18002a75c  nop
0x18002a75d  lea     rcx, [rsp+150h+var_128+8]
0x18002a762  call    DeleteTasks
0x18002a767  nop
0x18002a768  jmp     loc_18002A8A0
0x18002a76d  lea     rcx, [rbp+50h+arg_0]
0x18002a771  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a776  lea     rdx, [rbp+50h+arg_0]
0x18002a77a  mov     rcx, rdi
0x18002a77d  call    ?GetTaskFolder@TaskSchedulerSignalFactory@@AEAAJPEAV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@@Z; TaskSchedulerSignalFactory::GetTaskFolder(Microsoft::WRL::ComPtr<ITaskFolder> *)
0x18002a782  mov     ebx, eax
0x18002a784  test    eax, eax
0x18002a786  jns     short loc_18002A7A7
0x18002a788  mov     edx, eax
0x18002a78a  lea     rcx, aGettaskfolderF; "GetTaskFolder(&folder)"
0x18002a791  call    LogOpFailure
0x18002a796  nop
0x18002a797  lea     rcx, [rsp+150h+var_128+8]
0x18002a79c  call    DeleteTasks
0x18002a7a1  nop
0x18002a7a2  jmp     loc_18002A8A0
0x18002a7a7  mov     rbx, qword ptr [rsp+150h+var_128+8]
0x18002a7ac  mov     rcx, [rbp+50h+arg_0]
0x18002a7b0  mov     [rbp+50h+arg_10], rcx
0x18002a7b4  test    rcx, rcx
0x18002a7b7  jz      short loc_18002A7C6
0x18002a7b9  mov     rax, [rcx]
0x18002a7bc  mov     rax, [rax+8]
0x18002a7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7c5  nop
0x18002a7c6  xor     r9d, r9d
0x18002a7c9  lea     rdx, [rsi+8]
0x18002a7cd  mov     qword ptr [rsp+150h+var_128], rbx
0x18002a7d2  lea     rax, [rbp+50h+arg_10]
0x18002a7d6  mov     [rsp+150h+var_130], rax
0x18002a7db  xor     r8d, r8d
0x18002a7de  mov     rcx, rdi
0x18002a7e1  call    ?RegisterTask@TaskSchedulerSignalFactory@@AEAAJAEBUTime@TimeSignal@@W4Repeat@3@FV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBV_bstr_t@@@Z; TaskSchedulerSignalFactory::RegisterTask(TimeSignal::Time const &,TimeSignal::Repeat,short,Microsoft::WRL::ComPtr<ITaskFolder>,_bstr_t const &)
0x18002a7e6  mov     ebx, eax
0x18002a7e8  test    eax, eax
0x18002a7ea  jns     short loc_18002A80B
0x18002a7ec  mov     edx, eax
0x18002a7ee  lea     rcx, aRegistertaskSp; "RegisterTask( specification.daily.start"...
0x18002a7f5  call    LogOpFailure
0x18002a7fa  nop
0x18002a7fb  lea     rcx, [rsp+150h+var_128+8]
0x18002a800  call    DeleteTasks
0x18002a805  nop
0x18002a806  jmp     loc_18002A8A0
0x18002a80b  mov     rbx, qword ptr [rsp+150h+var_128+8]
0x18002a810  add     rbx, 8
0x18002a814  mov     rcx, [rbp+50h+arg_0]
0x18002a818  mov     [rbp+50h+arg_10], rcx
0x18002a81c  test    rcx, rcx
0x18002a81f  jz      short loc_18002A82E
0x18002a821  mov     rax, [rcx]
0x18002a824  mov     rax, [rax+8]
0x18002a828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a82d  nop
0x18002a82e  xor     r9d, r9d
0x18002a831  lea     rdx, [rsi+1Ch]
0x18002a835  mov     qword ptr [rsp+150h+var_128], rbx
0x18002a83a  lea     rax, [rbp+50h+arg_10]
0x18002a83e  mov     [rsp+150h+var_130], rax
0x18002a843  xor     r8d, r8d
0x18002a846  mov     rcx, rdi
0x18002a849  call    ?RegisterTask@TaskSchedulerSignalFactory@@AEAAJAEBUTime@TimeSignal@@W4Repeat@3@FV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBV_bstr_t@@@Z; TaskSchedulerSignalFactory::RegisterTask(TimeSignal::Time const &,TimeSignal::Repeat,short,Microsoft::WRL::ComPtr<ITaskFolder>,_bstr_t const &)
0x18002a84e  mov     ebx, eax
0x18002a850  test    eax, eax
0x18002a852  jns     short loc_18002A870
0x18002a854  mov     edx, eax
0x18002a856  lea     rcx, aRegistertaskSp_0; "RegisterTask( specification.daily.endTi"...
0x18002a85d  call    LogOpFailure
0x18002a862  nop
0x18002a863  lea     rcx, [rsp+150h+var_128+8]
0x18002a868  call    DeleteTasks
0x18002a86d  nop
0x18002a86e  jmp     short loc_18002A8A0
0x18002a870  lea     rax, [rsp+150h+var_128+8]
0x18002a875  mov     [rsp+150h+var_130], rax
0x18002a87a  mov     r9, rsi
0x18002a87d  mov     r8, r14
0x18002a880  lea     rdx, [rbp+50h+arg_10]
0x18002a884  call    ?ConstructSignal@TaskSchedulerSignalFactory@@AEAA?AV?$unique_ptr@VTaskSchedulerSignal@@U?$default_delete@VTaskSchedulerSignal@@@std@@@std@@_JAEBUSpec@TimeSignal@@AEBV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@3@@Z; TaskSchedulerSignalFactory::ConstructSignal(__int64,TimeSignal::Spec const &,std::vector<_bstr_t> const &)
0x18002a889  mov     rdx, rax
0x18002a88c  mov     rcx, r15
0x18002a88f  call    ??$?4VTaskSchedulerSignal@@U?$default_delete@VTaskSchedulerSignal@@@std@@$0A@@?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VTaskSchedulerSignal@@U?$default_delete@VTaskSchedulerSignal@@@std@@@1@@Z; std::unique_ptr<GenericPlugin::Signal>::operator=<TaskSchedulerSignal,std::default_delete<TaskSchedulerSignal>,0>(std::unique_ptr<TaskSchedulerSignal> &&)
0x18002a894  lea     rcx, [rbp+50h+arg_10]
0x18002a898  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x18002a89d  nop
0x18002a89e  xor     ebx, ebx
0x18002a8a0  lea     rcx, [rsp+150h+var_128+8]
0x18002a8a5  call    ?_Tidy@?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@AEAAXXZ; std::vector<_bstr_t>::_Tidy(void)
0x18002a8aa  nop
0x18002a8ab  lea     rcx, [rbp+50h+arg_0]
0x18002a8af  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a8b4  mov     eax, ebx
0x18002a8b6  lea     r11, [rsp+150h+var_20]
0x18002a8be  mov     rbx, [r11+38h]
0x18002a8c2  mov     rsi, [r11+48h]
0x18002a8c6  movaps  xmm6, xmmword ptr [r11-10h]
0x18002a8cb  movaps  xmm7, xmmword ptr [r11-20h]
0x18002a8d0  mov     rsp, r11
0x18002a8d3  pop     r15
0x18002a8d5  pop     r14
0x18002a8d7  pop     r12
0x18002a8d9  pop     rdi
0x18002a8da  pop     rbp
0x18002a8db  retn
```
