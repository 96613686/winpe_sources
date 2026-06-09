# Microsoft::Windows::Performance::CEventTraceReloggerFactory::CreateEventTraceRelogger(ulong,ushort const * const *,ushort const *,Microsoft::Windows::Performance::IEventTraceExtender *,IUnknown *,_GUID const &,void * *)

- ea: `0x180004740`
- end: `0x180004802`
- name: `?CreateEventTraceRelogger@CEventTraceReloggerFactory@Performance@Windows@Microsoft@@UEAAJKPEBQEBGPEBGPEAUIEventTraceExtender@234@PEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `194`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceReloggerFactory *__hidden this, unsigned int, const unsigned __int16 *const *, const unsigned __int16 *, struct Microsoft::Windows::Performance::IEventTraceExtender *, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004740`
- `0x180004ab0`
- `0x180005740`
- `0x18002a010`

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
  _QWORD v14[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( a2 && !a3 || !a4 )
    return 2147500035LL;
  v14[0] = 0;
  Instance = ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(a6, v14);
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
0x180004740  push    rbx
0x180004742  push    rbp
0x180004743  push    rsi
0x180004744  push    rdi
0x180004745  push    r14
0x180004747  sub     rsp, 40h
0x18000474b  mov     rsi, r9
0x18000474e  mov     rbp, r8
0x180004751  mov     r14d, edx
0x180004754  test    edx, edx
0x180004756  jz      short loc_18000475D
0x180004758  test    r8, r8
0x18000475b  jz      short loc_180004762
0x18000475d  test    rsi, rsi
0x180004760  jnz     short loc_18000476C
0x180004762  mov     eax, 80004003h
0x180004767  jmp     loc_1800047F7
0x18000476c  mov     rcx, [rsp+68h+arg_28]
0x180004774  lea     rdx, [rsp+68h+var_38]
0x180004779  mov     [rsp+68h+var_38], 0
0x180004782  call    ?CreateInstance@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@SAJPEAUIUnknown@@PEAPEAV12@@Z; ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(IUnknown *,ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger> * *)
0x180004787  mov     edi, eax
0x180004789  test    eax, eax
0x18000478b  js      short loc_1800047F5
0x18000478d  mov     rbx, [rsp+68h+var_38]
0x180004792  mov     rcx, rbx
0x180004795  mov     rax, [rbx]
0x180004798  mov     rax, [rax+8]
0x18000479c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047a1  mov     rax, [rsp+68h+arg_20]
0x1800047a9  lea     rcx, [rbx+10h]; this
0x1800047ad  mov     r9, rsi; unsigned __int16 *
0x1800047b0  mov     [rsp+68h+var_48], rax; struct Microsoft::Windows::Performance::IEventTraceExtender *
0x1800047b5  mov     r8, rbp; unsigned __int16 **
0x1800047b8  mov     edx, r14d; unsigned int
0x1800047bb  call    ?Init@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAAJKPEBQEBGPEBGPEAUIEventTraceExtender@234@@Z; Microsoft::Windows::Performance::CEventTraceRelogger::Init(ulong,ushort const * const *,ushort const *,Microsoft::Windows::Performance::IEventTraceExtender *)
0x1800047c0  mov     edi, eax
0x1800047c2  test    eax, eax
0x1800047c4  js      short loc_1800047E6
0x1800047c6  mov     rax, [rbx]
0x1800047c9  mov     rcx, rbx
0x1800047cc  mov     r8, [rsp+68h+arg_38]
0x1800047d4  mov     rdx, [rsp+68h+arg_30]
0x1800047dc  mov     rax, [rax]
0x1800047df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047e4  mov     edi, eax
0x1800047e6  mov     rax, [rbx]
0x1800047e9  mov     rcx, rbx
0x1800047ec  mov     rax, [rax+10h]
0x1800047f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047f5  mov     eax, edi
0x1800047f7  add     rsp, 40h
0x1800047fb  pop     r14
0x1800047fd  pop     rdi
0x1800047fe  pop     rsi
0x1800047ff  pop     rbp
0x180004800  pop     rbx
0x180004801  retn
```
