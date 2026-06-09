# Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItemAndWaitForHResult(std::function<long (void)> &&)

- ea: `0x18000d6c0`
- end: `0x18000d8c8`
- name: `?_SubmitThreadpoolWorkItemAndWaitForHResult@MBCategory@Internal@UX@Networking@Windows@@AEAAJ$$QEAV?$function@$$A6AJXZ@std@@@Z`
- size: `520`
- prototype: ``
- caller_count: `27`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800069f8`
- `0x18000c260`
- `0x18000d390`
- `0x18000d5d0`
- `0x18000ed60`
- `0x18001bb28`
- `0x1800284b0`
- `0x18003cca0`
- `0x18003d140`
- `0x18003eda0`
- `0x180040f20`
- `0x180041e80`
- `0x1800452f0`
- `0x1800453e0`
- `0x1800454d0`
- `0x1800455c0`
- `0x1800456e0`
- `0x180045850`
- `0x180045af0`
- `0x180045bd0`
- `0x180046050`
- `0x1800462f0`
- `0x1800464d0`
- `0x1800466e0`
- `0x1800468a0`
- `0x180046970`
- `0x180046a40`

## callees

- `0x180002150`
- `0x180006820`
- `0x18000735c`
- `0x18000d6c0`
- `0x18000fd08`
- `0x18000fe20`
- `0x180011ee0`
- `0x18001cb10`
- `0x180028720`
- `0x18002cd20`
- `0x18003abf0`
- `0x180059010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18000d7d8`
- `SHCORE!SHTaskPoolQueueTask` at `0x18000d7d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItemAndWaitForHResult(
        __int64 a1,
        __int64 a2)
{
  int WeakReference; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  _QWORD *v8; // rax
  int v9; // ebx
  _QWORD *v10; // rcx
  unsigned int v11; // ebx
  int v12; // [rsp+20h] [rbp-D8h]
  int v13; // [rsp+20h] [rbp-D8h]
  char *v14; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C0h] BYREF
  _QWORD *v16; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+50h] [rbp-A8h] BYREF
  _BYTE v18[72]; // [rsp+58h] [rbp-A0h] BYREF
  _BYTE v19[56]; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v15 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  WeakReference = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>::GetWeakReference(
                    a1 + 200,
                    &v15);
  v5 = WeakReference;
  if ( WeakReference >= 0 )
  {
    v17 = v15;
    Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(&v17);
    std::function<long (void)>::function<long (void)>(v18, a2);
    LODWORD(v14) = 0;
    v20 = 0;
    v20 = std::_Global_new_std::_Func_impl_no_alloc__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItemAndWaitForHResult_::_3_::_lambda_1__long___Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItemAndWaitForHResult_::_3_::_lambda_1__const___(&v17);
    v8 = (_QWORD *)Windows::Internal::ComTaskPool::WrapWithResultTask<std::function<long (void)>>(&v16, &v14, v19);
    v9 = SHTaskPoolQueueTask(0, 34, *(unsigned int *)(a1 + 712), 0, *v8, 0);
    v10 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v10 + 16LL))(v10, *v10);
    }
    std::_Func_class<void,>::~_Func_class<void,>(v19);
    if ( v9 >= 0 )
    {
      v11 = (unsigned int)v14;
      if ( (int)v14 >= 0 )
      {
        Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItem_::_12_::_lambda_1_::__lambda_1_(&v17);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13BE,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
          (const char *)(unsigned int)v14,
          v13);
        Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItem_::_12_::_lambda_1_::__lambda_1_(&v17);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
        return v11;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13BD,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
        (const char *)(unsigned int)v9,
        v13);
      Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItem_::_12_::_lambda_1_::__lambda_1_(&v17);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      return (unsigned int)v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13A5,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
      (const char *)(unsigned int)WeakReference,
      v12);
    v6 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v5;
  }
}

