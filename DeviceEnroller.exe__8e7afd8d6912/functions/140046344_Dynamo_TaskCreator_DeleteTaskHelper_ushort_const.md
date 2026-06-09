# Dynamo::TaskCreator::DeleteTaskHelper(ushort const *)

- ea: `0x140046344`
- end: `0x140046662`
- name: `?DeleteTaskHelper@TaskCreator@Dynamo@@AEAAXPEBG@Z`
- size: `798`
- prototype: `void __fastcall(Dynamo::TaskCreator *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400462f0`
- `0x140046310`
- `0x140046330`
- `0x140046670`

## callees

- `0x140005ea8`
- `0x14000a6e4`
- `0x140046344`
- `0x140046694`
- `0x140046a68`
- `0x14005890c`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14004654b`
- `OLEAUT32!__imp_SysFreeString` at `0x14004654b`
- `OLEAUT32!__imp_VariantInit` at `0x140046400`
- `OLEAUT32!__imp_VariantInit` at `0x140046417`
- `OLEAUT32!__imp_VariantInit` at `0x14004642f`
- `OLEAUT32!__imp_VariantInit` at `0x140046446`
- `OLEAUT32!__imp_VariantInit` at `0x140046400`
- `OLEAUT32!__imp_VariantInit` at `0x140046417`
- `OLEAUT32!__imp_VariantInit` at `0x14004642f`
- `OLEAUT32!__imp_VariantInit` at `0x140046446`
- `OLEAUT32!__imp_VariantClear` at `0x1400464b4`
- `OLEAUT32!__imp_VariantClear` at `0x1400464c7`
- `OLEAUT32!__imp_VariantClear` at `0x1400464da`
- `OLEAUT32!__imp_VariantClear` at `0x1400464ec`
- `OLEAUT32!__imp_VariantClear` at `0x1400464b4`
- `OLEAUT32!__imp_VariantClear` at `0x1400464c7`
- `OLEAUT32!__imp_VariantClear` at `0x1400464da`
- `OLEAUT32!__imp_VariantClear` at `0x1400464ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400463d9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400463d9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400465b6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400465b6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140046389`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140046389`

## string_xrefs

- `0x1400465f1`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140046606`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x14004661b`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140046630`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
void __fastcall Dynamo::TaskCreator::DeleteTaskHelper(Dynamo::TaskCreator *this, const unsigned __int16 *a2)
{
  HRESULT v4; // eax
  BOOL v5; // ebx
  __int64 *v6; // rax
  HRESULT Instance; // eax
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, VARIANTARG *, __int128 *, __int128 *); // rdi
  __int128 v10; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v12; // xmm8
  IRecordInfo *v13; // xmm9_8
  __int128 v14; // xmm6
  IRecordInfo *v15; // xmm7_8
  int v16; // eax
  HRESULT v17; // eax
  HRESULT v18; // eax
  HRESULT v19; // eax
  HRESULT v20; // eax
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, _QWORD, _QWORD); // rdi
  _QWORD *TaskName; // rax
  unsigned int v24; // edi
  const char *v25; // r9
  __int64 v26; // rcx
  __int64 v27; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG v32; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG v33; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG v34; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  int v36[4]; // [rsp+A0h] [rbp-60h] BYREF
  IRecordInfo *v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+C0h] [rbp-40h] BYREF
  IRecordInfo *v39; // [rsp+D0h] [rbp-30h]
  __int128 v40; // [rsp+E0h] [rbp-20h] BYREF
  IRecordInfo *v41; // [rsp+F0h] [rbp-10h]
  VARIANTARG v42; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]
  __int64 v44; // [rsp+1C8h] [rbp+C8h] BYREF

  v4 = CoInitializeEx(0, 0);
  v5 = v4 >= 0;
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x118,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  v44 = 0;
  v6 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(&v44);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)v6);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x11B,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  v8 = v44;
  v9 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v44 + 80LL);
  VariantInit(&pvarg);
  v10 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v34);
  v12 = *(_OWORD *)&v34.vt;
  v13 = v34.pRecInfo;
  VariantInit(&v33);
  v14 = *(_OWORD *)&v33.vt;
  v15 = v33.pRecInfo;
  VariantInit(&v32);
  *(_OWORD *)v36 = v10;
  v37 = pRecInfo;
  v38 = v12;
  v39 = v13;
  v40 = v14;
  v41 = v15;
  v42 = v32;
  v16 = v9(v8, &v42, &v40, &v38);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x11C,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v16,
      (int)v36);
  v17 = VariantClear(&v32);
  if ( v17 < 0 )
    _com_issue_error(v17);
  v18 = VariantClear(&v33);
  if ( v18 < 0 )
    _com_issue_error(v18);
  v19 = VariantClear(&v34);
  if ( v19 < 0 )
    _com_issue_error(v19);
  v20 = VariantClear(&pvarg);
  if ( v20 < 0 )
    _com_issue_error(v20);
  anonymous_namespace_::GetTaskFolder(&v30, v44, *((_QWORD *)this + 1));
  v21 = v30;
  v22 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v30 + 120LL);
  TaskName = (_QWORD *)anonymous_namespace_::GetTaskName(&bstrString, *((_QWORD *)this + 2), a2);
  v24 = v22(v21, *TaskName, 0);
  if ( bstrString )
    SysFreeString(bstrString);
  v25 = 0;
  if ( v24 != -2147024894 )
    v25 = (const char *)v24;
  if ( (int)v25 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x121,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      v25,
      (int)v36);
  v26 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  if ( v5 )
    CoUninitialize();
}

```

