# CAudioRenderClient::GetBuffer(uint,uchar * *)

- ea: `0x18002f940`
- end: `0x18002fc6b`
- name: `?GetBuffer@CAudioRenderClient@@UEAAJIPEAPEAE@Z`
- size: `811`
- prototype: `int(CAudioRenderClient *__hidden this, unsigned int, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18002f940`
- `0x18002fc80`
- `0x18002fcb0`
- `0x18002ff28`
- `0x18006a310`
- `0x180087e80`
- `0x180088ce8`
- `0x18008f6dc`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002f9bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002fabc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002f9bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002fabc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002f9d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002f9d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fa2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fa2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fa9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fa9f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002f99b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002f99b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002fa13`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002faae`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002fa13`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002faae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002fbfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002fbfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fc15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fc15`

## pseudocode

```c
__int64 __fastcall CAudioRenderClient::GetBuffer(CAudioRenderClient *this, unsigned int a2, unsigned __int8 **a3)
{
  CAudioRenderClient *v3; // r15
  RTL_SRWLOCK *v4; // rbx
  __int64 v5; // rax
  RTL_SRWLOCK *v9; // rbx
  char *v10; // rsi
  GUID *v11; // rcx
  unsigned __int8 *v12; // r14
  int v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // edi
  __int64 v16; // rcx
  int v18; // eax
  RTL_SRWLOCK *v19; // rax
  __int64 v20; // rax
  size_t *v21; // r15
  size_t v22; // r14
  LPVOID v23; // rax
  void *v24; // rcx
  void *v25; // rcx
  int v26; // [rsp+40h] [rbp-29h] BYREF
  PSRWLOCK v27; // [rsp+48h] [rbp-21h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-19h] BYREF
  void *v29; // [rsp+58h] [rbp-11h]
  __int128 v30; // [rsp+60h] [rbp-9h]
  GUID ActivityId; // [rsp+70h] [rbp+7h] BYREF

  v3 = (CAudioRenderClient *)((char *)this - 16);
  v4 = 0;
  v5 = *((_QWORD *)this + 14);
  v27 = 0;
  v29 = (char *)this - 16;
  if ( *(_DWORD *)(v5 + 836) == 2 )
  {
    v9 = (RTL_SRWLOCK *)(v5 + 864);
    AcquireSRWLockShared((PSRWLOCK)(v5 + 864));
    SRWLock = v9;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(
      &v27,
      &SRWLock);
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    v10 = (char *)this + 112;
    WaitForSingleObjectEx(*(HANDLE *)(*((_QWORD *)this + 14) + 872LL), 0xFFFFFFFF, 0);
    v4 = v27;
  }
  else
  {
    v10 = (char *)this + 112;
  }
  v11 = *(GUID **)v10;
  v30 = *(_OWORD *)(*(_QWORD *)v10 + 528LL);
  ActivityId = v11[33];
  EventActivityIdControl(4u, &ActivityId);
  v26 = 0;
  SRWLock = (PSRWLOCK)((char *)this + 56);
  v12 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( a3 )
    *a3 = 0;
  v13 = CAudioRenderClient::CheckForDisconnection(v3);
  v14 = (unsigned int)v13;
  if ( v13 < 0 )
    goto LABEL_11;
  if ( !a3 )
  {
    v14 = 2147500035LL;
LABEL_11:
    v15 = MapAEResultToAudioClient(*(_QWORD *)v10 + 168LL, v14);
    CAudioClientTraceLogger::LogRenderGetBufferFailure((CAudioClientTraceLogger *)(*(_QWORD *)v10 + 512LL), v15);
    goto LABEL_12;
  }
  if ( *((_QWORD *)this + 15) )
  {
    v14 = 2290679815LL;
    goto LABEL_11;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 48LL))(
          *(_QWORD *)v10 + 8LL,
          &v26);
  v14 = (unsigned int)v18;
  if ( v18 < 0 )
    goto LABEL_11;
  v16 = *(_QWORD *)v10;
  if ( (*(_DWORD *)(*(_QWORD *)v10 + 480LL) == 1 || *((_DWORD *)this + 38)) && *(_DWORD *)(v16 + 232) )
  {
    if ( a2 != *((_DWORD *)this + 33) )
    {
      v14 = 2290679830LL;
      goto LABEL_11;
    }
  }
  else if ( a2 > *((_DWORD *)this + 33) - v26 )
  {
    v14 = 2290679814LL;
    goto LABEL_11;
  }
  if ( a2 )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)(v16 + 332)) == 2 )
    {
      v14 = 2290679819LL;
    }
    else
    {
      v19 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 12) + 24LL))(
                             *((_QWORD *)this + 12),
                             a2,
                             0);
      v16 = *((_QWORD *)this + 14);
      v12 = (unsigned __int8 *)v19;
      v27 = v19;
      if ( *(_DWORD *)(v16 + 480) != 1 && !*((_DWORD *)this + 38) || v19 )
      {
        v20 = *((_QWORD *)this + 18);
        v21 = (size_t *)((char *)this + 168);
        v22 = a2 * *(unsigned __int16 *)(v20 + 12);
        if ( !*((_QWORD *)this + 20) || *v21 < v22 )
        {
          v23 = CoTaskMemAlloc(a2 * *(unsigned __int16 *)(v20 + 12));
          v24 = (void *)*((_QWORD *)this + 20);
          *((_QWORD *)this + 20) = v23;
          if ( v24 )
            CoTaskMemFree(v24);
          v25 = (void *)*((_QWORD *)this + 20);
          if ( !v25 )
          {
            v12 = (unsigned __int8 *)v27;
            v14 = 2147942414LL;
            goto LABEL_41;
          }
          *v21 = v22;
          memset_0(v25, 0, v22);
        }
        v12 = (unsigned __int8 *)v27;
        *a3 = (unsigned __int8 *)*((_QWORD *)this + 20);
        *((_QWORD *)this + 15) = v12;
        *((_DWORD *)this + 32) = a2;
        goto LABEL_28;
      }
      v14 = 2290679832LL;
    }
LABEL_41:
    _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v10 + 332LL));
    goto LABEL_11;
  }
LABEL_28:
  v15 = 0;
LABEL_12:
  TraceWASAPI_IAudioRenderClient_GetBuffer((const char *)v16, v14, v29, v15, a2, a3, v12);
  if ( SRWLock )
    LeaveCriticalSection((LPCRITICAL_SECTION)SRWLock);
  EventActivityIdControl(4u, &ActivityId);
  if ( v4 )
    ReleaseSRWLockShared(v4);
  return v15;
}

```

