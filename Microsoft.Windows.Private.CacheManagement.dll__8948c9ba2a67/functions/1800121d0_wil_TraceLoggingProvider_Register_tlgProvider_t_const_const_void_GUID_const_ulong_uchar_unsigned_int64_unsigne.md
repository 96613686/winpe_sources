# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x1800121d0`
- end: `0x180012289`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `185`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800116f0`
- `0x180012700`

## callees

- `0x1800121d0`
- `0x1800181b0`
- `0x18001cdf0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001224f`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001224f`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180012234`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180012234`

## pseudocode

```c
void __fastcall wil::TraceLoggingProvider::Register(
        wil::TraceLoggingProvider *this,
        const struct _tlgProvider_t *const a2,
        void (*a3)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))
{
  bool v5; // zf
  __int64 v6; // rax
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  *((_QWORD *)this + 1) = a2;
  *((_BYTE *)this + 16) = 1;
  v5 = *((_QWORD *)a2 + 4) == 0;
  ProviderId = *(GUID *)(*((_QWORD *)a2 + 1) - 16LL);
  if ( !v5 )
    __fastfail(5u);
  *((_QWORD *)a2 + 5) = 0;
  *((_QWORD *)a2 + 6) = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, a2, (PREGHANDLE)a2 + 4) )
    EventSetInformation(
      *((_QWORD *)a2 + 4),
      2,
      *((_QWORD *)a2 + 1),
      **((unsigned __int16 **)a2 + 1),
      *(_QWORD *)&ProviderId.Data1,
      *(_QWORD *)ProviderId.Data4);
  v6 = *(_QWORD *)this;
  *((_DWORD *)this + 5) = 1;
  (*(void (__fastcall **)(wil::TraceLoggingProvider *))(v6 + 8))(this);
}

```

## disassembly

```asm
0x1800121d0  mov     [rsp+arg_10], rbx
0x1800121d5  mov     [rsp+arg_18], rsi
0x1800121da  push    rdi
0x1800121db  sub     rsp, 40h
0x1800121df  mov     rax, cs:__security_cookie
0x1800121e6  xor     rax, rsp
0x1800121e9  mov     [rsp+48h+var_18], rax
0x1800121ee  mov     [rcx+8], rdx
0x1800121f2  mov     rdi, rdx
0x1800121f5  mov     byte ptr [rcx+10h], 1
0x1800121f9  mov     rbx, rcx
0x1800121fc  cmp     qword ptr [rdx+20h], 0
0x180012201  mov     rax, [rdx+8]
0x180012205  movups  xmm0, xmmword ptr [rax-10h]
0x180012209  movups  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x18001220e  jz      short loc_180012217
0x180012210  mov     ecx, 5
0x180012215  int     29h; Win8: RtlFailFast(ecx)
0x180012217  xor     eax, eax
0x180012219  lea     r9, [rdx+20h]; RegHandle
0x18001221d  mov     [rdx+28h], rax
0x180012221  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x180012226  mov     [rdx+30h], rax
0x18001222a  mov     r8, rdi; CallbackContext
0x18001222d  lea     rdx, _tlgEnableCallback; EnableCallback
0x180012234  call    cs:__imp_EventRegister
0x18001223a  test    eax, eax
0x18001223c  jnz     short loc_180012255
0x18001223e  mov     r8, [rdi+8]
0x180012242  mov     edx, 2
0x180012247  mov     rcx, [rdi+20h]
0x18001224b  movzx   r9d, word ptr [r8]
0x18001224f  call    cs:__imp_EventSetInformation
0x180012255  mov     rax, [rbx]
0x180012258  mov     rcx, rbx
0x18001225b  mov     dword ptr [rbx+14h], 1
0x180012262  mov     rax, [rax+8]
0x180012266  call    cs:__guard_dispatch_icall_fptr
0x18001226c  mov     rcx, [rsp+48h+var_18]
0x180012271  xor     rcx, rsp; StackCookie
0x180012274  call    __security_check_cookie
0x180012279  mov     rbx, [rsp+48h+arg_10]
0x18001227e  mov     rsi, [rsp+48h+arg_18]
0x180012283  add     rsp, 40h
0x180012287  pop     rdi
0x180012288  retn
```
