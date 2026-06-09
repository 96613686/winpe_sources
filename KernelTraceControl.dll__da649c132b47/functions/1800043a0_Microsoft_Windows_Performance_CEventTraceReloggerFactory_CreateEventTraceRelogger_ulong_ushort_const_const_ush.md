# Microsoft::Windows::Performance::CEventTraceReloggerFactory::CreateEventTraceRelogger(ulong,ushort const * const *,ushort const *,Microsoft::Windows::Performance::IEventTraceExtender *,IUnknown *,_GUID const &,void * *)

- ea: `0x1800043a0`
- end: `0x18000447a`
- name: `?CreateEventTraceRelogger@CEventTraceReloggerFactory@Performance@Windows@Microsoft@@UEAAJKPEBQEBGPEBGPEAUIEventTraceExtender@234@PEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `218`
- prototype: `int(Microsoft::Windows::Performance::CEventTraceReloggerFactory *__hidden this, unsigned int, const unsigned __int16 *const *, const unsigned __int16 *, struct Microsoft::Windows::Performance::IEventTraceExtender *, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002af0`
- `0x1800043a0`
- `0x180005384`
- `0x180027910`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceReloggerFactory::CreateEventTraceRelogger(
        Microsoft::Windows::Performance::CEventTraceReloggerFactory *this,
        unsigned int a2,
        const unsigned __int16 *const *a3,
        const unsigned __int16 *a4,
        struct Microsoft::Windows::Performance::IEventTraceExtender *a5,
        struct IUnknown *a6,
        const struct _GUID *a7,
        void **a8)
{
  int Instance; // edi
  __int64 v13; // rbx
  _QWORD v14[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( a2 && !a3 || !a4 )
    return 2147500035LL;
  v14[0] = 0;
  Instance = ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance((char *)a6, v14);
  if ( Instance >= 0 )
  {
    v13 = v14[0];
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14[0] + 8LL))(v14[0]);
    Instance = Microsoft::Windows::Performance::CEventTraceRelogger::Init(
                 (Microsoft::Windows::Performance::CEventTraceRelogger *)(v13 + 16),
                 a2,
                 a3,
                 a4,
                 a5);
    if ( Instance >= 0 )
      Instance = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v13)(v13, a7, a8);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800043a0  mov     rax, rsp
0x1800043a3  mov     [rax+8], rbx
0x1800043a7  mov     [rax+10h], rbp
0x1800043ab  mov     [rax+18h], rsi
0x1800043af  mov     [rax+20h], rdi
0x1800043b3  push    r14
0x1800043b5  sub     rsp, 40h
0x1800043b9  mov     rsi, r9
0x1800043bc  mov     rbp, r8
0x1800043bf  mov     r14d, edx
0x1800043c2  test    edx, edx
0x1800043c4  jz      short loc_1800043D5
0x1800043c6  test    r8, r8
0x1800043c9  jnz     short loc_1800043D5
0x1800043cb  mov     eax, 80004003h
0x1800043d0  jmp     loc_18000445F
0x1800043d5  test    rsi, rsi
0x1800043d8  jz      short loc_1800043CB
0x1800043da  mov     rcx, [rsp+48h+arg_28]
0x1800043df  lea     rdx, [rsp+48h+var_18]
0x1800043e4  and     [rsp+48h+var_18], 0
0x1800043ea  call    ?CreateInstance@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@SAJPEAUIUnknown@@PEAPEAV12@@Z; ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(IUnknown *,ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger> * *)
0x1800043ef  mov     edi, eax
0x1800043f1  test    eax, eax
0x1800043f3  js      short loc_18000445D
0x1800043f5  mov     rbx, [rsp+48h+var_18]
0x1800043fa  mov     rcx, rbx
0x1800043fd  mov     rax, [rbx]
0x180004400  mov     rax, [rax+8]
0x180004404  call    cs:__guard_dispatch_icall_fptr
0x18000440a  mov     rax, [rsp+48h+arg_20]
0x18000440f  lea     rcx, [rbx+10h]; this
0x180004413  mov     r9, rsi; unsigned __int16 *
0x180004416  mov     [rsp+48h+var_28], rax; struct Microsoft::Windows::Performance::IEventTraceExtender *
0x18000441b  mov     r8, rbp; unsigned __int16 **
0x18000441e  mov     edx, r14d; unsigned int
0x180004421  call    ?Init@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAAJKPEBQEBGPEBGPEAUIEventTraceExtender@234@@Z; Microsoft::Windows::Performance::CEventTraceRelogger::Init(ulong,ushort const * const *,ushort const *,Microsoft::Windows::Performance::IEventTraceExtender *)
0x180004426  mov     edi, eax
0x180004428  test    eax, eax
0x18000442a  js      short loc_18000444D
0x18000442c  mov     rax, [rbx]
0x18000442f  mov     rcx, rbx
0x180004432  mov     r8, [rsp+48h+arg_38]
0x18000443a  mov     rdx, [rsp+48h+arg_30]
0x180004442  mov     rax, [rax]
0x180004445  call    cs:__guard_dispatch_icall_fptr
0x18000444b  mov     edi, eax
0x18000444d  mov     rax, [rbx]
0x180004450  mov     rcx, rbx
0x180004453  mov     rax, [rax+10h]
0x180004457  call    cs:__guard_dispatch_icall_fptr
0x18000445d  mov     eax, edi
0x18000445f  mov     rbx, [rsp+48h+arg_0]
0x180004464  mov     rbp, [rsp+48h+arg_8]
0x180004469  mov     rsi, [rsp+48h+arg_10]
0x18000446e  mov     rdi, [rsp+48h+arg_18]
0x180004473  add     rsp, 40h
0x180004477  pop     r14
0x180004479  retn
```
