# Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_63f70fd3a6236e7362d86e89a2498b35_,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_63f70fd3a6236e7362d86e89a2498b35_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)

- ea: `0x180018cd0`
- end: `0x180018e3d`
- name: `??$InvokeDelegates@V_lambda_63f70fd3a6236e7362d86e89a2498b35_@@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextNonComponentUIHostDetectedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_63f70fd3a6236e7362d86e89a2498b35_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextNonComponentUIHostDetectedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z`
- size: `365`
- prototype: ``
- caller_count: `30`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001dea0`
- `0x18001e090`
- `0x18001e2c0`
- `0x18001e500`
- `0x18001e750`
- `0x18001e940`
- `0x18001eb30`
- `0x18001ed20`
- `0x18001ef30`
- `0x18001f120`
- `0x18001f370`
- `0x18001f570`
- `0x18001f780`
- `0x18001f9b0`
- `0x18001fba0`
- `0x18001fdb0`
- `0x18001ffe0`
- `0x180020220`
- `0x180020460`
- `0x180020660`
- `0x180020850`
- `0x180020a80`
- `0x180020c80`
- `0x180020e90`
- `0x180021070`
- `0x180021250`
- `0x180021470`
- `0x1800216c0`
- `0x180021900`
- `0x180021ae0`

## callees

- `0x180018cd0`
- `0x180024b70`
- `0x180024d98`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180018d85`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180018d94`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180018d85`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180018d94`
- `api-ms-win-core-winrt-error-l1-1-1!RoGetMatchingRestrictedErrorInfo` at `0x180018dd2`
- `api-ms-win-core-winrt-error-l1-1-1!RoGetMatchingRestrictedErrorInfo` at `0x180018dd2`
- `api-ms-win-core-winrt-error-l1-1-1!RoReportFailedDelegate` at `0x180018de6`
- `api-ms-win-core-winrt-error-l1-1-1!RoReportFailedDelegate` at `0x180018de6`
- `api-ms-win-core-winrt-error-l1-1-1!IsErrorPropagationEnabled` at `0x180018d74`
- `api-ms-win-core-winrt-error-l1-1-1!IsErrorPropagationEnabled` at `0x180018d74`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_63f70fd3a6236e7362d86e89a2498b35_,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
        _QWORD *a1,
        __int64 a2,
        RTL_SRWLOCK *a3)
{
  unsigned int v4; // edi
  _QWORD *v5; // rbx
  signed __int32 v6; // eax
  struct IUnknown **v7; // rsi
  __int64 v8; // r14
  _QWORD *v9; // r15
  _QWORD *v10; // rbp
  int v11; // eax
  int MatchingRestrictedErrorInfo; // ecx
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v16; // [rsp+68h] [rbp+10h] BYREF
  __int64 v17; // [rsp+78h] [rbp+20h]

  v4 = 0;
  v5 = 0;
  v17 = 0;
  if ( a2 )
  {
    do
      v6 = *(_DWORD *)(a2 + 12);
    while ( v6 != 0x7FFFFFFF && v6 != _InterlockedCompareExchange((volatile signed __int32 *)(a2 + 12), v6 + 1, v6) );
    v5 = (_QWORD *)a2;
    v17 = a2;
  }
  v7 = (struct IUnknown **)v5[2];
  if ( v7 != (struct IUnknown **)v5[3] )
  {
    v8 = v5[4];
    v9 = (_QWORD *)a1[1];
    v10 = (_QWORD *)*a1;
    while ( 1 )
    {
      v11 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD))(*v7)->lpVtbl[1].QueryInterface)(*v7, *v10, *v9);
      v4 = v11;
      if ( v11 == -2147417848 || v11 == -2147023174 || v11 == -1996357631 || v11 == -2147418105 || v11 == -2147418094 )
      {
        RoTransformError((unsigned int)v11, 0, 0);
        Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextHostOperationAcknowledgedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
          a3,
          *v7);
      }
      else
      {
        if ( v11 >= 0 )
          goto LABEL_18;
        if ( (unsigned int)IsErrorPropagationEnabled() )
        {
          v16 = 0;
          MatchingRestrictedErrorInfo = RoGetMatchingRestrictedErrorInfo(v4, &v16);
          if ( MatchingRestrictedErrorInfo >= 0 )
            MatchingRestrictedErrorInfo = RoReportFailedDelegate(*v7, v16);
          v13 = 0;
          if ( MatchingRestrictedErrorInfo < 0 )
            v13 = v4;
          v4 = v13;
          v14 = v16;
          if ( v16 )
          {
            v16 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          }
          break;
        }
        RoTransformError(v4, 0, 0);
      }
      v4 = 0;
LABEL_18:
      if ( ++v7 == (struct IUnknown **)v5[3] )
        break;
      v8 += 8;
    }
  }
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v5);
  return v4;
}

```

## disassembly

