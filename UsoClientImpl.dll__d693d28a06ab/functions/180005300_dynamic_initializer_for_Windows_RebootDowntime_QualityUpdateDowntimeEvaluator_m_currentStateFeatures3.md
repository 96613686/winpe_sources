# _dynamic_initializer_for__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3__

- ea: `0x180005300`
- end: `0x180005698`
- name: `_dynamic_initializer_for__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3__`
- size: `920`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005300`
- `0x18000a1f8`
- `0x1800338a4`
- `0x180033b00`
- `0x180056568`
- `0x1800569e8`

## string_xrefs

- `0x180005358`: `numDriverUpdates`
- `0x1800053b0`: `numOtherUpdates`
- `0x18000551d`: `totalOtherUpdatesSizeInBytes`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
int dynamic_initializer_for__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3__()
{
  __int64 v0; // rbx
  _DWORD *v1; // rdi
  _OWORD v3[2]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v4[2]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v5[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v6; // [rsp+88h] [rbp-78h] BYREF
  __int64 v7; // [rsp+98h] [rbp-68h]
  __int64 v8; // [rsp+A0h] [rbp-60h]
  __int128 v9; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v10; // [rsp+B8h] [rbp-48h]
  __int64 v11; // [rsp+C0h] [rbp-40h]
  int v12; // [rsp+C8h] [rbp-38h]
  int v13; // [rsp+CCh] [rbp-34h]
  _OWORD v14[2]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v15[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v16; // [rsp+110h] [rbp+10h]
  int v17; // [rsp+114h] [rbp+14h]
  __int128 v18; // [rsp+118h] [rbp+18h] BYREF
  __int64 v19; // [rsp+128h] [rbp+28h]
  __int64 v20; // [rsp+130h] [rbp+30h]
  __int128 v21; // [rsp+138h] [rbp+38h] BYREF
  __int64 v22; // [rsp+148h] [rbp+48h]
  __int64 v23; // [rsp+150h] [rbp+50h]
  int v24; // [rsp+158h] [rbp+58h]
  int v25; // [rsp+15Ch] [rbp+5Ch]
  _OWORD v26[2]; // [rsp+160h] [rbp+60h] BYREF
  _OWORD v27[2]; // [rsp+180h] [rbp+80h] BYREF
  int v28; // [rsp+1A0h] [rbp+A0h]
  int v29; // [rsp+1A4h] [rbp+A4h]
  __int128 v30; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v31; // [rsp+1B8h] [rbp+B8h]
  __int64 v32; // [rsp+1C0h] [rbp+C0h]
  __int128 v33; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v34; // [rsp+1D8h] [rbp+D8h]
  __int64 v35; // [rsp+1E0h] [rbp+E0h]
  int v36; // [rsp+1E8h] [rbp+E8h]
  int v37; // [rsp+1ECh] [rbp+ECh]
  _OWORD v38[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  _OWORD v39[2]; // [rsp+210h] [rbp+110h] BYREF
  int v40; // [rsp+230h] [rbp+130h]
  int v41; // [rsp+234h] [rbp+134h]
  char v42; // [rsp+238h] [rbp+138h] BYREF

  memset(v3, 0, sizeof(v3));
  std::wstring::_Construct<1,wchar_t const *>(v3);
  memset(v4, 0, sizeof(v4));
  std::wstring::_Construct<1,wchar_t const *>(v4);
  v5[0] = 0;
  v5[1] = 1101004800;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v6);
  v9 = 0;
  v10 = 0;
  v11 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v9);
  v12 = 0;
  v13 = 1097859072;
  memset(v14, 0, sizeof(v14));
  std::wstring::_Construct<1,wchar_t const *>(v14);
  memset(v15, 0, sizeof(v15));
  std::wstring::_Construct<1,wchar_t const *>(v15);
  v16 = 0;
  v17 = 1317997848;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v18);
  v21 = 0;
  v22 = 0;
  v23 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v21);
  v24 = 0;
  v25 = 1317997848;
  memset(v26, 0, sizeof(v26));
  std::wstring::_Construct<1,wchar_t const *>(v26);
  memset(v27, 0, sizeof(v27));
  std::wstring::_Construct<1,wchar_t const *>(v27);
  v28 = 0;
  v29 = 1345507422;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v30);
  v33 = 0;
  v34 = 0;
  v35 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v33);
  v36 = 0;
  v37 = 1317997848;
  memset(v38, 0, sizeof(v38));
  std::wstring::_Construct<1,wchar_t const *>(v38);
  memset(v39, 0, sizeof(v39));
  std::wstring::_Construct<1,wchar_t const *>(v39);
  v40 = 0;
  v41 = 1065353216;
  Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3 = 0;
  qword_1800A0648 = 0;
  v0 = std::_Allocate<16,std::_Default_allocate_traits>(504);
  *(_QWORD *)&Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3 = v0;
  *((_QWORD *)&Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3 + 1) = v0;
  qword_1800A0648 = v0 + 504;
  v1 = v5;
  do
  {
    std::wstring::wstring(v0, v1 - 16);
    std::wstring::wstring(v0 + 32, v1 - 8);
    *(_DWORD *)(v0 + 64) = *v1;
    *(_DWORD *)(v0 + 68) = v1[1];
    v0 += 72;
    v1 += 18;
  }
  while ( v1 - 16 != (_DWORD *)&v42 );
  *((_QWORD *)&Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3 + 1) = v0;
  `eh vector destructor iterator'(v3, 0x48u, 7u, std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3__);
}

