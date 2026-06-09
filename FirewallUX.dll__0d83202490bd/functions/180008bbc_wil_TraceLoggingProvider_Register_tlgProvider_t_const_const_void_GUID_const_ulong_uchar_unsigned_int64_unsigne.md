# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x180008bbc`
- end: `0x180008c7a`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008820`
- `0x180012fe4`

## callees

- `0x1800021c0`
- `0x180008bbc`
- `0x18002d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180008c41`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180008c41`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008c29`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008c29`

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
0x180008bbc  mov     [rsp+arg_10], rbx
0x180008bc1  mov     [rsp+arg_18], rsi
0x180008bc6  push    rdi
0x180008bc7  sub     rsp, 40h
0x180008bcb  mov     rax, cs:__security_cookie
0x180008bd2  xor     rax, rsp
0x180008bd5  mov     [rsp+48h+var_18], rax
0x180008bda  mov     [rcx+8], rdx
0x180008bde  lea     rsi, [rdx+20h]
0x180008be2  mov     byte ptr [rcx+10h], 1
0x180008be6  mov     rdi, rdx
0x180008be9  cmp     qword ptr [rsi], 0
0x180008bed  mov     rbx, rcx
0x180008bf0  mov     rax, [rdx+8]
0x180008bf4  movups  xmm0, xmmword ptr [rax-10h]
0x180008bf8  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x180008bfe  jz      short loc_180008C07
0x180008c00  mov     ecx, 5
0x180008c05  int     29h; Win8: RtlFailFast(ecx)
0x180008c07  mov     qword ptr [rdx+28h], 0
0x180008c0f  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x180008c14  mov     qword ptr [rdx+30h], 0
0x180008c1c  mov     r9, rsi; RegHandle
0x180008c1f  lea     rdx, _tlgEnableCallback; EnableCallback
0x180008c26  mov     r8, rdi; CallbackContext
0x180008c29  call    cs:__imp_EventRegister
0x180008c2f  test    eax, eax
0x180008c31  jnz     short loc_180008C47
0x180008c33  mov     r8, [rdi+8]
0x180008c37  lea     edx, [rax+2]
0x180008c3a  mov     rcx, [rsi]
0x180008c3d  movzx   r9d, word ptr [r8]
0x180008c41  call    cs:__imp_EventSetInformation
0x180008c47  mov     rax, [rbx]
0x180008c4a  mov     rcx, rbx
0x180008c4d  mov     dword ptr [rbx+14h], 1
0x180008c54  mov     rax, [rax+8]
0x180008c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c5d  mov     rcx, [rsp+48h+var_18]
0x180008c62  xor     rcx, rsp; StackCookie
0x180008c65  call    __security_check_cookie
0x180008c6a  mov     rbx, [rsp+48h+arg_10]
0x180008c6f  mov     rsi, [rsp+48h+arg_18]
0x180008c74  add     rsp, 40h
0x180008c78  pop     rdi
0x180008c79  retn
```
