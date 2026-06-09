# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x180011f18`
- end: `0x180011fd6`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010d90`
- `0x1800203f8`

## callees

- `0x1800032a0`
- `0x180011f18`
- `0x18002c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180011f9d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180011f9d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180011f85`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180011f85`

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
0x180011f18  mov     [rsp+arg_10], rbx
0x180011f1d  mov     [rsp+arg_18], rsi
0x180011f22  push    rdi
0x180011f23  sub     rsp, 40h
0x180011f27  mov     rax, cs:__security_cookie
0x180011f2e  xor     rax, rsp
0x180011f31  mov     [rsp+48h+var_18], rax
0x180011f36  mov     [rcx+8], rdx
0x180011f3a  lea     rsi, [rdx+20h]
0x180011f3e  mov     byte ptr [rcx+10h], 1
0x180011f42  mov     rdi, rdx
0x180011f45  cmp     qword ptr [rsi], 0
0x180011f49  mov     rbx, rcx
0x180011f4c  mov     rax, [rdx+8]
0x180011f50  movups  xmm0, xmmword ptr [rax-10h]
0x180011f54  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x180011f5a  jz      short loc_180011F63
0x180011f5c  mov     ecx, 5
0x180011f61  int     29h; Win8: RtlFailFast(ecx)
0x180011f63  mov     qword ptr [rdx+28h], 0
0x180011f6b  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x180011f70  mov     qword ptr [rdx+30h], 0
0x180011f78  mov     r9, rsi; RegHandle
0x180011f7b  lea     rdx, _tlgEnableCallback; EnableCallback
0x180011f82  mov     r8, rdi; CallbackContext
0x180011f85  call    cs:__imp_EventRegister
0x180011f8b  test    eax, eax
0x180011f8d  jnz     short loc_180011FA3
0x180011f8f  mov     r8, [rdi+8]
0x180011f93  lea     edx, [rax+2]
0x180011f96  mov     rcx, [rsi]
0x180011f99  movzx   r9d, word ptr [r8]
0x180011f9d  call    cs:__imp_EventSetInformation
0x180011fa3  mov     rax, [rbx]
0x180011fa6  mov     rcx, rbx
0x180011fa9  mov     dword ptr [rbx+14h], 1
0x180011fb0  mov     rax, [rax+8]
0x180011fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fb9  mov     rcx, [rsp+48h+var_18]
0x180011fbe  xor     rcx, rsp; StackCookie
0x180011fc1  call    __security_check_cookie
0x180011fc6  mov     rbx, [rsp+48h+arg_10]
0x180011fcb  mov     rsi, [rsp+48h+arg_18]
0x180011fd0  add     rsp, 40h
0x180011fd4  pop     rdi
0x180011fd5  retn
```
