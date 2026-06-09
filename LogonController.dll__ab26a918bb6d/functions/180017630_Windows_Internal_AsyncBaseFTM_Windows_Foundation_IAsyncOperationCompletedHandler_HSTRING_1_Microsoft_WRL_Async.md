# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180017630`
- end: `0x180017867`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `567`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000cd1c`
- `0x18000df10`
- `0x180015920`
- `0x180017204`
- `0x1800172fc`
- `0x1800173d0`
- `0x180017630`
- `0x180017d80`
- `0x180017dec`
- `0x180028d84`
- `0x18002a228`
- `0x180064d94`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18001785c`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18001785c`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180017805`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180017805`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180017831`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180017831`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  signed __int32 v1; // edx
  unsigned int v2; // esi
  int (__fastcall *v5)(__int64, GUID *, LPUNKNOWN *); // rbx
  signed __int32 v6; // ecx
  bool v7; // dl
  unsigned int v8; // eax
  struct IUnknown *v9; // rcx
  IUnknown *v10; // rbx
  __int64 v11; // [rsp+30h] [rbp-28h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-20h] BYREF
  HRESULT v13; // [rsp+40h] [rbp-18h]
  unsigned int v14; // [rsp+90h] [rbp+38h] BYREF
  struct IUnknown *v15; // [rsp+98h] [rbp+40h] BYREF
  LPUNKNOWN pUnk; // [rsp+A0h] [rbp+48h] BYREF
  struct IRpcOptions *v17; // [rsp+A8h] [rbp+50h] BYREF

  v1 = *(_DWORD *)(a1 + 56);
  v14 = -2;
  v2 = 0;
  _InterlockedCompareExchange((volatile signed __int32 *)&v14, v1, -2);
  if ( !v14 )
    _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), 1, 0);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedIncrement((volatile signed __int32 *)(a1 + 16)) == 1 )
  {
    v11 = a1;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v11);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const FSIAAsyncAction,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    v5 = **(int (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))a1;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&pUnk);
    if ( v5(a1, &GUID_3e1fe603_f897_5263_b328_0806426b8a79, &pUnk) >= 0 )
    {
      v6 = *(_DWORD *)(a1 + 56);
      v14 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v14, v6, -2);
      v15 = 0;
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v15);
      if ( *(_QWORD *)(a1 + 120) )
      {
        if ( (int)Microsoft::WRL::AgileRef::CopyTo(
                    (Microsoft::WRL::AgileRef *)(a1 + 120),
                    &GUID_b79a741f_7fb5_50ae_9e99_911201ec3d41,
                    &v15) >= 0 )
        {
          Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const c_WebDialogAsyncAction,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
          v17 = 0;
          Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v17);
          RpcOptionsHelper::GetRpcOptions(v15, v7, &v17);
          ppstm = 0;
          v13 = 0;
          if ( v17 && v15 )
          {
            v10 = pUnk;
            Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&ppstm);
            v13 = CreateStreamOnHGlobal(0, 1, &ppstm);
            if ( v13 >= 0 )
              v13 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v10, 0, 0, 1u);
          }
          else
          {
            v13 = -2147467262;
          }
          v8 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v15->lpVtbl[1].QueryInterface)(
                 v15,
                 pUnk,
                 v14);
          v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
                 v8,
                 v15,
                 *(_QWORD *)(a1 + 128));
          Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
          Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const c_WebDialogAsyncAction,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
          if ( v13 >= 0 )
          {
            (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
            CoReleaseMarshalData(ppstm);
          }
          Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&ppstm);
          Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v17);
        }
        v9 = v15;
      }
      else
      {
        v9 = 0;
      }
      if ( v9 )
      {
        v15 = 0;
        ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->Release)(v9);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  }
  return v2;
}

```

## disassembly