## disassembly

```asm
0x140046344  mov     rax, rsp
0x140046347  mov     [rax+8], rbx
0x14004634b  push    rbp
0x14004634c  push    rsi
0x14004634d  push    rdi
0x14004634e  push    r14
0x140046350  push    r15
0x140046352  lea     rbp, [rsp-80h]
0x140046357  sub     rsp, 180h
0x14004635e  movaps  xmmword ptr [rax-38h], xmm6
0x140046362  movaps  xmmword ptr [rax-48h], xmm7
0x140046366  movaps  xmmword ptr [rax-58h], xmm8
0x14004636b  movaps  xmmword ptr [rax-68h], xmm9
0x140046370  movaps  xmmword ptr [rax-78h], xmm10
0x140046375  movaps  xmmword ptr [rax-88h], xmm11
0x14004637d  mov     r15, rdx
0x140046380  mov     r14, rcx
0x140046383  xor     ebx, ebx
0x140046385  xor     edx, edx; dwCoInit
0x140046387  xor     ecx, ecx; pvReserved
0x140046389  call    cs:__imp_CoInitializeEx
0x14004638f  lea     edi, [rbx+1]
0x140046392  test    eax, eax
0x140046394  cmovns  ebx, edi
0x140046397  mov     [rbp+0A0h+arg_10], ebx
0x14004639d  mov     rcx, [rbp+0A8h]; this
0x1400463a4  js      loc_140046603
0x1400463aa  mov     [rbp+0A0h+arg_18], 0
0x1400463b5  lea     rcx, [rbp+0A0h+arg_18]
0x1400463bc  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x1400463c1  mov     qword ptr [rsp+1A0h+ppv], rax; int
0x1400463c6  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1400463cd  mov     r8d, edi; dwClsContext
0x1400463d0  xor     edx, edx; pUnkOuter
0x1400463d2  lea     rcx, CLSID_TaskScheduler; rclsid
0x1400463d9  call    cs:__imp_CoCreateInstance
0x1400463df  mov     rcx, [rbp+0A8h]; this
0x1400463e6  test    eax, eax
0x1400463e8  js      loc_140046618
0x1400463ee  mov     rsi, [rbp+0A0h+arg_18]
0x1400463f5  mov     rax, [rsi]
0x1400463f8  mov     rdi, [rax+50h]
0x1400463fc  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x140046400  call    cs:__imp_VariantInit
0x140046406  nop
0x140046407  movups  xmm10, xmmword ptr [rbp+0A0h+pvarg]
0x14004640c  movsd   xmm11, qword ptr [rbp+0A0h+pvarg+10h]
0x140046412  lea     rcx, [rsp+1A0h+var_130]; pvarg
0x140046417  call    cs:__imp_VariantInit
0x14004641d  nop
0x14004641e  movups  xmm8, xmmword ptr [rsp+1A0h+var_130]
0x140046424  movsd   xmm9, qword ptr [rbp+0A0h+var_130+10h]
0x14004642a  lea     rcx, [rsp+1A0h+var_148]; pvarg
0x14004642f  call    cs:__imp_VariantInit
0x140046435  nop
0x140046436  movups  xmm6, xmmword ptr [rsp+1A0h+var_148]
0x14004643b  movsd   xmm7, qword ptr [rsp+1A0h+var_148+10h]
0x140046441  lea     rcx, [rsp+1A0h+var_160]; pvarg
0x140046446  call    cs:__imp_VariantInit
0x14004644c  nop
0x14004644d  movups  xmm0, xmmword ptr [rsp+1A0h+var_160]
0x140046452  movsd   xmm1, qword ptr [rsp+1A0h+var_160+10h]
0x140046458  movaps  xmmword ptr [rbp+0A0h+var_100], xmm10
0x14004645d  movsd   [rbp+0A0h+var_F0], xmm11
0x140046463  movaps  [rbp+0A0h+var_E0], xmm8
0x140046468  movsd   [rbp+0A0h+var_D0], xmm9
0x14004646e  movaps  [rbp+0A0h+var_C0], xmm6
0x140046472  movsd   [rbp+0A0h+var_B0], xmm7
0x140046477  movaps  [rbp+0A0h+var_A0], xmm0
0x14004647b  movsd   [rbp+0A0h+var_90], xmm1
0x140046480  lea     rax, [rbp+0A0h+var_100]
0x140046484  mov     qword ptr [rsp+1A0h+ppv], rax; int
0x140046489  lea     r9, [rbp+0A0h+var_E0]
0x14004648d  lea     r8, [rbp+0A0h+var_C0]
0x140046491  lea     rdx, [rbp+0A0h+var_A0]
0x140046495  mov     rcx, rsi
0x140046498  mov     rax, rdi
0x14004649b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400464a0  mov     rcx, [rbp+0A8h]; this
0x1400464a7  test    eax, eax
0x1400464a9  js      loc_14004662D
0x1400464af  lea     rcx, [rsp+1A0h+var_160]; pvarg
0x1400464b4  call    cs:__imp_VariantClear
0x1400464ba  test    eax, eax
0x1400464bc  js      loc_140046642
0x1400464c2  lea     rcx, [rsp+1A0h+var_148]; pvarg
0x1400464c7  call    cs:__imp_VariantClear
0x1400464cd  test    eax, eax
0x1400464cf  js      loc_14004664A
0x1400464d5  lea     rcx, [rsp+1A0h+var_130]; pvarg
0x1400464da  call    cs:__imp_VariantClear
0x1400464e0  test    eax, eax
0x1400464e2  js      loc_140046652
0x1400464e8  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x1400464ec  call    cs:__imp_VariantClear
0x1400464f2  test    eax, eax
0x1400464f4  js      loc_14004665A
0x1400464fa  mov     r8, [r14+8]
0x1400464fe  mov     rdx, [rbp+0A0h+arg_18]
0x140046505  lea     rcx, [rsp+1A0h+var_170]
0x14004650a  call    _anonymous_namespace___GetTaskFolder
0x14004650f  nop
0x140046510  mov     rsi, [rsp+1A0h+var_170]
0x140046515  mov     rax, [rsi]
0x140046518  mov     rdi, [rax+78h]
0x14004651c  mov     r8, r15
0x14004651f  mov     rdx, [r14+10h]
0x140046523  lea     rcx, [rsp+1A0h+bstrString]
0x140046528  call    _anonymous_namespace___GetTaskName
0x14004652d  nop
0x14004652e  xor     r8d, r8d
0x140046531  mov     rdx, [rax]
0x140046534  mov     rcx, rsi
0x140046537  mov     rax, rdi
0x14004653a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004653f  mov     edi, eax
0x140046541  mov     rcx, [rsp+1A0h+bstrString]; bstrString
0x140046546  test    rcx, rcx
0x140046549  jz      short loc_140046551
0x14004654b  call    cs:__imp_SysFreeString
0x140046551  xor     r9d, r9d
0x140046554  cmp     edi, 80070002h
0x14004655a  cmovnz  r9d, edi; char *
0x14004655e  mov     rcx, [rbp+0A8h]; this
0x140046565  test    r9d, r9d
0x140046568  js      loc_1400465F1
0x14004656e  mov     rcx, [rsp+1A0h+var_170]
0x140046573  test    rcx, rcx
0x140046576  jz      short loc_14004658E
0x140046578  mov     [rsp+1A0h+var_170], 0
0x140046581  mov     rax, [rcx]
0x140046584  mov     rax, [rax+10h]
0x140046588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004658d  nop
0x14004658e  mov     rcx, [rbp+0A0h+arg_18]
0x140046595  test    rcx, rcx
0x140046598  jz      short loc_1400465B2
0x14004659a  mov     [rbp+0A0h+arg_18], 0
0x1400465a5  mov     rax, [rcx]
0x1400465a8  mov     rax, [rax+10h]
0x1400465ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400465b1  nop
0x1400465b2  test    ebx, ebx
0x1400465b4  jz      short loc_1400465BC
0x1400465b6  call    cs:__imp_CoUninitialize
0x1400465bc  lea     r11, [rsp+1A0h+var_20]
0x1400465c4  mov     rbx, [r11+30h]
0x1400465c8  movaps  xmm6, xmmword ptr [r11-10h]
0x1400465cd  movaps  xmm7, xmmword ptr [r11-20h]
0x1400465d2  movaps  xmm8, xmmword ptr [r11-30h]
0x1400465d7  movaps  xmm9, xmmword ptr [r11-40h]
0x1400465dc  movaps  xmm10, xmmword ptr [r11-50h]
0x1400465e1  movaps  xmm11, xmmword ptr [r11-60h]
0x1400465e6  mov     rsp, r11
0x1400465e9  pop     r15
0x1400465eb  pop     r14
0x1400465ed  pop     rdi
0x1400465ee  pop     rsi
0x1400465ef  pop     rbp
0x1400465f0  retn
0x1400465f1  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400465f8  mov     edx, 121h; void *
0x1400465fd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140046603  mov     r9d, eax; char *
0x140046606  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14004660d  mov     edx, 118h; void *
0x140046612  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140046618  mov     r9d, eax; char *
0x14004661b  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140046622  mov     edx, 11Bh; void *
0x140046627  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14004662d  mov     r9d, eax; char *
0x140046630  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140046637  mov     edx, 11Ch; void *
0x14004663c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140046642  mov     ecx, eax; int
0x140046644  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14004664a  mov     ecx, eax; int
0x14004664c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140046652  mov     ecx, eax; int
0x140046654  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14004665a  mov     ecx, eax; int
0x14004665c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
