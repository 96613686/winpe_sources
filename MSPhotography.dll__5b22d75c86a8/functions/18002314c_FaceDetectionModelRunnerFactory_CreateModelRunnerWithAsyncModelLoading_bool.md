# FaceDetectionModelRunnerFactory::CreateModelRunnerWithAsyncModelLoading(bool)

- ea: `0x18002314c`
- end: `0x1800234bf`
- name: `?CreateModelRunnerWithAsyncModelLoading@FaceDetectionModelRunnerFactory@@SA?AV?$shared_ptr@VFaceDetectionModelRunner@@@std@@_N@Z`
- size: `883`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800154fc`

## callees

- `0x180002da0`
- `0x18000e834`
- `0x18001c554`
- `0x18001d764`
- `0x18001d7d8`
- `0x18001d860`
- `0x18001e6a0`
- `0x18001e730`
- `0x180020e84`
- `0x180020ea4`
- `0x180022a58`
- `0x18002314c`
- `0x180025448`
- `0x180027f7c`
- `0x180028188`
- `0x1800281c8`
- `0x180028360`
- `0x180028554`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800231bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800231bc`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180023243`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180023243`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18002321b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18002321b`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18002324f`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18002324f`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800231f3`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800231f3`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18002327e`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18002327e`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x1800232d0`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x1800232d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall FaceDetectionModelRunnerFactory::CreateModelRunnerWithAsyncModelLoading(_QWORD *a1, char a2)
{
  unsigned int ModuleHandle; // eax
  HRSRC ResourceW; // rdi
  HGLOBAL Resource; // rbx
  UINT v7; // r15d
  const BYTE *v8; // rbx
  IStream *v9; // rax
  __int64 v10; // rdi
  struct IUnknown *v11; // rdx
  void **v12; // rax
  unsigned int RandomAccessStreamOverStream; // eax
  _DWORD *v14; // rdx
  volatile signed __int32 *v15; // rsi
  __int64 v16; // rbx
  __int64 v17; // rbx
  unsigned int v18; // eax
  _BYTE v20[24]; // [rsp+20h] [rbp-49h] BYREF
  int v21; // [rsp+38h] [rbp-31h]
  __int64 v22; // [rsp+40h] [rbp-29h] BYREF
  __int64 v23; // [rsp+48h] [rbp-21h] BYREF
  __int64 v24; // [rsp+50h] [rbp-19h] BYREF
  __int64 v25; // [rsp+58h] [rbp-11h] BYREF
  __int128 v26; // [rsp+60h] [rbp-9h]
  int v27; // [rsp+70h] [rbp+7h] BYREF
  __int128 v28; // [rsp+78h] [rbp+Fh]
  _DWORD *v29; // [rsp+E0h] [rbp+77h] BYREF
  HMODULE phModule; // [rsp+E8h] [rbp+7Fh] BYREF

  v21 = 0;
  if ( (unsigned __int8)byte_180160805 >= 0x20u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 14, &WPP_3819cc37a64338403add9ef0c33489c9_Traceguids);
  phModule = 0;
  *(_DWORD *)v20 = 0;
  *(_OWORD *)&v20[8] = 0;
  ModuleHandle = GetModuleHandleExW(6u, (LPCWSTR)FaceDetectionModelRunnerFactory::CreateModelRunner, &phModule);
  winrt::check_bool<int>(ModuleHandle, v20);
  *(_DWORD *)v20 = 0;
  *(_OWORD *)&v20[8] = 0;
  winrt::check_pointer<HRSRC__>(phModule, v20);
  ResourceW = FindResourceW(phModule, (LPCWSTR)0x65, (LPCWSTR)0xA);
  *(_DWORD *)v20 = 0;
  *(_OWORD *)&v20[8] = 0;
  winrt::check_pointer<HRSRC__>(ResourceW, v20);
  Resource = LoadResource(phModule, ResourceW);
  *(_DWORD *)v20 = 0;
  *(_OWORD *)&v20[8] = 0;
  winrt::check_pointer<HRSRC__>(Resource, v20);
  v7 = SizeofResource(phModule, ResourceW);
  v8 = (const BYTE *)LockResource(Resource);
  *(_DWORD *)v20 = 0;
  *(_OWORD *)&v20[8] = 0;
  winrt::check_pointer<HRSRC__>(v8, v20);
  v23 = 0;
  v22 = 0;
  v9 = SHCreateMemStream(v8, v7);
  winrt::com_ptr<IStream>::attach(&v23, v9);
  *(_DWORD *)v20 = 0;
  *(_OWORD *)&v20[8] = 0;
  v10 = v23;
  winrt::check_pointer<HRSRC__>(v23, v20);
  *(_DWORD *)v20 = 0;
  *(_OWORD *)&v20[8] = 0;
  v12 = winrt::put_abi((winrt *)&v22, v11);
  RandomAccessStreamOverStream = CreateRandomAccessStreamOverStream(
                                   v10,
                                   0,
                                   winrt::impl::guid_v<winrt::Windows::Storage::Streams::IRandomAccessStream>,
                                   v12);
  winrt::check_hresult(&v29, RandomAccessStreamOverStream, v20);
  if ( (unsigned __int8)byte_180160805 >= 0x20u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 15, &WPP_3819cc37a64338403add9ef0c33489c9_Traceguids, v7);
  v14 = operator new(0xB0u);
  v29 = v14;
  *v14 = 1057803469;
  v14[1] = 1017370378;
  *((_QWORD *)v14 + 1) = 0;
  *((_QWORD *)v14 + 2) = 0;
  *((_QWORD *)v14 + 3) = 0;
  *((_QWORD *)v14 + 5) = 0;
  *((_QWORD *)v14 + 9) = 0;
  *((_QWORD *)v14 + 10) = 0;
  *((_QWORD *)v14 + 11) = 0;
  *((_QWORD *)v14 + 12) = 0;
  *((_QWORD *)v14 + 13) = 0;
  *((_BYTE *)v14 + 112) = 0;
  *((_QWORD *)v14 + 15) = v14 + 30;
  *((_QWORD *)v14 + 16) = v14 + 30;
  *((_QWORD *)v14 + 17) = 0;
  *((_QWORD *)v14 + 18) = 0;
  *((_WORD *)v14 + 76) = 2048;
  *((_BYTE *)v14 + 160) = a2;
  v14[41] = -2147023728;
  v14[42] = 1;
  v14[14] = 224;
  v14[15] = 224;
  std::shared_ptr<FaceDetectionModelRunner>::shared_ptr<FaceDetectionModelRunner>(a1);
  v21 = 1;
  v26 = 0;
  v15 = (volatile signed __int32 *)a1[1];
  if ( v15 )
  {
    v16 = *a1;
    *(_QWORD *)&v26 = *a1;
    *((_QWORD *)&v26 + 1) = v15;
    _InterlockedAdd(v15 + 3, 1u);
  }
  else
  {
    v15 = (volatile signed __int32 *)*((_QWORD *)&v26 + 1);
    v16 = v26;
  }
  winrt::Windows::Storage::Streams::RandomAccessStreamReference::CreateFromStream((const struct winrt::Windows::Storage::Streams::IRandomAccessStream *)&v29);
  winrt::Windows::AI::MachineLearning::LearningModel::LoadFromStreamAsync((const struct winrt::Windows::Storage::Streams::IRandomAccessStreamReference *)&v25);
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v29);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSPhotographyUnloadFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MSPhotographyUnloadFix>::GetImpl'::`2'::impl) )
    _InterlockedExchange((volatile __int32 *)(*a1 + 168LL), 0);
  *(_OWORD *)v20 = 0;
  if ( v15 )
  {
    *(_QWORD *)v20 = v16;
    *(_QWORD *)&v20[8] = v15;
    _InterlockedAdd(v15 + 3, 1u);
  }
  winrt::Windows::Foundation::AsyncOperationCompletedHandler_winrt::Windows::AI::MachineLearning::LearningModel_::AsyncOperationCompletedHandler_winrt::Windows::AI::MachineLearning::LearningModel___lambda_f09f2dc7b752a88243f291f507563960___(
    &v24,
    v20);
  v27 = 0;
  v28 = 0;
  v17 = v24;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 48LL))(v25, v24);
  winrt::check_hresult(&v29, v18, &v27);
  if ( v17 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v24);
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v25);
  if ( v15 )
    std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v15);
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v22);
  if ( v10 )
    winrt::com_ptr<ITensorNative>::unconditional_release_ref(&v23);
  return a1;
}

