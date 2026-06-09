# CMidiEndpointProtocolWorker::FunctionBlockNamePropertyKeyFromNumber(uchar)

- ea: `0x1400417cc`
- end: `0x1400418ce`
- name: `?FunctionBlockNamePropertyKeyFromNumber@CMidiEndpointProtocolWorker@@AEAA?AU_DEVPROPKEY@@E@Z`
- size: `258`
- prototype: `struct _DEVPROPKEY *__fastcall(CMidiEndpointProtocolWorker *__hidden this, struct _DEVPROPKEY *__return_ptr __struct_ptr retstr, unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400447a0`
- `0x140045550`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x14000984c`
- `0x1400417cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14004188d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14004188d`

## string_xrefs

- `0x140041832`: `CMidiEndpointProtocolWorker::FunctionBlockNamePropertyKeyFromNumber`

## pseudocode

```c
struct _DEVPROPKEY *__fastcall CMidiEndpointProtocolWorker::FunctionBlockNamePropertyKeyFromNumber(
        CMidiEndpointProtocolWorker *this,
        struct _DEVPROPKEY *__return_ptr retstr,
        unsigned __int8 a3)
{
  int v3; // edi
  _DWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  _QWORD *v9; // rax
  DEVPROPGUID v10; // xmm0
  _QWORD *v12; // [rsp+40h] [rbp-48h] BYREF
  const wchar_t *v13; // [rsp+48h] [rbp-40h] BYREF
  CMidiEndpointProtocolWorker *v14; // [rsp+50h] [rbp-38h] BYREF
  const char *v15; // [rsp+58h] [rbp-30h] BYREF
  CLSID pclsid; // [rsp+60h] [rbp-28h] BYREF

  v3 = a3;
  v6 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v9 = (_QWORD *)((char *)this + 56);
    if ( *((_QWORD *)this + 10) > 7u )
      v9 = (_QWORD *)*v9;
    v12 = v9;
    v14 = this;
    v13 = L"Enter";
    v15 = "CMidiEndpointProtocolWorker::FunctionBlockNamePropertyKeyFromNumber";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)&dword_14008C1E4,
      v7,
      v8,
      &v15,
      (__int64)&v14,
      &v13,
      &v12);
  }
  retstr->fmtid = 0;
  retstr->pid = 0;
  pclsid = 0;
  if ( (unsigned __int8)v3 < 0x20u && CLSIDFromString(L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD}", &pclsid) >= 0 )
  {
    v10 = pclsid;
    retstr->pid = v3 + 300;
    retstr->fmtid = v10;
  }
  return retstr;
}

```

## disassembly

```asm
0x1400417cc  mov     [rsp+arg_0], rbx
0x1400417d1  mov     [rsp+arg_10], rsi
0x1400417d6  push    rdi
0x1400417d7  sub     rsp, 80h
0x1400417de  mov     rax, cs:__security_cookie
0x1400417e5  xor     rax, rsp
0x1400417e8  mov     [rsp+88h+var_18], rax
0x1400417ed  movzx   edi, r8b
0x1400417f1  mov     rbx, rdx
0x1400417f4  mov     rsi, rcx
0x1400417f7  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400417fc  mov     rcx, [rax+8]
0x140041800  mov     eax, [rcx]
0x140041802  cmp     eax, 4
0x140041805  jbe     short loc_14004186B
0x140041807  lea     rax, [rsi+38h]
0x14004180b  cmp     qword ptr [rax+18h], 7
0x140041810  jbe     short loc_140041815
0x140041812  mov     rax, [rax]
0x140041815  mov     [rsp+88h+var_48], rax
0x14004181a  lea     rdx, dword_14008C1E4
0x140041821  lea     rax, aEnter; "Enter"
0x140041828  mov     [rsp+88h+var_38], rsi
0x14004182d  mov     [rsp+88h+var_40], rax
0x140041832  lea     rax, aCmidiendpointp_1; "CMidiEndpointProtocolWorker::FunctionBl"...
0x140041839  mov     [rsp+88h+var_30], rax
0x14004183e  lea     rax, [rsp+88h+var_48]
0x140041843  mov     [rsp+88h+var_50], rax
0x140041848  lea     rax, [rsp+88h+var_40]
0x14004184d  mov     [rsp+88h+var_58], rax
0x140041852  lea     rax, [rsp+88h+var_38]
0x140041857  mov     [rsp+88h+var_60], rax
0x14004185c  lea     rax, [rsp+88h+var_30]
0x140041861  mov     [rsp+88h+var_68], rax
0x140041866  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14004186b  xorps   xmm0, xmm0
0x14004186e  xor     eax, eax
0x140041870  movups  xmmword ptr [rbx], xmm0
0x140041873  mov     [rbx+10h], eax
0x140041876  movups  xmmword ptr [rsp+88h+pclsid.Data1], xmm0
0x14004187b  cmp     dil, 20h ; ' '
0x14004187f  jnb     short loc_1400418A9
0x140041881  lea     rdx, [rsp+88h+pclsid]; pclsid
0x140041886  lea     rcx, sz; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD}"
0x14004188d  call    cs:__imp_CLSIDFromString
0x140041893  test    eax, eax
0x140041895  js      short loc_1400418A9
0x140041897  movups  xmm0, xmmword ptr [rsp+88h+pclsid.Data1]
0x14004189c  lea     ecx, [rdi+12Ch]
0x1400418a2  mov     [rbx+10h], ecx
0x1400418a5  movdqu  xmmword ptr [rbx], xmm0
0x1400418a9  mov     rax, rbx
0x1400418ac  mov     rcx, [rsp+88h+var_18]
0x1400418b1  xor     rcx, rsp; StackCookie
0x1400418b4  call    __security_check_cookie
0x1400418b9  lea     r11, [rsp+88h+var_8]
0x1400418c1  mov     rbx, [r11+10h]
0x1400418c5  mov     rsi, [r11+20h]
0x1400418c9  mov     rsp, r11
0x1400418cc  pop     rdi
0x1400418cd  retn
```
