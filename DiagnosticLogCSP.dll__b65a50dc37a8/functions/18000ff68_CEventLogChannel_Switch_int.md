# CEventLogChannel::Switch(int)

- ea: `0x18000ff68`
- end: `0x18001010f`
- name: `?Switch@CEventLogChannel@@QEAAJH@Z`
- size: `423`
- prototype: `__int64 __fastcall(CEventLogChannel *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800091b0`

## callees

- `0x180001090`
- `0x180001b90`
- `0x180002674`
- `0x1800026c8`
- `0x18000ff68`
- `0x180011a38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010086`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x1800100d9`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x1800100d9`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18001001d`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18001001d`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSaveChannelConfig` at `0x180010076`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSaveChannelConfig` at `0x180010076`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x180010061`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x180010061`

## pseudocode

```c
__int64 __fastcall CEventLogChannel::Switch(CEventLogChannel *this, BOOL a2)
{
  EVT_HANDLE v4; // rdi
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // ebx
  int v9; // eax
  __int64 v10; // rcx
  struct _EVT_VARIANT *p_PropertyValue; // rax
  signed int LastError; // eax
  unsigned int v14; // [rsp+30h] [rbp-D0h] BYREF
  BOOL v15; // [rsp+34h] [rbp-CCh] BYREF
  struct _EVT_VARIANT PropertyValue; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ChannelPath[264]; // [rsp+50h] [rbp-B0h] BYREF

  v14 = 261;
  PropertyValue = 0;
  v4 = 0;
  if ( (unsigned __int8)IsEvtExportLogPresent()
    && (unsigned __int8)IsEvtSaveChannelConfigPresent()
    && (unsigned __int8)IsEvtSaveChannelConfigPresent()
    && (unsigned __int8)IsEvtExportLogPresent() )
  {
    v8 = 0;
    v9 = ATL::CRegKey::QueryStringValue(this, &String2, ChannelPath, &v14);
    if ( v9 )
    {
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
      else
        v8 = v9;
    }
    if ( v8 >= 0 )
    {
      v4 = EvtOpenChannelConfig(0, ChannelPath, 0);
      if ( !v4 )
        goto LABEL_16;
      v10 = 16;
      p_PropertyValue = &PropertyValue;
      do
      {
        p_PropertyValue->SByteVal = 0;
        p_PropertyValue = (struct _EVT_VARIANT *)((char *)p_PropertyValue + 1);
        --v10;
      }
      while ( v10 );
      PropertyValue.Type = 13;
      PropertyValue.BooleanVal = a2;
      if ( !EvtSetChannelConfigProperty(v4, EvtChannelConfigEnabled, 0, &PropertyValue) || !EvtSaveChannelConfig(v4, 0) )
      {
LABEL_16:
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  else
  {
    v8 = -2147467263;
  }
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v14 = v8;
    v15 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_18004184D,
      v6,
      v7,
      (__int64)&v15,
      (__int64)&v14);
  }
  if ( v4 )
    EvtClose(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000ff68  mov     [rsp-8+arg_10], rbx
0x18000ff6d  mov     [rsp-8+arg_18], rsi
0x18000ff72  push    rbp
0x18000ff73  push    rdi
0x18000ff74  push    r14
0x18000ff76  lea     rbp, [rsp-170h]
0x18000ff7e  sub     rsp, 270h
0x18000ff85  mov     rax, cs:__security_cookie
0x18000ff8c  xor     rax, rsp
0x18000ff8f  mov     [rbp+180h+var_20], rax
0x18000ff96  xorps   xmm0, xmm0
0x18000ff99  mov     [rsp+280h+var_250], 105h
0x18000ffa1  movups  xmmword ptr [rsp+280h+PropertyValue], xmm0
0x18000ffa6  mov     r14d, edx
0x18000ffa9  mov     rsi, rcx
0x18000ffac  xor     edi, edi
0x18000ffae  call    IsEvtExportLogPresent
0x18000ffb3  test    al, al
0x18000ffb5  jnz     short loc_18000FFC1
0x18000ffb7  mov     ebx, 80004001h
0x18000ffbc  jmp     loc_18001009D
0x18000ffc1  call    IsEvtSaveChannelConfigPresent
0x18000ffc6  test    al, al
0x18000ffc8  jz      short loc_18000FFB7
0x18000ffca  call    IsEvtSaveChannelConfigPresent
0x18000ffcf  test    al, al
0x18000ffd1  jz      short loc_18000FFB7
0x18000ffd3  call    IsEvtExportLogPresent
0x18000ffd8  test    al, al
0x18000ffda  jz      short loc_18000FFB7
0x18000ffdc  lea     r9, [rsp+280h+var_250]; unsigned int *
0x18000ffe1  mov     rcx, rsi; this
0x18000ffe4  lea     r8, [rsp+280h+ChannelPath]; unsigned __int16 *
0x18000ffe9  xor     ebx, ebx
0x18000ffeb  lea     rdx, String2; unsigned __int16 *
0x18000fff2  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000fff7  mov     esi, 80070000h
0x18000fffc  test    eax, eax
0x18000fffe  jz      short loc_18001000B
0x180010000  jg      short loc_180010006
0x180010002  mov     ebx, eax
0x180010004  jmp     short loc_18001000B
0x180010006  movzx   ebx, ax
0x180010009  or      ebx, esi
0x18001000b  test    ebx, ebx
0x18001000d  js      loc_18001009D
0x180010013  xor     r8d, r8d; Flags
0x180010016  lea     rdx, [rsp+280h+ChannelPath]; ChannelPath
0x18001001b  xor     ecx, ecx; Session
0x18001001d  call    cs:__imp_EvtOpenChannelConfig
0x180010024  nop     dword ptr [rax+rax+00h]
0x180010029  mov     rdi, rax
0x18001002c  test    rax, rax
0x18001002f  jz      short loc_180010086
0x180010031  mov     ecx, 10h
0x180010036  lea     rax, [rsp+280h+PropertyValue]
0x18001003b  mov     byte ptr [rax], 0
0x18001003e  inc     rax
0x180010041  sub     rcx, 1
0x180010045  jnz     short loc_18001003B
0x180010047  lea     r9, [rsp+280h+PropertyValue]; PropertyValue
0x18001004c  mov     [rsp+280h+PropertyValue.Type], 0Dh
0x180010054  xor     r8d, r8d; Flags
0x180010057  mov     dword ptr [rsp+280h+PropertyValue], r14d
0x18001005c  xor     edx, edx; PropertyId
0x18001005e  mov     rcx, rdi; ChannelConfig
0x180010061  call    cs:__imp_EvtSetChannelConfigProperty
0x180010068  nop     dword ptr [rax+rax+00h]
0x18001006d  test    eax, eax
0x18001006f  jz      short loc_180010086
0x180010071  xor     edx, edx; Flags
0x180010073  mov     rcx, rdi; ChannelConfig
0x180010076  call    cs:__imp_EvtSaveChannelConfig
0x18001007d  nop     dword ptr [rax+rax+00h]
0x180010082  test    eax, eax
0x180010084  jnz     short loc_18001009D
0x180010086  call    cs:__imp_GetLastError
0x18001008d  nop     dword ptr [rax+rax+00h]
0x180010092  mov     ebx, eax
0x180010094  test    eax, eax
0x180010096  jle     short loc_18001009D
0x180010098  movzx   ebx, ax
0x18001009b  or      ebx, esi
0x18001009d  mov     eax, cs:dword_18004AE90
0x1800100a3  cmp     eax, 5
0x1800100a6  jbe     short loc_1800100D1
0x1800100a8  lea     rax, [rsp+280h+var_250]
0x1800100ad  mov     [rsp+280h+var_250], ebx
0x1800100b1  mov     [rsp+280h+var_258], rax
0x1800100b6  lea     rdx, byte_18004184D
0x1800100bd  lea     rax, [rsp+280h+var_24C]
0x1800100c2  mov     [rsp+280h+var_24C], r14d
0x1800100c7  mov     [rsp+280h+var_260], rax
0x1800100cc  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800100d1  test    rdi, rdi
0x1800100d4  jz      short loc_1800100E5
0x1800100d6  mov     rcx, rdi; Object
0x1800100d9  call    cs:__imp_EvtClose
0x1800100e0  nop     dword ptr [rax+rax+00h]
0x1800100e5  mov     eax, ebx
0x1800100e7  mov     rcx, [rbp+180h+var_20]
0x1800100ee  xor     rcx, rsp; StackCookie
0x1800100f1  call    __security_check_cookie
0x1800100f6  lea     r11, [rsp+280h+var_10]
0x1800100fe  mov     rbx, [r11+30h]
0x180010102  mov     rsi, [r11+38h]
0x180010106  mov     rsp, r11
0x180010109  pop     r14
0x18001010b  pop     rdi
0x18001010c  pop     rbp
0x18001010d  retn
```
