# SpeechOneSettingsTelemetry::LifeTime::CoalescedSessionEvent(long)

- ea: `0x140015f50`
- end: `0x1400161b8`
- name: `?CoalescedSessionEvent@LifeTime@SpeechOneSettingsTelemetry@@UEAAXJ@Z`
- size: `616`
- prototype: `void __fastcall(SpeechOneSettingsTelemetry::LifeTime *__hidden this, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x14000176c`
- `0x140002600`
- `0x140005ea0`
- `0x140006720`
- `0x140015f50`
- `0x1400189d4`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140016078`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400160ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140016122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140016078`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400160ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140016122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1400160be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1400160be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400160a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140016189`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400160a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140016189`

## string_xrefs

- `0x1400160b7`: `{ "Json too long" }`

## pseudocode

```c
void __fastcall SpeechOneSettingsTelemetry::LifeTime::CoalescedSessionEvent(
        SpeechOneSettingsTelemetry::LifeTime *this,
        int a2)
{
  const struct _tlgProvider_t *v4; // rax
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // rbx
  __int64 v11; // rcx
  unsigned int v12; // r14d
  PCWSTR v13; // rax
  int v14; // r15d
  const struct _tlgProvider_t *v15; // rax
  const struct _tlgProvider_t *v16; // rbx
  __int64 v17; // rax
  PCWSTR v18; // rax
  HSTRING string; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-41h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v22[32]; // [rsp+50h] [rbp-29h] BYREF
  unsigned int *v23; // [rsp+70h] [rbp-9h]
  __int64 v24; // [rsp+78h] [rbp-1h]
  unsigned int *v25; // [rsp+80h] [rbp+7h]
  __int64 v26; // [rsp+88h] [rbp+Fh]
  PCWSTR v27; // [rsp+90h] [rbp+17h]
  int v28; // [rsp+98h] [rbp+1Fh]
  int v29; // [rsp+9Ch] [rbp+23h]

  v4 = SpeechOneSettingsLogging::Provider();
  if ( *(_DWORD *)v4 > 5u
    && (*((_QWORD *)v4 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v4 + 3) & 0x400000000000LL) == *((_QWORD *)v4 + 3) )
  {
    if ( (int)Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(this) >= 0 )
    {
      string = 0;
      v8 = *((_QWORD *)this + 9);
      v21[0] = v8;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      Windows::Speech::Session::FlightDataRecorder::GetJsonString(v8, v21, &string);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v10 = -1;
      v11 = -1;
      do
        ++v11;
      while ( StringRawBuffer[v11] );
      v12 = 2 * v11 + 2;
      if ( v12 <= 0xFA0 )
      {
        v14 = 2 * v11 + 2;
      }
      else
      {
        WindowsDeleteString(string);
        string = 0;
        WindowsCreateString(L"{ \"Json too long\" }", 0x13u, &string);
        v13 = WindowsGetStringRawBuffer(string, 0);
        do
          ++v10;
        while ( v13[v10] );
        v14 = 2 * v10 + 2;
      }
      v15 = SpeechOneSettingsLogging::Provider();
      v16 = v15;
      if ( *(_DWORD *)v15 > 4u )
      {
        v17 = *((_QWORD *)v15 + 3);
        if ( (*((_QWORD *)v16 + 2) & 0x400000000000LL) != 0 && (v17 & 0x400000000000LL) == v17 )
        {
          v18 = WindowsGetStringRawBuffer(string, 0);
          v20 = v12;
          LODWORD(v21[0]) = a2;
          v27 = v18;
          v28 = v14;
          v29 = 0;
          v25 = &v20;
          v26 = 4;
          v23 = (unsigned int *)v21;
          v24 = 4;
          tlgWriteTransfer_EventWriteTransfer(v16, word_14002A2C2, (char *)this + 32, *((_QWORD *)this + 6), 5, v22);
        }
      }
      WindowsDeleteString(string);
    }
    else
    {
      v5 = SpeechOneSettingsLogging::Provider();
      v6 = v5;
      if ( *(_DWORD *)v5 > 4u )
      {
        v7 = *((_QWORD *)v5 + 3);
        if ( (*((_QWORD *)v6 + 2) & 1) != 0 && (v7 & 1) == v7 )
        {
          v20 = Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(this);
          v23 = &v20;
          v24 = 4;
          tlgWriteTransfer_EventWriteTransfer(v6, word_14002A972, (char *)this + 32, *((_QWORD *)this + 6), 3, v22);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140015f50  mov     [rsp-8+arg_8], rbx
0x140015f55  mov     [rsp-8+arg_10], rsi
0x140015f5a  push    rbp
0x140015f5b  push    r12
0x140015f5d  push    r13
0x140015f5f  push    r14
0x140015f61  push    r15
0x140015f63  lea     rbp, [rsp-37h]
0x140015f68  sub     rsp, 0B0h
0x140015f6f  mov     rax, cs:__security_cookie
0x140015f76  xor     rax, rsp
0x140015f79  mov     [rbp+57h+var_30], rax
0x140015f7d  mov     r12d, edx
0x140015f80  mov     rsi, rcx
0x140015f83  call    ?Provider@SpeechOneSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; SpeechOneSettingsLogging::Provider(void)
0x140015f88  mov     ecx, [rax]
0x140015f8a  cmp     ecx, 5
0x140015f8d  jbe     loc_14001618F
0x140015f93  mov     rcx, [rax+18h]
0x140015f97  mov     rax, [rax+10h]
0x140015f9b  mov     rdx, 400000000000h
0x140015fa5  test    rdx, rax
0x140015fa8  jz      loc_14001618F
0x140015fae  mov     rax, rcx
0x140015fb1  and     rax, rdx
0x140015fb4  cmp     rax, rcx
0x140015fb7  jnz     loc_14001618F
0x140015fbd  mov     rcx, rsi; this
0x140015fc0  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x140015fc5  xor     r13d, r13d
0x140015fc8  test    eax, eax
0x140015fca  jns     short loc_140016047
0x140015fcc  call    ?Provider@SpeechOneSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; SpeechOneSettingsLogging::Provider(void)
0x140015fd1  mov     rbx, rax
0x140015fd4  mov     ecx, [rax]
0x140015fd6  cmp     ecx, 4
0x140015fd9  jbe     loc_14001618F
0x140015fdf  mov     rax, [rax+18h]
0x140015fe3  mov     rcx, [rbx+10h]
0x140015fe7  test    cl, 1
0x140015fea  jz      loc_14001618F
0x140015ff0  mov     rcx, rax
0x140015ff3  and     ecx, 1
0x140015ff6  cmp     rcx, rax
0x140015ff9  jnz     loc_14001618F
0x140015fff  mov     rcx, rsi; this
0x140016002  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x140016007  mov     [rbp+57h+var_98], eax
0x14001600a  lea     rax, [rbp+57h+var_98]
0x14001600e  mov     [rbp+57h+var_60], rax
0x140016012  mov     [rbp+57h+var_58], 4
0x14001601a  lea     r8, [rsi+20h]
0x14001601e  lea     rax, [rbp+57h+var_80]
0x140016022  mov     [rsp+0D0h+var_A8], rax
0x140016027  mov     [rsp+0D0h+var_B0], 3
0x14001602f  mov     r9, [rsi+30h]
0x140016033  lea     rdx, word_14002A972
0x14001603a  mov     rcx, rbx
0x14001603d  call    _tlgWriteTransfer_EventWriteTransfer
0x140016042  jmp     loc_14001618F
0x140016047  mov     [rbp+57h+string], r13
0x14001604b  mov     rcx, [rsi+48h]
0x14001604f  mov     [rbp+57h+var_90], rcx
0x140016053  test    rcx, rcx
0x140016056  jz      short loc_140016065
0x140016058  mov     rax, [rcx]
0x14001605b  mov     rax, [rax+8]
0x14001605f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016064  nop
0x140016065  lea     r8, [rbp+57h+string]
0x140016069  lea     rdx, [rbp+57h+var_90]
0x14001606d  call    ?GetJsonString@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEAVHString@Wrappers@67@@Z; Windows::Speech::Session::FlightDataRecorder::GetJsonString(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>,Microsoft::WRL::Wrappers::HString *)
0x140016072  xor     edx, edx; length
0x140016074  mov     rcx, [rbp+57h+string]; string
0x140016078  call    cs:__imp_WindowsGetStringRawBuffer
0x14001607e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140016082  mov     rcx, rbx
0x140016085  inc     rcx
0x140016088  cmp     [rax+rcx*2], r13w
0x14001608d  jnz     short loc_140016085
0x14001608f  lea     r14d, ds:2[rcx*2]
0x140016097  cmp     r14d, 0FA0h
0x14001609e  jbe     short loc_1400160E4
0x1400160a0  mov     rcx, [rbp+57h+string]; string
0x1400160a4  call    cs:__imp_WindowsDeleteString
0x1400160aa  mov     [rbp+57h+string], r13
0x1400160ae  lea     r8, [rbp+57h+string]; string
0x1400160b2  mov     edx, 13h; length
0x1400160b7  lea     rcx, aJsonTooLong; "{ \"Json too long\" }"
0x1400160be  call    cs:__imp_WindowsCreateString
0x1400160c4  xor     edx, edx; length
0x1400160c6  mov     rcx, [rbp+57h+string]; string
0x1400160ca  call    cs:__imp_WindowsGetStringRawBuffer
0x1400160d0  inc     rbx
0x1400160d3  cmp     [rax+rbx*2], r13w
0x1400160d8  jnz     short loc_1400160D0
0x1400160da  lea     r15d, ds:2[rbx*2]
0x1400160e2  jmp     short loc_1400160E7
0x1400160e4  mov     r15d, r14d
0x1400160e7  call    ?Provider@SpeechOneSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; SpeechOneSettingsLogging::Provider(void)
0x1400160ec  mov     rbx, rax
0x1400160ef  mov     ecx, [rax]
0x1400160f1  cmp     ecx, 4
0x1400160f4  jbe     loc_140016185
0x1400160fa  mov     rax, [rax+18h]
0x1400160fe  mov     rcx, [rbx+10h]
0x140016102  mov     rdx, 400000000000h
0x14001610c  test    rdx, rcx
0x14001610f  jz      short loc_140016185
0x140016111  mov     rcx, rax
0x140016114  and     rcx, rdx
0x140016117  cmp     rcx, rax
0x14001611a  jnz     short loc_140016185
0x14001611c  xor     edx, edx; length
0x14001611e  mov     rcx, [rbp+57h+string]; string
0x140016122  call    cs:__imp_WindowsGetStringRawBuffer
0x140016128  mov     [rbp+57h+var_98], r14d
0x14001612c  mov     dword ptr [rbp+57h+var_90], r12d
0x140016130  mov     [rbp+57h+var_40], rax
0x140016134  mov     [rbp+57h+var_38], r15d
0x140016138  mov     [rbp+57h+var_34], r13d
0x14001613c  lea     rax, [rbp+57h+var_98]
0x140016140  mov     [rbp+57h+var_50], rax
0x140016144  mov     [rbp+57h+var_48], 4
0x14001614c  lea     rax, [rbp+57h+var_90]
0x140016150  mov     [rbp+57h+var_60], rax
0x140016154  mov     [rbp+57h+var_58], 4
0x14001615c  lea     r8, [rsi+20h]
0x140016160  lea     rax, [rbp+57h+var_80]
0x140016164  mov     [rsp+0D0h+var_A8], rax
0x140016169  mov     [rsp+0D0h+var_B0], 5
0x140016171  mov     r9, [rsi+30h]
0x140016175  lea     rdx, word_14002A2C2
0x14001617c  mov     rcx, rbx
0x14001617f  call    _tlgWriteTransfer_EventWriteTransfer
0x140016184  nop
0x140016185  mov     rcx, [rbp+57h+string]; string
0x140016189  call    cs:__imp_WindowsDeleteString
0x14001618f  mov     rcx, [rbp+57h+var_30]
0x140016193  xor     rcx, rsp; StackCookie
0x140016196  call    __security_check_cookie
0x14001619b  lea     r11, [rsp+0D0h+var_20]
0x1400161a3  mov     rbx, [r11+38h]
0x1400161a7  mov     rsi, [r11+40h]
0x1400161ab  mov     rsp, r11
0x1400161ae  pop     r15
0x1400161b0  pop     r14
0x1400161b2  pop     r13
0x1400161b4  pop     r12
0x1400161b6  pop     rbp
0x1400161b7  retn
```
