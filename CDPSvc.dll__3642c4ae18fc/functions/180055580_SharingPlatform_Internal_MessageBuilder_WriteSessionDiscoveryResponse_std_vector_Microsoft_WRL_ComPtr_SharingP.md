# SharingPlatform::Internal::MessageBuilder::WriteSessionDiscoveryResponse(std::vector<Microsoft::WRL::ComPtr<SharingPlatform::ISession>,std::allocator<Microsoft::WRL::ComPtr<SharingPlatform::ISession>>> const &,Windows::Storage::Streams::IBuffer * *)

- ea: `0x180055580`
- end: `0x180055861`
- name: `?WriteSessionDiscoveryResponse@MessageBuilder@Internal@SharingPlatform@@SAJAEBV?$vector@V?$ComPtr@UISession@SharingPlatform@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UISession@SharingPlatform@@@WRL@Microsoft@@@std@@@std@@PEAPEAUIBuffer@Streams@Storage@Windows@@@Z`
- size: `737`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180020ff0`

## callees

- `0x180004928`
- `0x18000a580`
- `0x1800130ec`
- `0x180018490`
- `0x1800225a0`
- `0x18003a1ec`
- `0x1800543a4`
- `0x180054c4c`
- `0x180055580`
- `0x1800565e0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005571e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800557a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005571e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800557a6`

## string_xrefs

- `0x1800555fc`: `MessageBuilder::WriteSessionDiscoveryResponse sessionCount > 255 (%zu)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SharingPlatform::Internal::MessageBuilder::WriteSessionDiscoveryResponse(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rcx
  int v5; // eax
  unsigned __int64 v6; // rdx
  unsigned __int8 v7; // cl
  unsigned int v8; // ebx
  __int64 v9; // rdx
  unsigned __int64 v10; // rbx
  __int64 v11; // rcx
  RemoteSessionTraceProvider *v12; // rax
  __int64 (__fastcall ****i)(_QWORD, GUID *, __int64); // rbx
  int v14; // eax
  int v15; // edi
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v17)(_QWORD, GUID *, __int64); // rdi
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rdi
  HSTRING v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v24; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+28h] [rbp-48h] BYREF
  __int64 v26; // [rsp+30h] [rbp-40h] BYREF
  SharingPlatform::Internal *v27; // [rsp+38h] [rbp-38h] BYREF
  __int128 v28; // [rsp+40h] [rbp-30h] BYREF
  __int128 v29; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v27 = 0;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v27);
  LOBYTE(v4) = 1;
  v5 = SharingPlatform::Internal::MessageBuilder::CreateMessageBuilder(v4, &v27);
  v8 = v5;
  if ( v5 < 0 )
  {
    v9 = 48;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)".\\messagebuilder.cpp",
      (const char *)(unsigned int)v5,
      v24);
    goto LABEL_34;
  }
  v10 = (__int64)(a1[1] - *a1) >> 3;
  if ( v10 <= 0xFF )
  {
    LOBYTE(v6) = (__int64)(a1[1] - *a1) >> 3;
    v5 = (*(__int64 (__fastcall **)(SharingPlatform::Internal *, unsigned __int64))(*(_QWORD *)v27 + 88LL))(v27, v6);
    v8 = v5;
    if ( v5 >= 0 )
    {
      for ( i = (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))*a1;
            i != (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))a1[1];
            ++i )
      {
        v26 = 0;
        v14 = Microsoft::WRL::ComPtr<SharingPlatform::ISession>::As<SharingPlatform::ISessionInternal>(i, (__int64)&v26);
        v15 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x43,
            (unsigned int)".\\messagebuilder.cpp",
            (const char *)(unsigned int)v14,
            v24);
          goto LABEL_30;
        }
        if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v26 + 48LL))(v26) )
        {
          v24 = 0;
          v16 = *i;
          v17 = (**i)[8];
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v24);
          v15 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64 *))v17)(v16, &v24);
          if ( v15 < 0 )
          {
            v22 = 75;
            goto LABEL_27;
          }
          v15 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v24 + 48LL))(v24, &v29);
          if ( v15 < 0 )
          {
            v22 = 79;
            goto LABEL_27;
          }
          v28 = v29;
          v15 = (*(__int64 (__fastcall **)(SharingPlatform::Internal *, __int128 *))(*(_QWORD *)v27 + 128LL))(v27, &v28);
          if ( v15 < 0 )
          {
            v22 = 80;
LABEL_27:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v22,
              (unsigned int)".\\messagebuilder.cpp",
              (const char *)(unsigned int)v15,
              v24);
            goto LABEL_28;
          }
          string = 0;
          v18 = v24;
          v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 56LL);
          WindowsDeleteString(0);
          string = 0;
          v15 = v19(v18, &string);
          if ( v15 < 0 )
          {
            v21 = 84;
LABEL_23:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v21,
              (unsigned int)".\\messagebuilder.cpp",
              (const char *)(unsigned int)v15,
              v24);
            WindowsDeleteString(string);
            string = 0;
