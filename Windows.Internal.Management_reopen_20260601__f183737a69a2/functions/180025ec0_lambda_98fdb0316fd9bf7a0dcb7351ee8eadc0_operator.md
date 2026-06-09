# _lambda_98fdb0316fd9bf7a0dcb7351ee8eadc0_::operator()

- ea: `0x180025ec0`
- end: `0x18002609a`
- name: `_lambda_98fdb0316fd9bf7a0dcb7351ee8eadc0_::operator()`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180033cd0`

## callees

- `0x180004eb0`
- `0x180009be4`
- `0x18000a5c4`
- `0x180017ba8`
- `0x18001d770`
- `0x180023380`
- `0x1800235a8`
- `0x180025ec0`
- `0x1800340e4`
- `0x180035620`
- `0x180035d04`
- `0x18003a588`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025f50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025f50`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180026017`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180026017`
- `dmEnrollEngine!__imp_FindDiscoveryServiceEx` at `0x180025f6f`
- `dmEnrollEngine!__imp_FindDiscoveryServiceEx` at `0x180025f6f`

## string_xrefs

- `0x180025ef4`: `FindDiscoveryService`

## pseudocode

```c
__int64 __fastcall lambda_98fdb0316fd9bf7a0dcb7351ee8eadc0_::operator()(__int64 a1, __int64 a2)
{
  int v4; // ebx
  HSTRING v5; // rcx
  PCWSTR StringRawBuffer; // rax
  int DiscoveryService; // eax
  unsigned int v8; // ebx
  __int64 v9; // r8
  HRESULT AgileReference; // eax
  __int64 v11; // rdi
  _QWORD *v12; // rax
  _QWORD *v13; // rbx
  unsigned __int16 *v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v19[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  wil::ActivityBase<EnrollmentLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<EnrollmentLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v19,
    "FindDiscoveryService");
  v19[0] = &EnrollmentLogging::FindDiscoveryService::`vftable';
  EnrollmentLogging::FindDiscoveryService::StartActivity((EnrollmentLogging::FindDiscoveryService *)v19);
  v15 = 0;
  v16 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v15,
    0);
  v4 = *(_BYTE *)(a1 + 16) != 0 ? 0x40 : 0;
  if ( *(_QWORD *)a1 )
    v5 = **(HSTRING **)a1;
  else
    v5 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v5, 0);
  DiscoveryService = FindDiscoveryServiceEx(StringRawBuffer, (unsigned int)(v4 + 4096), &v15, &v16);
  v8 = DiscoveryService;
  if ( DiscoveryService == -2145910758 )
  {
    *(_BYTE *)(*(_QWORD *)(a1 + 24) + 72LL) = 1;
LABEL_8:
    v9 = -1;
    do
      ++v9;
    while ( v15[v9] );
    AgileReference = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(*(_QWORD *)(a1 + 24) + 64LL), v15, v9);
    v8 = AgileReference;
    if ( AgileReference < 0 )
      goto LABEL_11;
    v11 = *(_QWORD *)(a1 + 24);
    v17 = a2 + 16;
    v12 = (_QWORD *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v17);
    v13 = v12;
    if ( v11 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v12);
      AgileReference = RoGetAgileReference(0, &GUID_ea03163e_5836_4ffd_84af_9dfe0e58e7f9, v11, v13);
      v8 = AgileReference;
      if ( AgileReference < 0 )
      {
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x132,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
          (const char *)(unsigned int)AgileReference,
          (int)v15);
        goto LABEL_17;
      }
    }
    else
    {
      v17 = *v12;
      v18 = 0;
      *v12 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    }
    wil::ActivityBase<EnrollmentLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v19);
    v8 = 0;
    goto LABEL_17;
  }
  if ( DiscoveryService >= 0 )
  {
    *(_BYTE *)(*(_QWORD *)(a1 + 24) + 72LL) = 0;
    goto LABEL_8;
  }
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
  EnrollmentLogging::FindDiscoveryService::~FindDiscoveryService((EnrollmentLogging::FindDiscoveryService *)v19);
  return v8;
}

