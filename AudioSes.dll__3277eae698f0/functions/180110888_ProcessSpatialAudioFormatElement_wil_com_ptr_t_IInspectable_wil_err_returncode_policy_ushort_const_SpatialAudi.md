# ProcessSpatialAudioFormatElement(wil::com_ptr_t<IInspectable,wil::err_returncode_policy>,ushort const *,SpatialAudioFormatSubtypeInfo *,int,bool *)

- ea: `0x180110888`
- end: `0x180110be6`
- name: `?ProcessSpatialAudioFormatElement@@YAJV?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@PEBGPEAUSpatialAudioFormatSubtypeInfo@@HPEA_N@Z`
- size: `862`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180110c9c`

## callees

- `0x180007f00`
- `0x18000cb1c`
- `0x180010a90`
- `0x1800161bc`
- `0x1800163a0`
- `0x180020764`
- `0x180043b64`
- `0x180043bc0`
- `0x18005b0a0`
- `0x180087e80`
- `0x18010fa38`
- `0x18010fc48`
- `0x180110888`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180110a61`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180110a61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180110a38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180110a38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180110a47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180110a47`

## string_xrefs

- `0x1801108fc`: `OneCoreUap\Private\AVCore\inc\SpatialAudioLicenseBrokerUtil.h`
- `0x18011095d`: `OneCoreUap\Private\AVCore\inc\SpatialAudioLicenseBrokerUtil.h`
- `0x1801109b0`: `OneCoreUap\Private\AVCore\inc\SpatialAudioLicenseBrokerUtil.h`
- `0x1801109fd`: `OneCoreUap\Private\AVCore\inc\SpatialAudioLicenseBrokerUtil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ProcessSpatialAudioFormatElement(
        _QWORD *a1,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5)
{
  void *v6; // r14
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, _QWORD); // rbx
  _QWORD *v11; // rax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // esi
  const WCHAR *v16; // rdi
  UINT32 StringLen; // ebx
  const WCHAR *StringRawBuffer; // rax
  unsigned __int16 *v19; // rbx
  unsigned __int16 *v20; // rdx
  __int64 v21; // rcx
  HSTRING *v22; // rdx
  __int64 result; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-B8h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-B8h]
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-A8h] BYREF
  unsigned __int16 *v27; // [rsp+38h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-98h] BYREF
  __int64 v29; // [rsp+48h] [rbp-90h] BYREF
  __int64 v30; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v31[8]; // [rsp+58h] [rbp-80h] BYREF
  unsigned __int16 *v32; // [rsp+60h] [rbp-78h]
  _QWORD *v33; // [rsp+68h] [rbp-70h]
  HSTRING v34[4]; // [rsp+70h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v32 = a2;
  v6 = a1;
  v33 = a1;
  *a5 = 0;
  v30 = 0;
  v7 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1)(
         *a1,
         &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
         &v30);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"OneCoreUap\\Private\\AVCore\\inc\\SpatialAudioLicenseBrokerUtil.h",
      (const char *)(unsigned int)v7,
      bIgnoreCasea);
    goto LABEL_22;
  }
  v26 = 0;
  v9 = v30;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v30 + 48LL);
  v26 = 0;
  v11 = (_QWORD *)Windows::Internal::StringReference::StringReference(v34, L"@Name");
  v12 = v10(v9, *v11, &v26);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"OneCoreUap\\Private\\AVCore\\inc\\SpatialAudioLicenseBrokerUtil.h",
      (const char *)(unsigned int)v12,
      bIgnoreCasea);
LABEL_5:
    wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v26);
    goto LABEL_22;
  }
  v29 = 0;
  v13 = (**v26)(v26, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v29);
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"OneCoreUap\\Private\\AVCore\\inc\\SpatialAudioLicenseBrokerUtil.h",
      (const char *)(unsigned int)v13,
      bIgnoreCasea);
