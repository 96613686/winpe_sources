# _lambda_98fdb0316fd9bf7a0dcb7351ee8eadc0_::operator()

- ea: `0x180027714`
- end: `0x1800278db`
- name: `_lambda_98fdb0316fd9bf7a0dcb7351ee8eadc0_::operator()`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180034c00`

## callees

- `0x180004d50`
- `0x18000992c`
- `0x18000a2a4`
- `0x1800173a4`
- `0x18001f234`
- `0x180024cf0`
- `0x180024eec`
- `0x180027714`
- `0x180034fcc`
- `0x180036350`
- `0x1800369f0`
- `0x18003b1ec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800277a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800277a4`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18002785f`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18002785f`
- `dmEnrollEngine!__imp_FindDiscoveryServiceEx` at `0x1800277bd`
- `dmEnrollEngine!__imp_FindDiscoveryServiceEx` at `0x1800277bd`

## string_xrefs

- `0x180027748`: `FindDiscoveryService`

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
0x180027714  mov     [rsp-8+arg_10], rbx
0x180027719  mov     [rsp-8+arg_18], rsi
0x18002771e  push    rbp
0x18002771f  push    rdi
0x180027720  push    r14
0x180027722  lea     rbp, [rsp-0A0h]
0x18002772a  sub     rsp, 1A0h
0x180027731  mov     rax, cs:__security_cookie
0x180027738  xor     rax, rsp
0x18002773b  mov     [rbp+0B0h+var_20], rax
0x180027742  mov     rsi, rdx
0x180027745  mov     rdi, rcx
0x180027748  lea     rdx, aFinddiscoverys; "FindDiscoveryService"
0x18002774f  lea     rcx, [rsp+1B0h+var_170]
0x180027754  call    ??0?$ActivityBase@VEnrollmentLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<EnrollmentLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<EnrollmentLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180027759  lea     rax, ??_7FindDiscoveryService@EnrollmentLogging@@6B@; const EnrollmentLogging::FindDiscoveryService::`vftable'
0x180027760  lea     rcx, [rsp+1B0h+var_170]; this
0x180027765  mov     [rsp+1B0h+var_170], rax
0x18002776a  call    ?StartActivity@FindDiscoveryService@EnrollmentLogging@@QEAAXXZ; EnrollmentLogging::FindDiscoveryService::StartActivity(void)
0x18002776f  xor     r14d, r14d
0x180027772  lea     rcx, [rsp+1B0h+var_190]
0x180027777  xor     edx, edx
0x180027779  mov     [rsp+1B0h+var_190], r14; int
0x18002777e  mov     [rsp+1B0h+var_188], r14d
0x180027783  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180027788  mov     al, [rdi+10h]
0x18002778b  mov     rcx, [rdi]
0x18002778e  neg     al
0x180027790  sbb     ebx, ebx
0x180027792  and     ebx, 40h
0x180027795  test    rcx, rcx
0x180027798  jz      short loc_18002779F
0x18002779a  mov     rcx, [rcx]
0x18002779d  jmp     short loc_1800277A2
0x18002779f  mov     rcx, r14; string
0x1800277a2  xor     edx, edx; length
0x1800277a4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800277aa  mov     rcx, rax
0x1800277ad  lea     r9, [rsp+1B0h+var_188]
0x1800277b2  lea     r8, [rsp+1B0h+var_190]
0x1800277b7  lea     edx, [rbx+1000h]
0x1800277bd  call    cs:__imp_FindDiscoveryServiceEx
0x1800277c3  mov     ebx, eax
0x1800277c5  cmp     eax, 8018001Ah
0x1800277ca  jnz     short loc_1800277D6
0x1800277cc  mov     rax, [rdi+18h]
0x1800277d0  mov     byte ptr [rax+48h], 1
0x1800277d4  jmp     short loc_1800277E6
0x1800277d6  test    eax, eax
0x1800277d8  js      loc_18002789E
0x1800277de  mov     rax, [rdi+18h]
0x1800277e2  mov     [rax+48h], r14b
0x1800277e6  mov     rcx, [rdi+18h]
0x1800277ea  mov     rdx, [rsp+1B0h+var_190]; unsigned __int16 *
0x1800277ef  add     rcx, 40h ; '@'; this
0x1800277f3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800277f7  inc     r8; unsigned int
0x1800277fa  cmp     [rdx+r8*2], r14w
0x1800277ff  jnz     short loc_1800277F7
0x180027801  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180027806  mov     ebx, eax
0x180027808  test    eax, eax
0x18002780a  jns     short loc_180027829
0x18002780c  mov     rcx, [rbp+0B8h]; this
0x180027813  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002781a  mov     r9d, eax; char *
0x18002781d  mov     edx, 132h; void *
0x180027822  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027827  jmp     short loc_18002789E
0x180027829  mov     rdi, [rdi+18h]
0x18002782d  lea     rax, [rsi+10h]
0x180027831  lea     rcx, [rsp+1B0h+var_180]
0x180027836  mov     [rsp+1B0h+var_180], rax
0x18002783b  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x180027840  mov     rbx, rax
0x180027843  test    rdi, rdi
0x180027846  jz      short loc_18002786D
0x180027848  mov     rcx, rax
0x18002784b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027850  mov     r9, rbx
0x180027853  lea     rdx, _GUID_ea03163e_5836_4ffd_84af_9dfe0e58e7f9
0x18002785a  mov     r8, rdi
0x18002785d  xor     ecx, ecx
0x18002785f  call    cs:__imp_RoGetAgileReference
0x180027865  mov     ebx, eax
0x180027867  test    eax, eax
0x180027869  jns     short loc_180027891
0x18002786b  jmp     short loc_18002780C
0x18002786d  mov     rax, [rax]
0x180027870  lea     rcx, [rsp+1B0h+var_180]
0x180027875  mov     [rsp+1B0h+var_180], rax
0x18002787a  mov     [rsp+1B0h+var_178], r14
0x18002787f  mov     [rbx], r14
0x180027882  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027887  lea     rcx, [rsp+1B0h+var_178]
0x18002788c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027891  lea     rcx, [rsp+1B0h+var_170]
0x180027896  call    ?Stop@?$ActivityBase@VEnrollmentLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<EnrollmentLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002789b  mov     ebx, r14d
0x18002789e  lea     rcx, [rsp+1B0h+var_190]
0x1800278a3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800278a8  lea     rcx, [rsp+1B0h+var_170]; this
0x1800278ad  call    ??1FindDiscoveryService@EnrollmentLogging@@QEAA@XZ; EnrollmentLogging::FindDiscoveryService::~FindDiscoveryService(void)
0x1800278b2  mov     eax, ebx
0x1800278b4  mov     rcx, [rbp+0B0h+var_20]
0x1800278bb  xor     rcx, rsp; StackCookie
0x1800278be  call    __security_check_cookie
0x1800278c3  lea     r11, [rsp+1B0h+var_10]
0x1800278cb  mov     rbx, [r11+30h]
0x1800278cf  mov     rsi, [r11+38h]
0x1800278d3  mov     rsp, r11
0x1800278d6  pop     r14
0x1800278d8  pop     rdi
0x1800278d9  pop     rbp
0x1800278da  retn
```
