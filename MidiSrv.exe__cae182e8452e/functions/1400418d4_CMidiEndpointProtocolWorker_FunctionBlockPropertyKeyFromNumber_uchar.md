# CMidiEndpointProtocolWorker::FunctionBlockPropertyKeyFromNumber(uchar)

- ea: `0x1400418d4`
- end: `0x140041a33`
- name: `?FunctionBlockPropertyKeyFromNumber@CMidiEndpointProtocolWorker@@AEAA?AU_DEVPROPKEY@@E@Z`
- size: `351`
- prototype: `struct _DEVPROPKEY *__fastcall(CMidiEndpointProtocolWorker *__hidden this, struct _DEVPROPKEY *__return_ptr __struct_ptr retstr, unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400447a0`
- `0x1400457ec`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x14000984c`
- `0x1400418d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140041996`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140041996`

## string_xrefs

- `0x14004190a`: `CMidiEndpointProtocolWorker::FunctionBlockPropertyKeyFromNumber`
- `0x1400419cd`: `CLSIDFromString failed for Function Block Property Key`

## pseudocode

```c
struct _DEVPROPKEY *__fastcall CMidiEndpointProtocolWorker::FunctionBlockPropertyKeyFromNumber(
        CMidiEndpointProtocolWorker *this,
        struct _DEVPROPKEY *__return_ptr retstr,
        unsigned __int8 a3)
{
  int v3; // esi
  const char *v6; // rbx
  _DWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  const char *v10; // rax
  DEVPROPGUID v11; // xmm0
  _DWORD *v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  const char *v16; // [rsp+40h] [rbp-19h] BYREF
  const wchar_t *v17; // [rsp+48h] [rbp-11h] BYREF
  const wchar_t *v18; // [rsp+50h] [rbp-9h] BYREF
  const char *v19; // [rsp+58h] [rbp-1h] BYREF
  CLSID pclsid; // [rsp+60h] [rbp+7h] BYREF

  v3 = a3;
  v6 = (char *)this + 56;
  v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v7 > 4u )
  {
    if ( *((_QWORD *)this + 10) <= 7u )
      v10 = (char *)this + 56;
    else
      v10 = *(const char **)v6;
    v16 = v10;
    v18 = (const wchar_t *)this;
    v17 = L"Enter";
    v19 = "CMidiEndpointProtocolWorker::FunctionBlockPropertyKeyFromNumber";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v7,
      (__int64)byte_14008BED3,
      v8,
      v9,
      &v19,
      (__int64)&v18,
      &v17,
      &v16);
  }
  retstr->fmtid = 0;
  retstr->pid = 0;
  pclsid = 0;
  if ( (unsigned __int8)v3 < 0x20u )
  {
    if ( CLSIDFromString(L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD}", &pclsid) < 0 )
    {
      v12 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v12 > 2u )
      {
        if ( *((_QWORD *)this + 10) > 7u )
          v6 = *(const char **)v6;
        v19 = v6;
        v18 = L"CLSIDFromString failed for Function Block Property Key";
        v17 = (const wchar_t *)this;
        v16 = "CMidiEndpointProtocolWorker::FunctionBlockPropertyKeyFromNumber";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (__int64)v12,
          (__int64)byte_14008B869,
          v13,
          v14,
          &v16,
          (__int64)&v17,
          &v18,
          &v19);
      }
    }
    else
    {
      v11 = pclsid;
      retstr->pid = v3 + 200;
      retstr->fmtid = v11;
    }
  }
  return retstr;
}

```

## disassembly

