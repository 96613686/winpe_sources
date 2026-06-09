# SpPerfTelemetry::SpeechRuntime::CoalescedSessionEvent(long)

- ea: `0x140009f70`
- end: `0x14000a180`
- name: `?CoalescedSessionEvent@SpeechRuntime@SpPerfTelemetry@@UEAAXJ@Z`
- size: `528`
- prototype: `void __fastcall(SpPerfTelemetry::SpeechRuntime *__hidden this, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001058`
- `0x1400011c4`
- `0x140001ffc`
- `0x140002d30`
- `0x140009f70`
- `0x14000aedc`
- `0x14000b9f8`
- `0x14000d3ec`
- `0x14000e848`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000a07c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000a0be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000a106`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000a07c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000a0be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000a106`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000a152`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000a152`

## string_xrefs

- `0x14000a0a8`: `{ "Json too long" }`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SpPerfTelemetry::SpeechRuntime::CoalescedSessionEvent(SpPerfTelemetry::SpeechRuntime *this, int a2)
{
  const struct _tlgProvider_t *v4; // rax
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v9; // rdi
  __int64 v10; // rcx
  unsigned int v11; // esi
  PCWSTR v12; // rax
  int v13; // r14d
  const struct _tlgProvider_t *v14; // rax
  int v15; // edi
  unsigned int v16; // [rsp+40h] [rbp-29h] BYREF
  HSTRING string; // [rsp+48h] [rbp-21h] BYREF
  __int64 v18; // [rsp+50h] [rbp-19h] BYREF
  PCWSTR v19; // [rsp+58h] [rbp-11h] BYREF
  int v20; // [rsp+60h] [rbp-9h]
  char v21[32]; // [rsp+68h] [rbp-1h] BYREF
  unsigned int *v22; // [rsp+88h] [rbp+1Fh]
  __int64 v23; // [rsp+90h] [rbp+27h]

  v4 = SpPerfLogging::Provider();
  if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
  {
    if ( (int)Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(this) >= 0 )
    {
      string = 0;
      v7 = *((_QWORD *)this + 9);
      v18 = v7;
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
      Windows::Speech::Session::FlightDataRecorder::GetJsonString(v7, &v18, &string);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v9 = -1;
      v10 = -1;
      do
        ++v10;
      while ( StringRawBuffer[v10] );
      v11 = 2 * v10 + 2;
      if ( v11 <= 0xFA0 )
      {
        v13 = 2 * v10 + 2;
      }
      else
      {
        Microsoft::WRL::Wrappers::HString::Set(&string, L"{ \"Json too long\" }", 0x13u);
        v12 = WindowsGetStringRawBuffer(string, 0);
        do
          ++v9;
        while ( v12[v9] );
        v13 = 2 * v9 + 2;
      }
      v14 = SpPerfLogging::Provider();
      v15 = (int)v14;
      if ( *(_DWORD *)v14 > 4u && (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL) )
      {
        v19 = WindowsGetStringRawBuffer(string, 0);
        v20 = v13;
        v16 = v11;
        LODWORD(v18) = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize>(
          v15,
          (unsigned int)word_140043642,
          (_DWORD)this + 32,
          *((_QWORD *)this + 6),
          (__int64)&v18,
          (__int64)&v16,
          (__int64)&v19);
      }
      WindowsDeleteString(string);
    }
    else
    {
      v5 = SpPerfLogging::Provider();
      v6 = v5;
      if ( *(_DWORD *)v5 > 4u )
      {
        if ( (unsigned __int8)tlgKeywordOn(v5, 1) )
        {
          v16 = Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(this);
          v22 = &v16;
          v23 = 4;
          tlgWriteTransfer_EventWriteTransfer(v6, byte_1400433E9, (char *)this + 32, *((_QWORD *)this + 6), 3, v21);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140009f70  mov     [rsp-8+arg_8], rbx
0x140009f75  mov     [rsp-8+arg_10], rsi
0x140009f7a  push    rbp
0x140009f7b  push    rdi
0x140009f7c  push    r12
0x140009f7e  push    r14
0x140009f80  push    r15
0x140009f82  lea     rbp, [rsp-37h]
0x140009f87  sub     rsp, 0A0h
0x140009f8e  mov     rax, cs:__security_cookie
0x140009f95  xor     rax, rsp
0x140009f98  mov     [rbp+57h+var_28], rax
0x140009f9c  mov     r15d, edx
0x140009f9f  mov     rbx, rcx
0x140009fa2  call    ?Provider@SpPerfLogging@@SAPEBU_tlgProvider_t@@XZ; SpPerfLogging::Provider(void)
0x140009fa7  mov     ecx, [rax]
0x140009fa9  cmp     ecx, 5
0x140009fac  jbe     loc_14000A158
0x140009fb2  mov     rdx, 400000000000h
0x140009fbc  mov     rcx, rax
0x140009fbf  call    _tlgKeywordOn
0x140009fc4  xor     r12d, r12d
0x140009fc7  test    al, al
0x140009fc9  jz      loc_14000A158
0x140009fcf  mov     rcx, rbx; this
0x140009fd2  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x140009fd7  test    eax, eax
0x140009fd9  jns     short loc_14000A04B
0x140009fdb  call    ?Provider@SpPerfLogging@@SAPEBU_tlgProvider_t@@XZ; SpPerfLogging::Provider(void)
0x140009fe0  mov     rdi, rax
0x140009fe3  mov     ecx, [rax]
0x140009fe5  cmp     ecx, 4
0x140009fe8  jbe     loc_14000A158
0x140009fee  lea     edx, [r12+1]
0x140009ff3  mov     rcx, rax
0x140009ff6  call    _tlgKeywordOn
0x140009ffb  test    al, al
0x140009ffd  jz      loc_14000A158
0x14000a003  mov     rcx, rbx; this
0x14000a006  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x14000a00b  mov     [rbp+57h+var_80], eax
0x14000a00e  lea     rax, [rbp+57h+var_80]
0x14000a012  mov     [rbp+57h+var_38], rax
0x14000a016  mov     [rbp+57h+var_30], 4
0x14000a01e  lea     r8, [rbx+20h]
0x14000a022  lea     rax, [rbp+57h+var_58]
0x14000a026  mov     [rsp+0C0h+var_98], rax
0x14000a02b  mov     dword ptr [rsp+0C0h+var_A0], 3
0x14000a033  mov     r9, [rbx+30h]
0x14000a037  lea     rdx, byte_1400433E9
0x14000a03e  mov     rcx, rdi
0x14000a041  call    _tlgWriteTransfer_EventWriteTransfer
0x14000a046  jmp     loc_14000A158
0x14000a04b  mov     [rbp+57h+string], r12
0x14000a04f  mov     rcx, [rbx+48h]
0x14000a053  mov     [rbp+57h+var_70], rcx
0x14000a057  test    rcx, rcx
0x14000a05a  jz      short loc_14000A069
0x14000a05c  mov     rax, [rcx]
0x14000a05f  mov     rax, [rax+8]
0x14000a063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a068  nop
0x14000a069  lea     r8, [rbp+57h+string]
0x14000a06d  lea     rdx, [rbp+57h+var_70]
0x14000a071  call    ?GetJsonString@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEAVHString@Wrappers@67@@Z; Windows::Speech::Session::FlightDataRecorder::GetJsonString(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>,Microsoft::WRL::Wrappers::HString *)
0x14000a076  xor     edx, edx; length
0x14000a078  mov     rcx, [rbp+57h+string]; string
0x14000a07c  call    cs:__imp_WindowsGetStringRawBuffer
0x14000a082  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000a086  mov     rcx, rdi
0x14000a089  inc     rcx
0x14000a08c  cmp     [rax+rcx*2], r12w
0x14000a091  jnz     short loc_14000A089
0x14000a093  lea     esi, ds:2[rcx*2]
0x14000a09a  cmp     esi, 0FA0h
0x14000a0a0  jbe     short loc_14000A0D8
0x14000a0a2  mov     r8d, 13h; unsigned int
0x14000a0a8  lea     rdx, aJsonTooLong; "{ \"Json too long\" }"
0x14000a0af  lea     rcx, [rbp+57h+string]; this
0x14000a0b3  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x14000a0b8  xor     edx, edx; length
0x14000a0ba  mov     rcx, [rbp+57h+string]; string
0x14000a0be  call    cs:__imp_WindowsGetStringRawBuffer
0x14000a0c4  inc     rdi
0x14000a0c7  cmp     [rax+rdi*2], r12w
0x14000a0cc  jnz     short loc_14000A0C4
0x14000a0ce  lea     r14d, ds:2[rdi*2]
0x14000a0d6  jmp     short loc_14000A0DB
0x14000a0d8  mov     r14d, esi
0x14000a0db  call    ?Provider@SpPerfLogging@@SAPEBU_tlgProvider_t@@XZ; SpPerfLogging::Provider(void)
0x14000a0e0  mov     rdi, rax
0x14000a0e3  mov     ecx, [rax]
0x14000a0e5  cmp     ecx, 4
0x14000a0e8  jbe     short loc_14000A14E
0x14000a0ea  mov     rdx, 400000000000h
0x14000a0f4  mov     rcx, rax
0x14000a0f7  call    _tlgKeywordOn
0x14000a0fc  test    al, al
0x14000a0fe  jz      short loc_14000A14E
0x14000a100  xor     edx, edx; length
0x14000a102  mov     rcx, [rbp+57h+string]; string
0x14000a106  call    cs:__imp_WindowsGetStringRawBuffer
0x14000a10c  mov     [rbp+57h+var_68], rax
0x14000a110  mov     [rbp+57h+var_60], r14d
0x14000a114  mov     [rbp+57h+var_80], esi
0x14000a117  mov     dword ptr [rbp+57h+var_70], r15d
0x14000a11b  lea     r8, [rbx+20h]
0x14000a11f  lea     rax, [rbp+57h+var_68]
0x14000a123  mov     [rsp+0C0h+var_90], rax
0x14000a128  lea     rax, [rbp+57h+var_80]
0x14000a12c  mov     [rsp+0C0h+var_98], rax
0x14000a131  lea     rax, [rbp+57h+var_70]
0x14000a135  mov     [rsp+0C0h+var_A0], rax
0x14000a13a  mov     r9, [rbx+30h]
0x14000a13e  lea     rdx, word_140043642
0x14000a145  mov     rcx, rdi
0x14000a148  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U_tlgWrapperPtrSize@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU_tlgWrapperPtrSize@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &)
0x14000a14d  nop
0x14000a14e  mov     rcx, [rbp+57h+string]; string
0x14000a152  call    cs:__imp_WindowsDeleteString
0x14000a158  mov     rcx, [rbp+57h+var_28]
0x14000a15c  xor     rcx, rsp; StackCookie
0x14000a15f  call    __security_check_cookie
0x14000a164  lea     r11, [rsp+0C0h+var_20]
0x14000a16c  mov     rbx, [r11+38h]
0x14000a170  mov     rsi, [r11+40h]
0x14000a174  mov     rsp, r11
0x14000a177  pop     r15
0x14000a179  pop     r14
0x14000a17b  pop     r12
0x14000a17d  pop     rdi
0x14000a17e  pop     rbp
0x14000a17f  retn
```