LABEL_8:
    wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v29);
    goto LABEL_5;
  }
  string = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 152LL))(v29, &string);
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"OneCoreUap\\Private\\AVCore\\inc\\SpatialAudioLicenseBrokerUtil.h",
      (const char *)(unsigned int)v14,
      bIgnoreCasea);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    goto LABEL_8;
  }
  v15 = 0;
  try
  {
    while ( v15 < 7 )
    {
      v16 = *(const WCHAR **)(a3 + 40LL * v15 + 8);
      StringLen = WindowsGetStringLen(string);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(StringRawBuffer, StringLen, v16, -1, 1) == 2 )
      {
        v27 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v27,
          0);
        v19 = v32;
        if ( (int)GetAppServiceName(v32, &v27) >= 0 )
        {
          *(_BYTE *)(a3 + 40LL * v15) = 1;
          *(_OWORD *)v34 = 0;
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            v31,
            v19,
            -1);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            v34,
            v31);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v31);
          v20 = v27;
          v27 = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v34[1],
            v20);
          v21 = a3 + 16 + 40LL * v15;
          v22 = *(HSTRING **)(v21 + 8);
          if ( v22 == *(HSTRING **)(v21 + 16) )
          {
            std::vector<SpatialAudioAppDetails>::_Emplace_reallocate<SpatialAudioAppDetails>(v21, v22, v34);
          }
          else
          {
            *v22 = v34[0];
            v34[0] = 0;
            v22[1] = v34[1];
            v34[1] = 0;
            *(_QWORD *)(v21 + 8) += 16LL;
          }
          SpatialAudioAppDetails::~SpatialAudioAppDetails((SpatialAudioAppDetails *)v34);
        }
        *a5 = 1;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v27);
      }
      ++v15;
    }
  }
  catch ( std::exception )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"OneCoreUap\\Private\\AVCore\\inc\\SpatialAudioLicenseBrokerUtil.h",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    SpatialAudioAppDetails::~SpatialAudioAppDetails((SpatialAudioAppDetails *)v34);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v27);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v29);
    wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v26);
    v8 = -2147024882;
    v6 = v33;
LABEL_22:
    wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v30);
    wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(v6);
    result = v8;
  }
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v29);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v26);
  v8 = 0;
  goto LABEL_22;
}