```asm
0x180018cd0  mov     [rsp+arg_0], rbx
0x180018cd5  mov     [rsp+arg_10], rbp
0x180018cda  push    rsi
0x180018cdb  push    rdi
0x180018cdc  push    r12
0x180018cde  push    r14
0x180018ce0  push    r15
0x180018ce2  sub     rsp, 30h
0x180018ce6  mov     r12, r8
0x180018ce9  mov     r9, rcx
0x180018cec  xor     edi, edi
0x180018cee  xor     ebx, ebx
0x180018cf0  mov     [rsp+58h+arg_18], rbx
0x180018cf5  test    rdx, rdx
0x180018cf8  jz      short loc_180018D1C
0x180018cfa  mov     r8d, 7FFFFFFFh
0x180018d00  jmp     short loc_180018D0C
0x180018d02  lea     ecx, [rax+1]
0x180018d05  lock cmpxchg [rdx+0Ch], ecx
0x180018d0a  jz      short loc_180018D14
0x180018d0c  mov     eax, [rdx+0Ch]
0x180018d0f  cmp     eax, r8d
0x180018d12  jnz     short loc_180018D02
0x180018d14  mov     rbx, rdx
0x180018d17  mov     [rsp+58h+arg_18], rdx
0x180018d1c  mov     rsi, [rbx+10h]
0x180018d20  cmp     rsi, [rbx+18h]
0x180018d24  jz      loc_180018E1C
0x180018d2a  mov     r14, [rbx+20h]
0x180018d2e  mov     r15, [r9+8]
0x180018d32  mov     rbp, [r9]
0x180018d35  mov     rcx, [rsi]
0x180018d38  mov     rax, [rcx]
0x180018d3b  mov     r8, [r15]
0x180018d3e  mov     rdx, [rbp+0]
0x180018d42  mov     rax, [rax+18h]
0x180018d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d4b  mov     edi, eax
0x180018d4d  cmp     eax, 80010108h
0x180018d52  jz      short loc_180018D8D
0x180018d54  cmp     eax, 800706BAh
0x180018d59  jz      short loc_180018D8D
0x180018d5b  cmp     eax, 89020001h
0x180018d60  jz      short loc_180018D8D
0x180018d62  cmp     eax, 80010007h
0x180018d67  jz      short loc_180018D8D
0x180018d69  cmp     eax, 80010012h
0x180018d6e  jz      short loc_180018D8D
0x180018d70  test    eax, eax
0x180018d72  jns     short loc_180018DA7
0x180018d74  call    cs:__imp_IsErrorPropagationEnabled
0x180018d7a  test    eax, eax
0x180018d7c  jnz     short loc_180018DBA
0x180018d7e  xor     r8d, r8d
0x180018d81  xor     edx, edx
0x180018d83  mov     ecx, edi
0x180018d85  call    cs:__imp_RoTransformError
0x180018d8b  jmp     short loc_180018DA5
0x180018d8d  xor     r8d, r8d
0x180018d90  xor     edx, edx
0x180018d92  mov     ecx, edi
0x180018d94  call    cs:__imp_RoTransformError
0x180018d9a  mov     rdx, [rsi]
0x180018d9d  mov     rcx, r12
0x180018da0  call    ?Remove@?$EventSource@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextHostOperationAcknowledgedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextHostOperationAcknowledgedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)
0x180018da5  xor     edi, edi
0x180018da7  add     rsi, 8
0x180018dab  cmp     rsi, [rbx+18h]
0x180018daf  jz      short loc_180018E1C
0x180018db1  add     r14, 8
0x180018db5  jmp     loc_180018D35
0x180018dba  mov     rax, [r14]
0x180018dbd  mov     [rsp+58h+var_38], rax
0x180018dc2  mov     [rsp+58h+arg_8], 0
0x180018dcb  lea     rdx, [rsp+58h+arg_8]
0x180018dd0  mov     ecx, edi
0x180018dd2  call    cs:__imp_RoGetMatchingRestrictedErrorInfo
0x180018dd8  mov     ecx, eax
0x180018dda  test    eax, eax
0x180018ddc  js      short loc_180018DEE
0x180018dde  mov     rdx, [rsp+58h+arg_8]
0x180018de3  mov     rcx, [rsi]
0x180018de6  call    cs:__imp_RoReportFailedDelegate
0x180018dec  mov     ecx, eax
0x180018dee  xor     eax, eax
0x180018df0  test    ecx, ecx
0x180018df2  cmovs   eax, edi
0x180018df5  mov     edi, eax
0x180018df7  mov     rax, [rsp+58h+var_38]
0x180018dfc  mov     rcx, [rsp+58h+arg_8]
0x180018e01  test    rcx, rcx
0x180018e04  jz      short loc_180018E1C
0x180018e06  mov     [rsp+58h+arg_8], 0
0x180018e0f  mov     rdx, [rcx]
0x180018e12  mov     rax, [rdx+10h]
0x180018e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e1b  nop
0x180018e1c  mov     rcx, rbx
0x180018e1f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180018e24  mov     eax, edi
0x180018e26  mov     rbx, [rsp+58h+arg_0]
0x180018e2b  mov     rbp, [rsp+58h+arg_10]
0x180018e30  add     rsp, 30h
0x180018e34  pop     r15
0x180018e36  pop     r14
0x180018e38  pop     r12
0x180018e3a  pop     rdi
0x180018e3b  pop     rsi
0x180018e3c  retn
```
