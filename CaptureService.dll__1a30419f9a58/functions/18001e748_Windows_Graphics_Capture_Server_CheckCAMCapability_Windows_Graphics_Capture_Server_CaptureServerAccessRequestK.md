# Windows::Graphics::Capture::Server::CheckCAMCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind,bool,ulong,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus *)

- ea: `0x18001e748`
- end: `0x18001e95e`
- name: `?CheckCAMCapability@Server@Capture@Graphics@Windows@@YAJW4CaptureServerAccessRequestKind@1234@_NKPEAW4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@4@@Z`
- size: `534`
- prototype: `__int64 __fastcall(unsigned int, char, unsigned int, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e964`
- `0x18001ea08`

## callees

- `0x180002e60`
- `0x18000907c`
- `0x18000ddc4`
- `0x18000f7b4`
- `0x18001e748`
- `0x18001ec70`
- `0x18001f484`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e7ba`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e7ba`

## string_xrefs

- `0x18001e79b`: `Windows.Internal.CapabilityAccess.CapabilityAccess`
- `0x18001e7cd`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`
- `0x18001e82f`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`
- `0x18001e8a8`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CheckCAMCapability(
        unsigned int a1,
        char a2,
        unsigned int a3,
        int *a4)
{
  int ActivationFactory; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // edi
  __int64 v14; // rdx
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-49h]
  __int64 v18; // [rsp+40h] [rbp-29h] BYREF
  int v19; // [rsp+48h] [rbp-21h] BYREF
  __int64 v20; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v21[24]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v22; // [rsp+70h] [rbp+7h]
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v24; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a4 = 3;
  v20 = 0;
  v24 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.CapabilityAccess.CapabilityAccess",
    0x33u,
    0x32u);
  ActivationFactory = RoGetActivationFactory(v24, &GUID_518f3880_4e5c_4524_ab03_cd01336b2178, &v20);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19A,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v17);
LABEL_10:
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v20);
    return v9;
  }
  v18 = 0;
  Windows::Graphics::Capture::Server::GetStringReferenceFromCapability(v21, a1);
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v20 + 56LL))(v20, 0, v22, a3);
  v9 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
      (const char *)(unsigned int)v10,
      0);
    v22 = 0;
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v18);
    goto LABEL_10;
  }
  v19 = 3;
  v12 = 1;
  LOBYTE(v11) = a2 ^ 1;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 88LL))(v18, v11);
  if ( v13 < 0 )
  {
    v14 = 422;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
      (const char *)(unsigned int)v13,
      0);
    v22 = 0;
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v18);
    v9 = v13;
    goto LABEL_10;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 152LL))(v18, &v19);
  if ( v13 < 0 )
  {
    v14 = 423;
    goto LABEL_9;
  }
  if ( v19 )
  {
    switch ( v19 )
    {
      case 1:
        v12 = 2;
        break;
      case 2:
        v12 = 3;
        break;
      case 3:
        v12 = 4;
        break;
      case 4:
        break;
      default:
        wil::details::in1diag3::FailFast_Hr(retaddr, (void *)0x189, v15, (const char *)0x8000FFFFLL, 0);
    }
  }
  else
  {
    v12 = 0;
  }
  *a4 = v12;
  v22 = 0;
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v18);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v20);
  return 0;
}

