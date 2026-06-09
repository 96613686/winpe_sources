# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x180009d5c`
- end: `0x180009e1a`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180009bf8`
- `0x18000f984`

## callees

- `0x180002470`
- `0x180009d5c`
- `0x180015010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180009de1`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180009de1`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180009dc9`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180009dc9`

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
0x180009d5c  mov     [rsp+arg_10], rbx
0x180009d61  mov     [rsp+arg_18], rsi
0x180009d66  push    rdi
0x180009d67  sub     rsp, 40h
0x180009d6b  mov     rax, cs:__security_cookie
0x180009d72  xor     rax, rsp
0x180009d75  mov     [rsp+48h+var_18], rax
0x180009d7a  mov     [rcx+8], rdx
0x180009d7e  lea     rsi, [rdx+20h]
0x180009d82  mov     byte ptr [rcx+10h], 1
0x180009d86  mov     rdi, rdx
0x180009d89  cmp     qword ptr [rsi], 0
0x180009d8d  mov     rbx, rcx
0x180009d90  mov     rax, [rdx+8]
0x180009d94  movups  xmm0, xmmword ptr [rax-10h]
0x180009d98  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x180009d9e  jz      short loc_180009DA7
0x180009da0  mov     ecx, 5
0x180009da5  int     29h; Win8: RtlFailFast(ecx)
0x180009da7  mov     qword ptr [rdx+28h], 0
0x180009daf  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x180009db4  mov     qword ptr [rdx+30h], 0
0x180009dbc  mov     r9, rsi; RegHandle
0x180009dbf  lea     rdx, _tlgEnableCallback; EnableCallback
0x180009dc6  mov     r8, rdi; CallbackContext
0x180009dc9  call    cs:__imp_EventRegister
0x180009dcf  test    eax, eax
0x180009dd1  jnz     short loc_180009DE7
0x180009dd3  mov     r8, [rdi+8]
0x180009dd7  lea     edx, [rax+2]
0x180009dda  mov     rcx, [rsi]
0x180009ddd  movzx   r9d, word ptr [r8]
0x180009de1  call    cs:__imp_EventSetInformation
0x180009de7  mov     rax, [rbx]
0x180009dea  mov     rcx, rbx
0x180009ded  mov     dword ptr [rbx+14h], 1
0x180009df4  mov     rax, [rax+8]
0x180009df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dfd  mov     rcx, [rsp+48h+var_18]
0x180009e02  xor     rcx, rsp; StackCookie
0x180009e05  call    __security_check_cookie
0x180009e0a  mov     rbx, [rsp+48h+arg_10]
0x180009e0f  mov     rsi, [rsp+48h+arg_18]
0x180009e14  add     rsp, 40h
0x180009e18  pop     rdi
0x180009e19  retn
```
