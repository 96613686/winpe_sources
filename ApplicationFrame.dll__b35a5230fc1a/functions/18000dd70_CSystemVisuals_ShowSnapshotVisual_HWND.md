# CSystemVisuals::ShowSnapshotVisual(HWND__ *)

- ea: `0x18000dd70`
- end: `0x18000e1c9`
- name: `?ShowSnapshotVisual@CSystemVisuals@@AEAAJPEAUHWND__@@@Z`
- size: `1113`
- prototype: `int(CSystemVisuals *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18000f784`

## callees

- `0x180004c98`
- `0x18000dd70`
- `0x180010478`
- `0x1800105f8`
- `0x180010728`
- `0x180010b58`
- `0x1800131a0`
- `0x180032b9c`
- `0x180039b84`
- `0x18003f0b4`
- `0x180040270`
- `0x180041570`
- `0x180041ddc`
- `0x180043c30`
- `0x180047200`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000df1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e031`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e10e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000df1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e031`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e10e`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x18000de2b`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x18000de2b`
- `dwmapi!DwmUnregisterThumbnail` at `0x18000e0a3`
- `dwmapi!DwmUnregisterThumbnail` at `0x18000e155`
- `dwmapi!DwmUnregisterThumbnail` at `0x18000e0a3`
- `dwmapi!DwmUnregisterThumbnail` at `0x18000e155`
- `dwmapi!__imp_DwmpCreateSharedThumbnailVisual` at `0x18000dfc4`
- `dwmapi!__imp_DwmpCreateSharedThumbnailVisual` at `0x18000dfc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CSystemVisuals::ShowSnapshotVisual(CSystemVisuals *this, HWND a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  int v5; // r15d
  const unsigned __int16 *v6; // rbx
  unsigned int LastErrorFailHr; // ebx
  wil::details *v8; // rcx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, int *); // rbx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  _QWORD *v16; // rbx
  int v17; // edi
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v21; // rdi
  int v22; // eax
  unsigned int v23; // esi
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // eax
  int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+20h] [rbp-E0h]
  int v29[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  struct _RTL_CRITICAL_SECTION *v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h]
  _BYTE v33[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h]
  char v35; // [rsp+70h] [rbp-90h]
  struct tagRECT Rect; // [rsp+78h] [rbp-88h] BYREF
  int v37; // [rsp+88h] [rbp-78h] BYREF
  struct tagRECT v38; // [rsp+8Ch] [rbp-74h]
  struct tagRECT v39; // [rsp+9Ch] [rbp-64h]
  char v40; // [rsp+ACh] [rbp-54h]
  int v41; // [rsp+ADh] [rbp-53h]
  int v42; // [rsp+B1h] [rbp-4Fh]
  _QWORD v43[42]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(((unsigned __int64)this + 40) & -(__int64)(this != 0));
  v31 = v4;
  v5 = CObjectWithThreadUseDetection::TryEnterOnCurrentThread((__int64)v4);
  v32 = v5;
  v6 = (const unsigned __int16 *)((char *)this + 96);
  if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged((char *)this + 96) )
    v6 = *(const unsigned __int16 **)v6;
  wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v43,
    "ShowSnapshotVisual");
  v43[0] = &SystemVisualTelemetry::ShowSnapshotVisual::`vftable';
  SystemVisualTelemetry::ShowSnapshotVisual::StartActivity((SystemVisualTelemetry::ShowSnapshotVisual *)v43, v6);
  if ( *((_QWORD *)this + 24) )
  {
    LastErrorFailHr = 0;
LABEL_34:
    SystemVisualTelemetry::ShowSnapshotVisual::~ShowSnapshotVisual((SystemVisualTelemetry::ShowSnapshotVisual *)v43);
    CThreadUseDetector::~CThreadUseDetector((CThreadUseDetector *)&v31);
    return LastErrorFailHr;
  }
  Rect = 0;
  if ( !GetClientRect(a2, &Rect) )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v8);
    goto LABEL_34;
  }
  Rect.bottom += *((_DWORD *)this + 53);
  v40 = 0;
  v37 = 1048603;
  v41 = 1;
  v42 = 1;
  v39 = Rect;
  v38 = Rect;
  *(_QWORD *)v29 = 0;
  v9 = *((_QWORD *)this + 19);
  v10 = *(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 32LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v29);
  v11 = v10(v9, v29);
  LastErrorFailHr = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x185,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\systemvisuals.cpp",
      (const char *)(unsigned int)v11,
      v27);
    v12 = *(_QWORD *)v29;
    if ( *(_QWORD *)v29 )
    {
      *(_QWORD *)v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v43[0] = &SystemVisualTelemetry::ShowSnapshotVisual::`vftable';
    wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v43);
    wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v43);
    if ( v5 >= 0 )
      LeaveCriticalSection(v4);
    return LastErrorFailHr;
  }
  v30 = 0;
  v13 = *((_QWORD *)this + 19);
  v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 40LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v30);
  v15 = v14(v13, &v30);
  LastErrorFailHr = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x189,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\systemvisuals.cpp",
      (const char *)(unsigned int)v15,
      v27);
