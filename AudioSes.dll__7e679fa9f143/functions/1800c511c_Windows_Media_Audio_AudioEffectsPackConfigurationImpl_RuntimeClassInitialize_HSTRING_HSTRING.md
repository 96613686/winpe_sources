# Windows::Media::Audio::AudioEffectsPackConfigurationImpl::RuntimeClassInitialize(HSTRING__ *,HSTRING__ *)

- ea: `0x1800c511c`
- end: `0x1800c54cc`
- name: `?RuntimeClassInitialize@AudioEffectsPackConfigurationImpl@Audio@Media@Windows@@QEAAJPEAUHSTRING__@@0@Z`
- size: `944`
- prototype: `__int64 __fastcall(Windows::Media::Audio::AudioEffectsPackConfigurationImpl *__hidden this, HSTRING, HSTRING)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18008b380`

## callees

- `0x18000479c`
- `0x18000cb1c`
- `0x18000cd10`
- `0x18000d11c`
- `0x180010a90`
- `0x180020764`
- `0x18002f388`
- `0x180054b90`
- `0x18005855c`
- `0x1800858e0`
- `0x180087e80`
- `0x18008bd48`
- `0x1800c41e4`
- `0x1800c4a30`
- `0x1800c511c`
- `0x180123010`

## import_xrefs

- `MMDevAPI!__imp_mmdDevGetMMDeviceIdFromInterfaceId` at `0x1800c5249`
- `MMDevAPI!__imp_mmdDevGetMMDeviceIdFromInterfaceId` at `0x1800c5249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c51c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c5206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c51c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c5206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c52a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c52a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c5154`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c523b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c52b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c5422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c5432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c5443`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c5154`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c523b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c52b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c5422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c5432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c5443`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c5336`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c5336`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800c5161`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800c5161`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c53d2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c53d2`

## string_xrefs

