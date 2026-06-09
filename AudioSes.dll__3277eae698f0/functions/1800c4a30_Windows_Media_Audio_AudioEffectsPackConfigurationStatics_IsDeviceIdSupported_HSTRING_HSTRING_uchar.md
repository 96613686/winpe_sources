# Windows::Media::Audio::AudioEffectsPackConfigurationStatics::IsDeviceIdSupported(HSTRING__ *,HSTRING__ *,uchar *)

- ea: `0x1800c4a30`
- end: `0x1800c4d25`
- name: `?IsDeviceIdSupported@AudioEffectsPackConfigurationStatics@Audio@Media@Windows@@UEAAJPEAUHSTRING__@@0PEAE@Z`
- size: `757`
- prototype: `int(Windows::Media::Audio::AudioEffectsPackConfigurationStatics *__hidden this, HSTRING, HSTRING, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c511c`

## callees

- `0x180007f00`
- `0x18000cb1c`
- `0x180010a90`
- `0x180020764`
- `0x180043bc0`
- `0x180054b90`
- `0x18005855c`
- `0x180087e80`
- `0x18008ac8d`
- `0x1800c4a30`
- `0x180123010`

## import_xrefs

- `MMDevAPI!__imp_mmdDevGetMMDeviceIdFromInterfaceId` at `0x1800c4ad4`
- `MMDevAPI!__imp_mmdDevGetMMDeviceIdFromInterfaceId` at `0x1800c4ad4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c4b22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c4b22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4a93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4ac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4a93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4ac7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800c4aa0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800c4aa0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c4b70`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c4b70`

## string_xrefs

- `0x1800c4a6c`: `avcore\audiocore\client\audioeffectspackconfiguration\lib\audioeffectspackconfiguration.cpp`
- `0x1800c4ae7`: `avcore\audiocore\client\audioeffectspackconfiguration\lib\audioeffectspackconfiguration.cpp`
- `0x1800c4b35`: `avcore\audiocore\client\audioeffectspackconfiguration\lib\audioeffectspackconfiguration.cpp`
- `0x1800c4b83`: `avcore\audiocore\client\audioeffectspackconfiguration\lib\audioeffectspackconfiguration.cpp`
- `0x1800c4bf0`: `avcore\audiocore\client\audioeffectspackconfiguration\lib\audioeffectspackconfiguration.cpp`
- `0x1800c4ce5`: `avcore\audiocore\client\audioeffectspackconfiguration\lib\audioeffectspackconfiguration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Media::Audio::AudioEffectsPackConfigurationStatics::IsDeviceIdSupported(
        Windows::Media::Audio::AudioEffectsPackConfigurationStatics *this,
        HSTRING a2,
        HSTRING a3,
        unsigned __int8 *a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  const OLECHAR *StringRawBuffer; // rax
  PCWSTR v9; // rax
  int MMDeviceIdFromInterfaceId; // eax
  __int64 v11; // rdx
  HRESULT v12; // eax
  const unsigned __int16 *v13; // rdx
  _QWORD *v14; // rax
  int ActivationFactory; // eax
  __int64 v16; // rax
  int v17; // eax
  unsigned int i; // ebx
  __int64 v19; // rax
  int v20; // edi
  __int64 v22; // rdx
  HSTRING string; // [rsp+20h] [rbp-39h] BYREF
  __int64 *v24; // [rsp+28h] [rbp-31h] BYREF
  __int64 v25; // [rsp+30h] [rbp-29h] BYREF
  __int64 *v26; // [rsp+38h] [rbp-21h] BYREF
  unsigned int v27; // [rsp+40h] [rbp-19h] BYREF
  PCNZWCH sourceString; // [rsp+48h] [rbp-11h] BYREF
  GUID pclsid; // [rsp+50h] [rbp-9h] BYREF
  HSTRING Buf1[4]; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( a4 )
  {
    *a4 = 0;
    pclsid = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    v6 = CLSIDFromString(StringRawBuffer, &pclsid);
    if ( (v6 & 0x80000000) != 0 )
    {
      v7 = 157;
      goto LABEL_3;
    }
    sourceString = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &sourceString,
      0);
    v9 = WindowsGetStringRawBuffer(a3, 0);
    MMDeviceIdFromInterfaceId = mmdDevGetMMDeviceIdFromInterfaceId(v9, &sourceString);
    v6 = MMDeviceIdFromInterfaceId;
    if ( MMDeviceIdFromInterfaceId >= 0 )
    {
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v11 = -1;
      do
        ++v11;
      while ( sourceString[v11] );
      v12 = WindowsCreateString(sourceString, v11, &string);
      v6 = v12;
      if ( v12 >= 0 )
      {
        v26 = 0;
        v14 = (_QWORD *)Windows::Internal::StringReference::StringReference(Buf1, (const unsigned __int16 (*)[41])v13);
        ActivationFactory = RoGetActivationFactory(*v14, &GUID_ab3d4648_e242_459f_b02f_541c70306324, &v26);
        v6 = ActivationFactory;
        if ( ActivationFactory >= 0 )
        {
          v24 = 0;
          v16 = *v26;
          v24 = 0;
          if ( (*(int (__fastcall **)(__int64 *, HSTRING, __int64 **))(v16 + 312))(v26, string, &v24) < 0 )
          {
LABEL_26:
            wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v24);
            wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v26);
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            v6 = 0;
            goto LABEL_27;
          }
          v27 = 0;
          v17 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v24 + 56))(v24, &v27);
          v6 = v17;
          if ( v17 >= 0 )
          {
            for ( i = 0; ; ++i )
            {
              if ( i >= v27 )
                goto LABEL_26;
              v25 = 0;
              v19 = *v24;
              v25 = 0;
              v20 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v19 + 48))(v24, i, &v25);
              if ( v20 < 0 )
                break;
              *(GUID *)Buf1 = GUID_00000000_0000_0000_0000_000000000000;
              v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 48LL))(v25, Buf1);
              if ( v20 < 0 )
              {
                v22 = 187;
LABEL_31:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v22,
                  (unsigned int)"avcore\\audiocore\\client\\audioeffectspackconfiguration\\lib\\audioeffectspackconfiguration.cpp",
                  (const char *)(unsigned int)v20,
                  (int)string);
                wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v25);
                wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v24);
                wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v26);
                Windows::Internal::String::~String((Windows::Internal::String *)&string);
                v6 = v20;
                goto LABEL_27;
              }
              if ( !memcmp_0(Buf1, &pclsid, 0x10u) )
              {
                *a4 = 1;
                wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v25);
                goto LABEL_26;
              }
              wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v25);
            }
            v22 = 184;
            goto LABEL_31;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB3,
            (unsigned int)"avcore\\audiocore\\client\\audioeffectspackconfiguration\\lib\\audioeffectspackconfiguration.cpp",
            (const char *)(unsigned int)v17,
            (int)string);
          wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v24);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAD,
            (unsigned int)"avcore\\audiocore\\client\\audioeffectspackconfiguration\\lib\\audioeffectspackconfiguration.cpp",
            (const char *)(unsigned int)ActivationFactory,
            (int)string);
        }
        wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v26);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA7,
          (unsigned int)"avcore\\audiocore\\client\\audioeffectspackconfiguration\\lib\\audioeffectspackconfiguration.cpp",
          (const char *)(unsigned int)v12,
          (int)string);
      }
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"avcore\\audiocore\\client\\audioeffectspackconfiguration\\lib\\audioeffectspackconfiguration.cpp",
        (const char *)(unsigned int)MMDeviceIdFromInterfaceId,
        (int)string);
    }
