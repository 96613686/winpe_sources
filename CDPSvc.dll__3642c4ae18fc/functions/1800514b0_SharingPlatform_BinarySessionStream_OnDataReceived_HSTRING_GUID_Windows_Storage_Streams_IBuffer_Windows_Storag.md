# SharingPlatform::BinarySessionStream::OnDataReceived(HSTRING__ *,_GUID,Windows::Storage::Streams::IBuffer *,Windows::Storage::Streams::IBuffer *)

- ea: `0x1800514b0`
- end: `0x18005172e`
- name: `?OnDataReceived@BinarySessionStream@SharingPlatform@@UEAAJPEAUHSTRING__@@U_GUID@@PEAUIBuffer@Streams@Storage@Windows@@2@Z`
- size: `638`
- prototype: `int(SharingPlatform::BinarySessionStream *__hidden this, HSTRING, struct _GUID *__struct_ptr, struct Windows::Storage::Streams::IBuffer *, struct Windows::Storage::Streams::IBuffer *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004928`
- `0x18000a580`
- `0x1800130ec`
- `0x180018490`
- `0x18001efa0`
- `0x1800225a0`
- `0x18004a640`
- `0x18005091c`
- `0x180050b1c`
- `0x180051208`
- `0x1800514b0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005157f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005158e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005157f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005158e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051540`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800516fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051540`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800516fc`

## pseudocode

```c
__int64 __fastcall SharingPlatform::BinarySessionStream::OnDataReceived(
        SharingPlatform::BinarySessionStream *this,
        HSTRING a2,
        struct _GUID *a3,
        struct Windows::Storage::Streams::IBuffer *a4,
        struct Windows::Storage::Streams::IBuffer *a5)
{
  char *v5; // r13
  __int64 v6; // rdi
  __int64 (__fastcall *v10)(__int64, struct Windows::Storage::Streams::IBuffer *, __int64 *); // rbx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v15; // rdi
  unsigned __int64 v16; // rdx
  unsigned __int8 v17; // cl
  __int64 v18; // rcx
  RemoteSessionTraceProvider *v19; // rax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, struct Windows::Storage::Streams::IBuffer *, __int64 *); // rbx
  int v22; // eax
  __int64 v23; // rdx
  int v24; // eax
  int v25; // eax
  HSTRING string; // [rsp+20h] [rbp-58h] BYREF
  __int64 v28; // [rsp+28h] [rbp-50h] BYREF
  struct _GUID *v29; // [rsp+30h] [rbp-48h] BYREF
  struct Sharing::IQueuedOperation *v30; // [rsp+38h] [rbp-40h] BYREF
  __int64 v31; // [rsp+40h] [rbp-38h] BYREF
  int v32; // [rsp+48h] [rbp-30h] BYREF
  char *v33; // [rsp+50h] [rbp-28h] BYREF
  struct _GUID *v34; // [rsp+58h] [rbp-20h] BYREF
  char *v35; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v5 = (char *)this - 16;
  v6 = *((_QWORD *)this + 3);
  v31 = 0;
  v34 = a3;
  v10 = *(__int64 (__fastcall **)(__int64, struct Windows::Storage::Streams::IBuffer *, __int64 *))(*(_QWORD *)v6 + 48LL);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v31);
  v11 = v10(v6, a4, &v31);
  v12 = v11;
  if ( v11 >= 0 )
  {
    WindowsDeleteString(0);
    string = 0;
    v13 = anonymous_namespace_::MessageHeaderFromBuffer(v31, (__int64)&string);
    v12 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)".\\binarysessionstream.cpp",
        (const char *)(unsigned int)v13,
        (int)string);
LABEL_20:
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_21;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    v15 = WindowsGetStringRawBuffer(string, 0);
    if ( RemoteSessionTraceProvider::IsEnabled(v17, v16) )
    {
      v19 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                            v18,
                                            _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
      RemoteSessionTraceProvider::LogVerbose_(
        v19,
        L"BinarySessionStream::OnDataReceived appName=%s streamId=%s",
        v15,
        StringRawBuffer);
    }
    v20 = *((_QWORD *)this + 3);
    v28 = 0;
    v21 = *(__int64 (__fastcall **)(__int64, struct Windows::Storage::Streams::IBuffer *, __int64 *))(*(_QWORD *)v20 + 48LL);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v28);
    v22 = v21(v20, a5, &v28);
    v12 = v22;
    if ( v22 >= 0 )
    {
      v22 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IBuffer *, int *))(*(_QWORD *)a5 + 56LL))(
              a5,
              &v32);
      v12 = v22;
      if ( v22 >= 0 )
      {
        v33 = (char *)v28;
        v29 = 0;
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v29);
        v24 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::SharingSessionMessageReceivedEventArgs,SharingPlatform::ISharingSessionMessageReceivedEventArgs,_GUID &,unsigned int &,Windows::Storage::Streams::IDataReader *>(
                &v29,
                v34,
                &v32,
                (__int64 *)&v33);
        v12 = v24;
        if ( v24 >= 0 )
        {
          v34 = v29;
          v35 = (char *)this + 32;
          v30 = 0;
          v33 = v5;
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v30);
          v25 = Microsoft::WRL::Details::MakeAndInitialize<Sharing::InvokeEventSourceOperation<SharingPlatform::IDeviceSessionBinaryChannel,SharingPlatform::ISharingSessionMessageReceivedEventArgs>,Sharing::IQueuedOperation,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::IDeviceSessionBinaryChannel *,SharingPlatform::ISharingSessionMessageReceivedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *,SharingPlatform::BinarySessionStream *,SharingPlatform::ISharingSessionMessageReceivedEventArgs *>(
                  &v30,
                  &v35,
                  &v33,
                  &v34);
          v12 = v25;
          if ( v25 >= 0 )
            v12 = Sharing::OperationQueue::EnqueueOperation(*((PVOID *)this + 7), v30);
          else
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE8,
              (unsigned int)".\\binarysessionstream.cpp",
              (const char *)(unsigned int)v25,
              (int)string);
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v30);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE3,
            (unsigned int)".\\binarysessionstream.cpp",
            (const char *)(unsigned int)v24,
            (int)string);
        }
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v29);
        goto LABEL_19;
      }
      v23 = 223;
    }
    else
    {
      v23 = 220;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)".\\binarysessionstream.cpp",
      (const char *)(unsigned int)v22,
      (int)string);
LABEL_19:
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v28);
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD3,
    (unsigned int)".\\binarysessionstream.cpp",
    (const char *)(unsigned int)v11,
    (int)string);
LABEL_21:
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v31);
  return v12;
}

```

