# OnDemandBrokerClient::~OnDemandBrokerClient(void)

- ea: `0x180001b70`
- end: `0x180001c18`
- name: `??1OnDemandBrokerClient@@AEAA@XZ`
- size: `168`
- prototype: `void __fastcall(OnDemandBrokerClient *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001b20`

## callees

- `0x180001840`
- `0x180001b70`
- `0x180002090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001bbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001bbc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001bc6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001bc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ba6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ba6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001bde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001bde`

## pseudocode

```c
void __fastcall OnDemandBrokerClient::~OnDemandBrokerClient(OnDemandBrokerClient *this)
{
  unsigned int v2; // edx
  _ODB_SESSION_ENTRY **v3; // rdi
  _ODB_SESSION_ENTRY *v4; // rcx
  HSTRING v5; // rcx
  _ODB_SESSION_ENTRY *v6; // rax

  *(_QWORD *)this = &OnDemandBrokerClient::`vftable'{for `IOnDemandBrokerClient'};
  *((_QWORD *)this + 1) = &OnDemandBrokerClient::`vftable'{for `IOnDemandBrokerLegacyClient'};
  *((_QWORD *)this + 2) = &OnDemandBrokerClient::`vftable'{for `IOnDemandBrokerClientPrivate'};
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v3 = (_ODB_SESSION_ENTRY **)((char *)this + 88);
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == (_ODB_SESSION_ENTRY *)v3 )
      break;
    if ( *((_ODB_SESSION_ENTRY ***)v4 + 1) != v3
      || (v6 = *(_ODB_SESSION_ENTRY **)v4, *(_ODB_SESSION_ENTRY **)(*(_QWORD *)v4 + 8LL) != v4) )
    {
      __fastfail(3u);
    }
    *v3 = v6;
    *((_QWORD *)v6 + 1) = v3;
    _ODB_SESSION_ENTRY::`scalar deleting destructor'(v4, v2);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 80);
  v5 = (HSTRING)*((_QWORD *)this + 9);
  if ( v5 )
    WindowsDeleteString(v5);
}

```

## disassembly

```asm
0x180001b70  mov     [rsp+arg_0], rbx
0x180001b75  mov     [rsp+arg_8], rsi
0x180001b7a  push    rdi
0x180001b7b  sub     rsp, 20h
0x180001b7f  lea     rax, ??_7OnDemandBrokerClient@@6BIOnDemandBrokerClient@@@; const OnDemandBrokerClient::`vftable'{for `IOnDemandBrokerClient'}
0x180001b86  mov     rbx, rcx
0x180001b89  mov     [rcx], rax
0x180001b8c  lea     rax, ??_7OnDemandBrokerClient@@6BIOnDemandBrokerLegacyClient@@@; const OnDemandBrokerClient::`vftable'{for `IOnDemandBrokerLegacyClient'}
0x180001b93  mov     [rcx+8], rax
0x180001b97  lea     rax, ??_7OnDemandBrokerClient@@6BIOnDemandBrokerClientPrivate@@@; const OnDemandBrokerClient::`vftable'{for `IOnDemandBrokerClientPrivate'}
0x180001b9e  mov     [rcx+10h], rax
0x180001ba2  add     rcx, 18h; lpCriticalSection
0x180001ba6  call    cs:__imp_EnterCriticalSection
0x180001bac  lea     rdi, [rbx+58h]
0x180001bb0  mov     rcx, [rdi]; this
0x180001bb3  cmp     rcx, rdi
0x180001bb6  jnz     short loc_180001BF4
0x180001bb8  lea     rcx, [rbx+18h]; lpCriticalSection
0x180001bbc  call    cs:__imp_LeaveCriticalSection
0x180001bc2  lea     rcx, [rbx+18h]; lpCriticalSection
0x180001bc6  call    cs:__imp_DeleteCriticalSection
0x180001bcc  lea     rcx, [rbx+50h]
0x180001bd0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180001bd5  mov     rcx, [rbx+48h]; string
0x180001bd9  test    rcx, rcx
0x180001bdc  jz      short loc_180001BE4
0x180001bde  call    cs:__imp_WindowsDeleteString
0x180001be4  mov     rbx, [rsp+28h+arg_0]
0x180001be9  mov     rsi, [rsp+28h+arg_8]
0x180001bee  add     rsp, 20h
0x180001bf2  pop     rdi
0x180001bf3  retn
0x180001bf4  cmp     [rcx+8], rdi
0x180001bf8  jnz     short loc_180001C11
0x180001bfa  mov     rax, [rcx]
0x180001bfd  cmp     [rax+8], rcx
0x180001c01  jnz     short loc_180001C11
0x180001c03  mov     [rdi], rax
0x180001c06  mov     [rax+8], rdi
0x180001c0a  call    ??_G_ODB_SESSION_ENTRY@@QEAAPEAXI@Z; _ODB_SESSION_ENTRY::`scalar deleting destructor'(uint)
0x180001c0f  jmp     short loc_180001BB0
0x180001c11  mov     ecx, 3
0x180001c16  int     29h; Win8: RtlFailFast(ecx)
```
