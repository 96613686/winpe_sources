# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x180009b70`
- end: `0x180009c2e`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800089ec`
- `0x18000c530`

## callees

- `0x180002170`
- `0x180009b70`
- `0x18000f010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180009bf5`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180009bf5`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180009bdd`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180009bdd`

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
0x180009b70  mov     [rsp+arg_10], rbx
0x180009b75  mov     [rsp+arg_18], rsi
0x180009b7a  push    rdi
0x180009b7b  sub     rsp, 40h
0x180009b7f  mov     rax, cs:__security_cookie
0x180009b86  xor     rax, rsp
0x180009b89  mov     [rsp+48h+var_18], rax
0x180009b8e  mov     [rcx+8], rdx
0x180009b92  lea     rsi, [rdx+20h]
0x180009b96  mov     byte ptr [rcx+10h], 1
0x180009b9a  mov     rdi, rdx
0x180009b9d  cmp     qword ptr [rsi], 0
0x180009ba1  mov     rbx, rcx
0x180009ba4  mov     rax, [rdx+8]
0x180009ba8  movups  xmm0, xmmword ptr [rax-10h]
0x180009bac  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x180009bb2  jz      short loc_180009BBB
0x180009bb4  mov     ecx, 5
0x180009bb9  int     29h; Win8: RtlFailFast(ecx)
0x180009bbb  mov     qword ptr [rdx+28h], 0
0x180009bc3  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x180009bc8  mov     qword ptr [rdx+30h], 0
0x180009bd0  mov     r9, rsi; RegHandle
0x180009bd3  lea     rdx, _tlgEnableCallback; EnableCallback
0x180009bda  mov     r8, rdi; CallbackContext
0x180009bdd  call    cs:__imp_EventRegister
0x180009be3  test    eax, eax
0x180009be5  jnz     short loc_180009BFB
0x180009be7  mov     r8, [rdi+8]
0x180009beb  lea     edx, [rax+2]
0x180009bee  mov     rcx, [rsi]
0x180009bf1  movzx   r9d, word ptr [r8]
0x180009bf5  call    cs:__imp_EventSetInformation
0x180009bfb  mov     rax, [rbx]
0x180009bfe  mov     rcx, rbx
0x180009c01  mov     dword ptr [rbx+14h], 1
0x180009c08  mov     rax, [rax+8]
0x180009c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c11  mov     rcx, [rsp+48h+var_18]
0x180009c16  xor     rcx, rsp; StackCookie
0x180009c19  call    __security_check_cookie
0x180009c1e  mov     rbx, [rsp+48h+arg_10]
0x180009c23  mov     rsi, [rsp+48h+arg_18]
0x180009c28  add     rsp, 40h
0x180009c2c  pop     rdi
0x180009c2d  retn
```
