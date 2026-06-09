# CStandardCollectorService::OnStart(ServiceOptions const &)

- ea: `0x140007f38`
- end: `0x140008364`
- name: `?OnStart@CStandardCollectorService@@AEAAJAEBUServiceOptions@@@Z`
- size: `1068`
- prototype: `HRESULT __fastcall(CStandardCollectorService *this, const struct ServiceOptions *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140007da0`

## callees

- `0x140002e74`
- `0x140003158`
- `0x140007f38`
- `0x140008b94`
- `0x1400137e0`
- `0x140013834`
- `0x14001473e`
- `0x140014c70`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x140008268`
- `KERNEL32!CreateThreadpoolTimer` at `0x140008268`
- `KERNEL32!InitializeCriticalSection` at `0x1400080eb`
- `KERNEL32!InitializeCriticalSection` at `0x140008155`
- `KERNEL32!InitializeCriticalSection` at `0x1400080eb`
- `KERNEL32!InitializeCriticalSection` at `0x140008155`
- `KERNEL32!SetThreadpoolTimer` at `0x1400082c2`
- `KERNEL32!SetThreadpoolTimer` at `0x1400082c2`
- `KERNEL32!GetLastError` at `0x14000821f`
- `KERNEL32!GetLastError` at `0x14000827a`
- `KERNEL32!GetLastError` at `0x14000821f`
- `KERNEL32!GetLastError` at `0x14000827a`
- `ole32!CoInitializeSecurity` at `0x140007f97`
- `ole32!CoInitializeSecurity` at `0x140007f97`
- `ole32!CoResumeClassObjects` at `0x1400081ab`
- `ole32!CoResumeClassObjects` at `0x1400081ec`
- `ole32!CoResumeClassObjects` at `0x1400081ab`
- `ole32!CoResumeClassObjects` at `0x1400081ec`
- `ole32!CoRegisterClassObject` at `0x1400081a1`
- `ole32!CoRegisterClassObject` at `0x1400081e2`
- `ole32!CoRegisterClassObject` at `0x1400081a1`
- `ole32!CoRegisterClassObject` at `0x1400081e2`
- `ole32!CoCreateInstance` at `0x140007fd3`
- `ole32!CoCreateInstance` at `0x140007fd3`
- `ADVAPI32!SetServiceStatus` at `0x140008215`
- `ADVAPI32!SetServiceStatus` at `0x140008215`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
HRESULT __fastcall CStandardCollectorService::OnStart(CStandardCollectorService *this, const struct ServiceOptions *a2)
{
  int v4; // ebx
  HRESULT Instance; // esi
  unsigned __int16 v6; // cx
  unsigned __int16 v7; // r8
  HRESULT result; // eax
  char *v9; // rsi
  __int64 v10; // rcx
  _QWORD *v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rcx
  signed int LastError; // eax
  signed int v15; // ecx
  PTP_TIMER ThreadpoolTimer; // rax
  signed int v17; // eax
  struct _TP_TIMER *v18; // rcx
  int v19; // eax
  void **v20; // [rsp+50h] [rbp-78h] BYREF
  __int128 v21; // [rsp+58h] [rbp-70h]
  void ***v22; // [rsp+88h] [rbp-40h]
  int v23; // [rsp+90h] [rbp-38h] BYREF
  LPVOID ppv[2]; // [rsp+98h] [rbp-30h] BYREF

  v4 = 0;
  Instance = CoInitializeSecurity(&CLSID_StandardCollectorHost, 0, 0, 0, 0, 0, 0, 8u, 0);
  if ( Instance < 0 )
    return Instance;
  ppv[0] = 0;
  Instance = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, ppv);
  if ( Instance < 0 )
  {
    if ( ppv[0] )
      goto LABEL_11;
    return Instance;
  }
  Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv[0] + 24LL))(ppv[0], 1, 2);
  if ( Instance < 0 )
  {
    if ( ppv[0] )
      goto LABEL_11;
    return Instance;
  }
  if ( IsWindowsVersionOrGreater(v6, 2u, v7) )
  {
    Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv[0] + 24LL))(ppv[0], 5, 1);
    if ( Instance < 0 )
    {
      if ( ppv[0] )
LABEL_11:
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
      return Instance;
    }
  }
  if ( ppv[0] )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
  v23 = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v9 = (char *)operator new(0x40u);
    *((_DWORD *)v9 + 3) = 0;
    *(_QWORD *)v9 = &StandardCollectorHostClassFactory::`vftable';
    *((_DWORD *)v9 + 2) = 1;
    *((_QWORD *)v9 + 2) = 0;
    *(_OWORD *)(v9 + 24) = 0;
    *(_OWORD *)(v9 + 40) = 0;
    *((_QWORD *)v9 + 7) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v9 + 24));
    v10 = *((_QWORD *)this + 9);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      result = -2147024882;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_140008325);
      return result;
    }
  }
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    *((_QWORD *)this + 9) = v9;
    v11 = operator new(0x48u);
    ppv[0] = v11;
    memset_0(v11, 0, 0x48u);
    v12 = *((_QWORD *)this + 9);
    if ( !v12 )
      ATL::AtlThrowImpl(-2147467259);
    *v11 = &CStandardCollectorClassFactory::`vftable';
    *((_DWORD *)v11 + 2) = 1;
    v11[2] = v12;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v11 + 4));
    v13 = *((_QWORD *)this + 8);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      result = -2147024882;
      __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_140008325);
      return result;
    }
  }
  *((_QWORD *)this + 8) = v11;
  if ( *(_DWORD *)a2 == 5 )
  {
    result = CoRegisterClassObject(&CLSID_StandardCollectorService, (LPUNKNOWN)v11, 4u, 5u, (LPDWORD)this + 9);
    if ( result )
    {
      if ( result != -2147220996 )
        return result;
    }
    else
    {
      result = CoResumeClassObjects();
      if ( result < 0 )
        return result;
    }
    result = CoRegisterClassObject(&CLSID_StandardCollectorHost, *((LPUNKNOWN *)this + 9), 4u, 5u, (LPDWORD)this + 10);
    if ( result )
    {
      if ( result != -2147220996 )
        return result;
    }
    else
    {
      result = CoResumeClassObjects();
      if ( result < 0 )
        return result;
    }
    *((_DWORD *)this + 4) |= 5u;
    *((_DWORD *)this + 3) = 4;
    if ( SetServiceStatus(*(SERVICE_STATUS_HANDLE *)this, (LPSERVICE_STATUS)((char *)this + 8)) )
      return 0;
    LastError = GetLastError();
    v15 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      return LastError;
    return v15;
  }
  if ( *((_BYTE *)a2 + 40) )
  {
    if ( *((_QWORD *)this + 24) )
      return -518979540;
    ThreadpoolTimer = CreateThreadpoolTimer(CStandardCollectorService::MarshallerShutdown, 0, 0);
    *((_QWORD *)this + 24) = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
    {
      v17 = GetLastError();
      v15 = (unsigned __int16)v17 | 0x80070000;
      if ( v17 <= 0 )
        v15 = v17;
      if ( v15 < 0 )
        return v15;
    }
    v18 = (struct _TP_TIMER *)*((_QWORD *)this + 24);
    if ( !v18 )
      return -2147024875;
    ppv[0] = (LPVOID)-300000000LL;
    SetThreadpoolTimer(v18, (PFILETIME)ppv, 0, 0);
    v23 = 0;
  }
  ppv[0] = &v23;
  ppv[1] = this;
  v20 = &std::_Func_impl_no_alloc<_lambda_4bc228a33a7adc1015eb6bff6e85dd8e_,long,DiagHubCommon::AutoEvent const &,void *>::`vftable';
  v21 = *(_OWORD *)ppv;
  v22 = &v20;
  v19 = DiagHubCommon::HubTask<long,0>::Start((char *)this + 80);
  if ( v19 < 0 )
    return v19;
  return v4;
}

