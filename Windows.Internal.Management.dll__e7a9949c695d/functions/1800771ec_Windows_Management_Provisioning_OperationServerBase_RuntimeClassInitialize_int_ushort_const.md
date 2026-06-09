# Windows::Management::Provisioning::OperationServerBase::RuntimeClassInitialize(int,ushort const *)

- ea: `0x1800771ec`
- end: `0x1800772d0`
- name: `?RuntimeClassInitialize@OperationServerBase@Provisioning@Management@Windows@@QEAAJHPEBG@Z`
- size: `228`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::OperationServerBase *this, unsigned int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180074994`
- `0x180077188`
- `0x1800772d8`

## callees

- `0x18000a2a4`
- `0x18000b014`
- `0x180016918`
- `0x180037a84`
- `0x18003af50`
- `0x1800771ec`
- `0x180077510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180077251`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180077251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007725f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007725f`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Management::Provisioning::OperationServerBase::RuntimeClassInitialize(
        Windows::Management::Provisioning::OperationServerBase *this,
        unsigned int a2,
        const unsigned __int16 *a3)
{
  int v5; // eax
  unsigned int v6; // edi
  const char *v7; // r9
  __int64 result; // rax
  HANDLE Event; // rdi
  const char *v10; // r9
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *((_DWORD *)this + 41) = -2147418113;
  try
  {
    std::wstring::operator=();
    v5 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::put_Id(
           (char *)this + 16,
           a2);
    v6 = v5;
    if ( v5 >= 0 )
    {
      Event = CreateEventExW(0, 0, 0, 0x1F0003u);
      if ( !Event )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1CC8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          v10);
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)this + 152,
        Event);
      v11 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start((char *)this + 16);
      v12 = v11;
      if ( v11 >= 0 )
      {
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
          (const char *)(unsigned int)v11,
          v13);
        result = v12;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x60,
        (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
        (const char *)(unsigned int)v5,
        v13);
      result = v6;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x66,
                           (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800771ec  mov     [rsp+arg_8], rbx
0x1800771f1  mov     [rsp+arg_10], rsi
0x1800771f6  push    rdi; int
0x1800771f7  sub     rsp, 20h
0x1800771fb  mov     edi, edx
0x1800771fd  mov     rbx, rcx
0x180077200  mov     dword ptr [rcx+0A4h], 8000FFFFh
0x18007720a  add     rcx, 70h ; 'p'
0x18007720e  mov     rdx, r8
0x180077211  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x180077216  mov     edx, edi
0x180077218  lea     rcx, [rbx+10h]
0x18007721c  call    ?put_Id@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJI@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::put_Id(uint)
0x180077221  mov     edi, eax
0x180077223  test    eax, eax
0x180077225  jns     short loc_180077244
0x180077227  mov     rcx, [rsp+28h]; this
0x18007722c  mov     r9d, eax; char *
0x18007722f  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180077236  mov     edx, 60h ; '`'; void *
0x18007723b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077240  mov     eax, edi
0x180077242  jmp     short loc_1800772BF
0x180077244  mov     r9d, 1F0003h; dwDesiredAccess
0x18007724a  xor     r8d, r8d; dwFlags
0x18007724d  xor     edx, edx; lpName
0x18007724f  xor     ecx, ecx; lpEventAttributes
0x180077251  call    cs:__imp_CreateEventExW
0x180077257  mov     rdi, rax
0x18007725a  test    rax, rax
0x18007725d  jz      short loc_1800772A4
0x18007725f  call    cs:__imp_GetLastError
0x180077265  lea     rcx, [rbx+98h]
0x18007726c  mov     rdx, rdi
0x18007726f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180077274  lea     rcx, [rbx+10h]
0x180077278  call    ?Start@?$AsyncBase@U?$IAsyncOperationCompletedHandler@I@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<uint>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)
0x18007727d  mov     ebx, eax
0x18007727f  test    eax, eax
0x180077281  jns     short loc_1800772A0
0x180077283  mov     rcx, [rsp+28h]; this
0x180077288  mov     r9d, eax; char *
0x18007728b  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180077292  mov     edx, 63h ; 'c'; void *
0x180077297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007729c  mov     eax, ebx
0x18007729e  jmp     short loc_1800772BF
0x1800772a0  xor     eax, eax
0x1800772a2  jmp     short loc_1800772BF
0x1800772a4  mov     rcx, [rsp+28h]; this
0x1800772a9  lea     r8, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; unsigned int
0x1800772b0  mov     edx, 1CC8h; void *
0x1800772b5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800772bb  mov     eax, [rsp+28h+arg_0]
0x1800772bf  mov     rbx, [rsp+28h+arg_8]
0x1800772c4  mov     rsi, [rsp+28h+arg_10]
0x1800772c9  add     rsp, 20h
0x1800772cd  pop     rdi
0x1800772ce  retn
```
