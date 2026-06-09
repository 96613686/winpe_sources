# ConnectedStorage::ChangeTaskStart(bool)

- ea: `0x18001f080`
- end: `0x18001f241`
- name: `?ChangeTaskStart@ConnectedStorage@@YAX_N@Z`
- size: `449`
- prototype: `void __fastcall(ConnectedStorage *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001ef04`

## callees

- `0x18000a040`
- `0x18000aae4`
- `0x18001f080`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f0c9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f0c9`
- `OLEAUT32!__imp_VariantInit` at `0x18001f0f3`
- `OLEAUT32!__imp_VariantInit` at `0x18001f0f3`

## string_xrefs

- `0x18001f0d3`: `CoCreateInstance(CLSID_TaskScheduler, nullptr, CLSCTX_INPROC_SERVER, IID_PPV_ARGS(&taskService))`
- `0x18001f14f`: `taskService->Connect(emptyVar, emptyVar, emptyVar, emptyVar)`
- `0x18001f194`: `taskService->GetFolder(L"\\Microsoft\\XblGameSave", &taskFolder)`
- `0x18001f1c3`: `XblGameSaveTask`
- `0x18001f1d9`: `taskFolder->GetTask(L"XblGameSaveTask", &task)`
- `0x18001f207`: `task->put_Enabled(vBool)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ConnectedStorage::ChangeTaskStart(ConnectedStorage *this)
{
  unsigned __int8 v1; // si
  HRESULT v2; // eax
  const unsigned __int16 *v3; // r8
  int v4; // eax
  const unsigned __int16 *v5; // r8
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, const wchar_t *, __int64 *); // rbx
  int v8; // eax
  const unsigned __int16 *v9; // r8
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, const wchar_t *, __int64 *); // rbx
  int v12; // eax
  const unsigned __int16 *v13; // r8
  int v14; // eax
  const unsigned __int16 *v15; // r8
  VARIANTARG pvarg; // [rsp+30h] [rbp-69h] BYREF
  VARIANTARG v17; // [rsp+50h] [rbp-49h] BYREF
  VARIANTARG v18; // [rsp+70h] [rbp-29h] BYREF
  VARIANTARG v19; // [rsp+90h] [rbp-9h] BYREF
  VARIANTARG v20; // [rsp+B0h] [rbp+17h] BYREF
  LPVOID ppv; // [rsp+108h] [rbp+6Fh] BYREF
  __int64 v22; // [rsp+110h] [rbp+77h] BYREF
  __int64 v23; // [rsp+118h] [rbp+7Fh] BYREF

  v1 = (unsigned __int8)this;
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  v2 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  if ( v2 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v2,
      (int)L"CoCreateInstance(CLSID_TaskScheduler, nullptr, CLSCTX_INPROC_SERVER, IID_PPV_ARGS(&taskService))",
      v3);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v17 = pvarg;
  v18 = pvarg;
  v19 = pvarg;
  v20 = pvarg;
  v4 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)ppv + 80LL))(
         ppv,
         &v20,
         &v19,
         &v18,
         &v17);
  if ( v4 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v4,
      (int)L"taskService->Connect(emptyVar, emptyVar, emptyVar, emptyVar)",
      v5);
  v23 = 0;
  v6 = ppv;
  v7 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  v8 = v7(v6, L"\\Microsoft\\XblGameSave", &v23);
  if ( v8 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v8,
      (int)L"taskService->GetFolder(L\"\\\\Microsoft\\\\XblGameSave\", &taskFolder)",
      v9);
  v22 = 0;
  v10 = v23;
  v11 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v23 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  v12 = v11(v10, L"XblGameSaveTask", &v22);
  if ( v12 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v12,
      (int)L"taskFolder->GetTask(L\"XblGameSaveTask\", &task)",
      v13);
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 88LL))(v22, (unsigned __int16)((v1 ^ 1) - 1));
  if ( v14 < 0 )
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v14, (int)L"task->put_Enabled(vBool)", v15);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
}

