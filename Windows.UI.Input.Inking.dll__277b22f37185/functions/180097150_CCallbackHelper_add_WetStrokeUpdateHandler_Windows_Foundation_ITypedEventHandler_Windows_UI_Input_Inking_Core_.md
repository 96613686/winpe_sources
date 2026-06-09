# CCallbackHelper::add_WetStrokeUpdateHandler(Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *> *,DirectInkPrivate::InputEvent,bool,EventRegistrationToken *)

- ea: `0x180097150`
- end: `0x1800971ec`
- name: `?add_WetStrokeUpdateHandler@CCallbackHelper@@QEAAJPEAU?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@W4InputEvent@DirectInkPrivate@@_NPEAUEventRegistrationToken@@@Z`
- size: `156`
- prototype: `__int64 __usercall@<rax>(CObjLifetime *this@<rcx>, __int64)`
- caller_count: `10`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180091f50`
- `0x180091fd0`
- `0x180092050`
- `0x1800920d0`
- `0x180092150`
- `0x1800921d0`
- `0x180092250`
- `0x1800922d0`
- `0x180092350`
- `0x1800923d0`

## callees

- `0x18008b1e4`
- `0x1800950dc`
- `0x1800969f8`
- `0x180096ae0`
- `0x180097150`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097171`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097171`

## pseudocode

```c
__int64 __fastcall CCallbackHelper::add_WetStrokeUpdateHandler(
        CObjLifetime *this,
        __int64 a2,
        unsigned int a3,
        char a4,
        __int64 a5)
{
  int v5; // ebx
  __int64 result; // rax
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF

  v5 = *((_DWORD *)this + 4);
  if ( GetCurrentThreadId() != v5 )
    return 2147549454LL;
  result = CObjLifetime::CheckAlive(this);
  if ( (int)result >= 0 )
  {
    if ( a2 && (v12 = a5) != 0 )
    {
      v13 = 0;
      if ( a4 )
        result = CCallbackHelper::_GetWetStrokeUpdateEventSourcePrivate(v11, a3, &v13);
      else
        result = CCallbackHelper::_GetWetStrokeUpdateEventSource(v11, a3, &v13);
      if ( (int)result >= 0 )
        return Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(
                 v13,
                 a2,
                 v12);
    }
    else
    {
      return 2147500035LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180097150  mov     [rsp+arg_8], rbx
0x180097155  mov     [rsp+arg_10], rbp
0x18009715a  push    rsi
0x18009715b  push    rdi
0x18009715c  push    r14
0x18009715e  sub     rsp, 20h
0x180097162  mov     ebx, [rcx+10h]
0x180097165  mov     r14b, r9b
0x180097168  mov     ebp, r8d
0x18009716b  mov     rdi, rdx
0x18009716e  mov     rsi, rcx
0x180097171  call    cs:__imp_GetCurrentThreadId
0x180097177  cmp     eax, ebx
0x180097179  jnz     short loc_1800971D4
0x18009717b  mov     rcx, rsi; this
0x18009717e  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x180097183  test    eax, eax
0x180097185  js      short loc_1800971D9
0x180097187  test    rdi, rdi
0x18009718a  jz      short loc_1800971CD
0x18009718c  mov     rbx, [rsp+38h+arg_20]
0x180097191  test    rbx, rbx
0x180097194  jz      short loc_1800971CD
0x180097196  mov     [rsp+38h+arg_0], 0
0x18009719f  lea     r8, [rsp+38h+arg_0]
0x1800971a4  mov     edx, ebp
0x1800971a6  test    r14b, r14b
0x1800971a9  jz      short loc_1800971C6
0x1800971ab  call    ?_GetWetStrokeUpdateEventSourcePrivate@CCallbackHelper@@IEAAJW4InputEvent@DirectInkPrivate@@PEAPEAV?$AgileEventSource@U?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@@Z; CCallbackHelper::_GetWetStrokeUpdateEventSourcePrivate(DirectInkPrivate::InputEvent,Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> * *)
0x1800971b0  test    eax, eax
0x1800971b2  js      short loc_1800971D9
0x1800971b4  mov     rcx, [rsp+38h+arg_0]
0x1800971b9  mov     r8, rbx
0x1800971bc  mov     rdx, rdi
0x1800971bf  call    ?Add@?$AgileEventSource@U?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAU?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z; Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *> *,EventRegistrationToken *)
0x1800971c4  jmp     short loc_1800971D9
0x1800971c6  call    ?_GetWetStrokeUpdateEventSource@CCallbackHelper@@IEAAJW4InputEvent@DirectInkPrivate@@PEAPEAV?$AgileEventSource@U?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@@Z; CCallbackHelper::_GetWetStrokeUpdateEventSource(DirectInkPrivate::InputEvent,Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> * *)
0x1800971cb  jmp     short loc_1800971B0
0x1800971cd  mov     eax, 80004003h
0x1800971d2  jmp     short loc_1800971D9
0x1800971d4  mov     eax, 8001010Eh
0x1800971d9  mov     rbx, [rsp+38h+arg_8]
0x1800971de  mov     rbp, [rsp+38h+arg_10]
0x1800971e3  add     rsp, 20h
0x1800971e7  pop     r14
0x1800971e9  pop     rdi
0x1800971ea  pop     rsi
0x1800971eb  retn
```