## disassembly

```asm
0x18002f940  mov     [rsp-8+arg_18], rbx
0x18002f945  push    rbp
0x18002f946  push    rsi
0x18002f947  push    rdi
0x18002f948  push    r12
0x18002f94a  push    r13
0x18002f94c  push    r14
0x18002f94e  push    r15
0x18002f950  lea     rbp, [rsp-27h]
0x18002f955  sub     rsp, 90h
0x18002f95c  mov     rax, cs:__security_cookie
0x18002f963  xor     rax, rsp
0x18002f966  mov     [rbp+57h+var_40], rax
0x18002f96a  lea     r15, [rcx-10h]
0x18002f96e  xor     ebx, ebx
0x18002f970  mov     rax, [r15+80h]
0x18002f977  mov     r13, r8
0x18002f97a  mov     r12d, edx
0x18002f97d  mov     [rbp+57h+var_78], rbx
0x18002f981  mov     rdi, rcx
0x18002f984  mov     [rbp+57h+var_68], r15
0x18002f988  cmp     dword ptr [rax+344h], 2
0x18002f98f  jnz     short loc_18002F9E1
0x18002f991  lea     rbx, [rax+360h]
0x18002f998  mov     rcx, rbx; SRWLock
0x18002f99b  call    cs:__imp_AcquireSRWLockShared
0x18002f9a1  lea     rdx, [rbp+57h+SRWLock]
0x18002f9a5  mov     [rbp+57h+SRWLock], rbx
0x18002f9a9  lea     rcx, [rbp+57h+var_78]
0x18002f9ad  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &&)
0x18002f9b2  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002f9b6  test    rcx, rcx
0x18002f9b9  jz      short loc_18002F9C1
0x18002f9bb  call    cs:__imp_ReleaseSRWLockShared
0x18002f9c1  lea     rsi, [rdi+70h]
0x18002f9c5  xor     r8d, r8d; bAlertable
0x18002f9c8  mov     rcx, [rsi]
0x18002f9cb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002f9ce  mov     rcx, [rcx+368h]; hHandle
0x18002f9d5  call    cs:__imp_WaitForSingleObjectEx
0x18002f9db  mov     rbx, [rbp+57h+var_78]
0x18002f9df  jmp     short loc_18002F9E5
0x18002f9e1  lea     rsi, [rcx+70h]
0x18002f9e5  mov     rcx, [rsi]
0x18002f9e8  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18002f9ec  movups  xmm0, xmmword ptr [rcx+210h]
0x18002f9f3  movdqu  [rbp+57h+var_60], xmm0
0x18002f9f8  mov     rax, [rcx+210h]
0x18002f9ff  mov     qword ptr [rbp+57h+ActivityId.Data1], rax
0x18002fa03  mov     rax, [rcx+218h]
0x18002fa0a  mov     ecx, 4; ControlCode
0x18002fa0f  mov     qword ptr [rbp+57h+ActivityId.Data4], rax
0x18002fa13  call    cs:__imp_EventActivityIdControl
0x18002fa19  lea     rax, [rdi+38h]
0x18002fa1d  mov     [rbp+57h+var_80], 0
0x18002fa24  mov     rcx, rax; lpCriticalSection
0x18002fa27  mov     [rbp+57h+SRWLock], rax
0x18002fa2b  xor     r14d, r14d
0x18002fa2e  call    cs:__imp_EnterCriticalSection
0x18002fa34  test    r13, r13
0x18002fa37  jz      short loc_18002FA3D
0x18002fa39  mov     [r13+0], r14
0x18002fa3d  mov     rcx, r15; this
0x18002fa40  call    ?CheckForDisconnection@CAudioRenderClient@@QEAAJXZ; CAudioRenderClient::CheckForDisconnection(void)
0x18002fa45  mov     edx, eax
0x18002fa47  test    eax, eax
0x18002fa49  js      short loc_18002FA59
0x18002fa4b  test    r13, r13
0x18002fa4e  jnz     loc_18002FAEB
0x18002fa54  mov     edx, 80004003h
0x18002fa59  mov     rcx, [rsi]
0x18002fa5c  add     rcx, 0A8h
0x18002fa63  call    ?MapAEResultToAudioClient@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@J@Z; MapAEResultToAudioClient(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,long)
0x18002fa68  mov     rcx, [rsi]
0x18002fa6b  mov     edx, eax; int
0x18002fa6d  add     rcx, 200h; this
0x18002fa74  mov     edi, eax
0x18002fa76  call    ?LogRenderGetBufferFailure@CAudioClientTraceLogger@@QEAAXJ@Z; CAudioClientTraceLogger::LogRenderGetBufferFailure(long)
0x18002fa7b  mov     r8, [rbp+57h+var_68]; void *
0x18002fa7f  mov     r9d, edi; int
0x18002fa82  mov     [rsp+0C0h+var_90], r14; unsigned __int8 *
0x18002fa87  mov     [rsp+0C0h+var_98], r13; unsigned __int8 **
0x18002fa8c  mov     [rsp+0C0h+var_A0], r12d; unsigned int
0x18002fa91  call    ?TraceWASAPI_IAudioRenderClient_GetBuffer@@YAXPEBDIPEAXJIPEAPEAEPEAE@Z; TraceWASAPI_IAudioRenderClient_GetBuffer(char const *,uint,void *,long,uint,uchar * *,uchar *)
0x18002fa96  mov     rcx, [rbp+57h+SRWLock]; lpCriticalSection
0x18002fa9a  test    rcx, rcx
0x18002fa9d  jz      short loc_18002FAA5
0x18002fa9f  call    cs:__imp_LeaveCriticalSection
0x18002faa5  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18002faa9  mov     ecx, 4; ControlCode
0x18002faae  call    cs:__imp_EventActivityIdControl
0x18002fab4  test    rbx, rbx
0x18002fab7  jz      short loc_18002FAC2
0x18002fab9  mov     rcx, rbx; SRWLock
0x18002fabc  call    cs:__imp_ReleaseSRWLockShared
0x18002fac2  mov     eax, edi
0x18002fac4  mov     rcx, [rbp+57h+var_40]
0x18002fac8  xor     rcx, rsp; StackCookie
0x18002facb  call    __security_check_cookie
0x18002fad0  mov     rbx, [rsp+0C0h+arg_18]
0x18002fad8  add     rsp, 90h
0x18002fadf  pop     r15
0x18002fae1  pop     r14
0x18002fae3  pop     r13
0x18002fae5  pop     r12
0x18002fae7  pop     rdi
0x18002fae8  pop     rsi
0x18002fae9  pop     rbp
0x18002faea  retn
0x18002faeb  cmp     [rdi+78h], r14
0x18002faef  jz      short loc_18002FAFB
0x18002faf1  mov     edx, 88890007h
0x18002faf6  jmp     loc_18002FA59
0x18002fafb  mov     rcx, [rsi]
0x18002fafe  lea     rdx, [rbp+57h+var_80]
0x18002fb02  add     rcx, 8
0x18002fb06  mov     rax, [rcx]
0x18002fb09  mov     rax, [rax+30h]
0x18002fb0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb12  mov     edx, eax
0x18002fb14  test    eax, eax
0x18002fb16  js      loc_18002FA59
0x18002fb1c  mov     rcx, [rsi]
0x18002fb1f  mov     r15d, 1
0x18002fb25  cmp     [rcx+1E0h], r15d
0x18002fb2c  jz      short loc_18002FB37
0x18002fb2e  cmp     [rdi+98h], r14d
0x18002fb35  jz      short loc_18002FB53
0x18002fb37  cmp     [rcx+0E8h], r14d
0x18002fb3e  jz      short loc_18002FB53
0x18002fb40  cmp     r12d, [rdi+84h]
0x18002fb47  jz      short loc_18002FB6B
0x18002fb49  mov     edx, 88890016h
0x18002fb4e  jmp     loc_18002FA59
0x18002fb53  mov     eax, [rdi+84h]
0x18002fb59  sub     eax, [rbp+57h+var_80]
0x18002fb5c  cmp     r12d, eax
0x18002fb5f  jbe     short loc_18002FB6B
0x18002fb61  mov     edx, 88890006h
0x18002fb66  jmp     loc_18002FA59
0x18002fb6b  test    r12d, r12d
0x18002fb6e  jnz     short loc_18002FB77
0x18002fb70  xor     edi, edi
0x18002fb72  jmp     loc_18002FA7B
0x18002fb77  mov     eax, r15d
0x18002fb7a  lock xadd [rcx+14Ch], eax
0x18002fb82  add     eax, r15d
0x18002fb85  cmp     eax, 2
0x18002fb88  jnz     short loc_18002FB94
0x18002fb8a  mov     edx, 8889000Bh
0x18002fb8f  jmp     loc_18002FC30
0x18002fb94  mov     rcx, [rdi+60h]
0x18002fb98  xor     r8d, r8d
0x18002fb9b  mov     edx, r12d
0x18002fb9e  mov     rax, [rcx]
0x18002fba1  mov     rax, [rax+18h]
0x18002fba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbaa  mov     rcx, [rdi+70h]
0x18002fbae  mov     r14, rax
0x18002fbb1  mov     [rbp+57h+var_78], rax
0x18002fbb5  cmp     [rcx+1E0h], r15d
0x18002fbbc  jz      short loc_18002FBC7
0x18002fbbe  cmp     dword ptr [rdi+98h], 0
0x18002fbc5  jz      short loc_18002FBD3
0x18002fbc7  test    rax, rax
0x18002fbca  jnz     short loc_18002FBD3
0x18002fbcc  mov     edx, 88890018h
0x18002fbd1  jmp     short loc_18002FC30
0x18002fbd3  mov     rax, [rdi+90h]
0x18002fbda  lea     r15, [rdi+0A8h]
0x18002fbe1  movzx   r14d, word ptr [rax+0Ch]
0x18002fbe6  imul    r14d, r12d
0x18002fbea  cmp     qword ptr [rdi+0A0h], 0
0x18002fbf2  jz      short loc_18002FBF9
0x18002fbf4  cmp     [r15], r14
0x18002fbf7  jnb     short loc_18002FC4C
0x18002fbf9  mov     rcx, r14; cb
0x18002fbfc  call    cs:__imp_CoTaskMemAlloc
0x18002fc02  mov     rcx, [rdi+0A0h]; pv
0x18002fc09  mov     [rdi+0A0h], rax
0x18002fc10  test    rcx, rcx
0x18002fc13  jz      short loc_18002FC1B
0x18002fc15  call    cs:__imp_CoTaskMemFree
0x18002fc1b  mov     rcx, [rdi+0A0h]; void *
0x18002fc22  test    rcx, rcx
0x18002fc25  jnz     short loc_18002FC3F
0x18002fc27  mov     r14, [rbp+57h+var_78]
0x18002fc2b  mov     edx, 8007000Eh
0x18002fc30  mov     rax, [rsi]
0x18002fc33  lock dec dword ptr [rax+14Ch]
0x18002fc3a  jmp     loc_18002FA59
0x18002fc3f  mov     r8, r14; Size
0x18002fc42  mov     [r15], r14
0x18002fc45  xor     edx, edx; Val
0x18002fc47  call    memset_0
0x18002fc4c  mov     rax, [rdi+0A0h]
0x18002fc53  mov     r14, [rbp+57h+var_78]
0x18002fc57  mov     [r13+0], rax
0x18002fc5b  mov     [rdi+78h], r14
0x18002fc5f  mov     [rdi+80h], r12d
0x18002fc66  jmp     loc_18002FB70
```
