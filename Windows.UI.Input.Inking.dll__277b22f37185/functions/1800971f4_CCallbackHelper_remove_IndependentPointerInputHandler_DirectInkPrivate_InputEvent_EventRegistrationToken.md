# CCallbackHelper::remove_IndependentPointerInputHandler(DirectInkPrivate::InputEvent,EventRegistrationToken)

- ea: `0x1800971f4`
- end: `0x180097254`
- name: `?remove_IndependentPointerInputHandler@CCallbackHelper@@QEAAJW4InputEvent@DirectInkPrivate@@UEventRegistrationToken@@@Z`
- size: `96`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800915c0`
- `0x180091640`
- `0x1800916c0`
- `0x180091740`
- `0x1800917c0`
- `0x180091840`
- `0x1800918c0`

## callees

- `0x180032d4c`
- `0x18008b1e4`
- `0x180096704`
- `0x1800971f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097208`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097208`

## pseudocode

```c
__int64 __fastcall CCallbackHelper::remove_IndependentPointerInputHandler(
        CObjLifetime *a1,
        unsigned int a2,
        __int64 a3)
{
  int v3; // edi
  __int64 result; // rax
  __int64 v8; // rcx
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  v3 = *((_DWORD *)a1 + 4);
  if ( GetCurrentThreadId() != v3 )
    return 2147549454LL;
  result = CObjLifetime::CheckAlive(a1);
  if ( (int)result >= 0 )
  {
    v9 = 0;
    result = CCallbackHelper::_GetIndependentInputEventSource(v8, a2, &v9);
    if ( (int)result >= 0 )
      return Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
               v9,
               a3);
  }
  return result;
}

```

## disassembly

```asm
0x1800971f4  push    rbx
0x1800971f6  push    rbp
0x1800971f7  push    rsi
0x1800971f8  push    rdi
0x1800971f9  sub     rsp, 28h
0x1800971fd  mov     edi, [rcx+10h]
0x180097200  mov     rbx, r8
0x180097203  mov     ebp, edx
0x180097205  mov     rsi, rcx
0x180097208  call    cs:__imp_GetCurrentThreadId
0x18009720e  cmp     eax, edi
0x180097210  jnz     short loc_180097246
0x180097212  mov     rcx, rsi; this
0x180097215  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18009721a  test    eax, eax
0x18009721c  js      short loc_18009724B
0x18009721e  lea     r8, [rsp+48h+arg_0]
0x180097223  mov     [rsp+48h+arg_0], 0
0x18009722c  mov     edx, ebp
0x18009722e  call    ?_GetIndependentInputEventSource@CCallbackHelper@@IEAAJW4InputEvent@DirectInkPrivate@@PEAPEAV?$GitEventSource@U?$ITypedEventHandler@PEAVCoreInkIndependentInputSource@Core@Inking@Input@UI@Windows@@PEAVPointerEventArgs@256@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@Internal@Windows@@@Z; CCallbackHelper::_GetIndependentInputEventSource(DirectInkPrivate::InputEvent,Windows::Internal::GitEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreInkIndependentInputSource *,Windows::UI::Core::PointerEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> * *)
0x180097233  test    eax, eax
0x180097235  js      short loc_18009724B
0x180097237  mov     rcx, [rsp+48h+arg_0]
0x18009723c  mov     rdx, rbx
0x18009723f  call    ?Remove@?$EventSource@U?$ITypedEventHandler@PEAVCoreIncrementalInkStroke@Core@Inking@Input@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreIncrementalInkStroke *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)
0x180097244  jmp     short loc_18009724B
0x180097246  mov     eax, 8001010Eh
0x18009724b  add     rsp, 28h
0x18009724f  pop     rdi
0x180097250  pop     rsi
0x180097251  pop     rbp
0x180097252  pop     rbx
0x180097253  retn
```
