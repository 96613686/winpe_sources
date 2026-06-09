# CCallbackHelper::remove_WetStrokeUpdateHandler(DirectInkPrivate::InputEvent,bool,EventRegistrationToken)

- ea: `0x1800972e4`
- end: `0x180097366`
- name: `?remove_WetStrokeUpdateHandler@CCallbackHelper@@QEAAJW4InputEvent@DirectInkPrivate@@_NUEventRegistrationToken@@@Z`
- size: `130`
- prototype: ``
- caller_count: `10`
- callee_count: `5`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180092470`
- `0x1800924a0`
- `0x1800924d0`
- `0x180092500`
- `0x180092530`
- `0x180092560`
- `0x180092590`
- `0x1800925c0`
- `0x1800925f0`
- `0x180092620`

## callees

- `0x180032d4c`
- `0x18008b1e4`
- `0x1800969f8`
- `0x180096ae0`
- `0x1800972e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097304`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097304`

## pseudocode

```c
__int64 __fastcall CCallbackHelper::remove_WetStrokeUpdateHandler(
        CObjLifetime *a1,
        unsigned int a2,
        char a3,
        __int64 a4)
{
  int v4; // edi
  __int64 result; // rax
  __int64 v10; // rcx
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF

  v4 = *((_DWORD *)a1 + 4);
  if ( GetCurrentThreadId() != v4 )
    return 2147549454LL;
  result = CObjLifetime::CheckAlive(a1);
  if ( (int)result >= 0 )
  {
    v11 = 0;
    if ( a3 )
      result = CCallbackHelper::_GetWetStrokeUpdateEventSourcePrivate(v10, a2, &v11);
    else
      result = CCallbackHelper::_GetWetStrokeUpdateEventSource(v10, a2, &v11);
    if ( (int)result >= 0 )
      return Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
               v11,
               a4);
  }
  return result;
}

```

## disassembly

```asm
0x1800972e4  mov     [rsp+arg_8], rbx
0x1800972e9  mov     [rsp+arg_10], rbp
0x1800972ee  push    rsi
0x1800972ef  push    rdi
0x1800972f0  push    r14
0x1800972f2  sub     rsp, 20h
0x1800972f6  mov     edi, [rcx+10h]
0x1800972f9  mov     rbx, r9
0x1800972fc  mov     r14b, r8b
0x1800972ff  mov     ebp, edx
0x180097301  mov     rsi, rcx
0x180097304  call    cs:__imp_GetCurrentThreadId
0x18009730a  cmp     eax, edi
0x18009730c  jnz     short loc_18009734E
0x18009730e  mov     rcx, rsi; this
0x180097311  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x180097316  test    eax, eax
0x180097318  js      short loc_180097353
0x18009731a  mov     [rsp+38h+arg_0], 0
0x180097323  lea     r8, [rsp+38h+arg_0]
0x180097328  mov     edx, ebp
0x18009732a  test    r14b, r14b
0x18009732d  jz      short loc_180097347
0x18009732f  call    ?_GetWetStrokeUpdateEventSourcePrivate@CCallbackHelper@@IEAAJW4InputEvent@DirectInkPrivate@@PEAPEAV?$AgileEventSource@U?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@@Z; CCallbackHelper::_GetWetStrokeUpdateEventSourcePrivate(DirectInkPrivate::InputEvent,Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> * *)
0x180097334  test    eax, eax
0x180097336  js      short loc_180097353
0x180097338  mov     rcx, [rsp+38h+arg_0]
0x18009733d  mov     rdx, rbx
0x180097340  call    ?Remove@?$EventSource@U?$ITypedEventHandler@PEAVCoreIncrementalInkStroke@Core@Inking@Input@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)
0x180097345  jmp     short loc_180097353
0x180097347  call    ?_GetWetStrokeUpdateEventSource@CCallbackHelper@@IEAAJW4InputEvent@DirectInkPrivate@@PEAPEAV?$AgileEventSource@U?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@@Z; CCallbackHelper::_GetWetStrokeUpdateEventSource(DirectInkPrivate::InputEvent,Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> * *)
0x18009734c  jmp     short loc_180097334
0x18009734e  mov     eax, 8001010Eh
0x180097353  mov     rbx, [rsp+38h+arg_8]
0x180097358  mov     rbp, [rsp+38h+arg_10]
0x18009735d  add     rsp, 20h
0x180097361  pop     r14
0x180097363  pop     rdi
0x180097364  pop     rsi
0x180097365  retn
```
