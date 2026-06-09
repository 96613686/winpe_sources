# BackgroundExecutionSessionClient::~BackgroundExecutionSessionClient(void)

- ea: `0x180003110`
- end: `0x18000324a`
- name: `??1BackgroundExecutionSessionClient@@UEAA@XZ`
- size: `314`
- prototype: `void __fastcall(BackgroundExecutionSessionClient *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800030d0`

## callees

- `0x180003110`
- `0x18000437c`
- `0x180006010`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000314f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000314f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003193`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003193`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800031a0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800031a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000317a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000317a`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000321c`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000321c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180003162`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180003162`

## pseudocode

```c
void __fastcall BackgroundExecutionSessionClient::~BackgroundExecutionSessionClient(
        BackgroundExecutionSessionClient *this)
{
  DWORD CurrentThreadId; // eax
  __int64 v3; // rcx
  int v4; // eax
  _QWORD **v5; // rsi
  _QWORD *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  _QWORD *v11; // rax

  *(_QWORD *)this = &BackgroundExecutionSessionClient::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IInspectable>'};
  *((_QWORD *)this + 5) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 6) = &BackgroundExecutionSessionClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'};
  if ( *((_QWORD *)this + 11) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v3 = *((_QWORD *)this + 11);
    v4 = *((_DWORD *)this + 24) == CurrentThreadId
       ? RtlUnsubscribeWnfStateChangeNotification(v3)
       : RtlUnsubscribeWnfNotificationWaitForCompletion(v3);
    if ( v4 >= 0 )
      *((_QWORD *)this + 11) = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v5 = (_QWORD **)((char *)this + 120);
  while ( 1 )
  {
    v6 = *v5;
    if ( *v5 == v5 )
      break;
    if ( (_QWORD **)v6[1] != v5 || (v11 = (_QWORD *)*v6, *(_QWORD **)(*v6 + 8LL) != v6) )
      __fastfail(3u);
    *v5 = v11;
    v11[1] = v5;
    operator delete(v6);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v7 = *((_QWORD *)this + 14);
  if ( v7 )
  {
    *((_QWORD *)this + 14) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v8 = *((_QWORD *)this + 13);
  if ( v8 )
  {
    *((_QWORD *)this + 13) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = *((_QWORD *)this + 8);
  if ( v9 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(2 * v9);
  v10 = *((_QWORD *)this + 4);
  if ( v10 )
  {
    *((_QWORD *)this + 4) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
}

```

## disassembly

```asm
0x180003110  push    rbx
0x180003112  push    rbp
0x180003113  push    rsi
0x180003114  push    rdi
0x180003115  sub     rsp, 28h
0x180003119  lea     rax, ??_7BackgroundExecutionSessionClient@@6BIInspectable@@@; const BackgroundExecutionSessionClient::`vftable'{for `IInspectable'}
0x180003120  xor     ebp, ebp
0x180003122  mov     rbx, rcx
0x180003125  mov     [rcx], rax
0x180003128  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIInspectable@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@UIInspectable@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IInspectable>'}
0x18000312f  mov     [rcx+8], rax
0x180003133  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIInspectable@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `IWeakReferenceSource'}
0x18000313a  mov     [rcx+28h], rax
0x18000313e  lea     rax, ??_7BackgroundExecutionSessionClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIInspectable@@@Details@WRL@Microsoft@@@; const BackgroundExecutionSessionClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'}
0x180003145  mov     [rcx+30h], rax
0x180003149  cmp     [rcx+58h], rbp
0x18000314d  jz      short loc_180003173
0x18000314f  call    cs:__imp_GetCurrentThreadId
0x180003155  mov     rcx, [rbx+58h]
0x180003159  cmp     [rbx+60h], eax
0x18000315c  jz      loc_18000321C
0x180003162  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180003168  or      eax, 10000000h
0x18000316d  jge     loc_180003213
0x180003173  lea     rcx, [rbx+88h]; lpCriticalSection
0x18000317a  call    cs:__imp_EnterCriticalSection
0x180003180  lea     rsi, [rbx+78h]
0x180003184  mov     rcx, [rsi]; Block
0x180003187  cmp     rcx, rsi
0x18000318a  jnz     short loc_1800031F3
0x18000318c  lea     rcx, [rbx+88h]; lpCriticalSection
0x180003193  call    cs:__imp_LeaveCriticalSection
0x180003199  lea     rcx, [rbx+88h]; lpCriticalSection
0x1800031a0  call    cs:__imp_DeleteCriticalSection
0x1800031a6  mov     rcx, [rbx+70h]
0x1800031aa  test    rcx, rcx
0x1800031ad  jz      short loc_1800031BF
0x1800031af  mov     [rbx+70h], rbp
0x1800031b3  mov     rax, [rcx]
0x1800031b6  mov     rax, [rax+10h]
0x1800031ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031bf  mov     rcx, [rbx+68h]
0x1800031c3  test    rcx, rcx
0x1800031c6  jnz     short loc_18000322E
0x1800031c8  mov     rcx, [rbx+40h]
0x1800031cc  test    rcx, rcx
0x1800031cf  js      short loc_180003240
0x1800031d1  mov     rcx, [rbx+20h]
0x1800031d5  test    rcx, rcx
0x1800031d8  jz      short loc_1800031EA
0x1800031da  mov     [rbx+20h], rbp
0x1800031de  mov     rax, [rcx]
0x1800031e1  mov     rax, [rax+10h]
0x1800031e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ea  add     rsp, 28h
0x1800031ee  pop     rdi
0x1800031ef  pop     rsi
0x1800031f0  pop     rbp
0x1800031f1  pop     rbx
0x1800031f2  retn
0x1800031f3  cmp     [rcx+8], rsi
0x1800031f7  jnz     short loc_180003227
0x1800031f9  mov     rax, [rcx]
0x1800031fc  cmp     [rax+8], rcx
0x180003200  jnz     short loc_180003227
0x180003202  mov     [rsi], rax
0x180003205  mov     [rax+8], rsi
0x180003209  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000320e  jmp     loc_180003184
0x180003213  mov     [rbx+58h], rbp
0x180003217  jmp     loc_180003173
0x18000321c  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x180003222  jmp     loc_180003168
0x180003227  mov     ecx, 3
0x18000322c  int     29h; Win8: RtlFailFast(ecx)
0x18000322e  mov     [rbx+68h], rbp
0x180003232  mov     rax, [rcx]
0x180003235  mov     rax, [rax+10h]
0x180003239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000323e  jmp     short loc_1800031C8
0x180003240  add     rcx, rcx
0x180003243  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x180003248  jmp     short loc_1800031D1
```
