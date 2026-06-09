# ConnectionManagerPtr::RefreshConnectionManager(ConnectionRundownState)

- ea: `0x18003cdcc`
- end: `0x18003cf5e`
- name: `?RefreshConnectionManager@ConnectionManagerPtr@@QEAAXW4ConnectionRundownState@@@Z`
- size: `402`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d854`
- `0x1800a0790`
- `0x1800e7da0`

## callees

- `0x180004e38`
- `0x18000e5f4`
- `0x18003bb48`
- `0x18003cdcc`
- `0x18003cf64`
- `0x18003d000`
- `0x18004c9e4`
- `0x18004ca20`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003cf20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003cf20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cea7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cea7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cec1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cec1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ce44`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ce44`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall ConnectionManagerPtr::RefreshConnectionManager(__int64 a1, int a2)
{
  __int64 v2; // rbx
  unsigned int v3; // esi
  HRESULT v4; // eax
  int v5; // eax
  DWORD CurrentThreadId; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  unsigned __int64 v11; // rdx
  wil *v12; // rcx
  char result; // al
  __int64 v14; // rcx
  __int64 v15; // rax
  int ppv; // [rsp+20h] [rbp-38h]
  _QWORD v17[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v20; // [rsp+68h] [rbp+10h] BYREF
  LPVOID v21; // [rsp+70h] [rbp+18h] BYREF

  v20 = a2;
  try
  {
    v2 = a1;
    v3 = 0;
    if ( ((a2 - 1) & 0xFFFFFFFD) != 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanager.cpp",
        (const char *)0x80070057LL,
        ppv);
    if ( a2 == 1 )
    {
      v21 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      v4 = CoCreateInstance(
             &GUID_7a6d9c0a_1e7a_41b6_82b4_c3f7a27ba381,
             0,
             4u,
             &GUID_e95e00fe_57b1_48c2_b372_5de8179efd7e,
             &v21);
      if ( v4 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanager.cpp",
          (const char *)(unsigned int)v4,
          ppv);
      v5 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 48LL))(v21);
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x64,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanager.cpp",
          (const char *)(unsigned int)v5,
          ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    }
    AcquireSRWLockExclusive((PSRWLOCK)(v2 + 16));
    v21 = (LPVOID)(v2 + 16);
    v17[0] = v2;
    v17[1] = &v20;
    CurrentThreadId = GetCurrentThreadId();
    v9 = Windows::Internal::ComTaskPool::QueueTask__lambda_76096f6a337891646ff39e8fc9bd98e1___(
           v8,
           v7,
           CurrentThreadId,
           v17);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanager.cpp",
        (const char *)(unsigned int)v9,
        ppv);
    v10 = NotificationPlatform::Connect(*(NotificationPlatform **)(v2 + 8));
    v12 = retaddr;
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanager.cpp",
        (const char *)(unsigned int)v10,
        ppv);
    if ( v2 != -16 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v2 + 16));
  }
  catch ( ... )
  {
    LODWORD(v21) = wil::ResultFromCaughtException(v12);
    v2 = a1;
    v3 = (unsigned int)v21;
  }
  result = WpncoreTelemetry::IsEnabled((unsigned __int8)v12, v11);
  if ( result )
  {
    v15 = wil::details::static_lazy<WpncoreTelemetry>::get(
            v14,
            _lambda_c91d295e9756ec26c89460bbd269b90b_::_lambda_invoker_cdecl_);
    return WpncoreTelemetry::RefreshConnectionManager_(v15, v3, *(unsigned int *)(v2 + 40));
  }
  return result;
}

```

## disassembly

