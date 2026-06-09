# Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)

- ea: `0x14000aedc`
- end: `0x14000b07b`
- name: `?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ`
- size: `415`
- prototype: `__int64 __fastcall(Windows::Speech::Session::FlightDataRecorder *__hidden this)`
- caller_count: `10`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004fa8`
- `0x14000509c`
- `0x140005274`
- `0x140005378`
- `0x140005458`
- `0x140008ba4`
- `0x140008c2c`
- `0x140009f70`
- `0x14000cdfc`
- `0x14000f470`

## callees

- `0x140002d30`
- `0x140004e50`
- `0x14000aab8`
- `0x14000aedc`
- `0x14000c32c`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000afbc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000afbc`

## string_xrefs

- `0x14000af91`: `Windows.Data.Json.JsonValue`
- `0x14000af5b`: `Windows.Data.Json.JsonArray`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(
        Windows::Speech::Session::FlightDataRecorder *this)
{
  __int64 *v3; // r15
  __int64 *v4; // r14
  int v5; // eax
  __int64 v6; // rbx
  int ActivationFactory; // eax
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 *v10; // rcx
  __int64 v11; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+28h] [rbp-40h] BYREF
  __int64 v13; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF
  __int64 v15; // [rsp+50h] [rbp-18h]

  if ( !*((_BYTE *)this + 10) && !*((_BYTE *)this + 9) )
    return 2147549183LL;
  if ( *((int *)this + 22) >= 0 )
  {
    v3 = (__int64 *)((char *)this + 72);
    v4 = (__int64 *)((char *)this + 80);
    if ( !*((_QWORD *)this + 9) || !*v4 )
    {
      v12 = 0;
      v11 = 0;
      v15 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonArray",
        0x1Cu,
        0x1Bu);
      v5 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(v15, &v12);
      *((_DWORD *)this + 22) = v5;
      if ( v5 >= 0 )
      {
        v15 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Data.Json.JsonValue",
          0x1Cu,
          0x1Bu);
        v6 = v15;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
        ActivationFactory = RoGetActivationFactory(v6, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v11);
        *((_DWORD *)this + 22) = ActivationFactory;
        if ( ActivationFactory >= 0 )
        {
          v8 = v12;
          if ( v12 )
          {
            v9 = v11;
            if ( v11 )
            {
              if ( *v3 != v12 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
                v13 = *v3;
                *v3 = v8;
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v13);
                v9 = v11;
              }
              if ( *v4 == v9 )
                goto LABEL_20;
              if ( v9 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
              v13 = *v4;
              *v4 = v9;
              v10 = &v13;
LABEL_19:
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v10);
LABEL_20:
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12);
              return *((unsigned int *)this + 22);
            }
          }
          *((_DWORD *)this + 22) = -2147467259;
        }
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v3);
      v10 = v4;
      goto LABEL_19;
    }
  }
  return *((unsigned int *)this + 22);
}