LABEL_14:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v29);
    goto LABEL_34;
  }
  v16 = (_QWORD *)((char *)this + 144);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 144);
  v28 = v29[0];
  v17 = DwmpCreateSharedThumbnailVisual(*((_QWORD *)this + 11), a2, 0, &v37);
  if ( v17 >= 0 )
  {
    v21 = *(_QWORD *)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                       v33,
                       this);
    v34 = v21;
    v35 = 1;
    v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v30 + 128LL))(v30, *v16, 1);
    v23 = v22;
    if ( v22 >= 0 )
    {
      v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v16 + 80LL))(*v16, 0);
      LastErrorFailHr = v26;
      if ( v26 >= 0 )
      {
        wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v43);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v30);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v29);
        LastErrorFailHr = 0;
        goto LABEL_34;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x199,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\systemvisuals.cpp",
        (const char *)(unsigned int)v26,
        v28);
      DwmUnregisterThumbnail(*(HTHUMBNAIL *)(v21 + 192));
      *(_QWORD *)(v21 + 192) = 0;
      goto LABEL_14;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x196,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\systemvisuals.cpp",
      (const char *)(unsigned int)v22,
      v28);
    DwmUnregisterThumbnail(*(HTHUMBNAIL *)(v21 + 192));
    *(_QWORD *)(v21 + 192) = 0;
    v24 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = *(_QWORD *)v29;
    if ( *(_QWORD *)v29 )
    {
      *(_QWORD *)v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v43[0] = &SystemVisualTelemetry::ShowSnapshotVisual::`vftable';
    wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v43);
    wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v43);
    if ( v5 >= 0 )
      LeaveCriticalSection(v4);
    return v23;
  }
  else
  {
    v18 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = *(_QWORD *)v29;
    if ( *(_QWORD *)v29 )
    {
      *(_QWORD *)v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v43[0] = &SystemVisualTelemetry::ShowSnapshotVisual::`vftable';
    wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v43);
    wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v43);
    if ( v5 >= 0 )
      LeaveCriticalSection(v4);
    return (unsigned int)v17;
  }
}