```asm
0x18003cdcc  mov     [rsp+arg_8], edx
0x18003cdd0  mov     [rsp+arg_0], rcx
0x18003cdd5  push    rbx
0x18003cdd6  push    rsi
0x18003cdd7  push    rdi
0x18003cdd8  sub     rsp, 40h
0x18003cddc  mov     rbx, rcx
0x18003cddf  xor     esi, esi
0x18003cde1  lea     eax, [rdx-1]
0x18003cde4  test    eax, 0FFFFFFFDh
0x18003cde9  setnz   al
0x18003cdec  mov     rcx, [rsp+58h]; this
0x18003cdf1  test    al, al
0x18003cdf3  jz      short loc_18003CE0A
0x18003cdf5  mov     r9d, 80070057h; char *
0x18003cdfb  lea     r8, aOnecoreuapBase_124; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003ce02  lea     edx, [rsi+5Bh]; void *
0x18003ce05  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003ce0a  cmp     edx, 1
0x18003ce0d  jnz     loc_18003CEA0
0x18003ce13  mov     [rsp+58h+arg_10], 0
0x18003ce1c  lea     rcx, [rsp+58h+arg_10]
0x18003ce21  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ce26  lea     rax, [rsp+58h+arg_10]
0x18003ce2b  mov     qword ptr [rsp+58h+ppv], rax; int
0x18003ce30  lea     r9, _GUID_e95e00fe_57b1_48c2_b372_5de8179efd7e; riid
0x18003ce37  xor     edx, edx; pUnkOuter
0x18003ce39  lea     r8d, [rdx+4]; dwClsContext
0x18003ce3d  lea     rcx, _GUID_7a6d9c0a_1e7a_41b6_82b4_c3f7a27ba381; rclsid
0x18003ce44  call    cs:__imp_CoCreateInstance
0x18003ce4a  mov     rcx, [rsp+58h]; this
0x18003ce4f  test    eax, eax
0x18003ce51  jns     short loc_18003CE67
0x18003ce53  mov     r9d, eax; char *
0x18003ce56  lea     r8, aOnecoreuapBase_124; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003ce5d  mov     edx, 63h ; 'c'; void *
0x18003ce62  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003ce67  mov     rcx, [rsp+58h+arg_10]
0x18003ce6c  mov     rax, [rcx]
0x18003ce6f  mov     rax, [rax+30h]
0x18003ce73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce78  mov     rcx, [rsp+58h]; this
0x18003ce7d  test    eax, eax
0x18003ce7f  jns     short loc_18003CE96
0x18003ce81  mov     r9d, eax; char *
0x18003ce84  lea     r8, aOnecoreuapBase_124; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003ce8b  mov     edx, 64h ; 'd'; void *
0x18003ce90  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003ce96  lea     rcx, [rsp+58h+arg_10]
0x18003ce9b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003cea0  lea     rdi, [rbx+10h]
0x18003cea4  mov     rcx, rdi; SRWLock
0x18003cea7  call    cs:__imp_AcquireSRWLockExclusive
0x18003cead  mov     [rsp+58h+arg_10], rdi
0x18003ceb2  mov     [rsp+58h+var_28], rbx
0x18003ceb7  lea     rax, [rsp+58h+arg_8]
0x18003cebc  mov     [rsp+58h+var_20], rax
0x18003cec1  call    cs:__imp_GetCurrentThreadId
0x18003cec7  lea     r9, [rsp+58h+var_28]
0x18003cecc  mov     r8d, eax
0x18003cecf  call    Windows__Internal__ComTaskPool__QueueTask__lambda_76096f6a337891646ff39e8fc9bd98e1___
0x18003ced4  mov     rcx, [rsp+58h]; this
0x18003ced9  test    eax, eax
0x18003cedb  jns     short loc_18003CEF1
0x18003cedd  mov     r9d, eax; char *
0x18003cee0  lea     r8, aOnecoreuapBase_124; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003cee7  mov     edx, 7Ah ; 'z'; void *
0x18003ceec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003cef1  mov     rcx, [rbx+8]; this
0x18003cef5  call    ?Connect@NotificationPlatform@@QEAAJXZ; NotificationPlatform::Connect(void)
0x18003cefa  mov     rcx, [rsp+58h]; this
0x18003ceff  test    eax, eax
0x18003cf01  jns     short loc_18003CF18
0x18003cf03  mov     r9d, eax; char *
0x18003cf06  lea     r8, aOnecoreuapBase_124; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003cf0d  mov     edx, 7Ch ; '|'; void *
0x18003cf12  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003cf18  test    rdi, rdi
0x18003cf1b  jz      short loc_18003CF27
0x18003cf1d  mov     rcx, rdi; SRWLock
0x18003cf20  call    cs:__imp_ReleaseSRWLockExclusive
0x18003cf26  nop
0x18003cf27  jmp     short loc_18003CF32
0x18003cf29  mov     rbx, [rsp+58h+arg_0]
0x18003cf2e  mov     esi, dword ptr [rsp+58h+arg_10]
0x18003cf32  call    ?IsEnabled@WpncoreTelemetry@@SA_NE_K@Z; WpncoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x18003cf37  test    al, al
0x18003cf39  jz      short loc_18003CF56
0x18003cf3b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c91d295e9756ec26c89460bbd269b90b_@@CA@XZ; _lambda_c91d295e9756ec26c89460bbd269b90b_::_lambda_invoker_cdecl_(void)
0x18003cf42  call    ?get@?$static_lazy@VWpncoreTelemetry@@@details@wil@@QEAAPEAVWpncoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<WpncoreTelemetry>::get(void (*)(void))
0x18003cf47  mov     r8d, [rbx+28h]
0x18003cf4b  mov     edx, esi
0x18003cf4d  mov     rcx, rax
0x18003cf50  call    ?RefreshConnectionManager_@WpncoreTelemetry@@QEAAXJW4ConnectionRundownState@@@Z; WpncoreTelemetry::RefreshConnectionManager_(long,ConnectionRundownState)
0x18003cf55  nop
0x18003cf56  add     rsp, 40h
0x18003cf5a  pop     rdi
0x18003cf5b  pop     rsi
0x18003cf5c  pop     rbx
0x18003cf5d  retn
```
