# CSmsDeviceManager::PublishSmsReadDoneData(void *,ulong)

- ea: `0x180041aa8`
- end: `0x180041c40`
- name: `?PublishSmsReadDoneData@CSmsDeviceManager@@AEAAXPEAXK@Z`
- size: `408`
- prototype: `void __fastcall(CSmsDeviceManager *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800430d0`

## callees

- `0x180003f30`
- `0x180004140`
- `0x1800041a8`
- `0x180041aa8`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180041c1d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180041c1d`
- `ntdll!RtlWaitForWnfMetaNotification` at `0x180041b39`
- `ntdll!RtlWaitForWnfMetaNotification` at `0x180041b39`
- `ntdll!RtlPublishWnfStateData` at `0x180041b85`
- `ntdll!RtlPublishWnfStateData` at `0x180041b85`

## string_xrefs

- `0x180041b65`: `CSmsDeviceManager::PublishSmsReadDoneData`
- `0x180041ba2`: `CSmsDeviceManager::PublishSmsReadDoneData`
- `0x180041bd2`: `CSmsDeviceManager::PublishSmsReadDoneData`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CSmsDeviceManager::PublishSmsReadDoneData(CSmsDeviceManager *this, void *a2, unsigned int a3)
{
  signed int v5; // eax
  signed int v6; // eax
  int v7; // [rsp+70h] [rbp+8h] BYREF
  int v8; // [rsp+74h] [rbp+Ch]

  v8 = HIDWORD(this);
  v7 = 0;
  if ( dword_18008DC90 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18008DC90);
    if ( dword_18008DC90 == -1 )
    {
      InitializeCriticalSection(&stru_18008C3C8);
      atexit(CSmsDeviceManager::PublishSmsReadDoneData_::_2_::_dynamic_atexit_destructor_for__s_smsIndexWnfMutex__);
      Init_thread_footer(&dword_18008DC90);
    }
  }
  ((void (__fastcall *)(void ***))*off_18008C3C0)(&off_18008C3C0);
  v5 = RtlWaitForWnfMetaNotification(WNF_SMSR_WWAN_READ_DONE, 8, 500, 100, &v7);
  if ( v5 )
  {
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    LogSmsRouterError(
      "CSmsDeviceManager::PublishSmsReadDoneData",
      0x678u,
      v5,
      "Failed to wait for wnf meta notification while publishing wnf(buffer=%p) Length=%d",
      a2,
      a3);
  }
  v6 = RtlPublishWnfStateData(WNF_SMSR_WWAN_READ_DONE, 0, a2, a3, 0);
  if ( v6 )
  {
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    LogSmsRouterError(
      "CSmsDeviceManager::PublishSmsReadDoneData",
      0x68Bu,
      v6,
      "Failed to publish wnf(buffer=%p) Length=%d",
      a2,
      a3);
  }
  else
  {
    LogSmsRouterInfo(
      "CSmsDeviceManager::PublishSmsReadDoneData",
      0x686u,
      "Done publishing wnf(buffer=%p) Length=%d",
      a2,
      a3);
  }
  ((void (__fastcall *)(void ***))off_18008C3C0[1])(&off_18008C3C0);
}

```

## disassembly

