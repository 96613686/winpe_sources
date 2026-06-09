# Windows::Management::Provisioning::OperationServerBase::RuntimeClassInitialize(int,ushort const *)

- ea: `0x18007896c`
- end: `0x180078a5f`
- name: `?RuntimeClassInitialize@OperationServerBase@Provisioning@Management@Windows@@QEAAJHPEBG@Z`
- size: `243`
- prototype: `int(Windows::Management::Provisioning::OperationServerBase *__hidden this, int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007604c`
- `0x180078908`
- `0x180078a68`

## callees

- `0x18000a5c4`
- `0x18000b3cc`
- `0x180017078`
- `0x180036d2c`
- `0x18003a2d0`
- `0x18007896c`
- `0x180078ca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800789d4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800789d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800789e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800789e8`

## pseudocode

```c
__int64 __fastcall Windows::Management::Provisioning::OperationServerBase::RuntimeClassInitialize(
        Windows::Management::Provisioning::OperationServerBase *this,
        unsigned int a2,
        const unsigned __int16 *a3)
{
  char *v5; // rcx
  int v6; // eax
  unsigned int v7; // edi
  const char *v8; // r9
  __int64 result; // rax
  HANDLE Event; // rdi
  const char *v11; // r9
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *((_DWORD *)this + 41) = -2147418113;
  v5 = (char *)this + 112;
  try
  {
    std::wstring::operator=(v5, a3);
    v6 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::put_Id(
           (char *)this + 16,
           a2);
    v7 = v6;
    if ( v6 >= 0 )
    {
      Event = CreateEventExW(0, 0, 0, 0x1F0003u);
      if ( !Event )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1CC8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          v11);
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)this + 152,
        Event);
      v12 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start((char *)this + 16);
      v13 = v12;
      if ( v12 >= 0 )
      {
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
          (const char *)(unsigned int)v12,
          v14);
        result = v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x60,
        (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
        (const char *)(unsigned int)v6,
        v14);
      result = v7;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x66,
                           (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x18007896c  mov     [rsp+arg_8], rbx
0x180078971  mov     [rsp+arg_10], rsi
0x180078976  push    rdi; int
0x180078977  sub     rsp, 20h
0x18007897b  mov     edi, edx
0x18007897d  mov     rbx, rcx
0x180078980  mov     dword ptr [rcx+0A4h], 8000FFFFh
0x18007898a  add     rcx, 70h ; 'p'
0x18007898e  mov     rdx, r8
0x180078991  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x180078996  mov     edx, edi
0x180078998  lea     rcx, [rbx+10h]
0x18007899c  call    ?put_Id@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJI@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::put_Id(uint)
0x1800789a1  mov     edi, eax
0x1800789a3  test    eax, eax
0x1800789a5  jns     short loc_1800789C7
0x1800789a7  mov     rcx, [rsp+28h]; this
0x1800789ac  mov     r9d, eax; char *
0x1800789af  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x1800789b6  mov     edx, 60h ; '`'; void *
0x1800789bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800789c0  mov     eax, edi
0x1800789c2  jmp     loc_180078A4E
0x1800789c7  mov     r9d, 1F0003h; dwDesiredAccess
0x1800789cd  xor     r8d, r8d; dwFlags
0x1800789d0  xor     edx, edx; lpName
0x1800789d2  xor     ecx, ecx; lpEventAttributes
0x1800789d4  call    cs:__imp_CreateEventExW
0x1800789db  nop     dword ptr [rax+rax+00h]
0x1800789e0  mov     rdi, rax
0x1800789e3  test    rax, rax
0x1800789e6  jz      short loc_180078A33
0x1800789e8  call    cs:__imp_GetLastError
0x1800789ef  nop     dword ptr [rax+rax+00h]
0x1800789f4  lea     rcx, [rbx+98h]
0x1800789fb  mov     rdx, rdi
0x1800789fe  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180078a03  lea     rcx, [rbx+10h]
0x180078a07  call    ?Start@?$AsyncBase@U?$IAsyncOperationCompletedHandler@I@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<uint>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)
0x180078a0c  mov     ebx, eax
0x180078a0e  test    eax, eax
0x180078a10  jns     short loc_180078A2F
0x180078a12  mov     rcx, [rsp+28h]; this
0x180078a17  mov     r9d, eax; char *
0x180078a1a  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180078a21  mov     edx, 63h ; 'c'; void *
0x180078a26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078a2b  mov     eax, ebx
0x180078a2d  jmp     short loc_180078A4E
0x180078a2f  xor     eax, eax
0x180078a31  jmp     short loc_180078A4E
0x180078a33  mov     rcx, [rsp+28h]; this
0x180078a38  lea     r8, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; unsigned int
0x180078a3f  mov     edx, 1CC8h; void *
0x180078a44  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180078a4a  mov     eax, [rsp+28h+arg_0]
0x180078a4e  mov     rbx, [rsp+28h+arg_8]
0x180078a53  mov     rsi, [rsp+28h+arg_10]
0x180078a58  add     rsp, 20h
0x180078a5c  pop     rdi
0x180078a5d  retn
```