```

## disassembly

```asm
0x18001f080  push    rbp
0x18001f082  push    rbx
0x18001f083  push    rsi
0x18001f084  push    rdi
0x18001f085  push    r15
0x18001f087  lea     rbp, [rsp-37h]
0x18001f08c  sub     rsp, 0D0h
0x18001f093  mov     sil, cl
0x18001f096  mov     [rbp+57h+arg_8], 0
0x18001f09e  lea     rcx, [rbp+57h+arg_8]
0x18001f0a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001f0a7  lea     rax, [rbp+57h+arg_8]
0x18001f0ab  mov     [rsp+0F0h+ppv], rax; ppv
0x18001f0b0  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18001f0b7  mov     r15d, 1
0x18001f0bd  mov     r8d, r15d; dwClsContext
0x18001f0c0  xor     edx, edx; pUnkOuter
0x18001f0c2  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001f0c9  call    cs:__imp_CoCreateInstance
0x18001f0cf  test    eax, eax
0x18001f0d1  jns     short loc_18001F0E2
0x18001f0d3  lea     rdx, aCocreateinstan_1; "CoCreateInstance(CLSID_TaskScheduler, n"...
0x18001f0da  mov     ecx, eax; this
0x18001f0dc  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18001f0e2  xorps   xmm0, xmm0
0x18001f0e5  xor     eax, eax
0x18001f0e7  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001f0eb  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001f0ef  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001f0f3  call    cs:__imp_VariantInit
0x18001f0f9  mov     rcx, [rbp+57h+arg_8]
0x18001f0fd  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18001f101  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18001f106  movaps  [rbp+57h+var_A0], xmm1
0x18001f10a  movsd   [rbp+57h+var_90], xmm0
0x18001f10f  movaps  [rbp+57h+var_80], xmm1
0x18001f113  movsd   [rbp+57h+var_70], xmm0
0x18001f118  movaps  [rbp+57h+var_60], xmm1
0x18001f11c  movsd   [rbp+57h+var_50], xmm0
0x18001f121  movaps  [rbp+57h+var_40], xmm1
0x18001f125  movsd   [rbp+57h+var_30], xmm0
0x18001f12a  mov     rax, [rcx]
0x18001f12d  lea     rdx, [rbp+57h+var_A0]
0x18001f131  mov     [rsp+0F0h+ppv], rdx
0x18001f136  lea     r9, [rbp+57h+var_80]
0x18001f13a  lea     r8, [rbp+57h+var_60]
0x18001f13e  lea     rdx, [rbp+57h+var_40]
0x18001f142  mov     rax, [rax+50h]
0x18001f146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f14b  test    eax, eax
0x18001f14d  jns     short loc_18001F15E
0x18001f14f  lea     rdx, aTaskserviceCon; "taskService->Connect(emptyVar, emptyVar"...
0x18001f156  mov     ecx, eax; this
0x18001f158  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18001f15e  mov     [rbp+57h+arg_18], 0
0x18001f166  mov     rdi, [rbp+57h+arg_8]
0x18001f16a  mov     rax, [rdi]
0x18001f16d  mov     rbx, [rax+38h]
0x18001f171  lea     rcx, [rbp+57h+arg_18]
0x18001f175  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001f17a  lea     r8, [rbp+57h+arg_18]
0x18001f17e  lea     rdx, aMicrosoftXblga; "\\Microsoft\\XblGameSave"
0x18001f185  mov     rcx, rdi
0x18001f188  mov     rax, rbx
0x18001f18b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f190  test    eax, eax
0x18001f192  jns     short loc_18001F1A3
0x18001f194  lea     rdx, aTaskserviceGet; "taskService->GetFolder(L\"\\\\Microsoft"...
0x18001f19b  mov     ecx, eax; this
0x18001f19d  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18001f1a3  mov     [rbp+57h+arg_10], 0
0x18001f1ab  mov     rdi, [rbp+57h+arg_18]
0x18001f1af  mov     rax, [rdi]
0x18001f1b2  mov     rbx, [rax+68h]
0x18001f1b6  lea     rcx, [rbp+57h+arg_10]
0x18001f1ba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001f1bf  lea     r8, [rbp+57h+arg_10]
0x18001f1c3  lea     rdx, aXblgamesavetas; "XblGameSaveTask"
0x18001f1ca  mov     rcx, rdi
0x18001f1cd  mov     rax, rbx
0x18001f1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1d5  test    eax, eax
0x18001f1d7  jns     short loc_18001F1E8
0x18001f1d9  lea     rdx, aTaskfolderGett; "taskFolder->GetTask(L\"XblGameSaveTask"...
0x18001f1e0  mov     ecx, eax; this
0x18001f1e2  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18001f1e8  mov     rcx, [rbp+57h+arg_10]
0x18001f1ec  mov     rax, [rcx]
0x18001f1ef  xor     sil, r15b
0x18001f1f2  movzx   edx, sil
0x18001f1f6  sub     dx, r15w
0x18001f1fa  mov     rax, [rax+58h]
0x18001f1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f203  test    eax, eax
0x18001f205  jns     short loc_18001F216
0x18001f207  lea     rdx, aTaskPutEnabled; "task->put_Enabled(vBool)"
0x18001f20e  mov     ecx, eax; this
0x18001f210  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18001f216  lea     rcx, [rbp+57h+arg_10]
0x18001f21a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001f21f  nop
0x18001f220  lea     rcx, [rbp+57h+arg_18]
0x18001f224  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001f229  nop
0x18001f22a  lea     rcx, [rbp+57h+arg_8]
0x18001f22e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001f233  add     rsp, 0D0h
0x18001f23a  pop     r15
0x18001f23c  pop     rdi
0x18001f23d  pop     rsi
0x18001f23e  pop     rbx
0x18001f23f  pop     rbp
0x18001f240  retn
```
