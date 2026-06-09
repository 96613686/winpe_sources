# Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>)

- ea: `0x180044ae8`
- end: `0x180044c6d`
- name: `?_SubmitThreadpoolInvoke@MBCategory@Internal@UX@Networking@Windows@@AEAAJV?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a460`
- `0x18000f5e0`

## callees

- `0x180002150`
- `0x180006820`
- `0x18000735c`
- `0x18000ccb0`
- `0x180011cb0`
- `0x18001cb10`
- `0x180039b1c`
- `0x18003abc8`
- `0x180044ae8`
- `0x180059010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x180044be5`
- `SHCORE!SHTaskPoolQueueTask` at `0x180044be5`

## string_xrefs

- `0x180044b06`: `Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke`
- `0x180044afa`: `MBCategory::_SubmitThreadpoolInvoke::ConnectionProfile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(__int64 a1, _QWORD *a2)
{
  int WeakReference; // eax
  unsigned int v5; // edi
  __int64 result; // rax
  unsigned int v7; // edi
  __int64 *v8; // rax
  __int64 v9; // rsi
  int v10; // eax
  int v11; // edi
  const char *v12; // r9
  int v13; // [rsp+20h] [rbp-38h]
  int v14; // [rsp+20h] [rbp-38h]
  __int64 v15; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v16[4]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v18; // [rsp+60h] [rbp+8h] BYREF
  _QWORD *v19; // [rsp+68h] [rbp+10h]
  __int64 v20; // [rsp+70h] [rbp+18h] BYREF

  v19 = a2;
  MBSettingUXLogging::Verbose(
    "Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke",
    5159,
    "MBCategory::_SubmitThreadpoolInvoke::ConnectionProfile");
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
    v16[0] = *a2;
    Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(v16);
    v7 = *(_DWORD *)(a1 + 716);
    v8 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke_::_3_::_lambda_1_____Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke_::_3_::_lambda_1___(
                      &v20,
                      &v15);
    v9 = *v8;
    *v8 = 0;
    if ( v20 )
    {
      v20 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
    }
    v10 = SHTaskPoolQueueTask(0, 2, v7, 0, v9, 0);
    try
    {
      v11 = v10;
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke_::_3_::_lambda_1_::__lambda_1_(&v15);
      if ( v11 >= 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1439,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
          (const char *)(unsigned int)v11,
          v14);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
        result = (unsigned int)v11;
      }
    }
    catch ( ... )
    {
      LODWORD(v18) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x143B,
                       (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
                       v12);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v19);
      return (unsigned int)v18;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x142A,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
      (const char *)(unsigned int)WeakReference,
      v13);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180044ae8  mov     [rsp+arg_8], rdx
0x180044aed  push    rbx
0x180044aee  push    rsi
0x180044aef  push    rdi
0x180044af0  sub     rsp, 40h
0x180044af4  mov     rbx, rdx
0x180044af7  mov     rsi, rcx
0x180044afa  lea     r8, aMbcategorySubm_4; "MBCategory::_SubmitThreadpoolInvoke::Co"...
0x180044b01  mov     edx, 1427h; unsigned int
0x180044b06  lea     rcx, aWindowsNetwork_218; "Windows::Networking::UX::Internal::MBCa"...
0x180044b0d  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x180044b12  mov     [rsp+58h+arg_0], 0
0x180044b1b  lea     rcx, [rsp+58h+arg_0]
0x180044b20  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044b25  lea     rcx, [rsi+0C8h]
0x180044b2c  lea     rdx, [rsp+58h+arg_0]
0x180044b31  call    ?GetWeakReference@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCategoryBase@Internal@UX@Networking@Windows@@UIMBCategory@5678@UIMBUXCategory@678@UIMBConnectionFlowCallback@5678@UIInspectableInterfaceNlmChangeListener@5678@@Details@WRL@Microsoft@@UEAAJPEAPEAUIWeakReference@@@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>::GetWeakReference(IWeakReference * *)
0x180044b36  mov     edi, eax
0x180044b38  test    eax, eax
0x180044b3a  jns     short loc_180044B6E
0x180044b3c  mov     rcx, [rsp+58h]; this
0x180044b41  mov     r9d, eax; char *
0x180044b44  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180044b4b  mov     edx, 142Ah; void *
0x180044b50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044b55  lea     rcx, [rsp+58h+arg_0]
0x180044b5a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044b5f  mov     rcx, rbx
0x180044b62  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044b67  mov     eax, edi
0x180044b69  jmp     loc_180044C64
0x180044b6e  mov     rax, [rsp+58h+arg_0]
0x180044b73  mov     [rsp+58h+var_28], rax
0x180044b78  lea     rcx, [rsp+58h+var_28]
0x180044b7d  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x180044b82  mov     rax, [rbx]
0x180044b85  mov     [rsp+58h+var_20], rax
0x180044b8a  lea     rcx, [rsp+58h+var_20]
0x180044b8f  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x180044b94  mov     edi, [rsi+2CCh]
0x180044b9a  lea     rdx, [rsp+58h+var_28]
0x180044b9f  lea     rcx, [rsp+58h+arg_10]
0x180044ba4  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolInvoke____3____lambda_1_____Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolInvoke____3____lambda_1___
0x180044ba9  mov     rsi, [rax]
0x180044bac  mov     qword ptr [rax], 0
0x180044bb3  mov     rcx, [rsp+58h+arg_10]
0x180044bb8  test    rcx, rcx
0x180044bbb  jz      short loc_180044BCB
0x180044bbd  mov     [rsp+58h+arg_10], 0
0x180044bc6  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180044bcb  mov     [rsp+58h+var_30], 0
0x180044bd4  mov     qword ptr [rsp+58h+var_38], rsi; int
0x180044bd9  xor     r9d, r9d
0x180044bdc  mov     r8d, edi
0x180044bdf  lea     edx, [r9+2]
0x180044be3  xor     ecx, ecx
0x180044be5  call    cs:__imp_SHTaskPoolQueueTask
0x180044beb  mov     edi, eax
0x180044bed  test    rsi, rsi
0x180044bf0  jz      short loc_180044C02
0x180044bf2  mov     rdx, [rsi]
0x180044bf5  mov     rcx, rsi
0x180044bf8  mov     rax, [rdx+10h]
0x180044bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c01  nop
0x180044c02  lea     rcx, [rsp+58h+var_28]
0x180044c07  call    _Windows__Networking__UX__Internal__MBCategory___SubmitThreadpoolInvoke____3____lambda_1_____lambda_1_
0x180044c0c  test    edi, edi
0x180044c0e  jns     short loc_180044C3F
0x180044c10  mov     rcx, [rsp+58h]; this
0x180044c15  mov     r9d, edi; char *
0x180044c18  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180044c1f  mov     edx, 1439h; void *
0x180044c24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044c29  lea     rcx, [rsp+58h+arg_0]
0x180044c2e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044c33  mov     rcx, rbx
0x180044c36  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044c3b  mov     eax, edi
0x180044c3d  jmp     short loc_180044C64
0x180044c3f  lea     rcx, [rsp+58h+arg_0]
0x180044c44  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044c49  nop
0x180044c4a  mov     rcx, rbx
0x180044c4d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044c52  xor     eax, eax
0x180044c54  jmp     short loc_180044C64
0x180044c56  mov     rcx, [rsp+58h+arg_8]
0x180044c5b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044c60  mov     eax, dword ptr [rsp+58h+arg_0]
0x180044c64  add     rsp, 40h
0x180044c68  pop     rdi
0x180044c69  pop     rsi
0x180044c6a  pop     rbx
0x180044c6b  retn
```
