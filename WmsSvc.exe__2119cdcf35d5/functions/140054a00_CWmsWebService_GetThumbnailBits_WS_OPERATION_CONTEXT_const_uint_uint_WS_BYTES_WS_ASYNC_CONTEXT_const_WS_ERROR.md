# CWmsWebService::GetThumbnailBits(_WS_OPERATION_CONTEXT const *,uint,uint,_WS_BYTES *,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)

- ea: `0x140054a00`
- end: `0x140054c01`
- name: `?GetThumbnailBits@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@IIPEAU_WS_BYTES@@PEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z`
- size: `513`
- prototype: `__int64 __usercall@<rax>(const struct _WS_OPERATION_CONTEXT *context@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, struct _WS_BYTES *@<r9>, const struct _WS_ASYNC_CONTEXT *, struct _WS_ERROR *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x14004c43c`
- `0x140054a00`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140054abb`
- `KERNEL32!IsDebuggerPresent` at `0x140054b73`
- `KERNEL32!IsDebuggerPresent` at `0x140054abb`
- `KERNEL32!IsDebuggerPresent` at `0x140054b73`
- `msvcrt!memcpy_s` at `0x140054b24`
- `msvcrt!memcpy_s` at `0x140054b24`
- `ole32!CoTaskMemFree` at `0x140054bbb`
- `ole32!CoTaskMemFree` at `0x140054bbb`
- `webservices!WsAlloc` at `0x140054aff`
- `webservices!WsAlloc` at `0x140054aff`
- `webservices!WsGetOperationContextProperty` at `0x140054a73`
- `webservices!WsGetOperationContextProperty` at `0x140054a73`

## string_xrefs

- `0x140054a9a`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointsession.cpp`
- `0x140054b4f`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointsession.cpp`
- `0x140054a90`: `CWmsWebService::GetThumbnailBits`
- `0x140054b3e`: `CWmsWebService::GetThumbnailBits`

## pseudocode

```c
__int64 __fastcall CWmsWebService::GetThumbnailBits(
        const struct _WS_OPERATION_CONTEXT *context,
        __int64 a2,
        __int64 a3,
        struct _WS_BYTES *a4,
        const struct _WS_ASYNC_CONTEXT *a5,
        struct _WS_ERROR *a6)
{
  HRESULT OperationContextProperty; // ebx
  unsigned int v9; // r13d
  HRESULT v11; // [rsp+30h] [rbp-30h]
  int v12; // [rsp+30h] [rbp-30h]
  HRESULT v13; // [rsp+38h] [rbp-28h]
  int v14; // [rsp+38h] [rbp-28h]
  void *Source; // [rsp+40h] [rbp-20h] BYREF
  WS_HEAP *value; // [rsp+48h] [rbp-18h] BYREF
  void *ptr[2]; // [rsp+50h] [rbp-10h] BYREF

  value = 0;
  Source = 0;
  *(_OWORD *)ptr = 0;
  OperationContextProperty = (*(__int64 (__fastcall **)(struct ISessionService *, __int64, __int64, void **, void **))(*(_QWORD *)CWmsWebService::s_pISessionService + 56LL))(
                               CWmsWebService::s_pISessionService,
                               a2,
                               a3,
                               ptr,
                               &Source);
  if ( OperationContextProperty >= 0 )
  {
    OperationContextProperty = WsGetOperationContextProperty(context, WS_OPERATION_CONTEXT_PROPERTY_HEAP, &value, 8u, 0);
    if ( OperationContextProperty < 0 )
    {
      v9 = 414;
      goto LABEL_4;
    }
    OperationContextProperty = WsAlloc(value, LODWORD(ptr[0]), &ptr[1], 0);
    if ( OperationContextProperty < 0 )
    {
      v9 = 417;
LABEL_4:
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointsession.cpp",
        v9,
        L"CWmsWebService::GetThumbnailBits",
        L"CHRA",
        L"hr",
        OperationContextProperty);
      if ( IsDebuggerPresent() )
      {
        v13 = OperationContextProperty;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointsession.cpp",
          v9,
          L"CWmsWebService::GetThumbnailBits",
          L"CHRA",
          L"hr",
          v13);
      }
      else
      {
        v11 = OperationContextProperty;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointsession.cpp",
          v9,
          L"CWmsWebService::GetThumbnailBits",
          L"CHRA",
          L"hr",
          v11);
      }
      goto LABEL_12;
    }
    if ( !memcpy_s(ptr[1], LODWORD(ptr[0]), Source, LODWORD(ptr[0])) )
    {
      *a4 = *(struct _WS_BYTES *)ptr;
      goto LABEL_14;
    }
    OperationContextProperty = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointsession.cpp",
      0x1A4u,
      L"CWmsWebService::GetThumbnailBits",
      L"CBRA",
      L"err == 0",
      -2147467259);
    if ( IsDebuggerPresent() )
    {
      v14 = -2147467259;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointsession.cpp",
        420,
        L"CWmsWebService::GetThumbnailBits",
        L"CBRA",
        L"err == 0",
        v14);
    }
    else
    {
      v12 = -2147467259;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointsession.cpp",
        420,
        L"CWmsWebService::GetThumbnailBits",
        L"CBRA",
        L"err == 0",
        v12);
    }
  }
