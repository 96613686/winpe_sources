# CEventLogChannel::Switch(int)

- ea: `0x18000f798`
- end: `0x18000f91c`
- name: `?Switch@CEventLogChannel@@QEAAJH@Z`
- size: `388`
- prototype: `__int64 __fastcall(CEventLogChannel *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180008f70`

## callees

- `0x18000108c`
- `0x180001b60`
- `0x180002644`
- `0x180002698`
- `0x18000f798`
- `0x180011170`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8a0`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18000f8ed`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18000f8ed`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18000f849`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18000f849`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSaveChannelConfig` at `0x18000f896`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSaveChannelConfig` at `0x18000f896`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x18000f887`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x18000f887`

## pseudocode

```c
__int64 __fastcall CEventLogChannel::Switch(CEventLogChannel *this, BOOL a2)
{
  EVT_HANDLE v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
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
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v14 = v8;
    v15 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v5,
      (__int64)byte_18003F84D,
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
0x18000f798  mov     [rsp-8+arg_10], rbx
0x18000f79d  mov     [rsp-8+arg_18], rsi
0x18000f7a2  push    rbp
0x18000f7a3  push    rdi
0x18000f7a4  push    r14
0x18000f7a6  lea     rbp, [rsp-170h]
0x18000f7ae  sub     rsp, 270h
0x18000f7b5  mov     rax, cs:__security_cookie
0x18000f7bc  xor     rax, rsp
0x18000f7bf  mov     [rbp+180h+var_20], rax
0x18000f7c6  xorps   xmm0, xmm0
0x18000f7c9  mov     [rsp+280h+var_250], 105h
0x18000f7d1  movups  xmmword ptr [rsp+280h+PropertyValue], xmm0
0x18000f7d6  mov     r14d, edx
0x18000f7d9  mov     rsi, rcx
0x18000f7dc  xor     edi, edi
0x18000f7de  call    IsEvtExportLogPresent
0x18000f7e3  test    al, al
0x18000f7e5  jnz     short loc_18000F7F1
0x18000f7e7  mov     ebx, 80004001h
0x18000f7ec  jmp     loc_18000F8B1
0x18000f7f1  call    IsEvtSaveChannelConfigPresent
0x18000f7f6  test    al, al
0x18000f7f8  jz      short loc_18000F7E7
0x18000f7fa  call    IsEvtSaveChannelConfigPresent
0x18000f7ff  test    al, al
0x18000f801  jz      short loc_18000F7E7
0x18000f803  call    IsEvtExportLogPresent
0x18000f808  test    al, al
0x18000f80a  jz      short loc_18000F7E7
0x18000f80c  lea     r9, [rsp+280h+var_250]; unsigned int *
0x18000f811  mov     rcx, rsi; this
0x18000f814  lea     r8, [rsp+280h+ChannelPath]; unsigned __int16 *
0x18000f819  xor     ebx, ebx
0x18000f81b  lea     rdx, String2; unsigned __int16 *
0x18000f822  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000f827  mov     esi, 80070000h
0x18000f82c  test    eax, eax
0x18000f82e  jz      short loc_18000F83B
0x18000f830  jg      short loc_18000F836
0x18000f832  mov     ebx, eax
0x18000f834  jmp     short loc_18000F83B
0x18000f836  movzx   ebx, ax
0x18000f839  or      ebx, esi
0x18000f83b  test    ebx, ebx
0x18000f83d  js      short loc_18000F8B1
0x18000f83f  xor     r8d, r8d; Flags
0x18000f842  lea     rdx, [rsp+280h+ChannelPath]; ChannelPath
0x18000f847  xor     ecx, ecx; Session
0x18000f849  call    cs:__imp_EvtOpenChannelConfig
0x18000f84f  mov     rdi, rax
0x18000f852  test    rax, rax
0x18000f855  jz      short loc_18000F8A0
0x18000f857  mov     ecx, 10h
0x18000f85c  lea     rax, [rsp+280h+PropertyValue]
0x18000f861  mov     byte ptr [rax], 0
0x18000f864  inc     rax
0x18000f867  sub     rcx, 1
0x18000f86b  jnz     short loc_18000F861
0x18000f86d  lea     r9, [rsp+280h+PropertyValue]; PropertyValue
0x18000f872  mov     [rsp+280h+PropertyValue.Type], 0Dh
0x18000f87a  xor     r8d, r8d; Flags
0x18000f87d  mov     dword ptr [rsp+280h+PropertyValue], r14d
0x18000f882  xor     edx, edx; PropertyId
0x18000f884  mov     rcx, rdi; ChannelConfig
0x18000f887  call    cs:__imp_EvtSetChannelConfigProperty
0x18000f88d  test    eax, eax
0x18000f88f  jz      short loc_18000F8A0
0x18000f891  xor     edx, edx; Flags
0x18000f893  mov     rcx, rdi; ChannelConfig
0x18000f896  call    cs:__imp_EvtSaveChannelConfig
0x18000f89c  test    eax, eax
0x18000f89e  jnz     short loc_18000F8B1
0x18000f8a0  call    cs:__imp_GetLastError
0x18000f8a6  mov     ebx, eax
0x18000f8a8  test    eax, eax
0x18000f8aa  jle     short loc_18000F8B1
0x18000f8ac  movzx   ebx, ax
0x18000f8af  or      ebx, esi
0x18000f8b1  mov     eax, cs:dword_180048E90
0x18000f8b7  cmp     eax, 5
0x18000f8ba  jbe     short loc_18000F8E5
0x18000f8bc  lea     rax, [rsp+280h+var_250]
0x18000f8c1  mov     [rsp+280h+var_250], ebx
0x18000f8c5  mov     [rsp+280h+var_258], rax
0x18000f8ca  lea     rdx, byte_18003F84D
0x18000f8d1  lea     rax, [rsp+280h+var_24C]
0x18000f8d6  mov     [rsp+280h+var_24C], r14d
0x18000f8db  mov     [rsp+280h+var_260], rax
0x18000f8e0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000f8e5  test    rdi, rdi
0x18000f8e8  jz      short loc_18000F8F3
0x18000f8ea  mov     rcx, rdi; Object
0x18000f8ed  call    cs:__imp_EvtClose
0x18000f8f3  mov     eax, ebx
0x18000f8f5  mov     rcx, [rbp+180h+var_20]
0x18000f8fc  xor     rcx, rsp; StackCookie
0x18000f8ff  call    __security_check_cookie
0x18000f904  lea     r11, [rsp+280h+var_10]
0x18000f90c  mov     rbx, [r11+30h]
0x18000f910  mov     rsi, [r11+38h]
0x18000f914  mov     rsp, r11
0x18000f917  pop     r14
0x18000f919  pop     rdi
0x18000f91a  pop     rbp
0x18000f91b  retn
```