- `0x1800c5174`: `avcore\audiocore\client\audioeffectspackconfiguration\lib\audioeffectspackconfiguration.cpp`
- `0x1800c51e1`: `avcore\audiocore\client\audioeffectspackconfiguration\lib\audioeffectspackconfiguration.cpp`
- `0x1800c525a`: `avcore\audiocore\client\audioeffectspackconfiguration\lib\audioeffectspackconfiguration.cpp`
- `0x1800c5349`: `avcore\audiocore\client\audioeffectspackconfiguration\lib\audioeffectspackconfiguration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Media::Audio::AudioEffectsPackConfigurationImpl::RuntimeClassInitialize(
        Windows::Media::Audio::AudioEffectsPackConfigurationImpl *this,
        HSTRING a2,
        HSTRING a3)
{
  const OLECHAR *StringRawBuffer; // rax
  HRESULT v7; // eax
  unsigned int v8; // ebx
  HRESULT IsDeviceIdSupported; // eax
  __int64 v10; // rdx
  PCWSTR v11; // rax
  HRESULT MMDeviceIdFromInterfaceId; // eax
  __int64 v13; // rdx
  HSTRING *v14; // r14
  __int64 v15; // rdx
  __int64 v16; // rcx
  HRESULT Instance; // eax
  HRESULT v18; // esi
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rcx
  _QWORD *v21; // rax
  _DWORD *v22; // rbx
  int v23; // r8d
  int v24; // r9d
  int ppv; // [rsp+20h] [rbp-E0h]
  PCNZWCH sourceString; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR v28; // [rsp+48h] [rbp-B8h] BYREF
  Windows::Media::Audio::AudioEffectsPackConfigurationImpl *v29; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR v30; // [rsp+58h] [rbp-A8h] BYREF
  PCWSTR v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v34[44]; // [rsp+98h] [rbp-68h] BYREF
  int v35; // [rsp+C4h] [rbp-3Ch]
  HSTRING string; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v7 = CLSIDFromString(StringRawBuffer, (LPCLSID)((char *)this + 104));
  v8 = v7;
  if ( v7 >= 0 )
  {
    Windows::Media::Audio::AudioEffectsPackConfigurationStatics::AudioEffectsPackConfigurationStatics((Windows::Media::Audio::AudioEffectsPackConfigurationStatics *)v32);
    IsDeviceIdSupported = Windows::Media::Audio::AudioEffectsPackConfigurationStatics::IsDeviceIdSupported(
                            (Windows::Media::Audio::AudioEffectsPackConfigurationStatics *)v34,
                            a2,
                            a3,
                            (unsigned __int8 *)this + 88);
    v8 = IsDeviceIdSupported;
    if ( IsDeviceIdSupported < 0 )
    {
      v10 = 105;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"avcore\\audiocore\\client\\audioeffectspackconfiguration\\lib\\audioeffectspackconfiguration.cpp",
        (const char *)(unsigned int)IsDeviceIdSupported,
        ppv);
LABEL_36:
      v35 = -1073741823;
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(v33);
      return v8;
    }
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      (char *)this + 72,
      0);
    IsDeviceIdSupported = WindowsDuplicateString(a3, (HSTRING *)this + 9);
    v8 = IsDeviceIdSupported;
    if ( IsDeviceIdSupported < 0 )
    {
      v10 = 107;
      goto LABEL_7;
    }
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      (char *)this + 96,
      0);
    IsDeviceIdSupported = WindowsDuplicateString(a2, (HSTRING *)this + 12);
    v8 = IsDeviceIdSupported;
    if ( IsDeviceIdSupported < 0 )
    {
      v10 = 108;
      goto LABEL_7;
    }
    if ( *((_BYTE *)this + 88) )
    {
      sourceString = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &sourceString,
        0);
      v11 = WindowsGetStringRawBuffer(a3, 0);
      MMDeviceIdFromInterfaceId = mmdDevGetMMDeviceIdFromInterfaceId(v11, &sourceString);
      v8 = MMDeviceIdFromInterfaceId;
      if ( MMDeviceIdFromInterfaceId < 0 )
      {
        v13 = 113;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"avcore\\audiocore\\client\\audioeffectspackconfiguration\\lib\\audioeffectspackconfiguration.cpp",
          (const char *)(unsigned int)MMDeviceIdFromInterfaceId,
          ppv);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&sourceString);
        goto LABEL_36;
      }
      v14 = (HSTRING *)((char *)this + 80);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        (char *)this + 80,
        0);
      v15 = -1;
      do
        ++v15;
      while ( sourceString[v15] );
      MMDeviceIdFromInterfaceId = WindowsCreateString(sourceString, v15, (HSTRING *)this + 10);
      v8 = MMDeviceIdFromInterfaceId;
      if ( MMDeviceIdFromInterfaceId < 0 )
      {
        v13 = 119;
        goto LABEL_13;
      }
      v28 = WindowsGetStringRawBuffer(*v14, 0);
      v29 = this;
      wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset((char *)this + 216);
      MMDeviceIdFromInterfaceId = Microsoft::WRL::Details::MakeAndInitialize<Windows::Media::Audio::AudioEffectsPackConfigurationImpl::PropertyChangedEventHandler,Windows::Media::Audio::AudioEffectsPackConfigurationImpl::PropertyChangedEventHandler,Windows::Media::Audio::AudioEffectsPackConfigurationImpl *,unsigned short const *>(
                                    (char *)this + 216,
                                    &v29,
                                    &v28);
      v8 = MMDeviceIdFromInterfaceId;
      if ( MMDeviceIdFromInterfaceId < 0 )
      {
        v13 = 122;
        goto LABEL_13;
      }
      v16 = *((_QWORD *)this + 23);
      *((_QWORD *)this + 23) = 0;
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      Instance = CoCreateInstance(
                   &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
                   0,
                   3u,
                   &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
                   (LPVOID *)this + 23);
      v18 = Instance;
      if ( Instance < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7D,
          (unsigned int)"avcore\\audiocore\\client\\audioeffectspackconfiguration\\lib\\audioeffectspackconfiguration.cpp",
          (const char *)(unsigned int)Instance,
          ppv);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&sourceString);
        v8 = v18;
        goto LABEL_36;
      }
      MMDeviceIdFromInterfaceId = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 23) + 48LL))(
                                    *((_QWORD *)this + 23),
                                    (*((_QWORD *)this + 27) + 8LL) & -(__int64)(*((_QWORD *)this + 27) != 0));
      v8 = MMDeviceIdFromInterfaceId;
      if ( MMDeviceIdFromInterfaceId < 0 )
      {
        v13 = 127;
        goto LABEL_13;
      }
      v20 = *((_QWORD *)this + 22);
      *((_QWORD *)this + 22) = 0;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v21 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[41])v19);
      MMDeviceIdFromInterfaceId = RoGetActivationFactory(
                                    *v21,
                                    &GUID_ab3d4648_e242_459f_b02f_541c70306324,
                                    (char *)this + 176);
      v8 = MMDeviceIdFromInterfaceId;
      if ( MMDeviceIdFromInterfaceId < 0 )
      {
        v13 = 132;
        goto LABEL_13;
      }
      MMDeviceIdFromInterfaceId = Windows::Media::Audio::AudioEffectsPackConfigurationImpl::UpdateCurrentEffectPackId(this);
      v8 = MMDeviceIdFromInterfaceId;
      if ( MMDeviceIdFromInterfaceId < 0 )
      {
        v13 = 134;
        goto LABEL_13;
      }
      v22 = (_DWORD *)*((_QWORD *)AudioSesTelemetryProvider::Instance() + 1);
      if ( *v22 > 5u )
      {
        v29 = (Windows::Media::Audio::AudioEffectsPackConfigurationImpl *)((char *)this + 160);
        v28 = WindowsGetStringRawBuffer(*((HSTRING *)this + 12), 0);
        v30 = WindowsGetStringRawBuffer(*v14, 0);
        v31[0] = WindowsGetStringRawBuffer(*((HSTRING *)this + 9), 0);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
          (_DWORD)v22,
          (unsigned int)&unk_180168DDA,
          v23,
          v24,
          (__int64)v31,
          (__int64)&v30,
          (__int64)&v28,
          (__int64)&v29);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&sourceString);
    }
    v8 = 0;
    goto LABEL_36;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x65,
    (unsigned int)"avcore\\audiocore\\client\\audioeffectspackconfiguration\\lib\\audioeffectspackconfiguration.cpp",
    (const char *)(unsigned int)v7,
    ppv);
  return v8;
}

```

