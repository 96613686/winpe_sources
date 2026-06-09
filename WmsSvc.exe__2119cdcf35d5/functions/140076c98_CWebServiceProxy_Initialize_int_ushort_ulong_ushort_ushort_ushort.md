# CWebServiceProxy::Initialize(int,ushort *,ulong,ushort *,ushort *,ushort *)

- ea: `0x140076c98`
- end: `0x140077044`
- name: `?Initialize@CWebServiceProxy@@QEAAJHPEAGK000@Z`
- size: `940`
- prototype: `int(CWebServiceProxy *__hidden this, int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `9`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140057ed8`
- `0x140058260`
- `0x140058644`
- `0x1400588d8`
- `0x140058b04`
- `0x140058d10`
- `0x140058f24`
- `0x140059214`
- `0x14007704c`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140063a08`
- `0x140063e7c`
- `0x140076c98`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140076d1c`
- `KERNEL32!IsDebuggerPresent` at `0x140076e02`
- `KERNEL32!IsDebuggerPresent` at `0x140076d1c`
- `KERNEL32!IsDebuggerPresent` at `0x140076e02`
- `OLEAUT32!__imp_SysAllocString` at `0x140076cc5`
- `OLEAUT32!__imp_SysAllocString` at `0x140076d8d`
- `OLEAUT32!__imp_SysAllocString` at `0x140076cc5`
- `OLEAUT32!__imp_SysAllocString` at `0x140076d8d`
- `webservices!WsCreateError` at `0x140076dba`
- `webservices!WsCreateError` at `0x140076dba`
- `webservices!WsCreateHeap` at `0x140076e4a`
- `webservices!WsCreateHeap` at `0x140076e4a`
- `webservices!WsCreateServiceProxy` at `0x140076fe8`
- `webservices!WsCreateServiceProxy` at `0x140076fe8`
- `webservices!WsOpenServiceProxy` at `0x14007700c`
- `webservices!WsOpenServiceProxy` at `0x14007700c`

## string_xrefs

- `0x140076ceb`: `CWebServiceProxy::Initialize`
- `0x140076dd7`: `CWebServiceProxy::Initialize`
- `0x140076cfd`: `termsrv\wms\src\common\srcutils\cwebserviceproxy.cpp`
- `0x140076de1`: `termsrv\wms\src\common\srcutils\cwebserviceproxy.cpp`

## pseudocode

