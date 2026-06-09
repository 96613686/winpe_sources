# OpenXmlWriter(IXmlWriter * *,IStream *)

- ea: `0x1800113dc`
- end: `0x1800115f5`
- name: `?OpenXmlWriter@@YAKPEAPEAUIXmlWriter@@PEAUIStream@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(struct IXmlWriter **ppvObject, struct IStream *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800138c0`
- `0x180014490`

## callees

- `0x18000827c`
- `0x180008360`
- `0x1800113dc`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001d010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x180011436`
- `XmlLite!CreateXmlWriter` at `0x180011436`

## string_xrefs

- `0x180011451`: `OpenXmlWriter: Failed to create IXmlWriter object with error %d`
- `0x18001148a`: `OpenXmlWriter: Failed to set the output stream for IXmlWriter object. Error %d`
- `0x1800114c0`: `OpenXmlWriter: Failed to set the XmlWriterProperty_Indent of IXmlWriter object. Error %d`
- `0x1800114f1`: `OpenXmlWriter: Failed to flush the output stream for IXmlWriter object. Error %d`
- `0x180011524`: `OpenXmlWriter: WriteStartDocument of IXmlWriter object failed with error %d`
- `0x180011530`: `ProxyConfig`
- `0x18001157e`: `OpenXmlWriter: WriteStartElement of IXmlWriter object failed with error %d`

## pseudocode

```c
__int64 __fastcall OpenXmlWriter(struct IXmlWriter **ppvObject, struct IStream *a2)
{
  unsigned int XmlWriter; // eax
  int v5; // ebx
  const wchar_t *v6; // rdx
  __int64 result; // rax
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  *ppvObject = 0;
  XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, (void **)ppvObject, 0);
  v5 = XmlWriter;
  if ( XmlWriter )
  {
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_23;
    LOWORD(v8) = 0;
    FormatRRASErrorString(&v8, L"OpenXmlWriter: Failed to create IXmlWriter object with error %d", XmlWriter);
  }
  else
  {
    v5 = ((__int64 (__fastcall *)(_QWORD, struct IStream *))(*ppvObject)->lpVtbl->SetOutput)(*ppvObject, a2);
    if ( v5 )
    {
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_23;
      v6 = L"OpenXmlWriter: Failed to set the output stream for IXmlWriter object. Error %d";
    }
    else
    {
      v5 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))(*ppvObject)->lpVtbl->SetProperty)(*ppvObject, 1, 1);
      if ( v5 )
      {
        if ( (byte_18002D803 & 8) == 0 )
          goto LABEL_23;
        v6 = L"OpenXmlWriter: Failed to set the XmlWriterProperty_Indent of IXmlWriter object. Error %d";
      }
      else
      {
        v5 = ((__int64 (__fastcall *)(_QWORD))(*ppvObject)->lpVtbl->Flush)(*ppvObject);
        if ( v5 )
        {
          if ( (byte_18002D803 & 8) == 0 )
            goto LABEL_23;
          v6 = L"OpenXmlWriter: Failed to flush the output stream for IXmlWriter object. Error %d";
        }
        else
        {
          v5 = ((__int64 (__fastcall *)(_QWORD, _QWORD))(*ppvObject)->lpVtbl->WriteStartDocument)(*ppvObject, 0);
          if ( v5 )
          {
            if ( (byte_18002D803 & 8) == 0 )
              goto LABEL_23;
            v6 = L"OpenXmlWriter: WriteStartDocument of IXmlWriter object failed with error %d";
          }
          else
          {
            v5 = ((__int64 (__fastcall *)(_QWORD, _QWORD, const wchar_t *, _QWORD))(*ppvObject)->lpVtbl->WriteStartElement)(
                   *ppvObject,
                   0,
                   L"ProxyConfig",
                   0);
            if ( !v5 )
            {
              v5 = ((__int64 (__fastcall *)(_QWORD, _QWORD, const wchar_t *, _QWORD))(*ppvObject)->lpVtbl->WriteStartElement)(
                     *ppvObject,
                     0,
                     L"TenantGatewayMap",
                     0);
              if ( !v5 )
                goto LABEL_23;
            }
            if ( (byte_18002D803 & 8) == 0 )
              goto LABEL_23;
            v6 = L"OpenXmlWriter: WriteStartElement of IXmlWriter object failed with error %d";
          }
        }
      }
    }
    LOWORD(v8) = 0;
    FormatRRASErrorString(&v8, v6, (unsigned int)v5);
  }
  if ( (byte_18002D803 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v8);
LABEL_23:
  result = 0;
  if ( v5 < 0 )
  {
    result = (unsigned __int16)v5;
    if ( (v5 & 0x1FFF0000) != 0x70000 )
      return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800113dc  mov     [rsp-8+arg_10], rbx
0x1800113e1  push    rbp
0x1800113e2  push    rsi
0x1800113e3  push    rdi
0x1800113e4  lea     rbp, [rsp-740h]
0x1800113ec  sub     rsp, 840h
0x1800113f3  mov     rax, cs:__security_cookie
0x1800113fa  xor     rax, rsp
0x1800113fd  mov     [rbp+750h+var_20], rax
0x180011404  mov     rsi, rdx
0x180011407  mov     rdi, rcx
0x18001140a  xor     eax, eax
0x18001140c  lea     rcx, [rsp+850h+var_81C]; void *
0x180011411  xor     edx, edx; Val
0x180011413  mov     [rsp+850h+var_820], eax
0x180011417  mov     r8d, 7FCh; Size
0x18001141d  call    memset_0
0x180011422  xor     r8d, r8d; pMalloc
0x180011425  mov     qword ptr [rdi], 0
0x18001142c  mov     rdx, rdi; ppvObject
0x18001142f  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180011436  call    cs:__imp_CreateXmlWriter
0x18001143c  mov     ebx, eax
0x18001143e  test    eax, eax
0x180011440  jz      short loc_180011465
0x180011442  test    cs:byte_18002D803, 8
0x180011449  jz      loc_1800115BA
0x18001144f  xor     ecx, ecx
0x180011451  lea     rdx, aOpenxmlwriterF_2; "OpenXmlWriter: Failed to create IXmlWri"...
0x180011458  mov     word ptr [rsp+850h+var_820], cx
0x18001145d  mov     r8d, eax
0x180011460  jmp     loc_18001158F
0x180011465  mov     rcx, [rdi]
0x180011468  mov     rdx, rsi
0x18001146b  mov     rax, [rcx]
0x18001146e  mov     rax, [rax+18h]
0x180011472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011477  mov     ebx, eax
0x180011479  test    eax, eax
0x18001147b  jz      short loc_180011496
0x18001147d  test    cs:byte_18002D803, 8
0x180011484  jz      loc_1800115BA
0x18001148a  lea     rdx, aOpenxmlwriterF_1; "OpenXmlWriter: Failed to set the output"...
0x180011491  jmp     loc_180011585
0x180011496  mov     rcx, [rdi]
0x180011499  mov     edx, 1
0x18001149e  mov     r8d, edx
0x1800114a1  mov     rax, [rcx]
0x1800114a4  mov     rax, [rax+28h]
0x1800114a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114ad  mov     ebx, eax
0x1800114af  test    eax, eax
0x1800114b1  jz      short loc_1800114CC
0x1800114b3  test    cs:byte_18002D803, 8
0x1800114ba  jz      loc_1800115BA
0x1800114c0  lea     rdx, aOpenxmlwriterF; "OpenXmlWriter: Failed to set the XmlWri"...
0x1800114c7  jmp     loc_180011585
0x1800114cc  mov     rcx, [rdi]
0x1800114cf  mov     rax, [rcx]
0x1800114d2  mov     rax, [rax+0F8h]
0x1800114d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114de  mov     ebx, eax
0x1800114e0  test    eax, eax
0x1800114e2  jz      short loc_1800114FD
0x1800114e4  test    cs:byte_18002D803, 8
0x1800114eb  jz      loc_1800115BA
0x1800114f1  lea     rdx, aOpenxmlwriterF_0; "OpenXmlWriter: Failed to flush the outp"...
0x1800114f8  jmp     loc_180011585
0x1800114fd  mov     rcx, [rdi]
0x180011500  xor     edx, edx
0x180011502  mov     rax, [rcx]
0x180011505  mov     rax, [rax+0D0h]
0x18001150c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011511  mov     ebx, eax
0x180011513  test    eax, eax
0x180011515  jz      short loc_18001152D
0x180011517  test    cs:byte_18002D803, 8
0x18001151e  jz      loc_1800115BA
0x180011524  lea     rdx, aOpenxmlwriterW; "OpenXmlWriter: WriteStartDocument of IX"...
0x18001152b  jmp     short loc_180011585
0x18001152d  mov     rcx, [rdi]
0x180011530  lea     r8, aProxyconfig; "ProxyConfig"
0x180011537  xor     r9d, r9d
0x18001153a  xor     edx, edx
0x18001153c  mov     rax, [rcx]
0x18001153f  mov     rax, [rax+0D8h]
0x180011546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001154b  mov     ebx, eax
0x18001154d  test    eax, eax
0x18001154f  jnz     short loc_180011575
0x180011551  mov     rcx, [rdi]
0x180011554  lea     r8, aTenantgatewaym; "TenantGatewayMap"
0x18001155b  xor     r9d, r9d
0x18001155e  xor     edx, edx
0x180011560  mov     rax, [rcx]
0x180011563  mov     rax, [rax+0D8h]
0x18001156a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001156f  mov     ebx, eax
0x180011571  test    eax, eax
0x180011573  jz      short loc_1800115BA
0x180011575  test    cs:byte_18002D803, 8
0x18001157c  jz      short loc_1800115BA
0x18001157e  lea     rdx, aOpenxmlwriterW_0; "OpenXmlWriter: WriteStartElement of IXm"...
0x180011585  xor     eax, eax
0x180011587  mov     r8d, ebx
0x18001158a  mov     word ptr [rsp+850h+var_820], ax
0x18001158f  lea     rcx, [rsp+850h+var_820]
0x180011594  call    FormatRRASErrorString
0x180011599  test    cs:byte_18002D803, 8
0x1800115a0  jz      short loc_1800115BA
0x1800115a2  lea     r8, [rsp+850h+var_820]
0x1800115a7  lea     rdx, RasSSTPSvcTraceError
0x1800115ae  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800115b5  call    McTemplateU0z_EventWriteTransfer
0x1800115ba  xor     eax, eax
0x1800115bc  test    ebx, ebx
0x1800115be  jns     short loc_1800115D3
0x1800115c0  mov     eax, ebx
0x1800115c2  and     eax, 1FFF0000h
0x1800115c7  cmp     eax, 70000h
0x1800115cc  movzx   eax, bx
0x1800115cf  jz      short loc_1800115D3
0x1800115d1  mov     eax, ebx
0x1800115d3  mov     rcx, [rbp+750h+var_20]
0x1800115da  xor     rcx, rsp; StackCookie
0x1800115dd  call    __security_check_cookie
0x1800115e2  mov     rbx, [rsp+850h+arg_10]
0x1800115ea  add     rsp, 840h
0x1800115f1  pop     rdi
0x1800115f2  pop     rsi
0x1800115f3  pop     rbp
0x1800115f4  retn
```