```

## disassembly

```asm
0x18002314c  mov     [rsp-8+arg_0], rcx
0x180023151  push    rbp
0x180023152  push    rbx
0x180023153  push    rsi
0x180023154  push    rdi
0x180023155  push    r12
0x180023157  push    r14
0x180023159  push    r15
0x18002315b  lea     rbp, [rsp-27h]
0x180023160  sub     rsp, 90h
0x180023167  mov     sil, dl
0x18002316a  mov     r14, rcx
0x18002316d  xor     r12d, r12d
0x180023170  mov     [rbp+57h+var_88], r12d
0x180023174  cmp     cs:byte_180160805, 20h ; ' '
0x18002317b  jb      short loc_18002319C
0x18002317d  lea     edx, [r12+0Eh]
0x180023182  lea     r8, WPP_3819cc37a64338403add9ef0c33489c9_Traceguids
0x180023189  mov     rcx, cs:WPP_GLOBAL_Control
0x180023190  mov     rcx, [rcx+0D8h]
0x180023197  call    WPP_SF_
0x18002319c  mov     [rbp+57h+phModule], r12
0x1800231a0  mov     dword ptr [rbp+57h+var_A0], r12d
0x1800231a4  xorps   xmm0, xmm0
0x1800231a7  movdqu  xmmword ptr [rbp+57h+var_A0+8], xmm0
0x1800231ac  lea     r8, [rbp+57h+phModule]; phModule
0x1800231b0  lea     rdx, ?CreateModelRunner@FaceDetectionModelRunnerFactory@@SAPEAVFaceDetectionModelRunner@@_N@Z; lpModuleName
0x1800231b7  mov     ecx, 6; dwFlags
0x1800231bc  call    cs:__imp_GetModuleHandleExW
0x1800231c2  lea     rdx, [rbp+57h+var_A0]
0x1800231c6  mov     ecx, eax
0x1800231c8  call    ??$check_bool@H@winrt@@YAHHAEBUslim_source_location@impl@0@@Z; winrt::check_bool<int>(int,winrt::impl::slim_source_location const &)
0x1800231cd  mov     dword ptr [rbp+57h+var_A0], r12d
0x1800231d1  xorps   xmm0, xmm0
0x1800231d4  movdqu  xmmword ptr [rbp+57h+var_A0+8], xmm0
0x1800231d9  lea     rdx, [rbp+57h+var_A0]
0x1800231dd  mov     rcx, [rbp+57h+phModule]
0x1800231e1  call    ??$check_pointer@UHRSRC__@@@winrt@@YAPEAUHRSRC__@@PEAU1@AEBUslim_source_location@impl@0@@Z; winrt::check_pointer<HRSRC__>(HRSRC__ *,winrt::impl::slim_source_location const &)
0x1800231e6  mov     edx, 65h ; 'e'; lpName
0x1800231eb  lea     r8d, [rdx-5Bh]; lpType
0x1800231ef  mov     rcx, [rbp+57h+phModule]; hModule
0x1800231f3  call    cs:__imp_FindResourceW
0x1800231f9  mov     rdi, rax
0x1800231fc  mov     dword ptr [rbp+57h+var_A0], r12d
0x180023200  xorps   xmm0, xmm0
0x180023203  movdqu  xmmword ptr [rbp+57h+var_A0+8], xmm0
0x180023208  lea     rdx, [rbp+57h+var_A0]
0x18002320c  mov     rcx, rax
0x18002320f  call    ??$check_pointer@UHRSRC__@@@winrt@@YAPEAUHRSRC__@@PEAU1@AEBUslim_source_location@impl@0@@Z; winrt::check_pointer<HRSRC__>(HRSRC__ *,winrt::impl::slim_source_location const &)
0x180023214  mov     rdx, rdi; hResInfo
0x180023217  mov     rcx, [rbp+57h+phModule]; hModule
0x18002321b  call    cs:__imp_LoadResource
0x180023221  mov     rbx, rax
0x180023224  mov     dword ptr [rbp+57h+var_A0], r12d
0x180023228  xorps   xmm0, xmm0
0x18002322b  movdqu  xmmword ptr [rbp+57h+var_A0+8], xmm0
0x180023230  lea     rdx, [rbp+57h+var_A0]
0x180023234  mov     rcx, rax
0x180023237  call    ??$check_pointer@UHRSRC__@@@winrt@@YAPEAUHRSRC__@@PEAU1@AEBUslim_source_location@impl@0@@Z; winrt::check_pointer<HRSRC__>(HRSRC__ *,winrt::impl::slim_source_location const &)
0x18002323c  mov     rdx, rdi; hResInfo
0x18002323f  mov     rcx, [rbp+57h+phModule]; hModule
0x180023243  call    cs:__imp_SizeofResource
0x180023249  mov     r15d, eax
0x18002324c  mov     rcx, rbx; hResData
0x18002324f  call    cs:__imp_LockResource
0x180023255  mov     rbx, rax
0x180023258  mov     dword ptr [rbp+57h+var_A0], r12d
0x18002325c  xorps   xmm0, xmm0
0x18002325f  movdqu  xmmword ptr [rbp+57h+var_A0+8], xmm0
0x180023264  lea     rdx, [rbp+57h+var_A0]
0x180023268  mov     rcx, rax
0x18002326b  call    ??$check_pointer@UHRSRC__@@@winrt@@YAPEAUHRSRC__@@PEAU1@AEBUslim_source_location@impl@0@@Z; winrt::check_pointer<HRSRC__>(HRSRC__ *,winrt::impl::slim_source_location const &)
0x180023270  mov     [rbp+57h+var_78], r12
0x180023274  mov     [rbp+57h+var_80], r12
0x180023278  mov     edx, r15d; cbInit
0x18002327b  mov     rcx, rbx; pInit
0x18002327e  call    cs:__imp_SHCreateMemStream
0x180023284  mov     rdx, rax
0x180023287  lea     rcx, [rbp+57h+var_78]
0x18002328b  call    ?attach@?$com_ptr@UIStream@@@winrt@@QEAAXPEAUIStream@@@Z; winrt::com_ptr<IStream>::attach(IStream *)
0x180023290  mov     dword ptr [rbp+57h+var_A0], r12d
0x180023294  xorps   xmm0, xmm0
0x180023297  movdqu  xmmword ptr [rbp+57h+var_A0+8], xmm0
0x18002329c  lea     rdx, [rbp+57h+var_A0]
0x1800232a0  mov     rdi, [rbp+57h+var_78]
0x1800232a4  mov     rcx, rdi
0x1800232a7  call    ??$check_pointer@UHRSRC__@@@winrt@@YAPEAUHRSRC__@@PEAU1@AEBUslim_source_location@impl@0@@Z; winrt::check_pointer<HRSRC__>(HRSRC__ *,winrt::impl::slim_source_location const &)
0x1800232ac  mov     dword ptr [rbp+57h+var_A0], r12d
0x1800232b0  xorps   xmm0, xmm0
0x1800232b3  movdqu  xmmword ptr [rbp+57h+var_A0+8], xmm0
0x1800232b8  lea     rcx, [rbp+57h+var_80]; this
0x1800232bc  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x1800232c1  mov     r9, rax
0x1800232c4  lea     r8, ??$guid_v@UIRandomAccessStream@Streams@Storage@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Storage::Streams::IRandomAccessStream>
0x1800232cb  xor     edx, edx
0x1800232cd  mov     rcx, rdi
0x1800232d0  call    cs:__imp_CreateRandomAccessStreamOverStream
0x1800232d6  lea     r8, [rbp+57h+var_A0]
0x1800232da  mov     edx, eax
0x1800232dc  lea     rcx, [rbp+57h+arg_10]
0x1800232e0  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800232e5  cmp     cs:byte_180160805, 20h ; ' '
0x1800232ec  jb      short loc_180023310
0x1800232ee  mov     edx, 0Fh
0x1800232f3  mov     r9d, r15d
0x1800232f6  lea     r8, WPP_3819cc37a64338403add9ef0c33489c9_Traceguids
0x1800232fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180023304  mov     rcx, [rcx+0D8h]
0x18002330b  call    WPP_SF_d
0x180023310  mov     ecx, 0B0h; Size
0x180023315  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002331a  mov     rdx, rax
0x18002331d  mov     [rbp+57h+arg_10], rax
0x180023321  mov     dword ptr [rax], 3F0CCCCDh
0x180023327  mov     dword ptr [rax+4], 3CA3D70Ah
0x18002332e  mov     [rax+8], r12
0x180023332  mov     [rax+10h], r12
0x180023336  mov     [rax+18h], r12
0x18002333a  mov     [rax+28h], r12
0x18002333e  mov     [rax+48h], r12
0x180023342  mov     [rax+50h], r12
0x180023346  mov     [rax+58h], r12
0x18002334a  mov     [rax+60h], r12
0x18002334e  mov     [rax+68h], r12
0x180023352  mov     [rax+70h], r12b
0x180023356  add     rax, 78h ; 'x'
0x18002335a  mov     [rax], rax
0x18002335d  mov     [rax+8], rax
0x180023361  mov     [rax+10h], r12
0x180023365  mov     [rax+18h], r12
0x180023369  mov     word ptr [rax+20h], 800h
0x18002336f  mov     [rdx+0A0h], sil
0x180023376  mov     dword ptr [rdx+0A4h], 80070490h
0x180023380  mov     r15d, 1
0x180023386  mov     [rdx+0A8h], r15d
0x18002338d  mov     eax, 0E0h
0x180023392  mov     [rdx+38h], eax
0x180023395  mov     [rdx+3Ch], eax
0x180023398  mov     rcx, r14
0x18002339b  call    ??$?0VFaceDetectionModelRunner@@$0A@@?$shared_ptr@VFaceDetectionModelRunner@@@std@@QEAA@PEAVFaceDetectionModelRunner@@@Z; std::shared_ptr<FaceDetectionModelRunner>::shared_ptr<FaceDetectionModelRunner>(FaceDetectionModelRunner *)
0x1800233a0  mov     [rbp+57h+var_88], r15d
0x1800233a4  xorps   xmm0, xmm0
0x1800233a7  movdqu  [rbp+57h+var_60], xmm0
0x1800233ac  mov     rsi, [r14+8]
0x1800233b0  test    rsi, rsi
0x1800233b3  jz      short loc_1800233C7
0x1800233b5  mov     rbx, [r14]
0x1800233b8  mov     qword ptr [rbp+57h+var_60], rbx
0x1800233bc  mov     qword ptr [rbp+57h+var_60+8], rsi
0x1800233c0  lock add [rsi+0Ch], r15d
0x1800233c5  jmp     short loc_1800233CF
0x1800233c7  mov     rsi, qword ptr [rbp+57h+var_60+8]
0x1800233cb  mov     rbx, qword ptr [rbp+57h+var_60]
0x1800233cf  lea     rdx, [rbp+57h+var_80]
0x1800233d3  lea     rcx, [rbp+57h+arg_10]; struct winrt::Windows::Storage::Streams::IRandomAccessStream *
0x1800233d7  call    ?CreateFromStream@RandomAccessStreamReference@Streams@Storage@Windows@winrt@@SA@AEBUIRandomAccessStream@2345@@Z; winrt::Windows::Storage::Streams::RandomAccessStreamReference::CreateFromStream(winrt::Windows::Storage::Streams::IRandomAccessStream const &)
0x1800233dc  nop
0x1800233dd  mov     rdx, rax
0x1800233e0  lea     rcx, [rbp+57h+var_68]; struct winrt::Windows::Storage::Streams::IRandomAccessStreamReference *
0x1800233e4  call    ?LoadFromStreamAsync@LearningModel@MachineLearning@AI@Windows@winrt@@SA@AEBUIRandomAccessStreamReference@Streams@Storage@45@@Z; winrt::Windows::AI::MachineLearning::LearningModel::LoadFromStreamAsync(winrt::Windows::Storage::Streams::IRandomAccessStreamReference const &)
0x1800233e9  nop
0x1800233ea  lea     rcx, [rbp+57h+arg_10]
0x1800233ee  call    ??1?$IAsyncOperation@ULearningModel@MachineLearning@AI@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(void)
0x1800233f3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MSPhotographyUnloadFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MSPhotographyUnloadFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSPhotographyUnloadFix> `wil::Feature<__WilFeatureTraits_Feature_MSPhotographyUnloadFix>::GetImpl(void)'::`2'::impl
0x1800233fa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MSPhotographyUnloadFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSPhotographyUnloadFix>::__private_IsEnabled(void)
0x1800233ff  test    al, al
0x180023401  jz      short loc_18002340F
0x180023403  mov     rcx, [r14]
0x180023406  mov     eax, r12d
0x180023409  xchg    eax, [rcx+0A8h]
0x18002340f  xorps   xmm0, xmm0
0x180023412  movdqu  xmmword ptr [rbp+57h+var_A0], xmm0
0x180023417  test    rsi, rsi
0x18002341a  jz      short loc_180023429
0x18002341c  mov     qword ptr [rbp+57h+var_A0], rbx
0x180023420  mov     qword ptr [rbp+57h+var_A0+8], rsi
0x180023424  lock add [rsi+0Ch], r15d
0x180023429  lea     rdx, [rbp+57h+var_A0]
0x18002342d  lea     rcx, [rbp+57h+var_70]
0x180023431  call    winrt__Windows__Foundation__AsyncOperationCompletedHandler_winrt__Windows__AI__MachineLearning__LearningModel___AsyncOperationCompletedHandler_winrt__Windows__AI__MachineLearning__LearningModel___lambda_f09f2dc7b752a88243f291f507563960___
0x180023436  nop
0x180023437  mov     rcx, [rbp+57h+var_68]
0x18002343b  mov     [rbp+57h+var_50], r12d
0x18002343f  xorps   xmm0, xmm0
0x180023442  movdqu  [rbp+57h+var_48], xmm0
0x180023447  mov     rax, [rcx]
0x18002344a  mov     rbx, [rbp+57h+var_70]
0x18002344e  mov     rdx, rbx
0x180023451  mov     rax, [rax+30h]
0x180023455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002345a  lea     r8, [rbp+57h+var_50]
0x18002345e  mov     edx, eax
0x180023460  lea     rcx, [rbp+57h+arg_10]
0x180023464  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180023469  nop
0x18002346a  test    rbx, rbx
0x18002346d  jz      short loc_180023479
0x18002346f  lea     rcx, [rbp+57h+var_70]
0x180023473  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023478  nop
0x180023479  lea     rcx, [rbp+57h+var_68]
0x18002347d  call    ??1?$IAsyncOperation@ULearningModel@MachineLearning@AI@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(void)
0x180023482  nop
0x180023483  test    rsi, rsi
0x180023486  jz      short loc_180023491
0x180023488  mov     rcx, rsi; this
0x18002348b  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180023490  nop
0x180023491  lea     rcx, [rbp+57h+var_80]
0x180023495  call    ??1?$IAsyncOperation@ULearningModel@MachineLearning@AI@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(void)
0x18002349a  nop
0x18002349b  test    rdi, rdi
0x18002349e  jz      short loc_1800234A9
0x1800234a0  lea     rcx, [rbp+57h+var_78]
0x1800234a4  call    ?unconditional_release_ref@?$com_ptr@UITensorNative@@@winrt@@AEAAXXZ; winrt::com_ptr<ITensorNative>::unconditional_release_ref(void)
0x1800234a9  mov     rax, r14
0x1800234ac  add     rsp, 90h
0x1800234b3  pop     r15
0x1800234b5  pop     r14
0x1800234b7  pop     r12
0x1800234b9  pop     rdi
0x1800234ba  pop     rsi
0x1800234bb  pop     rbx
0x1800234bc  pop     rbp
0x1800234bd  retn
```