```

## disassembly

```asm
0x18000d6c0  mov     [rsp+arg_10], rbx
0x18000d6c5  mov     [rsp+arg_18], rsi
0x18000d6ca  push    rdi
0x18000d6cb  sub     rsp, 0F0h
0x18000d6d2  mov     rax, cs:__security_cookie
0x18000d6d9  xor     rax, rsp
0x18000d6dc  mov     [rsp+0F8h+var_18], rax
0x18000d6e4  mov     rsi, rdx
0x18000d6e7  mov     rdi, rcx
0x18000d6ea  mov     [rsp+0F8h+var_C0], 0
0x18000d6f3  lea     rcx, [rsp+0F8h+var_C0]
0x18000d6f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d6fd  lea     rcx, [rdi+0C8h]
0x18000d704  lea     rdx, [rsp+0F8h+var_C0]
0x18000d709  call    ?GetWeakReference@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCategoryBase@Internal@UX@Networking@Windows@@UIMBCategory@5678@UIMBUXCategory@678@UIMBConnectionFlowCallback@5678@UIInspectableInterfaceNlmChangeListener@5678@@Details@WRL@Microsoft@@UEAAJPEAPEAUIWeakReference@@@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>::GetWeakReference(IWeakReference * *)
0x18000d70e  mov     ebx, eax
0x18000d710  test    eax, eax
0x18000d712  jns     short loc_18000D758
0x18000d714  mov     rcx, [rsp+0F8h]; this
0x18000d71c  mov     r9d, eax; char *
0x18000d71f  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18000d726  mov     edx, 13A5h; void *
0x18000d72b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d730  nop
0x18000d731  mov     rcx, [rsp+0F8h+var_C0]
0x18000d736  test    rcx, rcx
0x18000d739  jz      short loc_18000D751
0x18000d73b  mov     [rsp+0F8h+var_C0], 0
0x18000d744  mov     rax, [rcx]
0x18000d747  mov     rax, [rax+10h]
0x18000d74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d750  nop
0x18000d751  mov     eax, ebx
0x18000d753  jmp     loc_18000D8A2
0x18000d758  mov     rax, [rsp+0F8h+var_C0]
0x18000d75d  mov     [rsp+0F8h+var_A8], rax
0x18000d762  lea     rcx, [rsp+0F8h+var_A8]
0x18000d767  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x18000d76c  mov     rdx, rsi
0x18000d76f  lea     rcx, [rsp+0F8h+var_A0]
0x18000d774  call    ??0?$function@$$A6AJXZ@std@@QEAA@$$QEAV01@@Z; std::function<long (void)>::function<long (void)>(std::function<long (void)> &&)
0x18000d779  nop
0x18000d77a  mov     dword ptr [rsp+0F8h+var_C8], 0
0x18000d782  mov     [rsp+0F8h+var_20], 0
0x18000d78e  lea     rcx, [rsp+0F8h+var_A8]
0x18000d793  call    std___Global_new_std___Func_impl_no_alloc__Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolWorkItemAndWaitForHResult____3____lambda_1__long___Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolWorkItemAndWaitForHResult____3____lambda_1__const___
0x18000d798  mov     [rsp+0F8h+var_20], rax
0x18000d7a0  lea     r8, [rsp+0F8h+var_58]
0x18000d7a8  lea     rdx, [rsp+0F8h+var_C8]
0x18000d7ad  lea     rcx, [rsp+0F8h+var_B8]
0x18000d7b2  call    ??$WrapWithResultTask@V?$function@$$A6AJXZ@std@@@ComTaskPool@Internal@Windows@@SA?AV?$ComPtr@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@AEAJ$$QEAV?$function@$$A6AJXZ@std@@@Z; Windows::Internal::ComTaskPool::WrapWithResultTask<std::function<long (void)>>(long &,std::function<long (void)> &&)
0x18000d7b7  mov     [rsp+0F8h+var_D0], 0
0x18000d7c0  mov     rax, [rax]
0x18000d7c3  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x18000d7c8  xor     r9d, r9d
0x18000d7cb  mov     r8d, [rdi+2C8h]
0x18000d7d2  lea     edx, [r9+22h]
0x18000d7d6  xor     ecx, ecx
0x18000d7d8  call    cs:__imp_SHTaskPoolQueueTask
0x18000d7de  mov     ebx, eax
0x18000d7e0  mov     rcx, [rsp+0F8h+var_B8]
0x18000d7e5  test    rcx, rcx
0x18000d7e8  jz      short loc_18000D800
0x18000d7ea  mov     [rsp+0F8h+var_B8], 0
0x18000d7f3  mov     rdx, [rcx]
0x18000d7f6  mov     rax, [rdx+10h]
0x18000d7fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7ff  nop
0x18000d800  lea     rcx, [rsp+0F8h+var_58]
0x18000d808  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18000d80d  test    ebx, ebx
0x18000d80f  jns     short loc_18000D847
0x18000d811  mov     rcx, [rsp+0F8h]; this
0x18000d819  mov     r9d, ebx; char *
0x18000d81c  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18000d823  mov     edx, 13BDh; void *
0x18000d828  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d82d  nop
0x18000d82e  lea     rcx, [rsp+0F8h+var_A8]
0x18000d833  call    _Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolWorkItem____12____lambda_1_____lambda_1_
0x18000d838  nop
0x18000d839  lea     rcx, [rsp+0F8h+var_C0]
0x18000d83e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d843  mov     eax, ebx
0x18000d845  jmp     short loc_18000D8A2
0x18000d847  mov     ebx, dword ptr [rsp+0F8h+var_C8]
0x18000d84b  test    ebx, ebx
0x18000d84d  jns     short loc_18000D885
0x18000d84f  mov     rcx, [rsp+0F8h]; this
0x18000d857  mov     r9d, ebx; char *
0x18000d85a  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18000d861  mov     edx, 13BEh; void *
0x18000d866  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d86b  nop
0x18000d86c  lea     rcx, [rsp+0F8h+var_A8]
0x18000d871  call    _Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolWorkItem____12____lambda_1_____lambda_1_
0x18000d876  nop
0x18000d877  lea     rcx, [rsp+0F8h+var_C0]
0x18000d87c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d881  mov     eax, ebx
0x18000d883  jmp     short loc_18000D8A2
0x18000d885  lea     rcx, [rsp+0F8h+var_A8]
0x18000d88a  call    _Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolWorkItem____12____lambda_1_____lambda_1_
0x18000d88f  nop
0x18000d890  lea     rcx, [rsp+0F8h+var_C0]
0x18000d895  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d89a  xor     eax, eax
0x18000d89c  jmp     short loc_18000D8A2
0x18000d89e  mov     eax, dword ptr [rsp+0F8h+var_C8]
0x18000d8a2  mov     rcx, [rsp+0F8h+var_18]
0x18000d8aa  xor     rcx, rsp; StackCookie
0x18000d8ad  call    __security_check_cookie
0x18000d8b2  lea     r11, [rsp+0F8h+var_8]
0x18000d8ba  mov     rbx, [r11+20h]
0x18000d8be  mov     rsi, [r11+28h]
0x18000d8c2  mov     rsp, r11
0x18000d8c5  pop     rdi
0x18000d8c6  retn
```
