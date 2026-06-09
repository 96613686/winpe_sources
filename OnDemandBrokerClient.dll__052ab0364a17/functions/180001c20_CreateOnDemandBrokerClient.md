# CreateOnDemandBrokerClient

- ea: `0x180001c20`
- end: `0x180001d57`
- name: `CreateOnDemandBrokerClient`
- size: `311`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct OnDemandBrokerClient **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001840`
- `0x180001c20`
- `0x180001d60`
- `0x180001d80`
- `0x180004388`
- `0x180004d50`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c71`

## pseudocode

```c
__int64 __fastcall CreateOnDemandBrokerClient(unsigned __int16 *a1, struct OnDemandBrokerClient **a2)
{
  struct OnDemandBrokerClient *v3; // rsi
  OnDemandBrokerServerProxy *v5; // rax
  struct IOnDemandBrokerServerProxy *v6; // rbx
  int v7; // edi
  __int64 result; // rax
  OnDemandBrokerClient *v9; // rax
  struct OnDemandBrokerClient *v10; // rax
  struct IOnDemandBrokerServerProxy *v11; // [rsp+50h] [rbp+18h] BYREF

  v11 = 0;
  v3 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  v5 = (OnDemandBrokerServerProxy *)operator new(0x10u);
  if ( !v5 || (v6 = OnDemandBrokerServerProxy::OnDemandBrokerServerProxy(v5)) == 0 )
  {
    v6 = v11;
    v7 = -2147024882;
    goto LABEL_5;
  }
  EnterCriticalSection(&OnDemandBrokerClient::s_instancelock);
  if ( OnDemandBrokerClient::s_instance )
  {
    v3 = OnDemandBrokerClient::s_instance;
    LeaveCriticalSection(&OnDemandBrokerClient::s_instancelock);
    (*(void (__fastcall **)(struct OnDemandBrokerClient *))(*(_QWORD *)v3 + 8LL))(v3);
    v7 = 1;
    goto LABEL_5;
  }
  v9 = (OnDemandBrokerClient *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v9 )
  {
    v10 = OnDemandBrokerClient::OnDemandBrokerClient(v9, a1, v6);
    OnDemandBrokerClient::s_instance = v10;
    if ( v10 )
    {
      v3 = v10;
      LeaveCriticalSection(&OnDemandBrokerClient::s_instancelock);
      (*(void (__fastcall **)(struct OnDemandBrokerClient *))(*(_QWORD *)v3 + 8LL))(v3);
      v7 = 0;
      goto LABEL_5;
    }
  }
  else
  {
    OnDemandBrokerClient::s_instance = 0;
  }
  LeaveCriticalSection(&OnDemandBrokerClient::s_instancelock);
  v7 = -2147024882;
LABEL_5:
  if ( v6 )
    (*(void (__fastcall **)(struct IOnDemandBrokerServerProxy *))(*(_QWORD *)v6 + 16LL))(v6);
  result = (unsigned int)v7;
  if ( v7 >= 0 )
    *a2 = v3;
  return result;
}

```

## disassembly