```

## disassembly

```asm
0x180025ec0  mov     [rsp-8+arg_10], rbx
0x180025ec5  mov     [rsp-8+arg_18], rsi
0x180025eca  push    rbp
0x180025ecb  push    rdi
0x180025ecc  push    r14
0x180025ece  lea     rbp, [rsp-0A0h]
0x180025ed6  sub     rsp, 1A0h
0x180025edd  mov     rax, cs:__security_cookie
0x180025ee4  xor     rax, rsp
0x180025ee7  mov     [rbp+0B0h+var_20], rax
0x180025eee  mov     rsi, rdx
0x180025ef1  mov     rdi, rcx
0x180025ef4  lea     rdx, aFinddiscoverys; "FindDiscoveryService"
0x180025efb  lea     rcx, [rsp+1B0h+var_170]
0x180025f00  call    ??0?$ActivityBase@VEnrollmentLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<EnrollmentLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<EnrollmentLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180025f05  lea     rax, ??_7FindDiscoveryService@EnrollmentLogging@@6B@; const EnrollmentLogging::FindDiscoveryService::`vftable'
0x180025f0c  lea     rcx, [rsp+1B0h+var_170]; this
0x180025f11  mov     [rsp+1B0h+var_170], rax
0x180025f16  call    ?StartActivity@FindDiscoveryService@EnrollmentLogging@@QEAAXXZ; EnrollmentLogging::FindDiscoveryService::StartActivity(void)
0x180025f1b  xor     r14d, r14d
0x180025f1e  lea     rcx, [rsp+1B0h+var_190]
0x180025f23  xor     edx, edx
0x180025f25  mov     [rsp+1B0h+var_190], r14; int
0x180025f2a  mov     [rsp+1B0h+var_188], r14d
0x180025f2f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180025f34  mov     al, [rdi+10h]
0x180025f37  mov     rcx, [rdi]
0x180025f3a  neg     al
0x180025f3c  sbb     ebx, ebx
0x180025f3e  and     ebx, 40h
0x180025f41  test    rcx, rcx
0x180025f44  jz      short loc_180025F4B
0x180025f46  mov     rcx, [rcx]
0x180025f49  jmp     short loc_180025F4E
0x180025f4b  mov     rcx, r14; string
0x180025f4e  xor     edx, edx; length
0x180025f50  call    cs:__imp_WindowsGetStringRawBuffer
0x180025f57  nop     dword ptr [rax+rax+00h]
0x180025f5c  mov     rcx, rax
0x180025f5f  lea     r9, [rsp+1B0h+var_188]
0x180025f64  lea     r8, [rsp+1B0h+var_190]
0x180025f69  lea     edx, [rbx+1000h]
0x180025f6f  call    cs:__imp_FindDiscoveryServiceEx
0x180025f76  nop     dword ptr [rax+rax+00h]
0x180025f7b  mov     ebx, eax
0x180025f7d  cmp     eax, 8018001Ah
0x180025f82  jnz     short loc_180025F8E
0x180025f84  mov     rax, [rdi+18h]
0x180025f88  mov     byte ptr [rax+48h], 1
0x180025f8c  jmp     short loc_180025F9E
0x180025f8e  test    eax, eax
0x180025f90  js      loc_18002605C
0x180025f96  mov     rax, [rdi+18h]
0x180025f9a  mov     [rax+48h], r14b
0x180025f9e  mov     rcx, [rdi+18h]
0x180025fa2  mov     rdx, [rsp+1B0h+var_190]; unsigned __int16 *
0x180025fa7  add     rcx, 40h ; '@'; this
0x180025fab  or      r8, 0FFFFFFFFFFFFFFFFh
0x180025faf  inc     r8; unsigned int
0x180025fb2  cmp     [rdx+r8*2], r14w
0x180025fb7  jnz     short loc_180025FAF
0x180025fb9  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180025fbe  mov     ebx, eax
0x180025fc0  test    eax, eax
0x180025fc2  jns     short loc_180025FE1
0x180025fc4  mov     rcx, [rbp+0B8h]; this
0x180025fcb  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180025fd2  mov     r9d, eax; char *
0x180025fd5  mov     edx, 132h; void *
0x180025fda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025fdf  jmp     short loc_18002605C
0x180025fe1  mov     rdi, [rdi+18h]
0x180025fe5  lea     rax, [rsi+10h]
0x180025fe9  lea     rcx, [rsp+1B0h+var_180]
0x180025fee  mov     [rsp+1B0h+var_180], rax
0x180025ff3  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x180025ff8  mov     rbx, rax
0x180025ffb  test    rdi, rdi
0x180025ffe  jz      short loc_18002602B
0x180026000  mov     rcx, rax
0x180026003  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026008  mov     r9, rbx
0x18002600b  lea     rdx, _GUID_ea03163e_5836_4ffd_84af_9dfe0e58e7f9
0x180026012  mov     r8, rdi
0x180026015  xor     ecx, ecx
0x180026017  call    cs:__imp_RoGetAgileReference
0x18002601e  nop     dword ptr [rax+rax+00h]
0x180026023  mov     ebx, eax
0x180026025  test    eax, eax
0x180026027  jns     short loc_18002604F
0x180026029  jmp     short loc_180025FC4
0x18002602b  mov     rax, [rax]
0x18002602e  lea     rcx, [rsp+1B0h+var_180]
0x180026033  mov     [rsp+1B0h+var_180], rax
0x180026038  mov     [rsp+1B0h+var_178], r14
0x18002603d  mov     [rbx], r14
0x180026040  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026045  lea     rcx, [rsp+1B0h+var_178]
0x18002604a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002604f  lea     rcx, [rsp+1B0h+var_170]
0x180026054  call    ?Stop@?$ActivityBase@VEnrollmentLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<EnrollmentLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180026059  mov     ebx, r14d
0x18002605c  lea     rcx, [rsp+1B0h+var_190]
0x180026061  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026066  lea     rcx, [rsp+1B0h+var_170]; this
0x18002606b  call    ??1FindDiscoveryService@EnrollmentLogging@@QEAA@XZ; EnrollmentLogging::FindDiscoveryService::~FindDiscoveryService(void)
0x180026070  mov     eax, ebx
0x180026072  mov     rcx, [rbp+0B0h+var_20]
0x180026079  xor     rcx, rsp; StackCookie
0x18002607c  call    __security_check_cookie
0x180026081  lea     r11, [rsp+1B0h+var_10]
0x180026089  mov     rbx, [r11+30h]
0x18002608d  mov     rsi, [r11+38h]
0x180026091  mov     rsp, r11
0x180026094  pop     r14
0x180026096  pop     rdi
0x180026097  pop     rbp
0x180026098  retn
```
