# KsHandleWrapper::RegisterForNotifications(void)

- ea: `0x180047614`
- end: `0x1800477a6`
- name: `?RegisterForNotifications@KsHandleWrapper@@QEAAJXZ`
- size: `402`
- prototype: `__int64 __fastcall(KsHandleWrapper *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180047294`
- `0x180048b80`
- `0x180048e60`

## callees

- `0x180005020`
- `0x180005044`
- `0x180005070`
- `0x180005e9c`
- `0x180046958`
- `0x180047614`
- `0x180047838`
- `0x180047b58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180047691`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180047691`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800476bc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800476bc`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18004776d`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18004776d`

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
    v7[0] = off_18005F950;
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
0x180047614  mov     [rsp+arg_8], rbx
0x180047619  mov     [rsp+arg_10], rsi
0x18004761e  push    rdi
0x18004761f  sub     rsp, 220h
0x180047626  mov     rax, cs:__security_cookie
0x18004762d  xor     rax, rsp
0x180047630  mov     [rsp+228h+var_18], rax
0x180047638  mov     rax, [rcx+8]
0x18004763c  mov     rdi, rcx
0x18004763f  inc     rax
0x180047642  test    rax, 0FFFFFFFFFFFFFFFEh
0x180047648  jnz     short loc_180047654
0x18004764a  mov     eax, 80070006h
0x18004764f  jmp     loc_180047781
0x180047654  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x18004765b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x180047660  test    al, al
0x180047662  jz      loc_18004771E
0x180047668  cmp     qword ptr [rdi+38h], 0
0x18004766d  jnz     short loc_1800476E7
0x18004766f  mov     ecx, 48h ; 'H'; Size
0x180047674  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180047679  xor     r8d, r8d; Flags
0x18004767c  mov     [rsp+228h+var_208], rax
0x180047681  xor     edx, edx; dwSpinCount
0x180047683  mov     rbx, rax
0x180047686  lea     rcx, [rax+8]; lpCriticalSection
0x18004768a  mov     qword ptr [rax], 0
0x180047691  call    cs:__imp_InitializeCriticalSectionEx
0x180047697  xor     r8d, r8d; pcbe
0x18004769a  mov     qword ptr [rbx+30h], 0
0x1800476a2  mov     rdx, rbx; pv
0x1800476a5  mov     qword ptr [rbx+38h], 0
0x1800476ad  lea     rcx, ?Callback@ThreadpoolWork@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800476b4  mov     qword ptr [rbx+40h], 0
0x1800476bc  call    cs:__imp_CreateThreadpoolWork
0x1800476c2  mov     [rbx], rax
0x1800476c5  mov     rsi, [rdi+38h]
0x1800476c9  mov     [rdi+38h], rbx
0x1800476cd  test    rsi, rsi
0x1800476d0  jz      short loc_1800476E7
0x1800476d2  mov     rcx, rsi; this
0x1800476d5  call    ??1ThreadpoolWork@@QEAA@XZ; ThreadpoolWork::~ThreadpoolWork(void)
0x1800476da  mov     edx, 48h ; 'H'
0x1800476df  mov     rcx, rsi; Block
0x1800476e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800476e7  lea     rbx, [rdi+30h]
0x1800476eb  mov     rax, [rbx]
0x1800476ee  test    rax, rax
0x1800476f1  jz      short loc_18004772F
0x1800476f3  lea     rcx, off_18005F950
0x1800476fa  mov     [rsp+228h+var_1F8], rax
0x1800476ff  mov     [rsp+228h+var_200], rcx
0x180047704  lea     rax, [rsp+228h+var_200]
0x180047709  mov     rcx, [rdi+38h]
0x18004770d  lea     rdx, [rsp+228h+var_200]
0x180047712  mov     [rsp+228h+var_1C8], rax
0x180047717  call    ?Submit@ThreadpoolWork@@QEAAXV?$function@$$A6AXXZ@std@@@Z; ThreadpoolWork::Submit(std::function<void (void)>)
0x18004771c  jmp     short loc_180047728
0x18004771e  lea     rbx, [rdi+30h]
0x180047722  cmp     qword ptr [rbx], 0
0x180047726  jz      short loc_18004772F
0x180047728  mov     qword ptr [rbx], 0
0x18004772f  mov     esi, 1A0h
0x180047734  lea     rcx, [rsp+228h+var_1B8]; void *
0x180047739  mov     r8d, esi; Size
0x18004773c  xor     edx, edx; Val
0x18004773e  call    memset_0
0x180047743  mov     rax, [rdi+8]
0x180047747  lea     r8, ?PnPCallback@KsHandleWrapper@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; KsHandleWrapper::PnPCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x18004774e  mov     r9, rbx
0x180047751  mov     [rsp+228h+var_1A8], rax
0x180047759  mov     rdx, rdi
0x18004775c  mov     [rsp+228h+var_1B8], esi
0x180047760  lea     rcx, [rsp+228h+var_1B8]
0x180047765  mov     [rsp+228h+var_1B0], 1
0x18004776d  call    cs:__imp_CM_Register_Notification
0x180047773  test    eax, eax
0x180047775  jz      short loc_180047781
0x180047777  jle     short loc_180047781
0x180047779  movzx   eax, ax
0x18004777c  or      eax, 80070000h
0x180047781  mov     rcx, [rsp+228h+var_18]
0x180047789  xor     rcx, rsp; StackCookie
0x18004778c  call    __security_check_cookie
0x180047791  lea     r11, [rsp+228h+var_8]
0x180047799  mov     rbx, [r11+18h]
0x18004779d  mov     rsi, [r11+20h]
0x1800477a1  mov     rsp, r11
0x1800477a4  pop     rdi
0x1800477a5  retn
```
