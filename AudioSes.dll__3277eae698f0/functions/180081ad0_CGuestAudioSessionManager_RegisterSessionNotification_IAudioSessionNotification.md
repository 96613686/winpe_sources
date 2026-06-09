# CGuestAudioSessionManager::RegisterSessionNotification(IAudioSessionNotification *)

- ea: `0x180081ad0`
- end: `0x180081c9c`
- name: `?RegisterSessionNotification@CGuestAudioSessionManager@@UEAAJPEAUIAudioSessionNotification@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(CGuestAudioSessionManager *__hidden this, struct IAudioSessionNotification *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180007f00`
- `0x18000cd10`
- `0x180010a90`
- `0x18004d8a8`
- `0x180081ad0`
- `0x1800b821c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180081af3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180081af3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081b39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081c80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081b39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081c80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081c4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081c69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081c4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081c69`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CGuestAudioSessionManager::RegisterSessionNotification(
        struct _RTL_CRITICAL_SECTION *this,
        struct IAudioSessionNotification *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  int v5; // eax
  int v6; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HANDLE *); // rbx
  int v11; // r8d
  void *v12; // rcx
  void *v13; // rcx
  int v14; // [rsp+20h] [rbp-30h]
  int v15; // [rsp+20h] [rbp-30h]
  LPVOID *p_pv; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+38h] [rbp-18h] BYREF
  char v18; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  __int64 v20; // [rsp+80h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+40h] BYREF
  __int64 v22; // [rsp+98h] [rbp+48h] BYREF

  v4 = this + 4;
  EnterCriticalSection(this + 4);
  v5 = (*(__int64 (__fastcall **)(ULONG_PTR, struct IAudioSessionNotification *))(*(_QWORD *)(this[3].SpinCount + 16)
                                                                                + 48LL))(
         this[3].SpinCount + 16,
         a2);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudiosessionmanager.cpp",
      (const char *)(unsigned int)v5,
      v14);
LABEL_3:
    if ( v4 )
      LeaveCriticalSection(v4);
    return (unsigned int)v6;
  }
  if ( !this[1].OwningThread )
  {
    v20 = 0;
    v6 = (**(__int64 (__fastcall ***)(ULONG_PTR, GUID *, __int64 *))this[3].SpinCount)(
           this[3].SpinCount,
           &GUID_2bc4719a_bccc_4ead_adaf_155d5bb77478,
           &v20);
    if ( v6 < 0 )
    {
      v8 = 106;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudiosessionmanager.cpp",
        (const char *)(unsigned int)v6,
        v14);
LABEL_10:
      wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v20);
      goto LABEL_3;
    }
    v9 = v20;
    v10 = *(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v20 + 24LL);
    wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset(&this[1].OwningThread);
    v6 = v10(v9, &this[1].OwningThread);
    if ( v6 < 0 )
    {
      v8 = 108;
      goto LABEL_9;
    }
    pv = 0;
    v22 = 0;
    p_pv = &pv;
    v17 = 0;
    v18 = 1;
    LOBYTE(v11) = 0;
    v6 = CGuestXvmAudioObject::SendAndValidateResponse<XvmRegisterSessionEnabledNotification>(
           (int)this + 24,
           this[1].SpinCount,
           v11,
           (unsigned int)&v17,
           (__int64)&v22);
    wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudiosessionmanager.cpp",
        (const char *)(unsigned int)v6,
        v15);
      v12 = pv;
      pv = 0;
      if ( v12 )
        CoTaskMemFree(v12);
      goto LABEL_10;
    }
    v13 = pv;
    pv = 0;
    if ( v13 )
      CoTaskMemFree(v13);
    wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v20);
  }
  if ( v4 )
    LeaveCriticalSection(v4);
  return 0;
}

