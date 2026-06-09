# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x14000bdf0`
- end: `0x14000beae`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140009810`
- `0x14000a46c`

## callees

- `0x14000bdf0`
- `0x14000e1c0`
- `0x14000f010`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x14000be5d`
- `ADVAPI32!EventRegister` at `0x14000be5d`
- `ADVAPI32!EventSetInformation` at `0x14000be75`
- `ADVAPI32!EventSetInformation` at `0x14000be75`

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
0x14000bdf0  mov     [rsp+arg_10], rbx
0x14000bdf5  mov     [rsp+arg_18], rsi
0x14000bdfa  push    rdi
0x14000bdfb  sub     rsp, 40h
0x14000bdff  mov     rax, cs:__security_cookie
0x14000be06  xor     rax, rsp
0x14000be09  mov     [rsp+48h+var_18], rax
0x14000be0e  mov     [rcx+8], rdx
0x14000be12  lea     rsi, [rdx+20h]
0x14000be16  mov     byte ptr [rcx+10h], 1
0x14000be1a  mov     rdi, rdx
0x14000be1d  cmp     qword ptr [rsi], 0
0x14000be21  mov     rbx, rcx
0x14000be24  mov     rax, [rdx+8]
0x14000be28  movups  xmm0, xmmword ptr [rax-10h]
0x14000be2c  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x14000be32  jz      short loc_14000BE3B
0x14000be34  mov     ecx, 5
0x14000be39  int     29h; Win8: RtlFailFast(ecx)
0x14000be3b  mov     qword ptr [rdx+28h], 0
0x14000be43  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x14000be48  mov     qword ptr [rdx+30h], 0
0x14000be50  mov     r9, rsi; RegHandle
0x14000be53  lea     rdx, _tlgEnableCallback; EnableCallback
0x14000be5a  mov     r8, rdi; CallbackContext
0x14000be5d  call    cs:__imp_EventRegister
0x14000be63  test    eax, eax
0x14000be65  jnz     short loc_14000BE7B
0x14000be67  mov     r8, [rdi+8]
0x14000be6b  lea     edx, [rax+2]
0x14000be6e  mov     rcx, [rsi]
0x14000be71  movzx   r9d, word ptr [r8]
0x14000be75  call    cs:__imp_EventSetInformation
0x14000be7b  mov     rax, [rbx]
0x14000be7e  mov     rcx, rbx
0x14000be81  mov     dword ptr [rbx+14h], 1
0x14000be88  mov     rax, [rax+8]
0x14000be8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be91  mov     rcx, [rsp+48h+var_18]
0x14000be96  xor     rcx, rsp; StackCookie
0x14000be99  call    __security_check_cookie
0x14000be9e  mov     rbx, [rsp+48h+arg_10]
0x14000bea3  mov     rsi, [rsp+48h+arg_18]
0x14000bea8  add     rsp, 40h
0x14000beac  pop     rdi
0x14000bead  retn
```
