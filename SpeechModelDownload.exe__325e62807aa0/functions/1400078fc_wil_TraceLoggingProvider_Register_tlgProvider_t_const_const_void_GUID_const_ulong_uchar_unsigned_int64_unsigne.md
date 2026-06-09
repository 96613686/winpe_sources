# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x1400078fc`
- end: `0x1400079ba`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140005bfc`
- `0x1400077b0`
- `0x140018914`
- `0x1400189d4`

## callees

- `0x140002600`
- `0x1400078fc`
- `0x14001d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x140007981`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x140007981`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140007969`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140007969`

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
0x1400078fc  mov     [rsp+arg_10], rbx
0x140007901  mov     [rsp+arg_18], rsi
0x140007906  push    rdi
0x140007907  sub     rsp, 40h
0x14000790b  mov     rax, cs:__security_cookie
0x140007912  xor     rax, rsp
0x140007915  mov     [rsp+48h+var_18], rax
0x14000791a  mov     [rcx+8], rdx
0x14000791e  lea     rsi, [rdx+20h]
0x140007922  mov     byte ptr [rcx+10h], 1
0x140007926  mov     rdi, rdx
0x140007929  cmp     qword ptr [rsi], 0
0x14000792d  mov     rbx, rcx
0x140007930  mov     rax, [rdx+8]
0x140007934  movups  xmm0, xmmword ptr [rax-10h]
0x140007938  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x14000793e  jz      short loc_140007947
0x140007940  mov     ecx, 5
0x140007945  int     29h; Win8: RtlFailFast(ecx)
0x140007947  mov     qword ptr [rdx+28h], 0
0x14000794f  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x140007954  mov     qword ptr [rdx+30h], 0
0x14000795c  mov     r9, rsi; RegHandle
0x14000795f  lea     rdx, _tlgEnableCallback; EnableCallback
0x140007966  mov     r8, rdi; CallbackContext
0x140007969  call    cs:__imp_EventRegister
0x14000796f  test    eax, eax
0x140007971  jnz     short loc_140007987
0x140007973  mov     r8, [rdi+8]
0x140007977  lea     edx, [rax+2]
0x14000797a  mov     rcx, [rsi]
0x14000797d  movzx   r9d, word ptr [r8]
0x140007981  call    cs:__imp_EventSetInformation
0x140007987  mov     rax, [rbx]
0x14000798a  mov     rcx, rbx
0x14000798d  mov     dword ptr [rbx+14h], 1
0x140007994  mov     rax, [rax+8]
0x140007998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000799d  mov     rcx, [rsp+48h+var_18]
0x1400079a2  xor     rcx, rsp; StackCookie
0x1400079a5  call    __security_check_cookie
0x1400079aa  mov     rbx, [rsp+48h+arg_10]
0x1400079af  mov     rsi, [rsp+48h+arg_18]
0x1400079b4  add     rsp, 40h
0x1400079b8  pop     rdi
0x1400079b9  retn
```
