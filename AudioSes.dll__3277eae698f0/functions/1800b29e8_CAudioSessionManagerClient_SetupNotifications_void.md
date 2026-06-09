# CAudioSessionManagerClient::SetupNotifications(void)

- ea: `0x1800b29e8`
- end: `0x1800b2b23`
- name: `?SetupNotifications@CAudioSessionManagerClient@@IEAAJXZ`
- size: `315`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006fff0`
- `0x1800710e8`

## callees

- `0x180007f00`
- `0x18000a9cc`
- `0x18000cd10`
- `0x180010a90`
- `0x1800b1930`
- `0x1800b29e8`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800b2a24`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800b2a24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b2a09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b2a09`
- `ntdll!RtlDllShutdownInProgress` at `0x1800b29fa`
- `ntdll!RtlDllShutdownInProgress` at `0x1800b29fa`
- `MMDevAPI!__imp_RegisterForMediaCallback` at `0x1800b2aac`
- `MMDevAPI!__imp_RegisterForMediaCallback` at `0x1800b2aac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioSessionManagerClient::SetupNotifications(char *pv)
{
  const char *v2; // r9
  PTP_WORK ThreadpoolWork; // rax
  int v5; // eax
  unsigned int v6; // edi
  __int64 v7; // rdi
  int v8; // eax
  int v9; // esi
  __int64 v10; // rcx
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v13; // [rsp+30h] [rbp+8h] BYREF

  if ( RtlDllShutdownInProgress() )
  {
    SetLastError(0x32u);
    ThreadpoolWork = 0;
  }
  else
  {
    ThreadpoolWork = CreateThreadpoolWork(
                       lambda_4e4bcd79fbed1ed0f2626c483add86b9_::_lambda_invoker_cdecl_,
                       pv,
                       &stru_18018FD58);
  }
  *((_QWORD *)pv + 60) = ThreadpoolWork;
  if ( !ThreadpoolWork )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x380,
             (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientsessionmgr.cpp",
             v2);
  v13 = 0;
  wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset(&v13);
  v5 = Microsoft::WRL::Details::MakeAndInitialize<CAudioSessionManagerClient::CAudioSessionManagerNotificationDelegator,CAudioSessionManagerClient::CAudioSessionManagerNotificationDelegator,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> &>(
         &v13,
         pv + 160);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = v13;
    if ( *((_DWORD *)pv + 69) != 2 )
    {
      v8 = RegisterForMediaCallback(576, v13);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x38B,
          (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientsessionmgr.cpp",
          (const char *)(unsigned int)v8,
          v11);
        v6 = v9;
        goto LABEL_15;
      }
      pv[266] = 1;
    }
    v13 = 0;
    v10 = *((_QWORD *)pv + 23);
    *((_QWORD *)pv + 23) = v7;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v6 = 0;
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x383,
    (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientsessionmgr.cpp",
    (const char *)(unsigned int)v5,
    v11);
LABEL_15:
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v13);
  return v6;
}