```asm
0x180017630  push    rbp
0x180017632  push    rbx
0x180017633  push    rsi
0x180017634  push    rdi
0x180017635  push    r14
0x180017637  push    r15
0x180017639  mov     rbp, rsp
0x18001763c  sub     rsp, 58h
0x180017640  mov     edx, [rcx+38h]
0x180017643  xor     r14d, r14d
0x180017646  mov     [rbp+arg_0], 0FFFFFFFEh
0x18001764d  mov     esi, r14d
0x180017650  mov     eax, [rbp+arg_0]
0x180017653  mov     rdi, rcx
0x180017656  lock cmpxchg [rbp+arg_0], edx
0x18001765b  lea     r15d, [r14+1]
0x18001765f  cmp     [rbp+arg_0], r14d
0x180017663  jnz     short loc_18001766D
0x180017665  xor     eax, eax
0x180017667  lock cmpxchg [rcx+38h], r15d
0x18001766d  cmp     [rcx+88h], r14d
0x180017674  jle     short loc_180017686
0x180017676  mov     eax, r15d
0x180017679  lock xadd [rcx+10h], eax
0x18001767e  add     eax, r15d
0x180017681  cmp     eax, r15d
0x180017684  jz      short loc_180017695
0x180017686  mov     eax, esi
0x180017688  add     rsp, 58h
0x18001768c  pop     r15
0x18001768e  pop     r14
0x180017690  pop     rdi
0x180017691  pop     rsi
0x180017692  pop     rbx
0x180017693  pop     rbp
0x180017694  retn
0x180017695  lea     rcx, [rbp+var_28]
0x180017699  mov     [rbp+var_28], rdi
0x18001769d  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800176a2  mov     rcx, rdi
0x1800176a5  mov     [rbp+pUnk], r14
0x1800176a9  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?FSIAAsyncAction@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const FSIAAsyncAction,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x1800176ae  mov     rax, [rdi]
0x1800176b1  lea     rcx, [rbp+pUnk]
0x1800176b5  mov     rbx, [rax]
0x1800176b8  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800176bd  lea     r8, [rbp+pUnk]
0x1800176c1  mov     rcx, rdi
0x1800176c4  lea     rdx, _GUID_3e1fe603_f897_5263_b328_0806426b8a79
0x1800176cb  mov     rax, rbx
0x1800176ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176d3  test    eax, eax
0x1800176d5  js      loc_1800177C9
0x1800176db  mov     ecx, [rdi+38h]
0x1800176de  mov     [rbp+arg_0], 0FFFFFFFEh
0x1800176e5  mov     eax, [rbp+arg_0]
0x1800176e8  lock cmpxchg [rbp+arg_0], ecx
0x1800176ed  lea     rcx, [rbp+arg_8]
0x1800176f1  mov     [rbp+arg_8], r14
0x1800176f5  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1800176fa  cmp     [rdi+78h], r14
0x1800176fe  jz      loc_1800177E0
0x180017704  lea     r8, [rbp+arg_8]; struct IUnknown **
0x180017708  lea     rdx, _GUID_b79a741f_7fb5_50ae_9e99_911201ec3d41; struct _GUID *
0x18001770f  lea     rcx, [rdi+78h]; this
0x180017713  call    ?CopyTo@AgileRef@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; Microsoft::WRL::AgileRef::CopyTo(_GUID const &,IUnknown * *)
0x180017718  test    eax, eax
0x18001771a  js      loc_1800177B0
0x180017720  mov     rcx, rdi
0x180017723  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?c_WebDialogAsyncAction@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const c_WebDialogAsyncAction,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180017728  lea     rcx, [rbp+arg_18]
0x18001772c  mov     [rbp+arg_18], r14
0x180017730  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180017735  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180017739  lea     r8, [rbp+arg_18]; struct IRpcOptions **
0x18001773d  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x180017742  mov     [rbp+ppstm], r14
0x180017746  mov     [rbp+var_18], r14d
0x18001774a  cmp     [rbp+arg_18], r14
0x18001774e  jnz     loc_1800177E5
0x180017754  mov     [rbp+var_18], 80004002h
0x18001775b  mov     rcx, [rbp+arg_8]
0x18001775f  mov     r8d, [rbp+arg_0]
0x180017763  mov     rdx, [rbp+pUnk]
0x180017767  mov     rax, [rcx]
0x18001776a  mov     rax, [rax+18h]
0x18001776e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017773  mov     r8, [rdi+80h]
0x18001777a  mov     ecx, eax
0x18001777c  mov     rdx, [rbp+arg_8]
0x180017780  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180017785  mov     rcx, rdi
0x180017788  mov     esi, eax
0x18001778a  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18001778f  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?c_WebDialogAsyncAction@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const c_WebDialogAsyncAction,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x180017794  cmp     [rbp+var_18], r14d
0x180017798  jge     loc_18001783F
0x18001779e  lea     rcx, [rbp+ppstm]
0x1800177a2  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800177a7  lea     rcx, [rbp+arg_18]
0x1800177ab  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800177b0  mov     rcx, [rbp+arg_8]
0x1800177b4  test    rcx, rcx
0x1800177b7  jz      short loc_1800177C9
0x1800177b9  mov     [rbp+arg_8], r14
0x1800177bd  mov     rax, [rcx]
0x1800177c0  mov     rax, [rax+10h]
0x1800177c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177c9  lea     rcx, [rbp+pUnk]
0x1800177cd  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800177d2  lea     rcx, [rbp+var_28]
0x1800177d6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800177db  jmp     loc_180017686
0x1800177e0  mov     rcx, r14
0x1800177e3  jmp     short loc_1800177B4
0x1800177e5  cmp     [rbp+arg_8], r14
0x1800177e9  jz      loc_180017754
0x1800177ef  mov     rbx, [rbp+pUnk]
0x1800177f3  lea     rcx, [rbp+ppstm]
0x1800177f7  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800177fc  lea     r8, [rbp+ppstm]; ppstm
0x180017800  mov     edx, r15d; fDeleteOnRelease
0x180017803  xor     ecx, ecx; hGlobal
0x180017805  call    cs:__imp_CreateStreamOnHGlobal
0x18001780b  mov     [rbp+var_18], eax
0x18001780e  test    eax, eax
0x180017810  js      loc_18001775B
0x180017816  mov     rcx, [rbp+ppstm]; pStm
0x18001781a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180017821  mov     [rsp+58h+mshlflags], r15d; mshlflags
0x180017826  xor     r9d, r9d; dwDestContext
0x180017829  mov     r8, rbx; pUnk
0x18001782c  mov     [rsp+58h+pvDestContext], r14; pvDestContext
0x180017831  call    cs:__imp_CoMarshalInterface
0x180017837  mov     [rbp+var_18], eax
0x18001783a  jmp     loc_18001775B
0x18001783f  mov     rcx, [rbp+ppstm]
0x180017843  mov     rdx, r14
0x180017846  xor     r9d, r9d
0x180017849  mov     r8, [rcx]
0x18001784c  mov     rax, [r8+28h]
0x180017850  xor     r8d, r8d
0x180017853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017858  mov     rcx, [rbp+ppstm]; pStm
0x18001785c  call    cs:__imp_CoReleaseMarshalData
0x180017862  jmp     loc_18001779E
```