```

## disassembly

```asm
0x18001e748  mov     [rsp-8+arg_0], rbx
0x18001e74d  push    rbp
0x18001e74e  push    rsi
0x18001e74f  push    rdi
0x18001e750  push    r14
0x18001e752  push    r15
0x18001e754  lea     rbp, [rsp-37h]
0x18001e759  sub     rsp, 0A0h
0x18001e760  mov     rax, cs:__security_cookie
0x18001e767  xor     rax, rsp
0x18001e76a  mov     [rbp+57h+var_28], rax
0x18001e76e  mov     rsi, r9
0x18001e771  mov     r15d, r8d
0x18001e774  mov     dil, dl
0x18001e777  mov     r14d, ecx
0x18001e77a  mov     dword ptr [r9], 3
0x18001e781  mov     [rbp+57h+var_70], 0
0x18001e789  mov     [rbp+57h+var_30], 0
0x18001e791  mov     r9d, 32h ; '2'; unsigned int
0x18001e797  lea     r8d, [r9+1]; unsigned int
0x18001e79b  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x18001e7a2  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001e7a6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001e7ab  lea     r8, [rbp+57h+var_70]
0x18001e7af  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x18001e7b6  mov     rcx, [rbp+57h+var_30]
0x18001e7ba  call    cs:__imp_RoGetActivationFactory
0x18001e7c0  mov     ebx, eax
0x18001e7c2  test    eax, eax
0x18001e7c4  jns     short loc_18001E7E3
0x18001e7c6  mov     rcx, [rbp+5Fh]; this
0x18001e7ca  mov     r9d, eax; char *
0x18001e7cd  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001e7d4  mov     edx, 19Ah; void *
0x18001e7d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e7de  jmp     loc_18001E8CC
0x18001e7e3  mov     [rbp+57h+var_80], 0
0x18001e7eb  mov     edx, r14d
0x18001e7ee  lea     rcx, [rbp+57h+var_68]
0x18001e7f2  call    ?GetStringReferenceFromCapability@Server@Capture@Graphics@Windows@@YA?AVHStringReference@Wrappers@WRL@Microsoft@@W4CaptureServerAccessRequestKind@1234@@Z; Windows::Graphics::Capture::Server::GetStringReferenceFromCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind)
0x18001e7f7  nop
0x18001e7f8  mov     rcx, [rbp+57h+var_70]
0x18001e7fc  mov     rax, [rcx]
0x18001e7ff  lea     rdx, [rbp+57h+var_80]
0x18001e803  mov     [rsp+0C0h+var_98], rdx
0x18001e808  mov     [rsp+0C0h+var_A0], 0; int
0x18001e810  mov     r9d, r15d
0x18001e813  mov     r8, [rbp+57h+var_50]
0x18001e817  xor     edx, edx
0x18001e819  mov     rax, [rax+38h]
0x18001e81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e822  mov     ebx, eax
0x18001e824  test    eax, eax
0x18001e826  jns     short loc_18001E854
0x18001e828  mov     rcx, [rbp+5Fh]; this
0x18001e82c  mov     r9d, eax; char *
0x18001e82f  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001e836  mov     edx, 1A3h; void *
0x18001e83b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e840  nop
0x18001e841  mov     [rbp+57h+var_50], 0
0x18001e849  lea     rcx, [rbp+57h+var_80]
0x18001e84d  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001e852  jmp     short loc_18001E8CC
0x18001e854  mov     [rbp+57h+var_78], 3
0x18001e85b  mov     rcx, [rbp+57h+var_80]
0x18001e85f  mov     rax, [rcx]
0x18001e862  mov     ebx, 1
0x18001e867  xor     dil, bl
0x18001e86a  mov     dl, dil
0x18001e86d  mov     rax, [rax+58h]
0x18001e871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e876  mov     edi, eax
0x18001e878  test    eax, eax
0x18001e87a  jns     short loc_18001E883
0x18001e87c  mov     edx, 1A6h
0x18001e881  jmp     short loc_18001E8A5
0x18001e883  mov     rcx, [rbp+57h+var_80]
0x18001e887  mov     rax, [rcx]
0x18001e88a  lea     rdx, [rbp+57h+var_78]
0x18001e88e  mov     rax, [rax+98h]
0x18001e895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e89a  mov     edi, eax
0x18001e89c  test    eax, eax
0x18001e89e  jns     short loc_18001E8D9
0x18001e8a0  mov     edx, 1A7h; void *
0x18001e8a5  mov     r9d, edi; char *
0x18001e8a8  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001e8af  mov     rcx, [rbp+5Fh]; this
0x18001e8b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e8b8  nop
0x18001e8b9  mov     [rbp+57h+var_50], 0
0x18001e8c1  lea     rcx, [rbp+57h+var_80]
0x18001e8c5  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001e8ca  mov     ebx, edi
0x18001e8cc  lea     rcx, [rbp+57h+var_70]
0x18001e8d0  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001e8d5  mov     eax, ebx
0x18001e8d7  jmp     short loc_18001E93B
0x18001e8d9  mov     ecx, [rbp+57h+var_78]
0x18001e8dc  test    ecx, ecx
0x18001e8de  jz      short loc_18001E91A
0x18001e8e0  sub     ecx, ebx
0x18001e8e2  jz      short loc_18001E913
0x18001e8e4  sub     ecx, ebx
0x18001e8e6  jz      short loc_18001E90C
0x18001e8e8  sub     ecx, ebx
0x18001e8ea  jz      short loc_18001E905
0x18001e8ec  cmp     ecx, ebx
0x18001e8ee  jz      short loc_18001E91C
0x18001e8f0  mov     rcx, [rbp+5Fh]; this
0x18001e8f4  mov     edx, 189h; void *
0x18001e8f9  mov     r9d, 8000FFFFh; char *
0x18001e8ff  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18001e905  mov     ebx, 4
0x18001e90a  jmp     short loc_18001E91C
0x18001e90c  mov     ebx, 3
0x18001e911  jmp     short loc_18001E91C
0x18001e913  mov     ebx, 2
0x18001e918  jmp     short loc_18001E91C
0x18001e91a  xor     ebx, ebx
0x18001e91c  mov     [rsi], ebx
0x18001e91e  mov     [rbp+57h+var_50], 0
0x18001e926  lea     rcx, [rbp+57h+var_80]
0x18001e92a  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001e92f  nop
0x18001e930  lea     rcx, [rbp+57h+var_70]
0x18001e934  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001e939  xor     eax, eax
0x18001e93b  mov     rcx, [rbp+57h+var_28]
0x18001e93f  xor     rcx, rsp; StackCookie
0x18001e942  call    __security_check_cookie
0x18001e947  mov     rbx, [rsp+0C0h+arg_0]
0x18001e94f  add     rsp, 0A0h
0x18001e956  pop     r15
0x18001e958  pop     r14
0x18001e95a  pop     rdi
0x18001e95b  pop     rsi
0x18001e95c  pop     rbp
0x18001e95d  retn
```
