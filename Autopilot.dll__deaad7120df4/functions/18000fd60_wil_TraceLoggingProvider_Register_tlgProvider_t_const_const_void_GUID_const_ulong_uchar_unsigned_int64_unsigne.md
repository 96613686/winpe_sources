# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x18000fd60`
- end: `0x18000fe2b`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `203`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e928`
- `0x18001670c`
- `0x18002151c`

## callees

- `0x1800045d0`
- `0x18000fd60`
- `0x18002f010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000fdcd`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000fdcd`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000fdeb`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000fdeb`

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
0x18000fd60  mov     [rsp+arg_10], rbx
0x18000fd65  mov     [rsp+arg_18], rsi
0x18000fd6a  push    rdi
0x18000fd6b  sub     rsp, 40h
0x18000fd6f  mov     rax, cs:__security_cookie
0x18000fd76  xor     rax, rsp
0x18000fd79  mov     [rsp+48h+var_18], rax
0x18000fd7e  mov     [rcx+8], rdx
0x18000fd82  lea     rsi, [rdx+20h]
0x18000fd86  mov     byte ptr [rcx+10h], 1
0x18000fd8a  mov     rdi, rdx
0x18000fd8d  cmp     qword ptr [rsi], 0
0x18000fd91  mov     rbx, rcx
0x18000fd94  mov     rax, [rdx+8]
0x18000fd98  movups  xmm0, xmmword ptr [rax-10h]
0x18000fd9c  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x18000fda2  jz      short loc_18000FDAB
0x18000fda4  mov     ecx, 5
0x18000fda9  int     29h; Win8: RtlFailFast(ecx)
0x18000fdab  mov     qword ptr [rdx+28h], 0
0x18000fdb3  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x18000fdb8  mov     qword ptr [rdx+30h], 0
0x18000fdc0  mov     r9, rsi; RegHandle
0x18000fdc3  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000fdca  mov     r8, rdi; CallbackContext
0x18000fdcd  call    cs:__imp_EventRegister
0x18000fdd4  nop     dword ptr [rax+rax+00h]
0x18000fdd9  test    eax, eax
0x18000fddb  jnz     short loc_18000FDF7
0x18000fddd  mov     r8, [rdi+8]
0x18000fde1  lea     edx, [rax+2]
0x18000fde4  mov     rcx, [rsi]
0x18000fde7  movzx   r9d, word ptr [r8]
0x18000fdeb  call    cs:__imp_EventSetInformation
0x18000fdf2  nop     dword ptr [rax+rax+00h]
0x18000fdf7  mov     rax, [rbx]
0x18000fdfa  mov     rcx, rbx
0x18000fdfd  mov     dword ptr [rbx+14h], 1
0x18000fe04  mov     rax, [rax+8]
0x18000fe08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe0d  mov     rcx, [rsp+48h+var_18]
0x18000fe12  xor     rcx, rsp; StackCookie
0x18000fe15  call    __security_check_cookie
0x18000fe1a  mov     rbx, [rsp+48h+arg_10]
0x18000fe1f  mov     rsi, [rsp+48h+arg_18]
0x18000fe24  add     rsp, 40h
0x18000fe28  pop     rdi
0x18000fe29  retn
```
