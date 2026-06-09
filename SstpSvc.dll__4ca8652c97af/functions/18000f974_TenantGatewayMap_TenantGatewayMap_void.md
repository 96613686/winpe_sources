# TenantGatewayMap::TenantGatewayMap(void)

- ea: `0x18000f974`
- end: `0x18000faa5`
- name: `??0TenantGatewayMap@@AEAA@XZ`
- size: `305`
- prototype: `WCHAR *__fastcall(WCHAR *SRWLock)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180007c34`

## callees

- `0x180007944`
- `0x18000827c`
- `0x180008360`
- `0x18000f7dc`
- `0x18000f974`
- `0x180010f3c`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000fa3d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000fa3d`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000fa6e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000fa6e`

## string_xrefs

- `0x18000f9f7`: `TenantGatewayMap::TenantGatewayMap: GetXmlFilePath failed with error %d`
- `0x18000fa98`: `TenantGatewayMap::TenantGatewayMap: FATAL ERROR. Failed to open the xml file with error %d`

## pseudocode

```c
WCHAR *__fastcall TenantGatewayMap::TenantGatewayMap(WCHAR *SRWLock)
{
  unsigned int XmlFilePath; // eax
  __int64 v3; // r8
  const wchar_t *v4; // rdx
  unsigned int v6; // eax
  LPCWSTR lpFileName[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[2044]; // [rsp+34h] [rbp-CCh] BYREF

  lpFileName[1] = SRWLock;
  std::tr1::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>(SRWLock + 4);
  lpFileName[0] = 0;
  *((_QWORD *)SRWLock + 12) = 0;
  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  XmlFilePath = GetXmlFilePath((unsigned __int16 **)lpFileName);
  v3 = XmlFilePath;
  if ( XmlFilePath )
  {
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_6;
    v4 = L"TenantGatewayMap::TenantGatewayMap: GetXmlFilePath failed with error %d";
  }
  else
  {
    InitializeSRWLock((PSRWLOCK)SRWLock);
    v6 = FileStream::OpenFile(lpFileName[0], (struct IStream **)SRWLock + 12);
    v3 = v6;
    if ( !v6 )
      goto LABEL_6;
    *((_QWORD *)SRWLock + 12) = 0;
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_6;
    v4 = L"TenantGatewayMap::TenantGatewayMap: FATAL ERROR. Failed to open the xml file with error %d";
  }
  LOWORD(v8) = 0;
  FormatRRASErrorString(&v8, v4, v3);
  if ( (byte_18002D803 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v8);
LABEL_6:
  if ( lpFileName[0] )
    operator delete[]((void *)lpFileName[0]);
  return SRWLock;
}

```

## disassembly

```asm
0x18000f974  mov     [rsp-8+arg_8], rbx
0x18000f979  mov     [rsp-8+arg_10], rsi
0x18000f97e  push    rbp
0x18000f97f  lea     rbp, [rsp-740h]
0x18000f987  sub     rsp, 840h
0x18000f98e  mov     rax, cs:__security_cookie
0x18000f995  xor     rax, rsp
0x18000f998  mov     [rbp+740h+var_10], rax
0x18000f99f  mov     rbx, rcx
0x18000f9a2  mov     [rsp+840h+var_818], rcx
0x18000f9a7  add     rcx, 8
0x18000f9ab  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@tr1@std@@QEAA@XZ; std::tr1::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>(void)
0x18000f9b0  nop
0x18000f9b1  mov     [rsp+840h+lpFileName], 0
0x18000f9ba  lea     rsi, [rbx+60h]
0x18000f9be  mov     qword ptr [rsi], 0
0x18000f9c5  xor     eax, eax
0x18000f9c7  mov     [rsp+840h+var_810], eax
0x18000f9cb  xor     edx, edx; Val
0x18000f9cd  mov     r8d, 7FCh; Size
0x18000f9d3  lea     rcx, [rsp+840h+var_80C]; void *
0x18000f9d8  call    memset_0
0x18000f9dd  lea     rcx, [rsp+840h+lpFileName]; unsigned __int16 **
0x18000f9e2  call    ?GetXmlFilePath@@YAKPEAPEAG@Z; GetXmlFilePath(ushort * *)
0x18000f9e7  mov     r8d, eax
0x18000f9ea  test    eax, eax
0x18000f9ec  jz      short loc_18000FA6B
0x18000f9ee  test    cs:byte_18002D803, 8
0x18000f9f5  jz      short loc_18000FA30
0x18000f9f7  lea     rdx, aTenantgatewaym_5; "TenantGatewayMap::TenantGatewayMap: Get"...
0x18000f9fe  xor     eax, eax
0x18000fa00  mov     word ptr [rsp+840h+var_810], ax
0x18000fa05  lea     rcx, [rsp+840h+var_810]
0x18000fa0a  call    FormatRRASErrorString
0x18000fa0f  test    cs:byte_18002D803, 8
0x18000fa16  jz      short loc_18000FA30
0x18000fa18  lea     r8, [rsp+840h+var_810]
0x18000fa1d  lea     rdx, RasSSTPSvcTraceError
0x18000fa24  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000fa2b  call    McTemplateU0z_EventWriteTransfer
0x18000fa30  cmp     [rsp+840h+lpFileName], 0
0x18000fa36  jz      short loc_18000FA44
0x18000fa38  mov     rcx, [rsp+840h+lpFileName]
0x18000fa3d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000fa43  nop
0x18000fa44  mov     rax, rbx
0x18000fa47  mov     rcx, [rbp+740h+var_10]
0x18000fa4e  xor     rcx, rsp; StackCookie
0x18000fa51  call    __security_check_cookie
0x18000fa56  lea     r11, [rsp+840h+var_s0]
0x18000fa5e  mov     rbx, [r11+18h]
0x18000fa62  mov     rsi, [r11+20h]
0x18000fa66  mov     rsp, r11
0x18000fa69  pop     rbp
0x18000fa6a  retn
0x18000fa6b  mov     rcx, rbx; SRWLock
0x18000fa6e  call    cs:__imp_InitializeSRWLock
0x18000fa74  mov     rdx, rsi; struct IStream **
0x18000fa77  mov     rcx, [rsp+840h+lpFileName]; lpFileName
0x18000fa7c  call    ?OpenFile@FileStream@@SAJPEBGPEAPEAUIStream@@@Z; FileStream::OpenFile(ushort const *,IStream * *)
0x18000fa81  mov     r8d, eax
0x18000fa84  test    eax, eax
0x18000fa86  jz      short loc_18000FA30
0x18000fa88  mov     qword ptr [rsi], 0
0x18000fa8f  test    cs:byte_18002D803, 8
0x18000fa96  jz      short loc_18000FA30
0x18000fa98  lea     rdx, aTenantgatewaym_3; "TenantGatewayMap::TenantGatewayMap: FAT"...
0x18000fa9f  jmp     loc_18000F9FE
```
