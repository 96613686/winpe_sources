# BeginServiceInitialization(void)

- ea: `0x18003999c`
- end: `0x180039b40`
- name: `?BeginServiceInitialization@@YAKXZ`
- size: `420`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003ad70`

## callees

- `0x1800134a0`
- `0x180018194`
- `0x180019168`
- `0x180019c94`
- `0x18003999c`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039a59`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039a59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a86`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800399f8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180039b21`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800399f8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180039b21`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x180039a20`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x180039a20`

## pseudocode

```c
__int64 __fastcall BeginServiceInitialization(__int64 a1, unsigned int a2)
{
  signed int LastError; // ebx
  __int16 *v3; // rdx
  char *v5; // rbx
  char *v6; // rbx
  HANDLE EventW; // rdi
  __int64 (__fastcall *v8)(char *, const WCHAR *, __int64, void (__fastcall *)(void *, unsigned __int8), _QWORD, int); // rdi
  __int64 v9; // rbx
  struct ServiceContext *v10; // rax
  char v11; // [rsp+50h] [rbp+10h] BYREF
  signed int v12; // [rsp+58h] [rbp+18h] BYREF

  v11 = 0;
  LastError = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)&v11, a2);
  if ( LastError < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
    {
LABEL_5:
      if ( v11 )
        CoUninitialize();
      return (unsigned int)LastError;
    }
    v3 = (__int16 *)qword_1800A95C0;
LABEL_4:
    v12 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BE0B8,
      (_DWORD)v3,
      0,
      0,
      (__int64)&v12);
    goto LABEL_5;
  }
  v5 = (char *)ServiceContext::Instance() + 16;
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(v5);
  LastError = CoIncrementMTAUsage(v5 + 8);
  if ( LastError < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_5;
    v3 = (__int16 *)qword_1800A9598;
    goto LABEL_4;
  }
  v6 = (char *)ServiceContext::Instance() + 32;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW != *((HANDLE *)v6 + 1) )
  {
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(v6);
    *((_QWORD *)v6 + 1) = EventW;
  }
  if ( !*((_QWORD *)ServiceContext::Instance() + 5) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_5;
    v3 = word_1800A956A;
    goto LABEL_4;
  }
  v8 = *(__int64 (__fastcall **)(char *, const WCHAR *, __int64, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))(*(_QWORD *)ServiceContext::Instance() + 192LL);
  v9 = *((_QWORD *)ServiceContext::Instance() + 5);
  v10 = ServiceContext::Instance();
  LastError = v8((char *)v10 + 48, L"NgcCtnrSvc", v9, ServiceStopCallback, 0, 24);
  if ( LastError )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_5;
    v3 = &word_1800A953E;
    goto LABEL_4;
  }
  if ( v11 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18003999c  mov     [rsp-8+arg_10], rbx
0x1800399a1  mov     [rsp-8+arg_18], rdi
0x1800399a6  push    rbp
0x1800399a7  mov     rbp, rsp
0x1800399aa  sub     rsp, 40h
0x1800399ae  mov     [rbp+arg_0], 0
0x1800399b2  lea     rcx, [rbp+arg_0]; this
0x1800399b6  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x1800399bb  mov     ebx, eax
0x1800399bd  test    eax, eax
0x1800399bf  jns     short loc_180039A0B
0x1800399c1  mov     ecx, cs:dword_1800BE0B8
0x1800399c7  cmp     ecx, 2
0x1800399ca  jbe     short loc_1800399F2
0x1800399cc  lea     rdx, qword_1800A95C0
0x1800399d3  xor     r9d, r9d
0x1800399d6  lea     rax, [rbp+arg_8]
0x1800399da  xor     r8d, r8d
0x1800399dd  mov     [rsp+40h+var_20], rax
0x1800399e2  mov     [rbp+arg_8], ebx
0x1800399e5  lea     rcx, dword_1800BE0B8
0x1800399ec  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800399f1  nop
0x1800399f2  cmp     [rbp+arg_0], 0
0x1800399f6  jz      short loc_180039A04
0x1800399f8  call    cs:__imp_CoUninitialize
0x1800399ff  nop     dword ptr [rax+rax+00h]
0x180039a04  mov     eax, ebx
0x180039a06  jmp     loc_180039B2F
0x180039a0b  call    ?Instance@ServiceContext@@SAAEAU1@XZ; ServiceContext::Instance(void)
0x180039a10  lea     rbx, [rax+10h]
0x180039a14  mov     rcx, rbx
0x180039a17  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180039a1c  lea     rcx, [rbx+8]
0x180039a20  call    cs:__imp_CoIncrementMTAUsage
0x180039a27  nop     dword ptr [rax+rax+00h]
0x180039a2c  mov     ebx, eax
0x180039a2e  test    eax, eax
0x180039a30  jns     short loc_180039A46
0x180039a32  mov     ecx, cs:dword_1800BE0B8
0x180039a38  cmp     ecx, 2
0x180039a3b  jbe     short loc_1800399F2
0x180039a3d  lea     rdx, qword_1800A9598
0x180039a44  jmp     short loc_1800399D3
0x180039a46  call    ?Instance@ServiceContext@@SAAEAU1@XZ; ServiceContext::Instance(void)
0x180039a4b  lea     rbx, [rax+20h]
0x180039a4f  xor     r9d, r9d; lpName
0x180039a52  xor     r8d, r8d; bInitialState
0x180039a55  xor     edx, edx; bManualReset
0x180039a57  xor     ecx, ecx; lpEventAttributes
0x180039a59  call    cs:__imp_CreateEventW
0x180039a60  nop     dword ptr [rax+rax+00h]
0x180039a65  mov     rdi, rax
0x180039a68  cmp     rax, [rbx+8]
0x180039a6c  jz      short loc_180039A7A
0x180039a6e  mov     rcx, rbx
0x180039a71  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180039a76  mov     [rbx+8], rdi
0x180039a7a  call    ?Instance@ServiceContext@@SAAEAU1@XZ; ServiceContext::Instance(void)
0x180039a7f  cmp     qword ptr [rax+28h], 0
0x180039a84  jnz     short loc_180039AAF
0x180039a86  call    cs:__imp_GetLastError
0x180039a8d  nop     dword ptr [rax+rax+00h]
0x180039a92  mov     ebx, eax
0x180039a94  mov     ecx, cs:dword_1800BE0B8
0x180039a9a  cmp     ecx, 2
0x180039a9d  jbe     loc_1800399F2
0x180039aa3  lea     rdx, word_1800A956A
0x180039aaa  jmp     loc_1800399D3
0x180039aaf  call    ?Instance@ServiceContext@@SAAEAU1@XZ; ServiceContext::Instance(void)
0x180039ab4  mov     rcx, [rax]
0x180039ab7  mov     rdi, [rcx+0C0h]
0x180039abe  call    ?Instance@ServiceContext@@SAAEAU1@XZ; ServiceContext::Instance(void)
0x180039ac3  mov     rbx, [rax+28h]
0x180039ac7  call    ?Instance@ServiceContext@@SAAEAU1@XZ; ServiceContext::Instance(void)
0x180039acc  lea     rcx, [rax+30h]
0x180039ad0  mov     [rsp+40h+var_18], 18h
0x180039ad8  mov     [rsp+40h+var_20], 0
0x180039ae1  lea     r9, ?ServiceStopCallback@@YAXPEAXE@Z; ServiceStopCallback(void *,uchar)
0x180039ae8  mov     r8, rbx
0x180039aeb  lea     rdx, ServiceName; "NgcCtnrSvc"
0x180039af2  mov     rax, rdi
0x180039af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039afa  mov     ebx, eax
0x180039afc  test    eax, eax
0x180039afe  jz      short loc_180039B1B
0x180039b00  mov     ecx, cs:dword_1800BE0B8
0x180039b06  cmp     ecx, 2
0x180039b09  jbe     loc_1800399F2
0x180039b0f  lea     rdx, word_1800A953E
0x180039b16  jmp     loc_1800399D3
0x180039b1b  cmp     [rbp+arg_0], 0
0x180039b1f  jz      short loc_180039B2D
0x180039b21  call    cs:__imp_CoUninitialize
0x180039b28  nop     dword ptr [rax+rax+00h]
0x180039b2d  xor     eax, eax
0x180039b2f  mov     rbx, [rsp+40h+arg_10]
0x180039b34  mov     rdi, [rsp+40h+arg_18]
0x180039b39  add     rsp, 40h
0x180039b3d  pop     rbp
0x180039b3e  retn
```
