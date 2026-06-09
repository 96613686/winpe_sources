# KsHandleWrapper::RegisterForNotifications(void)

- ea: `0x180026b64`
- end: `0x180026cf6`
- name: `?RegisterForNotifications@KsHandleWrapper@@QEAAJXZ`
- size: `402`
- prototype: `__int64 __fastcall(KsHandleWrapper *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800267e4`
- `0x180028020`
- `0x180028300`

## callees

- `0x180004410`
- `0x180004434`
- `0x180004460`
- `0x18000526c`
- `0x180025ea4`
- `0x180026b64`
- `0x180026d88`
- `0x1800270a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180026be1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180026be1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180026c0c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180026c0c`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180026cbd`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180026cbd`

## pseudocode

```c
__int64 __fastcall KsHandleWrapper::RegisterForNotifications(KsHandleWrapper *this)
{
  __int64 result; // rax
  struct _TP_WORK **v3; // rsi
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  char *v6; // [rsp+20h] [rbp-208h]
  _QWORD v7[9]; // [rsp+28h] [rbp-200h] BYREF
  _DWORD v8[4]; // [rsp+70h] [rbp-1B8h] BYREF
  __int64 v9; // [rsp+80h] [rbp-1A8h]

  if ( ((*((_QWORD *)this + 1) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    return 2147942406LL;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl) )
  {
    if ( !*((_QWORD *)this + 7) )
    {
      v6 = (char *)operator new(0x48u);
      *(_QWORD *)v6 = 0;
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v6 + 8), 0, 0);
      *((_QWORD *)v6 + 6) = 0;
      *((_QWORD *)v6 + 7) = 0;
      *((_QWORD *)v6 + 8) = 0;
      *(_QWORD *)v6 = CreateThreadpoolWork(ThreadpoolWork::Callback, v6, 0);
      v3 = (struct _TP_WORK **)*((_QWORD *)this + 7);
      *((_QWORD *)this + 7) = v6;
      if ( v3 )
      {
        ThreadpoolWork::~ThreadpoolWork(v3);
        operator delete(v3);
      }
    }
    v4 = (_QWORD *)((char *)this + 48);
    if ( !*((_QWORD *)this + 6) )
      goto LABEL_11;
    v7[1] = *((_QWORD *)this + 6);
    v7[0] = off_180042820;
    v5 = *((_QWORD *)this + 7);
    v7[7] = v7;
    ThreadpoolWork::Submit(v5, (__int64)v7);
  }
  else
  {
    v4 = (_QWORD *)((char *)this + 48);
    if ( !*((_QWORD *)this + 6) )
      goto LABEL_11;
  }
  *v4 = 0;
LABEL_11:
  memset_0(v8, 0, 0x1A0u);
  v9 = *((_QWORD *)this + 1);
  v8[0] = 416;
  v8[2] = 1;
  result = CM_Register_Notification(v8, this, &KsHandleWrapper::PnPCallback, v4, v6);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180026b64  mov     [rsp+arg_8], rbx
0x180026b69  mov     [rsp+arg_10], rsi
0x180026b6e  push    rdi
0x180026b6f  sub     rsp, 220h
0x180026b76  mov     rax, cs:__security_cookie
0x180026b7d  xor     rax, rsp
0x180026b80  mov     [rsp+228h+var_18], rax
0x180026b88  mov     rax, [rcx+8]
0x180026b8c  mov     rdi, rcx
0x180026b8f  inc     rax
0x180026b92  test    rax, 0FFFFFFFFFFFFFFFEh
0x180026b98  jnz     short loc_180026BA4
0x180026b9a  mov     eax, 80070006h
0x180026b9f  jmp     loc_180026CD1
0x180026ba4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x180026bab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x180026bb0  test    al, al
0x180026bb2  jz      loc_180026C6E
0x180026bb8  cmp     qword ptr [rdi+38h], 0
0x180026bbd  jnz     short loc_180026C37
0x180026bbf  mov     ecx, 48h ; 'H'; Size
0x180026bc4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026bc9  xor     r8d, r8d; Flags
0x180026bcc  mov     [rsp+228h+var_208], rax
0x180026bd1  xor     edx, edx; dwSpinCount
0x180026bd3  mov     rbx, rax
0x180026bd6  lea     rcx, [rax+8]; lpCriticalSection
0x180026bda  mov     qword ptr [rax], 0
0x180026be1  call    cs:__imp_InitializeCriticalSectionEx
0x180026be7  xor     r8d, r8d; pcbe
0x180026bea  mov     qword ptr [rbx+30h], 0
0x180026bf2  mov     rdx, rbx; pv
0x180026bf5  mov     qword ptr [rbx+38h], 0
0x180026bfd  lea     rcx, ?Callback@ThreadpoolWork@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180026c04  mov     qword ptr [rbx+40h], 0
0x180026c0c  call    cs:__imp_CreateThreadpoolWork
0x180026c12  mov     [rbx], rax
0x180026c15  mov     rsi, [rdi+38h]
0x180026c19  mov     [rdi+38h], rbx
0x180026c1d  test    rsi, rsi
0x180026c20  jz      short loc_180026C37
0x180026c22  mov     rcx, rsi; this
0x180026c25  call    ??1ThreadpoolWork@@QEAA@XZ; ThreadpoolWork::~ThreadpoolWork(void)
0x180026c2a  mov     edx, 48h ; 'H'
0x180026c2f  mov     rcx, rsi; Block
0x180026c32  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026c37  lea     rbx, [rdi+30h]
0x180026c3b  mov     rax, [rbx]
0x180026c3e  test    rax, rax
0x180026c41  jz      short loc_180026C7F
0x180026c43  lea     rcx, off_180042820
0x180026c4a  mov     [rsp+228h+var_1F8], rax
0x180026c4f  mov     [rsp+228h+var_200], rcx
0x180026c54  lea     rax, [rsp+228h+var_200]
0x180026c59  mov     rcx, [rdi+38h]
0x180026c5d  lea     rdx, [rsp+228h+var_200]
0x180026c62  mov     [rsp+228h+var_1C8], rax
0x180026c67  call    ?Submit@ThreadpoolWork@@QEAAXV?$function@$$A6AXXZ@std@@@Z; ThreadpoolWork::Submit(std::function<void (void)>)
0x180026c6c  jmp     short loc_180026C78
0x180026c6e  lea     rbx, [rdi+30h]
0x180026c72  cmp     qword ptr [rbx], 0
0x180026c76  jz      short loc_180026C7F
0x180026c78  mov     qword ptr [rbx], 0
0x180026c7f  mov     esi, 1A0h
0x180026c84  lea     rcx, [rsp+228h+var_1B8]; void *
0x180026c89  mov     r8d, esi; Size
0x180026c8c  xor     edx, edx; Val
0x180026c8e  call    memset_0
0x180026c93  mov     rax, [rdi+8]
0x180026c97  lea     r8, ?PnPCallback@KsHandleWrapper@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; KsHandleWrapper::PnPCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x180026c9e  mov     r9, rbx
0x180026ca1  mov     [rsp+228h+var_1A8], rax
0x180026ca9  mov     rdx, rdi
0x180026cac  mov     [rsp+228h+var_1B8], esi
0x180026cb0  lea     rcx, [rsp+228h+var_1B8]
0x180026cb5  mov     [rsp+228h+var_1B0], 1
0x180026cbd  call    cs:__imp_CM_Register_Notification
0x180026cc3  test    eax, eax
0x180026cc5  jz      short loc_180026CD1
0x180026cc7  jle     short loc_180026CD1
0x180026cc9  movzx   eax, ax
0x180026ccc  or      eax, 80070000h
0x180026cd1  mov     rcx, [rsp+228h+var_18]
0x180026cd9  xor     rcx, rsp; StackCookie
0x180026cdc  call    __security_check_cookie
0x180026ce1  lea     r11, [rsp+228h+var_8]
0x180026ce9  mov     rbx, [r11+18h]
0x180026ced  mov     rsi, [r11+20h]
0x180026cf1  mov     rsp, r11
0x180026cf4  pop     rdi
0x180026cf5  retn
```
