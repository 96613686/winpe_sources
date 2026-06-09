# WpnUserService::RegisterClassFactoryCallback(tagComCallData *)

- ea: `0x18000b740`
- end: `0x18000ba6e`
- name: `?RegisterClassFactoryCallback@WpnUserService@@SAJPEAUtagComCallData@@@Z`
- size: `814`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180006224`
- `0x180006244`
- `0x18000a648`
- `0x18000b740`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b998`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b977`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000b987`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000b987`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b990`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b990`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000ba18`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000ba18`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000b962`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000b962`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b7a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b943`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b7a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b943`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18000b85d`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18000b85d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000b8b5`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000b8b5`

## string_xrefs

- `0x18000b764`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x18000b7b8`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x18000b870`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x18000b9ae`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`

## pseudocode

```c
__int64 __fastcall WpnUserService::RegisterClassFactoryCallback(struct tagComCallData *a1)
{
  unsigned int v1; // ebx
  void *pUserDefined; // r14
  HRESULT Instance; // eax
  LPUNKNOWN v5; // rcx
  __int64 v6; // rbx
  const struct _tlgProvider_t *v7; // rax
  int v8; // r9d
  const struct _tlgProvider_t *v9; // r8
  __int64 v10; // rax
  HRESULT v11; // eax
  LPUNKNOWN v12; // rcx
  __int64 v13; // rbx
  const struct _tlgProvider_t *v14; // rax
  int v15; // r9d
  const struct _tlgProvider_t *v16; // r8
  __int64 v17; // rax
  PTP_WORK *v18; // rdi
  PTP_WORK ThreadpoolWork; // rsi
  const char *v20; // r9
  struct _TP_WORK *v21; // r15
  DWORD LastError; // ebx
  LPVOID v23; // rcx
  LPUNKNOWN v24; // rcx
  LPVOID v25; // rcx
  LPVOID v26; // rcx
  LPUNKNOWN v27; // rcx
  int ppv; // [rsp+20h] [rbp-10h]
  int ppva; // [rsp+20h] [rbp-10h]
  int ppvb; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  LPVOID v32; // [rsp+60h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+68h] [rbp+38h] BYREF
  __int64 v34; // [rsp+70h] [rbp+40h] BYREF

  if ( !a1 )
  {
    v1 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
      (const char *)0x80070057LL,
      ppv);
    return v1;
  }
  pUserDefined = a1->pUserDefined;
  pUnk = 0;
  Instance = CoCreateInstance(
               &GUID_4655840e_ab1a_49d0_a4c4_261fa1c20e86,
               0,
               1u,
               &GUID_00000001_0000_0000_c000_000000000046,
               (LPVOID *)&pUnk);
  v1 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
    v5 = pUnk;
    if ( pUnk )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v5->lpVtbl->Release)(v5);
    }
    return v1;
  }
  v6 = *((_QWORD *)pUserDefined + 3);
  v7 = ServiceHostLogging::Provider();
  v9 = v7;
  if ( *(_DWORD *)v7 > 5u )
  {
    v10 = *((_QWORD *)v7 + 3);
    if ( (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
    {
      v32 = (LPVOID)(v6 + 8);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v9,
        (unsigned int)word_180014A5A,
        (_DWORD)v9,
        v8,
        (__int64)&v32);
    }
  }
  v11 = CoRegisterClassObject(&GUID_0c9281f9_6da1_4006_8729_de6e6b61581c, pUnk, 4u, 1u, *((LPDWORD *)pUserDefined + 1));
  v1 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x142,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
      (const char *)(unsigned int)v11,
      ppvb);
    v12 = pUnk;
    if ( pUnk )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v12->lpVtbl->Release)(v12);
    }
    return v1;
  }
  LODWORD(v32) = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v32, 0);
  if ( (_DWORD)v32 != 5 && (unsigned int)((_DWORD)v32 - 11) > 1 )
  {
    v13 = *((_QWORD *)pUserDefined + 3);
    v14 = ServiceHostLogging::Provider();
    v16 = v14;
    if ( *(_DWORD *)v14 > 5u )
    {
      v17 = *((_QWORD *)v14 + 3);
      if ( (*((_QWORD *)v16 + 2) & 0x400000000000LL) != 0 && (v17 & 0x400000000000LL) == v17 )
      {
        v34 = v13 + 8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v16,
          (unsigned int)&word_180014A26,
          (_DWORD)v16,
          v15,
          (__int64)&v34);
      }
    }
    v32 = 0;
    if ( CoCreateInstance(
           &GUID_77963c0e_91ba_479e_9192_686dda6bb722,
           0,
           0x17u,
           &GUID_f7c1d568_9f5d_4941_b642_e47265ec651b,
           &v32) >= 0 )
    {
      v18 = (PTP_WORK *)*((_QWORD *)pUserDefined + 3);
      ThreadpoolWork = CreateThreadpoolWork(lambda_1d7b18912370aa61c0520429307583ff_::_lambda_invoker_cdecl_, v18, 0);
      v21 = v18[29];
      if ( v21 )
      {
        LastError = GetLastError();
        WaitForThreadpoolWorkCallbacks(v21, 1);
        CloseThreadpoolWork(v21);
        SetLastError(LastError);
      }
      v18[29] = ThreadpoolWork;
      if ( !ThreadpoolWork )
      {
        v1 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x15B,
               (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
               v20);
        v23 = v32;
        if ( v32 )
        {
          v32 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
        }
        v24 = pUnk;
        if ( pUnk )
        {
          pUnk = 0;
          ((void (__fastcall *)(LPUNKNOWN))v24->lpVtbl->Release)(v24);
        }
        return v1;
      }
      v25 = v32;
      v32 = 0;
      **((_QWORD **)pUserDefined + 2) = v25;
      SubmitThreadpoolWork(v18[29]);
    }
    v26 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
    }
  }
  v27 = pUnk;
  if ( pUnk )
  {
    pUnk = 0;
    ((void (__fastcall *)(LPUNKNOWN))v27->lpVtbl->Release)(v27);
  }
  return 0;
}

```