```asm
0x180001c20  mov     [rsp+arg_0], rbx
0x180001c25  mov     [rsp+arg_8], rbp
0x180001c2a  push    rsi
0x180001c2b  push    rdi
0x180001c2c  push    r14
0x180001c2e  sub     rsp, 20h
0x180001c32  mov     rdi, rcx
0x180001c35  xor     ebp, ebp
0x180001c37  lea     rcx, [rsp+38h+arg_10]
0x180001c3c  mov     [rsp+38h+arg_10], rbp
0x180001c41  mov     esi, ebp
0x180001c43  mov     r14, rdx
0x180001c46  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180001c4b  mov     ecx, 10h; Size
0x180001c50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001c55  test    rax, rax
0x180001c58  jz      short loc_180001CD7
0x180001c5a  mov     rcx, rax; this
0x180001c5d  call    ??0OnDemandBrokerServerProxy@@AEAA@XZ; OnDemandBrokerServerProxy::OnDemandBrokerServerProxy(void)
0x180001c62  mov     rbx, rax
0x180001c65  test    rax, rax
0x180001c68  jz      short loc_180001CD7
0x180001c6a  lea     rcx, ?s_instancelock@OnDemandBrokerClient@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001c71  call    cs:__imp_EnterCriticalSection
0x180001c77  mov     rax, cs:?s_instance@OnDemandBrokerClient@@0PEAV1@EA; OnDemandBrokerClient * OnDemandBrokerClient::s_instance
0x180001c7e  test    rax, rax
0x180001c81  jz      short loc_180001CE3
0x180001c83  lea     rcx, ?s_instancelock@OnDemandBrokerClient@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001c8a  mov     rsi, rax
0x180001c8d  call    cs:__imp_LeaveCriticalSection
0x180001c93  mov     rax, [rsi]
0x180001c96  mov     rcx, rsi
0x180001c99  mov     rax, [rax+8]
0x180001c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ca2  mov     edi, 1
0x180001ca7  test    rbx, rbx
0x180001caa  jz      short loc_180001CBB
0x180001cac  mov     rcx, [rbx]
0x180001caf  mov     rax, [rcx+10h]
0x180001cb3  mov     rcx, rbx
0x180001cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cbb  mov     eax, edi
0x180001cbd  test    edi, edi
0x180001cbf  js      short loc_180001CC4
0x180001cc1  mov     [r14], rsi
0x180001cc4  mov     rbx, [rsp+38h+arg_0]
0x180001cc9  mov     rbp, [rsp+38h+arg_8]
0x180001cce  add     rsp, 20h
0x180001cd2  pop     r14
0x180001cd4  pop     rdi
0x180001cd5  pop     rsi
0x180001cd6  retn
0x180001cd7  mov     rbx, [rsp+38h+arg_10]
0x180001cdc  mov     edi, 8007000Eh
0x180001ce1  jmp     short loc_180001CA7
0x180001ce3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001cea  mov     ecx, 68h ; 'h'; unsigned __int64
0x180001cef  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001cf4  test    rax, rax
0x180001cf7  jz      short loc_180001D39
0x180001cf9  mov     r8, rbx; struct IOnDemandBrokerServerProxy *
0x180001cfc  mov     rdx, rdi; unsigned __int16 *
0x180001cff  mov     rcx, rax; this
0x180001d02  call    ??0OnDemandBrokerClient@@AEAA@PEBGPEAUIOnDemandBrokerServerProxy@@@Z; OnDemandBrokerClient::OnDemandBrokerClient(ushort const *,IOnDemandBrokerServerProxy *)
0x180001d07  mov     cs:?s_instance@OnDemandBrokerClient@@0PEAV1@EA, rax; OnDemandBrokerClient * OnDemandBrokerClient::s_instance
0x180001d0e  test    rax, rax
0x180001d11  jz      short loc_180001D40
0x180001d13  lea     rcx, ?s_instancelock@OnDemandBrokerClient@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001d1a  mov     rsi, rax
0x180001d1d  call    cs:__imp_LeaveCriticalSection
0x180001d23  mov     rax, [rsi]
0x180001d26  mov     rcx, rsi
0x180001d29  mov     rax, [rax+8]
0x180001d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d32  mov     edi, ebp
0x180001d34  jmp     loc_180001CA7
0x180001d39  mov     cs:?s_instance@OnDemandBrokerClient@@0PEAV1@EA, rbp; OnDemandBrokerClient * OnDemandBrokerClient::s_instance
0x180001d40  lea     rcx, ?s_instancelock@OnDemandBrokerClient@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001d47  call    cs:__imp_LeaveCriticalSection
0x180001d4d  mov     edi, 8007000Eh
0x180001d52  jmp     loc_180001CA7
```