## disassembly

```asm
0x1800514b0  push    rbp
0x1800514b2  push    rbx
0x1800514b3  push    rsi
0x1800514b4  push    rdi
0x1800514b5  push    r12
0x1800514b7  push    r13
0x1800514b9  push    r14
0x1800514bb  push    r15
0x1800514bd  mov     rbp, rsp
0x1800514c0  sub     rsp, 78h
0x1800514c4  mov     rax, cs:__security_cookie
0x1800514cb  xor     rax, rsp
0x1800514ce  mov     [rbp+var_10], rax
0x1800514d2  mov     r15, [rbp+arg_20]
0x1800514d6  lea     r13, [rcx-10h]
0x1800514da  mov     rdi, [r13+28h]
0x1800514de  mov     r14, rcx
0x1800514e1  mov     [rbp+var_38], 0
0x1800514e9  lea     rcx, [rbp+var_38]
0x1800514ed  mov     rsi, r9
0x1800514f0  mov     [rbp+var_20], r8
0x1800514f4  mov     r12, rdx
0x1800514f7  mov     rax, [rdi]
0x1800514fa  mov     rbx, [rax+30h]
0x1800514fe  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180051503  lea     r8, [rbp+var_38]
0x180051507  mov     rdx, rsi
0x18005150a  mov     rcx, rdi
0x18005150d  mov     rax, rbx
0x180051510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051515  xor     esi, esi
0x180051517  mov     ebx, eax
0x180051519  test    eax, eax
0x18005151b  jns     short loc_18005153A
0x18005151d  mov     rcx, [rbp+40h]; this
0x180051521  lea     r8, aBinarysessions_2; ".\\binarysessionstream.cpp"
0x180051528  mov     r9d, eax; char *
0x18005152b  mov     edx, 0D3h; void *
0x180051530  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051535  jmp     loc_180051706
0x18005153a  xor     ecx, ecx; string
0x18005153c  mov     [rbp+string], rsi
0x180051540  call    cs:__imp_WindowsDeleteString
0x180051546  mov     rcx, [rbp+var_38]
0x18005154a  lea     rdx, [rbp+string]
0x18005154e  mov     [rbp+string], rsi
0x180051552  call    _anonymous_namespace___MessageHeaderFromBuffer
0x180051557  mov     ebx, eax
0x180051559  test    eax, eax
0x18005155b  jns     short loc_18005157A
0x18005155d  mov     rcx, [rbp+40h]; this
0x180051561  lea     r8, aBinarysessions_2; ".\\binarysessionstream.cpp"
0x180051568  mov     r9d, eax; char *
0x18005156b  mov     edx, 0D6h; void *
0x180051570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051575  jmp     loc_1800516F8
0x18005157a  xor     edx, edx; length
0x18005157c  mov     rcx, r12; string
0x18005157f  call    cs:__imp_WindowsGetStringRawBuffer
0x180051585  mov     rcx, [rbp+string]; string
0x180051589  xor     edx, edx; length
0x18005158b  mov     rbx, rax
0x18005158e  call    cs:__imp_WindowsGetStringRawBuffer
0x180051594  mov     rdi, rax
0x180051597  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x18005159c  test    al, al
0x18005159e  jz      short loc_1800515C1
0x1800515a0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x1800515a7  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x1800515ac  mov     r9, rbx
0x1800515af  lea     rdx, aBinarysessions_1; "BinarySessionStream::OnDataReceived app"...
0x1800515b6  mov     r8, rdi
0x1800515b9  mov     rcx, rax; this
0x1800515bc  call    ?LogVerbose_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogVerbose_(ushort const *,...)
0x1800515c1  mov     rdi, [r14+18h]
0x1800515c5  lea     rcx, [rbp+var_50]
0x1800515c9  mov     [rbp+var_50], rsi
0x1800515cd  mov     rax, [rdi]
0x1800515d0  mov     rbx, [rax+30h]
0x1800515d4  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800515d9  lea     r8, [rbp+var_50]
0x1800515dd  mov     rdx, r15
0x1800515e0  mov     rcx, rdi
0x1800515e3  mov     rax, rbx
0x1800515e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515eb  mov     ebx, eax
0x1800515ed  test    eax, eax
0x1800515ef  jns     short loc_18005160E
0x1800515f1  mov     edx, 0DCh; void *
0x1800515f6  mov     rcx, [rbp+40h]; this
0x1800515fa  lea     r8, aBinarysessions_2; ".\\binarysessionstream.cpp"
0x180051601  mov     r9d, eax; char *
0x180051604  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051609  jmp     loc_1800516EF
0x18005160e  mov     rax, [r15]
0x180051611  lea     rdx, [rbp+var_30]
0x180051615  mov     rcx, r15
0x180051618  mov     rax, [rax+38h]
0x18005161c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051621  mov     ebx, eax
0x180051623  test    eax, eax
0x180051625  jns     short loc_18005162E
0x180051627  mov     edx, 0DFh
0x18005162c  jmp     short loc_1800515F6
0x18005162e  mov     rax, [rbp+var_50]
0x180051632  lea     rcx, [rbp+var_48]
0x180051636  mov     [rbp+var_28], rax
0x18005163a  mov     [rbp+var_48], rsi
0x18005163e  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180051643  mov     rdx, [rbp+var_20]
0x180051647  lea     r9, [rbp+var_28]
0x18005164b  lea     r8, [rbp+var_30]
0x18005164f  lea     rcx, [rbp+var_48]
0x180051653  call    ??$MakeAndInitialize@VSharingSessionMessageReceivedEventArgs@SharingPlatform@@UISharingSessionMessageReceivedEventArgs@2@AEAU_GUID@@AEAIPEAUIDataReader@Streams@Storage@Windows@@@Details@WRL@Microsoft@@YAJPEAPEAUISharingSessionMessageReceivedEventArgs@SharingPlatform@@AEAU_GUID@@AEAI$$QEAPEAUIDataReader@Streams@Storage@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::SharingSessionMessageReceivedEventArgs,SharingPlatform::ISharingSessionMessageReceivedEventArgs,_GUID &,uint &,Windows::Storage::Streams::IDataReader *>(SharingPlatform::ISharingSessionMessageReceivedEventArgs * *,_GUID &,uint &,Windows::Storage::Streams::IDataReader * &&)
0x180051658  mov     ebx, eax
0x18005165a  test    eax, eax
0x18005165c  jns     short loc_180051678
0x18005165e  mov     rcx, [rbp+40h]; this
0x180051662  lea     r8, aBinarysessions_2; ".\\binarysessionstream.cpp"
0x180051669  mov     r9d, eax; char *
0x18005166c  mov     edx, 0E3h; void *
0x180051671  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051676  jmp     short loc_1800516E6
0x180051678  mov     rax, [rbp+var_48]
0x18005167c  lea     rcx, [rbp+var_40]
0x180051680  mov     [rbp+var_20], rax
0x180051684  lea     rax, [r14+20h]
0x180051688  mov     [rbp+var_18], rax
0x18005168c  mov     [rbp+var_40], rsi
0x180051690  mov     [rbp+var_28], r13
0x180051694  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180051699  lea     r9, [rbp+var_20]
0x18005169d  lea     r8, [rbp+var_28]
0x1800516a1  lea     rdx, [rbp+var_18]
0x1800516a5  lea     rcx, [rbp+var_40]
0x1800516a9  call    ??$MakeAndInitialize@V?$InvokeEventSourceOperation@UIDeviceSessionBinaryChannel@SharingPlatform@@UISharingSessionMessageReceivedEventArgs@2@@Sharing@@UIQueuedOperation@2@PEAV?$EventSource@U?$ITypedEventHandler@PEAUIDeviceSessionBinaryChannel@SharingPlatform@@PEAUISharingSessionMessageReceivedEventArgs@2@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@PEAVBinarySessionStream@SharingPlatform@@PEAUISharingSessionMessageReceivedEventArgs@8@@Details@WRL@Microsoft@@YAJPEAPEAUIQueuedOperation@Sharing@@$$QEAPEAV?$EventSource@U?$ITypedEventHandler@PEAUIDeviceSessionBinaryChannel@SharingPlatform@@PEAUISharingSessionMessageReceivedEventArgs@2@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@$$QEAPEAVBinarySessionStream@SharingPlatform@@$$QEAPEAUISharingSessionMessageReceivedEventArgs@7@@Z; Microsoft::WRL::Details::MakeAndInitialize<Sharing::InvokeEventSourceOperation<SharingPlatform::IDeviceSessionBinaryChannel,SharingPlatform::ISharingSessionMessageReceivedEventArgs>,Sharing::IQueuedOperation,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::IDeviceSessionBinaryChannel *,SharingPlatform::ISharingSessionMessageReceivedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *,SharingPlatform::BinarySessionStream *,SharingPlatform::ISharingSessionMessageReceivedEventArgs *>(Sharing::IQueuedOperation * *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::IDeviceSessionBinaryChannel *,SharingPlatform::ISharingSessionMessageReceivedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> * &&,SharingPlatform::BinarySessionStream * &&,SharingPlatform::ISharingSessionMessageReceivedEventArgs * &&)
0x1800516ae  mov     ebx, eax
0x1800516b0  test    eax, eax
0x1800516b2  jns     short loc_1800516CE
0x1800516b4  mov     rcx, [rbp+40h]; this
0x1800516b8  lea     r8, aBinarysessions_2; ".\\binarysessionstream.cpp"
0x1800516bf  mov     r9d, eax; char *
0x1800516c2  mov     edx, 0E8h; void *
0x1800516c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800516cc  jmp     short loc_1800516DD
0x1800516ce  mov     rdx, [rbp+var_40]; struct Sharing::IQueuedOperation *
0x1800516d2  mov     rcx, [r14+38h]; pv
0x1800516d6  call    ?EnqueueOperation@OperationQueue@Sharing@@QEAAJPEAUIQueuedOperation@2@@Z; Sharing::OperationQueue::EnqueueOperation(Sharing::IQueuedOperation *)
0x1800516db  mov     ebx, eax
0x1800516dd  lea     rcx, [rbp+var_40]
0x1800516e1  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800516e6  lea     rcx, [rbp+var_48]
0x1800516ea  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800516ef  lea     rcx, [rbp+var_50]
0x1800516f3  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800516f8  mov     rcx, [rbp+string]; string
0x1800516fc  call    cs:__imp_WindowsDeleteString
0x180051702  mov     [rbp+string], rsi
0x180051706  lea     rcx, [rbp+var_38]
0x18005170a  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005170f  mov     eax, ebx
0x180051711  mov     rcx, [rbp+var_10]
0x180051715  xor     rcx, rsp; StackCookie
0x180051718  call    __security_check_cookie
0x18005171d  add     rsp, 78h
0x180051721  pop     r15
0x180051723  pop     r14
0x180051725  pop     r13
0x180051727  pop     r12
0x180051729  pop     rdi
0x18005172a  pop     rsi
0x18005172b  pop     rbx
0x18005172c  pop     rbp
0x18005172d  retn
```
