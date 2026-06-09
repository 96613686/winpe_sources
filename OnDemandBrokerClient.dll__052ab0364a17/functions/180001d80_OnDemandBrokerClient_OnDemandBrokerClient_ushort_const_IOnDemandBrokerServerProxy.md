# OnDemandBrokerClient::OnDemandBrokerClient(ushort const *,IOnDemandBrokerServerProxy *)

- ea: `0x180001d80`
- end: `0x180001e50`
- name: `??0OnDemandBrokerClient@@AEAA@PEBGPEAUIOnDemandBrokerServerProxy@@@Z`
- size: `208`
- prototype: `OnDemandBrokerClient *__fastcall(OnDemandBrokerClient *this, const unsigned __int16 *, struct IOnDemandBrokerServerProxy *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001c20`

## callees

- `0x180001d80`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001e2c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001e2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001e22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001e22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180001e0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180001e0b`

## pseudocode

```c
OnDemandBrokerClient *__fastcall OnDemandBrokerClient::OnDemandBrokerClient(
        OnDemandBrokerClient *this,
        const unsigned __int16 *a2,
        struct IOnDemandBrokerServerProxy *a3)
{
  unsigned __int64 v5; // rdx
  HSTRING v6; // rcx
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &OnDemandBrokerClient::`vftable'{for `IOnDemandBrokerClient'};
  *((_QWORD *)this + 1) = &OnDemandBrokerClient::`vftable'{for `IOnDemandBrokerLegacyClient'};
  *((_QWORD *)this + 2) = &OnDemandBrokerClient::`vftable'{for `IOnDemandBrokerClientPrivate'};
  *((_DWORD *)this + 16) = 1;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = a3;
  if ( a3 )
    (*(void (__fastcall **)(struct IOnDemandBrokerServerProxy *))(*(_QWORD *)a3 + 8LL))(a3);
  if ( a2 )
  {
    string = 0;
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    if ( v5 <= 0xFFFFFFFF && WindowsCreateString(a2, v5, &string) >= 0 )
    {
      v6 = (HSTRING)*((_QWORD *)this + 9);
      *((_QWORD *)this + 9) = string;
      WindowsDeleteString(v6);
    }
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *((_QWORD *)this + 12) = (char *)this + 88;
  *((_QWORD *)this + 11) = (char *)this + 88;
  return this;
}

```

## disassembly

```asm
0x180001d80  mov     [rsp+arg_8], rbx
0x180001d85  mov     [rsp+arg_10], rsi
0x180001d8a  push    rdi
0x180001d8b  sub     rsp, 20h
0x180001d8f  lea     rax, ??_7OnDemandBrokerClient@@6BIOnDemandBrokerClient@@@; const OnDemandBrokerClient::`vftable'{for `IOnDemandBrokerClient'}
0x180001d96  xor     esi, esi
0x180001d98  mov     [rcx], rax
0x180001d9b  lea     rax, ??_7OnDemandBrokerClient@@6BIOnDemandBrokerLegacyClient@@@; const OnDemandBrokerClient::`vftable'{for `IOnDemandBrokerLegacyClient'}
0x180001da2  mov     [rcx+8], rax
0x180001da6  lea     rax, ??_7OnDemandBrokerClient@@6BIOnDemandBrokerClientPrivate@@@; const OnDemandBrokerClient::`vftable'{for `IOnDemandBrokerClientPrivate'}
0x180001dad  mov     [rcx+10h], rax
0x180001db1  mov     rbx, rdx
0x180001db4  mov     dword ptr [rcx+40h], 1
0x180001dbb  mov     rdi, rcx
0x180001dbe  mov     [rcx+48h], rsi
0x180001dc2  mov     [rcx+50h], r8
0x180001dc6  test    r8, r8
0x180001dc9  jz      short loc_180001DDA
0x180001dcb  mov     rax, [r8]
0x180001dce  mov     rcx, r8
0x180001dd1  mov     rax, [rax+8]
0x180001dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dda  test    rbx, rbx
0x180001ddd  jz      short loc_180001E28
0x180001ddf  mov     [rsp+28h+string], rsi
0x180001de4  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180001deb  nop     dword ptr [rax+rax+00h]
0x180001df0  inc     rdx; length
0x180001df3  cmp     [rbx+rdx*2], si
0x180001df7  jnz     short loc_180001DF0
0x180001df9  mov     eax, 0FFFFFFFFh
0x180001dfe  cmp     rdx, rax
0x180001e01  ja      short loc_180001E28
0x180001e03  lea     r8, [rsp+28h+string]; string
0x180001e08  mov     rcx, rbx; sourceString
0x180001e0b  call    cs:__imp_WindowsCreateString
0x180001e11  test    eax, eax
0x180001e13  js      short loc_180001E28
0x180001e15  mov     rax, [rsp+28h+string]
0x180001e1a  mov     rcx, [rdi+48h]; string
0x180001e1e  mov     [rdi+48h], rax
0x180001e22  call    cs:__imp_WindowsDeleteString
0x180001e28  lea     rcx, [rdi+18h]; lpCriticalSection
0x180001e2c  call    cs:__imp_InitializeCriticalSection
0x180001e32  mov     rbx, [rsp+28h+arg_8]
0x180001e37  lea     rax, [rdi+58h]
0x180001e3b  mov     rsi, [rsp+28h+arg_10]
0x180001e40  mov     [rax+8], rax
0x180001e44  mov     [rax], rax
0x180001e47  mov     rax, rdi
0x180001e4a  add     rsp, 20h
0x180001e4e  pop     rdi
0x180001e4f  retn
```
