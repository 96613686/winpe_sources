# Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(Windows::Networking::UX::MbCategoryAuxiliaryPrefType)

- ea: `0x180044c74`
- end: `0x180044dd6`
- name: `?_SubmitThreadpoolInvoke@MBCategory@Internal@UX@Networking@Windows@@AEAAJW4MbCategoryAuxiliaryPrefType@345@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ef40`

## callees

- `0x180002150`
- `0x180006820`
- `0x18000735c`
- `0x18000ccb0`
- `0x180011cb0`
- `0x18001cb10`
- `0x180039bd4`
- `0x180044c74`
- `0x180059010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x180044d60`
- `SHCORE!SHTaskPoolQueueTask` at `0x180044d60`

## string_xrefs

- `0x180044c97`: `Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(__int64 a1, int a2)
{
  int WeakReference; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  unsigned int v7; // ebx
  __int64 *v8; // rax
  __int64 v9; // rdi
  int v10; // eax
  int v11; // ebx
  const char *v12; // r9
  int v13; // [rsp+20h] [rbp-28h]
  int v14; // [rsp+20h] [rbp-28h]
  __int64 v15; // [rsp+30h] [rbp-18h] BYREF
  int v16; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v18; // [rsp+50h] [rbp+8h] BYREF
  __int64 v19; // [rsp+60h] [rbp+18h] BYREF

  MBSettingUXLogging::Verbose(
    "Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke",
    5130,
    "auxiliaryPreferenceType=%d",
    a2);
  v18 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  WeakReference = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>::GetWeakReference(
                    a1 + 200,
                    &v18);
  v5 = WeakReference;
  if ( WeakReference >= 0 )
  {
    v15 = v18;
    Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(&v15);
    v16 = a2;
    v7 = *(_DWORD *)(a1 + 716);
    v8 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke_::_3_::_lambda_1_____Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke_::_3_::_lambda_1____0(
                      &v19,
                      &v15);
    v9 = *v8;
    *v8 = 0;
    if ( v19 )
    {
      v19 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
    }
    v10 = SHTaskPoolQueueTask(0, 2, v7, 0, v9, 0);
    try
    {
      v11 = v10;
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      if ( v11 >= 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x141C,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
          (const char *)(unsigned int)v11,
          v14);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
        result = (unsigned int)v11;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x141E,
                             (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
                             v12);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x140D,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
      (const char *)(unsigned int)WeakReference,
      v13);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180044c74  mov     [rsp+arg_8], rbx
0x180044c79  mov     [rsp+arg_18], rsi
0x180044c7e  push    rdi
0x180044c7f  sub     rsp, 40h
0x180044c83  mov     edi, edx
0x180044c85  mov     rsi, rcx
0x180044c88  mov     r9d, edx
0x180044c8b  lea     r8, aAuxiliaryprefe; "auxiliaryPreferenceType=%d"
0x180044c92  mov     edx, 140Ah; unsigned int
0x180044c97  lea     rcx, aWindowsNetwork_218; "Windows::Networking::UX::Internal::MBCa"...
0x180044c9e  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x180044ca3  mov     [rsp+48h+arg_0], 0
0x180044cac  lea     rcx, [rsp+48h+arg_0]
0x180044cb1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044cb6  lea     rcx, [rsi+0C8h]
0x180044cbd  lea     rdx, [rsp+48h+arg_0]
0x180044cc2  call    ?GetWeakReference@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCategoryBase@Internal@UX@Networking@Windows@@UIMBCategory@5678@UIMBUXCategory@678@UIMBConnectionFlowCallback@5678@UIInspectableInterfaceNlmChangeListener@5678@@Details@WRL@Microsoft@@UEAAJPEAPEAUIWeakReference@@@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>::GetWeakReference(IWeakReference * *)
0x180044cc7  mov     ebx, eax
0x180044cc9  test    eax, eax
0x180044ccb  jns     short loc_180044CF7
0x180044ccd  mov     rcx, [rsp+48h]; this
0x180044cd2  mov     r9d, eax; char *
0x180044cd5  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180044cdc  mov     edx, 140Dh; void *
0x180044ce1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044ce6  lea     rcx, [rsp+48h+arg_0]
0x180044ceb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044cf0  mov     eax, ebx
0x180044cf2  jmp     loc_180044DC5
0x180044cf7  mov     rax, [rsp+48h+arg_0]
0x180044cfc  mov     [rsp+48h+var_18], rax
0x180044d01  lea     rcx, [rsp+48h+var_18]
0x180044d06  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x180044d0b  mov     [rsp+48h+var_10], edi
0x180044d0f  mov     ebx, [rsi+2CCh]
0x180044d15  lea     rdx, [rsp+48h+var_18]
0x180044d1a  lea     rcx, [rsp+48h+arg_10]
0x180044d1f  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolInvoke____3____lambda_1_____Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolInvoke____3____lambda_1____0
0x180044d24  mov     rdi, [rax]
0x180044d27  mov     qword ptr [rax], 0
0x180044d2e  mov     rcx, [rsp+48h+arg_10]
0x180044d33  test    rcx, rcx
0x180044d36  jz      short loc_180044D46
0x180044d38  mov     [rsp+48h+arg_10], 0
0x180044d41  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180044d46  mov     [rsp+48h+var_20], 0
0x180044d4f  mov     qword ptr [rsp+48h+var_28], rdi; int
0x180044d54  xor     r9d, r9d
0x180044d57  mov     r8d, ebx
0x180044d5a  lea     edx, [r9+2]
0x180044d5e  xor     ecx, ecx
0x180044d60  call    cs:__imp_SHTaskPoolQueueTask
0x180044d66  mov     ebx, eax
0x180044d68  test    rdi, rdi
0x180044d6b  jz      short loc_180044D7D
0x180044d6d  mov     rdx, [rdi]
0x180044d70  mov     rcx, rdi
0x180044d73  mov     rax, [rdx+10h]
0x180044d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d7c  nop
0x180044d7d  lea     rcx, [rsp+48h+var_18]
0x180044d82  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044d87  test    ebx, ebx
0x180044d89  jns     short loc_180044DB2
0x180044d8b  mov     rcx, [rsp+48h]; this
0x180044d90  mov     r9d, ebx; char *
0x180044d93  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180044d9a  mov     edx, 141Ch; void *
0x180044d9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044da4  lea     rcx, [rsp+48h+arg_0]
0x180044da9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044dae  mov     eax, ebx
0x180044db0  jmp     short loc_180044DC5
0x180044db2  lea     rcx, [rsp+48h+arg_0]
0x180044db7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044dbc  nop
0x180044dbd  xor     eax, eax
0x180044dbf  jmp     short loc_180044DC5
0x180044dc1  mov     eax, dword ptr [rsp+48h+arg_0]
0x180044dc5  mov     rbx, [rsp+48h+arg_8]
0x180044dca  mov     rsi, [rsp+48h+arg_18]
0x180044dcf  add     rsp, 40h
0x180044dd3  pop     rdi
0x180044dd4  retn
```