```

## disassembly

```asm
0x180081ad0  mov     [rsp-28h+arg_8], rbx
0x180081ad5  push    rbp
0x180081ad6  push    rsi
0x180081ad7  push    rdi
0x180081ad8  push    r14
0x180081ada  push    r15
0x180081adc  mov     rbp, rsp
0x180081adf  sub     rsp, 50h
0x180081ae3  mov     rbx, rdx
0x180081ae6  mov     r14, rcx
0x180081ae9  lea     rsi, [rcx+0A0h]
0x180081af0  mov     rcx, rsi; lpCriticalSection
0x180081af3  call    cs:__imp_EnterCriticalSection
0x180081af9  mov     rcx, [r14+98h]
0x180081b00  add     rcx, 10h
0x180081b04  mov     rax, [rcx]
0x180081b07  mov     rdx, rbx
0x180081b0a  mov     rax, [rax+30h]
0x180081b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081b13  mov     ebx, eax
0x180081b15  test    eax, eax
0x180081b17  jns     short loc_180081B46
0x180081b19  mov     rcx, [rbp+28h]; this
0x180081b1d  mov     r9d, eax; char *
0x180081b20  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\client\\audioclient"...
0x180081b27  mov     edx, 63h ; 'c'; void *
0x180081b2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081b31  test    rsi, rsi
0x180081b34  jz      short loc_180081B3F
0x180081b36  mov     rcx, rsi; lpCriticalSection
0x180081b39  call    cs:__imp_LeaveCriticalSection
0x180081b3f  mov     eax, ebx
0x180081b41  jmp     loc_180081C88
0x180081b46  lea     r15, [r14+38h]
0x180081b4a  cmp     qword ptr [r15], 0
0x180081b4e  jnz     loc_180081C78
0x180081b54  mov     [rbp+arg_0], 0
0x180081b5c  mov     rcx, [r14+98h]
0x180081b63  mov     rax, [rcx]
0x180081b66  lea     r8, [rbp+arg_0]
0x180081b6a  lea     rdx, _GUID_2bc4719a_bccc_4ead_adaf_155d5bb77478
0x180081b71  mov     rax, [rax]
0x180081b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081b79  mov     ebx, eax
0x180081b7b  test    eax, eax
0x180081b7d  jns     short loc_180081BA2
0x180081b7f  mov     edx, 6Ah ; 'j'; void *
0x180081b84  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\client\\audioclient"...
0x180081b8b  mov     r9d, ebx; char *
0x180081b8e  mov     rcx, [rbp+28h]; this
0x180081b92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081b97  lea     rcx, [rbp+arg_0]; void *
0x180081b9b  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180081ba0  jmp     short loc_180081B31
0x180081ba2  mov     rdi, [rbp+arg_0]
0x180081ba6  mov     rax, [rdi]
0x180081ba9  mov     rbx, [rax+18h]
0x180081bad  mov     rcx, r15
0x180081bb0  call    ?reset@?$com_ptr_t@UIMediaNotificationCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset(void)
0x180081bb5  mov     rdx, r15
0x180081bb8  mov     rcx, rdi
0x180081bbb  mov     rax, rbx
0x180081bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081bc3  mov     ebx, eax
0x180081bc5  test    eax, eax
0x180081bc7  jns     short loc_180081BD0
0x180081bc9  mov     edx, 6Ch ; 'l'
0x180081bce  jmp     short loc_180081B84
0x180081bd0  mov     [rbp+pv], 0
0x180081bd8  mov     [rbp+arg_18], 0
0x180081be0  lea     rax, [rbp+pv]
0x180081be4  mov     [rbp+var_20], rax
0x180081be8  mov     [rbp+var_18], 0
0x180081bf0  mov     [rbp+var_10], 1
0x180081bf4  xor     r8b, r8b
0x180081bf7  lea     rcx, [r14+18h]
0x180081bfb  lea     rax, [rbp+arg_18]
0x180081bff  mov     qword ptr [rsp+50h+var_30], rax; int
0x180081c04  lea     r9, [rbp+var_18]
0x180081c08  mov     edx, [r14+48h]
0x180081c0c  call    ??$SendAndValidateResponse@UXvmRegisterSessionEnabledNotification@@@CGuestXvmAudioObject@@QEAAJIUXvmRegisterSessionEnabledNotification@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmRegisterSessionEnabledNotification>(uint,XvmRegisterSessionEnabledNotification,XvmMessage * *,XvmRegisterSessionEnabledNotification * *)
0x180081c11  mov     ebx, eax
0x180081c13  lea     rcx, [rbp+var_20]
0x180081c17  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180081c1c  test    ebx, ebx
0x180081c1e  jns     short loc_180081C58
0x180081c20  mov     rcx, [rbp+28h]; this
0x180081c24  mov     r9d, ebx; char *
0x180081c27  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\client\\audioclient"...
0x180081c2e  mov     edx, 71h ; 'q'; void *
0x180081c33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081c38  mov     rcx, [rbp+pv]; pv
0x180081c3c  mov     [rbp+pv], 0
0x180081c44  test    rcx, rcx
0x180081c47  jz      loc_180081B97
0x180081c4d  call    cs:__imp_CoTaskMemFree
0x180081c53  jmp     loc_180081B97
0x180081c58  mov     rcx, [rbp+pv]; pv
0x180081c5c  mov     [rbp+pv], 0
0x180081c64  test    rcx, rcx
0x180081c67  jz      short loc_180081C6F
0x180081c69  call    cs:__imp_CoTaskMemFree
0x180081c6f  lea     rcx, [rbp+arg_0]; void *
0x180081c73  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180081c78  test    rsi, rsi
0x180081c7b  jz      short loc_180081C86
0x180081c7d  mov     rcx, rsi; lpCriticalSection
0x180081c80  call    cs:__imp_LeaveCriticalSection
0x180081c86  xor     eax, eax
0x180081c88  mov     rbx, [rsp+50h+arg_8]
0x180081c90  add     rsp, 50h
0x180081c94  pop     r15
0x180081c96  pop     r14
0x180081c98  pop     rdi
0x180081c99  pop     rsi
0x180081c9a  pop     rbp
0x180081c9b  retn
```
