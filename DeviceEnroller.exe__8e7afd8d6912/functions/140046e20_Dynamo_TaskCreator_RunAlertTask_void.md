# Dynamo::TaskCreator::RunAlertTask(void)

- ea: `0x140046e20`
- end: `0x1400471db`
- name: `?RunAlertTask@TaskCreator@Dynamo@@UEAAXXZ`
- size: `955`
- prototype: `void __fastcall(Dynamo::TaskCreator *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140005ea8`
- `0x14000a6e4`
- `0x140046694`
- `0x140046a68`
- `0x140046e20`
- `0x14005890c`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14004703d`
- `OLEAUT32!__imp_SysFreeString` at `0x14004703d`
- `OLEAUT32!__imp_VariantInit` at `0x140046ed7`
- `OLEAUT32!__imp_VariantInit` at `0x140046eef`
- `OLEAUT32!__imp_VariantInit` at `0x140046f05`
- `OLEAUT32!__imp_VariantInit` at `0x140046f19`
- `OLEAUT32!__imp_VariantInit` at `0x140047056`
- `OLEAUT32!__imp_VariantInit` at `0x140046ed7`
- `OLEAUT32!__imp_VariantInit` at `0x140046eef`
- `OLEAUT32!__imp_VariantInit` at `0x140046f05`
- `OLEAUT32!__imp_VariantInit` at `0x140046f19`
- `OLEAUT32!__imp_VariantInit` at `0x140047056`
- `OLEAUT32!__imp_VariantClear` at `0x140046f87`
- `OLEAUT32!__imp_VariantClear` at `0x140046f99`
- `OLEAUT32!__imp_VariantClear` at `0x140046fab`
- `OLEAUT32!__imp_VariantClear` at `0x140046fbe`
- `OLEAUT32!__imp_VariantClear` at `0x14004709a`
- `OLEAUT32!__imp_VariantClear` at `0x140046f87`
- `OLEAUT32!__imp_VariantClear` at `0x140046f99`
- `OLEAUT32!__imp_VariantClear` at `0x140046fab`
- `OLEAUT32!__imp_VariantClear` at `0x140046fbe`
- `OLEAUT32!__imp_VariantClear` at `0x14004709a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140046eaf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140046eaf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140047114`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140047114`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140046e5f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140046e5f`

## string_xrefs

- `0x140046ff9`: `AlertTask`
- `0x140047155`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x14004716a`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x14004717f`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1400471b4`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1400471c9`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall Dynamo::TaskCreator::RunAlertTask(Dynamo::TaskCreator *this)
{
  HRESULT v2; // eax
  BOOL v3; // ebx
  __int64 *v4; // rax
  HRESULT Instance; // eax
  __int64 v6; // rsi
  __int64 (__fastcall *v7)(__int64, VARIANTARG *, __int128 *, __int128 *); // rdi
  __int128 v8; // xmm10
  IRecordInfo *v9; // xmm11_8
  __int128 v10; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v12; // xmm6
  IRecordInfo *v13; // xmm7_8
  int v14; // eax
  HRESULT v15; // eax
  HRESULT v16; // eax
  HRESULT v17; // eax
  HRESULT v18; // eax
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64 *); // rdi
  _QWORD *TaskName; // rax
  int v22; // eax
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, VARIANTARG *, _QWORD); // rdi
  int v25; // eax
  HRESULT v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  VARIANTARG pvarg; // [rsp+38h] [rbp-D0h] BYREF
  IRecordInfo *v33; // [rsp+50h] [rbp-B8h]
  BSTR bstrString; // [rsp+58h] [rbp-B0h] BYREF
  VARIANTARG v35; // [rsp+68h] [rbp-A0h] BYREF
  VARIANTARG v36; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v37; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG v38; // [rsp+B8h] [rbp-50h] BYREF
  int v39[4]; // [rsp+D8h] [rbp-30h] BYREF
  IRecordInfo *v40; // [rsp+E8h] [rbp-20h]
  __int128 v41; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v42; // [rsp+108h] [rbp+0h]
  __int128 v43; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v44; // [rsp+128h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+1C0h] [rbp+B8h]
  __int64 v46; // [rsp+1D8h] [rbp+D0h] BYREF
  __int64 v47; // [rsp+1E0h] [rbp+D8h] BYREF

  v2 = CoInitializeEx(0, 0);
  v3 = v2 >= 0;
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x107,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v2,
      ppv);
  v46 = 0;
  v4 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(&v46);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)v4);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x10A,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  v6 = v46;
  v7 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v46 + 80LL);
  VariantInit((VARIANTARG *)&pvarg.decVal.8);
  v8 = *(_OWORD *)&pvarg.decVal.Lo32;
  v9 = v33;
  VariantInit(&v38);
  v10 = *(_OWORD *)&v38.vt;
  pRecInfo = v38.pRecInfo;
  VariantInit(&v37);
  v12 = *(_OWORD *)&v37.vt;
  v13 = v37.pRecInfo;
  VariantInit(&v36);
  *(_OWORD *)v39 = v8;
  v40 = v9;
  v41 = v10;
  v42 = pRecInfo;
  v43 = v12;
  v44 = v13;
  v35 = v36;
  v14 = v7(v6, &v35, &v43, &v41);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x10B,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v14,
      (int)v39);
  v15 = VariantClear(&v36);
  if ( v15 < 0 )
    _com_issue_error(v15);
  v16 = VariantClear(&v37);
  if ( v16 < 0 )
    _com_issue_error(v16);
  v17 = VariantClear(&v38);
  if ( v17 < 0 )
    _com_issue_error(v17);
  v18 = VariantClear((VARIANTARG *)&pvarg.decVal.8);
  if ( v18 < 0 )
    _com_issue_error(v18);
  anonymous_namespace_::GetTaskFolder(&pvarg, v46, *((_QWORD *)this + 1));
  v47 = 0;
  v19 = *(_QWORD *)&pvarg.vt;
  v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)&pvarg.vt + 104LL);
  TaskName = (_QWORD *)anonymous_namespace_::GetTaskName(&bstrString, *((_QWORD *)this + 2), L"AlertTask");
  v22 = v20(v19, *TaskName, &v47);
  if ( v22 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x110,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v22,
      (int)v39);
  if ( bstrString )
    SysFreeString(bstrString);
  v23 = v47;
  v24 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, _QWORD))(*(_QWORD *)v47 + 96LL);
  VariantInit((VARIANTARG *)&pvarg.decVal.8);
  *(_OWORD *)&v35.vt = *(_OWORD *)&pvarg.decVal.Lo32;
  v35.pRecInfo = v33;
  v25 = v24(v23, &v35, 0);
  if ( v25 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x112,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v25,
      (int)v39);
  v26 = VariantClear((VARIANTARG *)&pvarg.decVal.8);
  if ( v26 < 0 )
    _com_issue_error(v26);
  v27 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = *(_QWORD *)&pvarg.vt;
  if ( *(_QWORD *)&pvarg.vt )
  {
    *(_QWORD *)&pvarg.vt = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  if ( v3 )
    CoUninitialize();
}

```

