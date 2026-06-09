# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x140004bcc`
- end: `0x140004c8a`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400044dc`
- `0x140007410`

## callees

- `0x140001cd0`
- `0x140004bcc`
- `0x140008010`

## import_xrefs

- `ADVAPI32!EventSetInformation` at `0x140004c51`
- `ADVAPI32!EventSetInformation` at `0x140004c51`
- `ADVAPI32!EventRegister` at `0x140004c39`
- `ADVAPI32!EventRegister` at `0x140004c39`

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
0x140004bcc  mov     [rsp+arg_10], rbx
0x140004bd1  mov     [rsp+arg_18], rsi
0x140004bd6  push    rdi
0x140004bd7  sub     rsp, 40h
0x140004bdb  mov     rax, cs:__security_cookie
0x140004be2  xor     rax, rsp
0x140004be5  mov     [rsp+48h+var_18], rax
0x140004bea  mov     [rcx+8], rdx
0x140004bee  lea     rsi, [rdx+20h]
0x140004bf2  mov     byte ptr [rcx+10h], 1
0x140004bf6  mov     rdi, rdx
0x140004bf9  cmp     qword ptr [rsi], 0
0x140004bfd  mov     rbx, rcx
0x140004c00  mov     rax, [rdx+8]
0x140004c04  movups  xmm0, xmmword ptr [rax-10h]
0x140004c08  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x140004c0e  jz      short loc_140004C17
0x140004c10  mov     ecx, 5
0x140004c15  int     29h; Win8: RtlFailFast(ecx)
0x140004c17  mov     qword ptr [rdx+28h], 0
0x140004c1f  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x140004c24  mov     qword ptr [rdx+30h], 0
0x140004c2c  mov     r9, rsi; RegHandle
0x140004c2f  lea     rdx, _tlgEnableCallback; EnableCallback
0x140004c36  mov     r8, rdi; CallbackContext
0x140004c39  call    cs:__imp_EventRegister
0x140004c3f  test    eax, eax
0x140004c41  jnz     short loc_140004C57
0x140004c43  mov     r8, [rdi+8]
0x140004c47  lea     edx, [rax+2]
0x140004c4a  mov     rcx, [rsi]
0x140004c4d  movzx   r9d, word ptr [r8]
0x140004c51  call    cs:__imp_EventSetInformation
0x140004c57  mov     rax, [rbx]
0x140004c5a  mov     rcx, rbx
0x140004c5d  mov     dword ptr [rbx+14h], 1
0x140004c64  mov     rax, [rax+8]
0x140004c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c6d  mov     rcx, [rsp+48h+var_18]
0x140004c72  xor     rcx, rsp; StackCookie
0x140004c75  call    __security_check_cookie
0x140004c7a  mov     rbx, [rsp+48h+arg_10]
0x140004c7f  mov     rsi, [rsp+48h+arg_18]
0x140004c84  add     rsp, 40h
0x140004c88  pop     rdi
0x140004c89  retn
```
