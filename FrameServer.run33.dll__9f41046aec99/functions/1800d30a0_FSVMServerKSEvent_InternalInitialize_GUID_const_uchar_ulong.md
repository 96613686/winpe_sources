# FSVMServerKSEvent::InternalInitialize(_GUID const &,uchar *,ulong)

- ea: `0x1800d30a0`
- end: `0x1800d3476`
- name: `?InternalInitialize@FSVMServerKSEvent@@MEAAJAEBU_GUID@@PEAEK@Z`
- size: `982`
- prototype: `int(FSVMServerKSEvent *__hidden this, const struct _GUID *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180009b5c`
- `0x180009f50`
- `0x18000a91c`
- `0x180017a3c`
- `0x180018998`
- `0x1800198f4`
- `0x18002681c`
- `0x18003b884`
- `0x18004d714`
- `0x18004da70`
- `0x1800d30a0`
- `0x1800d38d8`
- `0x1800e661c`
- `0x1800e924c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d32af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d32af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d3456`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d3456`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d30d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d30d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d32d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d32d8`
- `MFPlat!MFCreateAsyncResult` at `0x1800d332f`
- `MFPlat!MFCreateAsyncResult` at `0x1800d332f`
- `MFPlat!MFPutWaitingWorkItem` at `0x1800d335e`
- `MFPlat!MFPutWaitingWorkItem` at `0x1800d335e`

## pseudocode