```c
__int64 __fastcall CWebServiceProxy::Initialize(
        CWebServiceProxy *this,
        int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned __int16 *psz,
        unsigned __int16 *a7)
{
  BSTR v10; // rax
  const unsigned __int16 *v11; // r12
  unsigned int v12; // r15d
  int Error; // ebx
  unsigned __int16 *v14; // rsi
  BSTR v15; // rax
  WS_ERROR **v16; // rbp
  unsigned int v17; // r15d
  struct _WS_HEAP **v18; // r15
  const WS_SECURITY_DESCRIPTION *v19; // r8
  struct _WS_HEAP *v20; // rcx
  ULONG channelPropertyCount[2]; // [rsp+30h] [rbp-78h]
  WS_SERVICE_PROXY **serviceProxy; // [rsp+38h] [rbp-70h]
  WS_ERROR *v24; // [rsp+40h] [rbp-68h]
  WS_CHANNEL_PROPERTY channelProperties; // [rsp+50h] [rbp-58h] BYREF
  int v26; // [rsp+B0h] [rbp+8h] BYREF
  unsigned int v27; // [rsp+C8h] [rbp+20h]

  v27 = a4;
  v26 = 104857600;
  v10 = SysAllocString(a3);
  *((_QWORD *)this + 40) = v10;
  if ( !v10 )
  {
    v11 = L"m_bstrHostName";
    v12 = 102;
    goto LABEL_3;
  }
  v14 = psz;
  if ( psz )
  {
    v15 = SysAllocString(psz);
    *((_QWORD *)this + 41) = v15;
    if ( !v15 )
    {
      v11 = L"m_bstrUserName";
      v12 = 107;
LABEL_3:
      Error = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
        v12,
        L"CWebServiceProxy::Initialize",
        L"CPR",
        v11,
        -2147024882);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
          v12,
          L"CWebServiceProxy::Initialize",
          L"CPR",
          v11,
          -2147024882);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
          v12,
          L"CWebServiceProxy::Initialize",
          L"CPR",
          v11,
          -2147024882);
      return (unsigned int)Error;
    }
  }
  v16 = (WS_ERROR **)((char *)this + 8);
  Error = WsCreateError(0, 0, (WS_ERROR **)this + 1);
  if ( Error < 0 )
  {
    v17 = 112;
    goto LABEL_13;
  }
  v18 = (struct _WS_HEAP **)((char *)this + 16);
  Error = WsCreateHeap(0x100000u, 0x200u, 0, 0, (WS_HEAP **)this + 2, *v16);
  if ( Error < 0 )
  {
    v17 = 116;
LABEL_13:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
      v17,
      L"CWebServiceProxy::Initialize",
      L"CHRA",
      L"hr",
      Error);
    if ( IsDebuggerPresent() )
    {
      LODWORD(serviceProxy) = Error;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
        v17,
        L"CWebServiceProxy::Initialize",
        L"CHRA",
        L"hr",
        serviceProxy);
    }
    else
    {
      channelPropertyCount[0] = Error;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
        v17,
        L"CWebServiceProxy::Initialize",
        L"CHRA",
        L"hr",
        *(_QWORD *)channelPropertyCount);
    }
    return (unsigned int)Error;
  }
  Error = ConstructUri(*v18, a2, a3, v27, a5, (struct _WS_STRING *)this + 16);
  if ( Error < 0 )
    return (unsigned int)Error;
  v19 = 0;
  if ( a2 != 2 )
  {
LABEL_23:
    channelProperties.id = WS_CHANNEL_PROPERTY_MAX_BUFFERED_MESSAGE_SIZE;
    channelProperties.value = &v26;
    v24 = *v16;
    channelProperties.valueSize = 4;
    Error = WsCreateServiceProxy(
              WS_CHANNEL_TYPE_REQUEST,
              WS_HTTP_CHANNEL_BINDING,
              v19,
              0,
              0,
              &channelProperties,
              1u,
              (WS_SERVICE_PROXY **)this + 39,
              v24);
    if ( Error >= 0 )
    {
      Error = WsOpenServiceProxy(
                *((WS_SERVICE_PROXY **)this + 39),
                (const WS_ENDPOINT_ADDRESS *)((char *)this + 256),
                0,
                *v16);
      if ( Error >= 0 )
      {
        *((_DWORD *)this + 6) = 1;
        return (unsigned int)Error;
      }
      v17 = 189;
    }
    else
    {
      v17 = 185;
    }
    goto LABEL_13;
  }
  v20 = *v18;
  *((_DWORD *)this + 8) = 1;
  Error = BstrToWsString(v20, v14, (struct _WS_STRING *)((char *)this + 40));
  if ( Error >= 0 )
  {
    Error = BstrToWsString(*v18, a7, (struct _WS_STRING *)((char *)this + 56));
    if ( Error >= 0 )
    {
      *((_DWORD *)this + 48) = 16;
      *((_QWORD *)this + 38) = 0;
      *((_QWORD *)this + 23) = (char *)this + 296;
      *((_QWORD *)this + 37) = CWebServiceProxy::s_VerifyServerCert;
      *((_DWORD *)this + 50) = 20;
      *((_DWORD *)this + 44) = 23;
      *((_DWORD *)this + 84) = 4;
      *((_QWORD *)this + 26) = (char *)this + 336;
      v19 = (const WS_SECURITY_DESCRIPTION *)((char *)this + 224);
      *((_QWORD *)this + 17) = (char *)this + 176;
      *((_QWORD *)this + 20) = (char *)this + 128;
      *((_DWORD *)this + 18) = 4;
      *((_QWORD *)this + 21) = (char *)this + 72;
      *((_QWORD *)this + 28) = (char *)this + 160;
      *((_DWORD *)this + 54) = 4;
      *((_DWORD *)this + 32) = 1;
      *((_DWORD *)this + 36) = 2;
      *((_DWORD *)this + 24) = 1;
      *((_QWORD *)this + 13) = (char *)this + 32;
      *((_DWORD *)this + 58) = 2;
      goto LABEL_23;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x140076c98  mov     rax, rsp
0x140076c9b  mov     [rax+10h], rbx
0x140076c9f  mov     [rax+20h], r9d
0x140076ca3  push    rbp
0x140076ca4  push    rsi
0x140076ca5  push    rdi
0x140076ca6  push    r12
0x140076ca8  push    r13
0x140076caa  push    r14
0x140076cac  push    r15
0x140076cae  sub     rsp, 70h
0x140076cb2  mov     rdi, rcx
0x140076cb5  mov     dword ptr [rax+8], 6400000h
0x140076cbc  mov     rcx, r8; psz
0x140076cbf  mov     r12, r8
0x140076cc2  mov     r14d, edx
0x140076cc5  call    cs:__imp_SysAllocString
0x140076ccb  mov     [rdi+140h], rax
0x140076cd2  test    rax, rax
0x140076cd5  jnz     loc_140076D7D
0x140076cdb  lea     r12, aMBstrhostname; "m_bstrHostName"
0x140076ce2  lea     r15d, [rax+66h]
0x140076ce6  mov     ebp, 8007000Eh
0x140076ceb  lea     rsi, aCwebservicepro; "CWebServiceProxy::Initialize"
0x140076cf2  lea     r14, aCpr; "CPR"
0x140076cf9  mov     dword ptr [rsp+0A8h+error], ebp; int
0x140076cfd  lea     rdi, aTermsrvWmsSrcC_9; "termsrv\\wms\\src\\common\\srcutils\\cw"...
0x140076d04  mov     [rsp+0A8h+heap], r12; unsigned __int16 *
0x140076d09  mov     r8, rsi; unsigned __int16 *
0x140076d0c  mov     r9, r14; unsigned __int16 *
0x140076d0f  mov     rcx, rdi; unsigned __int16 *
0x140076d12  mov     edx, r15d; unsigned int
0x140076d15  mov     ebx, ebp
0x140076d17  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140076d1c  call    cs:__imp_IsDebuggerPresent
0x140076d22  test    eax, eax
0x140076d24  jz      short loc_140076D55
0x140076d26  mov     dword ptr [rsp+0A8h+serviceProxy], ebp
0x140076d2a  mov     qword ptr [rsp+0A8h+channelPropertyCount], r12
0x140076d2f  mov     [rsp+0A8h+error], r14
0x140076d34  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140076d3b  mov     r9d, r15d
0x140076d3e  mov     [rsp+0A8h+heap], rsi
0x140076d43  mov     r8, rdi
0x140076d46  mov     ecx, 2; unsigned __int8
0x140076d4b  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140076d50  jmp     loc_14007702A
0x140076d55  mov     [rsp+0A8h+channelPropertyCount], ebp
0x140076d59  mov     [rsp+0A8h+error], r12
0x140076d5e  mov     r9, rsi
0x140076d61  mov     [rsp+0A8h+heap], r14
0x140076d66  mov     r8d, r15d
0x140076d69  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140076d70  mov     rdx, rdi
0x140076d73  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140076d78  jmp     loc_14007702A
0x140076d7d  mov     rsi, [rsp+0A8h+psz]
0x140076d85  test    rsi, rsi
0x140076d88  jz      short loc_140076DAF
0x140076d8a  mov     rcx, rsi; psz
0x140076d8d  call    cs:__imp_SysAllocString
0x140076d93  mov     [rdi+148h], rax
0x140076d9a  test    rax, rax
0x140076d9d  jnz     short loc_140076DAF
0x140076d9f  lea     r12, aMBstrusername; "m_bstrUserName"
0x140076da6  lea     r15d, [rax+6Bh]
0x140076daa  jmp     loc_140076CE6
0x140076daf  lea     rbp, [rdi+8]
0x140076db3  xor     edx, edx; propertyCount
0x140076db5  mov     r8, rbp; error
0x140076db8  xor     ecx, ecx; properties
0x140076dba  call    cs:__imp_WsCreateError
0x140076dc0  mov     ebx, eax
0x140076dc2  test    eax, eax
0x140076dc4  jns     short loc_140076E28
0x140076dc6  mov     r15d, 70h ; 'p'
0x140076dcc  lea     r14, aChra; "CHRA"
0x140076dd3  mov     dword ptr [rsp+0A8h+error], ebx; int
0x140076dd7  lea     rsi, aCwebservicepro; "CWebServiceProxy::Initialize"
0x140076dde  mov     r9, r14; unsigned __int16 *
0x140076de1  lea     rdi, aTermsrvWmsSrcC_9; "termsrv\\wms\\src\\common\\srcutils\\cw"...
0x140076de8  mov     r8, rsi; unsigned __int16 *
0x140076deb  lea     rbp, aHr; "hr"
0x140076df2  mov     rcx, rdi; unsigned __int16 *
0x140076df5  mov     edx, r15d; unsigned int
0x140076df8  mov     [rsp+0A8h+heap], rbp; unsigned __int16 *
0x140076dfd  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140076e02  call    cs:__imp_IsDebuggerPresent
0x140076e08  test    eax, eax
0x140076e0a  jz      short loc_140076E1A
0x140076e0c  mov     dword ptr [rsp+0A8h+serviceProxy], ebx
0x140076e10  mov     qword ptr [rsp+0A8h+channelPropertyCount], rbp
0x140076e15  jmp     loc_140076D2F
0x140076e1a  mov     [rsp+0A8h+channelPropertyCount], ebx
0x140076e1e  mov     [rsp+0A8h+error], rbp
0x140076e23  jmp     loc_140076D5E
0x140076e28  mov     rax, [rbp+0]
0x140076e2c  lea     r15, [rdi+10h]
0x140076e30  mov     [rsp+0A8h+error], rax; error
0x140076e35  xor     r9d, r9d; propertyCount
0x140076e38  xor     r8d, r8d; properties
0x140076e3b  mov     [rsp+0A8h+heap], r15; heap
0x140076e40  mov     edx, 200h; trimSize
0x140076e45  mov     ecx, 100000h; maxSize
0x140076e4a  call    cs:__imp_WsCreateHeap
0x140076e50  mov     ebx, eax
0x140076e52  test    eax, eax
0x140076e54  jns     short loc_140076E61
0x140076e56  mov     r15d, 74h ; 't'
0x140076e5c  jmp     loc_140076DCC
0x140076e61  mov     rax, [rsp+0A8h+arg_20]
0x140076e69  lea     r13, [rdi+100h]
0x140076e70  mov     r9d, [rsp+0A8h+arg_18]; unsigned int
0x140076e78  mov     r8, r12; unsigned __int16 *
0x140076e7b  mov     rcx, [r15]; struct _WS_HEAP *
0x140076e7e  mov     edx, r14d; int
0x140076e81  mov     [rsp+0A8h+error], r13; struct _WS_STRING *
0x140076e86  mov     [rsp+0A8h+heap], rax; unsigned __int16 *
0x140076e8b  call    ?ConstructUri@@YAJPEAU_WS_HEAP@@HPEAGK1PEAU_WS_STRING@@@Z; ConstructUri(_WS_HEAP *,int,ushort *,ulong,ushort *,_WS_STRING *)
0x140076e90  xor     r12d, r12d
0x140076e93  mov     ebx, eax
0x140076e95  test    eax, eax
0x140076e97  js      loc_14007702A
0x140076e9d  lea     r9d, [r12+1]
0x140076ea2  mov     r8d, r12d
0x140076ea5  lea     r10d, [r12+4]
0x140076eaa  cmp     r14d, 2
0x140076eae  jnz     loc_140076FA0
0x140076eb4  mov     rcx, [r15]; heap
0x140076eb7  lea     r14, [rdi+20h]
0x140076ebb  lea     r8, [r14+8]; struct _WS_STRING *
0x140076ebf  mov     [r14], r9d
0x140076ec2  mov     rdx, rsi; unsigned __int16 *
0x140076ec5  call    ?BstrToWsString@@YAJPEAU_WS_HEAP@@PEAGPEAU_WS_STRING@@@Z; BstrToWsString(_WS_HEAP *,ushort *,_WS_STRING *)
0x140076eca  mov     ebx, eax
0x140076ecc  test    eax, eax
0x140076ece  js      loc_14007702A
0x140076ed4  mov     rdx, [rsp+0A8h+arg_30]; unsigned __int16 *
0x140076edc  lea     r8, [r14+18h]; struct _WS_STRING *
0x140076ee0  mov     rcx, [r15]; heap
0x140076ee3  call    ?BstrToWsString@@YAJPEAU_WS_HEAP@@PEAGPEAU_WS_STRING@@@Z; BstrToWsString(_WS_HEAP *,ushort *,_WS_STRING *)
0x140076ee8  mov     ebx, eax
0x140076eea  test    eax, eax
0x140076eec  js      loc_14007702A
0x140076ef2  lea     rax, [rdi+128h]
0x140076ef9  mov     dword ptr [rdi+0C0h], 10h
0x140076f03  lea     r10d, [r12+4]
0x140076f08  mov     [rax+8], r12
0x140076f0c  lea     rcx, ?s_VerifyServerCert@CWebServiceProxy@@CAJPEBU_CERT_CONTEXT@@PEAX@Z; CWebServiceProxy::s_VerifyServerCert(_CERT_CONTEXT const *,void *)
0x140076f13  mov     [rdi+0B8h], rax
0x140076f1a  mov     [rax], rcx
0x140076f1d  lea     rdx, [rdi+80h]
0x140076f24  lea     rcx, [rdi+0B0h]
0x140076f2b  mov     dword ptr [rdi+0C8h], 14h
0x140076f35  lea     rax, [rdi+150h]
0x140076f3c  mov     dword ptr [rcx], 17h
0x140076f42  lea     r9d, [r12+1]
0x140076f47  mov     [rax], r10d
0x140076f4a  mov     [rdi+0D0h], rax
0x140076f51  lea     r8, [rdi+0E0h]; securityDescription
0x140076f58  lea     rax, [rdi+0A0h]
0x140076f5f  mov     [rdi+88h], rcx
0x140076f66  lea     rcx, [rdi+48h]
0x140076f6a  mov     [rax], rdx
0x140076f6d  mov     [rcx], r10d
0x140076f70  mov     [rdi+0A8h], rcx
0x140076f77  mov     [r8], rax
0x140076f7a  mov     [rdi+0D8h], r10d
0x140076f81  mov     [rdx], r9d
0x140076f84  mov     dword ptr [rdi+90h], 2
0x140076f8e  mov     [rdi+60h], r9d
0x140076f92  mov     [rdi+68h], r14
0x140076f96  mov     dword ptr [rdi+0E8h], 2
0x140076fa0  lea     rax, [rsp+0A8h+arg_0]
0x140076fa8  mov     [rsp+0A8h+channelProperties.id], r12d
0x140076fad  mov     [rsp+0A8h+channelProperties.value], rax
0x140076fb2  lea     rsi, [rdi+138h]
0x140076fb9  mov     rax, [rbp+0]
0x140076fbd  xor     edx, edx; channelBinding
0x140076fbf  mov     [rsp+0A8h+var_68], rax; error
0x140076fc4  lea     rax, [rsp+0A8h+channelProperties]
0x140076fc9  mov     [rsp+0A8h+serviceProxy], rsi; serviceProxy
0x140076fce  mov     [rsp+0A8h+channelPropertyCount], r9d; channelPropertyCount
0x140076fd3  xor     r9d, r9d; properties
0x140076fd6  mov     [rsp+0A8h+error], rax; channelProperties
0x140076fdb  lea     ecx, [rdx+8]; channelType
0x140076fde  mov     dword ptr [rsp+0A8h+heap], r12d; propertyCount
0x140076fe3  mov     [rsp+0A8h+channelProperties.valueSize], r10d
0x140076fe8  call    cs:__imp_WsCreateServiceProxy
0x140076fee  mov     ebx, eax
0x140076ff0  test    eax, eax
0x140076ff2  jns     short loc_140076FFF
0x140076ff4  mov     r15d, 0B9h
0x140076ffa  jmp     loc_140076DCC
0x140076fff  mov     r9, [rbp+0]; error
0x140077003  xor     r8d, r8d; asyncContext
0x140077006  mov     rcx, [rsi]; serviceProxy
0x140077009  mov     rdx, r13; address
0x14007700c  call    cs:__imp_WsOpenServiceProxy
0x140077012  mov     ebx, eax
0x140077014  test    eax, eax
0x140077016  jns     short loc_140077023
0x140077018  mov     r15d, 0BDh
0x14007701e  jmp     loc_140076DCC
0x140077023  mov     dword ptr [rdi+18h], 1
0x14007702a  mov     eax, ebx
0x14007702c  mov     rbx, [rsp+0A8h+arg_8]
0x140077034  add     rsp, 70h
0x140077038  pop     r15
0x14007703a  pop     r14
0x14007703c  pop     r13
0x14007703e  pop     r12
0x140077040  pop     rdi
0x140077041  pop     rsi
0x140077042  pop     rbp
0x140077043  retn
```