```

## disassembly

```asm
0x180110888  push    rbx
0x18011088a  push    rsi
0x18011088b  push    rdi
0x18011088c  push    r12
0x18011088e  push    r13
0x180110890  push    r14
0x180110892  push    r15
0x180110894  sub     rsp, 0A0h
0x18011089b  mov     rax, cs:__security_cookie
0x1801108a2  xor     rax, rsp
0x1801108a5  mov     [rsp+0D8h+var_48], rax
0x1801108ad  mov     r12, r8
0x1801108b0  mov     [rsp+0D8h+var_78], rdx
0x1801108b5  mov     r14, rcx
0x1801108b8  mov     [rsp+0D8h+var_70], rcx
0x1801108bd  mov     r13, [rsp+0D8h+arg_20]
0x1801108c5  xor     r15d, r15d
0x1801108c8  mov     [r13+0], r15b
0x1801108cc  mov     [rsp+0D8h+var_88], r15
0x1801108d1  mov     rcx, [rcx]
0x1801108d4  mov     rax, [rcx]
0x1801108d7  lea     r8, [rsp+0D8h+var_88]
0x1801108dc  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1801108e3  mov     rax, [rax]
0x1801108e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801108eb  mov     ebx, eax
0x1801108ed  test    eax, eax
0x1801108ef  jns     short loc_180110912
0x1801108f1  mov     rcx, [rsp+0D8h]; this
0x1801108f9  mov     r9d, eax; char *
0x1801108fc  lea     r8, aOnecoreuapPriv; "OneCoreUap\\Private\\AVCore\\inc\\Spati"...
0x180110903  mov     edx, 0E6h; void *
0x180110908  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011090d  jmp     loc_180110BAE
0x180110912  mov     [rsp+0D8h+var_A8], r15
0x180110917  mov     rdi, [rsp+0D8h+var_88]
0x18011091c  mov     rax, [rdi]
0x18011091f  mov     rbx, [rax+30h]
0x180110923  mov     [rsp+0D8h+var_A8], r15
0x180110928  lea     rdx, aName; "@Name"
0x18011092f  lea     rcx, [rsp+0D8h+var_68]; string
0x180110934  call    ??$?0$05@StringReference@Internal@Windows@@QEAA@AEAY05$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[6])
0x180110939  lea     r8, [rsp+0D8h+var_A8]
0x18011093e  mov     rdx, [rax]
0x180110941  mov     rcx, rdi
0x180110944  mov     rax, rbx
0x180110947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011094c  mov     ebx, eax
0x18011094e  test    eax, eax
0x180110950  jns     short loc_18011097E
0x180110952  mov     rcx, [rsp+0D8h]; this
0x18011095a  mov     r9d, eax; char *
0x18011095d  lea     r8, aOnecoreuapPriv; "OneCoreUap\\Private\\AVCore\\inc\\Spati"...
0x180110964  mov     edx, 0E9h; void *
0x180110969  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011096e  nop
0x18011096f  lea     rcx, [rsp+0D8h+var_A8]; void *
0x180110974  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180110979  jmp     loc_180110BAE
0x18011097e  mov     [rsp+0D8h+var_90], r15
0x180110983  mov     rcx, [rsp+0D8h+var_A8]
0x180110988  mov     rax, [rcx]
0x18011098b  lea     r8, [rsp+0D8h+var_90]
0x180110990  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180110997  mov     rax, [rax]
0x18011099a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011099f  mov     ebx, eax
0x1801109a1  test    eax, eax
0x1801109a3  jns     short loc_1801109CE
0x1801109a5  mov     rcx, [rsp+0D8h]; this
0x1801109ad  mov     r9d, eax; char *
0x1801109b0  lea     r8, aOnecoreuapPriv; "OneCoreUap\\Private\\AVCore\\inc\\Spati"...
0x1801109b7  mov     edx, 0ECh; void *
0x1801109bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801109c1  nop
0x1801109c2  lea     rcx, [rsp+0D8h+var_90]; void *
0x1801109c7  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1801109cc  jmp     short loc_18011096F
0x1801109ce  mov     [rsp+0D8h+string], r15
0x1801109d3  mov     rcx, [rsp+0D8h+var_90]
0x1801109d8  mov     rax, [rcx]
0x1801109db  lea     rdx, [rsp+0D8h+string]
0x1801109e0  mov     rax, [rax+98h]
0x1801109e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801109ec  mov     ebx, eax
0x1801109ee  test    eax, eax
0x1801109f0  jns     short loc_180110A1B
0x1801109f2  mov     rcx, [rsp+0D8h]; this
0x1801109fa  mov     r9d, eax; char *
0x1801109fd  lea     r8, aOnecoreuapPriv; "OneCoreUap\\Private\\AVCore\\inc\\Spati"...
0x180110a04  mov     edx, 0EFh; void *
0x180110a09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180110a0e  nop
0x180110a0f  lea     rcx, [rsp+0D8h+string]; this
0x180110a14  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180110a19  jmp     short loc_1801109C2
0x180110a1b  mov     esi, r15d
0x180110a1e  cmp     esi, 7
0x180110a21  jge     loc_180110B8C
0x180110a27  movsxd  rax, esi
0x180110a2a  lea     r15, [rax+rax*4]
0x180110a2e  mov     rdi, [r12+r15*8+8]
0x180110a33  mov     rcx, [rsp+0D8h+string]; string
0x180110a38  call    cs:__imp_WindowsGetStringLen
0x180110a3e  mov     ebx, eax
0x180110a40  xor     edx, edx; length
0x180110a42  mov     rcx, [rsp+0D8h+string]; string
0x180110a47  call    cs:__imp_WindowsGetStringRawBuffer
0x180110a4d  mov     [rsp+0D8h+bIgnoreCase], 1; bIgnoreCase
0x180110a55  or      r9d, 0FFFFFFFFh; cchCount2
0x180110a59  mov     r8, rdi; lpString2
0x180110a5c  mov     edx, ebx; cchCount1
0x180110a5e  mov     rcx, rax; lpString1
0x180110a61  call    cs:__imp_CompareStringOrdinal
0x180110a67  cmp     eax, 2
0x180110a6a  jnz     loc_180110B43
0x180110a70  xor     edi, edi
0x180110a72  mov     [rsp+0D8h+var_A0], rdi
0x180110a77  xor     edx, edx
0x180110a79  lea     rcx, [rsp+0D8h+var_A0]
0x180110a7e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180110a83  lea     rdx, [rsp+0D8h+var_A0]; unsigned __int16 **
0x180110a88  mov     rbx, [rsp+0D8h+var_78]
0x180110a8d  mov     rcx, rbx; unsigned __int16 *
0x180110a90  call    ?GetAppServiceName@@YAJPEBGPEAPEAG@Z; GetAppServiceName(ushort const *,ushort * *)
0x180110a95  test    eax, eax
0x180110a97  js      loc_180110B34
0x180110a9d  mov     byte ptr [r12+r15*8], 1
0x180110aa2  xorps   xmm0, xmm0
0x180110aa5  movdqu  xmmword ptr [rsp+0D8h+var_68], xmm0
0x180110aab  or      r8, 0FFFFFFFFFFFFFFFFh
0x180110aaf  mov     rdx, rbx
0x180110ab2  lea     rcx, [rsp+0D8h+var_80]
0x180110ab7  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180110abc  lea     rdx, [rsp+0D8h+var_80]
0x180110ac1  lea     rcx, [rsp+0D8h+var_68]
0x180110ac6  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180110acb  lea     rcx, [rsp+0D8h+var_80]
0x180110ad0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180110ad5  mov     rdx, [rsp+0D8h+var_A0]
0x180110ada  mov     [rsp+0D8h+var_A0], rdi
0x180110adf  lea     rcx, [rsp+0D8h+var_68+8]
0x180110ae4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180110ae9  nop
0x180110aea  lea     rcx, [r12+10h]
0x180110aef  lea     rcx, [rcx+r15*8]
0x180110af3  mov     rdx, [rcx+8]
0x180110af7  cmp     rdx, [rcx+10h]
0x180110afb  jz      short loc_180110B1F
0x180110afd  mov     rax, [rsp+0D8h+var_68]
0x180110b02  mov     [rdx], rax
0x180110b05  mov     [rsp+0D8h+var_68], rdi
0x180110b0a  mov     rax, [rsp+0D8h+var_68+8]
0x180110b0f  mov     [rdx+8], rax
0x180110b13  mov     [rsp+0D8h+var_68+8], rdi
0x180110b18  add     qword ptr [rcx+8], 10h
0x180110b1d  jmp     short loc_180110B2A
0x180110b1f  lea     r8, [rsp+0D8h+var_68]
0x180110b24  call    ??$_Emplace_reallocate@USpatialAudioAppDetails@@@?$vector@USpatialAudioAppDetails@@V?$allocator@USpatialAudioAppDetails@@@std@@@std@@AEAAPEAUSpatialAudioAppDetails@@QEAU2@$$QEAU2@@Z; std::vector<SpatialAudioAppDetails>::_Emplace_reallocate<SpatialAudioAppDetails>(SpatialAudioAppDetails * const,SpatialAudioAppDetails &&)
0x180110b29  nop
0x180110b2a  lea     rcx, [rsp+0D8h+var_68]; this
0x180110b2f  call    ??1SpatialAudioAppDetails@@QEAA@XZ; SpatialAudioAppDetails::~SpatialAudioAppDetails(void)
0x180110b34  mov     byte ptr [r13+0], 1
0x180110b39  lea     rcx, [rsp+0D8h+var_A0]
0x180110b3e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180110b43  inc     esi
0x180110b45  jmp     loc_180110A1E
0x180110b4a  lea     rcx, [rsp+0D8h+var_68]; this
0x180110b4f  call    ??1SpatialAudioAppDetails@@QEAA@XZ; SpatialAudioAppDetails::~SpatialAudioAppDetails(void)
0x180110b54  nop
0x180110b55  lea     rcx, [rsp+0D8h+var_A0]
0x180110b5a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180110b5f  nop
0x180110b60  lea     rcx, [rsp+0D8h+string]; this
0x180110b65  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180110b6a  nop
0x180110b6b  lea     rcx, [rsp+0D8h+var_90]; void *
0x180110b70  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180110b75  nop
0x180110b76  lea     rcx, [rsp+0D8h+var_A8]; void *
0x180110b7b  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180110b80  mov     ebx, 8007000Eh
0x180110b85  mov     r14, [rsp+0D8h+var_70]
0x180110b8a  jmp     short loc_180110BAE
0x180110b8c  lea     rcx, [rsp+0D8h+string]; this
0x180110b91  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180110b96  nop
0x180110b97  lea     rcx, [rsp+0D8h+var_90]; void *
0x180110b9c  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180110ba1  nop
0x180110ba2  lea     rcx, [rsp+0D8h+var_A8]; void *
0x180110ba7  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180110bac  xor     ebx, ebx
0x180110bae  lea     rcx, [rsp+0D8h+var_88]; void *
0x180110bb3  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180110bb8  nop
0x180110bb9  mov     rcx, r14; void *
0x180110bbc  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180110bc1  mov     eax, ebx
0x180110bc3  mov     rcx, [rsp+0D8h+var_48]
0x180110bcb  xor     rcx, rsp; StackCookie
0x180110bce  call    __security_check_cookie
0x180110bd3  add     rsp, 0A0h
0x180110bda  pop     r15
0x180110bdc  pop     r14
0x180110bde  pop     r13
0x180110be0  pop     r12
0x180110be2  pop     rdi
0x180110be3  pop     rsi
0x180110be4  pop     rbx
0x180110be5  retn
```