## disassembly

```asm
0x1800c511c  mov     [rsp-8+arg_18], rbx
0x1800c5121  push    rbp
0x1800c5122  push    rsi
0x1800c5123  push    rdi
0x1800c5124  push    r12
0x1800c5126  push    r13
0x1800c5128  push    r14
0x1800c512a  push    r15
0x1800c512c  lea     rbp, [rsp-10h]
0x1800c5131  sub     rsp, 110h
0x1800c5138  mov     rax, cs:__security_cookie
0x1800c513f  xor     rax, rsp
0x1800c5142  mov     [rbp+40h+var_40], rax
0x1800c5146  mov     r14, r8
0x1800c5149  mov     r15, rdx
0x1800c514c  mov     rdi, rcx
0x1800c514f  xor     edx, edx; length
0x1800c5151  mov     rcx, r15; string
0x1800c5154  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c515a  mov     rcx, rax; lpsz
0x1800c515d  lea     rdx, [rdi+68h]; pclsid
0x1800c5161  call    cs:__imp_CLSIDFromString
0x1800c5167  mov     ebx, eax
0x1800c5169  test    eax, eax
0x1800c516b  jns     short loc_1800C518A
0x1800c516d  mov     rcx, [rbp+48h]; this
0x1800c5171  mov     r9d, eax; char *
0x1800c5174  lea     r8, aAvcoreAudiocor_37; "avcore\\audiocore\\client\\audioeffects"...
0x1800c517b  mov     edx, 65h ; 'e'; void *
0x1800c5180  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5185  jmp     loc_1800C54A3
0x1800c518a  lea     rcx, [rsp+140h+var_D0]; this
0x1800c518f  call    ??0AudioEffectsPackConfigurationStatics@Audio@Media@Windows@@QEAA@XZ; Windows::Media::Audio::AudioEffectsPackConfigurationStatics::AudioEffectsPackConfigurationStatics(void)
0x1800c5194  nop
0x1800c5195  lea     r9, [rdi+58h]; unsigned __int8 *
0x1800c5199  mov     r8, r14; HSTRING
0x1800c519c  mov     rdx, r15; HSTRING
0x1800c519f  lea     rcx, [rbp+40h+var_A8]; this
0x1800c51a3  call    ?IsDeviceIdSupported@AudioEffectsPackConfigurationStatics@Audio@Media@Windows@@UEAAJPEAUHSTRING__@@0PEAE@Z; Windows::Media::Audio::AudioEffectsPackConfigurationStatics::IsDeviceIdSupported(HSTRING__ *,HSTRING__ *,uchar *)
0x1800c51a8  mov     ebx, eax
0x1800c51aa  test    eax, eax
0x1800c51ac  jns     short loc_1800C51B5
0x1800c51ae  mov     edx, 69h ; 'i'
0x1800c51b3  jmp     short loc_1800C51DA
0x1800c51b5  lea     r12, [rdi+48h]
0x1800c51b9  xor     edx, edx
0x1800c51bb  mov     rcx, r12
0x1800c51be  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800c51c3  mov     rdx, r12; newString
0x1800c51c6  mov     rcx, r14; string
0x1800c51c9  call    cs:__imp_WindowsDuplicateString
0x1800c51cf  mov     ebx, eax
0x1800c51d1  test    eax, eax
0x1800c51d3  jns     short loc_1800C51F2
0x1800c51d5  mov     edx, 6Bh ; 'k'; void *
0x1800c51da  mov     rcx, [rbp+48h]; this
0x1800c51de  mov     r9d, eax; char *
0x1800c51e1  lea     r8, aAvcoreAudiocor_37; "avcore\\audiocore\\client\\audioeffects"...
0x1800c51e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c51ed  jmp     loc_1800C5493
0x1800c51f2  lea     r13, [rdi+60h]
0x1800c51f6  xor     edx, edx
0x1800c51f8  mov     rcx, r13
0x1800c51fb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800c5200  mov     rdx, r13; newString
0x1800c5203  mov     rcx, r15; string
0x1800c5206  call    cs:__imp_WindowsDuplicateString
0x1800c520c  mov     ebx, eax
0x1800c520e  xor     r15d, r15d
0x1800c5211  test    eax, eax
0x1800c5213  jns     short loc_1800C521B
0x1800c5215  lea     edx, [r15+6Ch]
0x1800c5219  jmp     short loc_1800C51DA
0x1800c521b  cmp     [rdi+58h], r15b
0x1800c521f  jz      loc_1800C5490
0x1800c5225  mov     [rsp+140h+sourceString], r15
0x1800c522a  xor     edx, edx
0x1800c522c  lea     rcx, [rsp+140h+sourceString]
0x1800c5231  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c5236  xor     edx, edx; length
0x1800c5238  mov     rcx, r14; string
0x1800c523b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c5241  lea     rdx, [rsp+140h+sourceString]
0x1800c5246  mov     rcx, rax
0x1800c5249  call    cs:__imp_mmdDevGetMMDeviceIdFromInterfaceId
0x1800c524f  mov     ebx, eax
0x1800c5251  test    eax, eax
0x1800c5253  jns     short loc_1800C527D
0x1800c5255  mov     edx, 71h ; 'q'; void *
0x1800c525a  lea     r8, aAvcoreAudiocor_37; "avcore\\audiocore\\client\\audioeffects"...
0x1800c5261  mov     r9d, eax; char *
0x1800c5264  mov     rcx, [rbp+48h]; this
0x1800c5268  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c526d  nop
0x1800c526e  lea     rcx, [rsp+140h+sourceString]
0x1800c5273  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c5278  jmp     loc_1800C5493
0x1800c527d  lea     r14, [rdi+50h]
0x1800c5281  xor     edx, edx
0x1800c5283  mov     rcx, r14
0x1800c5286  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800c528b  mov     rcx, [rsp+140h+sourceString]; sourceString
0x1800c5290  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800c5294  inc     rdx; length
0x1800c5297  cmp     [rcx+rdx*2], r15w
0x1800c529c  jnz     short loc_1800C5294
0x1800c529e  mov     r8, r14; string
0x1800c52a1  call    cs:__imp_WindowsCreateString
0x1800c52a7  mov     ebx, eax
0x1800c52a9  test    eax, eax
0x1800c52ab  jns     short loc_1800C52B4
0x1800c52ad  mov     edx, 77h ; 'w'
0x1800c52b2  jmp     short loc_1800C525A
0x1800c52b4  xor     edx, edx; length
0x1800c52b6  mov     rcx, [r14]; string
0x1800c52b9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c52bf  mov     [rsp+140h+var_F8], rax
0x1800c52c4  mov     [rsp+140h+var_F0], rdi
0x1800c52c9  lea     r15, [rdi+0D8h]
0x1800c52d0  mov     rcx, r15
0x1800c52d3  call    ?reset@?$com_ptr_t@UIMediaNotificationCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset(void)
0x1800c52d8  lea     r8, [rsp+140h+var_F8]
0x1800c52dd  lea     rdx, [rsp+140h+var_F0]
0x1800c52e2  mov     rcx, r15
0x1800c52e5  call    ??$MakeAndInitialize@VPropertyChangedEventHandler@AudioEffectsPackConfigurationImpl@Audio@Media@Windows@@V12345@PEAV2345@PEBG@Details@WRL@Microsoft@@YAJPEAPEAVPropertyChangedEventHandler@AudioEffectsPackConfigurationImpl@Audio@Media@Windows@@$$QEAPEAV4567@$$QEAPEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Media::Audio::AudioEffectsPackConfigurationImpl::PropertyChangedEventHandler,Windows::Media::Audio::AudioEffectsPackConfigurationImpl::PropertyChangedEventHandler,Windows::Media::Audio::AudioEffectsPackConfigurationImpl *,ushort const *>(Windows::Media::Audio::AudioEffectsPackConfigurationImpl::PropertyChangedEventHandler * *,Windows::Media::Audio::AudioEffectsPackConfigurationImpl * &&,ushort const * &&)
0x1800c52ea  mov     ebx, eax
0x1800c52ec  test    eax, eax
0x1800c52ee  jns     short loc_1800C52FA
0x1800c52f0  mov     edx, 7Ah ; 'z'
0x1800c52f5  jmp     loc_1800C525A
0x1800c52fa  lea     rbx, [rdi+0B8h]
0x1800c5301  mov     rcx, [rbx]
0x1800c5304  mov     qword ptr [rbx], 0
0x1800c530b  test    rcx, rcx
0x1800c530e  jz      short loc_1800C531D
0x1800c5310  mov     rax, [rcx]
0x1800c5313  mov     rax, [rax+10h]
0x1800c5317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c531c  nop
0x1800c531d  mov     [rsp+140h+ppv], rbx; int
0x1800c5322  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1800c5329  xor     edx, edx; pUnkOuter
0x1800c532b  lea     r8d, [rdx+3]; dwClsContext
0x1800c532f  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x1800c5336  call    cs:__imp_CoCreateInstance
0x1800c533c  mov     esi, eax
0x1800c533e  test    eax, eax
0x1800c5340  jns     short loc_1800C536C
0x1800c5342  mov     rcx, [rbp+48h]; this
0x1800c5346  mov     r9d, eax; char *
0x1800c5349  lea     r8, aAvcoreAudiocor_37; "avcore\\audiocore\\client\\audioeffects"...
0x1800c5350  mov     edx, 7Dh ; '}'; void *
0x1800c5355  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c535a  nop
0x1800c535b  lea     rcx, [rsp+140h+sourceString]
0x1800c5360  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c5365  mov     ebx, esi
0x1800c5367  jmp     loc_1800C5493
0x1800c536c  mov     rcx, [rbx]
0x1800c536f  mov     rdx, [r15]
0x1800c5372  mov     r8, [rcx]
0x1800c5375  lea     rax, [rdx+8]
0x1800c5379  neg     rdx
0x1800c537c  sbb     rdx, rdx
0x1800c537f  and     rdx, rax
0x1800c5382  mov     rax, [r8+30h]
0x1800c5386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c538b  mov     ebx, eax
0x1800c538d  xor     r15d, r15d
0x1800c5390  test    eax, eax
0x1800c5392  jns     short loc_1800C539D
0x1800c5394  lea     edx, [r15+7Fh]
0x1800c5398  jmp     loc_1800C525A
0x1800c539d  lea     rbx, [rdi+0B0h]
0x1800c53a4  mov     rcx, [rbx]
0x1800c53a7  mov     [rbx], r15
0x1800c53aa  test    rcx, rcx
0x1800c53ad  jz      short loc_1800C53BC
0x1800c53af  mov     rax, [rcx]
0x1800c53b2  mov     rax, [rax+10h]
0x1800c53b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c53bb  nop
0x1800c53bc  lea     rcx, [rbp+40h+string]; string
0x1800c53c0  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x1800c53c5  mov     r8, rbx
0x1800c53c8  lea     rdx, _GUID_ab3d4648_e242_459f_b02f_541c70306324
0x1800c53cf  mov     rcx, [rax]
0x1800c53d2  call    cs:__imp_RoGetActivationFactory
0x1800c53d8  mov     ebx, eax
0x1800c53da  test    eax, eax
0x1800c53dc  jns     short loc_1800C53E8
0x1800c53de  mov     edx, 84h
0x1800c53e3  jmp     loc_1800C525A
0x1800c53e8  mov     rcx, rdi; this
0x1800c53eb  call    ?UpdateCurrentEffectPackId@AudioEffectsPackConfigurationImpl@Audio@Media@Windows@@AEAAJXZ; Windows::Media::Audio::AudioEffectsPackConfigurationImpl::UpdateCurrentEffectPackId(void)
0x1800c53f0  mov     ebx, eax
0x1800c53f2  test    eax, eax
0x1800c53f4  jns     short loc_1800C5400
0x1800c53f6  mov     edx, 86h
0x1800c53fb  jmp     loc_1800C525A
0x1800c5400  call    ?Instance@AudioSesTelemetryProvider@@KAPEAV1@XZ; AudioSesTelemetryProvider::Instance(void)
0x1800c5405  mov     rbx, [rax+8]
0x1800c5409  mov     eax, [rbx]
0x1800c540b  cmp     eax, 5
0x1800c540e  jbe     short loc_1800C5486
0x1800c5410  lea     rax, [rdi+0A0h]
0x1800c5417  mov     [rsp+140h+var_F0], rax
0x1800c541c  xor     edx, edx; length
0x1800c541e  mov     rcx, [r13+0]; string
0x1800c5422  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c5428  mov     [rsp+140h+var_F8], rax
0x1800c542d  xor     edx, edx; length
0x1800c542f  mov     rcx, [r14]; string
0x1800c5432  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c5438  mov     [rsp+140h+var_E8], rax
0x1800c543d  xor     edx, edx; length
0x1800c543f  mov     rcx, [r12]; string
0x1800c5443  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c5449  mov     [rsp+140h+var_E0], rax
0x1800c544e  lea     rax, [rsp+140h+var_F0]
0x1800c5453  mov     [rsp+140h+var_108], rax
0x1800c5458  lea     rax, [rsp+140h+var_F8]
0x1800c545d  mov     [rsp+140h+var_110], rax
0x1800c5462  lea     rax, [rsp+140h+var_E8]
0x1800c5467  mov     [rsp+140h+var_118], rax
0x1800c546c  lea     rax, [rsp+140h+var_E0]
0x1800c5471  mov     [rsp+140h+ppv], rax
0x1800c5476  lea     rdx, unk_180168DDA
0x1800c547d  mov     rcx, rbx
0x1800c5480  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x1800c5485  nop
0x1800c5486  lea     rcx, [rsp+140h+sourceString]
0x1800c548b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c5490  mov     ebx, r15d
0x1800c5493  mov     [rbp+40h+var_7C], 0C0000001h
0x1800c549a  lea     rcx, [rbp+40h+var_B0]
0x1800c549e  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800c54a3  mov     eax, ebx
0x1800c54a5  mov     rcx, [rbp+40h+var_40]
0x1800c54a9  xor     rcx, rsp; StackCookie
0x1800c54ac  call    __security_check_cookie
0x1800c54b1  mov     rbx, [rsp+140h+arg_18]
0x1800c54b9  add     rsp, 110h
0x1800c54c0  pop     r15
0x1800c54c2  pop     r14
0x1800c54c4  pop     r13
0x1800c54c6  pop     r12
0x1800c54c8  pop     rdi
0x1800c54c9  pop     rsi
0x1800c54ca  pop     rbp
0x1800c54cb  retn
```
