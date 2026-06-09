# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x18002d360`
- end: `0x18002d41e`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002b19c`
- `0x18002befc`

## callees

- `0x18002d360`
- `0x1800350e0`
- `0x180037010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18002d3cd`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18002d3cd`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18002d3e5`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18002d3e5`

## pseudocode

```c
void __fastcall wil::TraceLoggingProvider::Register(
        wil::TraceLoggingProvider *this,
        const struct _tlgProvider_t *const a2,
        void (*a3)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))
{
  _QWORD *v3; // rsi
  bool v5; // zf
  __int64 v7; // rax
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  *((_QWORD *)this + 1) = a2;
  v3 = (_QWORD *)((char *)a2 + 32);
  *((_BYTE *)this + 16) = 1;
  v5 = *((_QWORD *)a2 + 4) == 0;
  ProviderId = *(GUID *)(*((_QWORD *)a2 + 1) - 16LL);
  if ( !v5 )
    __fastfail(5u);
  *((_QWORD *)a2 + 5) = 0;
  *((_QWORD *)a2 + 6) = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, a2, (PREGHANDLE)a2 + 4) )
    EventSetInformation(
      *v3,
      2,
      *((_QWORD *)a2 + 1),
      **((unsigned __int16 **)a2 + 1),
      *(_QWORD *)&ProviderId.Data1,
      *(_QWORD *)ProviderId.Data4);
  v7 = *(_QWORD *)this;
  *((_DWORD *)this + 5) = 1;
  (*(void (__fastcall **)(wil::TraceLoggingProvider *))(v7 + 8))(this);
}

```

## disassembly

```asm
0x18002d360  mov     [rsp+arg_10], rbx
0x18002d365  mov     [rsp+arg_18], rsi
0x18002d36a  push    rdi
0x18002d36b  sub     rsp, 40h
0x18002d36f  mov     rax, cs:__security_cookie
0x18002d376  xor     rax, rsp
0x18002d379  mov     [rsp+48h+var_18], rax
0x18002d37e  mov     [rcx+8], rdx
0x18002d382  lea     rsi, [rdx+20h]
0x18002d386  mov     byte ptr [rcx+10h], 1
0x18002d38a  mov     rdi, rdx
0x18002d38d  cmp     qword ptr [rsi], 0
0x18002d391  mov     rbx, rcx
0x18002d394  mov     rax, [rdx+8]
0x18002d398  movups  xmm0, xmmword ptr [rax-10h]
0x18002d39c  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x18002d3a2  jz      short loc_18002D3AB
0x18002d3a4  mov     ecx, 5
0x18002d3a9  int     29h; Win8: RtlFailFast(ecx)
0x18002d3ab  mov     qword ptr [rdx+28h], 0
0x18002d3b3  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x18002d3b8  mov     qword ptr [rdx+30h], 0
0x18002d3c0  mov     r9, rsi; RegHandle
0x18002d3c3  lea     rdx, _tlgEnableCallback; EnableCallback
0x18002d3ca  mov     r8, rdi; CallbackContext
0x18002d3cd  call    cs:__imp_EventRegister
0x18002d3d3  test    eax, eax
0x18002d3d5  jnz     short loc_18002D3EB
0x18002d3d7  mov     r8, [rdi+8]
0x18002d3db  lea     edx, [rax+2]
0x18002d3de  mov     rcx, [rsi]
0x18002d3e1  movzx   r9d, word ptr [r8]
0x18002d3e5  call    cs:__imp_EventSetInformation
0x18002d3eb  mov     rax, [rbx]
0x18002d3ee  mov     rcx, rbx
0x18002d3f1  mov     dword ptr [rbx+14h], 1
0x18002d3f8  mov     rax, [rax+8]
0x18002d3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d401  mov     rcx, [rsp+48h+var_18]
0x18002d406  xor     rcx, rsp; StackCookie
0x18002d409  call    __security_check_cookie
0x18002d40e  mov     rbx, [rsp+48h+arg_10]
0x18002d413  mov     rsi, [rsp+48h+arg_18]
0x18002d418  add     rsp, 40h
0x18002d41c  pop     rdi
0x18002d41d  retn
```
