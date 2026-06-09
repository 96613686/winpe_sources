# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x18000fca8`
- end: `0x18000fd66`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e7fc`
- `0x180016284`
- `0x180020b14`

## callees

- `0x1800045b0`
- `0x18000fca8`
- `0x18002e010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000fd15`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000fd15`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000fd2d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000fd2d`

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
0x18000fca8  mov     [rsp+arg_10], rbx
0x18000fcad  mov     [rsp+arg_18], rsi
0x18000fcb2  push    rdi
0x18000fcb3  sub     rsp, 40h
0x18000fcb7  mov     rax, cs:__security_cookie
0x18000fcbe  xor     rax, rsp
0x18000fcc1  mov     [rsp+48h+var_18], rax
0x18000fcc6  mov     [rcx+8], rdx
0x18000fcca  lea     rsi, [rdx+20h]
0x18000fcce  mov     byte ptr [rcx+10h], 1
0x18000fcd2  mov     rdi, rdx
0x18000fcd5  cmp     qword ptr [rsi], 0
0x18000fcd9  mov     rbx, rcx
0x18000fcdc  mov     rax, [rdx+8]
0x18000fce0  movups  xmm0, xmmword ptr [rax-10h]
0x18000fce4  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x18000fcea  jz      short loc_18000FCF3
0x18000fcec  mov     ecx, 5
0x18000fcf1  int     29h; Win8: RtlFailFast(ecx)
0x18000fcf3  mov     qword ptr [rdx+28h], 0
0x18000fcfb  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x18000fd00  mov     qword ptr [rdx+30h], 0
0x18000fd08  mov     r9, rsi; RegHandle
0x18000fd0b  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000fd12  mov     r8, rdi; CallbackContext
0x18000fd15  call    cs:__imp_EventRegister
0x18000fd1b  test    eax, eax
0x18000fd1d  jnz     short loc_18000FD33
0x18000fd1f  mov     r8, [rdi+8]
0x18000fd23  lea     edx, [rax+2]
0x18000fd26  mov     rcx, [rsi]
0x18000fd29  movzx   r9d, word ptr [r8]
0x18000fd2d  call    cs:__imp_EventSetInformation
0x18000fd33  mov     rax, [rbx]
0x18000fd36  mov     rcx, rbx
0x18000fd39  mov     dword ptr [rbx+14h], 1
0x18000fd40  mov     rax, [rax+8]
0x18000fd44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd49  mov     rcx, [rsp+48h+var_18]
0x18000fd4e  xor     rcx, rsp; StackCookie
0x18000fd51  call    __security_check_cookie
0x18000fd56  mov     rbx, [rsp+48h+arg_10]
0x18000fd5b  mov     rsi, [rsp+48h+arg_18]
0x18000fd60  add     rsp, 40h
0x18000fd64  pop     rdi
0x18000fd65  retn
```
