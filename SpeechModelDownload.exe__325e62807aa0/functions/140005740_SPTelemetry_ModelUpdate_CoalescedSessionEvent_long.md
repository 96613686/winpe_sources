# SPTelemetry::ModelUpdate::CoalescedSessionEvent(long)

- ea: `0x140005740`
- end: `0x1400059a8`
- name: `?CoalescedSessionEvent@ModelUpdate@SPTelemetry@@UEAAXJ@Z`
- size: `616`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *__hidden this, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x14000176c`
- `0x140002600`
- `0x140005740`
- `0x140005ea0`
- `0x140006720`
- `0x1400077b0`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140005868`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400058ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140005912`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140005868`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400058ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140005912`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1400058ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1400058ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140005894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140005979`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140005894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140005979`

## string_xrefs

- `0x1400058a7`: `{ "Json too long" }`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::CoalescedSessionEvent(SPTelemetry::ModelUpdate *this, int a2)
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

  v4 = SPTraceLoggingClass::Provider();
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
      v15 = SPTraceLoggingClass::Provider();
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
          tlgWriteTransfer_EventWriteTransfer(v16, byte_1400298C9, (char *)this + 32, *((_QWORD *)this + 6), 5, v22);
        }
      }
      WindowsDeleteString(string);
    }
    else
    {
      v5 = SPTraceLoggingClass::Provider();
      v6 = v5;
      if ( *(_DWORD *)v5 > 4u )
      {
        v7 = *((_QWORD *)v5 + 3);
        if ( (*((_QWORD *)v6 + 2) & 1) != 0 && (v7 & 1) == v7 )
        {
          v20 = Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(this);
          v23 = &v20;
          v24 = 4;
          tlgWriteTransfer_EventWriteTransfer(v6, byte_140029D39, (char *)this + 32, *((_QWORD *)this + 6), 3, v22);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140005740  mov     [rsp-8+arg_8], rbx
0x140005745  mov     [rsp-8+arg_10], rsi
0x14000574a  push    rbp
0x14000574b  push    r12
0x14000574d  push    r13
0x14000574f  push    r14
0x140005751  push    r15
0x140005753  lea     rbp, [rsp-37h]
0x140005758  sub     rsp, 0B0h
0x14000575f  mov     rax, cs:__security_cookie
0x140005766  xor     rax, rsp
0x140005769  mov     [rbp+57h+var_30], rax
0x14000576d  mov     r12d, edx
0x140005770  mov     rsi, rcx
0x140005773  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x140005778  mov     ecx, [rax]
0x14000577a  cmp     ecx, 5
0x14000577d  jbe     loc_14000597F
0x140005783  mov     rcx, [rax+18h]
0x140005787  mov     rax, [rax+10h]
0x14000578b  mov     rdx, 400000000000h
0x140005795  test    rdx, rax
0x140005798  jz      loc_14000597F
0x14000579e  mov     rax, rcx
0x1400057a1  and     rax, rdx
0x1400057a4  cmp     rax, rcx
0x1400057a7  jnz     loc_14000597F
0x1400057ad  mov     rcx, rsi; this
0x1400057b0  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x1400057b5  xor     r13d, r13d
0x1400057b8  test    eax, eax
0x1400057ba  jns     short loc_140005837
0x1400057bc  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x1400057c1  mov     rbx, rax
0x1400057c4  mov     ecx, [rax]
0x1400057c6  cmp     ecx, 4
0x1400057c9  jbe     loc_14000597F
0x1400057cf  mov     rax, [rax+18h]
0x1400057d3  mov     rcx, [rbx+10h]
0x1400057d7  test    cl, 1
0x1400057da  jz      loc_14000597F
0x1400057e0  mov     rcx, rax
0x1400057e3  and     ecx, 1
0x1400057e6  cmp     rcx, rax
0x1400057e9  jnz     loc_14000597F
0x1400057ef  mov     rcx, rsi; this
0x1400057f2  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x1400057f7  mov     [rbp+57h+var_98], eax
0x1400057fa  lea     rax, [rbp+57h+var_98]
0x1400057fe  mov     [rbp+57h+var_60], rax
0x140005802  mov     [rbp+57h+var_58], 4
0x14000580a  lea     r8, [rsi+20h]
0x14000580e  lea     rax, [rbp+57h+var_80]
0x140005812  mov     [rsp+0D0h+var_A8], rax
0x140005817  mov     [rsp+0D0h+var_B0], 3
0x14000581f  mov     r9, [rsi+30h]
0x140005823  lea     rdx, byte_140029D39
0x14000582a  mov     rcx, rbx
0x14000582d  call    _tlgWriteTransfer_EventWriteTransfer
0x140005832  jmp     loc_14000597F
0x140005837  mov     [rbp+57h+string], r13
0x14000583b  mov     rcx, [rsi+48h]
0x14000583f  mov     [rbp+57h+var_90], rcx
0x140005843  test    rcx, rcx
0x140005846  jz      short loc_140005855
0x140005848  mov     rax, [rcx]
0x14000584b  mov     rax, [rax+8]
0x14000584f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005854  nop
0x140005855  lea     r8, [rbp+57h+string]
0x140005859  lea     rdx, [rbp+57h+var_90]
0x14000585d  call    ?GetJsonString@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEAVHString@Wrappers@67@@Z; Windows::Speech::Session::FlightDataRecorder::GetJsonString(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>,Microsoft::WRL::Wrappers::HString *)
0x140005862  xor     edx, edx; length
0x140005864  mov     rcx, [rbp+57h+string]; string
0x140005868  call    cs:__imp_WindowsGetStringRawBuffer
0x14000586e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140005872  mov     rcx, rbx
0x140005875  inc     rcx
0x140005878  cmp     [rax+rcx*2], r13w
0x14000587d  jnz     short loc_140005875
0x14000587f  lea     r14d, ds:2[rcx*2]
0x140005887  cmp     r14d, 0FA0h
0x14000588e  jbe     short loc_1400058D4
0x140005890  mov     rcx, [rbp+57h+string]; string
0x140005894  call    cs:__imp_WindowsDeleteString
0x14000589a  mov     [rbp+57h+string], r13
0x14000589e  lea     r8, [rbp+57h+string]; string
0x1400058a2  mov     edx, 13h; length
0x1400058a7  lea     rcx, aJsonTooLong; "{ \"Json too long\" }"
0x1400058ae  call    cs:__imp_WindowsCreateString
0x1400058b4  xor     edx, edx; length
0x1400058b6  mov     rcx, [rbp+57h+string]; string
0x1400058ba  call    cs:__imp_WindowsGetStringRawBuffer
0x1400058c0  inc     rbx
0x1400058c3  cmp     [rax+rbx*2], r13w
0x1400058c8  jnz     short loc_1400058C0
0x1400058ca  lea     r15d, ds:2[rbx*2]
0x1400058d2  jmp     short loc_1400058D7
0x1400058d4  mov     r15d, r14d
0x1400058d7  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x1400058dc  mov     rbx, rax
0x1400058df  mov     ecx, [rax]
0x1400058e1  cmp     ecx, 4
0x1400058e4  jbe     loc_140005975
0x1400058ea  mov     rax, [rax+18h]
0x1400058ee  mov     rcx, [rbx+10h]
0x1400058f2  mov     rdx, 400000000000h
0x1400058fc  test    rdx, rcx
0x1400058ff  jz      short loc_140005975
0x140005901  mov     rcx, rax
0x140005904  and     rcx, rdx
0x140005907  cmp     rcx, rax
0x14000590a  jnz     short loc_140005975
0x14000590c  xor     edx, edx; length
0x14000590e  mov     rcx, [rbp+57h+string]; string
0x140005912  call    cs:__imp_WindowsGetStringRawBuffer
0x140005918  mov     [rbp+57h+var_98], r14d
0x14000591c  mov     dword ptr [rbp+57h+var_90], r12d
0x140005920  mov     [rbp+57h+var_40], rax
0x140005924  mov     [rbp+57h+var_38], r15d
0x140005928  mov     [rbp+57h+var_34], r13d
0x14000592c  lea     rax, [rbp+57h+var_98]
0x140005930  mov     [rbp+57h+var_50], rax
0x140005934  mov     [rbp+57h+var_48], 4
0x14000593c  lea     rax, [rbp+57h+var_90]
0x140005940  mov     [rbp+57h+var_60], rax
0x140005944  mov     [rbp+57h+var_58], 4
0x14000594c  lea     r8, [rsi+20h]
0x140005950  lea     rax, [rbp+57h+var_80]
0x140005954  mov     [rsp+0D0h+var_A8], rax
0x140005959  mov     [rsp+0D0h+var_B0], 5
0x140005961  mov     r9, [rsi+30h]
0x140005965  lea     rdx, byte_1400298C9
0x14000596c  mov     rcx, rbx
0x14000596f  call    _tlgWriteTransfer_EventWriteTransfer
0x140005974  nop
0x140005975  mov     rcx, [rbp+57h+string]; string
0x140005979  call    cs:__imp_WindowsDeleteString
0x14000597f  mov     rcx, [rbp+57h+var_30]
0x140005983  xor     rcx, rsp; StackCookie
0x140005986  call    __security_check_cookie
0x14000598b  lea     r11, [rsp+0D0h+var_20]
0x140005993  mov     rbx, [r11+38h]
0x140005997  mov     rsi, [r11+40h]
0x14000599b  mov     rsp, r11
0x14000599e  pop     r15
0x1400059a0  pop     r14
0x1400059a2  pop     r13
0x1400059a4  pop     r12
0x1400059a6  pop     rbp
0x1400059a7  retn
```
