# UtilGetFlightInfo(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1800e5034`
- end: `0x1800e5351`
- name: `?UtilGetFlightInfo@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0@Z`
- size: `797`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18019c878`

## callees

- `0x1800e4454`
- `0x1800e5034`
- `0x1801c0cf8`
- `0x1801e19ac`
- `0x180369010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800e504e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800e504e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e50bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e50ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5129`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5159`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e51c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e51d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e50bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e50ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5129`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5159`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e51c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e51d4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800e51df`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800e51df`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UtilGetFlightInfo(__int64 a1, __int64 a2)
{
  HRESULT v4; // ebx
  int v5; // edi
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, void **); // rsi
  void *v8; // rcx
  void *v9; // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, void **); // rsi
  void *v12; // rcx
  void *v13; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  void *v18; // [rsp+20h] [rbp-28h] BYREF
  LPVOID *p_pv; // [rsp+28h] [rbp-20h]
  LPVOID v20; // [rsp+88h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+48h] BYREF
  __int64 v22; // [rsp+98h] [rbp+50h] BYREF

  v4 = CoInitializeEx(0, 0);
  pv = 0;
  v20 = 0;
  v22 = 0;
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147417850 )
  {
    v5 = v4;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 125;
      v17 = (unsigned int)v4;
LABEL_53:
      WPP_SF_d(v15[2], v16, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v17);
      goto LABEL_20;
    }
    goto LABEL_20;
  }
  v5 = tlx::cocreate_unique<FlightSettingsAPIBroker,IFlightSettingsAPIBroker>(&v22);
  if ( v5 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v16 = 126;
LABEL_39:
    v17 = (unsigned int)v5;
    goto LABEL_53;
  }
  v6 = v22;
  v7 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v22 + 48LL);
  v18 = 0;
  p_pv = &pv;
  v8 = pv;
  pv = 0;
  if ( v8 )
    CoTaskMemFree(v8);
  v5 = v7(v6, &v18);
  if ( v18 )
  {
    v9 = *p_pv;
    *p_pv = v18;
    if ( v9 )
      CoTaskMemFree(v9);
  }
  if ( v5 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v16 = 127;
    goto LABEL_39;
  }
  v10 = v22;
  v11 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v22 + 80LL);
  v18 = 0;
  p_pv = &v20;
  v12 = v20;
  v20 = 0;
  if ( v12 )
    CoTaskMemFree(v12);
  v5 = v11(v10, &v18);
  if ( v18 )
  {
    v13 = *p_pv;
    *p_pv = v18;
    if ( v13 )
      CoTaskMemFree(v13);
  }
  if ( v5 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v16 = 128;
    goto LABEL_39;
  }
  if ( pv && v20 )
  {
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a1) )
    {
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a2) )
      {
        v5 = 0;
        goto LABEL_20;
      }
      v5 = -2147024882;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_20;
      v16 = 131;
    }
    else
    {
      v5 = -2147024882;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_20;
      v16 = 130;
    }
    v17 = 2147942414LL;
    goto LABEL_53;
  }
  v5 = -2147467261;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v16 = 129;
    v17 = 2147500035LL;
    goto LABEL_53;
  }
LABEL_20:
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v20 )
    CoTaskMemFree(v20);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v4 >= 0 )
    CoUninitialize();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800e5034  push    rbp
