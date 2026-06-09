# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x1800114a0`
- end: `0x180011559`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `185`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800119b0`
- `0x18002f6a0`

## callees

- `0x1800114a0`
- `0x180034ef0`
- `0x18003bed0`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x180011504`
- `ADVAPI32!EventRegister` at `0x180011504`
- `ADVAPI32!EventSetInformation` at `0x18001151f`
- `ADVAPI32!EventSetInformation` at `0x18001151f`

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
0x1800114a0  mov     [rsp+arg_10], rbx
0x1800114a5  mov     [rsp+arg_18], rsi
0x1800114aa  push    rdi
0x1800114ab  sub     rsp, 40h
0x1800114af  mov     rax, cs:__security_cookie
0x1800114b6  xor     rax, rsp
0x1800114b9  mov     [rsp+48h+var_18], rax
0x1800114be  mov     [rcx+8], rdx
0x1800114c2  mov     rdi, rdx
0x1800114c5  mov     byte ptr [rcx+10h], 1
0x1800114c9  mov     rbx, rcx
0x1800114cc  cmp     qword ptr [rdx+20h], 0
0x1800114d1  mov     rax, [rdx+8]
0x1800114d5  movups  xmm0, xmmword ptr [rax-10h]
0x1800114d9  movups  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x1800114de  jz      short loc_1800114E7
0x1800114e0  mov     ecx, 5
0x1800114e5  int     29h; Win8: RtlFailFast(ecx)
0x1800114e7  xor     eax, eax
0x1800114e9  lea     r9, [rdx+20h]; RegHandle
0x1800114ed  mov     [rdx+28h], rax
0x1800114f1  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x1800114f6  mov     [rdx+30h], rax
0x1800114fa  mov     r8, rdi; CallbackContext
0x1800114fd  lea     rdx, _tlgEnableCallback; EnableCallback
0x180011504  call    cs:__imp_EventRegister
0x18001150a  test    eax, eax
0x18001150c  jnz     short loc_180011525
0x18001150e  mov     r8, [rdi+8]
0x180011512  mov     edx, 2
0x180011517  mov     rcx, [rdi+20h]
0x18001151b  movzx   r9d, word ptr [r8]
0x18001151f  call    cs:__imp_EventSetInformation
0x180011525  mov     rax, [rbx]
0x180011528  mov     rcx, rbx
0x18001152b  mov     dword ptr [rbx+14h], 1
0x180011532  mov     rax, [rax+8]
0x180011536  call    cs:__guard_dispatch_icall_fptr
0x18001153c  mov     rcx, [rsp+48h+var_18]
0x180011541  xor     rcx, rsp; StackCookie
0x180011544  call    __security_check_cookie
0x180011549  mov     rbx, [rsp+48h+arg_10]
0x18001154e  mov     rsi, [rsp+48h+arg_18]
0x180011553  add     rsp, 40h
0x180011557  pop     rdi
0x180011558  retn
```