```

## disassembly

```asm
0x18000dd70  mov     [rsp-8+arg_10], rbx
0x18000dd75  push    rbp
0x18000dd76  push    rsi
0x18000dd77  push    rdi
0x18000dd78  push    r12
0x18000dd7a  push    r13
0x18000dd7c  push    r14
0x18000dd7e  push    r15
0x18000dd80  lea     rbp, [rsp-120h]
0x18000dd88  sub     rsp, 220h
0x18000dd8f  mov     rax, cs:__security_cookie
0x18000dd96  xor     rax, rsp
0x18000dd99  mov     [rbp+150h+var_40], rax
0x18000dda0  mov     r13, rdx
0x18000dda3  mov     rsi, rcx
0x18000dda6  mov     rax, rcx
0x18000dda9  add     rcx, 28h ; '('
0x18000ddad  neg     rax
0x18000ddb0  sbb     r14, r14
0x18000ddb3  and     r14, rcx
0x18000ddb6  mov     [rsp+250h+var_200], r14
0x18000ddbb  mov     rcx, r14
0x18000ddbe  call    ?TryEnterOnCurrentThread@CObjectWithThreadUseDetection@@IEAAJW4ThreadUseFailureResponse@@@Z; CObjectWithThreadUseDetection::TryEnterOnCurrentThread(ThreadUseFailureResponse)
0x18000ddc3  mov     r15d, eax
0x18000ddc6  mov     [rsp+250h+var_1F8], eax
0x18000ddca  lea     rbx, [rsi+60h]
0x18000ddce  mov     rcx, rbx
0x18000ddd1  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x18000ddd6  xor     edi, edi
0x18000ddd8  test    al, al
0x18000ddda  jz      short loc_18000DDDF
0x18000dddc  mov     rbx, [rbx]
0x18000dddf  lea     rdx, aShowsnapshotvi; "ShowSnapshotVisual"
0x18000dde6  lea     rcx, [rbp+150h+var_190]
0x18000ddea  call    ??0?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000ddef  lea     rax, ??_7ShowSnapshotVisual@SystemVisualTelemetry@@6B@; const SystemVisualTelemetry::ShowSnapshotVisual::`vftable'
0x18000ddf6  mov     [rbp+150h+var_190], rax
0x18000ddfa  mov     rdx, rbx; unsigned __int16 *
0x18000ddfd  lea     rcx, [rbp+150h+var_190]; this
0x18000de01  call    ?StartActivity@ShowSnapshotVisual@SystemVisualTelemetry@@QEAAXPEBG@Z; SystemVisualTelemetry::ShowSnapshotVisual::StartActivity(ushort const *)
0x18000de06  nop
0x18000de07  lea     r12, [rsi+0C0h]
0x18000de0e  cmp     [r12], rdi
0x18000de12  jz      short loc_18000DE1B
0x18000de14  mov     ebx, edi
0x18000de16  jmp     loc_18000E189
0x18000de1b  xorps   xmm0, xmm0
0x18000de1e  movups  xmmword ptr [rsp+250h+Rect.left], xmm0
0x18000de23  lea     rdx, [rsp+250h+Rect]; lpRect
0x18000de28  mov     rcx, r13; hWnd
0x18000de2b  call    cs:__imp_GetClientRect
0x18000de31  test    eax, eax
0x18000de33  jnz     short loc_18000DE41
0x18000de35  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000de3a  mov     ebx, eax
0x18000de3c  jmp     loc_18000E189
0x18000de41  mov     ecx, [rbp+150h+Rect.bottom]
0x18000de44  add     ecx, [rsi+0D4h]
0x18000de4a  mov     [rbp+150h+Rect.bottom], ecx
0x18000de4d  mov     [rbp+150h+var_1A4], dil
0x18000de51  mov     [rbp+150h+var_1C8], 10001Bh
0x18000de58  mov     eax, 1
0x18000de5d  mov     [rbp+150h+var_1A3], eax
0x18000de60  mov     [rbp+150h+var_19F], eax
0x18000de63  movsd   xmm0, qword ptr [rsp+250h+Rect.left]
0x18000de69  movsd   [rbp+150h+var_1B4], xmm0
0x18000de6e  mov     eax, [rbp+150h+Rect.right]
0x18000de71  mov     [rbp+150h+var_1AC], eax
0x18000de74  mov     [rbp+150h+var_1A8], ecx
0x18000de77  movsd   [rbp+150h+var_1C4], xmm0
0x18000de7c  mov     [rbp+150h+var_1BC], eax
0x18000de7f  mov     [rbp+150h+var_1B8], ecx
0x18000de82  mov     qword ptr [rsp+250h+var_210], rdi
0x18000de87  mov     rdi, [rsi+98h]
0x18000de8e  mov     rax, [rdi]
0x18000de91  mov     rbx, [rax+20h]
0x18000de95  lea     rcx, [rsp+250h+var_210]
0x18000de9a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000de9f  lea     rdx, [rsp+250h+var_210]
0x18000dea4  mov     rcx, rdi
0x18000dea7  mov     rax, rbx
0x18000deaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deaf  mov     ebx, eax
0x18000deb1  test    eax, eax
0x18000deb3  jns     short loc_18000DF26
0x18000deb5  mov     rcx, [rbp+158h]; this
0x18000debc  mov     r9d, eax; char *
0x18000debf  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\frame"...
0x18000dec6  mov     edx, 185h; void *
0x18000decb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ded0  nop
0x18000ded1  mov     rcx, qword ptr [rsp+250h+var_210]
0x18000ded6  test    rcx, rcx
0x18000ded9  jz      short loc_18000DEF1
0x18000dedb  mov     qword ptr [rsp+250h+var_210], 0
0x18000dee4  mov     rax, [rcx]
0x18000dee7  mov     rax, [rax+10h]
0x18000deeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000def0  nop
0x18000def1  lea     rax, ??_7ShowSnapshotVisual@SystemVisualTelemetry@@6B@; const SystemVisualTelemetry::ShowSnapshotVisual::`vftable'
0x18000def8  mov     [rbp+150h+var_190], rax
0x18000defc  lea     rcx, [rbp+150h+var_190]
0x18000df00  call    ?Destroy@?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000df05  lea     rcx, [rbp+150h+var_190]
0x18000df09  call    ??1?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000df0e  nop
0x18000df0f  test    r15d, r15d
0x18000df12  js      loc_18000E19D
0x18000df18  mov     rcx, r14; lpCriticalSection
0x18000df1b  call    cs:__imp_LeaveCriticalSection
0x18000df21  jmp     loc_18000E19D
0x18000df26  mov     [rsp+250h+var_208], 0
0x18000df2f  mov     rdi, [rsi+98h]
0x18000df36  mov     rax, [rdi]
0x18000df39  mov     rbx, [rax+28h]
0x18000df3d  lea     rcx, [rsp+250h+var_208]
0x18000df42  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000df47  lea     rdx, [rsp+250h+var_208]
0x18000df4c  mov     rcx, rdi
0x18000df4f  mov     rax, rbx
0x18000df52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df57  mov     ebx, eax
0x18000df59  test    eax, eax
0x18000df5b  jns     short loc_18000DF93
0x18000df5d  mov     rcx, [rbp+158h]; this
0x18000df64  mov     r9d, eax; char *
0x18000df67  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\frame"...
0x18000df6e  mov     edx, 189h; void *
0x18000df73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df78  nop
0x18000df79  lea     rcx, [rsp+250h+var_208]
0x18000df7e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000df83  nop
0x18000df84  lea     rcx, [rsp+250h+var_210]
0x18000df89  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000df8e  jmp     loc_18000E189
0x18000df93  lea     rbx, [rsi+90h]
0x18000df9a  mov     rcx, rbx
0x18000df9d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000dfa2  mov     rax, qword ptr [rsp+250h+var_210]
0x18000dfa7  mov     [rsp+250h+var_220], r12
0x18000dfac  mov     [rsp+250h+var_228], rbx
0x18000dfb1  mov     qword ptr [rsp+250h+var_230], rax; int
0x18000dfb6  lea     r9, [rbp+150h+var_1C8]
0x18000dfba  xor     r8d, r8d
0x18000dfbd  mov     rdx, r13
0x18000dfc0  mov     rcx, [rsi+58h]
0x18000dfc4  call    cs:__imp_DwmpCreateSharedThumbnailVisual
0x18000dfca  mov     edi, eax
0x18000dfcc  xor     r12d, r12d
0x18000dfcf  test    eax, eax
0x18000dfd1  jns     short loc_18000E03E
0x18000dfd3  mov     rcx, [rsp+250h+var_208]
0x18000dfd8  test    rcx, rcx
0x18000dfdb  jz      short loc_18000DFEF
0x18000dfdd  mov     [rsp+250h+var_208], r12
0x18000dfe2  mov     rdx, [rcx]
0x18000dfe5  mov     rax, [rdx+10h]
0x18000dfe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfee  nop
0x18000dfef  mov     rcx, qword ptr [rsp+250h+var_210]
0x18000dff4  test    rcx, rcx
0x18000dff7  jz      short loc_18000E00B
0x18000dff9  mov     qword ptr [rsp+250h+var_210], r12
0x18000dffe  mov     rax, [rcx]
0x18000e001  mov     rax, [rax+10h]
0x18000e005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e00a  nop
0x18000e00b  lea     rax, ??_7ShowSnapshotVisual@SystemVisualTelemetry@@6B@; const SystemVisualTelemetry::ShowSnapshotVisual::`vftable'
0x18000e012  mov     [rbp+150h+var_190], rax
0x18000e016  lea     rcx, [rbp+150h+var_190]
0x18000e01a  call    ?Destroy@?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000e01f  lea     rcx, [rbp+150h+var_190]
0x18000e023  call    ??1?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000e028  nop
0x18000e029  test    r15d, r15d
0x18000e02c  js      short loc_18000E037
0x18000e02e  mov     rcx, r14; lpCriticalSection
0x18000e031  call    cs:__imp_LeaveCriticalSection
0x18000e037  mov     eax, edi
0x18000e039  jmp     loc_18000E19F
0x18000e03e  mov     rdx, rsi
0x18000e041  lea     rcx, [rsp+250h+var_1F0]
0x18000e046  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18000e04b  mov     rdi, [rax]
0x18000e04e  mov     [rsp+250h+var_1E8], rdi
0x18000e053  mov     [rsp+250h+var_1E0], 1
0x18000e058  mov     rcx, [rsp+250h+var_208]
0x18000e05d  mov     rax, [rcx]
0x18000e060  xor     r9d, r9d
0x18000e063  lea     r8d, [r9+1]
0x18000e067  mov     rdx, [rbx]
0x18000e06a  mov     rax, [rax+80h]
0x18000e071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e076  mov     esi, eax
0x18000e078  test    eax, eax
0x18000e07a  jns     loc_18000E11B
0x18000e080  mov     rcx, [rbp+158h]; this
0x18000e087  mov     r9d, eax; char *
0x18000e08a  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\frame"...
0x18000e091  mov     edx, 196h; void *
0x18000e096  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e09b  nop
0x18000e09c  mov     rcx, [rdi+0C0h]; hThumbnailId
0x18000e0a3  call    cs:__imp_DwmUnregisterThumbnail
0x18000e0a9  mov     [rdi+0C0h], r12
0x18000e0b0  mov     rcx, [rsp+250h+var_208]
0x18000e0b5  test    rcx, rcx
0x18000e0b8  jz      short loc_18000E0CC
0x18000e0ba  mov     [rsp+250h+var_208], r12
0x18000e0bf  mov     rax, [rcx]
0x18000e0c2  mov     rax, [rax+10h]
0x18000e0c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0cb  nop
0x18000e0cc  mov     rcx, qword ptr [rsp+250h+var_210]
0x18000e0d1  test    rcx, rcx
0x18000e0d4  jz      short loc_18000E0E8
0x18000e0d6  mov     qword ptr [rsp+250h+var_210], r12
0x18000e0db  mov     rax, [rcx]
0x18000e0de  mov     rax, [rax+10h]
0x18000e0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0e7  nop
0x18000e0e8  lea     rax, ??_7ShowSnapshotVisual@SystemVisualTelemetry@@6B@; const SystemVisualTelemetry::ShowSnapshotVisual::`vftable'
0x18000e0ef  mov     [rbp+150h+var_190], rax
0x18000e0f3  lea     rcx, [rbp+150h+var_190]
0x18000e0f7  call    ?Destroy@?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000e0fc  lea     rcx, [rbp+150h+var_190]
0x18000e100  call    ??1?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000e105  nop
0x18000e106  test    r15d, r15d
0x18000e109  js      short loc_18000E114
0x18000e10b  mov     rcx, r14; lpCriticalSection
0x18000e10e  call    cs:__imp_LeaveCriticalSection
0x18000e114  mov     eax, esi
0x18000e116  jmp     loc_18000E19F
0x18000e11b  mov     rcx, [rbx]
0x18000e11e  mov     rax, [rcx]
0x18000e121  xor     edx, edx
0x18000e123  mov     rax, [rax+50h]
0x18000e127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e12c  mov     ebx, eax
0x18000e12e  test    eax, eax
0x18000e130  jns     short loc_18000E167
0x18000e132  mov     rcx, [rbp+158h]; this
0x18000e139  mov     r9d, eax; char *
0x18000e13c  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\frame"...
0x18000e143  mov     edx, 199h; void *
0x18000e148  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e14d  nop
0x18000e14e  mov     rcx, [rdi+0C0h]; hThumbnailId
0x18000e155  call    cs:__imp_DwmUnregisterThumbnail
0x18000e15b  mov     [rdi+0C0h], r12
0x18000e162  jmp     loc_18000DF79
0x18000e167  lea     rcx, [rbp+150h+var_190]
0x18000e16b  call    ?Stop@?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000e170  nop
0x18000e171  lea     rcx, [rsp+250h+var_208]
0x18000e176  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e17b  nop
0x18000e17c  lea     rcx, [rsp+250h+var_210]
0x18000e181  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000e186  mov     ebx, r12d
0x18000e189  lea     rcx, [rbp+150h+var_190]; this
0x18000e18d  call    ??1ShowSnapshotVisual@SystemVisualTelemetry@@QEAA@XZ; SystemVisualTelemetry::ShowSnapshotVisual::~ShowSnapshotVisual(void)
0x18000e192  nop
0x18000e193  lea     rcx, [rsp+250h+var_200]; this
0x18000e198  call    ??1CThreadUseDetector@@QEAA@XZ; CThreadUseDetector::~CThreadUseDetector(void)
0x18000e19d  mov     eax, ebx
0x18000e19f  mov     rcx, [rbp+150h+var_40]
0x18000e1a6  xor     rcx, rsp; StackCookie
0x18000e1a9  call    __security_check_cookie
0x18000e1ae  mov     rbx, [rsp+250h+arg_10]
0x18000e1b6  add     rsp, 220h
0x18000e1bd  pop     r15
0x18000e1bf  pop     r14
0x18000e1c1  pop     r13
0x18000e1c3  pop     r12
0x18000e1c5  pop     rdi
0x18000e1c6  pop     rsi
0x18000e1c7  pop     rbp
0x18000e1c8  retn
```