```

## disassembly

```asm
0x14000aedc  push    rbp
0x14000aede  push    rbx
0x14000aedf  push    rsi
0x14000aee0  push    rdi
0x14000aee1  push    r14
0x14000aee3  push    r15
0x14000aee5  mov     rbp, rsp
0x14000aee8  sub     rsp, 68h
0x14000aeec  mov     rax, cs:__security_cookie
0x14000aef3  xor     rax, rsp
0x14000aef6  mov     [rbp+var_10], rax
0x14000aefa  mov     rsi, rcx
0x14000aefd  cmp     byte ptr [rcx+0Ah], 0
0x14000af01  jnz     short loc_14000AF13
0x14000af03  cmp     byte ptr [rcx+9], 0
0x14000af07  jnz     short loc_14000AF13
0x14000af09  mov     eax, 8000FFFFh
0x14000af0e  jmp     loc_14000B062
0x14000af13  cmp     dword ptr [rcx+58h], 0
0x14000af17  jl      loc_14000B05F
0x14000af1d  lea     r15, [rcx+48h]
0x14000af21  lea     r14, [rcx+50h]
0x14000af25  cmp     qword ptr [r15], 0
0x14000af29  jz      short loc_14000AF35
0x14000af2b  cmp     qword ptr [r14], 0
0x14000af2f  jnz     loc_14000B05F
0x14000af35  mov     [rbp+var_40], 0
0x14000af3d  mov     [rbp+var_48], 0
0x14000af45  mov     [rbp+var_18], 0
0x14000af4d  mov     ebx, 1Bh
0x14000af52  mov     r9d, ebx; unsigned int
0x14000af55  lea     edi, [rbx+1]
0x14000af58  mov     r8d, edi; unsigned int
0x14000af5b  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x14000af62  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x14000af66  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14000af6b  lea     rdx, [rbp+var_40]
0x14000af6f  mov     rcx, [rbp+var_18]
0x14000af73  call    ??$ActivateInstance@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>)
0x14000af78  mov     [rsi+58h], eax
0x14000af7b  test    eax, eax
0x14000af7d  js      loc_14000B03D
0x14000af83  mov     [rbp+var_18], 0
0x14000af8b  mov     r9d, ebx; unsigned int
0x14000af8e  mov     r8d, edi; unsigned int
0x14000af91  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x14000af98  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x14000af9c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14000afa1  mov     rbx, [rbp+var_18]
0x14000afa5  lea     rcx, [rbp+var_48]
0x14000afa9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000afae  lea     r8, [rbp+var_48]
0x14000afb2  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x14000afb9  mov     rcx, rbx
0x14000afbc  call    cs:__imp_RoGetActivationFactory
0x14000afc2  mov     [rsi+58h], eax
0x14000afc5  test    eax, eax
0x14000afc7  js      short loc_14000B03D
0x14000afc9  mov     rdi, [rbp+var_40]
0x14000afcd  test    rdi, rdi
0x14000afd0  jz      short loc_14000B036
0x14000afd2  mov     rbx, [rbp+var_48]
0x14000afd6  test    rbx, rbx
0x14000afd9  jz      short loc_14000B036
0x14000afdb  cmp     [r15], rdi
0x14000afde  jz      short loc_14000B00C
0x14000afe0  test    rdi, rdi
0x14000afe3  jz      short loc_14000AFF5
0x14000afe5  mov     rax, [rdi]
0x14000afe8  mov     rcx, rdi
0x14000afeb  mov     rax, [rax+8]
0x14000afef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aff4  nop
0x14000aff5  mov     rax, [r15]
0x14000aff8  mov     [rbp+var_38], rax
0x14000affc  mov     [r15], rdi
0x14000afff  lea     rcx, [rbp+var_38]
0x14000b003  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000b008  mov     rbx, [rbp+var_48]
0x14000b00c  cmp     [r14], rbx
0x14000b00f  jz      short loc_14000B04D
0x14000b011  test    rbx, rbx
0x14000b014  jz      short loc_14000B026
0x14000b016  mov     rax, [rbx]
0x14000b019  mov     rcx, rbx
0x14000b01c  mov     rax, [rax+8]
0x14000b020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b025  nop
0x14000b026  mov     rax, [r14]
0x14000b029  mov     [rbp+var_38], rax
0x14000b02d  mov     [r14], rbx
0x14000b030  lea     rcx, [rbp+var_38]
0x14000b034  jmp     short loc_14000B048
0x14000b036  mov     dword ptr [rsi+58h], 80004005h
0x14000b03d  mov     rcx, r15
0x14000b040  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000b045  mov     rcx, r14
0x14000b048  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000b04d  lea     rcx, [rbp+var_48]
0x14000b051  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000b056  lea     rcx, [rbp+var_40]
0x14000b05a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14000b05f  mov     eax, [rsi+58h]
0x14000b062  mov     rcx, [rbp+var_10]
0x14000b066  xor     rcx, rsp; StackCookie
0x14000b069  call    __security_check_cookie
0x14000b06e  add     rsp, 68h
0x14000b072  pop     r15
0x14000b074  pop     r14
0x14000b076  pop     rdi
0x14000b077  pop     rsi
0x14000b078  pop     rbx
0x14000b079  pop     rbp
0x14000b07a  retn
```
