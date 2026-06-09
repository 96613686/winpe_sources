# Microsoft::WRL::Details::MakeAndInitialize<AuthBuffer,IAuthBuffer,uchar * &,ulong &>(IAuthBuffer * *,uchar * &,ulong &)

- ea: `0x180009604`
- end: `0x18000975f`
- name: `??$MakeAndInitialize@VAuthBuffer@@UIAuthBuffer@@AEAPEAEAEAK@Details@WRL@Microsoft@@YAJPEAPEAUIAuthBuffer@@AEAPEAEAEAK@Z`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d950`

## callees

- `0x18000379c`
- `0x1800041e8`
- `0x180007134`
- `0x180009604`
- `0x18000a15c`
- `0x18000a3fc`
- `0x18000a5c8`
- `0x18000aab8`
- `0x18000b4b0`
- `0x18000be5c`
- `0x18000beb0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000967e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000967e`

## string_xrefs

- `0x18000969b`: `shell\oobe\user\dll\oobebrokermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<AuthBuffer,IAuthBuffer,unsigned char * &,unsigned long &>(
        _QWORD *a1,
        const void **a2,
        unsigned int *a3)
{
  AuthBuffer *v6; // rax
  int v7; // ebx
  AuthBuffer *v8; // rax
  _DWORD *v9; // rdi
  size_t v10; // rbx
  const void *v11; // rbp
  void *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  int v19[10]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  _DWORD *v21; // [rsp+50h] [rbp+8h] BYREF
  void *v22; // [rsp+68h] [rbp+20h] BYREF

  *a1 = 0;
  v6 = (AuthBuffer *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  *(_QWORD *)v19 = v6;
  if ( v6 )
  {
    v8 = AuthBuffer::AuthBuffer(v6);
    v21 = 0;
    Microsoft::WRL::ComPtr<OOBEUserRegistration>::Attach(&v21, v8);
    *(_QWORD *)v19 = 0;
    v9 = v21;
    v10 = *a3;
    v11 = *a2;
    v12 = CoTaskMemAlloc((unsigned int)v10);
    v22 = v12;
    if ( v12 )
    {
      memcpy_0(v12, v11, v10);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        v9 + 4,
        &v22);
      v9[6] = v10;
      v7 = 0;
    }
    else
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37,
        (unsigned int)"shell\\oobe\\user\\dll\\oobebrokermanager.cpp",
        (const char *)0x8007000ELL,
        v19[0]);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v22);
    if ( v7 >= 0 )
    {
      *a1 = 0;
      if ( (unsigned int)InlineIsEqualGUID(
                           &GUID_5705c141_a307_465f_b66b_31f328ef498d,
                           &GUID_00000000_0000_0000_c000_000000000046,
                           v13,
                           v14) )
      {
        *a1 = v9;
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 8LL))(v9);
        v7 = 0;
      }
      else if ( (unsigned int)InlineIsEqualGUID(v15, v15, v16, v17) )
      {
        *a1 = v9;
        v7 = 0;
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 8LL))(v9);
      }
      else
      {
        v7 = -2147467262;
      }
    }
    Microsoft::WRL::ComPtr<UserToken>::InternalRelease(&v21);
  }
  else
  {
    v7 = -2147024882;
  }
  __1__MakeAllocator_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Details_WRL_Microsoft__QEAA_XZ(v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009604  mov     [rsp+arg_8], rbx
0x180009609  mov     [rsp+arg_10], rbp
0x18000960e  push    rsi
0x18000960f  push    rdi
0x180009610  push    r14
0x180009612  sub     rsp, 30h
0x180009616  mov     rbx, r8
0x180009619  mov     r14, rdx
0x18000961c  mov     rsi, rcx
0x18000961f  mov     qword ptr [rcx], 0
0x180009626  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000962d  mov     ecx, 20h ; ' '; unsigned __int64
0x180009632  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009637  mov     qword ptr [rsp+48h+var_28], rax
0x18000963c  test    rax, rax
0x18000963f  jnz     short loc_18000964B
0x180009641  mov     ebx, 8007000Eh
0x180009646  jmp     loc_180009740
0x18000964b  mov     rcx, rax; this
0x18000964e  call    ??0AuthBuffer@@QEAA@XZ; AuthBuffer::AuthBuffer(void)
0x180009653  mov     [rsp+48h+arg_0], 0
0x18000965c  mov     rdx, rax
0x18000965f  lea     rcx, [rsp+48h+arg_0]
0x180009664  call    ?Attach@?$ComPtr@VOOBEUserRegistration@@@WRL@Microsoft@@QEAAXPEAVOOBEUserRegistration@@@Z; Microsoft::WRL::ComPtr<OOBEUserRegistration>::Attach(OOBEUserRegistration *)
0x180009669  mov     qword ptr [rsp+48h+var_28], 0; int
0x180009672  mov     rdi, [rsp+48h+arg_0]
0x180009677  mov     ebx, [rbx]
0x180009679  mov     rbp, [r14]
0x18000967c  mov     ecx, ebx; cb
0x18000967e  call    cs:__imp_CoTaskMemAlloc
0x180009684  mov     [rsp+48h+arg_18], rax
0x180009689  test    rax, rax
0x18000968c  jnz     short loc_1800096AC
0x18000968e  mov     rcx, [rsp+48h]; this
0x180009693  mov     ebx, 8007000Eh
0x180009698  mov     r9d, ebx; char *
0x18000969b  lea     r8, aShellOobeUserD; "shell\\oobe\\user\\dll\\oobebrokermanag"...
0x1800096a2  lea     edx, [rax+37h]; void *
0x1800096a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096aa  jmp     short loc_1800096CD
0x1800096ac  mov     r8, rbx; Size
0x1800096af  mov     rdx, rbp; Src
0x1800096b2  mov     rcx, rax; void *
0x1800096b5  call    memcpy_0
0x1800096ba  lea     rcx, [rdi+10h]
0x1800096be  lea     rdx, [rsp+48h+arg_18]
0x1800096c3  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800096c8  mov     [rdi+18h], ebx
0x1800096cb  xor     ebx, ebx
0x1800096cd  lea     rcx, [rsp+48h+arg_18]
0x1800096d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800096d7  test    ebx, ebx
0x1800096d9  js      short loc_180009736
0x1800096db  mov     qword ptr [rsi], 0
0x1800096e2  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800096e9  lea     rcx, _GUID_5705c141_a307_465f_b66b_31f328ef498d
0x1800096f0  call    InlineIsEqualGUID
0x1800096f5  test    eax, eax
0x1800096f7  jnz     short loc_180009722
0x1800096f9  mov     rdx, rcx
0x1800096fc  call    InlineIsEqualGUID
0x180009701  test    eax, eax
0x180009703  jz      short loc_18000971B
0x180009705  mov     [rsi], rdi
0x180009708  xor     ebx, ebx
0x18000970a  mov     rax, [rdi]
0x18000970d  mov     rcx, rdi
0x180009710  mov     rax, [rax+8]
0x180009714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009719  jmp     short loc_180009736
0x18000971b  mov     ebx, 80004002h
0x180009720  jmp     short loc_180009736
0x180009722  mov     [rsi], rdi
0x180009725  mov     rax, [rdi]
0x180009728  mov     rcx, rdi
0x18000972b  mov     rax, [rax+8]
0x18000972f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009734  xor     ebx, ebx
0x180009736  lea     rcx, [rsp+48h+arg_0]
0x18000973b  call    ?InternalRelease@?$ComPtr@VUserToken@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<UserToken>::InternalRelease(void)
0x180009740  lea     rcx, [rsp+48h+var_28]
0x180009745  call    ??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)
0x18000974a  mov     eax, ebx
0x18000974c  mov     rbx, [rsp+48h+arg_8]
0x180009751  mov     rbp, [rsp+48h+arg_10]
0x180009756  add     rsp, 30h
0x18000975a  pop     r14
0x18000975c  pop     rdi
0x18000975d  pop     rsi
0x18000975e  retn
```
