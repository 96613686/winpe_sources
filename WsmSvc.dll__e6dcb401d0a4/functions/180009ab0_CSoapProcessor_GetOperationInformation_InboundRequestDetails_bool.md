# CSoapProcessor::GetOperationInformation(InboundRequestDetails *,bool *)

- ea: `0x180009ab0`
- end: `0x18000a15e`
- name: `?GetOperationInformation@CSoapProcessor@@MEAA_NPEAVInboundRequestDetails@@PEA_N@Z`
- size: `1710`
- prototype: `bool __fastcall(CSoapProcessor *this, struct InboundRequestDetails *, bool *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180005d10`
- `0x180009750`
- `0x180009ab0`
- `0x18002b7a0`
- `0x18008f6a0`
- `0x180112380`
- `0x1801133b0`
- `0x18011a6d4`
- `0x1801ba176`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180009c3f`
- `msvcrt!_wcsicmp` at `0x180009c58`
- `msvcrt!_wcsicmp` at `0x180009c3f`
- `msvcrt!_wcsicmp` at `0x180009c58`

## string_xrefs

- `0x180009bf6`: `http://schemas.xmlsoap.org/ws/2004/09/transfer/Get`
- `0x180009c35`: `http://schemas.microsoft.com/wbem/wsman/1/config/service/Analyze`
- `0x180009c4e`: `http://schemas.microsoft.com/wbem/wsman/1/config/service`
- `0x180009de5`: `http://schemas.xmlsoap.org/ws/2004/08/eventing/Subscribe`
- `0x180009dbc`: `http://schemas.xmlsoap.org/ws/2004/09/enumeration/Release`
- `0x180009e37`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Command`
- `0x180009f69`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Connect`
- `0x180009fca`: `http://schemas.xmlsoap.org/ws/2004/08/eventing/GetStatus`
- `0x180009e9d`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Send`
- `0x180009f9c`: `http://schemas.xmlsoap.org/ws/2004/09/enumeration/Renew`
- `0x180009fb3`: `http://schemas.xmlsoap.org/ws/2004/09/enumeration/GetStatus`
- `0x180009f03`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Disconnect`
- `0x180009f36`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Reconnect`
- `0x180009e6a`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Signal`
- `0x180009fe1`: `http://schemas.xmlsoap.org/ws/2004/08/eventing/Renew`
- `0x180009ed0`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Receive`
- `0x180009e54`: `Command`
- `0x180009ce7`: `Create`
- `0x180009d54`: `Delete`
- `0x180009e0e`: `http://schemas.xmlsoap.org/ws/2004/08/eventing/Unsubscribe`
- `0x18000a00d`: `http://schemas.microsoft.com/wbem/wsman/1/wsman/End`
- `0x180009d6a`: `http://schemas.xmlsoap.org/ws/2004/09/enumeration/Enumerate`
- `0x180009c99`: `http://schemas.xmlsoap.org/ws/2004/09/transfer/Create`
- `0x180009d06`: `http://schemas.xmlsoap.org/ws/2004/09/transfer/Delete`
- `0x180009c66`: `http://schemas.xmlsoap.org/ws/2004/09/transfer/Put`
- `0x180009b18`: `onecore\admin\wmi\wmx\service\soapprocessor.cpp`
- `0x180009d93`: `http://schemas.xmlsoap.org/ws/2004/09/enumeration/Pull`
- `0x180009cf4`: `CreateShell`
- `0x180009d61`: `DeleteShell`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall CSoapProcessor::GetOperationInformation(
        CSoapProcessor *this,
        struct InboundRequestDetails *a2,
        bool *a3)
{
  const wchar_t *v6; // rsi
  _DWORD *v7; // rbp
  struct IRequestContext *v8; // r14
  const wchar_t *Value; // rdi
  const unsigned __int16 *v10; // rax
  int v11; // edi
  const struct Catalog::Resource *Resource; // rax
  const wchar_t *v13; // rcx
  const struct Catalog::Resource *v14; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids, this);
  if ( !a3 )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\soapprocessor.cpp", 0x2E9u, L"745", 0x54Fu, 0);
  *a3 = 0;
  v6 = &Class;
  v7 = (_DWORD *)*((_QWORD *)a2 + 33);
  v8 = (struct IRequestContext *)*((_QWORD *)a2 + 9);
  if ( v7[774] )
  {
    Value = (const wchar_t *)PacketParser::PacketElement<unsigned short const *>::GetValue(v7 + 774);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids, Value);
  }
  else
  {
    Value = &Class;
  }
  if ( v7[756] )
  {
    v6 = (const wchar_t *)PacketParser::PacketElement<unsigned short const *>::GetValue(v7 + 756);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids, v6);
  }
  if ( v7[1074] )
  {
    *((_DWORD *)a2 + 116) = 1;
    *((_DWORD *)a2 + 113) = 1;
    v10 = L"Identify";
LABEL_80:
    *((_QWORD *)a2 + 57) = v10;
    goto LABEL_81;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/transfer/Get") )
    goto LABEL_78;
  if ( !Value )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x8Bu, L"139", 0x54Fu, 0);
  if ( !_wcsicmp(Value, L"http://schemas.microsoft.com/wbem/wsman/1/config/service/Analyze")
    && v6
    && !_wcsicmp(v6, L"http://schemas.microsoft.com/wbem/wsman/1/config/service") )
  {
LABEL_78:
    *((_DWORD *)a2 + 116) = 2;
    v10 = L"Get";
    goto LABEL_79;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/transfer/Put") )
  {
    *((_DWORD *)a2 + 116) = 3;
    v10 = L"Put";
    *((_DWORD *)a2 + 113) = 2;
    goto LABEL_80;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/transfer/Create") )
  {
    v11 = 0;
    if ( v6 )
    {
      Resource = Catalog::GetResource((CSoapProcessor *)((char *)this + 32), v6, v8);
      if ( Resource )
        v11 = *((_BYTE *)Resource + 68) & 1;
    }
    *((_DWORD *)a2 + 116) = v11 != 0 ? 13 : 4;
    v13 = L"Create";
    *((_DWORD *)a2 + 113) = 2 * v11 + 2;
    v10 = L"CreateShell";
LABEL_30:
    if ( !v11 )
      v10 = v13;
    goto LABEL_80;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/transfer/Delete") )
  {
    v11 = 0;
    if ( v6 )
    {
      v14 = Catalog::GetResource((CSoapProcessor *)((char *)this + 32), v6, v8);
      if ( v14 )
        v11 = *((_BYTE *)v14 + 68) & 1;
    }
    *((_DWORD *)a2 + 116) = v11 != 0 ? 14 : 5;
    v13 = L"Delete";
    *((_DWORD *)a2 + 113) = 2 * v11 + 2;
    v10 = L"DeleteShell";
    goto LABEL_30;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/enumeration/Enumerate") )
  {
    *((_DWORD *)a2 + 116) = 7;
    v10 = L"Enumerate";
LABEL_79:
    *((_DWORD *)a2 + 113) = 1;
    goto LABEL_80;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/enumeration/Pull") )
  {
    *((_DWORD *)a2 + 116) = 8;
    v10 = L"Pull";
    goto LABEL_79;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/enumeration/Release") )
  {
    *((_DWORD *)a2 + 116) = 9;
    v10 = L"Release";
    goto LABEL_79;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/08/eventing/Subscribe") )
  {
    *((_DWORD *)a2 + 116) = 10;
    v10 = L"Subscribe";
    goto LABEL_79;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/08/eventing/Unsubscribe") )
  {
    *((_DWORD *)a2 + 116) = 11;
    v10 = L"Unsubscribe";
    goto LABEL_79;
  }
  if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Command") )
  {
    *((_DWORD *)a2 + 116) = 15;
    v10 = L"Command";
    *((_DWORD *)a2 + 113) = 4;
    goto LABEL_80;
  }
  if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Signal") )
  {
    *((_DWORD *)a2 + 116) = 18;
    v10 = L"Signal";
    *((_DWORD *)a2 + 113) = 4;
    goto LABEL_80;
  }
  if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Send") )
  {
    *((_DWORD *)a2 + 116) = 16;
    v10 = L"Send";
    *((_DWORD *)a2 + 113) = 4;
    goto LABEL_80;
  }
  if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Receive") )
  {
    *((_DWORD *)a2 + 116) = 17;
    v10 = L"Receive";
    *((_DWORD *)a2 + 113) = 4;
    goto LABEL_80;
  }
  if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Disconnect") )
  {
    *((_DWORD *)a2 + 116) = 19;
    v10 = L"Disconnect";
    *((_DWORD *)a2 + 113) = 4;
    goto LABEL_80;
  }
  if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Reconnect") )
  {
    *((_DWORD *)a2 + 116) = 20;
    v10 = L"Reconnect";
    *((_DWORD *)a2 + 113) = 4;
    goto LABEL_80;
  }
  if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Connect") )
  {
    *((_DWORD *)a2 + 116) = 21;
    v10 = L"Connect";
    *((_DWORD *)a2 + 113) = 4;
    goto LABEL_80;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/enumeration/Renew")
    || !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/enumeration/GetStatus")
    || !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/08/eventing/GetStatus") )
  {
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)v8 + 64LL))(
      v8,
      2150858771LL,
      1077134280,
      Value);
  }
  else
  {
    if ( wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/08/eventing/Renew") )
    {
      if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/wsman/End") )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids);
        *a3 = 1;
        return 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids, Value);
      *((_DWORD *)a2 + 116) = 6;
      v10 = L"Invoke";
      *((_DWORD *)a2 + 113) = 4;
      goto LABEL_80;
    }
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)v8 + 72LL))(v8, 2150858788LL);
  }
LABEL_81:
  if ( (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)v8 + 144LL))(v8)
    && (unsigned int)(*((_DWORD *)a2 + 116) - 14) <= 7
    && !(unsigned int)PacketParser::ExtractShellId(*((PacketParser **)a2 + 33), v8, (unsigned __int16 *)a2 + 260, 0x25u) )
  {
    return 0;
  }
  return (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)v8 + 144LL))(v8) == 1;
}