```

## disassembly

```asm
0x1800b29e8  mov     [rsp+arg_8], rbx
0x1800b29ed  mov     [rsp+arg_10], rsi
0x1800b29f2  push    rdi; int
0x1800b29f3  sub     rsp, 20h
0x1800b29f7  mov     rbx, rcx
0x1800b29fa  call    cs:__imp_RtlDllShutdownInProgress
0x1800b2a00  test    al, al
0x1800b2a02  jz      short loc_1800B2A13
0x1800b2a04  mov     ecx, 32h ; '2'; dwErrCode
0x1800b2a09  call    cs:__imp_SetLastError
0x1800b2a0f  xor     eax, eax
0x1800b2a11  jmp     short loc_1800B2A2A
0x1800b2a13  lea     r8, stru_18018FD58; pcbe
0x1800b2a1a  mov     rdx, rbx; pv
0x1800b2a1d  lea     rcx, _lambda_4e4bcd79fbed1ed0f2626c483add86b9____lambda_invoker_cdecl_; pfnwk
0x1800b2a24  call    cs:__imp_CreateThreadpoolWork
0x1800b2a2a  mov     [rbx+1E0h], rax
0x1800b2a31  test    rax, rax
0x1800b2a34  jnz     short loc_1800B2A51
0x1800b2a36  mov     rcx, [rsp+28h]; this
0x1800b2a3b  lea     r8, aAvcoreAudiocor_21; "avcore\\audiocore\\client\\audioclient"...
0x1800b2a42  mov     edx, 380h; void *
0x1800b2a47  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b2a4c  jmp     loc_1800B2B13
0x1800b2a51  mov     [rsp+28h+arg_0], 0
0x1800b2a5a  lea     rcx, [rsp+28h+arg_0]
0x1800b2a5f  call    ?reset@?$com_ptr_t@UIMediaNotificationCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset(void)
0x1800b2a64  lea     rdx, [rbx+0A0h]
0x1800b2a6b  lea     rcx, [rsp+28h+arg_0]
0x1800b2a70  call    ??$MakeAndInitialize@VCAudioSessionManagerNotificationDelegator@CAudioSessionManagerClient@@V12@AEAV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@Details@WRL@Microsoft@@YAJPEAPEAVCAudioSessionManagerNotificationDelegator@CAudioSessionManagerClient@@AEAV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CAudioSessionManagerClient::CAudioSessionManagerNotificationDelegator,CAudioSessionManagerClient::CAudioSessionManagerNotificationDelegator,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> &>(CAudioSessionManagerClient::CAudioSessionManagerNotificationDelegator * *,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> &)
0x1800b2a75  mov     edi, eax
0x1800b2a77  test    eax, eax
0x1800b2a79  jns     short loc_1800B2A96
0x1800b2a7b  mov     rcx, [rsp+28h]; this
0x1800b2a80  mov     r9d, eax; char *
0x1800b2a83  lea     r8, aAvcoreAudiocor_21; "avcore\\audiocore\\client\\audioclient"...
0x1800b2a8a  mov     edx, 383h; void *
0x1800b2a8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2a94  jmp     short loc_1800B2B07
0x1800b2a96  mov     rdi, [rsp+28h+arg_0]
0x1800b2a9b  cmp     dword ptr [rbx+114h], 2
0x1800b2aa2  jz      short loc_1800B2ADC
0x1800b2aa4  mov     rdx, rdi
0x1800b2aa7  mov     ecx, 240h
0x1800b2aac  call    cs:__imp_RegisterForMediaCallback
0x1800b2ab2  mov     esi, eax
0x1800b2ab4  test    eax, eax
0x1800b2ab6  jns     short loc_1800B2AD5
0x1800b2ab8  mov     rcx, [rsp+28h]; this
0x1800b2abd  mov     r9d, eax; char *
0x1800b2ac0  lea     r8, aAvcoreAudiocor_21; "avcore\\audiocore\\client\\audioclient"...
0x1800b2ac7  mov     edx, 38Bh; void *
0x1800b2acc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2ad1  mov     edi, esi
0x1800b2ad3  jmp     short loc_1800B2B07
0x1800b2ad5  mov     byte ptr [rbx+10Ah], 1
0x1800b2adc  mov     [rsp+28h+arg_0], 0
0x1800b2ae5  mov     rcx, [rbx+0B8h]
0x1800b2aec  mov     [rbx+0B8h], rdi
0x1800b2af3  test    rcx, rcx
0x1800b2af6  jz      short loc_1800B2B05
0x1800b2af8  mov     rax, [rcx]
0x1800b2afb  mov     rax, [rax+10h]
0x1800b2aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2b04  nop
0x1800b2b05  xor     edi, edi
0x1800b2b07  lea     rcx, [rsp+28h+arg_0]; void *
0x1800b2b0c  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800b2b11  mov     eax, edi
0x1800b2b13  mov     rbx, [rsp+28h+arg_8]
0x1800b2b18  mov     rsi, [rsp+28h+arg_10]
0x1800b2b1d  add     rsp, 20h
0x1800b2b21  pop     rdi
0x1800b2b22  retn
```