```asm
0x180041aa8  mov     [rsp+arg_0], rcx
0x180041aad  push    rbx
0x180041aae  push    rsi
0x180041aaf  push    rdi
0x180041ab0  push    r15
0x180041ab2  sub     rsp, 48h
0x180041ab6  mov     edi, r8d
0x180041ab9  mov     rsi, rdx
0x180041abc  mov     rbx, cs:WNF_SMSR_WWAN_READ_DONE
0x180041ac3  mov     dword ptr [rsp+68h+arg_0], 0
0x180041acb  mov     ecx, cs:_tls_index
0x180041ad1  mov     rax, gs:58h
0x180041ada  mov     edx, 4
0x180041adf  mov     rax, [rax+rcx*8]
0x180041ae3  mov     eax, [rdx+rax]
0x180041ae6  cmp     cs:dword_18008DC90, eax
0x180041aec  jg      loc_180041BFD
0x180041af2  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180041af9  mov     [rsp+68h+var_38], rax
0x180041afe  lea     r15, off_18008C3C0
0x180041b05  mov     [rsp+68h+var_30], r15
0x180041b0a  mov     rax, cs:off_18008C3C0
0x180041b11  mov     rcx, r15
0x180041b14  mov     rax, [rax]
0x180041b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b1c  nop
0x180041b1d  lea     rax, [rsp+68h+arg_0]
0x180041b22  mov     [rsp+68h+var_48], rax
0x180041b27  mov     edx, 8
0x180041b2c  lea     r9d, [rdx+5Ch]
0x180041b30  mov     r8d, 1F4h
0x180041b36  mov     rcx, rbx
0x180041b39  call    cs:__imp_RtlWaitForWnfMetaNotification
0x180041b3f  test    eax, eax
0x180041b41  jz      short loc_180041B71
0x180041b43  jle     short loc_180041B4D
0x180041b45  movzx   eax, ax
0x180041b48  or      eax, 80070000h
0x180041b4d  mov     [rsp+68h+var_40], edi
0x180041b51  mov     [rsp+68h+var_48], rsi
0x180041b56  lea     r9, aFailedToWaitFo; "Failed to wait for wnf meta notificatio"...
0x180041b5d  mov     r8d, eax; int
0x180041b60  mov     edx, 678h; unsigned int
0x180041b65  lea     rcx, aCsmsdevicemana_14; "CSmsDeviceManager::PublishSmsReadDoneDa"...
0x180041b6c  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180041b71  mov     [rsp+68h+var_48], 0
0x180041b7a  mov     r9d, edi
0x180041b7d  mov     r8, rsi
0x180041b80  xor     edx, edx
0x180041b82  mov     rcx, rbx
0x180041b85  call    cs:__imp_RtlPublishWnfStateData
0x180041b8b  test    eax, eax
0x180041b8d  jnz     short loc_180041BB0
0x180041b8f  mov     dword ptr [rsp+68h+var_48], edi
0x180041b93  mov     r9, rsi
0x180041b96  lea     r8, aDonePublishing; "Done publishing wnf(buffer=%p) Length=%"...
0x180041b9d  mov     edx, 686h; unsigned int
0x180041ba2  lea     rcx, aCsmsdevicemana_14; "CSmsDeviceManager::PublishSmsReadDoneDa"...
0x180041ba9  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180041bae  jmp     short loc_180041BDF
0x180041bb0  jle     short loc_180041BBA
0x180041bb2  movzx   eax, ax
0x180041bb5  or      eax, 80070000h
0x180041bba  mov     [rsp+68h+var_40], edi
0x180041bbe  mov     [rsp+68h+var_48], rsi
0x180041bc3  lea     r9, aFailedToPublis; "Failed to publish wnf(buffer=%p) Length"...
0x180041bca  mov     r8d, eax; int
0x180041bcd  mov     edx, 68Bh; unsigned int
0x180041bd2  lea     rcx, aCsmsdevicemana_14; "CSmsDeviceManager::PublishSmsReadDoneDa"...
0x180041bd9  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180041bde  nop
0x180041bdf  mov     rax, cs:off_18008C3C0
0x180041be6  mov     rcx, r15
0x180041be9  mov     rax, [rax+8]
0x180041bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041bf2  nop
0x180041bf3  add     rsp, 48h
0x180041bf7  pop     r15
0x180041bf9  pop     rdi
0x180041bfa  pop     rsi
0x180041bfb  pop     rbx
0x180041bfc  retn
0x180041bfd  lea     rcx, dword_18008DC90
0x180041c04  call    _Init_thread_header
0x180041c09  cmp     cs:dword_18008DC90, 0FFFFFFFFh
0x180041c10  jnz     loc_180041AF2
0x180041c16  lea     rcx, stru_18008C3C8; lpCriticalSection
0x180041c1d  call    cs:__imp_InitializeCriticalSection
0x180041c23  lea     rcx, _CSmsDeviceManager__PublishSmsReadDoneData____2____dynamic_atexit_destructor_for__s_smsIndexWnfMutex__; void (__cdecl *)()
0x180041c2a  call    atexit
0x180041c2f  lea     rcx, dword_18008DC90
0x180041c36  call    _Init_thread_footer
0x180041c3b  jmp     loc_180041AF2
```