LABEL_28:
            Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v24);
LABEL_30:
            Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v26);
            v8 = v15;
            goto LABEL_34;
          }
          v15 = SharingPlatform::Internal::WriteShortStringAndLength(
                  v27,
                  (struct Windows::Storage::Streams::IDataWriter *)string,
                  v20);
          if ( v15 < 0 )
          {
            v21 = 85;
            goto LABEL_23;
          }
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v24);
        }
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v26);
      }
      v5 = (*(__int64 (__fastcall **)(SharingPlatform::Internal *, __int64))(*(_QWORD *)v27 + 248LL))(v27, a2);
      v8 = v5;
      if ( v5 >= 0 )
      {
        v8 = 0;
        goto LABEL_34;
      }
      v9 = 89;
    }
    else
    {
      v9 = 60;
    }
    goto LABEL_9;
  }
  if ( RemoteSessionTraceProvider::IsEnabled(v7, v6) )
  {
    v12 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                          v11,
                                          _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
    RemoteSessionTraceProvider::LogError_(
      v12,
      L"MessageBuilder::WriteSessionDiscoveryResponse sessionCount > 255 (%zu)",
      v10);
  }
  v8 = -2147024809;
LABEL_34:
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v27);
  return v8;
}

```

## disassembly

```asm
0x180055580  mov     [rsp-28h+arg_10], rbx
0x180055585  push    rbp
0x180055586  push    rsi
0x180055587  push    rdi
0x180055588  push    r14
0x18005558a  push    r15
0x18005558c  mov     rbp, rsp
0x18005558f  sub     rsp, 70h
0x180055593  mov     rax, cs:__security_cookie
0x18005559a  xor     rax, rsp
0x18005559d  mov     [rbp+var_10], rax
0x1800555a1  mov     r15, rdx
0x1800555a4  mov     r14, rcx
0x1800555a7  mov     [rbp+var_38], 0
0x1800555af  lea     rcx, [rbp+var_38]
0x1800555b3  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800555b8  lea     rdx, [rbp+var_38]
0x1800555bc  mov     cl, 1
0x1800555be  call    ?CreateMessageBuilder@MessageBuilder@Internal@SharingPlatform@@CAJW4MessageType@123@PEAPEAUIDataWriter@Streams@Storage@Windows@@@Z; SharingPlatform::Internal::MessageBuilder::CreateMessageBuilder(SharingPlatform::Internal::MessageBuilder::MessageType,Windows::Storage::Streams::IDataWriter * *)
0x1800555c3  mov     ebx, eax
0x1800555c5  test    eax, eax
0x1800555c7  jns     short loc_1800555D0
0x1800555c9  mov     edx, 30h ; '0'
0x1800555ce  jmp     short loc_180055632
0x1800555d0  mov     rbx, [r14+8]
0x1800555d4  sub     rbx, [r14]
0x1800555d7  sar     rbx, 3
0x1800555db  cmp     rbx, 0FFh
0x1800555e2  jbe     short loc_180055615
0x1800555e4  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x1800555e9  test    al, al
0x1800555eb  jz      short loc_18005560B
0x1800555ed  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x1800555f4  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x1800555f9  mov     r8, rbx
0x1800555fc  lea     rdx, aMessagebuilder_0; "MessageBuilder::WriteSessionDiscoveryRe"...
0x180055603  mov     rcx, rax; this
0x180055606  call    ?LogError_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogError_(ushort const *,...)
0x18005560b  mov     ebx, 80070057h
0x180055610  jmp     loc_180055836
0x180055615  mov     rcx, [rbp+var_38]
0x180055619  mov     rax, [rcx]
0x18005561c  mov     dl, bl
0x18005561e  mov     rax, [rax+58h]
0x180055622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055627  mov     ebx, eax
0x180055629  test    eax, eax
0x18005562b  jns     short loc_18005564A
0x18005562d  mov     edx, 3Ch ; '<'; void *
0x180055632  mov     rcx, [rbp+28h]; this
0x180055636  mov     r9d, eax; char *
0x180055639  lea     r8, aMessagebuilder; ".\\messagebuilder.cpp"
0x180055640  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055645  jmp     loc_180055836
0x18005564a  mov     rbx, [r14]
0x18005564d  cmp     rbx, [r14+8]
0x180055651  jz      loc_18005580E
0x180055657  mov     [rbp+var_40], 0
0x18005565f  lea     rdx, [rbp+var_40]
0x180055663  mov     rcx, rbx
0x180055666  call    ??$As@UISessionInternal@SharingPlatform@@@?$ComPtr@UISession@SharingPlatform@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISessionInternal@SharingPlatform@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<SharingPlatform::ISession>::As<SharingPlatform::ISessionInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SharingPlatform::ISessionInternal>>)
0x18005566b  mov     edi, eax
0x18005566d  test    eax, eax
0x18005566f  js      loc_1800557E8
0x180055675  mov     rcx, [rbp+var_40]
0x180055679  mov     rax, [rcx]
0x18005567c  mov     rax, [rax+30h]
0x180055680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055685  test    al, al
0x180055687  jz      loc_180055770
0x18005568d  mov     [rbp+var_50], 0
0x180055695  mov     rsi, [rbx]
0x180055698  mov     rax, [rsi]
0x18005569b  mov     rdi, [rax+40h]
0x18005569f  lea     rcx, [rbp+var_50]
0x1800556a3  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800556a8  lea     rdx, [rbp+var_50]
0x1800556ac  mov     rcx, rsi
0x1800556af  mov     rax, rdi
0x1800556b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556b7  mov     edi, eax
0x1800556b9  test    eax, eax
0x1800556bb  js      loc_1800557C4
0x1800556c1  mov     rcx, [rbp+var_50]
0x1800556c5  mov     rax, [rcx]
0x1800556c8  lea     rdx, [rbp+var_20]
0x1800556cc  mov     rax, [rax+30h]
0x1800556d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556d5  mov     edi, eax
0x1800556d7  test    eax, eax
0x1800556d9  js      loc_1800557BD
0x1800556df  mov     rcx, [rbp+var_38]
0x1800556e3  movaps  xmm0, [rbp+var_20]
0x1800556e7  movdqa  [rbp+var_30], xmm0
0x1800556ec  mov     rax, [rcx]
0x1800556ef  lea     rdx, [rbp+var_30]
0x1800556f3  mov     rax, [rax+80h]
0x1800556fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556ff  mov     edi, eax
0x180055701  test    eax, eax
0x180055703  js      loc_1800557B6
0x180055709  mov     [rbp+string], 0
0x180055711  mov     rsi, [rbp+var_50]
0x180055715  mov     rax, [rsi]
0x180055718  mov     rdi, [rax+38h]
0x18005571c  xor     ecx, ecx; string
0x18005571e  call    cs:__imp_WindowsDeleteString
0x180055724  mov     [rbp+string], 0
0x18005572c  lea     rdx, [rbp+string]
0x180055730  mov     rcx, rsi
0x180055733  mov     rax, rdi
0x180055736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005573b  mov     edi, eax
0x18005573d  test    eax, eax
0x18005573f  js      short loc_180055789
0x180055741  mov     rdx, [rbp+string]; struct Windows::Storage::Streams::IDataWriter *
0x180055745  mov     rcx, [rbp+var_38]; this
0x180055749  call    ?WriteShortStringAndLength@Internal@SharingPlatform@@YAJPEAUIDataWriter@Streams@Storage@Windows@@PEAUHSTRING__@@@Z; SharingPlatform::Internal::WriteShortStringAndLength(Windows::Storage::Streams::IDataWriter *,HSTRING__ *)
0x18005574e  mov     edi, eax
0x180055750  test    eax, eax
0x180055752  js      short loc_180055782
0x180055754  mov     rcx, [rbp+string]; string
0x180055758  call    cs:__imp_WindowsDeleteString
0x18005575e  mov     [rbp+string], 0
0x180055766  lea     rcx, [rbp+var_50]
0x18005576a  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005576f  nop
0x180055770  lea     rcx, [rbp+var_40]
0x180055774  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180055779  add     rbx, 8
0x18005577d  jmp     loc_18005564D
0x180055782  mov     edx, 55h ; 'U'
0x180055787  jmp     short loc_18005578E
0x180055789  mov     edx, 54h ; 'T'; void *
0x18005578e  lea     r8, aMessagebuilder; ".\\messagebuilder.cpp"
0x180055795  mov     r9d, edi; char *
0x180055798  mov     rcx, [rbp+28h]; this
0x18005579c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800557a1  nop
0x1800557a2  mov     rcx, [rbp+string]; string
0x1800557a6  call    cs:__imp_WindowsDeleteString
0x1800557ac  mov     [rbp+string], 0
0x1800557b4  jmp     short loc_1800557DD
0x1800557b6  mov     edx, 50h ; 'P'
0x1800557bb  jmp     short loc_1800557C9
0x1800557bd  mov     edx, 4Fh ; 'O'
0x1800557c2  jmp     short loc_1800557C9
0x1800557c4  mov     edx, 4Bh ; 'K'; void *
0x1800557c9  mov     rcx, [rbp+28h]; this
0x1800557cd  mov     r9d, edi; char *
0x1800557d0  lea     r8, aMessagebuilder; ".\\messagebuilder.cpp"
0x1800557d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800557dc  nop
0x1800557dd  lea     rcx, [rbp+var_50]
0x1800557e1  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800557e6  jmp     short loc_180055801
0x1800557e8  mov     rcx, [rbp+28h]; this
0x1800557ec  mov     r9d, edi; char *
0x1800557ef  lea     r8, aMessagebuilder; ".\\messagebuilder.cpp"
0x1800557f6  mov     edx, 43h ; 'C'; void *
0x1800557fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055800  nop
0x180055801  lea     rcx, [rbp+var_40]
0x180055805  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005580a  mov     ebx, edi
0x18005580c  jmp     short loc_180055836
0x18005580e  mov     rcx, [rbp+var_38]
0x180055812  mov     rax, [rcx]
0x180055815  mov     rdx, r15
0x180055818  mov     rax, [rax+0F8h]
0x18005581f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055824  mov     ebx, eax
0x180055826  test    eax, eax
0x180055828  jns     short loc_180055834
0x18005582a  mov     edx, 59h ; 'Y'
0x18005582f  jmp     loc_180055632
0x180055834  xor     ebx, ebx
0x180055836  lea     rcx, [rbp+var_38]
0x18005583a  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005583f  mov     eax, ebx
0x180055841  mov     rcx, [rbp+var_10]
0x180055845  xor     rcx, rsp; StackCookie
0x180055848  call    __security_check_cookie
0x18005584d  mov     rbx, [rsp+70h+arg_10]
0x180055855  add     rsp, 70h
0x180055859  pop     r15
0x18005585b  pop     r14
0x18005585d  pop     rdi
0x18005585e  pop     rsi
0x18005585f  pop     rbp
0x180055860  retn
```