## disassembly

```asm
0x18000b740  mov     [rsp-28h+arg_18], rbx
0x18000b745  push    rbp
0x18000b746  push    rsi
0x18000b747  push    rdi
0x18000b748  push    r14
0x18000b74a  push    r15
0x18000b74c  mov     rbp, rsp
0x18000b74f  sub     rsp, 30h
0x18000b753  test    rcx, rcx
0x18000b756  jnz     short loc_18000B77C
0x18000b758  mov     rcx, [rbp+28h]; this
0x18000b75c  mov     ebx, 80070057h
0x18000b761  mov     r9d, ebx; char *
0x18000b764  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000b76b  mov     edx, 130h; void *
0x18000b770  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b775  mov     eax, ebx
0x18000b777  jmp     loc_18000BA5D
0x18000b77c  mov     r14, [rcx+8]
0x18000b780  mov     [rbp+pUnk], 0
0x18000b788  lea     rax, [rbp+pUnk]
0x18000b78c  mov     qword ptr [rsp+30h+ppv], rax; int
0x18000b791  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18000b798  xor     edx, edx; pUnkOuter
0x18000b79a  lea     r8d, [rdx+1]; dwClsContext
0x18000b79e  lea     rcx, _GUID_4655840e_ab1a_49d0_a4c4_261fa1c20e86; rclsid
0x18000b7a5  call    cs:__imp_CoCreateInstance
0x18000b7ab  mov     ebx, eax
0x18000b7ad  test    eax, eax
0x18000b7af  jns     short loc_18000B7EA
0x18000b7b1  mov     rcx, [rbp+28h]; this
0x18000b7b5  mov     r9d, eax; char *
0x18000b7b8  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000b7bf  mov     edx, 139h; void *
0x18000b7c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b7c9  nop
0x18000b7ca  mov     rcx, [rbp+pUnk]
0x18000b7ce  test    rcx, rcx
0x18000b7d1  jz      short loc_18000B7E8
0x18000b7d3  mov     [rbp+pUnk], 0
0x18000b7db  mov     rax, [rcx]
0x18000b7de  mov     rax, [rax+10h]
0x18000b7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7e7  nop
0x18000b7e8  jmp     short loc_18000B775
0x18000b7ea  mov     rbx, [r14+18h]
0x18000b7ee  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000b7f3  mov     r8, rax
0x18000b7f6  mov     ecx, [rax]
0x18000b7f8  mov     rdi, 400000000000h
0x18000b802  cmp     ecx, 5
0x18000b805  jbe     short loc_18000B83F
0x18000b807  mov     rax, [rax+18h]
0x18000b80b  mov     rcx, [r8+10h]
0x18000b80f  test    rdi, rcx
0x18000b812  jz      short loc_18000B83F
0x18000b814  mov     rcx, rax
0x18000b817  and     rcx, rdi
0x18000b81a  cmp     rcx, rax
0x18000b81d  jnz     short loc_18000B83F
0x18000b81f  lea     rax, [rbx+8]
0x18000b823  mov     [rbp+arg_0], rax
0x18000b827  lea     rax, [rbp+arg_0]
0x18000b82b  mov     qword ptr [rsp+30h+ppv], rax
0x18000b830  lea     rdx, word_180014A5A
0x18000b837  mov     rcx, r8
0x18000b83a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000b83f  mov     rax, [r14+8]
0x18000b843  mov     qword ptr [rsp+30h+ppv], rax; int
0x18000b848  mov     r9d, 1; flags
0x18000b84e  lea     r8d, [r9+3]; dwClsContext
0x18000b852  mov     rdx, [rbp+pUnk]; pUnk
0x18000b856  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x18000b85d  call    cs:__imp_CoRegisterClassObject
0x18000b863  mov     ebx, eax
0x18000b865  test    eax, eax
0x18000b867  jns     short loc_18000B8A5
0x18000b869  mov     rcx, [rbp+28h]; this
0x18000b86d  mov     r9d, eax; char *
0x18000b870  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000b877  mov     edx, 142h; void *
0x18000b87c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b881  nop
0x18000b882  mov     rcx, [rbp+pUnk]
0x18000b886  test    rcx, rcx
0x18000b889  jz      short loc_18000B8A0
0x18000b88b  mov     [rbp+pUnk], 0
0x18000b893  mov     rax, [rcx]
0x18000b896  mov     rax, [rax+10h]
0x18000b89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b89f  nop
0x18000b8a0  jmp     loc_18000B775
0x18000b8a5  mov     dword ptr [rbp+arg_0], 0
0x18000b8ac  xor     r8d, r8d
0x18000b8af  lea     rdx, [rbp+arg_0]
0x18000b8b3  xor     ecx, ecx
0x18000b8b5  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18000b8bb  mov     eax, dword ptr [rbp+arg_0]
0x18000b8be  cmp     eax, 5
0x18000b8c1  jz      loc_18000BA3D
0x18000b8c7  add     eax, 0FFFFFFF5h
0x18000b8ca  cmp     eax, 1
0x18000b8cd  jbe     loc_18000BA3D
0x18000b8d3  mov     rbx, [r14+18h]
0x18000b8d7  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000b8dc  mov     r8, rax
0x18000b8df  mov     ecx, [rax]
0x18000b8e1  cmp     ecx, 5
0x18000b8e4  jbe     short loc_18000B91E
0x18000b8e6  mov     rax, [rax+18h]
0x18000b8ea  mov     rcx, [r8+10h]
0x18000b8ee  test    rdi, rcx
0x18000b8f1  jz      short loc_18000B91E
0x18000b8f3  mov     rcx, rax
0x18000b8f6  and     rcx, rdi
0x18000b8f9  cmp     rcx, rax
0x18000b8fc  jnz     short loc_18000B91E
0x18000b8fe  lea     rax, [rbx+8]
0x18000b902  mov     [rbp+arg_10], rax
0x18000b906  lea     rax, [rbp+arg_10]
0x18000b90a  mov     qword ptr [rsp+30h+ppv], rax
0x18000b90f  lea     rdx, word_180014A26
0x18000b916  mov     rcx, r8
0x18000b919  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000b91e  mov     [rbp+arg_0], 0
0x18000b926  lea     rax, [rbp+arg_0]
0x18000b92a  mov     qword ptr [rsp+30h+ppv], rax; ppv
0x18000b92f  lea     r9, _GUID_f7c1d568_9f5d_4941_b642_e47265ec651b; riid
0x18000b936  xor     edx, edx; pUnkOuter
0x18000b938  lea     r8d, [rdx+17h]; dwClsContext
0x18000b93c  lea     rcx, _GUID_77963c0e_91ba_479e_9192_686dda6bb722; rclsid
0x18000b943  call    cs:__imp_CoCreateInstance
0x18000b949  test    eax, eax
0x18000b94b  js      loc_18000BA1F
0x18000b951  mov     rdi, [r14+18h]
0x18000b955  xor     r8d, r8d; pcbe
0x18000b958  mov     rdx, rdi; pv
0x18000b95b  lea     rcx, _lambda_1d7b18912370aa61c0520429307583ff____lambda_invoker_cdecl_; pfnwk
0x18000b962  call    cs:__imp_CreateThreadpoolWork
0x18000b968  mov     rsi, rax
0x18000b96b  mov     r15, [rdi+0E8h]
0x18000b972  test    r15, r15
0x18000b975  jz      short loc_18000B99E
0x18000b977  call    cs:__imp_GetLastError
0x18000b97d  mov     ebx, eax
0x18000b97f  mov     edx, 1; fCancelPendingCallbacks
0x18000b984  mov     rcx, r15; pwk
0x18000b987  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000b98d  mov     rcx, r15; pwk
0x18000b990  call    cs:__imp_CloseThreadpoolWork
0x18000b996  mov     ecx, ebx; dwErrCode
0x18000b998  call    cs:__imp_SetLastError
0x18000b99e  mov     [rdi+0E8h], rsi
0x18000b9a5  test    rsi, rsi
0x18000b9a8  jnz     short loc_18000B9FE
0x18000b9aa  mov     rcx, [rbp+28h]; this
0x18000b9ae  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000b9b5  mov     edx, 15Bh; void *
0x18000b9ba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b9bf  mov     ebx, eax
0x18000b9c1  mov     rcx, [rbp+arg_0]
0x18000b9c5  test    rcx, rcx
0x18000b9c8  jz      short loc_18000B9DB
0x18000b9ca  mov     [rbp+arg_0], rsi
0x18000b9ce  mov     rdx, [rcx]
0x18000b9d1  mov     rax, [rdx+10h]
0x18000b9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9da  nop
0x18000b9db  mov     rcx, [rbp+pUnk]
0x18000b9df  test    rcx, rcx
0x18000b9e2  jz      short loc_18000B9F9
0x18000b9e4  mov     [rbp+pUnk], 0
0x18000b9ec  mov     rax, [rcx]
0x18000b9ef  mov     rax, [rax+10h]
0x18000b9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9f8  nop
0x18000b9f9  jmp     loc_18000B775
0x18000b9fe  mov     rcx, [rbp+arg_0]
0x18000ba02  mov     [rbp+arg_0], 0
0x18000ba0a  mov     rax, [r14+10h]
0x18000ba0e  mov     [rax], rcx
0x18000ba11  mov     rcx, [rdi+0E8h]; pwk
0x18000ba18  call    cs:__imp_SubmitThreadpoolWork
0x18000ba1e  nop
0x18000ba1f  mov     rcx, [rbp+arg_0]
0x18000ba23  test    rcx, rcx
0x18000ba26  jz      short loc_18000BA3D
0x18000ba28  mov     [rbp+arg_0], 0
0x18000ba30  mov     rax, [rcx]
0x18000ba33  mov     rax, [rax+10h]
0x18000ba37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba3c  nop
0x18000ba3d  mov     rcx, [rbp+pUnk]
0x18000ba41  test    rcx, rcx
0x18000ba44  jz      short loc_18000BA5B
0x18000ba46  mov     [rbp+pUnk], 0
0x18000ba4e  mov     rax, [rcx]
0x18000ba51  mov     rax, [rax+10h]
0x18000ba55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba5a  nop
0x18000ba5b  xor     eax, eax
0x18000ba5d  mov     rbx, [rsp+30h+arg_18]
0x18000ba62  add     rsp, 30h
0x18000ba66  pop     r15
0x18000ba68  pop     r14
0x18000ba6a  pop     rdi
0x18000ba6b  pop     rsi
0x18000ba6c  pop     rbp
0x18000ba6d  retn
```
