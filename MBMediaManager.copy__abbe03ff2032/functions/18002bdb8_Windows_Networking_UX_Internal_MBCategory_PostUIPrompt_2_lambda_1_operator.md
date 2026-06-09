# _Windows::Networking::UX::Internal::MBCategory::PostUIPrompt_::_2_::_lambda_1_::operator()

- ea: `0x18002bdb8`
- end: `0x18002bf2b`
- name: `_Windows::Networking::UX::Internal::MBCategory::PostUIPrompt_::_2_::_lambda_1_::operator()`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800434c0`

## callees

- `0x180002150`
- `0x18000735c`
- `0x180011cb0`
- `0x180017fa8`
- `0x18001cb10`
- `0x1800259f4`
- `0x18002bdb8`
- `0x18002bf34`
- `0x180039a54`
- `0x18003ae0c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bec1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bec1`
- `SHCORE!SHTaskPoolQueueTask` at `0x18002bedf`
- `SHCORE!SHTaskPoolQueueTask` at `0x18002bedf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::MBCategory::PostUIPrompt_::_2_::_lambda_1_::operator()(
        _QWORD *a1)
{
  bool v2; // si
  __int64 v3; // rcx
  __int64 v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rbx
  __int64 *v8; // rax
  __int64 v9; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v11; // edi
  int v13; // [rsp+20h] [rbp-30h]
  __int64 v14; // [rsp+30h] [rbp-20h] BYREF
  int v15; // [rsp+38h] [rbp-18h]
  bool v16; // [rsp+3Ch] [rbp-14h]
  __int64 v17; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 *v19; // [rsp+70h] [rbp+20h] BYREF
  __int64 v20; // [rsp+78h] [rbp+28h] BYREF
  __int64 v21; // [rsp+80h] [rbp+30h] BYREF

  v2 = 1;
  v3 = *(_QWORD *)(*a1 + 360LL);
  if ( v3 )
  {
    LODWORD(v19) = 0;
    if ( (*(int (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v3 + 48LL))(v3, &v19) >= 0 )
      v2 = *((_DWORD *)a1 + 2) != (_DWORD)v19;
  }
  Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::operator=(*a1 + 360LL, a1[2]);
  v20 = 0;
  v19 = &v20;
  v4 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v19);
  v5 = Microsoft::WRL::AsWeak<Windows::Networking::UX::Internal::MBCategory>(*a1, v4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v21 = a1[2];
    v7 = v21;
    Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(&v21);
    v14 = v20;
    Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(&v14);
    v15 = *((_DWORD *)a1 + 2);
    v16 = v2;
    v17 = v7;
    Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(&v17);
    v8 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper___Windows::Networking::UX::Internal::MBCategory::PostUIPrompt_::_2_::_lambda_1_::operator()_::_2_::_lambda_1______Windows::Networking::UX::Internal::MBCategory::PostUIPrompt_::_2_::_lambda_1_::operator()_::_2_::_lambda_1___(
                      &v19,
                      &v14);
    v9 = *v8;
    *v8 = 0;
    if ( v19 )
    {
      v19 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
    }
    CurrentThreadId = GetCurrentThreadId();
    v11 = SHTaskPoolQueueTask(0, 0, CurrentThreadId, 0, v9, 0);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    _Windows::Networking::UX::Internal::MBCategory::PostUIPrompt_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::__lambda_1_(&v14);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    v6 = v11;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA9F,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
      (const char *)(unsigned int)v5,
      v13);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  return v6;
}