```asm
0x1400418d4  push    rbp
0x1400418d6  push    rbx
0x1400418d7  push    rsi
0x1400418d8  push    rdi
0x1400418d9  push    r14
0x1400418db  push    r15
0x1400418dd  lea     rbp, [rsp-2Fh]
0x1400418e2  sub     rsp, 88h
0x1400418e9  mov     rax, cs:__security_cookie
0x1400418f0  xor     rax, rsp
0x1400418f3  mov     [rbp+57h+var_40], rax
0x1400418f7  movzx   esi, r8b
0x1400418fb  mov     rdi, rdx
0x1400418fe  mov     r14, rcx
0x140041901  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140041906  lea     rbx, [r14+38h]
0x14004190a  lea     r15, aCmidiendpointp_13; "CMidiEndpointProtocolWorker::FunctionBl"...
0x140041911  mov     rcx, [rax+8]
0x140041915  mov     eax, [rcx]
0x140041917  cmp     eax, 4
0x14004191a  jbe     short loc_140041972
0x14004191c  cmp     qword ptr [rbx+18h], 7
0x140041921  jbe     short loc_140041928
0x140041923  mov     rax, [rbx]
0x140041926  jmp     short loc_14004192B
0x140041928  mov     rax, rbx
0x14004192b  mov     [rbp+57h+var_70], rax
0x14004192f  lea     rdx, byte_14008BED3
0x140041936  lea     rax, aEnter; "Enter"
0x14004193d  mov     [rbp+57h+var_60], r14
0x140041941  mov     [rbp+57h+var_68], rax
0x140041945  lea     rax, [rbp+57h+var_70]
0x140041949  mov     [rsp+0B0h+var_78], rax
0x14004194e  lea     rax, [rbp+57h+var_68]
0x140041952  mov     [rsp+0B0h+var_80], rax
0x140041957  lea     rax, [rbp+57h+var_60]
0x14004195b  mov     [rsp+0B0h+var_88], rax
0x140041960  lea     rax, [rbp+57h+var_58]
0x140041964  mov     [rsp+0B0h+var_90], rax
0x140041969  mov     [rbp+57h+var_58], r15
0x14004196d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140041972  xorps   xmm0, xmm0
0x140041975  xor     eax, eax
0x140041977  movups  xmmword ptr [rdi], xmm0
0x14004197a  mov     [rdi+10h], eax
0x14004197d  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x140041981  cmp     sil, 20h ; ' '
0x140041985  jnb     loc_140041A14
0x14004198b  lea     rdx, [rbp+57h+pclsid]; pclsid
0x14004198f  lea     rcx, sz; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD}"
0x140041996  call    cs:__imp_CLSIDFromString
0x14004199c  test    eax, eax
0x14004199e  js      short loc_1400419B3
0x1400419a0  movups  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x1400419a4  lea     eax, [rsi+0C8h]
0x1400419aa  mov     [rdi+10h], eax
0x1400419ad  movdqu  xmmword ptr [rdi], xmm0
0x1400419b1  jmp     short loc_140041A14
0x1400419b3  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400419b8  mov     rcx, [rax+8]
0x1400419bc  mov     eax, [rcx]
0x1400419be  cmp     eax, 2
0x1400419c1  jbe     short loc_140041A14
0x1400419c3  cmp     qword ptr [rbx+18h], 7
0x1400419c8  jbe     short loc_1400419CD
0x1400419ca  mov     rbx, [rbx]
0x1400419cd  lea     rax, aClsidfromstrin; "CLSIDFromString failed for Function Blo"...
0x1400419d4  mov     [rbp+57h+var_58], rbx
0x1400419d8  mov     [rbp+57h+var_60], rax
0x1400419dc  lea     rdx, byte_14008B869
0x1400419e3  lea     rax, [rbp+57h+var_58]
0x1400419e7  mov     [rbp+57h+var_68], r14
0x1400419eb  mov     [rsp+0B0h+var_78], rax
0x1400419f0  lea     rax, [rbp+57h+var_60]
0x1400419f4  mov     [rsp+0B0h+var_80], rax
0x1400419f9  lea     rax, [rbp+57h+var_68]
0x1400419fd  mov     [rsp+0B0h+var_88], rax
0x140041a02  lea     rax, [rbp+57h+var_70]
0x140041a06  mov     [rsp+0B0h+var_90], rax
0x140041a0b  mov     [rbp+57h+var_70], r15
0x140041a0f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140041a14  mov     rax, rdi
0x140041a17  mov     rcx, [rbp+57h+var_40]
0x140041a1b  xor     rcx, rsp; StackCookie
0x140041a1e  call    __security_check_cookie
0x140041a23  add     rsp, 88h
0x140041a2a  pop     r15
0x140041a2c  pop     r14
0x140041a2e  pop     rdi
0x140041a2f  pop     rsi
0x140041a30  pop     rbx
0x140041a31  pop     rbp
0x140041a32  retn
```