## disassembly

```asm
0x140046e20  mov     rax, rsp
0x140046e23  push    rbp
0x140046e24  push    rbx
0x140046e25  push    rsi
0x140046e26  push    rdi
0x140046e27  push    r14
0x140046e29  lea     rbp, [rax-0B8h]
0x140046e30  sub     rsp, 190h
0x140046e37  movaps  xmmword ptr [rax-38h], xmm6
0x140046e3b  movaps  xmmword ptr [rax-48h], xmm7
0x140046e3f  movaps  xmmword ptr [rax-58h], xmm8
0x140046e44  movaps  xmmword ptr [rax-68h], xmm9
0x140046e49  movaps  xmmword ptr [rax-78h], xmm10
0x140046e4e  movaps  xmmword ptr [rax-88h], xmm11
0x140046e56  mov     r14, rcx
0x140046e59  xor     ebx, ebx
0x140046e5b  xor     edx, edx; dwCoInit
0x140046e5d  xor     ecx, ecx; pvReserved
0x140046e5f  call    cs:__imp_CoInitializeEx
0x140046e65  lea     edi, [rbx+1]
0x140046e68  test    eax, eax
0x140046e6a  cmovns  ebx, edi
0x140046e6d  mov     [rbp+0B0h+arg_8], ebx
0x140046e73  mov     rcx, [rbp+0B8h]; this
0x140046e7a  js      loc_140047152
0x140046e80  mov     [rbp+0B0h+arg_10], 0
0x140046e8b  lea     rcx, [rbp+0B0h+arg_10]
0x140046e92  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x140046e97  mov     qword ptr [rsp+1B0h+ppv], rax; int
0x140046e9c  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x140046ea3  mov     r8d, edi; dwClsContext
0x140046ea6  xor     edx, edx; pUnkOuter
0x140046ea8  lea     rcx, CLSID_TaskScheduler; rclsid
0x140046eaf  call    cs:__imp_CoCreateInstance
0x140046eb5  mov     rcx, [rbp+0B8h]; this
0x140046ebc  test    eax, eax
0x140046ebe  js      loc_140047167
0x140046ec4  mov     rsi, [rbp+0B0h+arg_10]
0x140046ecb  mov     rax, [rsi]
0x140046ece  mov     rdi, [rax+50h]
0x140046ed2  lea     rcx, [rsp+1B0h+pvarg+8]; pvarg
0x140046ed7  call    cs:__imp_VariantInit
0x140046edd  nop
0x140046ede  movups  xmm10, xmmword ptr [rsp+1B0h+pvarg+8]
0x140046ee4  movsd   xmm11, [rsp+1B0h+var_168]
0x140046eeb  lea     rcx, [rbp+0B0h+var_100]; pvarg
0x140046eef  call    cs:__imp_VariantInit
0x140046ef5  nop
0x140046ef6  movups  xmm8, xmmword ptr [rbp+0B0h+var_100]
0x140046efb  movsd   xmm9, qword ptr [rbp+0B0h+var_100+10h]
0x140046f01  lea     rcx, [rbp+0B0h+var_118]; pvarg
0x140046f05  call    cs:__imp_VariantInit
0x140046f0b  nop
0x140046f0c  movups  xmm6, xmmword ptr [rbp+0B0h+var_118]
0x140046f10  movsd   xmm7, qword ptr [rbp+0B0h+var_118+10h]
0x140046f15  lea     rcx, [rbp+0B0h+var_130]; pvarg
0x140046f19  call    cs:__imp_VariantInit
0x140046f1f  nop
0x140046f20  movups  xmm0, xmmword ptr [rbp+0B0h+var_130]
0x140046f24  movsd   xmm1, qword ptr [rbp+0B0h+var_130+10h]
0x140046f29  movaps  xmmword ptr [rbp+0B0h+var_E0], xmm10
0x140046f2e  movsd   [rbp+0B0h+var_D0], xmm11
0x140046f34  movaps  [rbp+0B0h+var_C0], xmm8
0x140046f39  movsd   [rbp+0B0h+var_B0], xmm9
0x140046f3f  movaps  [rbp+0B0h+var_A0], xmm6
0x140046f43  movsd   [rbp+0B0h+var_90], xmm7
0x140046f48  movaps  xmmword ptr [rsp+1B0h+var_158+8], xmm0
0x140046f4d  movsd   [rsp+1B0h+var_140], xmm1
0x140046f53  lea     rax, [rbp+0B0h+var_E0]
0x140046f57  mov     qword ptr [rsp+1B0h+ppv], rax; int
0x140046f5c  lea     r9, [rbp+0B0h+var_C0]
0x140046f60  lea     r8, [rbp+0B0h+var_A0]
0x140046f64  lea     rdx, [rsp+1B0h+var_158+8]
0x140046f69  mov     rcx, rsi
0x140046f6c  mov     rax, rdi
0x140046f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046f74  mov     rcx, [rbp+0B8h]; this
0x140046f7b  test    eax, eax
0x140046f7d  js      loc_14004717C
0x140046f83  lea     rcx, [rbp+0B0h+var_130]; pvarg
0x140046f87  call    cs:__imp_VariantClear
0x140046f8d  test    eax, eax
0x140046f8f  js      loc_140047191
0x140046f95  lea     rcx, [rbp+0B0h+var_118]; pvarg
0x140046f99  call    cs:__imp_VariantClear
0x140046f9f  test    eax, eax
0x140046fa1  js      loc_140047199
0x140046fa7  lea     rcx, [rbp+0B0h+var_100]; pvarg
0x140046fab  call    cs:__imp_VariantClear
0x140046fb1  test    eax, eax
0x140046fb3  js      loc_1400471A1
0x140046fb9  lea     rcx, [rsp+1B0h+pvarg+8]; pvarg
0x140046fbe  call    cs:__imp_VariantClear
0x140046fc4  test    eax, eax
0x140046fc6  js      loc_1400471A9
0x140046fcc  mov     r8, [r14+8]
0x140046fd0  mov     rdx, [rbp+0B0h+arg_10]
0x140046fd7  lea     rcx, [rsp+1B0h+pvarg]
0x140046fdc  call    _anonymous_namespace___GetTaskFolder
0x140046fe1  nop
0x140046fe2  mov     [rbp+0B0h+arg_18], 0
0x140046fed  mov     rsi, qword ptr [rsp+1B0h+pvarg]
0x140046ff2  mov     rax, [rsi]
0x140046ff5  mov     rdi, [rax+68h]
0x140046ff9  lea     r8, aAlerttask; "AlertTask"
0x140047000  mov     rdx, [r14+10h]
0x140047004  lea     rcx, [rsp+1B0h+bstrString]
0x140047009  call    _anonymous_namespace___GetTaskName
0x14004700e  nop
0x14004700f  lea     r8, [rbp+0B0h+arg_18]
0x140047016  mov     rdx, [rax]
0x140047019  mov     rcx, rsi
0x14004701c  mov     rax, rdi
0x14004701f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047024  mov     rcx, [rbp+0B8h]; this
0x14004702b  test    eax, eax
0x14004702d  js      loc_1400471B1
0x140047033  mov     rcx, [rsp+1B0h+bstrString]; bstrString
0x140047038  test    rcx, rcx
0x14004703b  jz      short loc_140047043
0x14004703d  call    cs:__imp_SysFreeString
0x140047043  mov     rsi, [rbp+0B0h+arg_18]
0x14004704a  mov     rax, [rsi]
0x14004704d  mov     rdi, [rax+60h]
0x140047051  lea     rcx, [rsp+1B0h+pvarg+8]; pvarg
0x140047056  call    cs:__imp_VariantInit
0x14004705c  nop
0x14004705d  movups  xmm0, xmmword ptr [rsp+1B0h+pvarg+8]
0x140047062  movaps  xmmword ptr [rsp+1B0h+var_158+8], xmm0
0x140047067  movsd   xmm1, [rsp+1B0h+var_168]
0x14004706d  movsd   [rsp+1B0h+var_140], xmm1
0x140047073  xor     r8d, r8d
0x140047076  lea     rdx, [rsp+1B0h+var_158+8]
0x14004707b  mov     rcx, rsi
0x14004707e  mov     rax, rdi
0x140047081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047086  mov     rcx, [rbp+0B8h]; this
0x14004708d  test    eax, eax
0x14004708f  js      loc_1400471C6
0x140047095  lea     rcx, [rsp+1B0h+pvarg+8]; pvarg
0x14004709a  call    cs:__imp_VariantClear
0x1400470a0  test    eax, eax
0x1400470a2  js      loc_14004714A
0x1400470a8  mov     rcx, [rbp+0B0h+arg_18]
0x1400470af  test    rcx, rcx
0x1400470b2  jz      short loc_1400470CC
0x1400470b4  mov     [rbp+0B0h+arg_18], 0
0x1400470bf  mov     rax, [rcx]
0x1400470c2  mov     rax, [rax+10h]
0x1400470c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400470cb  nop
0x1400470cc  mov     rcx, qword ptr [rsp+1B0h+pvarg]
0x1400470d1  test    rcx, rcx
0x1400470d4  jz      short loc_1400470EC
0x1400470d6  mov     qword ptr [rsp+1B0h+pvarg], 0
0x1400470df  mov     rax, [rcx]
0x1400470e2  mov     rax, [rax+10h]
0x1400470e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400470eb  nop
0x1400470ec  mov     rcx, [rbp+0B0h+arg_10]
0x1400470f3  test    rcx, rcx
0x1400470f6  jz      short loc_140047110
0x1400470f8  mov     [rbp+0B0h+arg_10], 0
0x140047103  mov     rax, [rcx]
0x140047106  mov     rax, [rax+10h]
0x14004710a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004710f  nop
0x140047110  test    ebx, ebx
0x140047112  jz      short loc_14004711A
0x140047114  call    cs:__imp_CoUninitialize
0x14004711a  lea     r11, [rsp+1B0h+var_20]
0x140047122  movaps  xmm6, xmmword ptr [r11-10h]
0x140047127  movaps  xmm7, xmmword ptr [r11-20h]
0x14004712c  movaps  xmm8, xmmword ptr [r11-30h]
0x140047131  movaps  xmm9, xmmword ptr [r11-40h]
0x140047136  movaps  xmm10, xmmword ptr [r11-50h]
0x14004713b  movaps  xmm11, xmmword ptr [r11-60h]
0x140047140  mov     rsp, r11
0x140047143  pop     r14
0x140047145  pop     rdi
0x140047146  pop     rsi
0x140047147  pop     rbx
0x140047148  pop     rbp
0x140047149  retn
0x14004714a  mov     ecx, eax; int
0x14004714c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140047152  mov     r9d, eax; char *
0x140047155  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14004715c  mov     edx, 107h; void *
0x140047161  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140047167  mov     r9d, eax; char *
0x14004716a  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140047171  mov     edx, 10Ah; void *
0x140047176  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14004717c  mov     r9d, eax; char *
0x14004717f  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140047186  mov     edx, 10Bh; void *
0x14004718b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140047191  mov     ecx, eax; int
0x140047193  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140047199  mov     ecx, eax; int
0x14004719b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400471a1  mov     ecx, eax; int
0x1400471a3  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400471a9  mov     ecx, eax; int
0x1400471ab  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400471b1  mov     r9d, eax; char *
0x1400471b4  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400471bb  mov     edx, 110h; void *
0x1400471c0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400471c6  mov     r9d, eax; char *
0x1400471c9  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400471d0  mov     edx, 112h; void *
0x1400471d5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
