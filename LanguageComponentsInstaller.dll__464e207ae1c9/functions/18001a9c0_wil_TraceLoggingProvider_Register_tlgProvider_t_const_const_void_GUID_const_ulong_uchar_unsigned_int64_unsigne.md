# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x18001a9c0`
- end: `0x18001aa7e`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001860c`
- `0x1800195c0`

## callees

- `0x180003520`
- `0x18001a9c0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001aa45`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001aa45`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001aa2d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001aa2d`

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
0x18001a9c0  mov     [rsp+arg_10], rbx
0x18001a9c5  mov     [rsp+arg_18], rsi
0x18001a9ca  push    rdi
0x18001a9cb  sub     rsp, 40h
0x18001a9cf  mov     rax, cs:__security_cookie
0x18001a9d6  xor     rax, rsp
0x18001a9d9  mov     [rsp+48h+var_18], rax
0x18001a9de  mov     [rcx+8], rdx
0x18001a9e2  lea     rsi, [rdx+20h]
0x18001a9e6  mov     byte ptr [rcx+10h], 1
0x18001a9ea  mov     rdi, rdx
0x18001a9ed  cmp     qword ptr [rsi], 0
0x18001a9f1  mov     rbx, rcx
0x18001a9f4  mov     rax, [rdx+8]
0x18001a9f8  movups  xmm0, xmmword ptr [rax-10h]
0x18001a9fc  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x18001aa02  jz      short loc_18001AA0B
0x18001aa04  mov     ecx, 5
0x18001aa09  int     29h; Win8: RtlFailFast(ecx)
0x18001aa0b  mov     qword ptr [rdx+28h], 0
0x18001aa13  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x18001aa18  mov     qword ptr [rdx+30h], 0
0x18001aa20  mov     r9, rsi; RegHandle
0x18001aa23  lea     rdx, _tlgEnableCallback; EnableCallback
0x18001aa2a  mov     r8, rdi; CallbackContext
0x18001aa2d  call    cs:__imp_EventRegister
0x18001aa33  test    eax, eax
0x18001aa35  jnz     short loc_18001AA4B
0x18001aa37  mov     r8, [rdi+8]
0x18001aa3b  lea     edx, [rax+2]
0x18001aa3e  mov     rcx, [rsi]
0x18001aa41  movzx   r9d, word ptr [r8]
0x18001aa45  call    cs:__imp_EventSetInformation
0x18001aa4b  mov     rax, [rbx]
0x18001aa4e  mov     rcx, rbx
0x18001aa51  mov     dword ptr [rbx+14h], 1
0x18001aa58  mov     rax, [rax+8]
0x18001aa5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa61  mov     rcx, [rsp+48h+var_18]
0x18001aa66  xor     rcx, rsp; StackCookie
0x18001aa69  call    __security_check_cookie
0x18001aa6e  mov     rbx, [rsp+48h+arg_10]
0x18001aa73  mov     rsi, [rsp+48h+arg_18]
0x18001aa78  add     rsp, 40h
0x18001aa7c  pop     rdi
0x18001aa7d  retn
```