```c
__int64 __fastcall FSVMServerKSEvent::InternalInitialize(
        FSVMServerKSEvent *this,
        const struct _GUID *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  size_t v4; // rdi
  char v6; // r15
  GuidTrace *v9; // rax
  const char *String; // rax
  signed int v11; // edi
  __int64 v12; // rdx
  __int64 unique; // rax
  void *v14; // rcx
  int v15; // eax
  const struct _GUID *v16; // r14
  HRESULT v17; // eax
  __int64 v18; // rdx
  signed int LastError; // eax
  IMFAsyncResult *v20; // rcx
  __int64 v21; // rbx
  GuidTrace *v22; // rax
  const char *v23; // rax
  int v24; // r8d
  bool v25; // zf
  __int64 v26; // rbx
  GuidTrace *v27; // rax
  const char *v28; // rax
  int v29; // r8d
  HANDLE EventW; // [rsp+40h] [rbp-30h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-28h]
  _BYTE v33[32]; // [rsp+50h] [rbp-20h] BYREF
  struct IFSVMEvent *v34; // [rsp+B0h] [rbp+40h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+C0h] [rbp+50h] BYREF

  v4 = a4;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 48);
  v6 = 0;
  LODWORD(v34) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  ppAsyncResult = 0;
  v34 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v9 = GuidTrace::GuidTrace((GuidTrace *)v33, a2);
    String = GuidTrace::GetString(v9);
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      18,
      (unsigned int)&WPP_956102e314603234c0af5b934e32accd_Traceguids,
      (_DWORD)this,
      (__int64)String);
    v6 = 1;
  }
  if ( (v6 & 1) != 0 )
  {
    v6 &= ~1u;
    FSString::~FSString((FSString *)v33);
  }
  if ( !a3 )
  {
    v11 = -2147024809;
    if ( g_wppLevels )
    {
      v12 = 19;
LABEL_8:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_956102e314603234c0af5b934e32accd_Traceguids,
        this,
        -2147024809);
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  if ( (unsigned int)v4 < 0x18 )
  {
    v11 = -2147024809;
    if ( g_wppLevels )
    {
      v12 = 20;
      goto LABEL_8;
    }
LABEL_40:
    if ( byte_18010EC4D )
    {
      v21 = *((_QWORD *)this + 12);
      v6 |= 2u;
      v22 = GuidTrace::GuidTrace((GuidTrace *)v33, (const struct _GUID *)((char *)this + 8));
      v23 = GuidTrace::GetString(v22);
      WPP_SF_qDsq(*((_QWORD *)WPP_GLOBAL_Control + 27), 27, v24, (_DWORD)this, v11, (__int64)v23, v21);
    }
    v25 = (v6 & 2) == 0;
    goto LABEL_46;
  }
  unique = wil::make_unique_nothrow<unsigned char [0]>(&EventW, v4);
  wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=((char *)this + 160, unique);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&EventW);
  v14 = (void *)*((_QWORD *)this + 20);
  if ( !v14 )
  {
    v11 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        &WPP_956102e314603234c0af5b934e32accd_Traceguids,
        this,
        -2147024882);
    goto LABEL_40;
  }
  memcpy_0(v14, a3, v4);
  *((_DWORD *)this + 42) = v4;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v34);
  v15 = FSVMEvent::CreateFSVMEvent(a2, &v34);
  v11 = v15;
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_956102e314603234c0af5b934e32accd_Traceguids, this, v15);
    v16 = (const struct _GUID *)((char *)this + 8);
    goto LABEL_39;
  }
  v16 = (const struct _GUID *)((char *)this + 8);
  v17 = (*(__int64 (__fastcall **)(struct IFSVMEvent *, char *))(*(_QWORD *)v34 + 32LL))(v34, (char *)this + 8);
  v11 = v17;
  if ( v17 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_39;
    v18 = 23;
LABEL_23:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_956102e314603234c0af5b934e32accd_Traceguids, this, v17);
    goto LABEL_39;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::swap(
    (char *)this + 96,
    &EventW);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&EventW);
  if ( *((_QWORD *)this + 12) )
  {
    v20 = ppAsyncResult;
    ppAsyncResult = 0;
    if ( v20 )
      ((void (__fastcall *)(IMFAsyncResult *))v20->lpVtbl->Release)(v20);
    v17 = MFCreateAsyncResult(0, (IMFAsyncCallback *)this + 5, 0, &ppAsyncResult);
    v11 = v17;
    if ( v17 >= 0 )
    {
      v17 = MFPutWaitingWorkItem(*((HANDLE *)this + 12), 1, ppAsyncResult, (MFWORKITEM_KEY *)this + 14);
      v11 = v17;
      if ( v17 >= 0 )
      {
        wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=((char *)this + 104, &v34);
        goto LABEL_39;
      }
      if ( !g_wppLevels )
        goto LABEL_39;
      v18 = 26;
    }
    else
    {
      if ( !g_wppLevels )
        goto LABEL_39;
      v18 = 25;
    }
    goto LABEL_23;
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_956102e314603234c0af5b934e32accd_Traceguids, this, v11);
LABEL_39:
  if ( v11 < 0 )
    goto LABEL_40;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v26 = *((_QWORD *)this + 12);
    v6 |= 4u;
    v27 = GuidTrace::GuidTrace((GuidTrace *)v33, v16);
    v28 = GuidTrace::GetString(v27);
    WPP_SF_qDsq(*((_QWORD *)WPP_GLOBAL_Control + 27), 28, v29, (_DWORD)this, v11, (__int64)v28, v26);
  }
  v25 = (v6 & 4) == 0;
LABEL_46:
  if ( !v25 )
    FSString::~FSString((FSString *)v33);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v34);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppAsyncResult);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800d30a0  mov     [rsp-38h+arg_8], rbx
0x1800d30a5  push    rbp
0x1800d30a6  push    rsi
0x1800d30a7  push    rdi
0x1800d30a8  push    r12
0x1800d30aa  push    r13
0x1800d30ac  push    r14
0x1800d30ae  push    r15
0x1800d30b0  mov     rbp, rsp
0x1800d30b3  sub     rsp, 70h
0x1800d30b7  lea     rax, [rcx+30h]
0x1800d30bb  mov     edi, r9d
0x1800d30be  mov     rsi, rcx
0x1800d30c1  mov     [rbp+lpCriticalSection], rax
0x1800d30c5  xor     r15d, r15d
0x1800d30c8  mov     rcx, rax; lpCriticalSection
0x1800d30cb  mov     r14, r8
0x1800d30ce  mov     dword ptr [rbp+arg_0], r15d
0x1800d30d2  mov     r13, rdx
0x1800d30d5  call    cs:__imp_EnterCriticalSection
0x1800d30db  mov     [rbp+ppAsyncResult], r15
0x1800d30df  mov     [rbp+arg_0], r15
0x1800d30e3  cmp     cs:byte_18010EC4D, 8
0x1800d30ea  lea     rbx, WPP_956102e314603234c0af5b934e32accd_Traceguids
0x1800d30f1  jb      short loc_1800D312F
0x1800d30f3  mov     rdx, r13; struct _GUID *
0x1800d30f6  lea     rcx, [rbp+var_20]; this
0x1800d30fa  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800d30ff  mov     rcx, rax; this
0x1800d3102  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800d3107  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d310e  lea     edx, [r15+12h]
0x1800d3112  mov     r9, rsi
0x1800d3115  mov     [rsp+70h+var_50], rax
0x1800d311a  mov     r8, rbx
0x1800d311d  mov     rcx, [rcx+0D8h]
0x1800d3124  call    WPP_SF_qs
0x1800d3129  mov     r15d, 1
0x1800d312f  test    r15b, 1
0x1800d3133  jz      short loc_1800D3142
0x1800d3135  and     r15d, 0FFFFFFFEh
0x1800d3139  lea     rcx, [rbp+var_20]; this
0x1800d313d  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800d3142  test    r14, r14
0x1800d3145  jnz     short loc_1800D317E
0x1800d3147  mov     eax, 80070057h
0x1800d314c  mov     edi, eax
0x1800d314e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d3155  jb      loc_1800D338E
0x1800d315b  lea     edx, [r14+13h]
0x1800d315f  mov     dword ptr [rsp+70h+var_50], eax
0x1800d3163  mov     r8, rbx
0x1800d3166  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d316d  mov     r9, rsi
0x1800d3170  mov     rcx, [rcx+10h]
0x1800d3174  call    WPP_SF_qD
0x1800d3179  jmp     loc_1800D338E
0x1800d317e  cmp     edi, 18h
0x1800d3181  jnb     short loc_1800D319E
0x1800d3183  mov     eax, 80070057h
0x1800d3188  mov     edi, eax
0x1800d318a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d3191  jb      loc_1800D338E
0x1800d3197  mov     edx, 14h
0x1800d319c  jmp     short loc_1800D315F
0x1800d319e  mov     rdx, rdi
0x1800d31a1  lea     rcx, [rbp+var_30]
0x1800d31a5  lea     rbx, [rsi+0A0h]
0x1800d31ac  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x1800d31b1  mov     rdx, rax
0x1800d31b4  mov     rcx, rbx
0x1800d31b7  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x1800d31bc  lea     rcx, [rbp+var_30]
0x1800d31c0  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x1800d31c5  mov     rcx, [rbx]; void *
0x1800d31c8  test    rcx, rcx
0x1800d31cb  jnz     short loc_1800D31F2
0x1800d31cd  mov     edi, 8007000Eh
0x1800d31d2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d31d9  jb      loc_1800D338E
0x1800d31df  lea     edx, [rcx+15h]
0x1800d31e2  mov     dword ptr [rsp+70h+var_50], edi
0x1800d31e6  lea     r8, WPP_956102e314603234c0af5b934e32accd_Traceguids
0x1800d31ed  jmp     loc_1800D3166
0x1800d31f2  mov     r8, rdi; Size
0x1800d31f5  mov     rdx, r14; Src
0x1800d31f8  call    memcpy_0
0x1800d31fd  lea     rcx, [rbp+arg_0]
0x1800d3201  mov     [rsi+0A8h], edi
0x1800d3207  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800d320c  lea     rdx, [rbp+arg_0]; struct IFSVMEvent **
0x1800d3210  mov     rcx, r13; struct _GUID *
0x1800d3213  call    ?CreateFSVMEvent@FSVMEvent@@SAJAEBU_GUID@@PEAPEAUIFSVMEvent@@@Z; FSVMEvent::CreateFSVMEvent(_GUID const &,IFSVMEvent * *)
0x1800d3218  mov     edi, eax
0x1800d321a  test    eax, eax
0x1800d321c  jns     short loc_1800D3253
0x1800d321e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d3225  jb      short loc_1800D324A
0x1800d3227  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d322e  lea     r8, WPP_956102e314603234c0af5b934e32accd_Traceguids
0x1800d3235  mov     edx, 16h
0x1800d323a  mov     dword ptr [rsp+70h+var_50], eax
0x1800d323e  mov     r9, rsi
0x1800d3241  mov     rcx, [rcx+10h]
0x1800d3245  call    WPP_SF_qD
0x1800d324a  lea     r14, [rsi+8]
0x1800d324e  jmp     loc_1800D338A
0x1800d3253  mov     rcx, [rbp+arg_0]
0x1800d3257  lea     r14, [rsi+8]
0x1800d325b  mov     rdx, r14
0x1800d325e  mov     rax, [rcx]
0x1800d3261  mov     rax, [rax+20h]
0x1800d3265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d326a  mov     edi, eax
0x1800d326c  test    eax, eax
0x1800d326e  jns     short loc_1800D32A5
0x1800d3270  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d3277  jb      loc_1800D338A
0x1800d327d  mov     edx, 17h
0x1800d3282  mov     dword ptr [rsp+70h+var_50], eax
0x1800d3286  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d328d  lea     r8, WPP_956102e314603234c0af5b934e32accd_Traceguids
0x1800d3294  mov     r9, rsi
0x1800d3297  mov     rcx, [rcx+10h]
0x1800d329b  call    WPP_SF_qD
0x1800d32a0  jmp     loc_1800D338A
0x1800d32a5  xor     r9d, r9d; lpName
0x1800d32a8  xor     r8d, r8d; bInitialState
0x1800d32ab  xor     edx, edx; bManualReset
0x1800d32ad  xor     ecx, ecx; lpEventAttributes
0x1800d32af  call    cs:__imp_CreateEventW
0x1800d32b5  lea     rbx, [rsi+60h]
0x1800d32b9  mov     [rbp+var_30], rax
0x1800d32bd  mov     rcx, rbx
0x1800d32c0  lea     rdx, [rbp+var_30]
0x1800d32c4  call    ?swap@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x1800d32c9  lea     rcx, [rbp+var_30]
0x1800d32cd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d32d2  cmp     qword ptr [rbx], 0
0x1800d32d6  jnz     short loc_1800D3305
0x1800d32d8  call    cs:__imp_GetLastError
0x1800d32de  mov     edi, eax
0x1800d32e0  test    eax, eax
0x1800d32e2  jle     short loc_1800D32ED
0x1800d32e4  movzx   edi, ax
0x1800d32e7  or      edi, 80070000h
0x1800d32ed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d32f4  jb      loc_1800D338A
0x1800d32fa  mov     edx, 18h
0x1800d32ff  mov     dword ptr [rsp+70h+var_50], edi
0x1800d3303  jmp     short loc_1800D3286
0x1800d3305  mov     rcx, [rbp+ppAsyncResult]
0x1800d3309  mov     [rbp+ppAsyncResult], 0
0x1800d3311  test    rcx, rcx
0x1800d3314  jz      short loc_1800D3322
0x1800d3316  mov     rax, [rcx]
0x1800d3319  mov     rax, [rax+10h]
0x1800d331d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3322  lea     rdx, [rsi+28h]; pCallback
0x1800d3326  xor     r8d, r8d; punkState
0x1800d3329  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x1800d332d  xor     ecx, ecx; punkObject
0x1800d332f  call    cs:__imp_MFCreateAsyncResult
0x1800d3335  mov     edi, eax
0x1800d3337  test    eax, eax
0x1800d3339  jns     short loc_1800D334E
0x1800d333b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d3342  jb      short loc_1800D338A
0x1800d3344  mov     edx, 19h
0x1800d3349  jmp     loc_1800D3282
0x1800d334e  mov     r8, [rbp+ppAsyncResult]; pResult
0x1800d3352  lea     r9, [rsi+70h]; pKey
0x1800d3356  mov     rcx, [rbx]; hEvent
0x1800d3359  mov     edx, 1; Priority
0x1800d335e  call    cs:__imp_MFPutWaitingWorkItem
0x1800d3364  mov     edi, eax
0x1800d3366  test    eax, eax
0x1800d3368  jns     short loc_1800D337D
0x1800d336a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d3371  jb      short loc_1800D338A
0x1800d3373  mov     edx, 1Ah
0x1800d3378  jmp     loc_1800D3282
0x1800d337d  lea     rcx, [rsi+68h]
0x1800d3381  lea     rdx, [rbp+arg_0]
0x1800d3385  call    ??4?$com_ptr_t@UIFSControl@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IFSControl,wil::err_returncode_policy> const &)
0x1800d338a  test    edi, edi
0x1800d338c  jns     short loc_1800D33E3
0x1800d338e  cmp     cs:byte_18010EC4D, 1
0x1800d3395  jb      short loc_1800D33DD
0x1800d3397  mov     rbx, [rsi+60h]
0x1800d339b  lea     rdx, [rsi+8]; struct _GUID *
0x1800d339f  lea     rcx, [rbp+var_20]; this
0x1800d33a3  or      r15d, 2
0x1800d33a7  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800d33ac  mov     rcx, rax; this
0x1800d33af  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800d33b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d33bb  mov     edx, 1Bh
0x1800d33c0  mov     [rsp+70h+var_40], rbx
0x1800d33c5  mov     r9, rsi
0x1800d33c8  mov     [rsp+70h+var_48], rax
0x1800d33cd  mov     dword ptr [rsp+70h+var_50], edi
0x1800d33d1  mov     rcx, [rcx+0D8h]
0x1800d33d8  call    WPP_SF_qDsq
0x1800d33dd  test    r15b, 2
0x1800d33e1  jmp     short loc_1800D3435
0x1800d33e3  cmp     cs:byte_18010EC4D, 8
0x1800d33ea  jb      short loc_1800D3431
0x1800d33ec  mov     rbx, [rsi+60h]
0x1800d33f0  lea     rcx, [rbp+var_20]; this
0x1800d33f4  mov     rdx, r14; struct _GUID *
0x1800d33f7  or      r15d, 4
0x1800d33fb  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800d3400  mov     rcx, rax; this
0x1800d3403  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800d3408  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d340f  mov     edx, 1Ch
0x1800d3414  mov     [rsp+70h+var_40], rbx
0x1800d3419  mov     r9, rsi
0x1800d341c  mov     [rsp+70h+var_48], rax
0x1800d3421  mov     dword ptr [rsp+70h+var_50], edi
0x1800d3425  mov     rcx, [rcx+0D8h]
0x1800d342c  call    WPP_SF_qDsq
0x1800d3431  test    r15b, 4
0x1800d3435  jz      short loc_1800D3440
0x1800d3437  lea     rcx, [rbp+var_20]; this
0x1800d343b  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800d3440  lea     rcx, [rbp+arg_0]; void *
0x1800d3444  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800d3449  lea     rcx, [rbp+ppAsyncResult]; void *
0x1800d344d  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800d3452  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800d3456  call    cs:__imp_LeaveCriticalSection
0x1800d345c  mov     rbx, [rsp+70h+arg_8]
0x1800d3464  mov     eax, edi
0x1800d3466  add     rsp, 70h
0x1800d346a  pop     r15
0x1800d346c  pop     r14
0x1800d346e  pop     r13
0x1800d3470  pop     r12
0x1800d3472  pop     rdi
0x1800d3473  pop     rsi
0x1800d3474  pop     rbp
0x1800d3475  retn
```
