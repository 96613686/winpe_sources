# CTitleBar::SetWindowTitle(ushort const *)

- ea: `0x18003d6f0`
- end: `0x18003da1b`
- name: `?SetWindowTitle@CTitleBar@@UEAAJPEBG@Z`
- size: `811`
- prototype: `int(CTitleBar *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800116c0`
- `0x180024184`
- `0x1800294d4`
- `0x18003d6f0`
- `0x18003fbc0`
- `0x180043c30`
- `0x1800440b0`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003d835`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003d835`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003d73b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003d73b`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18003d806`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18003d806`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18003d7eb`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18003d7eb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003d924`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003d924`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowTextW` at `0x18003d96a`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowTextW` at `0x18003d96a`

## pseudocode

```c
__int64 __fastcall CTitleBar::SetWindowTitle(CTitleBar *this, WCHAR *a2)
{
  _QWORD *v4; // rdi
  ULONGLONG *v5; // r9
  __int64 v6; // rcx
  const WCHAR *v7; // rdx
  __int64 v8; // rax
  int v10; // eax
  char *v11; // rax
  char *v12; // r8
  int v13; // ecx
  int v14; // edx
  const char *v15; // r9
  int updated; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  ULONG UserDataCount; // [rsp+20h] [rbp-49h]
  WINBOOL fPending; // [rsp+30h] [rbp-39h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-31h] BYREF
  GUID ProviderId; // [rsp+40h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-19h] BYREF
  char *v25; // [rsp+60h] [rbp-9h]
  int v26; // [rsp+68h] [rbp-1h]
  int v27; // [rsp+6Ch] [rbp+3h]
  WINBOOL *p_fPending; // [rsp+70h] [rbp+7h]
  __int64 v29; // [rsp+78h] [rbp+Fh]
  const WCHAR *v30; // [rsp+80h] [rbp+17h]
  int v31; // [rsp+88h] [rbp+1Fh]
  int v32; // [rsp+8Ch] [rbp+23h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`CApplicationFrameLogging::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_180091D30 = 0;
    Context = &qword_180091D28;
    byte_180091D38 = 0;
    dword_180091D3C = 0;
    qword_180091D28 = (__int64)&wil::details::FeatureLogging::`vftable';
    CallbackContext = &`CApplicationFrameLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8adcf3751b4402ee818619e8ba416ee6_::_lambda_invoker_cdecl_);
    v4 = CallbackContext;
    qword_180091D30 = (__int64)CallbackContext;
    byte_180091D38 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v5 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v4[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v4, v5) )
      EventSetInformation(v4[4], 2, v4[1], *(unsigned __int16 *)v4[1]);
    dword_180091D3C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180091D28 + 8))(&qword_180091D28);
    InitOnceComplete(&`CApplicationFrameLogging::Instance'::`2'::wrapper, 0, &qword_180091D28);
  }
  v6 = *((_QWORD *)Context + 1);
  if ( *(_DWORD *)v6 > 5u )
  {
    fPending = *((_DWORD *)this + 112);
    if ( a2 )
    {
      v7 = a2;
      v8 = -1;
      while ( a2[++v8] != 0 )
        ;
      v10 = 2 * v8 + 2;
    }
    else
    {
      v7 = &pszDefault;
      v10 = 2;
    }
    v31 = v10;
    v30 = v7;
    p_fPending = &fPending;
    *(_DWORD *)&ProviderId.Data2 = 5;
    UserData.Ptr = *(_QWORD *)(v6 + 8);
    v32 = 0;
    v29 = 4;
    ProviderId.Data1 = 184549376;
    *(_QWORD *)ProviderId.Data4 = 0;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v25 = &byte_180081DA7;
    UserData.Reserved = 2;
    v26 = 60;
    v27 = 1;
    LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v6 + 32), (PCEVENT_DESCRIPTOR)&ProviderId, 0, 0, 4u, &UserData);
  }
  v11 = (char *)*((_QWORD *)this + 50);
  if ( !v11 )
    goto LABEL_32;
  v12 = (char *)((char *)a2 - v11);
  do
  {
    v13 = *(unsigned __int16 *)&v12[(_QWORD)v11];
    v14 = *(unsigned __int16 *)v11 - v13;
    if ( v14 )
      break;
    v11 += 2;
  }
  while ( v13 );
  if ( v14 )
  {
LABEL_32:
    if ( !SetWindowTextW(*((HWND *)this + 56), a2) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x1382,
               (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
               v15);
    if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                (__int64)this + 400,
                a2,
                0xFFFFFFFFFFFFFFFFuLL) >= 0 )
    {
      updated = CTitleBar::_UpdateButtonStateAndCommit((char *)this - 56, 3);
      if ( updated < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1386,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
          (const char *)(unsigned int)updated,
          UserDataCount);
    }
    v18 = *((_QWORD *)this + 43);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 64LL))(v18);
    v19 = *((_QWORD *)this + 42);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 64LL))(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x18003d6f0  push    rbp
0x18003d6f2  push    rbx
0x18003d6f3  push    rsi
0x18003d6f4  push    rdi
0x18003d6f5  push    r14
0x18003d6f7  lea     rbp, [rsp-37h]
0x18003d6fc  sub     rsp, 0A0h
0x18003d703  mov     rax, cs:__security_cookie
0x18003d70a  xor     rax, rsp
0x18003d70d  mov     [rbp+57h+var_30], rax
0x18003d711  mov     rbx, rdx
0x18003d714  mov     [rsp+0C0h+arg_18], r15
0x18003d71c  xor     r15d, r15d
0x18003d71f  lea     r9, [rbp+57h+Context]; lpContext
0x18003d723  mov     rsi, rcx
0x18003d726  mov     [rbp+57h+Context], r15
0x18003d72a  lea     r8, [rbp+57h+fPending]; fPending
0x18003d72e  mov     [rbp+57h+fPending], r15d
0x18003d732  xor     edx, edx; dwFlags
0x18003d734  lea     rcx, ?wrapper@?1??Instance@CApplicationFrameLogging@@KAPEAV2@XZ@4V?$static_lazy@VCApplicationFrameLogging@@@details@wil@@A; lpInitOnce
0x18003d73b  call    cs:__imp_InitOnceBeginInitialize
0x18003d741  test    eax, eax
0x18003d743  jz      loc_18003D843
0x18003d749  cmp     [rbp+57h+fPending], r15d
0x18003d74d  jz      loc_18003D843
0x18003d753  mov     [rsp+0C0h+arg_10], r12
0x18003d75b  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18003d762  lea     r12, qword_180091D28
0x18003d769  mov     cs:qword_180091D30, r15
0x18003d770  mov     [rbp+57h+Context], r12
0x18003d774  mov     cs:byte_180091D38, r15b
0x18003d77b  mov     cs:dword_180091D3C, r15d
0x18003d782  mov     cs:qword_180091D28, rax
0x18003d789  lea     rax, ?__hInner@?1???0StaticHandle@CApplicationFrameLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `CApplicationFrameLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18003d790  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8adcf3751b4402ee818619e8ba416ee6_@@CA@XZ; void (__cdecl *)()
0x18003d797  mov     cs:CallbackContext, rax
0x18003d79e  call    atexit
0x18003d7a3  mov     rdi, cs:CallbackContext
0x18003d7aa  mov     cs:qword_180091D30, rdi
0x18003d7b1  mov     cs:byte_180091D38, 1
0x18003d7b8  mov     rax, [rdi+8]
0x18003d7bc  movups  xmm0, xmmword ptr [rax-10h]
0x18003d7c0  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x18003d7c4  cmp     [rdi+20h], r15
0x18003d7c8  jz      short loc_18003D7D1
0x18003d7ca  mov     ecx, 5
0x18003d7cf  int     29h; Win8: RtlFailFast(ecx)
0x18003d7d1  lea     r9, [rdi+20h]; RegHandle
0x18003d7d5  mov     [rdi+28h], r15
0x18003d7d9  mov     r8, rdi; CallbackContext
0x18003d7dc  mov     [rdi+30h], r15
0x18003d7e0  lea     rdx, _tlgEnableCallback; EnableCallback
0x18003d7e7  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x18003d7eb  call    cs:__imp_EventRegister
0x18003d7f1  test    eax, eax
0x18003d7f3  jnz     short loc_18003D80C
0x18003d7f5  mov     r8, [rdi+8]
0x18003d7f9  mov     edx, 2
0x18003d7fe  mov     rcx, [rdi+20h]
0x18003d802  movzx   r9d, word ptr [r8]
0x18003d806  call    cs:__imp_EventSetInformation
0x18003d80c  mov     rax, cs:qword_180091D28
0x18003d813  mov     rcx, r12
0x18003d816  mov     cs:dword_180091D3C, 1
0x18003d820  mov     rax, [rax+8]
0x18003d824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d829  mov     r8, r12; lpContext
0x18003d82c  lea     rcx, ?wrapper@?1??Instance@CApplicationFrameLogging@@KAPEAV2@XZ@4V?$static_lazy@VCApplicationFrameLogging@@@details@wil@@A; lpInitOnce
0x18003d833  xor     edx, edx; dwFlags
0x18003d835  call    cs:__imp_InitOnceComplete
0x18003d83b  mov     r12, [rsp+0C0h+arg_10]
0x18003d843  mov     rax, [rbp+57h+Context]
0x18003d847  mov     rcx, [rax+8]
0x18003d84b  mov     eax, [rcx]
0x18003d84d  cmp     eax, 5
0x18003d850  jbe     loc_18003D92A
0x18003d856  mov     eax, [rsi+1C0h]
0x18003d85c  mov     [rbp+57h+fPending], eax
0x18003d85f  test    rbx, rbx
0x18003d862  jz      short loc_18003D885
0x18003d864  mov     rdx, rbx
0x18003d867  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18003d86e  xchg    ax, ax
0x18003d870  cmp     [rbx+rax*2+2], r15w
0x18003d876  lea     rax, [rax+1]
0x18003d87a  jnz     short loc_18003D870
0x18003d87c  lea     eax, ds:2[rax*2]
0x18003d883  jmp     short loc_18003D891
0x18003d885  lea     rdx, pszDefault
0x18003d88c  mov     eax, 2
0x18003d891  mov     [rbp+57h+var_38], eax
0x18003d894  xor     r9d, r9d; RelatedActivityId
0x18003d897  mov     [rbp+57h+var_40], rdx
0x18003d89b  lea     rax, [rbp+57h+fPending]
0x18003d89f  mov     [rbp+57h+var_50], rax
0x18003d8a3  lea     rdx, _TraceLoggingMetadata
0x18003d8aa  movzx   eax, cs:word_180081D9D
0x18003d8b1  xor     r8d, r8d; ActivityId
0x18003d8b4  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x18003d8b7  mov     rax, [rcx+8]
0x18003d8bb  mov     [rbp+57h+var_70.Ptr], rax
0x18003d8bf  mov     [rbp+57h+var_34], r15d
0x18003d8c3  mov     [rbp+57h+var_48], 4
0x18003d8cb  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x18003d8d2  mov     qword ptr [rbp+57h+ProviderId.Data4], r15
0x18003d8d6  movzx   eax, word ptr [rax]
0x18003d8d9  mov     [rbp+57h+var_70.Size], eax
0x18003d8dc  lea     rax, byte_180081DA7
0x18003d8e3  mov     [rbp+57h+var_60], rax
0x18003d8e7  lea     rax, _TraceLoggingMetadataEnd
0x18003d8ee  sub     eax, edx
0x18003d8f0  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x18003d8f7  mov     [rbp+57h+var_58], 3Ch ; '<'
0x18003d8fe  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x18003d902  mov     [rbp+57h+var_54], 1
0x18003d909  mov     dword ptr [rbp+57h+Context], eax
0x18003d90c  mov     eax, dword ptr [rbp+57h+Context]
0x18003d90f  mov     rcx, [rcx+20h]; RegHandle
0x18003d913  lea     rax, [rbp+57h+var_70]
0x18003d917  mov     [rsp+0C0h+UserData], rax; UserData
0x18003d91c  mov     [rsp+0C0h+UserDataCount], 4; int
0x18003d924  call    cs:__imp_EventWriteTransfer
0x18003d92a  mov     rax, [rsi+190h]
0x18003d931  mov     r15, [rsp+0C0h+arg_18]
0x18003d939  test    rax, rax
0x18003d93c  jz      short loc_18003D960
0x18003d93e  mov     r8, rbx
0x18003d941  sub     r8, rax
0x18003d944  movzx   edx, word ptr [rax]
0x18003d947  movzx   ecx, word ptr [rax+r8]
0x18003d94c  sub     edx, ecx
0x18003d94e  jnz     short loc_18003D958
0x18003d950  add     rax, 2
0x18003d954  test    ecx, ecx
0x18003d956  jnz     short loc_18003D944
0x18003d958  test    edx, edx
0x18003d95a  jz      loc_18003D9FF
0x18003d960  mov     rcx, [rsi+1C0h]; hWnd
0x18003d967  mov     rdx, rbx; lpString
0x18003d96a  call    cs:__imp_SetWindowTextW
0x18003d970  test    eax, eax
0x18003d972  jnz     short loc_18003D98B
0x18003d974  mov     rcx, [rbp+5Fh]; this
0x18003d978  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x18003d97f  mov     edx, 1382h; void *
0x18003d984  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d989  jmp     short loc_18003DA01
0x18003d98b  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18003d992  lea     rcx, [rsi+190h]
0x18003d999  mov     rdx, rbx
0x18003d99c  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003d9a1  test    eax, eax
0x18003d9a3  js      short loc_18003D9CF
0x18003d9a5  mov     edx, 3
0x18003d9aa  lea     rcx, [rsi-38h]
0x18003d9ae  call    ?_UpdateButtonStateAndCommit@CTitleBar@@AEAAJW4TitleBarControl@1@_N@Z; CTitleBar::_UpdateButtonStateAndCommit(CTitleBar::TitleBarControl,bool)
0x18003d9b3  test    eax, eax
0x18003d9b5  jns     short loc_18003D9CF
0x18003d9b7  mov     rcx, [rbp+5Fh]; this
0x18003d9bb  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x18003d9c2  mov     r9d, eax; char *
0x18003d9c5  mov     edx, 1386h; void *
0x18003d9ca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d9cf  mov     rcx, [rsi+158h]
0x18003d9d6  test    rcx, rcx
0x18003d9d9  jz      short loc_18003D9E7
0x18003d9db  mov     rax, [rcx]
0x18003d9de  mov     rax, [rax+40h]
0x18003d9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9e7  mov     rcx, [rsi+150h]
0x18003d9ee  test    rcx, rcx
0x18003d9f1  jz      short loc_18003D9FF
0x18003d9f3  mov     rax, [rcx]
0x18003d9f6  mov     rax, [rax+40h]
0x18003d9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9ff  xor     eax, eax
0x18003da01  mov     rcx, [rbp+57h+var_30]
0x18003da05  xor     rcx, rsp; StackCookie
0x18003da08  call    __security_check_cookie
0x18003da0d  add     rsp, 0A0h
0x18003da14  pop     r14
0x18003da16  pop     rdi
0x18003da17  pop     rsi
0x18003da18  pop     rbx
0x18003da19  pop     rbp
0x18003da1a  retn
```
