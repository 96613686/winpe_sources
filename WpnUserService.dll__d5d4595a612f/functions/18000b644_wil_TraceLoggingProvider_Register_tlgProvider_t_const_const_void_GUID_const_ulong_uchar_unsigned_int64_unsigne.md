# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x18000b644`
- end: `0x18000b702`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180009a7c`
- `0x18000a648`

## callees

- `0x180002bc0`
- `0x18000b644`
- `0x180012010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000b6b1`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000b6b1`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000b6c9`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000b6c9`

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
0x18000b644  mov     [rsp+arg_10], rbx
0x18000b649  mov     [rsp+arg_18], rsi
0x18000b64e  push    rdi
0x18000b64f  sub     rsp, 40h
0x18000b653  mov     rax, cs:__security_cookie
0x18000b65a  xor     rax, rsp
0x18000b65d  mov     [rsp+48h+var_18], rax
0x18000b662  mov     [rcx+8], rdx
0x18000b666  lea     rsi, [rdx+20h]
0x18000b66a  mov     byte ptr [rcx+10h], 1
0x18000b66e  mov     rdi, rdx
0x18000b671  cmp     qword ptr [rsi], 0
0x18000b675  mov     rbx, rcx
0x18000b678  mov     rax, [rdx+8]
0x18000b67c  movups  xmm0, xmmword ptr [rax-10h]
0x18000b680  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x18000b686  jz      short loc_18000B68F
0x18000b688  mov     ecx, 5
0x18000b68d  int     29h; Win8: RtlFailFast(ecx)
0x18000b68f  mov     qword ptr [rdx+28h], 0
0x18000b697  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x18000b69c  mov     qword ptr [rdx+30h], 0
0x18000b6a4  mov     r9, rsi; RegHandle
0x18000b6a7  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000b6ae  mov     r8, rdi; CallbackContext
0x18000b6b1  call    cs:__imp_EventRegister
0x18000b6b7  test    eax, eax
0x18000b6b9  jnz     short loc_18000B6CF
0x18000b6bb  mov     r8, [rdi+8]
0x18000b6bf  lea     edx, [rax+2]
0x18000b6c2  mov     rcx, [rsi]
0x18000b6c5  movzx   r9d, word ptr [r8]
0x18000b6c9  call    cs:__imp_EventSetInformation
0x18000b6cf  mov     rax, [rbx]
0x18000b6d2  mov     rcx, rbx
0x18000b6d5  mov     dword ptr [rbx+14h], 1
0x18000b6dc  mov     rax, [rax+8]
0x18000b6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6e5  mov     rcx, [rsp+48h+var_18]
0x18000b6ea  xor     rcx, rsp; StackCookie
0x18000b6ed  call    __security_check_cookie
0x18000b6f2  mov     rbx, [rsp+48h+arg_10]
0x18000b6f7  mov     rsi, [rsp+48h+arg_18]
0x18000b6fc  add     rsp, 40h
0x18000b700  pop     rdi
0x18000b701  retn
```
