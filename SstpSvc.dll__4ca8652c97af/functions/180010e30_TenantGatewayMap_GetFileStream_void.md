# TenantGatewayMap::GetFileStream(void)

- ea: `0x180010e30`
- end: `0x180010f35`
- name: `?GetFileStream@TenantGatewayMap@@QEAAPEAUIStream@@XZ`
- size: `261`
- prototype: `struct IStream *__fastcall(TenantGatewayMap *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180013464`
- `0x1800138c0`
- `0x180014490`

## callees

- `0x180007944`
- `0x18000827c`
- `0x180008360`
- `0x180010e30`
- `0x180010f3c`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180010eda`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180010eda`

## string_xrefs

- `0x180010e99`: `TenantGatewayMap::GetFileStream: GetXmlFilePath failed with error %d`
- `0x180010f29`: `TenantGatewayMap::GetFileStream: FATAL ERROR. Failed to open the xml file with error %d`

## pseudocode

```c
struct IStream *__fastcall TenantGatewayMap::GetFileStream(TenantGatewayMap *this)
{
  unsigned int XmlFilePath; // eax
  WCHAR *v3; // rbx
  __int64 v4; // r8
  const wchar_t *v5; // rdx
  unsigned int v7; // eax
  LPCWSTR lpFileName; // [rsp+20h] [rbp-828h] BYREF
  int v9; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v10[2044]; // [rsp+34h] [rbp-814h] BYREF

  lpFileName = 0;
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( *((_QWORD *)this + 12) )
    return (struct IStream *)*((_QWORD *)this + 12);
  XmlFilePath = GetXmlFilePath((unsigned __int16 **)&lpFileName);
  v3 = (WCHAR *)lpFileName;
  v4 = XmlFilePath;
  if ( XmlFilePath )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      v5 = L"TenantGatewayMap::GetFileStream: GetXmlFilePath failed with error %d";
      goto LABEL_5;
    }
  }
  else
  {
    v7 = FileStream::OpenFile(lpFileName, (struct IStream **)this + 12);
    v4 = v7;
    if ( v7 )
    {
      *((_QWORD *)this + 12) = 0;
      if ( (byte_18002D803 & 8) != 0 )
      {
        v5 = L"TenantGatewayMap::GetFileStream: FATAL ERROR. Failed to open the xml file with error %d";
LABEL_5:
        LOWORD(v9) = 0;
        FormatRRASErrorString(&v9, v5, v4);
        if ( (byte_18002D803 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v9);
      }
    }
  }
  if ( v3 )
    operator delete[](v3);
  return (struct IStream *)*((_QWORD *)this + 12);
}

```

## disassembly

```asm
0x180010e30  mov     [rsp+arg_8], rbx
0x180010e35  push    rdi
0x180010e36  sub     rsp, 840h
0x180010e3d  mov     rax, cs:__security_cookie
0x180010e44  xor     rax, rsp
0x180010e47  mov     [rsp+848h+var_18], rax
0x180010e4f  mov     rdi, rcx
0x180010e52  mov     [rsp+848h+lpFileName], 0
0x180010e5b  xor     eax, eax
0x180010e5d  lea     rcx, [rsp+848h+var_814]; void *
0x180010e62  xor     edx, edx; Val
0x180010e64  mov     [rsp+848h+var_818], eax
0x180010e68  mov     r8d, 7FCh; Size
0x180010e6e  call    memset_0
0x180010e73  cmp     qword ptr [rdi+60h], 0
0x180010e78  jnz     short loc_180010EE0
0x180010e7a  lea     rcx, [rsp+848h+lpFileName]; unsigned __int16 **
0x180010e7f  call    ?GetXmlFilePath@@YAKPEAPEAG@Z; GetXmlFilePath(ushort * *)
0x180010e84  mov     rbx, [rsp+848h+lpFileName]
0x180010e89  mov     r8d, eax
0x180010e8c  test    eax, eax
0x180010e8e  jz      short loc_180010F05
0x180010e90  test    cs:byte_18002D803, 8
0x180010e97  jz      short loc_180010ED2
0x180010e99  lea     rdx, aTenantgatewaym_2; "TenantGatewayMap::GetFileStream: GetXml"...
0x180010ea0  xor     eax, eax
0x180010ea2  lea     rcx, [rsp+848h+var_818]
0x180010ea7  mov     word ptr [rsp+848h+var_818], ax
0x180010eac  call    FormatRRASErrorString
0x180010eb1  test    cs:byte_18002D803, 8
0x180010eb8  jz      short loc_180010ED2
0x180010eba  lea     r8, [rsp+848h+var_818]
0x180010ebf  lea     rdx, RasSSTPSvcTraceError
0x180010ec6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010ecd  call    McTemplateU0z_EventWriteTransfer
0x180010ed2  test    rbx, rbx
0x180010ed5  jz      short loc_180010EE0
0x180010ed7  mov     rcx, rbx
0x180010eda  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180010ee0  mov     rax, [rdi+60h]
0x180010ee4  mov     rcx, [rsp+848h+var_18]
0x180010eec  xor     rcx, rsp; StackCookie
0x180010eef  call    __security_check_cookie
0x180010ef4  mov     rbx, [rsp+848h+arg_8]
0x180010efc  add     rsp, 840h
0x180010f03  pop     rdi
0x180010f04  retn
0x180010f05  lea     rdx, [rdi+60h]; struct IStream **
0x180010f09  mov     rcx, rbx; lpFileName
0x180010f0c  call    ?OpenFile@FileStream@@SAJPEBGPEAPEAUIStream@@@Z; FileStream::OpenFile(ushort const *,IStream * *)
0x180010f11  mov     r8d, eax
0x180010f14  test    eax, eax
0x180010f16  jz      short loc_180010ED2
0x180010f18  mov     qword ptr [rdi+60h], 0
0x180010f20  test    cs:byte_18002D803, 8
0x180010f27  jz      short loc_180010ED2
0x180010f29  lea     rdx, aTenantgatewaym_4; "TenantGatewayMap::GetFileStream: FATAL "...
0x180010f30  jmp     loc_180010EA0
```
