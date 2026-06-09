# CCallbackHelper::add_IndependentPointerInputHandler(Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreInkIndependentInputSource *,Windows::UI::Core::PointerEventArgs *> *,DirectInkPrivate::InputEvent,EventRegistrationToken *)

- ea: `0x180096f88`
- end: `0x180097069`
- name: `?add_IndependentPointerInputHandler@CCallbackHelper@@QEAAJPEAU?$ITypedEventHandler@PEAVCoreInkIndependentInputSource@Core@Inking@Input@UI@Windows@@PEAVPointerEventArgs@256@@Foundation@Windows@@W4InputEvent@DirectInkPrivate@@PEAUEventRegistrationToken@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(CObjLifetime *this)`
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180090ea0`
- `0x180090f60`
- `0x180091020`
- `0x1800910e0`
- `0x1800911a0`
- `0x180091260`
- `0x180091320`

## callees

- `0x1800101bc`
- `0x180026140`
- `0x18008b1e4`
- `0x180094104`
- `0x180096704`
- `0x180096f88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180096fa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180096fa9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCallbackHelper::add_IndependentPointerInputHandler(
        CObjLifetime *this,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  int v8; // ebx
  __int64 v9; // rcx
  int IndependentInputEventSource; // ebx
  _QWORD v12[5]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+50h] [rbp+8h] BYREF

  v8 = *((_DWORD *)this + 4);
  if ( GetCurrentThreadId() == v8 )
  {
    IndependentInputEventSource = CObjLifetime::CheckAlive(this);
    if ( IndependentInputEventSource >= 0 )
    {
      if ( a2 && a4 )
      {
        v12[0] = 0;
        IndependentInputEventSource = CCallbackHelper::_GetIndependentInputEventSource(v9, a3, v12);
        if ( IndependentInputEventSource >= 0 )
        {
          v13 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
          IndependentInputEventSource = Windows::Internal::Details::CreateGitHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreInkIndependentInputSource *,Windows::UI::Core::PointerEventArgs *>,Windows::Internal::GitPtr>(
                                          a2,
                                          &v13);
          if ( IndependentInputEventSource >= 0 )
          {
            if ( v13 )
              IndependentInputEventSource = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
                                              v12[0],
                                              v13,
                                              *(_QWORD *)(*(_QWORD *)a2 + 24LL),
                                              a4);
            else
              IndependentInputEventSource = -2147024809;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
        }
      }
      else
      {
        return (unsigned int)-2147467261;
      }
    }
  }
  else
  {
    return (unsigned int)-2147417842;
  }
  return (unsigned int)IndependentInputEventSource;
}

```

## disassembly

```asm
0x180096f88  mov     [rsp+arg_8], rbx
0x180096f8d  mov     [rsp+arg_10], rbp
0x180096f92  push    rsi
0x180096f93  push    rdi
0x180096f94  push    r14
0x180096f96  sub     rsp, 30h
0x180096f9a  mov     rbp, r9
0x180096f9d  mov     r14d, r8d
0x180096fa0  mov     rdi, rdx
0x180096fa3  mov     rsi, rcx
0x180096fa6  mov     ebx, [rcx+10h]
0x180096fa9  call    cs:__imp_GetCurrentThreadId
0x180096faf  cmp     eax, ebx
0x180096fb1  jnz     loc_18009704F
0x180096fb7  mov     rcx, rsi; this
0x180096fba  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x180096fbf  mov     ebx, eax
0x180096fc1  test    eax, eax
0x180096fc3  js      loc_180097054
0x180096fc9  test    rdi, rdi
0x180096fcc  jz      short loc_180097048
0x180096fce  test    rbp, rbp
0x180096fd1  jz      short loc_180097048
0x180096fd3  mov     [rsp+48h+var_28], 0
0x180096fdc  lea     r8, [rsp+48h+var_28]
0x180096fe1  mov     edx, r14d
0x180096fe4  call    ?_GetIndependentInputEventSource@CCallbackHelper@@IEAAJW4InputEvent@DirectInkPrivate@@PEAPEAV?$GitEventSource@U?$ITypedEventHandler@PEAVCoreInkIndependentInputSource@Core@Inking@Input@UI@Windows@@PEAVPointerEventArgs@256@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@Internal@Windows@@@Z; CCallbackHelper::_GetIndependentInputEventSource(DirectInkPrivate::InputEvent,Windows::Internal::GitEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreInkIndependentInputSource *,Windows::UI::Core::PointerEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> * *)
0x180096fe9  mov     ebx, eax
0x180096feb  test    eax, eax
0x180096fed  js      short loc_180097054
0x180096fef  mov     [rsp+48h+arg_0], 0
0x180096ff8  lea     rcx, [rsp+48h+arg_0]
0x180096ffd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180097002  lea     rdx, [rsp+48h+arg_0]
0x180097007  mov     rcx, rdi
0x18009700a  call    ??$CreateGitHelper@U?$ITypedEventHandler@PEAVCoreInkIndependentInputSource@Core@Inking@Input@UI@Windows@@PEAVPointerEventArgs@256@@Foundation@Windows@@VGitPtr@Internal@3@@Details@Internal@Windows@@YAJPEAU?$ITypedEventHandler@PEAVCoreInkIndependentInputSource@Core@Inking@Input@UI@Windows@@PEAVPointerEventArgs@256@@Foundation@2@PEAPEAU342@@Z; Windows::Internal::Details::CreateGitHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreInkIndependentInputSource *,Windows::UI::Core::PointerEventArgs *>,Windows::Internal::GitPtr>(Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreInkIndependentInputSource *,Windows::UI::Core::PointerEventArgs *> *,Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreInkIndependentInputSource *,Windows::UI::Core::PointerEventArgs *> * *)
0x18009700f  mov     ebx, eax
0x180097011  test    eax, eax
0x180097013  js      short loc_18009703C
0x180097015  mov     rdx, [rsp+48h+arg_0]
0x18009701a  test    rdx, rdx
0x18009701d  jnz     short loc_180097026
0x18009701f  mov     ebx, 80070057h
0x180097024  jmp     short loc_18009703C
0x180097026  mov     r8, [rdi]
0x180097029  mov     r9, rbp
0x18009702c  mov     r8, [r8+18h]
0x180097030  mov     rcx, [rsp+48h+var_28]
0x180097035  call    ?AddInternal@?$EventSource@U?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$ITypedEventHandler@PEAVCoreWetStrokeUpdateSource@Core@Inking@Input@UI@Windows@@PEAVCoreWetStrokeUpdateEventArgs@23456@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateSource *,Windows::UI::Input::Inking::Core::CoreWetStrokeUpdateEventArgs *> *,void *,EventRegistrationToken *)
0x18009703a  mov     ebx, eax
0x18009703c  lea     rcx, [rsp+48h+arg_0]
0x180097041  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180097046  jmp     short loc_180097054
0x180097048  mov     ebx, 80004003h
0x18009704d  jmp     short loc_180097054
0x18009704f  mov     ebx, 8001010Eh
0x180097054  mov     eax, ebx
0x180097056  mov     rbx, [rsp+48h+arg_8]
0x18009705b  mov     rbp, [rsp+48h+arg_10]
0x180097060  add     rsp, 30h
0x180097064  pop     r14
0x180097066  pop     rdi
0x180097067  pop     rsi
0x180097068  retn
```