LABEL_12:
  if ( a6 )
    CWmsWebService::s_CreateWmsFault(OperationContextProperty, a6);
LABEL_14:
  CoTaskMemFree(Source);
  return (unsigned int)OperationContextProperty;
}

```

## disassembly

```asm
0x140054a00  push    rbp
0x140054a02  push    rbx
0x140054a03  push    rsi
0x140054a04  push    rdi
0x140054a05  push    r13
0x140054a07  push    r14
0x140054a09  push    r15
0x140054a0b  mov     rbp, rsp
0x140054a0e  sub     rsp, 60h
0x140054a12  mov     rdi, r9
0x140054a15  mov     [rbp+value], 0
0x140054a1d  mov     rsi, rcx
0x140054a20  mov     [rbp+Source], 0
0x140054a28  mov     rcx, cs:?s_pISessionService@CWmsWebService@@0PEAUISessionService@@EA; ISessionService * CWmsWebService::s_pISessionService
0x140054a2f  lea     r9, [rbp+Source]
0x140054a33  xorps   xmm0, xmm0
0x140054a36  mov     [rsp+60h+error], r9
0x140054a3b  movups  xmmword ptr [rbp+ptr], xmm0
0x140054a3f  lea     r9, [rbp+ptr]
0x140054a43  mov     rax, [rcx]
0x140054a46  mov     rax, [rax+38h]
0x140054a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054a4f  mov     ebx, eax
0x140054a51  test    eax, eax
0x140054a53  js      loc_140054BA7
0x140054a59  mov     r9d, 8; valueSize
0x140054a5f  mov     [rsp+60h+error], 0; error
0x140054a68  lea     r8, [rbp+value]; value
0x140054a6c  mov     rcx, rsi; context
0x140054a6f  lea     edx, [r9-2]; id
0x140054a73  call    cs:__imp_WsGetOperationContextProperty
0x140054a79  mov     ebx, eax
0x140054a7b  test    eax, eax
0x140054a7d  jns     short loc_140054AF1
0x140054a7f  mov     r13d, 19Eh
0x140054a85  lea     r15, aChra; "CHRA"
0x140054a8c  mov     [rsp+60h+var_38], ebx; int
0x140054a90  lea     rsi, aCwmswebservice_42; "CWmsWebService::GetThumbnailBits"
0x140054a97  mov     r9, r15; unsigned __int16 *
0x140054a9a  lea     rdi, aTermsrvWmsSrcD_16; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140054aa1  mov     r8, rsi; unsigned __int16 *
0x140054aa4  lea     r14, aHr; "hr"
0x140054aab  mov     rcx, rdi; unsigned __int16 *
0x140054aae  mov     edx, r13d; unsigned int
0x140054ab1  mov     [rsp+60h+error], r14; unsigned __int16 *
0x140054ab6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140054abb  call    cs:__imp_IsDebuggerPresent
0x140054ac1  test    eax, eax
0x140054ac3  jz      short loc_140054ADB
0x140054ac5  mov     [rsp+60h+var_28], ebx
0x140054ac9  mov     r9d, r13d
0x140054acc  mov     [rsp+60h+var_30], r14
0x140054ad1  mov     qword ptr [rsp+60h+var_38], r15
0x140054ad6  jmp     loc_140054B8E
0x140054adb  mov     dword ptr [rsp+60h+var_30], ebx
0x140054adf  mov     r8d, r13d
0x140054ae2  mov     qword ptr [rsp+60h+var_38], r14
0x140054ae7  mov     [rsp+60h+error], r15
0x140054aec  jmp     loc_140054BE3
0x140054af1  mov     edx, dword ptr [rbp+ptr]; size
0x140054af4  lea     r8, [rbp+ptr+8]; ptr
0x140054af8  mov     rcx, [rbp+value]; heap
0x140054afc  xor     r9d, r9d; error
0x140054aff  call    cs:__imp_WsAlloc
0x140054b05  mov     ebx, eax
0x140054b07  test    eax, eax
0x140054b09  jns     short loc_140054B16
0x140054b0b  mov     r13d, 1A1h
0x140054b11  jmp     loc_140054A85
0x140054b16  mov     edx, dword ptr [rbp+ptr]; DestinationSize
0x140054b19  mov     r8, [rbp+Source]; Source
0x140054b1d  mov     r9d, edx; SourceSize
0x140054b20  mov     rcx, [rbp+ptr+8]; Destination
0x140054b24  call    cs:__imp_memcpy_s
0x140054b2a  test    eax, eax
0x140054b2c  jz      loc_140054BF7
0x140054b32  mov     ebx, 80004005h
0x140054b37  lea     r13, aCbra; "CBRA"
0x140054b3e  lea     rsi, aCwmswebservice_42; "CWmsWebService::GetThumbnailBits"
0x140054b45  mov     [rsp+60h+var_38], ebx; int
0x140054b49  mov     r14d, 1A4h
0x140054b4f  lea     rdi, aTermsrvWmsSrcD_16; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140054b56  lea     r15, aErr0; "err == 0"
0x140054b5d  mov     r9, r13; unsigned __int16 *
0x140054b60  mov     r8, rsi; unsigned __int16 *
0x140054b63  mov     [rsp+60h+error], r15; unsigned __int16 *
0x140054b68  mov     edx, r14d; unsigned int
0x140054b6b  mov     rcx, rdi; unsigned __int16 *
0x140054b6e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140054b73  call    cs:__imp_IsDebuggerPresent
0x140054b79  test    eax, eax
0x140054b7b  jz      short loc_140054BD2
0x140054b7d  mov     [rsp+60h+var_28], ebx
0x140054b81  mov     r9d, r14d
0x140054b84  mov     [rsp+60h+var_30], r15
0x140054b89  mov     qword ptr [rsp+60h+var_38], r13
0x140054b8e  mov     r8, rdi
0x140054b91  mov     [rsp+60h+error], rsi
0x140054b96  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140054b9d  mov     ecx, 2; unsigned __int8
0x140054ba2  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140054ba7  mov     rdx, [rbp+arg_28]; struct _WS_ERROR *
0x140054bab  test    rdx, rdx
0x140054bae  jz      short loc_140054BB7
0x140054bb0  mov     ecx, ebx; int
0x140054bb2  call    ?s_CreateWmsFault@CWmsWebService@@CAJJPEAU_WS_ERROR@@@Z; CWmsWebService::s_CreateWmsFault(long,_WS_ERROR *)
0x140054bb7  mov     rcx, [rbp+Source]; pv
0x140054bbb  call    cs:__imp_CoTaskMemFree
0x140054bc1  mov     eax, ebx
0x140054bc3  add     rsp, 60h
0x140054bc7  pop     r15
0x140054bc9  pop     r14
0x140054bcb  pop     r13
0x140054bcd  pop     rdi
0x140054bce  pop     rsi
0x140054bcf  pop     rbx
0x140054bd0  pop     rbp
0x140054bd1  retn
0x140054bd2  mov     dword ptr [rsp+60h+var_30], ebx
0x140054bd6  mov     r8d, r14d
0x140054bd9  mov     qword ptr [rsp+60h+var_38], r15
0x140054bde  mov     [rsp+60h+error], r13
0x140054be3  mov     r9, rsi
0x140054be6  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140054bed  mov     rdx, rdi
0x140054bf0  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140054bf5  jmp     short loc_140054BA7
0x140054bf7  movups  xmm0, xmmword ptr [rbp+ptr]
0x140054bfb  movdqu  xmmword ptr [rdi], xmm0
0x140054bff  jmp     short loc_140054BB7
```