```

## disassembly

```asm
0x180005300  mov     [rsp-8+arg_10], rbx
0x180005305  push    rbp
0x180005306  push    rdi
0x180005307  push    r14
0x180005309  lea     rbp, [rsp-140h]
0x180005311  sub     rsp, 240h
0x180005318  xorps   xmm0, xmm0
0x18000531b  movups  [rsp+250h+var_210], xmm0
0x180005320  xorps   xmm1, xmm1
0x180005323  movdqa  [rsp+250h+var_200], xmm1
0x180005329  mov     ebx, 0Ah
0x18000532e  mov     r8d, ebx
0x180005331  lea     rdx, aNumdrvupv1; "NumDrvUpV1"
0x180005338  lea     rcx, [rsp+250h+var_210]
0x18000533d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005342  nop
0x180005343  xorps   xmm0, xmm0
0x180005346  movups  [rsp+250h+var_1F0], xmm0
0x18000534b  xorps   xmm1, xmm1
0x18000534e  movdqa  [rsp+250h+var_1E0], xmm1
0x180005354  lea     r8d, [rbx+6]
0x180005358  lea     rdx, aNumdriverupdat; "numDriverUpdates"
0x18000535f  lea     rcx, [rsp+250h+var_1F0]
0x180005364  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005369  mov     [rbp+150h+var_1D0], 0
0x180005370  mov     [rbp+150h+var_1CC], 41A00000h
0x180005377  xorps   xmm0, xmm0
0x18000537a  movups  [rbp+150h+var_1C8], xmm0
0x18000537e  xor     r14d, r14d
0x180005381  mov     [rbp+150h+var_1B8], r14
0x180005385  mov     [rbp+150h+var_1B0], r14
0x180005389  mov     r8d, ebx
0x18000538c  lea     rdx, aNumothupv1; "NumOthUpV1"
0x180005393  lea     rcx, [rbp+150h+var_1C8]
0x180005397  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000539c  nop
0x18000539d  xorps   xmm0, xmm0
0x1800053a0  movups  [rbp+150h+var_1A8], xmm0
0x1800053a4  mov     [rbp+150h+var_198], r14
0x1800053a8  mov     [rbp+150h+var_190], r14
0x1800053ac  lea     r8d, [rbx+5]
0x1800053b0  lea     rdx, aNumotherupdate; "numOtherUpdates"
0x1800053b7  lea     rcx, [rbp+150h+var_1A8]
0x1800053bb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800053c0  mov     [rbp+150h+var_188], r14d
0x1800053c4  mov     [rbp+150h+var_184], 41700000h
0x1800053cb  xorps   xmm0, xmm0
0x1800053ce  movups  [rbp+150h+var_180], xmm0
0x1800053d2  xorps   xmm1, xmm1
0x1800053d5  movdqa  [rbp+150h+var_170], xmm1
0x1800053da  lea     r8d, [rbx-4]
0x1800053de  lea     rdx, aSzquv1; "SzQUV1"
0x1800053e5  lea     rcx, [rbp+150h+var_180]
0x1800053e9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800053ee  nop
0x1800053ef  xorps   xmm0, xmm0
0x1800053f2  movups  [rbp+150h+var_160], xmm0
0x1800053f6  xorps   xmm1, xmm1
0x1800053f9  movdqa  [rbp+150h+var_150], xmm1
0x1800053fe  lea     r8d, [rbx+9]
0x180005402  lea     rdx, aTotallcusizein; "totalLCUSizeInBytes"
0x180005409  lea     rcx, [rbp+150h+var_160]
0x18000540d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005412  mov     [rbp+150h+var_140], r14d
0x180005416  mov     [rbp+150h+var_13C], 4E8F0D18h
0x18000541d  xorps   xmm0, xmm0
0x180005420  movups  [rbp+150h+var_138], xmm0
0x180005424  mov     [rbp+150h+var_128], r14
0x180005428  mov     [rbp+150h+var_120], r14
0x18000542c  lea     edi, [rbx-1]
0x18000542f  mov     r8d, edi
0x180005432  lea     rdx, aSzdrvupv1; "SzDrvUpV1"
0x180005439  lea     rcx, [rbp+150h+var_138]
0x18000543d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005442  nop
0x180005443  xorps   xmm0, xmm0
0x180005446  movups  [rbp+150h+var_118], xmm0
0x18000544a  mov     [rbp+150h+var_108], r14
0x18000544e  mov     [rbp+150h+var_100], r14
0x180005452  lea     ebx, [rdi+0Dh]
0x180005455  mov     r8d, ebx
0x180005458  lea     rdx, aTotaldriversiz; "totalDriverSizeInBytes"
0x18000545f  lea     rcx, [rbp+150h+var_118]
0x180005463  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005468  mov     [rbp+150h+var_F8], r14d
0x18000546c  mov     [rbp+150h+var_F4], 4E8F0D18h
0x180005473  xorps   xmm0, xmm0
0x180005476  movups  [rbp+150h+var_F0], xmm0
0x18000547a  xorps   xmm1, xmm1
0x18000547d  movdqa  [rbp+150h+var_E0], xmm1
0x180005482  mov     r8d, edi
0x180005485  lea     rdx, aSzdrvupv2; "SzDrvUpV2"
0x18000548c  lea     rcx, [rbp+150h+var_F0]
0x180005490  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005495  nop
0x180005496  xorps   xmm0, xmm0
0x180005499  movups  [rbp+150h+var_D0], xmm0
0x1800054a0  xorps   xmm1, xmm1
0x1800054a3  movdqa  [rbp+150h+var_C0], xmm1
0x1800054ab  mov     r8d, ebx
0x1800054ae  lea     rdx, aTotaldriversiz; "totalDriverSizeInBytes"
0x1800054b5  lea     rcx, [rbp+150h+var_D0]
0x1800054bc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800054c1  mov     [rbp+150h+var_B0], r14d
0x1800054c8  mov     [rbp+150h+var_AC], 5032D05Eh
0x1800054d2  xorps   xmm0, xmm0
0x1800054d5  movups  [rbp+150h+var_A8], xmm0
0x1800054dc  mov     [rbp+150h+var_98], r14
0x1800054e3  mov     [rbp+150h+var_90], r14
0x1800054ea  mov     r8d, edi
0x1800054ed  lea     rdx, aSzothupv1; "SzOthUpV1"
0x1800054f4  lea     rcx, [rbp+150h+var_A8]
0x1800054fb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005500  nop
0x180005501  xorps   xmm0, xmm0
0x180005504  movups  [rbp+150h+var_88], xmm0
0x18000550b  mov     [rbp+150h+var_78], r14
0x180005512  mov     [rbp+150h+var_70], r14
0x180005519  lea     r8d, [r14+1Ch]
0x18000551d  lea     rdx, aTotalotherupda; "totalOtherUpdatesSizeInBytes"
0x180005524  lea     rcx, [rbp+150h+var_88]
0x18000552b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005530  mov     [rbp+150h+var_68], r14d
0x180005537  mov     [rbp+150h+var_64], 4E8F0D18h
0x180005541  xorps   xmm0, xmm0
0x180005544  movups  [rbp+150h+var_60], xmm0
0x18000554b  xorps   xmm1, xmm1
0x18000554e  movdqa  [rbp+150h+var_50], xmm1
0x180005556  lea     r8d, [r14+7]
0x18000555a  lea     rdx, aIsekbv1; "IsEKBV1"
0x180005561  lea     rcx, [rbp+150h+var_60]
0x180005568  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000556d  nop
0x18000556e  xorps   xmm0, xmm0
0x180005571  movups  [rbp+150h+var_40], xmm0
0x180005578  xorps   xmm1, xmm1
0x18000557b  movdqa  [rbp+150h+var_30], xmm1
0x180005583  lea     r8d, [r14+6]
0x180005587  lea     rdx, aHasekb; "hasEKB"
0x18000558e  lea     rcx, [rbp+150h+var_40]
0x180005595  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000559a  mov     [rbp+150h+var_20], r14d
0x1800055a1  mov     [rbp+150h+var_1C], 3F800000h
0x1800055ab  xorps   xmm0, xmm0
0x1800055ae  movdqu  cs:?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B, xmm0; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x1800055b6  mov     cs:qword_1800A0648, r14
0x1800055bd  mov     ecx, 1F8h
0x1800055c2  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800055c7  mov     rbx, rax
0x1800055ca  mov     qword ptr cs:?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B, rax; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x1800055d1  mov     qword ptr cs:?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B+8, rax; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x1800055d8  lea     rcx, [rax+1F8h]
0x1800055df  mov     cs:qword_1800A0648, rcx
0x1800055e6  lea     rcx, ?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x1800055ed  mov     [rbp+150h+arg_0], rcx
0x1800055f4  xorps   xmm0, xmm0
0x1800055f7  movups  [rsp+250h+var_230], xmm0
0x1800055fc  mov     qword ptr [rsp+250h+var_230], rax
0x180005601  mov     qword ptr [rsp+250h+var_230+8], rax
0x180005606  mov     [rsp+250h+var_220], rcx
0x18000560b  lea     rdi, [rbp+150h+var_1D0]
0x18000560f  mov     [rbp+150h+arg_8], rbx
0x180005616  lea     rdx, [rdi-40h]
0x18000561a  mov     rcx, rbx
0x18000561d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180005622  nop
0x180005623  lea     rdx, [rdi-20h]
0x180005627  lea     rcx, [rbx+20h]
0x18000562b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180005630  mov     eax, [rdi]
0x180005632  mov     [rbx+40h], eax
0x180005635  mov     eax, [rdi+4]
0x180005638  mov     [rbx+44h], eax
0x18000563b  add     rbx, 48h ; 'H'
0x18000563f  mov     qword ptr [rsp+250h+var_230+8], rbx
0x180005644  lea     rdi, [rdi+48h]
0x180005648  lea     rax, [rdi-40h]
0x18000564c  lea     rcx, [rbp+150h+var_18]
0x180005653  cmp     rax, rcx
0x180005656  jnz     short loc_18000560F
0x180005658  mov     qword ptr cs:?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B+8, rbx; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x18000565f  lea     r9, ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@QEAA@XZ; void (*)(void *)
0x180005666  mov     edx, 48h ; 'H'; unsigned __int64
0x18000566b  lea     r8d, [rdx-41h]; unsigned __int64
0x18000566f  lea     rcx, [rsp+250h+var_210]; void *
0x180005674  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180005679  lea     rcx, _dynamic_atexit_destructor_for__Windows__RebootDowntime__QualityUpdateDowntimeEvaluator__m_currentStateFeatures3__
0x180005680  mov     rbx, [rsp+250h+arg_10]
0x180005688  add     rsp, 240h
0x18000568f  pop     r14
0x180005691  pop     rdi
0x180005692  pop     rbp
0x180005693  jmp     atexit
```