0x1800e5036  push    rbx
0x1800e5037  push    rsi
0x1800e5038  push    rdi
0x1800e5039  push    r14
0x1800e503b  push    r15
0x1800e503d  mov     rbp, rsp
0x1800e5040  sub     rsp, 48h
0x1800e5044  mov     r14, rdx
0x1800e5047  mov     r15, rcx
0x1800e504a  xor     edx, edx; dwCoInit
0x1800e504c  xor     ecx, ecx; pvReserved
0x1800e504e  call    cs:__imp_CoInitializeEx
0x1800e5054  mov     ebx, eax
0x1800e5056  mov     [rbp+arg_0], eax
0x1800e5059  mov     [rbp+pv], 0
0x1800e5061  mov     [rbp+arg_8], 0
0x1800e5069  mov     [rbp+arg_18], 0
0x1800e5071  mov     ecx, 80000000h
0x1800e5076  add     eax, ecx
0x1800e5078  test    ecx, eax
0x1800e507a  jz      loc_1800E51F4
0x1800e5080  lea     rcx, [rbp+arg_18]
0x1800e5084  call    ??$cocreate_unique@VFlightSettingsAPIBroker@@UIFlightSettingsAPIBroker@@@tlx@@YAJPEAV?$unique_ptr@UIFlightSettingsAPIBroker@@Urelease_delete@tlx@@@utl@@KPEAUIUnknown@@AEBU_GUID@@@Z; tlx::cocreate_unique<FlightSettingsAPIBroker,IFlightSettingsAPIBroker>(utl::unique_ptr<IFlightSettingsAPIBroker,tlx::release_delete> *,ulong,IUnknown *,_GUID const &)
0x1800e5089  mov     edi, eax
0x1800e508b  test    eax, eax
0x1800e508d  js      loc_1800E5228
0x1800e5093  mov     rdi, [rbp+arg_18]
0x1800e5097  mov     rax, [rdi]
0x1800e509a  mov     rsi, [rax+30h]
0x1800e509e  mov     [rbp+var_28], 0
0x1800e50a6  lea     rax, [rbp+pv]
0x1800e50aa  mov     [rbp+var_20], rax
0x1800e50ae  mov     rcx, [rbp+pv]; pv
0x1800e50b2  mov     [rbp+pv], 0
0x1800e50ba  test    rcx, rcx
0x1800e50bd  jz      short loc_1800E50C6
0x1800e50bf  call    cs:__imp_CoTaskMemFree
0x1800e50c5  nop
0x1800e50c6  lea     rdx, [rbp+var_28]
0x1800e50ca  mov     rcx, rdi
0x1800e50cd  mov     rax, rsi
0x1800e50d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e50d5  mov     edi, eax
0x1800e50d7  mov     rdx, [rbp+var_28]
0x1800e50db  test    rdx, rdx
0x1800e50de  jz      short loc_1800E50F5
0x1800e50e0  mov     rax, [rbp+var_20]
0x1800e50e4  mov     rcx, [rax]; pv
0x1800e50e7  mov     [rax], rdx
0x1800e50ea  test    rcx, rcx
0x1800e50ed  jz      short loc_1800E50F5
0x1800e50ef  call    cs:__imp_CoTaskMemFree
0x1800e50f5  test    edi, edi
0x1800e50f7  js      loc_1800E5250
0x1800e50fd  mov     rdi, [rbp+arg_18]
0x1800e5101  mov     rax, [rdi]
0x1800e5104  mov     rsi, [rax+50h]
0x1800e5108  mov     [rbp+var_28], 0
0x1800e5110  lea     rax, [rbp+arg_8]
0x1800e5114  mov     [rbp+var_20], rax
0x1800e5118  mov     rcx, [rbp+arg_8]; pv
0x1800e511c  mov     [rbp+arg_8], 0
0x1800e5124  test    rcx, rcx
0x1800e5127  jz      short loc_1800E5130
0x1800e5129  call    cs:__imp_CoTaskMemFree
0x1800e512f  nop
0x1800e5130  lea     rdx, [rbp+var_28]
0x1800e5134  mov     rcx, rdi
0x1800e5137  mov     rax, rsi
0x1800e513a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e513f  mov     edi, eax
0x1800e5141  mov     rdx, [rbp+var_28]
0x1800e5145  test    rdx, rdx
0x1800e5148  jz      short loc_1800E515F
0x1800e514a  mov     rax, [rbp+var_20]
0x1800e514e  mov     rcx, [rax]; pv
0x1800e5151  mov     [rax], rdx
0x1800e5154  test    rcx, rcx
0x1800e5157  jz      short loc_1800E515F
0x1800e5159  call    cs:__imp_CoTaskMemFree
0x1800e515f  test    edi, edi
0x1800e5161  js      loc_1800E5285
0x1800e5167  mov     rdx, [rbp+pv]
0x1800e516b  test    rdx, rdx
0x1800e516e  jz      loc_1800E530A
0x1800e5174  cmp     [rbp+arg_8], 0
0x1800e5179  jz      loc_1800E530A
0x1800e517f  mov     rcx, r15
0x1800e5182  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800e5187  test    al, al
0x1800e5189  jz      loc_1800E52A8
0x1800e518f  mov     rdx, [rbp+arg_8]
0x1800e5193  mov     rcx, r14
0x1800e5196  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800e519b  test    al, al
0x1800e519d  jz      loc_1800E52E2
0x1800e51a3  xor     edi, edi
0x1800e51a5  mov     rcx, [rbp+arg_18]
0x1800e51a9  test    rcx, rcx
0x1800e51ac  jz      short loc_1800E51BB
0x1800e51ae  mov     rax, [rcx]
0x1800e51b1  mov     rax, [rax+10h]
0x1800e51b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e51ba  nop
0x1800e51bb  mov     rcx, [rbp+arg_8]; pv
0x1800e51bf  test    rcx, rcx
0x1800e51c2  jz      short loc_1800E51CB
0x1800e51c4  call    cs:__imp_CoTaskMemFree
0x1800e51ca  nop
0x1800e51cb  mov     rcx, [rbp+pv]; pv
0x1800e51cf  test    rcx, rcx
0x1800e51d2  jz      short loc_1800E51DB
0x1800e51d4  call    cs:__imp_CoTaskMemFree
0x1800e51da  nop
0x1800e51db  test    ebx, ebx
0x1800e51dd  js      short loc_1800E51E5
0x1800e51df  call    cs:__imp_CoUninitialize
0x1800e51e5  mov     eax, edi
0x1800e51e7  add     rsp, 48h
0x1800e51eb  pop     r15
0x1800e51ed  pop     r14
0x1800e51ef  pop     rdi
0x1800e51f0  pop     rsi
0x1800e51f1  pop     rbx
0x1800e51f2  pop     rbp
0x1800e51f3  retn
0x1800e51f4  cmp     ebx, 80010106h
0x1800e51fa  jz      loc_1800E5080
0x1800e5200  mov     edi, ebx
0x1800e5202  lea     rax, WPP_GLOBAL_Control
0x1800e5209  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5210  cmp     rcx, rax
0x1800e5213  jz      short loc_1800E51A5
0x1800e5215  test    byte ptr [rcx+1Ch], 1
0x1800e5219  jz      short loc_1800E51A5
0x1800e521b  mov     edx, 7Dh ; '}'
0x1800e5220  mov     r9d, ebx
0x1800e5223  jmp     loc_1800E533B
0x1800e5228  lea     rax, WPP_GLOBAL_Control
0x1800e522f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5236  cmp     rcx, rax
0x1800e5239  jz      loc_1800E51A5
0x1800e523f  test    byte ptr [rcx+1Ch], 1
0x1800e5243  jz      loc_1800E51A5
0x1800e5249  mov     edx, 7Eh ; '~'
0x1800e524e  jmp     short loc_1800E527D
0x1800e5250  lea     rax, WPP_GLOBAL_Control
0x1800e5257  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e525e  cmp     rcx, rax
0x1800e5261  jz      loc_1800E51A5
0x1800e5267  test    byte ptr [rcx+1Ch], 1
0x1800e526b  jz      loc_1800E51A5
0x1800e5271  mov     edx, 7Fh
0x1800e5276  jmp     short loc_1800E527D
0x1800e5278  mov     edx, 80h
0x1800e527d  mov     r9d, edi
0x1800e5280  jmp     loc_1800E533B
0x1800e5285  lea     rax, WPP_GLOBAL_Control
0x1800e528c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5293  cmp     rcx, rax
0x1800e5296  jz      loc_1800E51A5
0x1800e529c  test    byte ptr [rcx+1Ch], 1
0x1800e52a0  jz      loc_1800E51A5
0x1800e52a6  jmp     short loc_1800E5278
0x1800e52a8  mov     edi, 8007000Eh
0x1800e52ad  lea     rax, WPP_GLOBAL_Control
0x1800e52b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e52bb  cmp     rcx, rax
0x1800e52be  jz      loc_1800E51A5
0x1800e52c4  test    byte ptr [rcx+1Ch], 1
0x1800e52c8  jz      loc_1800E51A5
0x1800e52ce  mov     edx, 82h
0x1800e52d3  jmp     short loc_1800E52DA
0x1800e52d5  mov     edx, 83h
0x1800e52da  mov     r9d, 8007000Eh
0x1800e52e0  jmp     short loc_1800E533B
0x1800e52e2  mov     edi, 8007000Eh
0x1800e52e7  lea     rax, WPP_GLOBAL_Control
0x1800e52ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e52f5  cmp     rcx, rax
0x1800e52f8  jz      loc_1800E51A5
0x1800e52fe  test    byte ptr [rcx+1Ch], 1
0x1800e5302  jz      loc_1800E51A5
0x1800e5308  jmp     short loc_1800E52D5
0x1800e530a  mov     edi, 80004003h
0x1800e530f  lea     rax, WPP_GLOBAL_Control
0x1800e5316  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e531d  cmp     rcx, rax
0x1800e5320  jz      loc_1800E51A5
0x1800e5326  test    byte ptr [rcx+1Ch], 1
0x1800e532a  jz      loc_1800E51A5
0x1800e5330  mov     edx, 81h
0x1800e5335  mov     r9d, 80004003h
0x1800e533b  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800e5342  mov     rcx, [rcx+10h]
0x1800e5346  call    WPP_SF_d
0x1800e534b  jmp     loc_1800E51A5
```