LABEL_27:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&sourceString);
    return v6;
  }
  v6 = -2147024809;
  v7 = 153;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"avcore\\audiocore\\client\\audioeffectspackconfiguration\\lib\\audioeffectspackconfiguration.cpp",
    (const char *)v6,
    (int)string);
  return v6;
}

```

## disassembly

```asm
0x1800c4a30  push    rbp
0x1800c4a32  push    rbx
0x1800c4a33  push    rsi
0x1800c4a34  push    rdi
0x1800c4a35  push    r14
0x1800c4a37  lea     rbp, [rsp-37h]
0x1800c4a3c  sub     rsp, 90h
0x1800c4a43  mov     rax, cs:__security_cookie
0x1800c4a4a  xor     rax, rsp
0x1800c4a4d  mov     [rbp+57h+var_30], rax
0x1800c4a51  mov     rsi, r9
0x1800c4a54  mov     rdi, r8
0x1800c4a57  mov     rax, rdx
0x1800c4a5a  xor     r14d, r14d
0x1800c4a5d  test    r9, r9
0x1800c4a60  jnz     short loc_1800C4A84
0x1800c4a62  mov     ebx, 80070057h
0x1800c4a67  mov     edx, 99h; void *
0x1800c4a6c  lea     r8, aAvcoreAudiocor_37; "avcore\\audiocore\\client\\audioeffects"...
0x1800c4a73  mov     r9d, ebx; char *
0x1800c4a76  mov     rcx, [rbp+5Fh]; this
0x1800c4a7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4a7f  jmp     loc_1800C4CBD
0x1800c4a84  mov     [r9], r14b
0x1800c4a87  xorps   xmm0, xmm0
0x1800c4a8a  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x1800c4a8e  xor     edx, edx; length
0x1800c4a90  mov     rcx, rax; string
0x1800c4a93  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c4a99  mov     rcx, rax; lpsz
0x1800c4a9c  lea     rdx, [rbp+57h+pclsid]; pclsid
0x1800c4aa0  call    cs:__imp_CLSIDFromString
0x1800c4aa6  mov     ebx, eax
0x1800c4aa8  test    eax, eax
0x1800c4aaa  jns     short loc_1800C4AB3
0x1800c4aac  mov     edx, 9Dh
0x1800c4ab1  jmp     short loc_1800C4A6C
0x1800c4ab3  mov     [rbp+57h+sourceString], r14
0x1800c4ab7  xor     edx, edx
0x1800c4ab9  lea     rcx, [rbp+57h+sourceString]
0x1800c4abd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c4ac2  xor     edx, edx; length
0x1800c4ac4  mov     rcx, rdi; string
0x1800c4ac7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c4acd  lea     rdx, [rbp+57h+sourceString]
0x1800c4ad1  mov     rcx, rax
0x1800c4ad4  call    cs:__imp_mmdDevGetMMDeviceIdFromInterfaceId
0x1800c4ada  mov     ebx, eax
0x1800c4adc  test    eax, eax
0x1800c4ade  jns     short loc_1800C4AFD
0x1800c4ae0  mov     rcx, [rbp+5Fh]; this
0x1800c4ae4  mov     r9d, eax; char *
0x1800c4ae7  lea     r8, aAvcoreAudiocor_37; "avcore\\audiocore\\client\\audioeffects"...
0x1800c4aee  mov     edx, 0A0h; void *
0x1800c4af3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4af8  jmp     loc_1800C4CB4
0x1800c4afd  mov     [rbp+57h+string], r14
0x1800c4b01  xor     edx, edx
0x1800c4b03  lea     rcx, [rbp+57h+string]
0x1800c4b07  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800c4b0c  mov     rcx, [rbp+57h+sourceString]; sourceString
0x1800c4b10  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800c4b14  inc     rdx; length
0x1800c4b17  cmp     [rcx+rdx*2], r14w
0x1800c4b1c  jnz     short loc_1800C4B14
0x1800c4b1e  lea     r8, [rbp+57h+string]; string
0x1800c4b22  call    cs:__imp_WindowsCreateString
0x1800c4b28  mov     ebx, eax
0x1800c4b2a  test    eax, eax
0x1800c4b2c  jns     short loc_1800C4B55
0x1800c4b2e  mov     rcx, [rbp+5Fh]; this
0x1800c4b32  mov     r9d, eax; char *
0x1800c4b35  lea     r8, aAvcoreAudiocor_37; "avcore\\audiocore\\client\\audioeffects"...
0x1800c4b3c  mov     edx, 0A7h; void *
0x1800c4b41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4b46  nop
0x1800c4b47  lea     rcx, [rbp+57h+string]; this
0x1800c4b4b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800c4b50  jmp     loc_1800C4CB4
0x1800c4b55  mov     [rbp+57h+var_78], r14
0x1800c4b59  lea     rcx, [rbp+57h+Buf1]; string
0x1800c4b5d  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x1800c4b62  lea     r8, [rbp+57h+var_78]
0x1800c4b66  lea     rdx, _GUID_ab3d4648_e242_459f_b02f_541c70306324
0x1800c4b6d  mov     rcx, [rax]
0x1800c4b70  call    cs:__imp_RoGetActivationFactory
0x1800c4b76  mov     ebx, eax
0x1800c4b78  test    eax, eax
0x1800c4b7a  jns     short loc_1800C4BA0
0x1800c4b7c  mov     rcx, [rbp+5Fh]; this
0x1800c4b80  mov     r9d, eax; char *
0x1800c4b83  lea     r8, aAvcoreAudiocor_37; "avcore\\audiocore\\client\\audioeffects"...
0x1800c4b8a  mov     edx, 0ADh; void *
0x1800c4b8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4b94  nop
0x1800c4b95  lea     rcx, [rbp+57h+var_78]; void *
0x1800c4b99  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800c4b9e  jmp     short loc_1800C4B47
0x1800c4ba0  mov     [rbp+57h+var_88], r14
0x1800c4ba4  mov     rcx, [rbp+57h+var_78]
0x1800c4ba8  mov     rax, [rcx]
0x1800c4bab  mov     [rbp+57h+var_88], r14
0x1800c4baf  lea     r8, [rbp+57h+var_88]
0x1800c4bb3  mov     rdx, [rbp+57h+string]
0x1800c4bb7  mov     rax, [rax+138h]
0x1800c4bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4bc3  test    eax, eax
0x1800c4bc5  js      loc_1800C4C94
0x1800c4bcb  mov     [rbp+57h+var_70], r14d
0x1800c4bcf  mov     rcx, [rbp+57h+var_88]
0x1800c4bd3  mov     rax, [rcx]
0x1800c4bd6  lea     rdx, [rbp+57h+var_70]
0x1800c4bda  mov     rax, [rax+38h]
0x1800c4bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4be3  mov     ebx, eax
0x1800c4be5  test    eax, eax
0x1800c4be7  jns     short loc_1800C4C0D
0x1800c4be9  mov     rcx, [rbp+5Fh]; this
0x1800c4bed  mov     r9d, eax; char *
0x1800c4bf0  lea     r8, aAvcoreAudiocor_37; "avcore\\audiocore\\client\\audioeffects"...
0x1800c4bf7  mov     edx, 0B3h; void *
0x1800c4bfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4c01  nop
0x1800c4c02  lea     rcx, [rbp+57h+var_88]; void *
0x1800c4c06  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800c4c0b  jmp     short loc_1800C4B95
0x1800c4c0d  mov     ebx, r14d
0x1800c4c10  cmp     ebx, [rbp+57h+var_70]
0x1800c4c13  jnb     short loc_1800C4C94
0x1800c4c15  mov     [rbp+57h+var_80], r14
0x1800c4c19  mov     rcx, [rbp+57h+var_88]
0x1800c4c1d  mov     rax, [rcx]
0x1800c4c20  mov     [rbp+57h+var_80], r14
0x1800c4c24  lea     r8, [rbp+57h+var_80]
0x1800c4c28  mov     edx, ebx
0x1800c4c2a  mov     rax, [rax+30h]
0x1800c4c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4c33  mov     edi, eax
0x1800c4c35  test    eax, eax
0x1800c4c37  js      loc_1800C4CE0
0x1800c4c3d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800c4c44  movdqu  xmmword ptr [rbp+57h+Buf1], xmm0
0x1800c4c49  mov     rcx, [rbp+57h+var_80]
0x1800c4c4d  mov     rax, [rcx]
0x1800c4c50  lea     rdx, [rbp+57h+Buf1]
0x1800c4c54  mov     rax, [rax+30h]
0x1800c4c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4c5d  mov     edi, eax
0x1800c4c5f  test    eax, eax
0x1800c4c61  js      short loc_1800C4CD9
0x1800c4c63  mov     r8d, 10h; Size
0x1800c4c69  lea     rdx, [rbp+57h+pclsid]; Buf2
0x1800c4c6d  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800c4c71  call    memcmp_0
0x1800c4c76  test    eax, eax
0x1800c4c78  jz      short loc_1800C4C87
0x1800c4c7a  lea     rcx, [rbp+57h+var_80]; void *
0x1800c4c7e  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800c4c83  inc     ebx
0x1800c4c85  jmp     short loc_1800C4C10
0x1800c4c87  mov     byte ptr [rsi], 1
0x1800c4c8a  lea     rcx, [rbp+57h+var_80]; void *
0x1800c4c8e  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800c4c93  nop
0x1800c4c94  lea     rcx, [rbp+57h+var_88]; void *
0x1800c4c98  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800c4c9d  nop
0x1800c4c9e  lea     rcx, [rbp+57h+var_78]; void *
0x1800c4ca2  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800c4ca7  nop
0x1800c4ca8  lea     rcx, [rbp+57h+string]; this
0x1800c4cac  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800c4cb1  mov     ebx, r14d
0x1800c4cb4  lea     rcx, [rbp+57h+sourceString]
0x1800c4cb8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c4cbd  mov     eax, ebx
0x1800c4cbf  mov     rcx, [rbp+57h+var_30]
0x1800c4cc3  xor     rcx, rsp; StackCookie
0x1800c4cc6  call    __security_check_cookie
0x1800c4ccb  add     rsp, 90h
0x1800c4cd2  pop     r14
0x1800c4cd4  pop     rdi
0x1800c4cd5  pop     rsi
0x1800c4cd6  pop     rbx
0x1800c4cd7  pop     rbp
0x1800c4cd8  retn
0x1800c4cd9  mov     edx, 0BBh
0x1800c4cde  jmp     short loc_1800C4CE5
0x1800c4ce0  mov     edx, 0B8h; void *
0x1800c4ce5  lea     r8, aAvcoreAudiocor_37; "avcore\\audiocore\\client\\audioeffects"...
0x1800c4cec  mov     r9d, edi; char *
0x1800c4cef  mov     rcx, [rbp+5Fh]; this
0x1800c4cf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4cf8  nop
0x1800c4cf9  lea     rcx, [rbp+57h+var_80]; void *
0x1800c4cfd  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800c4d02  nop
0x1800c4d03  lea     rcx, [rbp+57h+var_88]; void *
0x1800c4d07  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800c4d0c  nop
0x1800c4d0d  lea     rcx, [rbp+57h+var_78]; void *
0x1800c4d11  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800c4d16  nop
0x1800c4d17  lea     rcx, [rbp+57h+string]; this
0x1800c4d1b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800c4d20  mov     ebx, edi
0x1800c4d22  jmp     short loc_1800C4CB4
```
