# RemoveRetailDemoOfflineContentTask::Start(IUnknown *,ushort *)

- ea: `0x180013110`
- end: `0x180013246`
- name: `?Start@RemoveRetailDemoOfflineContentTask@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `310`
- prototype: `__int64 __fastcall(RemoveRetailDemoOfflineContentTask *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x180010740`
- `0x180012120`
- `0x180012360`
- `0x180012404`
- `0x1800124ac`
- `0x180012b90`
- `0x180013110`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800131fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800131fc`

## string_xrefs

- `0x18001315f`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x1800131ba`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RemoveRetailDemoOfflineContentTask::Start(
        RemoveRetailDemoOfflineContentTask *this,
        struct IUnknown *a2,
        unsigned __int16 *a3)
{
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  volatile int *v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v23; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v24[3]; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  RemoveRetailDemoOfflineContentTask *v26; // [rsp+68h] [rbp+28h] BYREF
  __int64 v27; // [rsp+78h] [rbp+38h] BYREF

  v23 = 0;
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23, a2, a3);
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
         a2,
         &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
         &v23);
  v9 = v6;
  if ( v6 >= 0 )
  {
    v27 = 0;
    LODWORD(v26) = 2;
    v24[0] = v23;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27, v7, v8);
    v12 = Microsoft::WRL::Details::MakeAndInitialize<CMarshaledInterface::CMarshalStream,CMarshaledInterface::CMarshalStream,_GUID const &,IUnknown * &,enum MARSHAL_KIND &>(
            &v27,
            &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
            v24,
            &v26);
    v9 = v12;
    if ( v12 >= 0 )
    {
      v26 = this;
      if ( this )
        Microsoft::WRL::Details::SafeUnknownIncrementReference(
          (RemoveRetailDemoOfflineContentTask *)((char *)this + 12),
          v13);
      v16 = _lambda_5596f6d2c9ee3e090fe226ad29d0b955_::_lambda_5596f6d2c9ee3e090fe226ad29d0b955_(v24, &v27, &v26);
      CurrentThreadId = GetCurrentThreadId();
      Windows::Internal::ComTaskPool::QueueTask<_lambda_5596f6d2c9ee3e090fe226ad29d0b955_>(
        v19,
        v18,
        CurrentThreadId,
        v16);
      _lambda_5596f6d2c9ee3e090fe226ad29d0b955_::~_lambda_5596f6d2c9ee3e090fe226ad29d0b955_((_lambda_5596f6d2c9ee3e090fe226ad29d0b955_ *)v24);
      if ( this )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler>::Release(this);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27, v20, v21);
      v9 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
        (const char *)(unsigned int)v12,
        v23);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27, v14, v15);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
      (const char *)(unsigned int)v6,
      v23);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23, v10, v11);
  return v9;
}

```

## disassembly

```asm
0x180013110  mov     [rsp-18h+arg_0], rbx
0x180013115  push    rbp
0x180013116  push    rsi
0x180013117  push    rdi
0x180013118  mov     rbp, rsp
0x18001311b  sub     rsp, 40h
0x18001311f  mov     rdi, rdx
0x180013122  mov     rsi, rcx
0x180013125  mov     [rbp+var_20], 0
0x18001312d  mov     rax, [rdx]
0x180013130  mov     rbx, [rax]
0x180013133  lea     rcx, [rbp+var_20]
0x180013137  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001313c  lea     r8, [rbp+var_20]
0x180013140  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180013147  mov     rcx, rdi
0x18001314a  mov     rax, rbx
0x18001314d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013152  mov     ebx, eax
0x180013154  test    eax, eax
0x180013156  jns     short loc_180013175
0x180013158  mov     rcx, [rbp+18h]; this
0x18001315c  mov     r9d, eax; char *
0x18001315f  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180013166  mov     edx, 17h; void *
0x18001316b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013170  jmp     loc_18001322E
0x180013175  mov     [rbp+arg_18], 0
0x18001317d  mov     dword ptr [rbp+arg_8], 2
0x180013184  mov     rax, [rbp+var_20]
0x180013188  mov     [rbp+var_18], rax
0x18001318c  lea     rcx, [rbp+arg_18]
0x180013190  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013195  lea     r9, [rbp+arg_8]
0x180013199  lea     r8, [rbp+var_18]
0x18001319d  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x1800131a4  lea     rcx, [rbp+arg_18]
0x1800131a8  call    ??$MakeAndInitialize@VCMarshalStream@CMarshaledInterface@@V12@AEBU_GUID@@AEAPEAUIUnknown@@AEAW4MARSHAL_KIND@@@Details@WRL@Microsoft@@YAJPEAPEAVCMarshalStream@CMarshaledInterface@@AEBU_GUID@@AEAPEAUIUnknown@@AEAW4MARSHAL_KIND@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMarshaledInterface::CMarshalStream,CMarshaledInterface::CMarshalStream,_GUID const &,IUnknown * &,MARSHAL_KIND &>(CMarshaledInterface::CMarshalStream * *,_GUID const &,IUnknown * &,MARSHAL_KIND &)
0x1800131ad  mov     ebx, eax
0x1800131af  test    eax, eax
0x1800131b1  jns     short loc_1800131D6
0x1800131b3  mov     rcx, [rbp+18h]; this
0x1800131b7  mov     r9d, eax; char *
0x1800131ba  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800131c1  mov     edx, 19h; void *
0x1800131c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800131cb  lea     rcx, [rbp+arg_18]
0x1800131cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800131d4  jmp     short loc_18001322E
0x1800131d6  mov     [rbp+arg_8], rsi
0x1800131da  test    rsi, rsi
0x1800131dd  jz      short loc_1800131E8
0x1800131df  lea     rcx, [rsi+0Ch]; this
0x1800131e3  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x1800131e8  lea     r8, [rbp+arg_8]
0x1800131ec  lea     rdx, [rbp+arg_18]
0x1800131f0  lea     rcx, [rbp+var_18]
0x1800131f4  call    ??0_lambda_5596f6d2c9ee3e090fe226ad29d0b955_@@QEAA@AEBVCMarshaledInterface@@AEBV?$ComPtr@VRemoveRetailDemoOfflineContentTask@@@WRL@Microsoft@@@Z; _lambda_5596f6d2c9ee3e090fe226ad29d0b955_::_lambda_5596f6d2c9ee3e090fe226ad29d0b955_(CMarshaledInterface const &,Microsoft::WRL::ComPtr<RemoveRetailDemoOfflineContentTask> const &)
0x1800131f9  mov     rbx, rax
0x1800131fc  call    cs:__imp_GetCurrentThreadId
0x180013202  mov     r9, rbx
0x180013205  mov     r8d, eax
0x180013208  call    ??$QueueTask@V_lambda_5596f6d2c9ee3e090fe226ad29d0b955_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@W4TaskOptions@12@K$$QEAV_lambda_5596f6d2c9ee3e090fe226ad29d0b955_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_5596f6d2c9ee3e090fe226ad29d0b955_>(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,_lambda_5596f6d2c9ee3e090fe226ad29d0b955_ &&)
0x18001320d  lea     rcx, [rbp+var_18]; this
0x180013211  call    ??1_lambda_5596f6d2c9ee3e090fe226ad29d0b955_@@QEAA@XZ; _lambda_5596f6d2c9ee3e090fe226ad29d0b955_::~_lambda_5596f6d2c9ee3e090fe226ad29d0b955_(void)
0x180013216  test    rsi, rsi
0x180013219  jz      short loc_180013223
0x18001321b  mov     rcx, rsi
0x18001321e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UITaskHandler@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler>::Release(void)
0x180013223  lea     rcx, [rbp+arg_18]
0x180013227  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001322c  xor     ebx, ebx
0x18001322e  lea     rcx, [rbp+var_20]
0x180013232  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013237  mov     eax, ebx
0x180013239  mov     rbx, [rsp+40h+arg_0]
0x18001323e  add     rsp, 40h
0x180013242  pop     rdi
0x180013243  pop     rsi
0x180013244  pop     rbp
0x180013245  retn
```