```

## disassembly

```asm
0x180009ab0  push    rbx
0x180009ab2  push    rbp
0x180009ab3  push    rsi
0x180009ab4  push    rdi
0x180009ab5  push    r12
0x180009ab7  push    r14
0x180009ab9  push    r15
0x180009abb  sub     rsp, 30h
0x180009abf  mov     r12, r8
0x180009ac2  mov     rbx, rdx
0x180009ac5  mov     r15, rcx
0x180009ac8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009acf  lea     rax, WPP_GLOBAL_Control
0x180009ad6  cmp     rcx, rax
0x180009ad9  jz      short loc_180009AFC
0x180009adb  test    dword ptr [rcx+1Ch], 400h
0x180009ae2  jz      short loc_180009AFC
0x180009ae4  mov     rcx, [rcx+10h]
0x180009ae8  lea     r8, WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids
0x180009aef  mov     edx, 2Ch ; ','
0x180009af4  mov     r9, r15
0x180009af7  call    WPP_SF_q
0x180009afc  test    r12, r12
0x180009aff  jnz     short loc_180009B24
0x180009b01  mov     r9d, 54Fh; unsigned int
0x180009b07  mov     [rsp+68h+var_48], r12; struct IRequestContext *
0x180009b0c  lea     r8, a745; "745"
0x180009b13  mov     edx, 2E9h; unsigned int
0x180009b18  lea     rcx, aOnecoreAdminWm_162; "onecore\\admin\\wmi\\wmx\\service\\soap"...
0x180009b1f  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180009b24  mov     byte ptr [r12], 0
0x180009b29  lea     rsi, Class
0x180009b30  mov     rbp, [rbx+108h]
0x180009b37  mov     r14, [rbx+48h]
0x180009b3b  lea     rcx, [rbp+0C18h]
0x180009b42  cmp     dword ptr [rcx], 0
0x180009b45  jz      short loc_180009B85
0x180009b47  call    ?GetValue@?$PacketElement@PEBG@PacketParser@@QEBAPEBGXZ; PacketParser::PacketElement<ushort const *>::GetValue(void)
0x180009b4c  mov     rdi, rax
0x180009b4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b56  lea     rax, WPP_GLOBAL_Control
0x180009b5d  cmp     rcx, rax
0x180009b60  jz      short loc_180009B88
0x180009b62  test    dword ptr [rcx+1Ch], 400h
0x180009b69  jz      short loc_180009B88
0x180009b6b  mov     rcx, [rcx+10h]
0x180009b6f  lea     r8, WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids
0x180009b76  mov     edx, 2Dh ; '-'
0x180009b7b  mov     r9, rdi
0x180009b7e  call    WPP_SF_S
0x180009b83  jmp     short loc_180009B88
0x180009b85  mov     rdi, rsi
0x180009b88  lea     rcx, [rbp+0BD0h]
0x180009b8f  cmp     dword ptr [rcx], 0
0x180009b92  jz      short loc_180009BD0
0x180009b94  call    ?GetValue@?$PacketElement@PEBG@PacketParser@@QEBAPEBGXZ; PacketParser::PacketElement<ushort const *>::GetValue(void)
0x180009b99  mov     rsi, rax
0x180009b9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ba3  lea     rax, WPP_GLOBAL_Control
0x180009baa  cmp     rcx, rax
0x180009bad  jz      short loc_180009BD0
0x180009baf  test    dword ptr [rcx+1Ch], 400h
0x180009bb6  jz      short loc_180009BD0
0x180009bb8  mov     rcx, [rcx+10h]
0x180009bbc  lea     r8, WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids
0x180009bc3  mov     edx, 2Eh ; '.'
0x180009bc8  mov     r9, rsi
0x180009bcb  call    WPP_SF_S
0x180009bd0  cmp     dword ptr [rbp+10C8h], 0
0x180009bd7  mov     eax, 1
0x180009bdc  jz      short loc_180009BF6
0x180009bde  mov     [rbx+1D0h], eax
0x180009be4  mov     [rbx+1C4h], eax
0x180009bea  lea     rax, aIdentify; "Identify"
0x180009bf1  jmp     loc_18000A0E8
0x180009bf6  lea     rdx, aHttpSchemasXml_27; "http://schemas.xmlsoap.org/ws/2004/09/t"...
0x180009bfd  mov     rcx, rdi; String1
0x180009c00  call    wcscmp_0
0x180009c05  test    eax, eax
0x180009c07  jz      loc_18000A0CD
0x180009c0d  test    rdi, rdi
0x180009c10  jnz     short loc_180009C35
0x180009c12  mov     r9d, 54Fh; unsigned int
0x180009c18  mov     [rsp+68h+var_48], rdi; struct IRequestContext *
0x180009c1d  lea     r8, a139; "139"
0x180009c24  mov     edx, 8Bh; unsigned int
0x180009c29  lea     rcx, aOnecoreAdminWm_90; "onecore\\admin\\wmi\\wmx\\stdlib\\wsman"...
0x180009c30  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180009c35  lea     rdx, aHttpSchemasMic_47; "http://schemas.microsoft.com/wbem/wsman"...
0x180009c3c  mov     rcx, rdi; String1
0x180009c3f  call    cs:__imp__wcsicmp
0x180009c45  test    eax, eax
0x180009c47  jnz     short loc_180009C66
0x180009c49  test    rsi, rsi
0x180009c4c  jz      short loc_180009C66
0x180009c4e  lea     rdx, aHttpSchemasMic_42; "http://schemas.microsoft.com/wbem/wsman"...
0x180009c55  mov     rcx, rsi; String1
0x180009c58  call    cs:__imp__wcsicmp
0x180009c5e  test    eax, eax
0x180009c60  jz      loc_18000A0CD
0x180009c66  lea     rdx, aHttpSchemasXml_2; "http://schemas.xmlsoap.org/ws/2004/09/t"...
0x180009c6d  mov     rcx, rdi; String1
0x180009c70  call    wcscmp_0
0x180009c75  test    eax, eax
0x180009c77  jnz     short loc_180009C99
0x180009c79  mov     dword ptr [rbx+1D0h], 3
0x180009c83  lea     rax, aPut; "Put"
0x180009c8a  mov     dword ptr [rbx+1C4h], 2
0x180009c94  jmp     loc_18000A0E8
0x180009c99  lea     rdx, aHttpSchemasXml_30; "http://schemas.xmlsoap.org/ws/2004/09/t"...
0x180009ca0  mov     rcx, rdi; String1
0x180009ca3  call    wcscmp_0
0x180009ca8  test    eax, eax
0x180009caa  jnz     short loc_180009D06
0x180009cac  xor     edi, edi
0x180009cae  test    rsi, rsi
0x180009cb1  jz      short loc_180009CCE
0x180009cb3  lea     rcx, [r15+20h]; this
0x180009cb7  mov     r8, r14; struct IRequestContext *
0x180009cba  mov     rdx, rsi; unsigned __int16 *
0x180009cbd  call    ?GetResource@Catalog@@QEBAPEBVResource@1@PEBGAEAVIRequestContext@@@Z; Catalog::GetResource(ushort const *,IRequestContext &)
0x180009cc2  test    rax, rax
0x180009cc5  jz      short loc_180009CCE
0x180009cc7  movzx   edi, byte ptr [rax+44h]
0x180009ccb  and     edi, 1
0x180009cce  mov     eax, edi
0x180009cd0  neg     eax
0x180009cd2  lea     eax, ds:2[rdi*2]
0x180009cd9  sbb     ecx, ecx
0x180009cdb  and     ecx, 9
0x180009cde  add     ecx, 4
0x180009ce1  mov     [rbx+1D0h], ecx
0x180009ce7  lea     rcx, aCreate_0; "Create"
0x180009cee  mov     [rbx+1C4h], eax
0x180009cf4  lea     rax, aCreateshell; "CreateShell"
0x180009cfb  test    edi, edi
0x180009cfd  cmovz   rax, rcx
0x180009d01  jmp     loc_18000A0E8
0x180009d06  lea     rdx, aHttpSchemasXml_18; "http://schemas.xmlsoap.org/ws/2004/09/t"...
0x180009d0d  mov     rcx, rdi; String1
0x180009d10  call    wcscmp_0
0x180009d15  test    eax, eax
0x180009d17  jnz     short loc_180009D6A
0x180009d19  xor     edi, edi
0x180009d1b  test    rsi, rsi
0x180009d1e  jz      short loc_180009D3B
0x180009d20  lea     rcx, [r15+20h]; this
0x180009d24  mov     r8, r14; struct IRequestContext *
0x180009d27  mov     rdx, rsi; unsigned __int16 *
0x180009d2a  call    ?GetResource@Catalog@@QEBAPEBVResource@1@PEBGAEAVIRequestContext@@@Z; Catalog::GetResource(ushort const *,IRequestContext &)
0x180009d2f  test    rax, rax
0x180009d32  jz      short loc_180009D3B
0x180009d34  movzx   edi, byte ptr [rax+44h]
0x180009d38  and     edi, 1
0x180009d3b  mov     eax, edi
0x180009d3d  neg     eax
0x180009d3f  lea     eax, ds:2[rdi*2]
0x180009d46  sbb     ecx, ecx
0x180009d48  and     ecx, 9
0x180009d4b  add     ecx, 5
0x180009d4e  mov     [rbx+1D0h], ecx
0x180009d54  lea     rcx, aDelete; "Delete"
0x180009d5b  mov     [rbx+1C4h], eax
0x180009d61  lea     rax, aDeleteshell; "DeleteShell"
0x180009d68  jmp     short loc_180009CFB
0x180009d6a  lea     rdx, aHttpSchemasXml_1; "http://schemas.xmlsoap.org/ws/2004/09/e"...
0x180009d71  mov     rcx, rdi; String1
0x180009d74  call    wcscmp_0
0x180009d79  test    eax, eax
0x180009d7b  jnz     short loc_180009D93
0x180009d7d  mov     dword ptr [rbx+1D0h], 7
0x180009d87  lea     rax, aEnumerate; "Enumerate"
0x180009d8e  jmp     loc_18000A0DE
0x180009d93  lea     rdx, aHttpSchemasXml_31; "http://schemas.xmlsoap.org/ws/2004/09/e"...
0x180009d9a  mov     rcx, rdi; String1
0x180009d9d  call    wcscmp_0
0x180009da2  test    eax, eax
0x180009da4  jnz     short loc_180009DBC
0x180009da6  mov     dword ptr [rbx+1D0h], 8
0x180009db0  lea     rax, aPull; "Pull"
0x180009db7  jmp     loc_18000A0DE
0x180009dbc  lea     rdx, aHttpSchemasXml_19; "http://schemas.xmlsoap.org/ws/2004/09/e"...
0x180009dc3  mov     rcx, rdi; String1
0x180009dc6  call    wcscmp_0
0x180009dcb  test    eax, eax
0x180009dcd  jnz     short loc_180009DE5
0x180009dcf  mov     dword ptr [rbx+1D0h], 9
0x180009dd9  lea     rax, aRelease; "Release"
0x180009de0  jmp     loc_18000A0DE
0x180009de5  lea     rdx, aHttpSchemasXml_28; "http://schemas.xmlsoap.org/ws/2004/08/e"...
0x180009dec  mov     rcx, rdi; String1
0x180009def  call    wcscmp_0
0x180009df4  test    eax, eax
0x180009df6  jnz     short loc_180009E0E
0x180009df8  mov     dword ptr [rbx+1D0h], 0Ah
0x180009e02  lea     rax, aSubscribe; "Subscribe"
0x180009e09  jmp     loc_18000A0DE
0x180009e0e  lea     rdx, aHttpSchemasXml_11; "http://schemas.xmlsoap.org/ws/2004/08/e"...
0x180009e15  mov     rcx, rdi; String1
0x180009e18  call    wcscmp_0
0x180009e1d  test    eax, eax
0x180009e1f  jnz     short loc_180009E37
0x180009e21  mov     dword ptr [rbx+1D0h], 0Bh
0x180009e2b  lea     rax, aUnsubscribe; "Unsubscribe"
0x180009e32  jmp     loc_18000A0DE
0x180009e37  lea     rdx, aHttpSchemasMic_26; "http://schemas.microsoft.com/wbem/wsman"...
0x180009e3e  mov     rcx, rdi; String1
0x180009e41  call    wcscmp_0
0x180009e46  test    eax, eax
0x180009e48  jnz     short loc_180009E6A
0x180009e4a  mov     dword ptr [rbx+1D0h], 0Fh
0x180009e54  lea     rax, aCommand; "Command"
0x180009e5b  mov     dword ptr [rbx+1C4h], 4
0x180009e65  jmp     loc_18000A0E8
0x180009e6a  lea     rdx, aHttpSchemasMic_11; "http://schemas.microsoft.com/wbem/wsman"...
0x180009e71  mov     rcx, rdi; String1
0x180009e74  call    wcscmp_0
0x180009e79  test    eax, eax
0x180009e7b  jnz     short loc_180009E9D
0x180009e7d  mov     dword ptr [rbx+1D0h], 12h
0x180009e87  lea     rax, aSignal_0; "Signal"
0x180009e8e  mov     dword ptr [rbx+1C4h], 4
0x180009e98  jmp     loc_18000A0E8
0x180009e9d  lea     rdx, aHttpSchemasMic_39; "http://schemas.microsoft.com/wbem/wsman"...
0x180009ea4  mov     rcx, rdi; String1
0x180009ea7  call    wcscmp_0
0x180009eac  test    eax, eax
0x180009eae  jnz     short loc_180009ED0
0x180009eb0  mov     dword ptr [rbx+1D0h], 10h
0x180009eba  lea     rax, aSend; "Send"
0x180009ec1  mov     dword ptr [rbx+1C4h], 4
0x180009ecb  jmp     loc_18000A0E8
0x180009ed0  lea     rdx, aHttpSchemasMic_17; "http://schemas.microsoft.com/wbem/wsman"...
0x180009ed7  mov     rcx, rdi; String1
0x180009eda  call    wcscmp_0
0x180009edf  test    eax, eax
0x180009ee1  jnz     short loc_180009F03
0x180009ee3  mov     dword ptr [rbx+1D0h], 11h
0x180009eed  lea     rax, aReceive_0; "Receive"
0x180009ef4  mov     dword ptr [rbx+1C4h], 4
0x180009efe  jmp     loc_18000A0E8
0x180009f03  lea     rdx, aHttpSchemasMic_16; "http://schemas.microsoft.com/wbem/wsman"...
0x180009f0a  mov     rcx, rdi; String1
0x180009f0d  call    wcscmp_0
0x180009f12  test    eax, eax
0x180009f14  jnz     short loc_180009F36
0x180009f16  mov     dword ptr [rbx+1D0h], 13h
0x180009f20  lea     rax, aDisconnect; "Disconnect"
0x180009f27  mov     dword ptr [rbx+1C4h], 4
0x180009f31  jmp     loc_18000A0E8
0x180009f36  lea     rdx, aHttpSchemasMic_35; "http://schemas.microsoft.com/wbem/wsman"...
0x180009f3d  mov     rcx, rdi; String1
0x180009f40  call    wcscmp_0
0x180009f45  test    eax, eax
0x180009f47  jnz     short loc_180009F69
0x180009f49  mov     dword ptr [rbx+1D0h], 14h
0x180009f53  lea     rax, aReconnect; "Reconnect"
0x180009f5a  mov     dword ptr [rbx+1C4h], 4
0x180009f64  jmp     loc_18000A0E8
0x180009f69  lea     rdx, aHttpSchemasMic_48; "http://schemas.microsoft.com/wbem/wsman"...
0x180009f70  mov     rcx, rdi; String1
0x180009f73  call    wcscmp_0
0x180009f78  test    eax, eax
0x180009f7a  jnz     short loc_180009F9C
0x180009f7c  mov     dword ptr [rbx+1D0h], 15h
0x180009f86  lea     rax, aConnect; "Connect"
0x180009f8d  mov     dword ptr [rbx+1C4h], 4
0x180009f97  jmp     loc_18000A0E8
0x180009f9c  lea     rdx, aHttpSchemasXml_13; "http://schemas.xmlsoap.org/ws/2004/09/e"...
0x180009fa3  mov     rcx, rdi; String1
0x180009fa6  call    wcscmp_0
0x180009fab  test    eax, eax
0x180009fad  jz      loc_18000A0AE
0x180009fb3  lea     rdx, aHttpSchemasXml_5; "http://schemas.xmlsoap.org/ws/2004/09/e"...
0x180009fba  mov     rcx, rdi; String1
0x180009fbd  call    wcscmp_0
0x180009fc2  test    eax, eax
0x180009fc4  jz      loc_18000A0AE
0x180009fca  lea     rdx, aHttpSchemasXml_15; "http://schemas.xmlsoap.org/ws/2004/08/e"...
0x180009fd1  mov     rcx, rdi; String1
0x180009fd4  call    wcscmp_0
0x180009fd9  test    eax, eax
0x180009fdb  jz      loc_18000A0AE
0x180009fe1  lea     rdx, aHttpSchemasXml_16; "http://schemas.xmlsoap.org/ws/2004/08/e"...
0x180009fe8  mov     rcx, rdi; String1
0x180009feb  call    wcscmp_0
0x180009ff0  test    eax, eax
0x180009ff2  jnz     short loc_18000A00D
0x180009ff4  mov     rax, [r14]
0x180009ff7  mov     edx, 80338024h
0x180009ffc  mov     rcx, r14
0x180009fff  mov     rax, [rax+48h]
0x18000a003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a008  jmp     loc_18000A0EF
0x18000a00d  lea     rdx, aHttpSchemasMic_41; "http://schemas.microsoft.com/wbem/wsman"...
0x18000a014  mov     rcx, rdi; String1
0x18000a017  call    wcscmp_0
0x18000a01c  test    eax, eax
0x18000a01e  jnz     short loc_18000A05D
0x18000a020  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
