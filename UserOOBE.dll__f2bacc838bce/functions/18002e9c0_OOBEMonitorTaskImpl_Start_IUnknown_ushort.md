# OOBEMonitorTaskImpl::Start(IUnknown *,ushort *)

- ea: `0x18002e9c0`
- end: `0x18002eaee`
- name: `?Start@OOBEMonitorTaskImpl@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `302`
- prototype: `__int64 __fastcall(OOBEMonitorTaskImpl *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800067b0`
- `0x180007134`
- `0x18000d400`
- `0x18002dbe8`
- `0x18002e25c`
- `0x18002e688`
- `0x18002e6a8`
- `0x18002e9c0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002eaa6`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002eaa6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ea59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ea59`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OOBEMonitorTaskImpl::Start(OOBEMonitorTaskImpl *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  DWORD CurrentThreadId; // edi
  __int64 *v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rcx
  int v13; // [rsp+20h] [rbp-30h]
  OOBEMonitorTaskImpl *v14; // [rsp+30h] [rbp-20h] BYREF
  __int64 v15; // [rsp+38h] [rbp-18h] BYREF
  OOBEMonitorTaskImpl *v16; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v18; // [rsp+78h] [rbp+28h] BYREF
  __int64 v19; // [rsp+88h] [rbp+38h] BYREF

  v18 = 0;
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
         a2,
         &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
         &v18);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v14 = this;
    Microsoft::WRL::ComPtr<OOBEMonitorTaskImpl>::InternalAddRef(&v14);
    v15 = v18;
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
    v16 = this;
    Microsoft::WRL::ComPtr<OOBEMonitorTaskImpl>::InternalAddRef(&v16);
    CurrentThreadId = GetCurrentThreadId();
    v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_>,_lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_>(
                      &v19,
                      &v15);
    v10 = *v9;
    *v9 = 0;
    v11 = v19;
    if ( v19 )
    {
      v19 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(v11);
    }
    SHTaskPoolQueueTask(0, 0, CurrentThreadId, 0, v10, 0);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    _lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_::~_lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_((_lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_ *)&v15);
    Microsoft::WRL::ComPtr<OOBEMonitorTaskImpl>::InternalRelease(&v14);
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"shell\\oobe\\user\\monitor\\oobemonitor.cpp",
      (const char *)(unsigned int)v6,
      v13);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  return v7;
}

```

## disassembly

```asm
0x18002e9c0  mov     [rsp-18h+arg_0], rbx
0x18002e9c5  push    rbp
0x18002e9c6  push    rsi
0x18002e9c7  push    rdi
0x18002e9c8  mov     rbp, rsp
0x18002e9cb  sub     rsp, 50h
0x18002e9cf  mov     rdi, rdx
0x18002e9d2  mov     rsi, rcx
0x18002e9d5  mov     [rbp+arg_8], 0
0x18002e9dd  mov     rax, [rdx]
0x18002e9e0  mov     rbx, [rax]
0x18002e9e3  lea     rcx, [rbp+arg_8]
0x18002e9e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e9ec  lea     r8, [rbp+arg_8]
0x18002e9f0  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18002e9f7  mov     rcx, rdi
0x18002e9fa  mov     rax, rbx
0x18002e9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea02  mov     ebx, eax
0x18002ea04  test    eax, eax
0x18002ea06  jns     short loc_18002EA25
0x18002ea08  mov     rcx, [rbp+18h]; this
0x18002ea0c  mov     r9d, eax; char *
0x18002ea0f  lea     r8, aShellOobeUserM_0; "shell\\oobe\\user\\monitor\\oobemonitor"...
0x18002ea16  mov     edx, 68h ; 'h'; void *
0x18002ea1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ea20  jmp     loc_18002EAD6
0x18002ea25  mov     [rbp+var_20], rsi
0x18002ea29  lea     rcx, [rbp+var_20]
0x18002ea2d  call    ?InternalAddRef@?$ComPtr@VOOBEMonitorTaskImpl@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<OOBEMonitorTaskImpl>::InternalAddRef(void)
0x18002ea32  mov     rcx, [rbp+arg_8]
0x18002ea36  mov     [rbp+var_18], rcx
0x18002ea3a  test    rcx, rcx
0x18002ea3d  jz      short loc_18002EA4C
0x18002ea3f  mov     rax, [rcx]
0x18002ea42  mov     rax, [rax+8]
0x18002ea46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea4b  nop
0x18002ea4c  mov     [rbp+var_10], rsi
0x18002ea50  lea     rcx, [rbp+var_10]
0x18002ea54  call    ?InternalAddRef@?$ComPtr@VOOBEMonitorTaskImpl@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<OOBEMonitorTaskImpl>::InternalAddRef(void)
0x18002ea59  call    cs:__imp_GetCurrentThreadId
0x18002ea5f  mov     edi, eax
0x18002ea61  lea     rdx, [rbp+var_18]
0x18002ea65  lea     rcx, [rbp+arg_18]
0x18002ea69  call    ??$Make@V?$CTaskWrapper@V_lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_@@@ComTaskPool@Internal@Windows@@V_lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_>,_lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_>(_lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_ &&)
0x18002ea6e  mov     rbx, [rax]
0x18002ea71  mov     qword ptr [rax], 0
0x18002ea78  mov     rcx, [rbp+arg_18]
0x18002ea7c  test    rcx, rcx
0x18002ea7f  jz      short loc_18002EA8E
0x18002ea81  mov     [rbp+arg_18], 0
0x18002ea89  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)
0x18002ea8e  mov     [rsp+50h+var_28], 0
0x18002ea97  mov     [rsp+50h+var_30], rbx
0x18002ea9c  xor     r9d, r9d
0x18002ea9f  mov     r8d, edi
0x18002eaa2  xor     edx, edx
0x18002eaa4  xor     ecx, ecx
0x18002eaa6  call    cs:__imp_SHTaskPoolQueueTask
0x18002eaac  nop
0x18002eaad  test    rbx, rbx
0x18002eab0  jz      short loc_18002EAC2
0x18002eab2  mov     rax, [rbx]
0x18002eab5  mov     rcx, rbx
0x18002eab8  mov     rax, [rax+10h]
0x18002eabc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eac1  nop
0x18002eac2  lea     rcx, [rbp+var_18]; this
0x18002eac6  call    ??1_lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_@@QEAA@XZ; _lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_::~_lambda_e2db9c1a7b895ddc5ce5cb27fc4a1788_(void)
0x18002eacb  lea     rcx, [rbp+var_20]
0x18002eacf  call    ?InternalRelease@?$ComPtr@VOOBEMonitorTaskImpl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OOBEMonitorTaskImpl>::InternalRelease(void)
0x18002ead4  xor     ebx, ebx
0x18002ead6  lea     rcx, [rbp+arg_8]
0x18002eada  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002eadf  mov     eax, ebx
0x18002eae1  mov     rbx, [rsp+50h+arg_0]
0x18002eae6  add     rsp, 50h
0x18002eaea  pop     rdi
0x18002eaeb  pop     rsi
0x18002eaec  pop     rbp
0x18002eaed  retn
```