```

## disassembly

```asm
0x18002bdb8  mov     [rsp-18h+arg_18], rbx
0x18002bdbd  push    rbp
0x18002bdbe  push    rsi
0x18002bdbf  push    rdi
0x18002bdc0  mov     rbp, rsp
0x18002bdc3  sub     rsp, 50h
0x18002bdc7  mov     rdi, rcx
0x18002bdca  mov     sil, 1
0x18002bdcd  mov     rax, [rcx]
0x18002bdd0  mov     rcx, [rax+168h]
0x18002bdd7  test    rcx, rcx
0x18002bdda  jz      short loc_18002BE01
0x18002bddc  mov     dword ptr [rbp+arg_0], 0
0x18002bde3  mov     rax, [rcx]
0x18002bde6  lea     rdx, [rbp+arg_0]
0x18002bdea  mov     rax, [rax+30h]
0x18002bdee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdf3  test    eax, eax
0x18002bdf5  js      short loc_18002BE01
0x18002bdf7  mov     eax, dword ptr [rbp+arg_0]
0x18002bdfa  cmp     [rdi+8], eax
0x18002bdfd  setnz   sil
0x18002be01  mov     rcx, [rdi]
0x18002be04  add     rcx, 168h
0x18002be0b  mov     rdx, [rdi+10h]
0x18002be0f  call    ??4?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUserInputType@UX@Networking@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::operator=(Windows::Networking::UX::IUserInputType *)
0x18002be14  mov     [rbp+arg_8], 0
0x18002be1c  lea     rax, [rbp+arg_8]
0x18002be20  mov     [rbp+arg_0], rax
0x18002be24  lea     rcx, [rbp+arg_0]
0x18002be28  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18002be2d  mov     rdx, rax
0x18002be30  mov     rcx, [rdi]
0x18002be33  call    ??$AsWeak@VMBCategory@Internal@UX@Networking@Windows@@@WRL@Microsoft@@YAJPEAVMBCategory@Internal@UX@Networking@Windows@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<Windows::Networking::UX::Internal::MBCategory>(Windows::Networking::UX::Internal::MBCategory *,Microsoft::WRL::WeakRef *)
0x18002be38  mov     ebx, eax
0x18002be3a  test    eax, eax
0x18002be3c  jns     short loc_18002BE5B
0x18002be3e  mov     rcx, [rbp+18h]; this
0x18002be42  mov     r9d, eax; char *
0x18002be45  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18002be4c  mov     edx, 0A9Fh; void *
0x18002be51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002be56  jmp     loc_18002BF10
0x18002be5b  mov     rbx, [rdi+10h]
0x18002be5f  mov     [rbp+arg_10], rbx
0x18002be63  lea     rcx, [rbp+arg_10]
0x18002be67  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x18002be6c  mov     rax, [rbp+arg_8]
0x18002be70  mov     [rbp+var_20], rax
0x18002be74  lea     rcx, [rbp+var_20]
0x18002be78  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x18002be7d  mov     eax, [rdi+8]
0x18002be80  mov     [rbp+var_18], eax
0x18002be83  mov     [rbp+var_14], sil
0x18002be87  mov     [rbp+var_10], rbx
0x18002be8b  lea     rcx, [rbp+var_10]
0x18002be8f  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x18002be94  lea     rdx, [rbp+var_20]
0x18002be98  lea     rcx, [rbp+arg_0]
0x18002be9c  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper___Windows__Networking__UX__Internal__MBCategory__PostUIPrompt____2____lambda_1___operator______2____lambda_1______Windows__Networking__UX__Internal__MBCategory__PostUIPrompt____2____lambda_1___operator______2____lambda_1___
0x18002bea1  mov     rbx, [rax]
0x18002bea4  mov     qword ptr [rax], 0
0x18002beab  mov     rcx, [rbp+arg_0]
0x18002beaf  test    rcx, rcx
0x18002beb2  jz      short loc_18002BEC1
0x18002beb4  mov     [rbp+arg_0], 0
0x18002bebc  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18002bec1  call    cs:__imp_GetCurrentThreadId
0x18002bec7  mov     [rsp+50h+var_28], 0
0x18002bed0  mov     [rsp+50h+var_30], rbx
0x18002bed5  xor     r9d, r9d
0x18002bed8  mov     r8d, eax
0x18002bedb  xor     edx, edx
0x18002bedd  xor     ecx, ecx
0x18002bedf  call    cs:__imp_SHTaskPoolQueueTask
0x18002bee5  mov     edi, eax
0x18002bee7  test    rbx, rbx
0x18002beea  jz      short loc_18002BEFC
0x18002beec  mov     rdx, [rbx]
0x18002beef  mov     rcx, rbx
0x18002bef2  mov     rax, [rdx+10h]
0x18002bef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002befb  nop
0x18002befc  lea     rcx, [rbp+var_20]
0x18002bf00  call    __Windows__Networking__UX__Internal__MBCategory__PostUIPrompt____2____lambda_1___operator______2____lambda_1_____lambda_1_
0x18002bf05  lea     rcx, [rbp+arg_10]
0x18002bf09  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bf0e  mov     ebx, edi
0x18002bf10  lea     rcx, [rbp+arg_8]
0x18002bf14  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bf19  mov     eax, ebx
0x18002bf1b  mov     rbx, [rsp+50h+arg_18]
0x18002bf23  add     rsp, 50h
0x18002bf27  pop     rdi
0x18002bf28  pop     rsi
0x18002bf29  pop     rbp
0x18002bf2a  retn
```
