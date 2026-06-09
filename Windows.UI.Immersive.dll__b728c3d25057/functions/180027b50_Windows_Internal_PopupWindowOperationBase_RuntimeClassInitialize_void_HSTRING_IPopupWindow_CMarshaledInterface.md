# Windows::Internal::PopupWindowOperationBase::RuntimeClassInitialize(void *,HSTRING__ *,IPopupWindow *,CMarshaledInterface,uint,uint,uint,CMarshaledInterface,bool)

- ea: `0x180027b50`
- end: `0x180027d94`
- name: `?RuntimeClassInitialize@PopupWindowOperationBase@Internal@Windows@@QEAAJPEAXPEAUHSTRING__@@PEAUIPopupWindow@@VCMarshaledInterface@@III3_N@Z`
- size: `580`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003bd40`
- `0x18004bc5c`

## callees

- `0x180013244`
- `0x180027b50`
- `0x180027d9c`
- `0x1800387c8`
- `0x18003aa84`
- `0x18003f64c`
- `0x180046508`
- `0x180083c8c`
- `0x180087f80`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180027c7d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180027c7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180027baf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180027baf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027bcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027bcf`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180027cae`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180027cae`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::PopupWindowOperationBase::RuntimeClassInitialize(
        __int64 a1,
        __int64 a2,
        HSTRING a3,
        HSTRING a4,
        __int64 a5,
        int a6,
        unsigned int a7,
        unsigned int a8,
        CMarshaledInterface *a9,
        bool a10)
{
  HRESULT v13; // ebx
  CMarshaledInterface *v14; // r14
  HSTRING v15; // rcx
  HANDLE Event; // rbx
  int Error; // eax
  __int128 v19; // [rsp+20h] [rbp-10h] BYREF
  HSTRING newString; // [rsp+50h] [rbp+20h] BYREF
  __int64 v21; // [rsp+58h] [rbp+28h] BYREF

  *(_QWORD *)(a1 + 88) = a2;
  if ( *(HSTRING *)(a1 + 32) != a4 )
  {
    newString = a4;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&newString);
    newString = *(HSTRING *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = a4;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&newString);
  }
  *(_DWORD *)(a1 + 76) = a6;
  newString = 0;
  v13 = WindowsDuplicateString(a3, &newString);
  v14 = a9;
  if ( v13 >= 0 )
  {
    v15 = *(HSTRING *)(a1 + 40);
    *(_QWORD *)(a1 + 40) = newString;
    WindowsDeleteString(v15);
    v13 = CMarshaledInterface::Unmarshal<Windows::Foundation::Collections::IVector<Windows::UI::Popups::IUICommand *>>(
            a5,
            a1 + 56);
    if ( v13 >= 0 )
    {
      if ( !*(_QWORD *)v14
        || (Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(a1 + 64),
            v13 = CMarshaledInterface::_Unmarshal(
                    v14,
                    &GUID_daf77a4f_c27a_4298_9ac6_2922c45e7da6,
                    (void **)(a1 + 64),
                    0),
            v13 >= 0) )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 32) + 120LL))(*(_QWORD *)(a1 + 32), a8);
        if ( v13 >= 0 )
        {
          v13 = Windows::Internal::PopupWindowOperationBase::_AdjustButtons(
                  (Windows::Internal::PopupWindowOperationBase *)a1,
                  *(struct IPopupWindow **)(a1 + 32),
                  a10);
          if ( v13 >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 32) + 88LL))(*(_QWORD *)(a1 + 32), a7);
            if ( v13 >= 0 )
            {
              Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
              CAutoHandle<void *>::~CAutoHandle<void *>(a1 + 80);
              *(_QWORD *)(a1 + 80) = Event;
              if ( (((unsigned __int64)Event + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
                || (Error = ResultFromKnownLastError(), v13 = Error, Error >= 0) )
              {
                *(_QWORD *)&v19 =  Windows::Internal::PopupWindowOperationBase::`vcall'{24,{flat}};
                DWORD2(v19) = 0;
                Microsoft::WRL::Callback<IPopupEventHandler,Windows::Internal::PopupWindowOperationBase,IPopupWindow *>(
                  &v21,
                  a1,
                  &v19);
                if ( v21 )
                {
                  v13 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 168LL))(*(_QWORD *)(a1 + 32));
                  if ( v13 >= 0 )
                  {
                    *(_QWORD *)&v19 =  Windows::Internal::PopupWindowOperationBase::`vcall'{32,{flat}};
                    DWORD2(v19) = 0;
                    Microsoft::WRL::Callback<IPopupEventHandler,Windows::Internal::PopupWindowOperationBase,IPopupWindow *>(
                      &newString,
                      a1,
                      &v19);
                    if ( newString )
                      v13 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 320LL))(*(_QWORD *)(a1 + 32));
                    else
                      v13 = -2147024882;
                    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&newString);
                  }
                }
                else
                {
                  v13 = -2147024882;
                }
                Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v21);
              }
              else
              {
                RoOriginateError((unsigned int)Error, 0);
              }
            }
          }
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(a5);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v14);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180027b50  mov     [rsp-18h+arg_10], rbx
0x180027b55  mov     [rsp-18h+arg_18], rsi
0x180027b5a  push    rbp
0x180027b5b  push    rdi
0x180027b5c  push    r14
0x180027b5e  mov     rbp, rsp
0x180027b61  sub     rsp, 30h
0x180027b65  mov     rbx, r9
0x180027b68  mov     rdi, r8
0x180027b6b  mov     rsi, rcx
0x180027b6e  mov     [rcx+58h], rdx
0x180027b72  cmp     [rcx+20h], r9
0x180027b76  jz      short loc_180027B9A
0x180027b78  mov     [rbp+newString], rbx
0x180027b7c  lea     rcx, [rbp+newString]
0x180027b80  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180027b85  mov     rax, [rsi+20h]
0x180027b89  mov     [rbp+newString], rax
0x180027b8d  mov     [rsi+20h], rbx
0x180027b91  lea     rcx, [rbp+newString]
0x180027b95  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180027b9a  mov     eax, [rbp+arg_28]
0x180027b9d  mov     [rsi+4Ch], eax
0x180027ba0  mov     [rbp+newString], 0
0x180027ba8  lea     rdx, [rbp+newString]; newString
0x180027bac  mov     rcx, rdi; string
0x180027baf  call    cs:__imp_WindowsDuplicateString
0x180027bb5  mov     ebx, eax
0x180027bb7  mov     r14, [rbp+arg_40]
0x180027bbb  test    eax, eax
0x180027bbd  js      loc_180027D6D
0x180027bc3  mov     rcx, [rsi+28h]; string
0x180027bc7  mov     rax, [rbp+newString]
0x180027bcb  mov     [rsi+28h], rax
0x180027bcf  call    cs:__imp_WindowsDeleteString
0x180027bd5  lea     rdx, [rsi+38h]
0x180027bd9  mov     rcx, [rbp+arg_20]
0x180027bdd  call    ??$Unmarshal@U?$IVector@PEAUIUICommand@Popups@UI@Windows@@@Collections@Foundation@Windows@@@CMarshaledInterface@@QEAAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIUICommand@Popups@UI@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; CMarshaledInterface::Unmarshal<Windows::Foundation::Collections::IVector<Windows::UI::Popups::IUICommand *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::UI::Popups::IUICommand *>>>)
0x180027be2  mov     ebx, eax
0x180027be4  test    eax, eax
0x180027be6  js      loc_180027D6D
0x180027bec  cmp     qword ptr [r14], 0
0x180027bf0  jz      short loc_180027C1B
0x180027bf2  lea     rcx, [rsi+40h]
0x180027bf6  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180027bfb  xor     r9d, r9d; bool
0x180027bfe  lea     r8, [rsi+40h]; void **
0x180027c02  lea     rdx, _GUID_daf77a4f_c27a_4298_9ac6_2922c45e7da6; struct _GUID *
0x180027c09  mov     rcx, r14; this
0x180027c0c  call    ?_Unmarshal@CMarshaledInterface@@AEAAJAEBU_GUID@@PEAPEAX_N@Z; CMarshaledInterface::_Unmarshal(_GUID const &,void * *,bool)
0x180027c11  mov     ebx, eax
0x180027c13  test    eax, eax
0x180027c15  js      loc_180027D6D
0x180027c1b  mov     rcx, [rsi+20h]
0x180027c1f  mov     rax, [rcx]
0x180027c22  mov     edx, [rbp+arg_38]
0x180027c25  mov     rax, [rax+78h]
0x180027c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c2e  mov     ebx, eax
0x180027c30  test    eax, eax
0x180027c32  js      loc_180027D6D
0x180027c38  mov     r8b, [rbp+arg_48]; bool
0x180027c3c  mov     rdx, [rsi+20h]; struct IPopupWindow *
0x180027c40  mov     rcx, rsi; this
0x180027c43  call    ?_AdjustButtons@PopupWindowOperationBase@Internal@Windows@@AEAAJPEAUIPopupWindow@@_N@Z; Windows::Internal::PopupWindowOperationBase::_AdjustButtons(IPopupWindow *,bool)
0x180027c48  mov     ebx, eax
0x180027c4a  test    eax, eax
0x180027c4c  js      loc_180027D6D
0x180027c52  mov     rcx, [rsi+20h]
0x180027c56  mov     rax, [rcx]
0x180027c59  mov     edx, [rbp+arg_30]
0x180027c5c  mov     rax, [rax+58h]
0x180027c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c65  mov     ebx, eax
0x180027c67  test    eax, eax
0x180027c69  js      loc_180027D6D
0x180027c6f  xor     edx, edx; lpName
0x180027c71  xor     ecx, ecx; lpEventAttributes
0x180027c73  mov     r9d, 1F0003h; dwDesiredAccess
0x180027c79  lea     r8d, [rdx+1]; dwFlags
0x180027c7d  call    cs:__imp_CreateEventExW
0x180027c83  mov     rbx, rax
0x180027c86  lea     rcx, [rsi+50h]
0x180027c8a  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x180027c8f  mov     [rsi+50h], rbx
0x180027c93  lea     rax, [rbx+1]
0x180027c97  test    rax, 0FFFFFFFFFFFFFFFEh
0x180027c9d  jnz     short loc_180027CB9
0x180027c9f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180027ca4  mov     ebx, eax
0x180027ca6  test    eax, eax
0x180027ca8  jns     short loc_180027CB9
0x180027caa  xor     edx, edx
0x180027cac  mov     ecx, eax
0x180027cae  call    cs:__imp_RoOriginateError
0x180027cb4  jmp     loc_180027D6D
0x180027cb9  lea     rax, ??_9PopupWindowOperationBase@Internal@Windows@@$BBI@AA; [thunk]: Windows::Internal::PopupWindowOperationBase::`vcall'{24,{flat}}
0x180027cc0  mov     [rbp+var_10], rax
0x180027cc4  mov     [rbp+var_8], 0
0x180027ccb  mov     eax, [rbp+var_4]
0x180027cce  mov     [rbp+var_4], eax
0x180027cd1  lea     r8, [rbp+var_10]
0x180027cd5  mov     rdx, rsi
0x180027cd8  lea     rcx, [rbp+arg_8]
0x180027cdc  call    ??$Callback@UIPopupEventHandler@@VPopupWindowOperationBase@Internal@Windows@@PEAUIPopupWindow@@@WRL@Microsoft@@YA?AV?$ComPtr@UIPopupEventHandler@@@01@PEAVPopupWindowOperationBase@Internal@Windows@@P8345@EAAJPEAUIPopupWindow@@@Z@Z; Microsoft::WRL::Callback<IPopupEventHandler,Windows::Internal::PopupWindowOperationBase,IPopupWindow *>(Windows::Internal::PopupWindowOperationBase *,long (Windows::Internal::PopupWindowOperationBase::*)(IPopupWindow *))
0x180027ce1  nop
0x180027ce2  mov     rdx, [rbp+arg_8]
0x180027ce6  test    rdx, rdx
0x180027ce9  jnz     short loc_180027CF2
0x180027ceb  mov     ebx, 8007000Eh
0x180027cf0  jmp     short loc_180027D63
0x180027cf2  mov     rcx, [rsi+20h]
0x180027cf6  mov     rax, [rcx]
0x180027cf9  mov     rax, [rax+0A8h]
0x180027d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d05  mov     ebx, eax
0x180027d07  test    eax, eax
0x180027d09  js      short loc_180027D63
0x180027d0b  lea     rax, ??_9PopupWindowOperationBase@Internal@Windows@@$BCA@AA; [thunk]: Windows::Internal::PopupWindowOperationBase::`vcall'{32,{flat}}
0x180027d12  mov     [rbp+var_10], rax
0x180027d16  mov     [rbp+var_8], 0
0x180027d1d  mov     eax, [rbp+var_4]
0x180027d20  mov     [rbp+var_4], eax
0x180027d23  lea     r8, [rbp+var_10]
0x180027d27  mov     rdx, rsi
0x180027d2a  lea     rcx, [rbp+newString]
0x180027d2e  call    ??$Callback@UIPopupEventHandler@@VPopupWindowOperationBase@Internal@Windows@@PEAUIPopupWindow@@@WRL@Microsoft@@YA?AV?$ComPtr@UIPopupEventHandler@@@01@PEAVPopupWindowOperationBase@Internal@Windows@@P8345@EAAJPEAUIPopupWindow@@@Z@Z; Microsoft::WRL::Callback<IPopupEventHandler,Windows::Internal::PopupWindowOperationBase,IPopupWindow *>(Windows::Internal::PopupWindowOperationBase *,long (Windows::Internal::PopupWindowOperationBase::*)(IPopupWindow *))
0x180027d33  nop
0x180027d34  mov     rdx, [rbp+newString]
0x180027d38  test    rdx, rdx
0x180027d3b  jnz     short loc_180027D44
0x180027d3d  mov     ebx, 8007000Eh
0x180027d42  jmp     short loc_180027D59
0x180027d44  mov     rcx, [rsi+20h]
0x180027d48  mov     rax, [rcx]
0x180027d4b  mov     rax, [rax+140h]
0x180027d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d57  mov     ebx, eax
0x180027d59  lea     rcx, [rbp+newString]
0x180027d5d  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180027d62  nop
0x180027d63  lea     rcx, [rbp+arg_8]
0x180027d67  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180027d6c  nop
0x180027d6d  mov     rcx, [rbp+arg_20]
0x180027d71  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180027d76  nop
0x180027d77  mov     rcx, r14
0x180027d7a  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180027d7f  mov     eax, ebx
0x180027d81  mov     rbx, [rsp+30h+arg_10]
0x180027d86  mov     rsi, [rsp+30h+arg_18]
0x180027d8b  add     rsp, 30h
0x180027d8f  pop     r14
0x180027d91  pop     rdi
0x180027d92  pop     rbp
0x180027d93  retn
```