```

## disassembly

```asm
0x140007f38  mov     [rsp+arg_8], rbx
0x140007f3d  mov     [rsp+arg_10], rsi
0x140007f42  mov     [rsp+arg_18], rdi
0x140007f47  push    r12
0x140007f49  push    r13
0x140007f4b  push    r14
0x140007f4d  sub     rsp, 0B0h
0x140007f54  mov     rax, cs:__security_cookie
0x140007f5b  xor     rax, rsp
0x140007f5e  mov     [rsp+0C8h+var_20], rax
0x140007f66  mov     r12, rdx
0x140007f69  mov     rdi, rcx
0x140007f6c  xor     ebx, ebx
0x140007f6e  mov     [rsp+0C8h+pReserved3], rbx; pReserved3
0x140007f73  mov     [rsp+0C8h+dwCapabilities], 8; dwCapabilities
0x140007f7b  mov     [rsp+0C8h+pAuthList], rbx; pAuthList
0x140007f80  mov     [rsp+0C8h+dwImpLevel], ebx; dwImpLevel
0x140007f84  mov     [rsp+0C8h+dwAuthnLevel], ebx; dwAuthnLevel
0x140007f88  xor     r9d, r9d; pReserved1
0x140007f8b  xor     r8d, r8d; asAuthSvc
0x140007f8e  xor     edx, edx; cAuthSvc
0x140007f90  lea     rcx, CLSID_StandardCollectorHost; pSecDesc
0x140007f97  call    cs:__imp_CoInitializeSecurity
0x140007f9d  mov     esi, eax
0x140007f9f  test    eax, eax
0x140007fa1  js      loc_14000808C
0x140007fa7  mov     [rsp+0C8h+ppv], rbx
0x140007faf  lea     rax, [rsp+0C8h+ppv]
0x140007fb7  mov     qword ptr [rsp+0C8h+dwAuthnLevel], rax; ppv
0x140007fbc  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x140007fc3  lea     r13d, [rbx+1]
0x140007fc7  mov     r8d, r13d; dwClsContext
0x140007fca  xor     edx, edx; pUnkOuter
0x140007fcc  lea     rcx, CLSID_GlobalOptions; rclsid
0x140007fd3  call    cs:__imp_CoCreateInstance
0x140007fd9  mov     esi, eax
0x140007fdb  test    eax, eax
0x140007fdd  jns     short loc_140007FFF
0x140007fdf  mov     rcx, [rsp+0C8h+ppv]
0x140007fe7  test    rcx, rcx
0x140007fea  jz      short loc_140007FFA
0x140007fec  mov     rax, [rcx]
0x140007fef  mov     rax, [rax+10h]
0x140007ff3  call    cs:__guard_dispatch_icall_fptr
0x140007ff9  nop
0x140007ffa  jmp     loc_14000808C
0x140007fff  mov     rcx, [rsp+0C8h+ppv]
0x140008007  mov     rax, [rcx]
0x14000800a  mov     r8d, 2
0x140008010  mov     edx, r13d
0x140008013  mov     rax, [rax+18h]
0x140008017  call    cs:__guard_dispatch_icall_fptr
0x14000801d  mov     esi, eax
0x14000801f  test    eax, eax
0x140008021  jns     short loc_140008040
0x140008023  mov     rcx, [rsp+0C8h+ppv]
0x14000802b  test    rcx, rcx
0x14000802e  jz      short loc_14000803E
0x140008030  mov     rax, [rcx]
0x140008033  mov     rax, [rax+10h]
0x140008037  call    cs:__guard_dispatch_icall_fptr
0x14000803d  nop
0x14000803e  jmp     short loc_14000808C
0x140008040  mov     edx, 2; unsigned __int16
0x140008045  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x14000804a  test    al, al
0x14000804c  jz      short loc_140008093
0x14000804e  mov     rcx, [rsp+0C8h+ppv]
0x140008056  mov     rax, [rcx]
0x140008059  mov     r8, r13
0x14000805c  mov     edx, 5
0x140008061  mov     rax, [rax+18h]
0x140008065  call    cs:__guard_dispatch_icall_fptr
0x14000806b  mov     esi, eax
0x14000806d  test    eax, eax
0x14000806f  jns     short loc_140008093
0x140008071  mov     rcx, [rsp+0C8h+ppv]
0x140008079  test    rcx, rcx
0x14000807c  jz      short loc_14000808C
0x14000807e  mov     rax, [rcx]
0x140008081  mov     rax, [rax+10h]
0x140008085  call    cs:__guard_dispatch_icall_fptr
0x14000808b  nop
0x14000808c  mov     eax, esi
0x14000808e  jmp     loc_14000832A
0x140008093  mov     rcx, [rsp+0C8h+ppv]
0x14000809b  test    rcx, rcx
0x14000809e  jz      short loc_1400080AE
0x1400080a0  mov     rax, [rcx]
0x1400080a3  mov     rax, [rax+10h]
0x1400080a7  call    cs:__guard_dispatch_icall_fptr
0x1400080ad  nop
0x1400080ae  mov     [rsp+0C8h+var_38], ebx
0x1400080b5  mov     ecx, 40h ; '@'; Size
0x1400080ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400080bf  mov     rsi, rax
0x1400080c2  mov     [rax+0Ch], ebx
0x1400080c5  lea     rax, ??_7StandardCollectorHostClassFactory@@6B@; const StandardCollectorHostClassFactory::`vftable'
0x1400080cc  mov     [rsi], rax
0x1400080cf  mov     [rsi+8], r13d
0x1400080d3  mov     [rsi+10h], rbx
0x1400080d7  lea     rcx, [rsi+18h]; lpCriticalSection
0x1400080db  xorps   xmm0, xmm0
0x1400080de  xor     eax, eax
0x1400080e0  movups  xmmword ptr [rcx], xmm0
0x1400080e3  movups  xmmword ptr [rcx+10h], xmm0
0x1400080e7  mov     [rcx+20h], rax
0x1400080eb  call    cs:__imp_InitializeCriticalSection
0x1400080f1  nop
0x1400080f2  mov     rcx, [rdi+48h]
0x1400080f6  test    rcx, rcx
0x1400080f9  jz      short loc_140008108
0x1400080fb  mov     rax, [rcx]
0x1400080fe  mov     rax, [rax+10h]
0x140008102  call    cs:__guard_dispatch_icall_fptr
0x140008108  mov     [rdi+48h], rsi
0x14000810c  mov     r14d, 48h ; 'H'
0x140008112  mov     ecx, r14d; Size
0x140008115  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000811a  mov     rsi, rax
0x14000811d  mov     [rsp+0C8h+ppv], rax
0x140008125  mov     r8d, r14d; Size
0x140008128  xor     edx, edx; Val
0x14000812a  mov     rcx, rax; void *
0x14000812d  call    memset_0
0x140008132  mov     rax, [rdi+48h]
0x140008136  test    rax, rax
0x140008139  jz      loc_140008358
0x14000813f  lea     rcx, ??_7CStandardCollectorClassFactory@@6B@; const CStandardCollectorClassFactory::`vftable'
0x140008146  mov     [rsi], rcx
0x140008149  mov     [rsi+8], r13d
0x14000814d  mov     [rsi+10h], rax
0x140008151  lea     rcx, [rsi+20h]; lpCriticalSection
0x140008155  call    cs:__imp_InitializeCriticalSection
0x14000815b  nop
0x14000815c  mov     rcx, [rdi+40h]
0x140008160  test    rcx, rcx
0x140008163  jz      short loc_140008172
0x140008165  mov     rax, [rcx]
0x140008168  mov     rax, [rax+10h]
0x14000816c  call    cs:__guard_dispatch_icall_fptr
0x140008172  mov     [rdi+40h], rsi
0x140008176  cmp     dword ptr [r12], 5
0x14000817b  jnz     loc_140008241
0x140008181  lea     rax, [rdi+24h]
0x140008185  mov     qword ptr [rsp+0C8h+dwAuthnLevel], rax; lpdwRegister
0x14000818a  mov     r9d, 5; flags
0x140008190  lea     r14d, [r9-1]
0x140008194  mov     r8d, r14d; dwClsContext
0x140008197  mov     rdx, rsi; pUnk
0x14000819a  lea     rcx, CLSID_StandardCollectorService; rclsid
0x1400081a1  call    cs:__imp_CoRegisterClassObject
0x1400081a7  test    eax, eax
0x1400081a9  jnz     short loc_1400081BA
0x1400081ab  call    cs:__imp_CoResumeClassObjects
0x1400081b1  test    eax, eax
0x1400081b3  jns     short loc_1400081C5
0x1400081b5  jmp     loc_14000832A
0x1400081ba  cmp     eax, 800401FCh
0x1400081bf  jnz     loc_14000832A
0x1400081c5  lea     rax, [rdi+28h]
0x1400081c9  mov     qword ptr [rsp+0C8h+dwAuthnLevel], rax; lpdwRegister
0x1400081ce  mov     r9d, 5; flags
0x1400081d4  mov     r8d, r14d; dwClsContext
0x1400081d7  mov     rdx, [rdi+48h]; pUnk
0x1400081db  lea     rcx, CLSID_StandardCollectorHost; rclsid
0x1400081e2  call    cs:__imp_CoRegisterClassObject
0x1400081e8  test    eax, eax
0x1400081ea  jnz     short loc_1400081FB
0x1400081ec  call    cs:__imp_CoResumeClassObjects
0x1400081f2  test    eax, eax
0x1400081f4  jns     short loc_140008206
0x1400081f6  jmp     loc_14000832A
0x1400081fb  cmp     eax, 800401FCh
0x140008200  jnz     loc_14000832A
0x140008206  or      dword ptr [rdi+10h], 5
0x14000820a  mov     [rdi+0Ch], r14d
0x14000820e  lea     rdx, [rdi+8]; lpServiceStatus
0x140008212  mov     rcx, [rdi]; hServiceStatus
0x140008215  call    cs:__imp_SetServiceStatus
0x14000821b  test    eax, eax
0x14000821d  jnz     short loc_14000823A
0x14000821f  call    cs:__imp_GetLastError
0x140008225  movzx   ecx, ax
0x140008228  or      ecx, 80070000h
0x14000822e  test    eax, eax
0x140008230  cmovle  ecx, eax
0x140008233  mov     eax, ecx
0x140008235  jmp     loc_14000832A
0x14000823a  xor     eax, eax
0x14000823c  jmp     loc_14000832A
0x140008241  cmp     [r12+28h], bl
0x140008246  jz      loc_1400082CF
0x14000824c  cmp     [rdi+0C0h], rbx
0x140008253  jz      short loc_14000825C
0x140008255  mov     ecx, 0E111002Ch
0x14000825a  jmp     short loc_140008233
0x14000825c  xor     r8d, r8d; pcbe
0x14000825f  xor     edx, edx; pv
0x140008261  lea     rcx, ?MarshallerShutdown@CStandardCollectorService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140008268  call    cs:__imp_CreateThreadpoolTimer
0x14000826e  mov     [rdi+0C0h], rax
0x140008275  test    rax, rax
0x140008278  jnz     short loc_140008292
0x14000827a  call    cs:__imp_GetLastError
0x140008280  movzx   ecx, ax
0x140008283  or      ecx, 80070000h
0x140008289  test    eax, eax
0x14000828b  cmovle  ecx, eax
0x14000828e  test    ecx, ecx
0x140008290  js      short loc_140008233
0x140008292  mov     rcx, [rdi+0C0h]; pti
0x140008299  test    rcx, rcx
0x14000829c  jnz     short loc_1400082A8
0x14000829e  mov     eax, 80070015h
0x1400082a3  jmp     loc_14000832A
0x1400082a8  mov     [rsp+0C8h+ppv], 0FFFFFFFFEE1E5D00h
0x1400082b4  xor     r9d, r9d; msWindowLength
0x1400082b7  xor     r8d, r8d; msPeriod
0x1400082ba  lea     rdx, [rsp+0C8h+ppv]; pftDueTime
0x1400082c2  call    cs:__imp_SetThreadpoolTimer
0x1400082c8  mov     [rsp+0C8h+var_38], ebx
0x1400082cf  lea     rax, [rsp+0C8h+var_38]
0x1400082d7  mov     [rsp+0C8h+ppv], rax
0x1400082df  mov     [rsp+0C8h+ppv+8], rdi
0x1400082e7  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_4bc228a33a7adc1015eb6bff6e85dd8e_@@JAEBVAutoEvent@DiagHubCommon@@PEAX@std@@6B@; const std::_Func_impl_no_alloc<_lambda_4bc228a33a7adc1015eb6bff6e85dd8e_,long,DiagHubCommon::AutoEvent const &,void *>::`vftable'
0x1400082ee  mov     [rsp+0C8h+var_78], rax
0x1400082f3  movups  xmm0, xmmword ptr [rsp+0C8h+ppv]
0x1400082fb  movdqu  [rsp+0C8h+var_70], xmm0
0x140008301  lea     rax, [rsp+0C8h+var_78]
0x140008306  mov     [rsp+0C8h+var_40], rax
0x14000830e  lea     rcx, [rdi+50h]; lpParameter
0x140008312  lea     rdx, [rsp+0C8h+var_78]
0x140008317  call    ?Start@?$HubTask@J$0A@@DiagHubCommon@@QEAAJV?$function@$$A6AJAEBVAutoEvent@DiagHubCommon@@PEAX@Z@std@@PEAX@Z; DiagHubCommon::HubTask<long,0>::Start(std::function<long (DiagHubCommon::AutoEvent const &,void *)>,void *)
0x14000831c  test    eax, eax
0x14000831e  cmovs   ebx, eax
0x140008321  mov     eax, ebx
0x140008323  jmp     short loc_14000832A
0x140008325  mov     eax, 8007000Eh
0x14000832a  mov     rcx, [rsp+0C8h+var_20]
0x140008332  xor     rcx, rsp; StackCookie
0x140008335  call    __security_check_cookie
0x14000833a  lea     r11, [rsp+0C8h+var_18]
0x140008342  mov     rbx, [r11+28h]
0x140008346  mov     rsi, [r11+30h]
0x14000834a  mov     rdi, [r11+38h]
0x14000834e  mov     rsp, r11
0x140008351  pop     r14
0x140008353  pop     r13
0x140008355  pop     r12
0x140008357  retn
0x140008358  mov     ecx, 80004005h; int
0x14000835d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
