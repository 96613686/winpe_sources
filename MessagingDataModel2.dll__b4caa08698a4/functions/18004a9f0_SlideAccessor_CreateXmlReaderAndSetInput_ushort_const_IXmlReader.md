# SlideAccessor::_CreateXmlReaderAndSetInput(ushort const *,IXmlReader * *)

- ea: `0x18004a9f0`
- end: `0x18004ab18`
- name: `?_CreateXmlReaderAndSetInput@SlideAccessor@@IEAAJPEBGPEAPEAUIXmlReader@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(SlideAccessor *__hidden this, const unsigned __int16 *, struct IXmlReader **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004ab20`

## callees

- `0x1800013dc`
- `0x180005c50`
- `0x18004a3a8`
- `0x18004a9f0`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x18004aa29`
- `XmlLite!CreateXmlReader` at `0x18004aa29`
- `UserDataTypeHelperUtil!StreamFromStringW` at `0x18004aa5b`
- `UserDataTypeHelperUtil!StreamFromStringW` at `0x18004aa5b`

## string_xrefs

- `0x18004aab3`: `[MessagingDataModel] XmlReader SetInput failed with hr`

## pseudocode

```c
__int64 __fastcall SlideAccessor::_CreateXmlReaderAndSetInput(
        SlideAccessor *this,
        const unsigned __int16 *a2,
        struct IXmlReader **a3)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  int v12; // [rsp+30h] [rbp-30h] BYREF
  const char *v13; // [rsp+38h] [rbp-28h] BYREF
  __int64 v14; // [rsp+40h] [rbp-20h] BYREF
  void *ppvObject; // [rsp+48h] [rbp-18h] BYREF

  ppvObject = 0;
  v5 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v14 = 0;
    v7 = StreamFromStringW(a2, &v14);
    v6 = v7;
    if ( v7 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v14);
      v6 = v8;
      if ( v8 >= 0 )
      {
        *a3 = (struct IXmlReader *)ppvObject;
        ppvObject = 0;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
        v6 = 0;
        goto LABEL_10;
      }
      if ( (unsigned int)dword_1800FD5F0 > 3 )
      {
        v12 = v8;
        v13 = "[MessagingDataModel] XmlReader SetInput failed with hr";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)dword_1800FD5F0,
          (int)byte_1800EB1B3,
          v9,
          v10,
          (const unsigned __int16 **)&v13,
          (__int64)&v12);
      }
    }
    else
    {
      Log_HREvent_23(v7);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  }
  else
  {
    Log_HREvent_23(v5);
  }
LABEL_10:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppvObject);
  return v6;
}

```

## disassembly

```asm
0x18004a9f0  mov     [rsp-18h+arg_0], rbx
0x18004a9f5  push    rbp
0x18004a9f6  push    rsi
0x18004a9f7  push    rdi
0x18004a9f8  mov     rbp, rsp
0x18004a9fb  sub     rsp, 60h
0x18004a9ff  mov     rax, cs:__security_cookie
0x18004aa06  xor     rax, rsp
0x18004aa09  mov     [rbp+var_10], rax
0x18004aa0d  mov     rsi, r8
0x18004aa10  mov     [rbp+ppvObject], 0
0x18004aa18  mov     rdi, rdx
0x18004aa1b  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18004aa22  xor     r8d, r8d; pMalloc
0x18004aa25  lea     rdx, [rbp+ppvObject]; ppvObject
0x18004aa29  call    cs:__imp_CreateXmlReader
0x18004aa2f  mov     ebx, eax
0x18004aa31  test    eax, eax
0x18004aa33  jns     short loc_18004AA4C
0x18004aa35  mov     edx, 1
0x18004aa3a  mov     r9d, 0B6h
0x18004aa40  mov     ecx, eax; int
0x18004aa42  call    Log_HREvent_23
0x18004aa47  jmp     loc_18004AAF1
0x18004aa4c  lea     rdx, [rbp+var_20]
0x18004aa50  mov     [rbp+var_20], 0
0x18004aa58  mov     rcx, rdi
0x18004aa5b  call    cs:__imp_StreamFromStringW
0x18004aa61  mov     ebx, eax
0x18004aa63  test    eax, eax
0x18004aa65  jns     short loc_18004AA84
0x18004aa67  mov     edx, 1
0x18004aa6c  mov     r9d, 0B9h
0x18004aa72  mov     ecx, eax; int
0x18004aa74  call    Log_HREvent_23
0x18004aa79  lea     rcx, [rbp+var_20]
0x18004aa7d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004aa82  jmp     short loc_18004AAF1
0x18004aa84  mov     rcx, [rbp+ppvObject]
0x18004aa88  mov     rdx, [rbp+var_20]
0x18004aa8c  mov     rax, [rcx]
0x18004aa8f  mov     rax, [rax+18h]
0x18004aa93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa98  mov     ebx, eax
0x18004aa9a  test    eax, eax
0x18004aa9c  jns     short loc_18004AAD7
0x18004aa9e  mov     ecx, cs:dword_1800FD5F0
0x18004aaa4  cmp     ecx, 3
0x18004aaa7  jbe     short loc_18004AA79
0x18004aaa9  mov     [rbp+var_30], eax
0x18004aaac  lea     rdx, byte_1800EB1B3
0x18004aab3  lea     rax, aMessagingdatam_4; "[MessagingDataModel] XmlReader SetInput"...
0x18004aaba  mov     [rbp+var_28], rax
0x18004aabe  lea     rax, [rbp+var_30]
0x18004aac2  mov     [rsp+60h+var_38], rax
0x18004aac7  lea     rax, [rbp+var_28]
0x18004aacb  mov     [rsp+60h+var_40], rax
0x18004aad0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004aad5  jmp     short loc_18004AA79
0x18004aad7  mov     rax, [rbp+ppvObject]
0x18004aadb  lea     rcx, [rbp+var_20]
0x18004aadf  mov     [rsi], rax
0x18004aae2  mov     [rbp+ppvObject], 0
0x18004aaea  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004aaef  xor     ebx, ebx
0x18004aaf1  lea     rcx, [rbp+ppvObject]
0x18004aaf5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004aafa  mov     eax, ebx
0x18004aafc  mov     rcx, [rbp+var_10]
0x18004ab00  xor     rcx, rsp; StackCookie
0x18004ab03  call    __security_check_cookie
0x18004ab08  mov     rbx, [rsp+60h+arg_0]
0x18004ab10  add     rsp, 60h
0x18004ab14  pop     rdi
0x18004ab15  pop     rsi
0x18004ab16  pop     rbp
0x18004ab17  retn
```
